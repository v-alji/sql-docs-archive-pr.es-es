---
title: Administrador de conexiones de archivos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- files [Integration Services]
- connection managers [Integration Services], File
- connections [Integration Services], files
- File connection manager
ms.assetid: 019078bc-44ee-4975-9169-0f9a89e3f3be
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cebb5438003c6b14c547d14012ff1bc1175a706d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748852"
---
# <a name="file-connection-manager"></a><span data-ttu-id="7e988-102">administrador de conexiones de archivos</span><span class="sxs-lookup"><span data-stu-id="7e988-102">File Connection Manager</span></span>
  <span data-ttu-id="7e988-103">Un administrador de conexiones de archivos permite a un paquete hacer referencia a un archivo o carpeta existente o crear un archivo o carpeta en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7e988-103">A File connection manager enables a package to reference an existing file or folder, or to create a file or folder at run time.</span></span> <span data-ttu-id="7e988-104">Por ejemplo, puede hacer referencia a un archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="7e988-104">For example, you can reference an Excel file.</span></span> <span data-ttu-id="7e988-105">Ciertos componentes de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilizan información de los archivos para realizar su trabajo.</span><span class="sxs-lookup"><span data-stu-id="7e988-105">Certain components in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] use information in files to perform their work.</span></span> <span data-ttu-id="7e988-106">Por ejemplo, una tarea Ejecutar SQL puede hacer referencia a un archivo que contiene las instrucciones SQL que ejecuta la tarea.</span><span class="sxs-lookup"><span data-stu-id="7e988-106">For example, an Execute SQL task can reference a file that contains the SQL statements that the task executes.</span></span> <span data-ttu-id="7e988-107">Otros componentes realizan operaciones en los archivos.</span><span class="sxs-lookup"><span data-stu-id="7e988-107">Other components perform operations on files.</span></span> <span data-ttu-id="7e988-108">Por ejemplo, la tarea Sistema de archivos puede hacer referencia a un archivo para copiarlo en una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="7e988-108">For example, the File System task can reference a file to copy it to a new location.</span></span>  
  
## <a name="usage-types-of-the-file-connection-manager"></a><span data-ttu-id="7e988-109">Tipos de uso del administrador de conexiones de archivos</span><span class="sxs-lookup"><span data-stu-id="7e988-109">Usage Types of the File Connection Manager</span></span>  
 <span data-ttu-id="7e988-110">La propiedad `FileUsageType` del administrador de conexiones de archivos especifica la forma en que se usa la conexión de archivos.</span><span class="sxs-lookup"><span data-stu-id="7e988-110">The `FileUsageType` property of the File connection manager specifies how the file connection is used.</span></span> <span data-ttu-id="7e988-111">El administrador de conexiones de archivos puede crear un archivo, crear una carpeta, usar un archivo o una carpeta existente.</span><span class="sxs-lookup"><span data-stu-id="7e988-111">The File connection manager can create a file, create a folder, use an existing file, or use an existing folder.</span></span>  
  
 <span data-ttu-id="7e988-112">La tabla siguiente enumera los valores de `FileUsageType`.</span><span class="sxs-lookup"><span data-stu-id="7e988-112">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="7e988-113">Value</span><span class="sxs-lookup"><span data-stu-id="7e988-113">Value</span></span>|<span data-ttu-id="7e988-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e988-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="7e988-115">El administrador de conexiones de archivos usa un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="7e988-115">File connection manager uses an existing file.</span></span>|  
|`1`|<span data-ttu-id="7e988-116">El administrador de conexiones de archivos crea un archivo.</span><span class="sxs-lookup"><span data-stu-id="7e988-116">File connection manager creates a file.</span></span>|  
|`2`|<span data-ttu-id="7e988-117">El administrador de conexiones de archivos usa una carpeta existente.</span><span class="sxs-lookup"><span data-stu-id="7e988-117">File connection manager uses an existing folder.</span></span>|  
|`3`|<span data-ttu-id="7e988-118">El administrador de conexiones de archivos crea una carpeta.</span><span class="sxs-lookup"><span data-stu-id="7e988-118">File connection manager creates a folder.</span></span>|  
  
## <a name="multiple-file-or-folder-connections"></a><span data-ttu-id="7e988-119">Conexiones de varios archivos o carpetas</span><span class="sxs-lookup"><span data-stu-id="7e988-119">Multiple File or Folder Connections</span></span>  
 <span data-ttu-id="7e988-120">El administrador de conexiones de archivos puede hacer referencia a un solo archivo o carpeta.</span><span class="sxs-lookup"><span data-stu-id="7e988-120">The File connection manager can reference only one file or folder.</span></span> <span data-ttu-id="7e988-121">Para hacer referencia a varios archivos o carpetas, use, en lugar de un Administrador de conexiones de archivos, un administrador de conexiones de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="7e988-121">To reference multiple files or folders, use a Multiple Files connection manager instead of a File connection manager.</span></span> <span data-ttu-id="7e988-122">Para más información, consulte [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7e988-122">For more information, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
## <a name="configuration-of-the-file-connection-manager"></a><span data-ttu-id="7e988-123">Configuración del administrador de conexiones de archivos</span><span class="sxs-lookup"><span data-stu-id="7e988-123">Configuration of the File Connection Manager</span></span>  
 <span data-ttu-id="7e988-124">Cuando se agrega un administrador de conexiones de archivos a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve en una conexión de archivos en tiempo de ejecución, establece las propiedades de conexión de archivos y agrega la conexión de archivos a la colección `Connections` del paquete.</span><span class="sxs-lookup"><span data-stu-id="7e988-124">When you add a File connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a File connection at run time, sets the File connection properties, and adds the File connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="7e988-125">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `FILE`.</span><span class="sxs-lookup"><span data-stu-id="7e988-125">The `ConnectionManagerType` property of the connection manager is set to `FILE`.</span></span>  
  
 <span data-ttu-id="7e988-126">Puede configurar el administrador de conexiones de archivos de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e988-126">You can configure a File connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="7e988-127">Especificar el tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="7e988-127">Specify the usage type.</span></span>  
  
-   <span data-ttu-id="7e988-128">Especificar un archivo o carpeta.</span><span class="sxs-lookup"><span data-stu-id="7e988-128">Specify a file or folder.</span></span>  
  
 <span data-ttu-id="7e988-129">Para establecer la propiedad ConnectionString del administrador de conexiones de archivos, puede especificar una expresión en la ventana Propiedades de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e988-129">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="7e988-130">Pero para evitar que se produzca un error de validación al usar una expresión para especificar el archivo o la carpeta, en **Editor del administrador de conexiones de archivos**, en **Archivo/Carpeta**, agregue la ruta de acceso de un archivo o una carpeta.</span><span class="sxs-lookup"><span data-stu-id="7e988-130">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="7e988-131">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7e988-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7e988-132">Para más información sobre las propiedades que puede configurar en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Editor del administrador de conexiones de archivos](../file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="7e988-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [File Connection Manager Editor](../file-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="7e988-133">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="7e988-133">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
