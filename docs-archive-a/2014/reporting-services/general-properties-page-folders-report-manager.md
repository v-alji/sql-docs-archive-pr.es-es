---
title: Página de propiedades generales, carpetas (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 31d99d9b-2303-4bae-9466-fb67b97cf11a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb1c3fbf2e9020ac5d1fe5ebbd1e9ed48b45adb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676887"
---
# <a name="general-properties-page-folders-report-manager"></a><span data-ttu-id="fc63f-102">Página de propiedades generales, carpetas (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="fc63f-102">General Properties Page, Folders (Report Manager)</span></span>
  <span data-ttu-id="fc63f-103">Use la página de propiedades General de carpetas para ver y establecer las propiedades de las carpetas que cree.</span><span class="sxs-lookup"><span data-stu-id="fc63f-103">Use the General properties page for folders to view and set properties for the folders that you create.</span></span> <span data-ttu-id="fc63f-104">En la parte superior de la página, aparece información sobre quién creó o modificó la carpeta y cuándo se modificó en la página Propiedades generales.</span><span class="sxs-lookup"><span data-stu-id="fc63f-104">Information about who created or modified the folder and when the folder was modified appear at the top of the General properties page.</span></span>  
  
 <span data-ttu-id="fc63f-105">Las propiedades de carpeta también incluyen opciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fc63f-105">Folder properties also include security settings.</span></span> <span data-ttu-id="fc63f-106">Para obtener más información acerca de la seguridad de las carpetas, vea [proteger carpetas](security/secure-folders.md).</span><span class="sxs-lookup"><span data-stu-id="fc63f-106">For more information about folder security, see [Secure Folders](security/secure-folders.md).</span></span>  
  
 <span data-ttu-id="fc63f-107">Las carpetas que tienen una finalidad específica, como Inicio, Mis informes y Carpetas de usuarios, no se pueden mover en el espacio de nombres del servidor de informes y su nombre no puede cambiarse.</span><span class="sxs-lookup"><span data-stu-id="fc63f-107">Special-purpose folders such as Home, My Reports, and Users folders cannot be renamed or moved within the report server namespace.</span></span> <span data-ttu-id="fc63f-108">La página de propiedades General no está disponible para estas carpetas.</span><span class="sxs-lookup"><span data-stu-id="fc63f-108">The General properties page is not available for these folders.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="fc63f-109">Navegación</span><span class="sxs-lookup"><span data-stu-id="fc63f-109">Navigation</span></span>  
 <span data-ttu-id="fc63f-110">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="fc63f-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-general-properties-page-for-a-folder"></a><span data-ttu-id="fc63f-111">Para abrir la página de propiedades General de una carpeta</span><span class="sxs-lookup"><span data-stu-id="fc63f-111">To open the General properties page for a folder</span></span>  
  
1.  <span data-ttu-id="fc63f-112">Abra el Administrador de informes y abra la carpeta para la que desea ver o configurar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="fc63f-112">Open Report Manager, and open the folder for which you want to view or configure properties.</span></span>  
  
2.  <span data-ttu-id="fc63f-113">En el título de la carpeta, en la barra de herramientas, haga clic en **Configuración de carpeta**.</span><span class="sxs-lookup"><span data-stu-id="fc63f-113">Under the folder banner, in the toolbar, click **Folder Settings**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fc63f-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="fc63f-114">Options</span></span>  
 <span data-ttu-id="fc63f-115">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="fc63f-115">**Name**</span></span>  
 <span data-ttu-id="fc63f-116">Especifique un nombre para la carpeta.</span><span class="sxs-lookup"><span data-stu-id="fc63f-116">Specify a name for the folder.</span></span> <span data-ttu-id="fc63f-117">El nombre debe incluir al menos un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="fc63f-117">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="fc63f-118">También puede incluir espacios y algunos símbolos.</span><span class="sxs-lookup"><span data-stu-id="fc63f-118">It can also include spaces and some symbols.</span></span> <span data-ttu-id="fc63f-119">No use los caracteres ; ?</span><span class="sxs-lookup"><span data-stu-id="fc63f-119">Do not use the characters ; ?</span></span> <span data-ttu-id="fc63f-120">: \@ & = +, $ \* \< > | "o/al especificar un nombre.</span><span class="sxs-lookup"><span data-stu-id="fc63f-120">: \@ & = + , $ \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="fc63f-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fc63f-121">**Description**</span></span>  
 <span data-ttu-id="fc63f-122">Escriba una descripción del contenido de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="fc63f-122">Type a description of the folder contents.</span></span> <span data-ttu-id="fc63f-123">Esta descripción se mostrará en la página Contenido para los usuarios que tengan permisos de acceso a la carpeta.</span><span class="sxs-lookup"><span data-stu-id="fc63f-123">This description appears on the Contents page for users who have permission to access the folder.</span></span>  
  
 <span data-ttu-id="fc63f-124">**Ocultar en la vista de lista**</span><span class="sxs-lookup"><span data-stu-id="fc63f-124">**Hide in list view**</span></span>  
 <span data-ttu-id="fc63f-125">Seleccione esta opción para ocultar la carpeta a usuarios que usen el modo de vista de lista en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="fc63f-125">Select this option to hide the folder from users who are using list view mode in Report Manager.</span></span> <span data-ttu-id="fc63f-126">El modo de vista de lista es el formato de vista predeterminado al explorar la jerarquía de carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fc63f-126">List view mode is the default view format when browsing the report server folder hierarchy.</span></span> <span data-ttu-id="fc63f-127">En la vista de lista, los nombres y descripciones de elementos se presentan en formato horizontal.</span><span class="sxs-lookup"><span data-stu-id="fc63f-127">In list view, item names and descriptions flow across the page.</span></span> <span data-ttu-id="fc63f-128">El formato alternativo es la vista Detalles.</span><span class="sxs-lookup"><span data-stu-id="fc63f-128">The alternate format is details view.</span></span> <span data-ttu-id="fc63f-129">La vista Detalles no incluye descripciones, pero sí otra información acerca del elemento.</span><span class="sxs-lookup"><span data-stu-id="fc63f-129">Details view omits descriptions, but includes other information about the item.</span></span> <span data-ttu-id="fc63f-130">Aunque se puede ocultar un elemento en la vista de lista, no se puede ocultar en la vista Detalles.</span><span class="sxs-lookup"><span data-stu-id="fc63f-130">Although you can hide an item in list view, you cannot hide an item in details view.</span></span> <span data-ttu-id="fc63f-131">Si desea restringir el acceso a un elemento, deberá crear una asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="fc63f-131">If you want to restrict access to an item, you must create a role assignment.</span></span>  
  
 <span data-ttu-id="fc63f-132">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="fc63f-132">**Apply**</span></span>  
 <span data-ttu-id="fc63f-133">Haga clic para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="fc63f-133">Click to save your changes.</span></span>  
  
 <span data-ttu-id="fc63f-134">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="fc63f-134">**Delete**</span></span>  
 <span data-ttu-id="fc63f-135">Haga clic para quitar la carpeta y su contenido.</span><span class="sxs-lookup"><span data-stu-id="fc63f-135">Click to remove the folder and its contents.</span></span>  
  
 <span data-ttu-id="fc63f-136">**Mover**</span><span class="sxs-lookup"><span data-stu-id="fc63f-136">**Move**</span></span>  
 <span data-ttu-id="fc63f-137">Haga clic para cambiar de posición un informe o una carpeta dentro del espacio de nombres del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fc63f-137">Click to relocate a report or folder within the report server namespace.</span></span> <span data-ttu-id="fc63f-138">Al hacer clic en este botón, se abre la página Mover elementos, que permite buscar una nueva ubicación de carpeta.</span><span class="sxs-lookup"><span data-stu-id="fc63f-138">Clicking this button opens the Move Items page that allows you to browse folders for a new folder location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc63f-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc63f-139">See Also</span></span>  
 <span data-ttu-id="fc63f-140">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="fc63f-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="fc63f-141">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="fc63f-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
