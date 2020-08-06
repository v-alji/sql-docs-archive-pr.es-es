---
title: Editor del administrador de conexiones de archivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnectionmanager.f1
helpviewer_keywords:
- File Connection Manager Editor
ms.assetid: 051c48e5-3d86-49af-b554-ff62e3de3622
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f3261b836d4800787fc078b05b15e469d3c200d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676053"
---
# <a name="file-connection-manager-editor"></a><span data-ttu-id="563f7-102">Editor del administrador de conexiones de archivos</span><span class="sxs-lookup"><span data-stu-id="563f7-102">File Connection Manager Editor</span></span>
  <span data-ttu-id="563f7-103">Utilice el cuadro de diálogo **Editor del administrador de conexiones de archivos** para especificar las propiedades utilizadas para conectarse a un archivo o una carpeta.</span><span class="sxs-lookup"><span data-stu-id="563f7-103">Use the **File Connection Manager Editor** dialog box to specify the properties used to connect to a file or a folder.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="563f7-104">Para establecer la propiedad ConnectionString del administrador de conexiones de archivos, puede especificar una expresión en la ventana Propiedades de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="563f7-104">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="563f7-105">Pero para evitar que se produzca un error de validación al usar una expresión para especificar el archivo o la carpeta, en **Editor del administrador de conexiones de archivos**, en **Archivo/Carpeta**, agregue la ruta de acceso de un archivo o una carpeta.</span><span class="sxs-lookup"><span data-stu-id="563f7-105">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="563f7-106">Para obtener más información acerca del administrador de conexiones de archivos, vea [File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="563f7-106">To learn more about the File connection manager, see [File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="563f7-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="563f7-107">Options</span></span>  
 <span data-ttu-id="563f7-108">**Tipo de uso**</span><span class="sxs-lookup"><span data-stu-id="563f7-108">**Usage Type**</span></span>  
 <span data-ttu-id="563f7-109">Especifica si el **Administrador de conexiones de archivos** se conecta a un archivo o una carpeta existente o si crea un nuevo archivo o una nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="563f7-109">Specify whether the **File Connection Manager** connects to an existing file or folder or creates a new file or folder.</span></span>  
  
|<span data-ttu-id="563f7-110">Value</span><span class="sxs-lookup"><span data-stu-id="563f7-110">Value</span></span>|<span data-ttu-id="563f7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="563f7-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="563f7-112">Crear archivo</span><span class="sxs-lookup"><span data-stu-id="563f7-112">Create file</span></span>|<span data-ttu-id="563f7-113">Crea un nuevo archivo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="563f7-113">Create a new file at run time.</span></span>|  
|<span data-ttu-id="563f7-114">Archivo existente</span><span class="sxs-lookup"><span data-stu-id="563f7-114">Existing file</span></span>|<span data-ttu-id="563f7-115">Utiliza un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="563f7-115">Use an existing file.</span></span>|  
|<span data-ttu-id="563f7-116">Crear carpeta</span><span class="sxs-lookup"><span data-stu-id="563f7-116">Create folder</span></span>|<span data-ttu-id="563f7-117">Crea una nueva carpeta en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="563f7-117">Create a new folder at run time.</span></span>|  
|<span data-ttu-id="563f7-118">Carpeta existente</span><span class="sxs-lookup"><span data-stu-id="563f7-118">Existing folder</span></span>|<span data-ttu-id="563f7-119">Utiliza una carpeta existente.</span><span class="sxs-lookup"><span data-stu-id="563f7-119">Use an existing folder.</span></span>|  
  
 <span data-ttu-id="563f7-120">**Archivo / Carpeta**</span><span class="sxs-lookup"><span data-stu-id="563f7-120">**File / Folder**</span></span>  
 <span data-ttu-id="563f7-121">Si se trata de **Archivo**, especifica el archivo que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="563f7-121">If **File**, specify the file to use.</span></span>  
  
 <span data-ttu-id="563f7-122">Si se trata de **Carpeta**, especifica la carpeta que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="563f7-122">If **Folder**, specify the folder to use.</span></span>  
  
 <span data-ttu-id="563f7-123">**Browse**</span><span class="sxs-lookup"><span data-stu-id="563f7-123">**Browse**</span></span>  
 <span data-ttu-id="563f7-124">Seleccione el archivo o la carpeta mediante el cuadro de diálogo **Seleccionar archivo** o **Buscar carpeta** .</span><span class="sxs-lookup"><span data-stu-id="563f7-124">Select the file or folder by using the **Select File** or **Browse for Folder** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="563f7-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="563f7-125">See Also</span></span>  
 [<span data-ttu-id="563f7-126">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="563f7-126">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
