---
title: Crear una consulta en el Diseñador de consultas relacionales (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 28b25861-f3b4-4c3e-a9b0-03d6e4cfea26
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 555d72c4d3bca8677d04fdc4160639f004d6bbe9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749138"
---
# <a name="build-a-query-in-the-relational-query-designer-report-builder-and-ssrs"></a><span data-ttu-id="75481-102">Crear una consulta en el Diseñador de consultas relacionales (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="75481-102">Build a Query in the Relational Query Designer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="75481-103">Los diseñadores de consultas le ayudan a especificar los datos que se deben recuperar de un origen de datos externo para un conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="75481-103">A query designer helps you specify which data to retrieve from an external data source for a report dataset.</span></span> <span data-ttu-id="75481-104">Puede utilizar un diseñador de consultas cuando genere una consulta en un asistente o cree una consulta de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="75481-104">You use a query designer when you build a query in a wizard or create a dataset query.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="75481-105">Una conjunto de datos se basa en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="75481-105">A dataset is based on a data source.</span></span> <span data-ttu-id="75481-106">El tipo de origen de datos y el entorno de creación determina el diseñador de consultas que se ha de abrir al definir la consulta de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="75481-106">The type of data source and the authoring environment determines which query designer opens when you define the dataset query.</span></span> <span data-ttu-id="75481-107">Las características del diseñador de consultas varían en función del origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="75481-107">Query designer features vary based on the underlying data source.</span></span> <span data-ttu-id="75481-108">Para obtener más información sobre las capas de datos, vea [conexiones de datos, orígenes de datos y cadenas de conexión en generador de informes](../data-connections-data-sources-and-connection-strings-in-report-builder.md) o [conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="75481-108">For more information about data layers, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) or [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span></span>  
  
 <span data-ttu-id="75481-109">Puede utilizar un diseñador de consultas para las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="75481-109">You can use a query designer for the following tasks:</span></span>  
  
-   <span data-ttu-id="75481-110">Explorar los metadatos de varios esquemas en el origen de datos externo</span><span class="sxs-lookup"><span data-stu-id="75481-110">Explore the metadata for multiple schemas on the external data source</span></span>  
  
-   <span data-ttu-id="75481-111">Especificar los campos para recuperar del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="75481-111">Specify fields to retrieve for the dataset</span></span>  
  
-   <span data-ttu-id="75481-112">Especificar las relaciones entre dos objetos, como las tablas</span><span class="sxs-lookup"><span data-stu-id="75481-112">Specify relationships between two objects such as tables</span></span>  
  
-   <span data-ttu-id="75481-113">Especificar filtros para restringir los datos antes de recuperarlos como datos del informe</span><span class="sxs-lookup"><span data-stu-id="75481-113">Specify filters to restrict the data before it is retrieved as report data</span></span>  
  
-   <span data-ttu-id="75481-114">Indicar si se crearán parámetros</span><span class="sxs-lookup"><span data-stu-id="75481-114">Indicate whether to create parameters</span></span>  
  
-   <span data-ttu-id="75481-115">Especificar agregados para realizar cálculos en el origen de datos externo</span><span class="sxs-lookup"><span data-stu-id="75481-115">Specify aggregates to perform calculations on the external data source</span></span>  
  
 <span data-ttu-id="75481-116">Después de abrir un diseñador de consultas, cree una consulta de la misma manera para un conjunto de datos incrustado que para uno compartido.</span><span class="sxs-lookup"><span data-stu-id="75481-116">After you open a query designer, you build a query in the same way for either an embedded dataset or a shared dataset.</span></span> <span data-ttu-id="75481-117">Los siguientes procedimientos utilizan una consulta de conjunto de datos incrustada.</span><span class="sxs-lookup"><span data-stu-id="75481-117">The following procedures use an embedded dataset query.</span></span>  
  
 <span data-ttu-id="75481-118">Para obtener más información, vea [Interfaz de usuario del Diseñador de consultas relacionales &#40;Generador de informes&#41;](relational-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="75481-118">For more information, see [Relational Query Designer User Interface &#40;Report Builder&#41;](relational-query-designer-user-interface-report-builder.md).</span></span>  
  
### <a name="to-build-a-query-for-an-embedded-dataset-in-report-design-view"></a><span data-ttu-id="75481-119">Para crear una consulta para un conjunto de datos incrustado en la vista de diseño del informe</span><span class="sxs-lookup"><span data-stu-id="75481-119">To build a query for an embedded dataset in Report Design View</span></span>  
  
1.  <span data-ttu-id="75481-120">Abra el diseñador de consultas.</span><span class="sxs-lookup"><span data-stu-id="75481-120">Open the query designer.</span></span> <span data-ttu-id="75481-121">En el panel Datos de informe, haga clic con el botón derecho en el conjunto de datos y, después, haga clic en **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="75481-121">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
     <span data-ttu-id="75481-122">Se abrirá el diseñador de consultas que esté asociado al origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="75481-122">The query designer that is associated with the data source opens.</span></span>  
  
2.  <span data-ttu-id="75481-123">En el panel Vista de base de datos, expanda las carpetas que muestran una vista jerárquica de objetos de esquema de la base de datos, como tablas, vistas y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="75481-123">In the Database view pane, expand the folders that display a hierarchical view of database schema objects such as tables, views, and stored procedures.</span></span> <span data-ttu-id="75481-124">Haga clic en el cuadro de selección para elegir todos los campos de un objeto o expandir el nodo para seleccionar campos individuales.</span><span class="sxs-lookup"><span data-stu-id="75481-124">Click the select box to select all fields for an object or expand the node to select individual fields.</span></span>  
  
     <span data-ttu-id="75481-125">A medida que seleccione campos en el panel Vista de base de datos, el panel **Seleccionar campos** mostrará sus selecciones.</span><span class="sxs-lookup"><span data-stu-id="75481-125">As you select fields from the Database view pane, the **Select fields** pane displays your selections.</span></span>  
  
     <span data-ttu-id="75481-126">Si selecciona campos de más de una tabla de base de datos relacionada, utilice el panel Relaciones para ver las relaciones entre tablas que se detectaron en el esquema de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="75481-126">If you select fields from more than one related database table, use the Relationships pane to view the table relationships that were detected from the database schema.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="75481-127">La lista de campos de conjunto de datos aparecerá en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="75481-127">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-specify-limits-for-a-query"></a><span data-ttu-id="75481-128">Para especificar los límites de una consulta</span><span class="sxs-lookup"><span data-stu-id="75481-128">To specify limits for a query</span></span>  
  
1.  <span data-ttu-id="75481-129">En el diseñador de consultas relacionales, compruebe que los campos están seleccionados y que aparecen en el panel **Campos seleccionados** .</span><span class="sxs-lookup"><span data-stu-id="75481-129">In the relational query designer, verify that you have fields selected and that the fields appear in the **Selected fields** pane.</span></span>  
  
2.  <span data-ttu-id="75481-130">En la barra de herramientas del panel Filtros aplicados, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="75481-130">In the Applied filters pane toolbar, click **Add Filter**.</span></span> <span data-ttu-id="75481-131">Aparece una nueva fila de filtro.</span><span class="sxs-lookup"><span data-stu-id="75481-131">A new filter row appears.</span></span>  
  
3.  <span data-ttu-id="75481-132">En **Nombre de campo**, haga clic para mostrar la lista desplegable de campos y, después, haga clic en el nombre del campo por el que quiere filtrar.</span><span class="sxs-lookup"><span data-stu-id="75481-132">In **Field name**, click to display the drop-down list of fields, and then click the name of the field that you want to filter by.</span></span> <span data-ttu-id="75481-133">Por ejemplo, para filtrar por cantidad, haga clic en el campo que contiene el número de elementos.</span><span class="sxs-lookup"><span data-stu-id="75481-133">For example, to filter by quantity, click the field that contains the number of items.</span></span>  
  
4.  <span data-ttu-id="75481-134">En **Operador**, haga clic para mostrar la lista desplegable de operadores y, después, seleccione el operador de comparación que se usará en el filtro.</span><span class="sxs-lookup"><span data-stu-id="75481-134">In **Operator**, click to display the drop-down list of operators, and then select the comparison operator to use in the filter.</span></span>  
  
5.  <span data-ttu-id="75481-135">En **Valor**, escriba el valor por el que desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="75481-135">In **Value**, type the value that you want to filter by.</span></span> <span data-ttu-id="75481-136">Por ejemplo, para filtrar por una cantidad mayor que 100, escriba 100.</span><span class="sxs-lookup"><span data-stu-id="75481-136">For example, to filter on quantity greater than 100, type 100.</span></span>  
  
6.  <span data-ttu-id="75481-137">Seleccione la opción de parámetro de esta fila para crear un parámetro de conjunto de datos que permita a los usuarios especificar valores de filtro.</span><span class="sxs-lookup"><span data-stu-id="75481-137">Select the parameter option in this row to create a dataset parameter to enable a user to specify a filter value.</span></span> <span data-ttu-id="75481-138">Automáticamente se creará un parámetro de informe que coincida con el parámetro de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="75481-138">A report parameter that matches the dataset parameter is automatically created.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="75481-139">La lista de campos de conjunto de datos aparecerá en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="75481-139">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-view-a-query-result-set"></a><span data-ttu-id="75481-140">Para ver un conjunto de resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="75481-140">To view a query result set</span></span>  
  
1.  <span data-ttu-id="75481-141">En la barra de herramientas del diseñador de consultas, haga clic en **Ejecutar consulta (!)** .</span><span class="sxs-lookup"><span data-stu-id="75481-141">On the query designer toolbar, click **Run Query (!)**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75481-142">El diseñador de consultas utiliza las credenciales de tiempo de diseño para ejecutar la consulta y recuperar el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="75481-142">The query designer uses design time credentials to run the query and retrieve the result set.</span></span> <span data-ttu-id="75481-143">Para más información, vea [Especificar credenciales en el Generador de informes](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="75481-143">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="75481-144">La consulta se ejecuta en el origen de datos y devuelve datos de ejemplo en el panel Resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="75481-144">The query runs on the data source and returns example data in the Query results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75481-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="75481-145">See Also</span></span>  
 <span data-ttu-id="75481-146">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="75481-146">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="75481-147">[Agregar datos de orígenes de datos externos &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="75481-147">[Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="75481-148">[Diseñadores de consultas &#40;Generador de informes&#41;](../query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="75481-148">[Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="75481-149">[Crear un conjunto de datos compartido o un conjunto de datos incrustado &#40;Generador de informes y SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="75481-149">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="75481-150">[Vista de diseño de informe &#40;Generador de informes&#41;](../report-builder/report-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="75481-150">[Report Design View &#40;Report Builder&#41;](../report-builder/report-design-view-report-builder.md) </span></span>  
 <span data-ttu-id="75481-151">[Vista de diseño de conjunto de datos compartidos &#40;Generador de informes&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="75481-151">[Shared Dataset Design View &#40;Report Builder&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span></span>  
 [<span data-ttu-id="75481-152">Diseñadores de consultas de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="75481-152">Reporting Services Query Designers</span></span>](../reporting-services-query-designers.md)  
  
  
