---
title: Usar SQL Server Profiler para crear y probar guías de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- checking plan guides
- plan guides [SQL Server], testing
- plan guides [SQL Server], SQL Server Profiler
- matching queries to plan guides [SQL Server]
- testing plan guides
- SQL Server Profiler, plan guides
- plan guides [SQL Server], creating
- capturing query text [SQL Server]
- verifying plan guides
- Profiler [SQL Server Profiler], plan guides
- query-to-plan guide matching [SQL Server]
ms.assetid: 7018dbf0-1a1a-411a-88af-327bedf9cfbd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 543905343d74c9fbabe5f671d9021657ea5f76b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746254"
---
# <a name="use-sql-server-profiler-to-create-and-test-plan-guides"></a><span data-ttu-id="91937-102">Usar SQL Server Profiler para crear y probar guías de plan</span><span class="sxs-lookup"><span data-stu-id="91937-102">Use SQL Server Profiler to Create and Test Plan Guides</span></span>
  <span data-ttu-id="91937-103">Cuando cree una guía de plan, puede usar [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para capturar el texto exacto de la consulta con el fin de usarlo en el argumento *statement_text* del procedimiento almacenado **sp_create_plan_guide** .</span><span class="sxs-lookup"><span data-stu-id="91937-103">When you are creating a plan guide, you can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to capture the exact query text for use in the *statement_text* argument of the **sp_create_plan_guide** stored procedure.</span></span> <span data-ttu-id="91937-104">Esto contribuye a garantizar que la guía de plan coincidirá con la consulta en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="91937-104">This helps make sure that the plan guide will be matched to the query at compile time.</span></span> <span data-ttu-id="91937-105">Una vez creada la guía de plan, se puede utilizar también el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para probar que, realmente, esa guía de plan coincidirá con la consulta.</span><span class="sxs-lookup"><span data-stu-id="91937-105">After the plan guide is created, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can also be used to test that the plan guide is, in fact, being matched to the query.</span></span> <span data-ttu-id="91937-106">Por lo general, debe probar las guías de plan mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para comprobar que se buscan las coincidencias de la consulta con la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="91937-106">Generally, you should test plan guides by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to verify that your query is being matched to your plan guide.</span></span>  
  
## <a name="capturing-query-text-by-using-sql-server-profiler"></a><span data-ttu-id="91937-107">Capturar texto de consulta utilizando SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="91937-107">Capturing Query Text by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="91937-108">Si ejecuta una consulta y captura el texto exactamente como se envió a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], puede crear una guía de plan de tipo SQL o TEMPLATE que coincidirá exactamente con el texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="91937-108">If you run a query and capture the text exactly as it was submitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can create a plan guide of type SQL or TEMPLATE that will match the query text exactly.</span></span> <span data-ttu-id="91937-109">Esto garantiza que el optimizador de consultas utiliza la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="91937-109">This makes sure that the plan guide is used by the query optimizer.</span></span>  
  
 <span data-ttu-id="91937-110">Considere la siguiente consulta que envía una aplicación como lote independiente:</span><span class="sxs-lookup"><span data-stu-id="91937-110">Consider the following query that is submitted by an application as a stand-alone batch:</span></span>  
  
```  
SELECT COUNT(*) AS c  
FROM Sales.SalesOrderHeader AS h  
INNER JOIN Sales.SalesOrderDetail AS d  
  ON h.SalesOrderID = d.SalesOrderID  
WHERE h.OrderDate BETWEEN '20000101' and '20050101';  
```  
  
 <span data-ttu-id="91937-111">Imagine que desea ejecutar esta consulta utilizando una operación de combinación de mezcla, pero SHOWPLAN indica que la consulta no utiliza una combinación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="91937-111">Suppose you want this query to execute using a merge join operation, but SHOWPLAN indicates that the query is not using a merge join.</span></span> <span data-ttu-id="91937-112">No puede cambiar la consulta directamente en la aplicación; por tanto, en su lugar crea una guía de plan para especificar que se adjunte la sugerencia de consulta MERGE JOIN a la consulta en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="91937-112">You cannot change the query directly in the application, so instead you create a plan guide to specify that the MERGE JOIN query hint be appended to the query at compile time.</span></span>  
  
 <span data-ttu-id="91937-113">Para capturar el texto de la consulta exactamente como lo recibe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="91937-113">To capture the text of the query exactly as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] receives it, follow these steps:</span></span>  
  
1.  <span data-ttu-id="91937-114">Inicie un seguimiento del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , asegurándose de que selecciona el tipo de evento **SQL:BatchStarting** .</span><span class="sxs-lookup"><span data-stu-id="91937-114">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making sure that the **SQL:BatchStarting** event type is selected.</span></span>  
  
2.  <span data-ttu-id="91937-115">Haga que la aplicación ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="91937-115">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="91937-116">Pause el seguimiento del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91937-116">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="91937-117">Haga clic en el evento **SQL:BatchStarting** que corresponde a la consulta.</span><span class="sxs-lookup"><span data-stu-id="91937-117">Click the **SQL:BatchStarting** event that corresponds to the query.</span></span>  
  
5.  <span data-ttu-id="91937-118">Haga clic con el botón derecho y seleccione **Extraer datos de evento**.</span><span class="sxs-lookup"><span data-stu-id="91937-118">Right-click and select **Extract Event Data**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="91937-119">No intente copiar el texto del lote seleccionándolo del panel inferior de la ventana de Seguimiento de SQL Server Profiler.</span><span class="sxs-lookup"><span data-stu-id="91937-119">Do not try to copy the batch text by selecting it from the lower pane of the Profiler trace window.</span></span> <span data-ttu-id="91937-120">Esto puede dar lugar a que la guía de plan que cree no coincida con el lote original.</span><span class="sxs-lookup"><span data-stu-id="91937-120">This might cause the plan guide that you create to not match the original batch.</span></span>  
  
6.  <span data-ttu-id="91937-121">Guarde los datos del evento en un archivo.</span><span class="sxs-lookup"><span data-stu-id="91937-121">Save the event data to a file.</span></span> <span data-ttu-id="91937-122">Éste es el texto del lote.</span><span class="sxs-lookup"><span data-stu-id="91937-122">This is the batch text.</span></span>  
  
7.  <span data-ttu-id="91937-123">Abra el archivo de texto del lote en el Bloc de notas y copie el texto en el búfer de copiar y pegar.</span><span class="sxs-lookup"><span data-stu-id="91937-123">Open the batch text file in Notepad and copy the text to the copy and paste buffer.</span></span>  
  
8.  <span data-ttu-id="91937-124">Cree la guía de plan y pegue el texto copiado entre las comillas (**''**) especificadas para el argumento **@stmt** .</span><span class="sxs-lookup"><span data-stu-id="91937-124">Create the plan guide and paste the copied text inside the quotation marks (**''**) specified for the **@stmt** argument.</span></span> <span data-ttu-id="91937-125">Debe anteponer las comillas simples en el **@stmt** argumento, precedidos por otra comilla simple.</span><span class="sxs-lookup"><span data-stu-id="91937-125">You must escape any single quotation marks in the **@stmt** argument by preceding them with another single quotation mark.</span></span> <span data-ttu-id="91937-126">Al insertar estas comillas simples, tenga cuidado de no agregar ni quitar ningún otro carácter.</span><span class="sxs-lookup"><span data-stu-id="91937-126">Be careful not to add or remove any other characters when you insert these single quotation marks.</span></span> <span data-ttu-id="91937-127">Por ejemplo, el literal de fecha **'** 20000101 **'** debe delimitarse como **''** 20000101 **''** .</span><span class="sxs-lookup"><span data-stu-id="91937-127">For example, the date literal **'** 20000101 **'** must be delimited as **''** 20000101 **''**.</span></span>  
  
 <span data-ttu-id="91937-128">Ésta es la guía de plan:</span><span class="sxs-lookup"><span data-stu-id="91937-128">Here is the plan guide:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'MyGuide1',  
    @stmt = N'<paste the text copied from the batch text file here>',  
    @type = N'SQL',  
    @module_or_batch = NULL,  
    @params = NULL,  
    @hints = N'OPTION (MERGE JOIN)';  
```  
  
## <a name="testing-plan-guides-by-using-sql-server-profiler"></a><span data-ttu-id="91937-129">Probar guías de plan utilizando SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="91937-129">Testing Plan Guides by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="91937-130">Para comprobar que una guía de plan coincide con una consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="91937-130">To verify that a plan guide is being matched to a query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="91937-131">Inicie un seguimiento de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , asegurándose de seleccionar el tipo de evento **Showplan XML** (ubicado en el nodo **Performance** ).</span><span class="sxs-lookup"><span data-stu-id="91937-131">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making certain that the **Showplan XML** event type is selected (located under the **Performance** node).</span></span>  
  
2.  <span data-ttu-id="91937-132">Haga que la aplicación ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="91937-132">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="91937-133">Pause el seguimiento del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91937-133">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="91937-134">Busque el evento **Showplan XML** de la consulta afectada.</span><span class="sxs-lookup"><span data-stu-id="91937-134">Find the **Showplan XML** event for the affected query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91937-135">No se puede utilizar el evento **Showplan XML for Query Compile** .</span><span class="sxs-lookup"><span data-stu-id="91937-135">The **Showplan XML for Query Compile** event cannot be used.</span></span> <span data-ttu-id="91937-136">**PlanGuideDB** no existe en ese evento.</span><span class="sxs-lookup"><span data-stu-id="91937-136">**PlanGuideDB** does not exist in that event.</span></span>  
  
5.  <span data-ttu-id="91937-137">Si la guía de plan es de tipo OBJECT o SQL, compruebe que el evento **Showplan XML** contiene los atributos **PlanGuideDB** y **PlanGuideName** para la guía de plan que espera que coincida con la consulta.</span><span class="sxs-lookup"><span data-stu-id="91937-137">If the plan guide is of type OBJECT or SQL, verify that the **Showplan XML** event contains the **PlanGuideDB** and **PlanGuideName** attributes for the plan guide that you expected to match the query.</span></span> <span data-ttu-id="91937-138">O bien, en el caso de una guía de plan TEMPLATE, compruebe que el evento **Showplan XML** contiene los atributos **TemplatePlanGuideDB** y **TemplatePlanGuideName** de la guía de plan que se espera.</span><span class="sxs-lookup"><span data-stu-id="91937-138">Or, in the case of a TEMPLATE plan guide, verify that the **Showplan XML** event contains the **TemplatePlanGuideDB** and **TemplatePlanGuideName** attributes for the expected plan guide.</span></span> <span data-ttu-id="91937-139">Esto comprueba que la guía de plan funciona.</span><span class="sxs-lookup"><span data-stu-id="91937-139">This verifies that the plan guide is working.</span></span> <span data-ttu-id="91937-140">Estos atributos se incluyen en el elemento del plan de **\<StmtSimple>** .</span><span class="sxs-lookup"><span data-stu-id="91937-140">These attributes are contained under the **\<StmtSimple>** element of the plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91937-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91937-141">See Also</span></span>  
 [<span data-ttu-id="91937-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91937-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)  
  
  
