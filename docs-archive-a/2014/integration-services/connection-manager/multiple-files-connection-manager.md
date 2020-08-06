---
title: Administrador de conexiones de varios archivos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- Multiple Files connection manager
- connection managers [Integration Services], Multiple Files
- connections [Integration Services], files
- multiple file connections
ms.assetid: 10bdc56e-c5cd-4ddb-b2f7-375fe57fe8b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9ebd45aa4f0794d98be6a79125bf1874913d491
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676131"
---
# <a name="multiple-files-connection-manager"></a><span data-ttu-id="252ef-102">administrador de conexiones de varios archivos</span><span class="sxs-lookup"><span data-stu-id="252ef-102">Multiple Files Connection Manager</span></span>
  <span data-ttu-id="252ef-103">Un administrador de conexiones de varios archivos habilita un paquete para que haga referencia a los archivos y carpetas existentes o para crear archivos y carpetas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="252ef-103">A Multiple Files connection manager enables a package to reference existing files and folders, or to create files and folders at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="252ef-104">Las tareas integradas y componentes de flujo de datos en [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no usan el administrador de conexiones de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="252ef-104">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="252ef-105">Sin embargo, puede usar este administrador de conexiones en la tarea Script o en el componente de script.</span><span class="sxs-lookup"><span data-stu-id="252ef-105">However, you can use this connection manager in the Script task or Script component.</span></span> <span data-ttu-id="252ef-106">Para obtener información acerca de cómo se utilizan los administradores de conexión en la tarea Script, vea [Conectarse a orígenes de datos de la tarea Script](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="252ef-106">For information about how to use connection managers in the Script task, see [Connecting to Data Sources in the Script Task](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span></span> <span data-ttu-id="252ef-107">Para obtener información sobre cómo usar los administradores de conexión en el componente de script, vea [conectar a orígenes de datos en el componente de script] (.. /extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="252ef-107">For information about how to use connection managers in the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span></span>  
  
## <a name="usage-types-of-the-multiple-files-connection-manager"></a><span data-ttu-id="252ef-108">Tipos de uso del administrador de conexiones de varios archivos</span><span class="sxs-lookup"><span data-stu-id="252ef-108">Usage Types of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="252ef-109">La propiedad `FileUsageType` del administrador de conexiones de varios archivos especifica la forma en que se usa la conexión.</span><span class="sxs-lookup"><span data-stu-id="252ef-109">The `FileUsageType` property of the Multiple Files connection manager specifies how the connection is used.</span></span> <span data-ttu-id="252ef-110">El administrador de conexiones de varios archivos puede crear archivos, carpetas, usar archivos existentes y usar carpetas existentes.</span><span class="sxs-lookup"><span data-stu-id="252ef-110">The Multiple Files connection manager can create files, create folders, use existing files, and use existing folders.</span></span>  
  
 <span data-ttu-id="252ef-111">La tabla siguiente enumera los valores de `FileUsageType`.</span><span class="sxs-lookup"><span data-stu-id="252ef-111">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="252ef-112">Value</span><span class="sxs-lookup"><span data-stu-id="252ef-112">Value</span></span>|<span data-ttu-id="252ef-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="252ef-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="252ef-114">**0**</span><span class="sxs-lookup"><span data-stu-id="252ef-114">**0**</span></span>|<span data-ttu-id="252ef-115">El administrador de conexiones de varios archivos usa un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="252ef-115">Multiple Files connection manager uses an existing file.</span></span>|  
|<span data-ttu-id="252ef-116">**1**</span><span class="sxs-lookup"><span data-stu-id="252ef-116">**1**</span></span>|<span data-ttu-id="252ef-117">El administrador de conexiones de varios archivos crea un archivo.</span><span class="sxs-lookup"><span data-stu-id="252ef-117">Multiple Files connection manager creates a file.</span></span>|  
|<span data-ttu-id="252ef-118">**2**</span><span class="sxs-lookup"><span data-stu-id="252ef-118">**2**</span></span>|<span data-ttu-id="252ef-119">El administrador de conexiones de varios archivos usa una carpeta existente.</span><span class="sxs-lookup"><span data-stu-id="252ef-119">Multiple Files connection manager uses an existing folder.</span></span>|  
|<span data-ttu-id="252ef-120">**3**</span><span class="sxs-lookup"><span data-stu-id="252ef-120">**3**</span></span>|<span data-ttu-id="252ef-121">El administrador de conexiones de varios archivos crea una carpeta.</span><span class="sxs-lookup"><span data-stu-id="252ef-121">Multiple Files connection manager creates a folder.</span></span>|  
  
## <a name="configuration-of-the-multiple-files-connection-manager"></a><span data-ttu-id="252ef-122">Configuración del administrador de conexiones de varios archivos</span><span class="sxs-lookup"><span data-stu-id="252ef-122">Configuration of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="252ef-123">Cuando se agrega un administrador de conexiones de varios archivos a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve en una conexión de varios archivos en tiempo de ejecución, configura las propiedades de conexión de varios archivos y agrega la conexión de varios archivos a la colección `Connections` del paquete.</span><span class="sxs-lookup"><span data-stu-id="252ef-123">When you add a Multiple Files connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a Multiple Files connection at run time, sets the Multiple Files connection properties, and adds the Multiple Files connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="252ef-124">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `MULTIFILE`.</span><span class="sxs-lookup"><span data-stu-id="252ef-124">The `ConnectionManagerType` property of the connection manager is set to `MULTIFILE`.</span></span>  
  
 <span data-ttu-id="252ef-125">Puede configurar el administrador de conexiones de varios archivos de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="252ef-125">You can configure a Multiple Files connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="252ef-126">Especificar el tipo de uso de archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="252ef-126">Specify the usage type of files and folders.</span></span>  
  
-   <span data-ttu-id="252ef-127">Especificar archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="252ef-127">Specify files and folders.</span></span>  
  
-   <span data-ttu-id="252ef-128">Si usa varios archivos o carpetas, especificar el orden en que se obtiene acceso a los archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="252ef-128">If using multiple files or folders, specify the order in which the files and folders are accessed.</span></span>  
  
 <span data-ttu-id="252ef-129">Si el administrador de conexiones de varios archivos hace referencia a varios archivos y carpetas, las rutas de los archivos y carpetas se separan con la barra vertical (|).</span><span class="sxs-lookup"><span data-stu-id="252ef-129">If the Multiple Files connection manager references multiple files and folders, the paths of the files and folders are separated by the pipe (|) character.</span></span> <span data-ttu-id="252ef-130">La propiedad `ConnectionString` del administrador de conexiones tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="252ef-130">The `ConnectionString` property of the connection manager has the following format:</span></span>  
  
 \<*path*>|\<*path*>  
  
 <span data-ttu-id="252ef-131">También puede especificar varios archivos o carpetas mediante caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="252ef-131">You can also specify multiple files or folders using wildcard characters.</span></span> <span data-ttu-id="252ef-132">Por ejemplo, para hacer referencia a todos los archivos de texto de la unidad C, el valor de la `ConnectionString` propiedad se puede establecer en C: \\ \*. txt.</span><span class="sxs-lookup"><span data-stu-id="252ef-132">For example, to reference all the text files on the C drive, the value of the `ConnectionString` property can be set to C:\\*.txt.</span></span>  
  
 <span data-ttu-id="252ef-133">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="252ef-133">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="252ef-134">Para obtener más información sobre las propiedades que puede configurar en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vea [Referencia de la interfaz de usuario del cuadro de diálogo Agregar administrador de conexiones de archivos](add-file-connection-manager-dialog-box-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="252ef-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add File Connection Manager Dialog Box UI Reference](add-file-connection-manager-dialog-box-ui-reference.md).</span></span>  
  
 <span data-ttu-id="252ef-135">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="252ef-135">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
