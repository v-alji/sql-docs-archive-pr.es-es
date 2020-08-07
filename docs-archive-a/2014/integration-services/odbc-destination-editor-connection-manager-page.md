---
title: Editor de destino de ODBC (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.connection.f1
ms.assetid: f6d9c6c2-e4c4-468b-9e0d-af7b9609614d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e4fc1073bb187c0864d2991459a358a7f81d066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747140"
---
# <a name="odbc-destination-editor-connection-manager-page"></a><span data-ttu-id="ef98d-102">Editor de destino de ODBC (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="ef98d-102">ODBC Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="ef98d-103">Use la página **Administrador de conexiones** del cuadro de diálogo **Editor de destino de ODBC** para seleccionar el administrador de conexiones de ODBC para el destino.</span><span class="sxs-lookup"><span data-stu-id="ef98d-103">Use the **Connection Manager** page of the **ODBC Destination Editor** dialog box to select the ODBC connection manager for the destination.</span></span> <span data-ttu-id="ef98d-104">Esta página también permite seleccionar una tabla o vista de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ef98d-104">This page also lets you select a table or view from the database</span></span>  
  
 <span data-ttu-id="ef98d-105">Para obtener más información acerca del destino de ODBC, vea [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ef98d-105">For more information about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="ef98d-106">**Para abrir la página Administrador de conexiones del Editor de destino de ODBC**</span><span class="sxs-lookup"><span data-stu-id="ef98d-106">**To open the ODBC Destination Editor Connection Manager Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="ef98d-107">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="ef98d-107">Task List</span></span>  
  
-   <span data-ttu-id="ef98d-108">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el paquete [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tiene el destino de ODBC.</span><span class="sxs-lookup"><span data-stu-id="ef98d-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="ef98d-109">En la pestaña **Flujo de datos** , haga doble clic en el destino de ODBC.</span><span class="sxs-lookup"><span data-stu-id="ef98d-109">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="ef98d-110">En el **Editor de destino de ODBC**, haga clic en **Administrador de conexiones**.</span><span class="sxs-lookup"><span data-stu-id="ef98d-110">In the **ODBC Destination Editor**, click **Connection Manager**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ef98d-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="ef98d-111">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="ef98d-112">Administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="ef98d-112">Connection manager</span></span>  
 <span data-ttu-id="ef98d-113">Seleccione un administrador de conexiones de ODBC existente en la lista o haga clic en Nueva para crear una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="ef98d-113">Select an existing ODBC connection manager from the list, or click New to create a new connection.</span></span> <span data-ttu-id="ef98d-114">La conexión puede ser a cualquier base de datos compatible con ODBC.</span><span class="sxs-lookup"><span data-stu-id="ef98d-114">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="ef98d-115">Nuevo</span><span class="sxs-lookup"><span data-stu-id="ef98d-115">New</span></span>  
 <span data-ttu-id="ef98d-116">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="ef98d-116">Click **New**.</span></span> <span data-ttu-id="ef98d-117">Se abrirá el cuadro de diálogo **Configurar el administrador de conexiones ODBC** , donde puede crear un administrador de conexiones nuevo.</span><span class="sxs-lookup"><span data-stu-id="ef98d-117">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="ef98d-118">Modo de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="ef98d-118">Data Access Mode</span></span>  
 <span data-ttu-id="ef98d-119">Seleccione el método para cargar datos en el destino.</span><span class="sxs-lookup"><span data-stu-id="ef98d-119">Select the method for loading data to the destination.</span></span> <span data-ttu-id="ef98d-120">Las opciones se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef98d-120">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="ef98d-121">Opción</span><span class="sxs-lookup"><span data-stu-id="ef98d-121">Option</span></span>|<span data-ttu-id="ef98d-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef98d-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ef98d-123">Nombre de la tabla - Lote</span><span class="sxs-lookup"><span data-stu-id="ef98d-123">Table Name - Batch</span></span>|<span data-ttu-id="ef98d-124">Seleccione esta opción para configurar el destino de ODBC de manera que funcione en modo por lotes.</span><span class="sxs-lookup"><span data-stu-id="ef98d-124">Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="ef98d-125">Cuando seleccione esta opción, aparecerán las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef98d-125">When you select this option the following options are available:</span></span>|  
||<span data-ttu-id="ef98d-126">**Nombre de la tabla o la vista**: seleccione una tabla o vista disponible en la lista.</span><span class="sxs-lookup"><span data-stu-id="ef98d-126">**Name of the table or the view**: Select an available table or view from the list.</span></span><br /><br /> <span data-ttu-id="ef98d-127">Esta lista contiene solo las 1000 primeras tablas.</span><span class="sxs-lookup"><span data-stu-id="ef98d-127">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="ef98d-128">Si la base de datos contiene más de 1000 tablas, puede escribir el principio de un nombre de tabla o usar el carácter comodín (\*) para escribir cualquier parte del nombre con el fin de mostrar las tablas que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="ef98d-128">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span><br /><br /> <span data-ttu-id="ef98d-129">**Tamaño del lote**: escriba el tamaño del lote para la carga masiva.</span><span class="sxs-lookup"><span data-stu-id="ef98d-129">**Batch size**: Type the size of the batch for bulk loading.</span></span> <span data-ttu-id="ef98d-130">Es el número de filas cargadas como un lote.</span><span class="sxs-lookup"><span data-stu-id="ef98d-130">This is the number of rows loaded as a batch</span></span>|  
|<span data-ttu-id="ef98d-131">Nombre de la tabla - Fila a fila</span><span class="sxs-lookup"><span data-stu-id="ef98d-131">Table Name - Row by Row</span></span>|<span data-ttu-id="ef98d-132">Seleccione esta opción para configurar el destino de ODBC de manera que se inserte cada una de las filas en la tabla de destino de una en una.</span><span class="sxs-lookup"><span data-stu-id="ef98d-132">Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="ef98d-133">Cuando seleccione esta opción, aparecerá la opción siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef98d-133">When you select this option the following option is available:</span></span>|  
||<span data-ttu-id="ef98d-134">**Nombre de la tabla o la vista**: seleccione en la lista una tabla o vista disponible en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ef98d-134">**Name of the table or the view**: Select an available table or view from the database from the list.</span></span><br /><br /> <span data-ttu-id="ef98d-135">Esta lista contiene solo las 1000 primeras tablas.</span><span class="sxs-lookup"><span data-stu-id="ef98d-135">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="ef98d-136">Si la base de datos contiene más de 1000 tablas, puede escribir el principio de un nombre de tabla o usar el comodín (\*) para escribir cualquier parte del nombre con el fin de mostrar la tabla o las tablas que desea usar.</span><span class="sxs-lookup"><span data-stu-id="ef98d-136">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="ef98d-137">Vista previa</span><span class="sxs-lookup"><span data-stu-id="ef98d-137">Preview</span></span>  
 <span data-ttu-id="ef98d-138">Haga clic en **Vista previa** para ver hasta 200 filas de datos para la tabla que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ef98d-138">Click **Preview** to view up to 200 rows of data for the table that you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef98d-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef98d-139">See Also</span></span>  
 <span data-ttu-id="ef98d-140">[Propiedades personalizadas del destino ODBC](data-flow/odbc-destination-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ef98d-140">[ODBC Destination Custom Properties](data-flow/odbc-destination-custom-properties.md) </span></span>  
 <span data-ttu-id="ef98d-141">[Editor de destino de ODBC &#40;página asignaciones&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="ef98d-141">[ODBC Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="ef98d-142">Editor de destinos de ODBC &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="ef98d-142">ODBC Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-error-output-page.md)  
  
  
