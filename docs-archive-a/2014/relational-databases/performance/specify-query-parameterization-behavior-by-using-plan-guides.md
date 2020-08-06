---
title: Especificar el comportamiento de parametrización de consultas por medio de guías de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- TEMPLATE plan guide
- PARAMETERIZATION FORCED option
- PARAMETERIZATION option
- PARAMETERIZATION SIMPLE option
- parameterization [SQL Server]
- overriding parameterization behavior
- plan guides [SQL Server], parameterization
- parameterized queries [SQL Server]
ms.assetid: f0f738ff-2819-4675-a8c8-1eb6c210a7e6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f595b9f0e0a6d7bceffc5cb283c60b6f40e025b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677598"
---
# <a name="specify-query-parameterization-behavior-by-using-plan-guides"></a><span data-ttu-id="bcbd1-102">Especificar el comportamiento de parametrización de consultas por medio de guías de plan</span><span class="sxs-lookup"><span data-stu-id="bcbd1-102">Specify Query Parameterization Behavior by Using Plan Guides</span></span>
  <span data-ttu-id="bcbd1-103">Cuando la opción de base de datos PARAMETERIZATION se establece en SIMPLE, el optimizador de consultas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede optar por parametrizar las consultas.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-103">When the PARAMETERIZATION database option is set to SIMPLE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer may choose to parameterize the queries.</span></span> <span data-ttu-id="bcbd1-104">Esto quiere decir que todos los valores literales incluidos en una consulta se sustituirán por parámetros.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-104">This means that any literal values that are contained in a query are substituted with parameters.</span></span> <span data-ttu-id="bcbd1-105">Este proceso se conoce como parametrización simple.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-105">This process is referred to as simple parameterization.</span></span> <span data-ttu-id="bcbd1-106">Cuando la parametrización SIMPLE está habilitada, no se pueden controlar las consultas que se parametrizarán y las que no.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-106">When SIMPLE parameterization is in effect, you cannot control which queries are parameterized and which queries are not.</span></span> <span data-ttu-id="bcbd1-107">No obstante, puede especificar que todas las consultas de una base de datos se parametricen estableciendo la opción PARAMETERIZATION de base de datos en FORCED.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-107">However, you can specify that all queries in a database be parameterized by setting the PARAMETERIZATION database option to FORCED.</span></span> <span data-ttu-id="bcbd1-108">Este proceso se conoce como parametrización forzada.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-108">This process is referred to as forced parameterization.</span></span>  
  
 <span data-ttu-id="bcbd1-109">Puede cambiar el comportamiento de parametrización de una base de datos por medio de guías de plan tal y como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="bcbd1-109">You can override the parameterization behavior of a database by using plan guides in the following ways:</span></span>  
  
-   <span data-ttu-id="bcbd1-110">Cuando la opción PARAMETERIZATION de base de datos se establece en SIMPLE, puede especificar que se intente realizar una parametrización forzada en una clase determinada de consultas.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-110">When the PARAMETERIZATION database option is set to SIMPLE, you can specify that forced parameterization is attempted on a certain class of queries.</span></span> <span data-ttu-id="bcbd1-111">Para ello, cree una guía de plan TEMPLATE en la consulta con parámetros y especifique la sugerencia de consulta PARAMETERIZATION FORCED en el procedimiento almacenado [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="bcbd1-111">You do this by creating a TEMPLATE plan guide on the parameterized form of the query, and specifying the PARAMETERIZATION FORCED query hint in the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure.</span></span> <span data-ttu-id="bcbd1-112">Puede considerar este tipo de guía de plan como una forma de habilitar la parametrización forzada solo para una determinada clase de consultas, no para todas.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-112">You can consider this kind of plan guide as a way to enable forced parameterization only on a certain class of queries, instead of all queries.</span></span>  
  
-   <span data-ttu-id="bcbd1-113">Cuando la opción PARAMETERIZATION de la base de datos se establece en FORCED, puede especificar que para una clase determinada de consultas se intente solamente realizar la parametrización simple, y no la parametrización forzada.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-113">When the PARAMETERIZATION database option is set to FORCED, you can specify that for a certain class of queries, only simple parameterization is attempted, not forced parameterization.</span></span> <span data-ttu-id="bcbd1-114">Para ello, cree una guía de plan TEMPLATE en la consulta con parametrización forzada y especifique la sugerencia de consulta PARAMETERIZATION SIMPLE en el procedimiento almacenado **sp_create_plan_guide**.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-114">You do this by creating a TEMPLATE plan guide on the force-parameterized form of the query, and specifying the PARAMETERIZATION SIMPLE query hint in **sp_create_plan_guide**.</span></span>  
  
 <span data-ttu-id="bcbd1-115">Fíjese en la consulta siguiente en la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="bcbd1-115">Consider the following query on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT pi.ProductID, SUM(pi.Quantity) AS Total  
FROM Production.ProductModel AS pm   
    INNER JOIN Production.ProductInventory AS pi   
        ON pm.ProductModelID = pi.ProductID   
WHERE pi.ProductID = 101   
GROUP BY pi.ProductID, pi.Quantity HAVING SUM(pi.Quantity) > 50;  
```  
  
 <span data-ttu-id="bcbd1-116">Como administrador de base de datos, ha decidido que no desea habilitar la parametrización forzada para todas las consultas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-116">As a database administrator, you have determined that you do not want to enable forced parameterization on all queries in the database.</span></span> <span data-ttu-id="bcbd1-117">No obstante, desea evitar los costos de compilación en todas las consultas que son sintácticamente equivalentes a consultas anteriores y que solo difieren en los valores literales constantes.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-117">However, you do want to avoid compilation costs on all queries that are syntactically equivalent to the previous query, but differ only in their constant literal values.</span></span> <span data-ttu-id="bcbd1-118">En otras palabras, desea que la consulta se parametrice para poder reutilizar un plan de consulta.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-118">In other words, you want the query to be parameterized so that a query plan for this kind of query is reused.</span></span> <span data-ttu-id="bcbd1-119">En este caso, siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bcbd1-119">In this case, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="bcbd1-120">Recupere la consulta con parámetros.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-120">Retrieve the parameterized form of the query.</span></span> <span data-ttu-id="bcbd1-121">El único modo seguro de obtener este valor para usarlo en **sp_create_plan_guide** consiste en usar el procedimiento almacenado del sistema [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="bcbd1-121">The only safe way to obtain this value for use in **sp_create_plan_guide** is by using the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span>  
  
2.  <span data-ttu-id="bcbd1-122">Cree la guía de plan en la consulta con parámetros, especificando la sugerencia de consulta PARAMETERIZATION FORCED.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-122">Create the plan guide on the parameterized form of the query, specifying the PARAMETERIZATION FORCED query hint.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="bcbd1-123">Como parte de la parametrización de una consulta, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asigna un tipo de datos a los parámetros que reemplazan a los valores literales, dependiendo del valor y el tamaño del literal.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-123">As part of parameterizing a query, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns a data type to the parameters that replace the literal values, depending on the value and size of the literal.</span></span> <span data-ttu-id="bcbd1-124">El mismo proceso se produce en el valor de los literales de constante pasados al **@stmt** parámetro de salida de **sp_get_query_template**.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-124">The same process occurs to the value of the constant literals passed to the **@stmt** output parameter of **sp_get_query_template**.</span></span> <span data-ttu-id="bcbd1-125">Dado que el tipo de datos especificado en el **@params** argumento de **sp_create_plan_guide** debe coincidir con el de la consulta, es [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] posible que tenga que crear más de una guía de plan para cubrir el intervalo completo de posibles valores de parámetro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-125">Because the data type specified in the **@params** argument of **sp_create_plan_guide** must match that of the query as it is parameterized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you may have to create more than one plan guide to cover the complete range of possible parameter values for the query.</span></span>  
  
 <span data-ttu-id="bcbd1-126">El siguiente script puede utilizarse para obtener la consulta con parámetros y, a continuación, crear una guía de plan en ella.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-126">The following script can be used both to obtain the parameterized query and then create a plan guide on it:</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT pi.ProductID, SUM(pi.Quantity) AS Total   
      FROM Production.ProductModel AS pm   
      INNER JOIN Production.ProductInventory AS pi ON pm.ProductModelID = pi.ProductID   
      WHERE pi.ProductID = 101   
      GROUP BY pi.ProductID, pi.Quantity   
      HAVING sum(pi.Quantity) > 50',  
    @stmt OUTPUT,   
    @params OUTPUT;  
EXEC sp_create_plan_guide   
    N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="bcbd1-127">Asimismo, en una base de datos en la que ya esté habilitada la parametrización forzada, puede asegurarse de que la consulta de ejemplo y otras consultas sintácticamente equivalentes, salvo por sus valores literales constantes, tengan parámetros definidos según las reglas de parametrización simple.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-127">Similarly, in a database in which forced parameterization is already enabled, you can make sure that the sample query, and others that are syntactically equivalent, except for their constant literal values, are parameterized according to the rules of simple parameterization.</span></span> <span data-ttu-id="bcbd1-128">Para ello, especifique PARAMETERIZATION SIMPLE, en lugar de PARAMETERIZATION FORCED, en la cláusula OPTION.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-128">To do this, specify PARAMETERIZATION SIMPLE instead of PARAMETERIZATION FORCED in the OPTION clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bcbd1-129">Las guías de plan TEMPLATE asocian las instrucciones con las consultas enviadas en lotes que están formadas solamente por una instrucción.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-129">TEMPLATE plan guides match statements to queries submitted in batches that consist of a single statement only.</span></span> <span data-ttu-id="bcbd1-130">Las instrucciones incluidas en lotes de varias instrucciones no tienen la posibilidad de ser elegidas por las guías de plan TEMPLATE.</span><span class="sxs-lookup"><span data-stu-id="bcbd1-130">Statements inside multistatement batches are not eligible to be matched by TEMPLATE plan guides.</span></span>  
  
  
