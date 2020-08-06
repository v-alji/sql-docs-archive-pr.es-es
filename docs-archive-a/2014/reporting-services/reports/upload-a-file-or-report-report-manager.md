---
title: Cargar un archivo o un informe (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing reports [Reporting Services], uploading files
- reports [Reporting Services], publishing
- uploading reports [Reporting Services]
- uploading files [Reporting Services]
- files [Reporting Services], uploading
ms.assetid: 79027e11-f4ba-4bfd-bd8c-d334e3da02a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 119e2b22976dc227e017b81a59b698cf9eb7457f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670277"
---
# <a name="upload-a-file-or-report-report-manager"></a><span data-ttu-id="05926-102">Cargar un archivo o un informe (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="05926-102">Upload a File or Report (Report Manager)</span></span>
  <span data-ttu-id="05926-103">El Administrador de informes proporciona una característica de carga para poder agregar informes, modelos y otros archivos a un servidor de informes sin tener que publicar dichos elementos desde una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="05926-103">Report Manager provides an upload feature so that you can add reports, models, and other files to a report server without having to publish those items from a client application.</span></span> <span data-ttu-id="05926-104">Los archivos que se cargan del sistema de archivos se almacenan como elementos en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="05926-104">Files that you upload from the file system are stored as items on the report server.</span></span> <span data-ttu-id="05926-105">El tipo de archivo que se carga determina la manera de almacenarse:</span><span class="sxs-lookup"><span data-stu-id="05926-105">The type of file you upload determines how it is stored:</span></span>  
  
-   <span data-ttu-id="05926-106">Los archivos .rdl se almacenan como informes.</span><span class="sxs-lookup"><span data-stu-id="05926-106">.rdl files are stored as reports.</span></span>  
  
-   <span data-ttu-id="05926-107">Los archivos .smdl se almacenan como modelos de informe.</span><span class="sxs-lookup"><span data-stu-id="05926-107">.smdl files are stored as report models.</span></span>  
  
-   <span data-ttu-id="05926-108">Todos los demás archivos, incluyendo los archivos de origen de datos compartido (.rds), se cargan como recursos.</span><span class="sxs-lookup"><span data-stu-id="05926-108">All other files, including shared data source (.rds) files, are uploaded as resources.</span></span> <span data-ttu-id="05926-109">Los recursos no se procesan por un servidor de informes pero se pueden ver en el Administrador de informes si el servidor de informes admite el tipo MIME del archivo.</span><span class="sxs-lookup"><span data-stu-id="05926-109">Resources are not processed by a report server, but can be viewed in Report Manager if the report server supports the MIME type of the file.</span></span>  
  
### <a name="to-upload-a-file-or-report"></a><span data-ttu-id="05926-110">Para cargar un archivo o un informe</span><span class="sxs-lookup"><span data-stu-id="05926-110">To upload a file or report</span></span>  
  
1.  <span data-ttu-id="05926-111">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="05926-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="05926-112">En Administrador de informes, vaya a la página **contenido** .</span><span class="sxs-lookup"><span data-stu-id="05926-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="05926-113">Navegue a la carpeta en la que desea agregar un elemento.</span><span class="sxs-lookup"><span data-stu-id="05926-113">Navigate to the folder to which you want to add an item.</span></span>  
  
3.  <span data-ttu-id="05926-114">Haga clic en **Cargar archivo**.</span><span class="sxs-lookup"><span data-stu-id="05926-114">Click **Upload File**.</span></span>  
  
4.  <span data-ttu-id="05926-115">Haga clic en **Examinar** para seleccionar el archivo que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="05926-115">Click **Browse** to select a file to upload.</span></span> <span data-ttu-id="05926-116">Se puede cargar un archivo de definición de informe, una imagen, un documento o cualquier archivo que desee que esté disponible en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="05926-116">You can upload a report definition file, an image, a document, or any file that you want to make available on the report server.</span></span>  
  
5.  <span data-ttu-id="05926-117">Escriba el nombre del nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="05926-117">Type a name for the new item.</span></span> <span data-ttu-id="05926-118">Un nombre de elemento puede incluir espacios, pero no puede incluir caracteres reservados:</span><span class="sxs-lookup"><span data-stu-id="05926-118">An item name can include spaces, but cannot include the reserved characters: ; ?</span></span> <span data-ttu-id="05926-119">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="05926-119">: \@ & = + , $ / \* \< > |.</span></span>  
  
6.  <span data-ttu-id="05926-120">Si desea reemplazar un elemento existente por el nuevo elemento, seleccione **Sobrescribir elemento si existe**.</span><span class="sxs-lookup"><span data-stu-id="05926-120">If you want to replace an existing item with the new item, select **Overwrite item if it exists**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="05926-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05926-121">See Also</span></span>  
 <span data-ttu-id="05926-122">[Crear, eliminar o modificar un origen de datos compartido &#40;Administrador de informes&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="05926-122">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="05926-123">[Administrador de informes de &#40;de página de contenido&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="05926-123">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="05926-124">[Página Cargar archivo &#40;Administrador de informes&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="05926-124">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 [<span data-ttu-id="05926-125">Cargar archivos a una carpeta</span><span class="sxs-lookup"><span data-stu-id="05926-125">Upload Files to a Folder</span></span>](../report-server/upload-files-to-a-folder.md)  
  
  
