---
title: Implementar una transformación búsqueda en el modo de caché completa mediante el administrador de conexiones de OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Lookup transformation [Integration Services]
ms.assetid: c4150e1b-bdff-4f7a-af4c-3401c34def83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f77a753dd71bc487d57492371906fc48bc114357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676138"
---
# <a name="implement-a-lookup-transformation-in-full-cache-mode-using-the-ole-db-connection-manager"></a><span data-ttu-id="71250-102">Implementar una transformación Búsqueda en el modo de caché completa mediante el Administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="71250-102">Implement a Lookup Transformation in Full Cache Mode Using the OLE DB Connection Manager</span></span>
  <span data-ttu-id="71250-103">Puede configurar la transformación Búsqueda para que use el modo de caché completa y un administrador de conexiones OLE DB.</span><span class="sxs-lookup"><span data-stu-id="71250-103">You can configure the Lookup transformation to use full cache mode and an OLE DB connection manager.</span></span> <span data-ttu-id="71250-104">En el modo de caché completa, el conjunto de datos de referencia se carga en la memoria caché antes de que se ejecute la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="71250-104">In the full cache mode, the reference dataset is loaded into cache before the Lookup transformation runs.</span></span>  
  
 <span data-ttu-id="71250-105">La transformación Búsqueda realiza búsquedas mediante la combinación de datos de las columnas de entrada procedentes de un origen de datos conectado con columnas de un conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="71250-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in a reference dataset.</span></span> <span data-ttu-id="71250-106">Para más información, consulte [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="71250-106">For more information, see [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="71250-107">Al configurar la transformación Búsqueda para que use un administrador de conexiones OLE DB, debe seleccionar una tabla, una vista o una consulta SQL para generar el conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="71250-107">When you configure the Lookup transformation to use an OLE DB connection manager, you select a table, view, or SQL query to generate the reference dataset.</span></span>  
  
### <a name="to-implement-a-lookup-transformation-in-full-cache-mode-by-using-ole-db-connection-manager"></a><span data-ttu-id="71250-108">Para implementar una transformación Búsqueda en el modo de caché completa mediante el administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="71250-108">To implement a Lookup transformation in full cache mode by using OLE DB connection manager</span></span>  
  
1.  <span data-ttu-id="71250-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete con el que desea trabajar y, a continuación, en el Explorador de soluciones, haga doble clic en el paquete.</span><span class="sxs-lookup"><span data-stu-id="71250-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want, and then double-click the package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="71250-110">En la pestaña **Flujo de datos** , en el **Cuadro de herramientas**, arrastre la transformación Búsqueda hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="71250-110">On the **Data Flow** tab, from the **Toolbox**, drag the Lookup transformation to the design surface.</span></span>  
  
3.  <span data-ttu-id="71250-111">Conecte la transformación Búsqueda al flujo de datos arrastrando un conector desde un origen o una transformación anterior hasta la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="71250-111">Connect the Lookup transformation to the data flow by dragging a connector from a source or a previous transformation to the Lookup transformation.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="71250-112">Una transformación Búsqueda podría no validarse si se conecta a un archivo plano que contiene un campo de fecha vacío.</span><span class="sxs-lookup"><span data-stu-id="71250-112">A Lookup transformation might not validate if that transformation connects to a flat file that contains an empty date field.</span></span> <span data-ttu-id="71250-113">El que la transformación se valide depende de si el administrador de conexiones para el archivo plano se ha configurado para conservar los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="71250-113">Whether the transformation validates depends on whether the connection manager for the flat file has been configured to retain null values.</span></span> <span data-ttu-id="71250-114">Para asegurarse de que la transformación Búsqueda se valida, en el **Editor de origen de archivos planos**, de la página **Administrador de conexiones**, seleccione la opción **Conservar los valores null del origen como valores null en el flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="71250-114">To ensure that the Lookup transformation validates, in the **Flat File Source Editor**, on the **Connection Manager Page**, select the **Retain null values from the source as null values in the data flow** option.</span></span>  
  
4.  <span data-ttu-id="71250-115">Haga doble clic en el origen o la transformación anterior para configurar el componente.</span><span class="sxs-lookup"><span data-stu-id="71250-115">Double-click the source or previous transformation to configure the component.</span></span>  
  
5.  <span data-ttu-id="71250-116">Haga doble clic en la transformación Búsqueda y, después, en el **Editor de transformación Búsqueda**, en la página **General** , seleccione **Caché completa**.</span><span class="sxs-lookup"><span data-stu-id="71250-116">Double-click the Lookup transformation, and then in the **Lookup Transformation Editor**, on the **General** page, select **Full cache**.</span></span>  
  
6.  <span data-ttu-id="71250-117">En el área **Tipo de conexión** , seleccione **Administrador de conexiones OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="71250-117">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
7.  <span data-ttu-id="71250-118">En la lista **Especificar cómo tratar las filas sin entradas coincidentes** , seleccione una opción de control de errores para las filas sin entradas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="71250-118">In the **Specify how to handle rows with no matching entries** list, select an error handling option for rows without matching entries.</span></span>  
  
8.  <span data-ttu-id="71250-119">En la página Conexión, seleccione un administrador de conexiones en la lista **Administrador de conexiones OLE DB** o haga clic en **Nuevo** para crear un nuevo administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="71250-119">On the Connection page, select a connection manager from the **OLE DB connection manager** list or click **New** to create a new connection manager.</span></span> <span data-ttu-id="71250-120">Para más información, consulte [OLE DB Connection Manager](ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="71250-120">For more information, see [OLE DB Connection Manager](ole-db-connection-manager.md).</span></span>  
  
9. <span data-ttu-id="71250-121">Realice una de las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="71250-121">Do one of the following tasks:</span></span>  
  
    -   <span data-ttu-id="71250-122">Haga clic en **Usar una tabla o una vista**y, a continuación, seleccione una tabla o una vista, o haga clic en **Nueva** para crear una tabla o una vista.</span><span class="sxs-lookup"><span data-stu-id="71250-122">Click **Use a table or a view**, and then either select a table or view, or click **New** to create a table or view.</span></span>  
  
         <span data-ttu-id="71250-123">O bien</span><span class="sxs-lookup"><span data-stu-id="71250-123">-or-</span></span>  
  
    -   <span data-ttu-id="71250-124">Haga clic en **Usar los resultados de una consulta SQL**y después genere una consulta en la ventana **Comando SQL** , o haga clic en **Generar consulta** para generar una consulta mediante las herramientas gráficas que proporciona el **Generador de consultas** .</span><span class="sxs-lookup"><span data-stu-id="71250-124">Click **Use results of an SQL query**, and then build a query in the **SQL Command** window, or click **Build Query** to build a query by using the graphical tools that the **Query Builder** provides.</span></span>  
  
         <span data-ttu-id="71250-125">O bien</span><span class="sxs-lookup"><span data-stu-id="71250-125">-or-</span></span>  
  
    -   <span data-ttu-id="71250-126">Haga clic en **Examinar** para importar una instrucción SQL de un archivo.</span><span class="sxs-lookup"><span data-stu-id="71250-126">Alternatively, click **Browse** to import an SQL statement from a file.</span></span>  
  
     <span data-ttu-id="71250-127">Para validar la consulta SQL, haga clic en **Analizar consulta**.</span><span class="sxs-lookup"><span data-stu-id="71250-127">To validate the SQL query, click **Parse Query**.</span></span>  
  
     <span data-ttu-id="71250-128">Para ver un ejemplo de los datos, haga clic en **Vista previa**.</span><span class="sxs-lookup"><span data-stu-id="71250-128">To view a sample of the data, click **Preview**.</span></span>  
  
10. <span data-ttu-id="71250-129">Haga clic en la página **Columnas** y, a continuación, arrastre por lo menos una columna desde la lista **Columnas de entrada disponibles** hasta una columna de la lista **Columnas de búsqueda disponibles** .</span><span class="sxs-lookup"><span data-stu-id="71250-129">Click the **Columns** page, and then from the **Available Input Columns** list, drag at least one column to a column in the **Available Lookup Column** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="71250-130">La transformación Búsqueda asigna automáticamente las columnas que tienen el mismo nombre y el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="71250-130">The Lookup transformation automatically maps columns that have the same name and the same data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="71250-131">Las columnas deben tener tipos coincidentes de datos para asignarse.</span><span class="sxs-lookup"><span data-stu-id="71250-131">Columns must have matching data types to be mapped.</span></span> <span data-ttu-id="71250-132">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="71250-132">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
11. <span data-ttu-id="71250-133">Incluya las columnas de búsqueda en el resultado realizando las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="71250-133">Include lookup columns in the output by doing the following tasks:</span></span>  
  
    1.  <span data-ttu-id="71250-134">En la lista **Columnas de búsqueda disponibles** ,</span><span class="sxs-lookup"><span data-stu-id="71250-134">In the **Available Lookup Columns** list.</span></span> <span data-ttu-id="71250-135">seleccione las columnas.</span><span class="sxs-lookup"><span data-stu-id="71250-135">select columns.</span></span>  
  
    2.  <span data-ttu-id="71250-136">En la lista **Operación de búsqueda** , especifique si los valores de las columnas de búsqueda reemplazan los valores de la columna de entrada o se escriben en una nueva columna.</span><span class="sxs-lookup"><span data-stu-id="71250-136">In **Lookup Operation** list, specify whether the values from the lookup columns replace values in the input column or are written to a new column.</span></span>  
  
12. <span data-ttu-id="71250-137">Para configurar la salida de errores, haga clic en la página **Salida de error** y establezca las opciones de control de errores.</span><span class="sxs-lookup"><span data-stu-id="71250-137">To configure the error output, click the **Error Output** page and set the error handling options.</span></span> <span data-ttu-id="71250-138">Para obtener más información, vea [Editor de transformación Búsqueda &#40;página Salida de error&#41;](../lookup-transformation-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="71250-138">For more information, see [Lookup Transformation Editor &#40;Error Output Page&#41;](../lookup-transformation-editor-error-output-page.md).</span></span>  
  
13. <span data-ttu-id="71250-139">Haga clic en **Aceptar** para guardar los cambios en la transformación Búsqueda y, a continuación, ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="71250-139">Click **OK** to save your changes to the Lookup transformation, and then run the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71250-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71250-140">See Also</span></span>  
 <span data-ttu-id="71250-141">[Implementación de una transformación Búsqueda en el modo de caché completa con el Administrador de conexiones de caché](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="71250-141">[Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span></span>  
 <span data-ttu-id="71250-142">[Implementación de una búsqueda en los modos No hay caché o Caché parcial](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span><span class="sxs-lookup"><span data-stu-id="71250-142">[Implement a Lookup in No Cache or Partial Cache Mode](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span></span>  
 [<span data-ttu-id="71250-143">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="71250-143">Integration Services Transformations</span></span>](../data-flow/transformations/integration-services-transformations.md)  
  
  
