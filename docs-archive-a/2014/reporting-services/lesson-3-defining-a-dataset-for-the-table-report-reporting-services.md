---
title: 'Lección 3: Definir un conjunto de datos para el informe de tabla (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ee93dfcb-8f52-4d63-b4f6-0d38e00fd350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 33fe48a60db2e7d15d205a4bff6205347f95c61c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670851"
---
# <a name="lesson-3-defining-a-dataset-for-the-table-report-reporting-services"></a><span data-ttu-id="7baed-102">Lección 3: Definir un conjunto de datos para el informe de tabla (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="7baed-102">Lesson 3: Defining a Dataset for the Table Report (Reporting Services)</span></span>
  <span data-ttu-id="7baed-103">Después de definir el origen de datos, necesita definir un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="7baed-103">After you define the data source, you need to define a dataset.</span></span> <span data-ttu-id="7baed-104">En [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], los datos que usa en los informes proceden de un *conjunto de datos*.</span><span class="sxs-lookup"><span data-stu-id="7baed-104">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], data that you use in reports is contained in a *dataset*.</span></span> <span data-ttu-id="7baed-105">Un conjunto de datos incluye un puntero a un origen de datos y la consulta que usará para el informe, así como campos y variables calculados.</span><span class="sxs-lookup"><span data-stu-id="7baed-105">A dataset includes a pointer to a data source and a query to be used by the report, as well as calculated fields and variables.</span></span>  
  
 <span data-ttu-id="7baed-106">Puede usar el Diseñador de consultas del Diseñador de informes para diseñar la consulta.</span><span class="sxs-lookup"><span data-stu-id="7baed-106">You can use the query designer in Report Designer to design the query.</span></span> <span data-ttu-id="7baed-107">En este tutorial, creará una consulta que recupera información de pedidos de ventas de la [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] base de datos **2008** .</span><span class="sxs-lookup"><span data-stu-id="7baed-107">For this tutorial, you will create a query that retrieves sales order information from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]**2008** database.</span></span>  
  
### <a name="to-define-a-transact-sql-query-for-report-data"></a><span data-ttu-id="7baed-108">Para definir una consulta de Transact-SQL para los datos de informe</span><span class="sxs-lookup"><span data-stu-id="7baed-108">To define a Transact-SQL query for report data</span></span>  
  
1.  <span data-ttu-id="7baed-109">En el panel **datos de informe** , haga clic en **nuevo**y, a continuación, haga clic en **DataSet...**. Se abrirá el cuadro de diálogo **propiedades del conjunto de propiedades** .</span><span class="sxs-lookup"><span data-stu-id="7baed-109">In the **Report Data** pane, click **New**, and then click **Dataset...**. The **Dataset Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="7baed-110">En el cuadro **Nombre** , escriba **AdventureWorksDataset**.</span><span class="sxs-lookup"><span data-stu-id="7baed-110">In the **Name** box, type **AdventureWorksDataset**.</span></span>  
  
3.  <span data-ttu-id="7baed-111">Haga clic en **Usar un conjunto de datos insertado en el informe**.</span><span class="sxs-lookup"><span data-stu-id="7baed-111">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="7baed-112">Asegúrese de que el nombre del origen de datos, AdventureWorks2012, se encuentra en el cuadro de texto **origen de datos** y que el **tipo de consulta** es **texto**.</span><span class="sxs-lookup"><span data-stu-id="7baed-112">Make sure the name of your data source, AdventureWorks2012, is in the **Data source** text box, and that the **Query type** is **Text**.</span></span>  
  
5.  <span data-ttu-id="7baed-113">Escriba o copie y pegue la siguiente consulta de Transact-SQL en el cuadro **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="7baed-113">Type, or copy and paste, the following Transact-SQL query into the **Query** box.</span></span>  
  
    ```  
    SELECT   
       soh.OrderDate AS [Date],   
       soh.SalesOrderNumber AS [Order],   
       pps.Name AS Subcat, pp.Name as Product,    
       SUM(sd.OrderQty) AS Qty,  
       SUM(sd.LineTotal) AS LineTotal  
    FROM Sales.SalesPerson sp   
       INNER JOIN Sales.SalesOrderHeader AS soh   
          ON sp.BusinessEntityID = soh.SalesPersonID  
       INNER JOIN Sales.SalesOrderDetail AS sd   
          ON sd.SalesOrderID = soh.SalesOrderID  
       INNER JOIN Production.Product AS pp   
          ON sd.ProductID = pp.ProductID  
       INNER JOIN Production.ProductSubcategory AS pps   
          ON pp.ProductSubcategoryID = pps.ProductSubcategoryID  
       INNER JOIN Production.ProductCategory AS ppc   
          ON ppc.ProductCategoryID = pps.ProductCategoryID  
    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name,   
       soh.SalesPersonID  
    HAVING ppc.Name = 'Clothing'  
    ```  
  
6.  <span data-ttu-id="7baed-114">(Opcional) Haga clic en el botón **Diseñador de consultas** .</span><span class="sxs-lookup"><span data-stu-id="7baed-114">(Optional) Click the **Query Designer** button.</span></span> <span data-ttu-id="7baed-115">La consulta se muestra en el Diseñador de consultas basado en texto.</span><span class="sxs-lookup"><span data-stu-id="7baed-115">The query is displayed in the text-based query designer.</span></span> <span data-ttu-id="7baed-116">Puede cambiar al diseñador gráfico de consultas si hace clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="7baed-116">You can toggle to the graphical query designer by clicking **Edit As Text**.</span></span> <span data-ttu-id="7baed-117">Para ver los resultados de la consulta, haga clic en el botón ejecutar **(!)** de la barra de herramientas del diseñador de consultas.</span><span class="sxs-lookup"><span data-stu-id="7baed-117">View the results of the query by clicking the run **(!)** button on the query designer toolbar.</span></span>  
  
     <span data-ttu-id="7baed-118">Verá los datos procedentes de seis campos de cuatro tablas distintas de la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7baed-118">You see the data from six fields from four different tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="7baed-119">La consulta utiliza funcionalidad de Transact-SQL como los alias.</span><span class="sxs-lookup"><span data-stu-id="7baed-119">The query makes use of Transact-SQL functionality such as aliases.</span></span> <span data-ttu-id="7baed-120">Por ejemplo, la tabla SalesOrderHeader se denomina soh.</span><span class="sxs-lookup"><span data-stu-id="7baed-120">For example, the SalesOrderHeader table is called soh.</span></span>  
  
     <span data-ttu-id="7baed-121">Haga clic en **Aceptar** para salir del diseñador de consultas.</span><span class="sxs-lookup"><span data-stu-id="7baed-121">Click **OK** to exit the query designer.</span></span>  
  
7.  <span data-ttu-id="7baed-122">Haga clic en **Aceptar** para salir del cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="7baed-122">Click **OK** to exit the **Dataset Properties** dialog box.</span></span>  
  
     <span data-ttu-id="7baed-123">El conjunto de datos **AdventureWorksDataset** y los campos aparecen en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="7baed-123">Your **AdventureWorksDataset** dataset and fields appear in the Report Data pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="7baed-124">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="7baed-124">Next Task</span></span>  
 <span data-ttu-id="7baed-125">Ha especificado correctamente una consulta que recupera datos para su informe.</span><span class="sxs-lookup"><span data-stu-id="7baed-125">You have successfully specified a query that retrieves data for your report.</span></span> <span data-ttu-id="7baed-126">A continuación, creará el diseño para el informe.</span><span class="sxs-lookup"><span data-stu-id="7baed-126">Next, you will create the report layout.</span></span> <span data-ttu-id="7baed-127">Vea [Lección 4: Agregar una tabla al informe &#40;Reporting Services&#41;](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="7baed-127">See [Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7baed-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7baed-128">See Also</span></span>  
 <span data-ttu-id="7baed-129">[Herramientas de diseño de consultas en Diseñador de informes SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7baed-129">[Query Design Tools in Report Designer SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span></span>  
 <span data-ttu-id="7baed-130">[Tipo de conexión SQL Server &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7baed-130">[SQL Server Connection Type &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="7baed-131">Tutorial: Escribir instrucciones Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7baed-131">Tutorial: Writing Transact-SQL Statements</span></span>](../t-sql/tutorial-writing-transact-sql-statements.md)  
  
  
