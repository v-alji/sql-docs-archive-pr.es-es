---
title: Página nueva carpeta (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9212fc68-f0a6-4f79-83c1-84baf4d1957e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 27c6a82c4911ba42215d4ab7dcafd666ddce5d54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675235"
---
# <a name="new-folder-page-report-manager"></a><span data-ttu-id="64ea2-102">Página Nueva carpeta (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="64ea2-102">New Folder Page (Report Manager)</span></span>
  <span data-ttu-id="64ea2-103">Use la página Nueva carpeta para crear una carpeta nueva en la jerarquía de carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="64ea2-103">Use the New Folder page to create a new folder in the report server folder hierarchy.</span></span> <span data-ttu-id="64ea2-104">La carpeta será una carpeta virtual que se almacenará en una base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="64ea2-104">The folder that you create is a virtual folder that is stored in a report server database.</span></span> <span data-ttu-id="64ea2-105">No se crea en el sistema de archivos del equipo.</span><span class="sxs-lookup"><span data-stu-id="64ea2-105">The folder is not created in the file system of your computer.</span></span>  
  
 <span data-ttu-id="64ea2-106">La carpeta se crea in situ, como subcarpeta de la carpeta actualmente seleccionada.</span><span class="sxs-lookup"><span data-stu-id="64ea2-106">A folder is created in-place, as a subfolder of the folder that is currently selected.</span></span> <span data-ttu-id="64ea2-107">Antes de crear una carpeta, debe navegar hasta el lugar donde desea crearla.</span><span class="sxs-lookup"><span data-stu-id="64ea2-107">Before creating a folder, you should navigate to the location where you want to create the folder.</span></span>  
  
 <span data-ttu-id="64ea2-108">Después de crear una carpeta, puede modificar su nombre y descripción en la página de propiedades General de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="64ea2-108">After you create a folder, you can modify its name and description through the General properties page of the folder.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="64ea2-109">Navegación</span><span class="sxs-lookup"><span data-stu-id="64ea2-109">Navigation</span></span>  
 <span data-ttu-id="64ea2-110">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="64ea2-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-folder-page"></a><span data-ttu-id="64ea2-111">Para abrir la página Nueva carpeta</span><span class="sxs-lookup"><span data-stu-id="64ea2-111">To open the New Folder page</span></span>  
  
1.  <span data-ttu-id="64ea2-112">Abra el Administrador de informes y navegue hasta la carpeta en la que desea crear una nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="64ea2-112">Open Report Manager, and navigate to the folder in which you want to create a new folder.</span></span>  
  
2.  <span data-ttu-id="64ea2-113">En la barra de herramientas, haga clic en **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="64ea2-113">In the toolbar, click **New Folder**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="64ea2-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="64ea2-114">Options</span></span>  
 <span data-ttu-id="64ea2-115">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="64ea2-115">**Name**</span></span>  
 <span data-ttu-id="64ea2-116">Especifique el nombre de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="64ea2-116">Specify the name of the folder.</span></span> <span data-ttu-id="64ea2-117">El nombre debe incluir al menos un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="64ea2-117">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="64ea2-118">También puede incluir espacios en blanco y algunos símbolos.</span><span class="sxs-lookup"><span data-stu-id="64ea2-118">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="64ea2-119">No use los caracteres ; ?</span><span class="sxs-lookup"><span data-stu-id="64ea2-119">Do not use the characters ; ?</span></span> <span data-ttu-id="64ea2-120">: \@ & = +, $/\* \< > | "o/al especificar un nombre.</span><span class="sxs-lookup"><span data-stu-id="64ea2-120">: \@ & = + , $ / \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="64ea2-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="64ea2-121">**Description**</span></span>  
 <span data-ttu-id="64ea2-122">Escriba una descripción del contenido de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="64ea2-122">Type a description of folder contents.</span></span> <span data-ttu-id="64ea2-123">La descripción aparece en la página Contenido de aquellos usuarios que tengan permiso de acceso a la carpeta.</span><span class="sxs-lookup"><span data-stu-id="64ea2-123">This description appears in the Contents page to users who have permission to access the folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ea2-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64ea2-124">See Also</span></span>  
 <span data-ttu-id="64ea2-125">[Crear, eliminar o modificar una carpeta &#40;Administrador de informes&#41;](report-server/create-delete-or-modify-a-folder-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="64ea2-125">[Create, Delete, or Modify a Folder &#40;Report Manager&#41;](report-server/create-delete-or-modify-a-folder-report-manager.md) </span></span>  
 <span data-ttu-id="64ea2-126">[Página de propiedades generales, carpetas &#40;Administrador de informes&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="64ea2-126">[General Properties Page, Folders &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span></span>  
 <span data-ttu-id="64ea2-127">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="64ea2-127">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="64ea2-128">[Administrador de informes de &#40;de página de contenido&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="64ea2-128">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="64ea2-129">[Administrador de informes la ayuda F1](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="64ea2-129">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="64ea2-130">Página de propiedades generales, carpetas &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="64ea2-130">General Properties Page, Folders &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/general-properties-page-folders-report-manager.md)  
  
  
