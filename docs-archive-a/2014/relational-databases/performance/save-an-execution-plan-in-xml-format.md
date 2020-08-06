---
title: Guardar un plan de ejecución en formato XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- XML query plans [SQL Server]
- opening execution plans
- XML Showplans [SQL Server]
- execution plans [SQL Server], saving
- saving execution plans
ms.assetid: c439e53b-56f3-4442-97c6-dabd48a203d8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 84ed341d186993ed77260e8361156b324c597839
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674772"
---
# <a name="save-an-execution-plan-in-xml-format"></a><span data-ttu-id="4b428-102">Guardar un plan de ejecución en formato XML</span><span class="sxs-lookup"><span data-stu-id="4b428-102">Save an Execution Plan in XML Format</span></span>
  <span data-ttu-id="4b428-103">Utilice [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para guardar planes de ejecución como archivos XML y para visualizarlos.</span><span class="sxs-lookup"><span data-stu-id="4b428-103">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to save execution plans as an XML file, and to open them for viewing.</span></span>  
  
 <span data-ttu-id="4b428-104">Para utilizar la característica de plan de ejecución en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]o para usar las opciones SET del plan de presentación XML, los usuarios deben disponer de los permisos adecuados para ejecutar la consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] para la que se está generando un plan de ejecución y deben tener el permiso SHOWPLAN para todas las bases de datos a las que haga referencia la consulta.</span><span class="sxs-lookup"><span data-stu-id="4b428-104">To use the execution plan feature in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or to use the XML Showplan SET options, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which an execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-save-a-query-plan-by-using-the-xml-showplan-set-options"></a><span data-ttu-id="4b428-105">Para guardar un plan de consulta mediante las opciones SET del plan de presentación XML</span><span class="sxs-lookup"><span data-stu-id="4b428-105">To save a query plan by using the XML Showplan SET options</span></span>  
  
1.  <span data-ttu-id="4b428-106">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , abra un editor de consultas y conéctese a [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b428-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] open a query editor and connect to [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4b428-107">Active SHOWPLAN_XML con la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="4b428-107">Turn SHOWPLAN_XML on with the following statement:</span></span>  
  
    ```  
    SET SHOWPLAN_XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="4b428-108">Para activar STATISTICS XML, utilice la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="4b428-108">To turn STATISTICS XML on, use the following statement:</span></span>  
  
    ```  
    SET STATISTICS XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="4b428-109">SHOWPLAN_XML genera información del plan de ejecución de la consulta de tiempo de compilación de una consulta, pero no ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="4b428-109">SHOWPLAN_XML generates compile-time query execution plan information for a query, but does not execute the query.</span></span> <span data-ttu-id="4b428-110">STATISTICS XML genera información del plan de ejecución de la consulta de tiempo de compilación de una consulta y ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="4b428-110">STATISTICS XML generates run-time query execution plan information for a query, and executes the query.</span></span>  
  
3.  <span data-ttu-id="4b428-111">Ejecutar una consulta.</span><span class="sxs-lookup"><span data-stu-id="4b428-111">Execute a query.</span></span> <span data-ttu-id="4b428-112">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b428-112">Example:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SET SHOWPLAN_XML ON;  
    GO  
    -- Execute a query.  
    SELECT BusinessEntityID   
    FROM HumanResources.Employee  
    WHERE NationalIDNumber = '509647174';  
    GO  
    SET SHOWPLAN_XML OFF;  
    ```  
  
4.  <span data-ttu-id="4b428-113">En el panel **Resultados** , haga clic con el botón derecho en el **Plan de presentación XML de Microsoft SQL Server** que contiene el plan de consulta y, después, haga clic en **Guardar resultados como**.</span><span class="sxs-lookup"><span data-stu-id="4b428-113">In the **Results** pane, right-click the **Microsoft SQL Server XML Showplan** that contains the query plan, and then click **Save Results As**.</span></span>  
  
5.  <span data-ttu-id="4b428-114">En el cuadro de diálogo **Guardar** \<Grid or Text> **Resultados**, en el cuadro **Guardar como tipo**, haga clic en **Todos los archivos (\*.\*)** .</span><span class="sxs-lookup"><span data-stu-id="4b428-114">In the **Save** \<Grid or Text> **Results** dialog box, in the **Save as type** box, click **All files (\*.\*)**.</span></span>  
  
6.  <span data-ttu-id="4b428-115">En el cuadro **Nombre de archivo**, proporcione un nombre con el formato \<name**>.sqlplan\*\* y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b428-115">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-save-an-execution-plan-by-using-sql-server-management-studio-options"></a><span data-ttu-id="4b428-116">Para guardar un plan de ejecución mediante las opciones de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b428-116">To save an execution plan by using SQL Server Management Studio options</span></span>  
  
1.  <span data-ttu-id="4b428-117">Genere un plan de ejecución estimado o uno real mediante [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b428-117">Generate either an estimated execution plan or an actual execution plan by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="4b428-118">Para obtener más información, vea [Mostrar el plan de ejecución estimado](display-the-estimated-execution-plan.md) o [Mostrar un plan de ejecución real](display-an-actual-execution-plan.md).</span><span class="sxs-lookup"><span data-stu-id="4b428-118">For more information, see [Display the Estimated Execution Plan](display-the-estimated-execution-plan.md) or [Display an Actual Execution Plan](display-an-actual-execution-plan.md).</span></span>  
  
2.  <span data-ttu-id="4b428-119">En la pestaña **Plan de ejecución** del panel de resultados, haga clic con el botón derecho en el plan de ejecución gráfico y elija **Guardar plan de ejecución como**.</span><span class="sxs-lookup"><span data-stu-id="4b428-119">In the **Execution plan** tab of the results pane, right-click the graphical execution plan, and choose **Save Execution Plan As**.</span></span>  
  
     <span data-ttu-id="4b428-120">Como alternativa, también puede elegir **Guardar plan de ejecución como** en el menú **Archivo** .</span><span class="sxs-lookup"><span data-stu-id="4b428-120">As an alternative, you can also choose **Save Execution Plan As** on the **File** menu.</span></span>  
  
3.  <span data-ttu-id="4b428-121">En el cuadro de diálogo **Guardar como**, asegúrese de que **Guardar como tipo** está establecido en **Archivos de plan de ejecución (\*.sqlplan)** .</span><span class="sxs-lookup"><span data-stu-id="4b428-121">In the **Save As** dialog box, make sure that the **Save as type** is set to **Execution Plan Files (\*.sqlplan)**.</span></span>  
  
4.  <span data-ttu-id="4b428-122">En el cuadro **Nombre de archivo**, proporcione un nombre con el formato \<name**>.sqlplan\*\* y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b428-122">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-open-a-saved-xml-query-plan-in-sql-server-management-studio"></a><span data-ttu-id="4b428-123">Para abrir un plan de consulta XML guardado en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b428-123">To open a saved XML query plan in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="4b428-124">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Archivo** , elija **Abrir**y, a continuación, haga clic en **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="4b428-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, choose **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="4b428-125">En el cuadro de diálogo **Abrir archivo**, establezca **Archivos de tipo** en **Archivos de plan de ejecución (\*.sqlplan)** para generar una lista filtrada de archivos de plan de consulta XML guardados.</span><span class="sxs-lookup"><span data-stu-id="4b428-125">In the **Open File** dialog box, set **Files of type** to **Execution Plan Files (\*.sqlplan)** to produce a filtered list of saved XML query plan files.</span></span>  
  
3.  <span data-ttu-id="4b428-126">Seleccione el archivo de plan de consulta XML que desea ver y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4b428-126">Select the XML query plan file that you want to view, and click **Open**.</span></span>  
  
     <span data-ttu-id="4b428-127">Como alternativa, en el Explorador de Windows, haga doble clic en un archivo con la extensión **.sqlplan**.</span><span class="sxs-lookup"><span data-stu-id="4b428-127">As an alternative, in Windows Explorer, double-click a file with extension **.sqlplan**.</span></span> <span data-ttu-id="4b428-128">El plan se abre en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b428-128">The plan opens in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b428-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b428-129">See Also</span></span>  
 <span data-ttu-id="4b428-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4b428-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span></span>  
 [<span data-ttu-id="4b428-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b428-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
  
