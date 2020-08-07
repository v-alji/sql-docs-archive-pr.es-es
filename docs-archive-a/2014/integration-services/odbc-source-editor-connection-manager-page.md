---
title: Editor de origen de ODBC (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.connection.f1
ms.assetid: e2c8dc83-6394-4d6c-9232-97e94be72431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c8b54ce4a1c1b3fea0afb51f1cbf7447971ccab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747134"
---
# <a name="odbc-source-editor-connection-manager-page"></a><span data-ttu-id="60065-102">Editor de origen de ODBC (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="60065-102">ODBC Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="60065-103">Use la página **Administrador de conexiones** del cuadro de diálogo **Editor de origen de ODBC** para seleccionar el administrador de conexiones de ODBC para el origen.</span><span class="sxs-lookup"><span data-stu-id="60065-103">Use the **Connection Manager** page of the **ODBC Source Editor** dialog box to select the ODBC connection manager for the source.</span></span> <span data-ttu-id="60065-104">Esta página también permite seleccionar una tabla o vista de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="60065-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="60065-105">Para obtener más información acerca del origen de ODBC, vea [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="60065-105">For more information about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="60065-106">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="60065-106">Task List</span></span>  
 <span data-ttu-id="60065-107">**Para abrir la página Administrador de conexiones del Editor de origen de ODBC**</span><span class="sxs-lookup"><span data-stu-id="60065-107">**To open the ODBC Source Editor Connection Manager Page**</span></span>  
  
-   <span data-ttu-id="60065-108">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el paquete [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tiene el origen de ODBC.</span><span class="sxs-lookup"><span data-stu-id="60065-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="60065-109">En la pestaña **Flujo de datos** , haga doble clic en el origen de ODBC.</span><span class="sxs-lookup"><span data-stu-id="60065-109">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="60065-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="60065-110">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="60065-111">Administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="60065-111">Connection manager</span></span>  
 <span data-ttu-id="60065-112">Seleccione un administrador de conexiones ODBC existente en la lista o haga clic en **nuevo** para crear una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="60065-112">Select an existing ODBC connection manager from the list, or click **New** to create a new connection.</span></span> <span data-ttu-id="60065-113">La conexión puede ser a cualquier base de datos compatible con ODBC.</span><span class="sxs-lookup"><span data-stu-id="60065-113">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="60065-114">Nuevo</span><span class="sxs-lookup"><span data-stu-id="60065-114">New</span></span>  
 <span data-ttu-id="60065-115">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="60065-115">Click **New**.</span></span> <span data-ttu-id="60065-116">Se abrirá el cuadro de diálogo **Configurar el administrador de conexiones ODBC** , donde puede crear un administrador de conexiones ODBC nuevo.</span><span class="sxs-lookup"><span data-stu-id="60065-116">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new ODBC connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="60065-117">Modo de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="60065-117">Data Access Mode</span></span>  
 <span data-ttu-id="60065-118">Elija el método para la selección de datos desde el origen.</span><span class="sxs-lookup"><span data-stu-id="60065-118">Select the method for selecting data from the source.</span></span> <span data-ttu-id="60065-119">Las opciones se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="60065-119">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="60065-120">Opción</span><span class="sxs-lookup"><span data-stu-id="60065-120">Option</span></span>|<span data-ttu-id="60065-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="60065-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="60065-122">Nombre de la tabla</span><span class="sxs-lookup"><span data-stu-id="60065-122">Table Name</span></span>|<span data-ttu-id="60065-123">Recupera datos de una tabla o vista del origen de datos de ODBC.</span><span class="sxs-lookup"><span data-stu-id="60065-123">Retrieve data from a table or view in the ODBC data source.</span></span> <span data-ttu-id="60065-124">Cuando seleccione esta opción, seleccione un valor de la lista para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60065-124">When you select this option, select a value from the list for the following:</span></span>|  
||<span data-ttu-id="60065-125">**Nombre de la tabla o la vista**: seleccione una tabla o vista disponible en la lista o escriba una expresión regular para identificar la tabla.</span><span class="sxs-lookup"><span data-stu-id="60065-125">**Name of the table or the view**: Select an available table or view from the list or type a regular expression to identify the table.</span></span>|  
||<span data-ttu-id="60065-126">Esta lista contiene solo las 1000 primeras tablas.</span><span class="sxs-lookup"><span data-stu-id="60065-126">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="60065-127">Si la base de datos contiene más de 1000 tablas, puede escribir el principio de un nombre de tabla o usar el comodín (\*) para escribir cualquier parte del nombre con el fin de mostrar la tabla o las tablas que desea usar.</span><span class="sxs-lookup"><span data-stu-id="60065-127">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
|<span data-ttu-id="60065-128">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="60065-128">SQL command</span></span>|<span data-ttu-id="60065-129">Recupera datos del origen de datos de ODBC mediante una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="60065-129">Retrieve data from the ODBC data source by using an SQL query.</span></span> <span data-ttu-id="60065-130">Debe escribir la consulta con la sintaxis de la base de datos de origen con la que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="60065-130">You should write the query in the syntax of the source database you are working with.</span></span> <span data-ttu-id="60065-131">Cuando seleccione esta opción, escriba una consulta de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="60065-131">When you select this option, enter a query in one of the following ways:</span></span>|  
||<span data-ttu-id="60065-132">Escriba el texto de la consulta SQL en el campo de **Texto de comando SQL** .</span><span class="sxs-lookup"><span data-stu-id="60065-132">Enter the text of the SQL query in the **SQL command text** field.</span></span>|  
||<span data-ttu-id="60065-133">Haga clic en **Examinar** para cargar la consulta SQL desde un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="60065-133">Click **Browse** to load the SQL query from a text file.</span></span>|  
||<span data-ttu-id="60065-134">Haga clic en **Analizar consulta** para comprobar la sintaxis del texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="60065-134">Click **Parse query** to verify the syntax of the query text.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="60065-135">Versión preliminar</span><span class="sxs-lookup"><span data-stu-id="60065-135">Preview</span></span>  
 <span data-ttu-id="60065-136">Haga clic en **Vista previa** para ver hasta las 200 primeras filas de los datos extraídos de la tabla o la vista seleccionada.</span><span class="sxs-lookup"><span data-stu-id="60065-136">Click **Preview** to view up to the first 200 rows of the data extracted from the table or view you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60065-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60065-137">See Also</span></span>  
 <span data-ttu-id="60065-138">[Propiedades personalizadas del origen ODBC](data-flow/odbc-source-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="60065-138">[ODBC Source Custom Properties](data-flow/odbc-source-custom-properties.md) </span></span>  
 <span data-ttu-id="60065-139">[Editor de origen ODBC &#40;página columnas&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="60065-139">[ODBC Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="60065-140">Editor de orígenes ODBC &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="60065-140">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
