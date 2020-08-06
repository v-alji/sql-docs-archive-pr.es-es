---
title: Actualizar un recurso (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- updating resources
- resources [Reporting Services], updating
ms.assetid: d21f7493-bcf7-4e9e-9886-55ebdc1f1037
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0fca59e476c2820b715ff46729784edc562f74d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672611"
---
# <a name="update-a-resource-report-manager"></a><span data-ttu-id="ec1c0-102">Actualizar un recurso (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="ec1c0-102">Update a Resource (Report Manager)</span></span>
  <span data-ttu-id="ec1c0-103">Puede actualizar un recurso reemplazándolo por una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="ec1c0-103">You can update a resource by replacing it with a newer version.</span></span> <span data-ttu-id="ec1c0-104">Los recursos son elementos almacenados en un servidor de informes que contienen el contenido de un archivo que el usuario carga.</span><span class="sxs-lookup"><span data-stu-id="ec1c0-104">Resources are items stored on a report server that contain content from a file that you upload.</span></span> <span data-ttu-id="ec1c0-105">Puede reemplazar un recurso existente importando el contenido de archivo nuevo o diferente en el recurso existente.</span><span class="sxs-lookup"><span data-stu-id="ec1c0-105">You can replace an existing resource by importing new or different file content into the existing resource.</span></span> <span data-ttu-id="ec1c0-106">La actualización de un recurso proporciona un modo de actualizar contenido preservando las propiedades existentes y la configuración de seguridad del recurso.</span><span class="sxs-lookup"><span data-stu-id="ec1c0-106">Updating a resource provides a way to update content while preserving existing properties and security settings on the resource.</span></span>  
  
### <a name="to-update-a-resource"></a><span data-ttu-id="ec1c0-107">Para actualizar un recurso</span><span class="sxs-lookup"><span data-stu-id="ec1c0-107">To update a resource</span></span>  
  
1.  <span data-ttu-id="ec1c0-108">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="ec1c0-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="ec1c0-109">En el Administrador de informes, navegue al recurso que desea actualizar o búsquelo.</span><span class="sxs-lookup"><span data-stu-id="ec1c0-109">In Report Manager, navigate to or search for the resource you want to update.</span></span>  
  
3.  <span data-ttu-id="ec1c0-110">Haga clic en el recurso para abrirlo en la página **Vista** .</span><span class="sxs-lookup"><span data-stu-id="ec1c0-110">Click the resource to open it in the **View** page.</span></span>  
  
4.  <span data-ttu-id="ec1c0-111">Haga clic en **Propiedades** para abrir la página de propiedades **General** .</span><span class="sxs-lookup"><span data-stu-id="ec1c0-111">Click **Properties** to open the **General** properties page.</span></span>  
  
5.  <span data-ttu-id="ec1c0-112">Haga clic en **Reemplazar** para abrir la página de propiedades **Importar recurso** .</span><span class="sxs-lookup"><span data-stu-id="ec1c0-112">Click **Replace** to open the **Import Resource** page.</span></span>  
  
6.  <span data-ttu-id="ec1c0-113">Haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="ec1c0-113">Click **Browse**.</span></span>  
  
7.  <span data-ttu-id="ec1c0-114">Seleccione el archivo que desea utilizar para reemplazar el recurso actual.</span><span class="sxs-lookup"><span data-stu-id="ec1c0-114">Select the file that you want to use to replace the current resource.</span></span> <span data-ttu-id="ec1c0-115">Puede utilizar una versión actualizada del archivo de recursos o especificar un archivo con un nombre o tipo de archivo diferente.</span><span class="sxs-lookup"><span data-stu-id="ec1c0-115">You can use an updated version of the resource file, or specify a file with a different name or file type.</span></span>  
  
8.  <span data-ttu-id="ec1c0-116">Haga clic en **Aceptar** para cargar el archivo de recursos, cierre la página **Importar recurso** y guarde los cambios en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="ec1c0-116">Click **OK** to upload the resource file, close the **Import Resource** page, and save your changes to the report server.</span></span>  
  
 <span data-ttu-id="ec1c0-117">Si el recurso que está actualizando contiene una imagen que se utiliza en un informe, debe actualizar el informe para ver la imagen actualizada.</span><span class="sxs-lookup"><span data-stu-id="ec1c0-117">If the resource you are updating contains an image that is used in a report, you need to refresh the report to see the updated image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec1c0-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec1c0-118">See Also</span></span>  
 <span data-ttu-id="ec1c0-119">[Administrador de informes de &#40;de página de contenido&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ec1c0-119">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="ec1c0-120">[Página Cargar archivo &#40;Administrador de informes&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ec1c0-120">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 <span data-ttu-id="ec1c0-121">[Cargar archivos en una carpeta](upload-files-to-a-folder.md) </span><span class="sxs-lookup"><span data-stu-id="ec1c0-121">[Upload Files to a Folder](upload-files-to-a-folder.md) </span></span>  
 [<span data-ttu-id="ec1c0-122">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="ec1c0-122">Report Manager F1 Help</span></span>](../report-manager-f1-help.md)  
  
  
