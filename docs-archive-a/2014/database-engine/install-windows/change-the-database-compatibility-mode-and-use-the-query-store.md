---
title: Migrar planes de consulta | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- query plans [SQL Server], migrating
- upgrading SQL Server, migrating query plans
- plan guides [SQL Server], migrating query plans
ms.assetid: 7e02a137-6867-4f6a-a45a-2b02674f7e65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dafd3a5f8a460bb08e63919c2cb853ad74dc2f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747174"
---
# <a name="migrate-query-plans"></a><span data-ttu-id="94859-102">Migrar los planes de consulta</span><span class="sxs-lookup"><span data-stu-id="94859-102">Migrate Query Plans</span></span>
  <span data-ttu-id="94859-103">En la mayoría de los casos, al actualizar una base de datos a la versión más reciente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se obtendrá una mejora del rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="94859-103">In most cases, upgrading a database to the most recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will result in improved query performance.</span></span> <span data-ttu-id="94859-104">No obstante, si tiene consultas de gran importancia que se han optimizado cuidadosamente con el fin de obtener el máximo rendimiento, es probable que desee conservar los planes de consulta de dichas consultas antes de llevar a cabo la actualización mediante la creación de una guía de plan para cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="94859-104">However, if you have mission-critical queries that have been carefully tuned for performance, you may want to preserve the query plans for these queries before upgrading by creating a plan guide for each query.</span></span> <span data-ttu-id="94859-105">Si tras la actualización, el optimizador de consultas elige un plan menos eficiente para una o varias de las consultas, podrá habilitar las guías de plan y obligar al optimizador de consultas a utilizar los planes previos a la actualización.</span><span class="sxs-lookup"><span data-stu-id="94859-105">If, after upgrading, the query optimizer chooses a less efficient plan for one or more of the queries, you can enable the plan guides and force the query optimizer to use the pre-upgrade plans.</span></span>  
  
 <span data-ttu-id="94859-106">Siga estos pasos para crear planes de guía antes de llevar a cabo la actualización:</span><span class="sxs-lookup"><span data-stu-id="94859-106">To create plan guides before upgrading follow these steps:</span></span>  
  
1.  <span data-ttu-id="94859-107">Registre el plan actual para cada consulta de misión crítica mediante el [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) procedimiento almacenado y especificando el plan de consulta en la sugerencia de consulta use plan.</span><span class="sxs-lookup"><span data-stu-id="94859-107">Record the current plan for each mission critical query by using the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure and specifying the query plan in the USE PLAN query hint.</span></span>  
  
2.  <span data-ttu-id="94859-108">Compruebe que la guía de plan se aplica a la consulta.</span><span class="sxs-lookup"><span data-stu-id="94859-108">Verify that the plan guide is applied to the query.</span></span>  
  
3.  <span data-ttu-id="94859-109">Actualice la base de datos a la versión más reciente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94859-109">Upgrade the database to the newer version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="94859-110">Los planes se conservan en las guías de plan residentes en la base en datos actualizada y sirven de reserva en caso de regresión de los planes tras la actualización.</span><span class="sxs-lookup"><span data-stu-id="94859-110">The plans are persisted in the upgraded database in the plan guides and serve as a fallback in case of plan regressions after the upgrade.</span></span>  
  
     <span data-ttu-id="94859-111">Recomendamos no habilitar las guías de plan tras la actualización, ya que es posible que se pierdan oportunidades de conseguir mejores planes en la nueva versión o recompilaciones beneficiosas gracias a las estadísticas actualizadas.</span><span class="sxs-lookup"><span data-stu-id="94859-111">We recommend that you not enable the plan guides after the upgrade because you might miss opportunities for better plans in the new release or beneficial recompiles due to updated statistics.</span></span>  
  
4.  <span data-ttu-id="94859-112">Si tras la actualización se escogen planes menos eficientes, active todas las guías de plan o bien solo un subconjunto de ellas con el fin de invalidar los nuevos planes.</span><span class="sxs-lookup"><span data-stu-id="94859-112">If less efficient plans are chosen after the upgrade, activate all or a subset of the plan guides to override the new plans.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94859-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94859-113">Example</span></span>  
 <span data-ttu-id="94859-114">En el siguiente ejemplo se muestra cómo registrar un plan para una consulta antes de la actualización por medio de la creación de una guía de plan.</span><span class="sxs-lookup"><span data-stu-id="94859-114">The following example shows how to record a pre-upgrade plan for a query by creating a plan guide.</span></span>  
  
### <a name="step-1-collect-the-plan"></a><span data-ttu-id="94859-115">Paso 1: recopilar el plan</span><span class="sxs-lookup"><span data-stu-id="94859-115">Step 1: Collect the Plan</span></span>  
 <span data-ttu-id="94859-116">El plan de consulta registrado en la guía de plan debe estar en formato XML.</span><span class="sxs-lookup"><span data-stu-id="94859-116">The query plan recorded in the plan guide must be in XML format.</span></span> <span data-ttu-id="94859-117">Es posible generar planes de consulta en formato XML de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="94859-117">XML-formatted query plans can be produced through the following ways:</span></span>  
  
-   [<span data-ttu-id="94859-118">SET SHOWPLAN_XML</span><span class="sxs-lookup"><span data-stu-id="94859-118">SET SHOWPLAN_XML</span></span>](/sql/t-sql/statements/set-showplan-xml-transact-sql)  
  
-   [<span data-ttu-id="94859-119">SET STATISTICS XML</span><span class="sxs-lookup"><span data-stu-id="94859-119">SET STATISTICS XML</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
-   <span data-ttu-id="94859-120">Consultar el query_plan columna de la función de administración dinámica [Sys. dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="94859-120">Querying the query_plan column of the [sys.dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) dynamic management function.</span></span>  
  
-   <span data-ttu-id="94859-121">Las [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] clases de eventos [SHOWPLAN XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [SHOWPLAN XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md)y [SHOWPLAN XML for Query compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) .</span><span class="sxs-lookup"><span data-stu-id="94859-121">The [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] [Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md), and [Showplan XML For Query Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) event classes.</span></span>  
  
 <span data-ttu-id="94859-122">En el siguiente ejemplo se recopila el plan de consulta para la instrucción `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` mediante la consulta a vistas de administración dinámica.</span><span class="sxs-lookup"><span data-stu-id="94859-122">The following example collects the query plan for the statement `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` by querying dynamic management views.</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%';  
GO  
```  
  
### <a name="step-2-create-the-plan-guide-to-force-the-plan"></a><span data-ttu-id="94859-123">Paso 2: crear la guía de plan para imponer el plan</span><span class="sxs-lookup"><span data-stu-id="94859-123">Step 2: Create the Plan Guide to Force the Plan</span></span>  
 <span data-ttu-id="94859-124">Utilizando el plan de consulta con formato XML (obtenido mediante cualquiera de los métodos explicados) en la guía de plan, copie y pegue el plan de consulta como un literal de cadena en la sugerencia de consulta USE PLAN especificada en la cláusula OPTION de sp_create_plan_guide.</span><span class="sxs-lookup"><span data-stu-id="94859-124">Using the XML-formatted query plan (obtained by any of the methods previously described) in the plan guide, copy and paste the query plan as a string literal inside the USE PLAN query hint specified in the OPTION clause of sp_create_plan_guide.</span></span>  
  
 <span data-ttu-id="94859-125">Dentro del propio plan XML, escape las comillas (') que aparezcan en el plan antes de crear la guía de plan, insertando para ello unas segundas comillas.</span><span class="sxs-lookup"><span data-stu-id="94859-125">Within the XML plan itself, escape quotation marks (') that appear in the plan with a second quotation mark before creating the plan guide.</span></span> <span data-ttu-id="94859-126">Por ejemplo, a un plan que contiene `WHERE A.varchar = 'This is a string'` habrá que agregarle unas segundas comillas para que el código quede `WHERE A.varchar = ''This is a string''`.</span><span class="sxs-lookup"><span data-stu-id="94859-126">For example, a plan that contains `WHERE A.varchar = 'This is a string'` must be escaped by modifying the code to `WHERE A.varchar = ''This is a string''`.</span></span>  
  
 <span data-ttu-id="94859-127">En el ejemplo siguiente se crea una guía de plan para el plan de consulta recopilado en el paso 1, y se inserta el XML Showplan par la consulta en el parámetro `@hints`.</span><span class="sxs-lookup"><span data-stu-id="94859-127">The following example creates a plan guide for the query plan collected in step 1 and inserts the XML Showplan for the query in the `@hints` parameter.</span></span> <span data-ttu-id="94859-128">Por razones de brevedad, el ejemplo solo incluye resultados parciales de Showplan.</span><span class="sxs-lookup"><span data-stu-id="94859-128">For brevity, only partial Showplan output is included in the example.</span></span>  
  
```  
EXECUTE sp_create_plan_guide   
@name = N'Guide1',  
@stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',  
@type = N'SQL',  
@module_or_batch = NULL,  
@params = NULL,  
@hints = N'OPTION(USE PLAN N''<ShowPlanXML xmlns=''''https://schemas.microsoft.com/sqlserver/2004/07/showplan''''   
    Version=''''0.5'''' Build=''''9.00.1116''''>  
    <BatchSequence><Batch><Statements><StmtSimple>  
    ...  
    </StmtSimple></Statements></Batch>  
    </BatchSequence></ShowPlanXML>'')';  
GO  
```  
  
### <a name="step-3-verify-that-the-plan-guide-is-applied-to-the-query"></a><span data-ttu-id="94859-129">Paso 3: comprobar que la guía de plan corresponde a la consulta</span><span class="sxs-lookup"><span data-stu-id="94859-129">Step 3: Verify That the Plan Guide Is Applied to the Query</span></span>  
 <span data-ttu-id="94859-130">Vuelva a ejecutar la consulta y examine el plan de consulta generado.</span><span class="sxs-lookup"><span data-stu-id="94859-130">Run the query again and examine the query plan that is produced.</span></span> <span data-ttu-id="94859-131">Observará que el plan coincide con el plan especificado en la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="94859-131">You should see that the plan matches the one that you specified in the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94859-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94859-132">See Also</span></span>  
 <span data-ttu-id="94859-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="94859-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="94859-134">[Sugerencias de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="94859-134">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="94859-135">Guías de plan</span><span class="sxs-lookup"><span data-stu-id="94859-135">Plan Guides</span></span>](../../relational-databases/performance/plan-guides.md)  
  
  
