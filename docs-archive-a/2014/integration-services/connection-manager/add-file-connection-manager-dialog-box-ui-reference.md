---
title: Referencia de la interfaz de usuario del cuadro de diálogo Agregar administrador de conexiones de archivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnection.f1
helpviewer_keywords:
- Add File Connection Manager
ms.assetid: 9370bfb5-5993-4ad8-a9cd-2de53f320f34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 044d8e2eaae9db17d7155cb354f8d009750f44d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748856"
---
# <a name="add-file-connection-manager-dialog-box-ui-reference"></a><span data-ttu-id="e24bf-102">Referencia de la interfaz de usuario del cuadro de diálogo Agregar administrador de conexiones de archivos</span><span class="sxs-lookup"><span data-stu-id="e24bf-102">Add File Connection Manager Dialog Box UI Reference</span></span>
  <span data-ttu-id="e24bf-103">Utilice el cuadro de diálogo **Agregar administrador de conexiones de archivos** para definir una conexión a un grupo de archivos o carpetas.</span><span class="sxs-lookup"><span data-stu-id="e24bf-103">Use the **Add File Connection Manager** dialog box to define a connection to a group of files or folders.</span></span>  
  
 <span data-ttu-id="e24bf-104">Para obtener más información acerca del administrador de conexiones de varios archivos, vea [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e24bf-104">To learn more about the Multiple Files connection manager, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e24bf-105">Las tareas integradas y componentes de flujo de datos en [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no usan el administrador de conexiones de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="e24bf-105">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="e24bf-106">Sin embargo, puede usar este administrador de conexiones en la tarea Script o en el componente de script.</span><span class="sxs-lookup"><span data-stu-id="e24bf-106">However, you can use this connection manager in the Script task or Script component.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e24bf-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="e24bf-107">Options</span></span>  
 <span data-ttu-id="e24bf-108">**Tipo de uso**</span><span class="sxs-lookup"><span data-stu-id="e24bf-108">**Usage type**</span></span>  
 <span data-ttu-id="e24bf-109">Especifique el tipo de archivo que va a utilizar para el administrador de conexiones de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="e24bf-109">Specify the type of files to use for the multiple files connection manager.</span></span>  
  
|<span data-ttu-id="e24bf-110">Value</span><span class="sxs-lookup"><span data-stu-id="e24bf-110">Value</span></span>|<span data-ttu-id="e24bf-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e24bf-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e24bf-112">**Crear archivos**</span><span class="sxs-lookup"><span data-stu-id="e24bf-112">**Create files**</span></span>|<span data-ttu-id="e24bf-113">El administrador de conexiones creará los archivos.</span><span class="sxs-lookup"><span data-stu-id="e24bf-113">The connection manager will create the files.</span></span>|  
|<span data-ttu-id="e24bf-114">**Archivos existentes**</span><span class="sxs-lookup"><span data-stu-id="e24bf-114">**Existing files**</span></span>|<span data-ttu-id="e24bf-115">El administrador de conexiones utilizará archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="e24bf-115">The connection manager will use existing files.</span></span>|  
|<span data-ttu-id="e24bf-116">**Crear carpetas**</span><span class="sxs-lookup"><span data-stu-id="e24bf-116">**Create folders**</span></span>|<span data-ttu-id="e24bf-117">El administrador de conexiones creará las carpetas.</span><span class="sxs-lookup"><span data-stu-id="e24bf-117">The connection manager will create the folders.</span></span>|  
|<span data-ttu-id="e24bf-118">**Carpetas existentes**</span><span class="sxs-lookup"><span data-stu-id="e24bf-118">**Existing folders**</span></span>|<span data-ttu-id="e24bf-119">El administrador de conexiones utilizará carpetas existentes.</span><span class="sxs-lookup"><span data-stu-id="e24bf-119">The connection manager will use existing folders.</span></span>|  
  
 <span data-ttu-id="e24bf-120">**Archivos/Carpetas**</span><span class="sxs-lookup"><span data-stu-id="e24bf-120">**Files / Folders**</span></span>  
 <span data-ttu-id="e24bf-121">Muestra los archivos o carpetas que se han agregado mediante los botones descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="e24bf-121">View the files or folders that you have added by using the buttons described as follows.</span></span>  
  
 <span data-ttu-id="e24bf-122">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="e24bf-122">**Add**</span></span>  
 <span data-ttu-id="e24bf-123">Agregue un archivo desde el cuadro de diálogo **Seleccionar archivos** o agregue una carpeta desde el cuadro de diálogo **Buscar carpeta** .</span><span class="sxs-lookup"><span data-stu-id="e24bf-123">Add a file by using the **Select Files** dialog box, or add a folder by using the **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="e24bf-124">**Edición**</span><span class="sxs-lookup"><span data-stu-id="e24bf-124">**Edit**</span></span>  
 <span data-ttu-id="e24bf-125">Seleccione un archivo o una carpeta y reemplácelos con un archivo o una carpeta diferentes desde el cuadro de diálogo **Seleccionar archivos** o **Buscar carpeta** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e24bf-125">Select a file or folder, and then replace it with a different file or folder by using the **Select Files** or **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="e24bf-126">**Remove**</span><span class="sxs-lookup"><span data-stu-id="e24bf-126">**Remove**</span></span>  
 <span data-ttu-id="e24bf-127">Seleccione un archivo o una carpeta y quítelos de la lista con el botón **Quitar** .</span><span class="sxs-lookup"><span data-stu-id="e24bf-127">Select a file or folder, and then remove it from the list by using the **Remove** button.</span></span>  
  
 <span data-ttu-id="e24bf-128">**Botones de flecha**</span><span class="sxs-lookup"><span data-stu-id="e24bf-128">**Arrow buttons**</span></span>  
 <span data-ttu-id="e24bf-129">Seleccione un archivo o una carpeta y utilice los botones de flecha para subirlos o bajarlos y especificar la secuencia de acceso.</span><span class="sxs-lookup"><span data-stu-id="e24bf-129">Select a file or folder, and then use the arrow buttons to move it up or down to specify the sequence of access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e24bf-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e24bf-130">See Also</span></span>  
 [<span data-ttu-id="e24bf-131">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="e24bf-131">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
  
  
