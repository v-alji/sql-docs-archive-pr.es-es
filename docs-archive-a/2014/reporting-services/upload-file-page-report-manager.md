---
title: Página Cargar archivo (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7bb3166f-9374-4449-b66a-ffb77298507d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de03c6c6bd03cbe083d5e1edfd320264d2cc3bde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747414"
---
# <a name="upload-file-page-report-manager"></a><span data-ttu-id="fa8dc-102">Cargar archivo (página del Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="fa8dc-102">Upload File Page (Report Manager)</span></span>
  <span data-ttu-id="fa8dc-103">Use la página Cargar archivo para publicar un archivo del sistema de archivos en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-103">Use the Upload File page to publish a file from the file system into the report server database.</span></span> <span data-ttu-id="fa8dc-104">Los archivos cargados se representan como elementos en la jerarquía de carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-104">Uploaded files are represented as items in the report server folder hierarchy.</span></span>  
  
-   <span data-ttu-id="fa8dc-105">Los archivos .rdl cargados se publican como informes en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-105">Uploaded .rdl files are published to a report server as reports.</span></span>  
  
-   <span data-ttu-id="fa8dc-106">Los archivos .smdl cargados se publican como modelos de informe si contienen información de la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-106">Uploaded .smdl files are published as report models if they contain data source view information.</span></span> <span data-ttu-id="fa8dc-107">Si les falta una referencia de vista del origen de datos, se produce un error durante la carga.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-107">If they are missing a data source view reference, an error occurs during the upload.</span></span> <span data-ttu-id="fa8dc-108">Es posible que falte información de la vista del origen de datos si se carga un archivo. SMDL desde un [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] proyecto de modelos de informe.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-108">Data source view information might be missing if you upload an .smdl file from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] report model project.</span></span> <span data-ttu-id="fa8dc-109">En los proyectos de modelo de informe, la información de la vista del origen de datos se almacena en un archivo independiente en lugar de hacerlo en el mismo archivo .smdl.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-109">In report model projects, data source view information is stored in a separate file rather than in the .smdl file itself.</span></span>  
  
     <span data-ttu-id="fa8dc-110">Los archivos de modelo que no contienen información de vista del origen de datos (y que por tanto se cargan correctamente) son aquellos que se han publicado previamente en un servidor de informes y se han guardado posteriormente del servidor a un archivo del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-110">Model files that do contain data source view information (and can therefore be successfully uploaded) are those that have been previously published to a report server and then saved from the server to a file on the file system.</span></span> <span data-ttu-id="fa8dc-111">Si abre la página Propiedades generales de un modelo y hace clic en **Editar** para abrirlo, puede guardarlo en un archivo y, a continuación, cargarlo como un nuevo modelo en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-111">If you open the General Properties page of a model and click **Edit** to open the model, you can save it to a file and then upload it as a new model on the report server.</span></span> <span data-ttu-id="fa8dc-112">El archivo .SMDL que cargue posteriormente dispondrá de toda la información necesaria para la publicación de modelos.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-112">The .smdl file that you subsequently upload will have all of information that is necessary for model publication.</span></span>  
  
-   <span data-ttu-id="fa8dc-113">Todos los demás tipos de archivo que se cargan se almacenan como recursos.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-113">All other file types that you upload are stored as resources.</span></span> <span data-ttu-id="fa8dc-114">Esto incluye archivos .rds que contienen información de conexión del origen de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-114">This includes .rds files that contain report data source connection information.</span></span> <span data-ttu-id="fa8dc-115">Al cargar un archivo .rds no se genera un elemento de origen de datos compartidos en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-115">Uploading an .rds file does not produce a shared data source item on the report server.</span></span>  
  
 <span data-ttu-id="fa8dc-116">Al cargar un elemento, se coloca en la carpeta actual.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-116">When you upload an item, it is placed in the current folder.</span></span> <span data-ttu-id="fa8dc-117">Una vez finalizada la carga, el elemento se puede mover a una ubicación diferente.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-117">After the upload is complete, you can move the item to a different location.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa8dc-118">Esta característica no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa8dc-118">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fa8dc-119">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="fa8dc-119">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="fa8dc-120">Navegación</span><span class="sxs-lookup"><span data-stu-id="fa8dc-120">Navigation</span></span>  
 <span data-ttu-id="fa8dc-121">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="fa8dc-121">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-upload-file-page"></a><span data-ttu-id="fa8dc-122">Para abrir la página Cargar archivo</span><span class="sxs-lookup"><span data-stu-id="fa8dc-122">To open the Upload File page</span></span>  
  
1.  <span data-ttu-id="fa8dc-123">Abra el Administrador de informes y desplácese hasta la carpeta en la que desea cargar un archivo.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-123">Open Report Manager, and navigate to the folder in which you want to upload a file.</span></span>  
  
2.  <span data-ttu-id="fa8dc-124">En la barra de herramientas, haga clic en **Cargar archivo**.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-124">In the toolbar, click **Upload File**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa8dc-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="fa8dc-125">Options</span></span>  
 <span data-ttu-id="fa8dc-126">**Archivo para cargar**</span><span class="sxs-lookup"><span data-stu-id="fa8dc-126">**File to Upload**</span></span>  
 <span data-ttu-id="fa8dc-127">Muestra la ruta de acceso completa del archivo que se va a copiar desde el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-127">Displays the fully qualified path to the file you are copying from the file system.</span></span>  
  
 <span data-ttu-id="fa8dc-128">**Browse**</span><span class="sxs-lookup"><span data-stu-id="fa8dc-128">**Browse**</span></span>  
 <span data-ttu-id="fa8dc-129">Haga clic para elegir un archivo del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-129">Click to choose a file from the file system.</span></span>  
  
 <span data-ttu-id="fa8dc-130">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="fa8dc-130">**Name**</span></span>  
 <span data-ttu-id="fa8dc-131">Escriba el nombre del archivo tal como desea que aparezca en el espacio de nombres del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-131">Type the name of the file, as it will appear in the report server namespace.</span></span> <span data-ttu-id="fa8dc-132">El nombre debe incluir al menos un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-132">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="fa8dc-133">También puede incluir espacios en blanco y algunos símbolos.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-133">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="fa8dc-134">No use los caracteres ; ?</span><span class="sxs-lookup"><span data-stu-id="fa8dc-134">Do not use the characters ; ?</span></span> <span data-ttu-id="fa8dc-135">: \@ & = +, $ \* \< > | "o/al especificar un nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-135">: \@ & = + , $ \* \< > | " or / when specifying an item name.</span></span>  
  
 <span data-ttu-id="fa8dc-136">**Sobrescribir elemento si existe**</span><span class="sxs-lookup"><span data-stu-id="fa8dc-136">**Overwrite item if it exists**</span></span>  
 <span data-ttu-id="fa8dc-137">Active esta casilla si desea reemplazar un elemento por una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-137">Select this check box if you want to replace an existing item with a newer version.</span></span> <span data-ttu-id="fa8dc-138">Para que se sobrescriba una versión existente, deben coincidir exactamente el nombre del elemento nuevo y el nombre del elemento existente.</span><span class="sxs-lookup"><span data-stu-id="fa8dc-138">To overwrite an existing version, the name of the new item and the existing item must be an exact match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa8dc-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa8dc-139">See Also</span></span>  
 <span data-ttu-id="fa8dc-140">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="fa8dc-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="fa8dc-141">[Administrador de informes de &#40;de página de contenido&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fa8dc-141">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="fa8dc-142">[Administrador de informes la ayuda F1](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="fa8dc-142">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="fa8dc-143">Cargar archivos a una carpeta</span><span class="sxs-lookup"><span data-stu-id="fa8dc-143">Upload Files to a Folder</span></span>](report-server/upload-files-to-a-folder.md)  
  
  
