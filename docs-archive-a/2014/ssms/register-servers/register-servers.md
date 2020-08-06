---
title: Registrar servidores
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlserverregisteredserver.dhelp
helpviewer_keywords:
- connections [SQL Server], registered servers
- registering servers
- servers [SQL Server], registering
- server management [SQL Server], registering servers
- server registration [SQL Server]
ms.assetid: c2a2513e-fa09-419c-99e7-a12d57c5a0db
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f4b23ba127c6b000b0abbe832c4c072ada78c5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671307"
---
# <a name="register-servers"></a><span data-ttu-id="3e363-102">Registrar servidores</span><span class="sxs-lookup"><span data-stu-id="3e363-102">Register Servers</span></span>
  <span data-ttu-id="3e363-103">Registrar un servidor en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] permite almacenar la información de conexión del servidor para futuras conexiones. Hay tres formas de registrar un servidor en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e363-103">Registering a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] allows you to store the server connection information for future connections.There are three ways to register a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="3e363-104">Las instancias locales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se registran automáticamente durante el primer inicio de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] después de su instalación.</span><span class="sxs-lookup"><span data-stu-id="3e363-104">Local instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are automatically registered during the first launch of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] after its installation.</span></span>  
  
2.  <span data-ttu-id="3e363-105">También puede iniciar el proceso de registro automático en cualquier momento para restaurar el registro de las instancias de los servidores locales.</span><span class="sxs-lookup"><span data-stu-id="3e363-105">You can also initiate the automatic registration process at any time, to restore the registration of local server instances.</span></span>  
  
3.  <span data-ttu-id="3e363-106">Por último, puede registrar un servidor mediante la herramienta Servidores registrados de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e363-106">Lastly, you can register a server using the Registered Servers tool in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="benefits-of-registered-servers"></a><span data-ttu-id="3e363-107">Ventajas de los servidores registrados</span><span class="sxs-lookup"><span data-stu-id="3e363-107">Benefits of Registered Servers</span></span>  
 <span data-ttu-id="3e363-108">Con Servidores registrados puede:</span><span class="sxs-lookup"><span data-stu-id="3e363-108">With Registered Servers you can:</span></span>  
  
-   <span data-ttu-id="3e363-109">Registrar servidores para conservar la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="3e363-109">Register servers to preserve the connection information.</span></span>  
  
-   <span data-ttu-id="3e363-110">Determinar si un servidor registrado está funcionando.</span><span class="sxs-lookup"><span data-stu-id="3e363-110">Determine if a registered server is running.</span></span>  
  
-   <span data-ttu-id="3e363-111">Conectar fácilmente el Explorador de objetos y el Editor de consultas a un servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="3e363-111">Easily connect Object Explorer and Query Editor to a registered server.</span></span>  
  
-   <span data-ttu-id="3e363-112">Modificar o eliminar la información de registro de un servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="3e363-112">Edit or delete the registration information for a registered server.</span></span>  
  
-   <span data-ttu-id="3e363-113">Crear grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="3e363-113">Create groups of servers.</span></span>  
  
-   <span data-ttu-id="3e363-114">Proporcionar nombres descriptivos a los servidores registrados escribiendo en el cuadro **Nombre del servidor registrado** un valor distinto al de la lista **Nombre del servidor** .</span><span class="sxs-lookup"><span data-stu-id="3e363-114">Provide user-friendly names for registered servers by providing a value in the **Registered server name** box that is different from the **Server name** list.</span></span>  
  
-   <span data-ttu-id="3e363-115">Proporcionar descripciones detalladas de los servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="3e363-115">Provide detailed descriptions for registered servers.</span></span>  
  
-   <span data-ttu-id="3e363-116">Proporcionar descripciones detalladas de los grupos de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="3e363-116">Provide detailed descriptions of registered server groups.</span></span>  
  
-   <span data-ttu-id="3e363-117">Exportar grupos de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="3e363-117">Export registered server groups.</span></span>  
  
-   <span data-ttu-id="3e363-118">Importar grupos de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="3e363-118">Import registered server groups.</span></span>  
  
-   <span data-ttu-id="3e363-119">Vea los archivos de registro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de las instancias con conexión o sin conexión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e363-119">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files for online or offline instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3e363-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="3e363-120">Related Tasks</span></span>  
 <span data-ttu-id="3e363-121">Use los temas siguientes para empezar a trabajar con servidores registrados:</span><span class="sxs-lookup"><span data-stu-id="3e363-121">Use the following topics to get started with registered servers:</span></span>  
  
|<span data-ttu-id="3e363-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3e363-122">**Description**</span></span>|<span data-ttu-id="3e363-123">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="3e363-123">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="3e363-124">Registrar instancias de servidores locales</span><span class="sxs-lookup"><span data-stu-id="3e363-124">Register local server instances</span></span>|[<span data-ttu-id="3e363-125">Registrar un servidor conectado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-125">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](register-a-connected-server-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-126">Registrar un servidor</span><span class="sxs-lookup"><span data-stu-id="3e363-126">Register a server</span></span>|[<span data-ttu-id="3e363-127">Crear un servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-127">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-128">Ver servidores registrados</span><span class="sxs-lookup"><span data-stu-id="3e363-128">View registered servers</span></span>|[<span data-ttu-id="3e363-129">Ver los servidores registrados en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e363-129">View Registered Servers in SQL Server Management Studio</span></span>](view-registered-servers-in-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-130">Quitar un servidor registrado</span><span class="sxs-lookup"><span data-stu-id="3e363-130">Remove a registered server</span></span>|[<span data-ttu-id="3e363-131">Quitar un servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-131">Remove a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](remove-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-132">Cambiar el registro de un servidor</span><span class="sxs-lookup"><span data-stu-id="3e363-132">Change a server's registration</span></span>|[<span data-ttu-id="3e363-133">Cambiar el registro de un servidor &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-133">Change a Server's Registration &#40;SQL Server Management Studio&#41;</span></span>](change-a-server-s-registration-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-134">Conectarse a un servidor registrado</span><span class="sxs-lookup"><span data-stu-id="3e363-134">Connect to a registered server</span></span>|[<span data-ttu-id="3e363-135">Conectarse a un servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-135">Connect to a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](connect-to-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-136">Desconectarse de un servidor registrado</span><span class="sxs-lookup"><span data-stu-id="3e363-136">Disconnect from a registered server</span></span>|[<span data-ttu-id="3e363-137">Desconectarse de un servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-137">Disconnect from a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](disconnect-from-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-138">Mover un servidor o un grupo de servidores registrados</span><span class="sxs-lookup"><span data-stu-id="3e363-138">Move a registered server or server group</span></span>|[<span data-ttu-id="3e363-139">Mover un servidor registrado o un grupo de servidores registrados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-139">Move a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](move-a-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="3e363-140">Cambiar el nombre de un servidor o un grupo de servidores registrados</span><span class="sxs-lookup"><span data-stu-id="3e363-140">Change the name of a registered server or server group</span></span>|[<span data-ttu-id="3e363-141">Cambiar el nombre de un servidor registrado o un grupo de servidores registrados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-141">Change the Name of a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](change-the-name-of-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="3e363-142">Crear o editar un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="3e363-142">Create or edit a server group</span></span>|[<span data-ttu-id="3e363-143">Crear o editar un grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-143">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-or-edit-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-144">Quitar un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="3e363-144">Remove a server group</span></span>|[<span data-ttu-id="3e363-145">Quitar un grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-145">Remove a Server Group &#40;SQL Server Management Studio&#41;</span></span>](remove-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-146">Exportar información de servidores registrados</span><span class="sxs-lookup"><span data-stu-id="3e363-146">Export registered server information</span></span>|[<span data-ttu-id="3e363-147">Exportar información de servidores registrados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-147">Export Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](export-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-148">Importar información de servidores registrados</span><span class="sxs-lookup"><span data-stu-id="3e363-148">Import registered server information</span></span>|[<span data-ttu-id="3e363-149">Importar información de servidores registrados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-149">Import Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](import-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="3e363-150">Crear un servidor de administración central y un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="3e363-150">Create a Central Management Server and Server Group</span></span>|[<span data-ttu-id="3e363-151">Crear un servidor de administración central y un grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-151">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-a-central-management-server-and-server-group.md)|  
|<span data-ttu-id="3e363-152">Ejecutar instrucciones en varios servidores simultáneamente</span><span class="sxs-lookup"><span data-stu-id="3e363-152">Execute statements against multiple servers simultaneously</span></span>|[<span data-ttu-id="3e363-153">Ejecutar instrucciones con varios servidores simultáneamente &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e363-153">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](execute-statements-against-multiple-servers-simultaneously.md)|  
  
## <a name="see-also"></a><span data-ttu-id="3e363-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e363-154">See Also</span></span>  
 [<span data-ttu-id="3e363-155">Servidores remotos</span><span class="sxs-lookup"><span data-stu-id="3e363-155">Remote Servers</span></span>](../../database-engine/configure-windows/remote-servers.md)  
  
  
