---
title: Aspectos básicos del control de código fuente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- source controls [SQL Server Management Studio], providers
- source controls [SQL Server Management Studio]
- source controls [SQL Server Management Studio], about source controls
- source controls [SQL Server Management Studio], clients
ms.assetid: ca35b67a-104a-41fb-ac58-a61be06fe114
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1112dcd8cfdec429b27b22ea3853de859553af0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663083"
---
# <a name="source-control-basics"></a><span data-ttu-id="4de5f-102">Fundamentos del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="4de5f-102">Source Control Basics</span></span>
  <span data-ttu-id="4de5f-103">El control de código fuente hace referencia a un sistema en el que una pieza central de software del servidor almacena y realiza un seguimiento de las versiones de los archivos, además de controlar el acceso a esos archivos.</span><span class="sxs-lookup"><span data-stu-id="4de5f-103">Source control refers to a system in which a central piece of server software stores and tracks file versions, and also controls access to files.</span></span> <span data-ttu-id="4de5f-104">Un sistema típico de control de código fuente incluye un proveedor de control de código fuente y dos o más clientes de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-104">A typical source control system includes a source control provider and two or more source control clients.</span></span>  
  
## <a name="source-control-benefits"></a><span data-ttu-id="4de5f-105">Ventajas del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="4de5f-105">Source Control Benefits</span></span>  
 <span data-ttu-id="4de5f-106">La colocación de los archivos bajo control de código fuente permite</span><span class="sxs-lookup"><span data-stu-id="4de5f-106">Placing your files under source control makes it possible to</span></span>  
  
-   <span data-ttu-id="4de5f-107">Administrar el proceso mediante el que el control de los elementos pasa de una persona a otra.</span><span class="sxs-lookup"><span data-stu-id="4de5f-107">Manage the process by which the control of items passes from one person to another.</span></span> <span data-ttu-id="4de5f-108">Los proveedores de control de código fuente permiten tanto el acceso compartido como el acceso exclusivo a los archivos.</span><span class="sxs-lookup"><span data-stu-id="4de5f-108">Source control providers support both shared and exclusive file access.</span></span> <span data-ttu-id="4de5f-109">Si el acceso a los archivos de un proyecto es exclusivo, el proveedor de control de código fuente solamente permite que un usuario desproteja los archivos y los modifique cada vez.</span><span class="sxs-lookup"><span data-stu-id="4de5f-109">If access to project files is exclusive, the source control provider allows only one user at a time to check files out and modify them.</span></span> <span data-ttu-id="4de5f-110">Si el acceso es compartido, más de un usuario podrá desproteger el archivo de script. Además, el proveedor de control de código fuente proporciona un mecanismo para combinar las versiones cuando éstas se protegen.</span><span class="sxs-lookup"><span data-stu-id="4de5f-110">If access is shared, more than one user can check out the script file, and the source control provider provides a mechanism for merging the versions as they are checked in.</span></span>  
  
-   <span data-ttu-id="4de5f-111">Archivar versiones sucesivas de los elementos controlados por código fuente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-111">Archive successive versions of source-controlled items.</span></span> <span data-ttu-id="4de5f-112">Un proveedor de control de código fuente almacena los datos que distinguen una versión de un elemento controlado por código fuente de otra.</span><span class="sxs-lookup"><span data-stu-id="4de5f-112">A source control provider stores the data that distinguishes one version of a source-controlled item from another.</span></span> <span data-ttu-id="4de5f-113">El proveedor almacena las diferencias entre versiones, así como información vital sobre la versión: cuándo fue creada, cuándo fue modificada y por quién.</span><span class="sxs-lookup"><span data-stu-id="4de5f-113">The provider stores the differences between versions, as well as crucial information about the version: when it was created, when it was modified, and by whom.</span></span> <span data-ttu-id="4de5f-114">Cuando varios usuarios trabajan en el mismo archivo, deben utilizar la misma página de códigos para que las versiones se puedan comparar de una forma precisa.</span><span class="sxs-lookup"><span data-stu-id="4de5f-114">When several people are working on the same file, they must use the same code page, so that versions can be accurately compared.</span></span> <span data-ttu-id="4de5f-115">Por lo tanto, es posible recuperar cualquier versión de un elemento controlado por código fuente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-115">Consequently, you can retrieve any version of a source-controlled item.</span></span> <span data-ttu-id="4de5f-116">También se puede designar cualquier versión como última versión de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="4de5f-116">You can also designate any version to be the latest version of that item.</span></span>  
  
-   <span data-ttu-id="4de5f-117">Conservar información detallada del historial y de la versión de los elementos controlados por código fuente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-117">Maintain detailed historical and version information on source-controlled items.</span></span> <span data-ttu-id="4de5f-118">El control de código fuente almacena la fecha y la hora en que se creó el elemento, cuándo fue protegido o desprotegido y el usuario que realizó la acción.</span><span class="sxs-lookup"><span data-stu-id="4de5f-118">Source control stores the date and time on which the item was created, when it was checked out or checked in, and the user who performed the action.</span></span>  
  
-   <span data-ttu-id="4de5f-119">Colaborar en varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="4de5f-119">Collaborate across projects.</span></span> <span data-ttu-id="4de5f-120">El hecho de compartir archivos permite que varios proyectos compartan elementos controlados por código fuente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-120">File sharing makes it possible for multiple projects to share source-controlled items.</span></span> <span data-ttu-id="4de5f-121">Los cambios realizados en un elemento compartido se reflejan en todos los proyectos que comparten ese elemento.</span><span class="sxs-lookup"><span data-stu-id="4de5f-121">Changes to a shared item are reflected in all the projects that share the item.</span></span>  
  
-   <span data-ttu-id="4de5f-122">Automatizar operaciones de control de código fuente que se repiten con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="4de5f-122">Automate frequently repeated source control operations.</span></span> <span data-ttu-id="4de5f-123">Un proveedor de control de código fuente puede definir una interfaz de símbolo del sistema que sea compatible con las características clave del control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-123">A source control provider may define an interface from the command prompt that supports the key features of source control.</span></span> <span data-ttu-id="4de5f-124">Es posible utilizar esta interfaz en los archivos por lotes para automatizar las tareas de control de código fuente que se realizan con regularidad.</span><span class="sxs-lookup"><span data-stu-id="4de5f-124">You can use this interface in batch files to automate the source control tasks that you perform regularly.</span></span>  
  
-   <span data-ttu-id="4de5f-125">Recuperar archivos eliminados accidentalmente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-125">Recover from accidental deletions.</span></span> <span data-ttu-id="4de5f-126">Es posible restaurar la última versión del archivo protegido en el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-126">You can restore the latest file version checked into source control.</span></span>  
  
-   <span data-ttu-id="4de5f-127">Ahorrar espacio en disco tanto en el cliente como en el servidor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-127">Conserve disk space on both the source control client and server.</span></span> <span data-ttu-id="4de5f-128">Algunos proveedores de control de código fuente, como [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, ofrecen ahorro de espacio en disco en el servidor mediante el almacenamiento de la última versión de un archivo y las diferencias entre cada versión y la versión anterior y siguiente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-128">Some source control providers, such as [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, support disk space conservation on the server by storing the latest version of a file and the differences between each version and the version that precedes or follows it.</span></span> <span data-ttu-id="4de5f-129">En el cliente, Visual SourceSafe proporciona ahorro de espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="4de5f-129">On the client, Visual SourceSafe supports disk space conservation.</span></span> <span data-ttu-id="4de5f-130">Puede esconder carpetas y archivos para que no se descarguen en el disco local.</span><span class="sxs-lookup"><span data-stu-id="4de5f-130">You can cloak folders and files so that they are not downloaded to your local disk.</span></span>  
  
 <span data-ttu-id="4de5f-131">Las desprotecciones y protecciones de archivos y otras operaciones de control de código fuente se realizan realmente mediante un cliente de control de código fuente, como [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4de5f-131">File check outs, check ins, and other source control operations are actually accomplished through a source control client, such as [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4de5f-132">El cliente está diseñado para interactuar con el proveedor y así poner a disposición de un grupo de usuarios distribuido las funciones del proveedor.</span><span class="sxs-lookup"><span data-stu-id="4de5f-132">The client is designed to interact with the provider to make the provider's capabilities available to a distributed group of users.</span></span> <span data-ttu-id="4de5f-133">Mediante un cliente de control de código fuente, los usuarios pueden examinar los archivos almacenados por el proveedor, agregar y eliminar archivos, proteger y desproteger archivos, y recuperar copias de archivos locales.</span><span class="sxs-lookup"><span data-stu-id="4de5f-133">Using a source control client, users can browse the files stored by the provider; add and delete files; check files in and out; and retrieve copies of local files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4de5f-134">En la presente documentación se supone que se utiliza [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe como proveedor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-134">This documentation assumes that you are using [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe as your source control provider.</span></span> <span data-ttu-id="4de5f-135">Si utiliza otro proveedor de control de código fuente, puede observar diferencias entre esta documentación y el software que ejecute.</span><span class="sxs-lookup"><span data-stu-id="4de5f-135">If you are using a different source control provider, you might see differences between this documentation and the software you are running.</span></span> <span data-ttu-id="4de5f-136">Si observa diferencias, consulte la documentación de su proveedor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="4de5f-136">If you see differences, consult the documentation for your source control provider.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4de5f-137">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4de5f-137">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4de5f-138">**Task**</span><span class="sxs-lookup"><span data-stu-id="4de5f-138">**Task**</span></span>|<span data-ttu-id="4de5f-139">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="4de5f-139">**Topic**</span></span>|  
|<span data-ttu-id="4de5f-140">Establecer opciones de control de código fuente</span><span class="sxs-lookup"><span data-stu-id="4de5f-140">Set Source Control options</span></span>|[<span data-ttu-id="4de5f-141">Establecer las opciones de control de código fuente</span><span class="sxs-lookup"><span data-stu-id="4de5f-141">Set Source Control Options</span></span>](../../2014/database-engine/set-source-control-options.md)|  
|<span data-ttu-id="4de5f-142">Cambiar las conexiones del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="4de5f-142">Change source control Connections</span></span>|[<span data-ttu-id="4de5f-143">Cambiar las conexiones del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="4de5f-143">Change Source Control Connections</span></span>](../../2014/database-engine/change-source-control-connections.md)|  
|<span data-ttu-id="4de5f-144">Excluir archivos del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="4de5f-144">Exclude files from source control</span></span>|[<span data-ttu-id="4de5f-145">Excluir archivos desde el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="4de5f-145">Exclude Files from Source Control</span></span>](../../2014/database-engine/exclude-files-from-source-control.md)|  
  
  