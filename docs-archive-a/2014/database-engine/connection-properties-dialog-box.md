---
title: Cuadro de diálogo Propiedades de conexión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectionproperties.f1
helpviewer_keywords:
- Connection Properties dialog box
ms.assetid: 6df812ad-4d80-4503-8a23-47719ce85624
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db2817ebaf3f1655f146c060fcb79d550ad0cc8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749445"
---
# <a name="connection-properties-dialog-box"></a><span data-ttu-id="3b735-102">Propiedades de conexión, cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="3b735-102">Connection Properties Dialog Box</span></span>
  <span data-ttu-id="3b735-103">Utilice este cuadro de diálogo para ver las propiedades de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="3b735-103">Use this dialog box to view the current connection properties.</span></span> <span data-ttu-id="3b735-104">Este cuadro de diálogo está disponible cuando se hace clic en **Ver propiedades de conexión** en varios cuadros de diálogo del Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="3b735-104">This dialog box is available when you click **View connection properties** in various Object Explorer dialog boxes.</span></span> <span data-ttu-id="3b735-105">Las propiedades que aparecen en esta página son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="3b735-105">The properties displayed on this page are read-only.</span></span>  
  
 <span data-ttu-id="3b735-106">Para cambiar propiedades tales como **Base de datos**, conéctese a la base de datos deseada con el Explorador de objetos antes de abrir el cuadro de diálogo **Propiedades de conexión** .</span><span class="sxs-lookup"><span data-stu-id="3b735-106">To change properties such as **Database**, connect to the desired database with Object Explorer before opening the **Connection Properties** dialog box.</span></span>  
  
 <span data-ttu-id="3b735-107">Observe que el tiempo de espera de consulta para SQL Azure es de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="3b735-107">Note that the query time-out period for SQL Azure is 30 minutes.</span></span>  
  
## <a name="authentication"></a><span data-ttu-id="3b735-108">Authentication</span><span class="sxs-lookup"><span data-stu-id="3b735-108">Authentication</span></span>  
 <span data-ttu-id="3b735-109">Vea las propiedades de autenticación de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="3b735-109">View authentication properties for the current connection.</span></span> <span data-ttu-id="3b735-110">Las propiedades de autenticación son el inicio de sesión y el método de autenticación cuando se establece la conexión.</span><span class="sxs-lookup"><span data-stu-id="3b735-110">Authentication properties are the login and authentication method when the connection was established.</span></span> <span data-ttu-id="3b735-111">Para cambiar las propiedades de autenticación, desconéctese de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y, a continuación, vuelva a conectar explorador de objetos con el servidor, con las opciones de conexión deseadas.</span><span class="sxs-lookup"><span data-stu-id="3b735-111">To change the authentication properties, disconnect from [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then connect Object Explorer to the server again, using the desired connection options.</span></span>  
  
 <span data-ttu-id="3b735-112">**Método de autenticación**</span><span class="sxs-lookup"><span data-stu-id="3b735-112">**Authentication Method**</span></span>  
 <span data-ttu-id="3b735-113">El método de autenticación que utiliza la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="3b735-113">The authentication method used for the current connection.</span></span>  
  
 <span data-ttu-id="3b735-114">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="3b735-114">**User Name**</span></span>  
 <span data-ttu-id="3b735-115">El nombre de usuario del inicio de sesión para la autenticación de la conexión.</span><span class="sxs-lookup"><span data-stu-id="3b735-115">The name of the user of login used for the connection authentication.</span></span>  
  
## <a name="connection-category"></a><span data-ttu-id="3b735-116">Categoría de la conexión</span><span class="sxs-lookup"><span data-stu-id="3b735-116">Connection Category</span></span>  
 <span data-ttu-id="3b735-117">Vea las propiedades de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="3b735-117">View connection properties for the current connection.</span></span> <span data-ttu-id="3b735-118">La mayoría de las propiedades de conexión se seleccionaron en la pestaña **Propiedades de conexión** del cuadro de diálogo **Conectar al servidor** durante el proceso de conexión.</span><span class="sxs-lookup"><span data-stu-id="3b735-118">Most connection properties were selected on the **Connection Properties** tab of the **Connect to server** dialog box during the connection process.</span></span>  
  
 <span data-ttu-id="3b735-119">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="3b735-119">**Database**</span></span>  
 <span data-ttu-id="3b735-120">Nombre de la base de datos a la que está conectado.</span><span class="sxs-lookup"><span data-stu-id="3b735-120">The name of the database currently connected to.</span></span> <span data-ttu-id="3b735-121">Para efectuar cambios, use la barra de herramientas del Editor SQL.</span><span class="sxs-lookup"><span data-stu-id="3b735-121">To change this use, the SQL Editor toolbar.</span></span>  
  
 <span data-ttu-id="3b735-122">**SPID**</span><span class="sxs-lookup"><span data-stu-id="3b735-122">**SPID**</span></span>  
 <span data-ttu-id="3b735-123">Id. de proceso del sistema que asigna el servidor a la conexión.</span><span class="sxs-lookup"><span data-stu-id="3b735-123">The system process ID assigned by the server to the connection.</span></span> <span data-ttu-id="3b735-124">No puede cambiarse para esta conexión.</span><span class="sxs-lookup"><span data-stu-id="3b735-124">This cannot be changed for this connection.</span></span>  
  
 <span data-ttu-id="3b735-125">**Protocolo de red**</span><span class="sxs-lookup"><span data-stu-id="3b735-125">**Network Protocol**</span></span>  
 <span data-ttu-id="3b735-126">Protocolo de red de la conexión [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b735-126">The network protocol of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] connection.</span></span> <span data-ttu-id="3b735-127">Para cambiar esta opción, conéctese de nuevo con las propiedades de conexión deseadas.</span><span class="sxs-lookup"><span data-stu-id="3b735-127">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="3b735-128">**Tamaño de paquete de red**</span><span class="sxs-lookup"><span data-stu-id="3b735-128">**Network Packet Size**</span></span>  
 <span data-ttu-id="3b735-129">Tamaño del paquete que se utiliza en la comunicación con el servidor.</span><span class="sxs-lookup"><span data-stu-id="3b735-129">The packet size used when communicating with the server.</span></span> <span data-ttu-id="3b735-130">Para cambiar esta opción, conéctese de nuevo con las propiedades de conexión deseadas.</span><span class="sxs-lookup"><span data-stu-id="3b735-130">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="3b735-131">**Tiempo de espera de conexión**</span><span class="sxs-lookup"><span data-stu-id="3b735-131">**Connection Timeout**</span></span>  
 <span data-ttu-id="3b735-132">Intervalo de tiempo de espera (en segundos) al conectarse a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] antes de que se agote el tiempo y se devuelva un error de conexión al usuario.</span><span class="sxs-lookup"><span data-stu-id="3b735-132">The amount of time is seconds to wait when connecting to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before timing out and returning a failure to connect error to the user.</span></span> <span data-ttu-id="3b735-133">Para cambiar esta opción, conéctese de nuevo con las propiedades de conexión deseadas.</span><span class="sxs-lookup"><span data-stu-id="3b735-133">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="3b735-134">**Tiempo de espera de ejecución**</span><span class="sxs-lookup"><span data-stu-id="3b735-134">**Execution Timeout**</span></span>  
 <span data-ttu-id="3b735-135">Intervalo de tiempo (en segundos) que hay que esperar antes de que finalice la ejecución de una tarea en el servidor.</span><span class="sxs-lookup"><span data-stu-id="3b735-135">The amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="3b735-136">Para cambiar esta opción, conéctese de nuevo con las propiedades de conexión deseadas.</span><span class="sxs-lookup"><span data-stu-id="3b735-136">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="3b735-137">**Cifrado**</span><span class="sxs-lookup"><span data-stu-id="3b735-137">**Encrypted**</span></span>  
 <span data-ttu-id="3b735-138">Indica si la conexión actual está cifrada.</span><span class="sxs-lookup"><span data-stu-id="3b735-138">Whether the current connection is encrypted.</span></span> <span data-ttu-id="3b735-139">Para cambiar esta opción, conéctese de nuevo con las propiedades de conexión deseadas.</span><span class="sxs-lookup"><span data-stu-id="3b735-139">To change this, connect again with the desired connection properties.</span></span>  
  
## <a name="product-category"></a><span data-ttu-id="3b735-140">Categoría de productos</span><span class="sxs-lookup"><span data-stu-id="3b735-140">Product Category</span></span>  
 <span data-ttu-id="3b735-141">Vea las propiedades del producto de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="3b735-141">View product properties for the current connection.</span></span> <span data-ttu-id="3b735-142">Estas propiedades describen el producto, la versión, el nombre de instancia y la intercalación del servidor.</span><span class="sxs-lookup"><span data-stu-id="3b735-142">These properties describe the server product, version, instance name, and collation.</span></span> <span data-ttu-id="3b735-143">Las propiedades se configuran durante la instalación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b735-143">The properties are set during [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="3b735-144">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="3b735-144">**Product Name**</span></span>  
 <span data-ttu-id="3b735-145">El nombre del producto [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b735-145">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product name.</span></span>  
  
 <span data-ttu-id="3b735-146">**Versión del producto**</span><span class="sxs-lookup"><span data-stu-id="3b735-146">**Product Version**</span></span>  
 <span data-ttu-id="3b735-147">Versión del producto [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b735-147">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product version.</span></span>  
  
 <span data-ttu-id="3b735-148">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="3b735-148">**Server Name**</span></span>  
 <span data-ttu-id="3b735-149">Nombre del equipo que ejecuta [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b735-149">The name of the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3b735-150">**Nombre de instancia**</span><span class="sxs-lookup"><span data-stu-id="3b735-150">**Instance Name**</span></span>  
 <span data-ttu-id="3b735-151">Nombre de instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="3b735-151">The instance name of the server.</span></span> <span data-ttu-id="3b735-152">Está en blanco de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3b735-152">The default instance is blank.</span></span>  
  
 <span data-ttu-id="3b735-153">**Lenguaje**</span><span class="sxs-lookup"><span data-stu-id="3b735-153">**Language**</span></span>  
 <span data-ttu-id="3b735-154">La versión de idioma del producto [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b735-154">The language version of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product.</span></span>  
  
 <span data-ttu-id="3b735-155">**Intercalación**</span><span class="sxs-lookup"><span data-stu-id="3b735-155">**Collation**</span></span>  
 <span data-ttu-id="3b735-156">La intercalación del servidor.</span><span class="sxs-lookup"><span data-stu-id="3b735-156">The collation of the server.</span></span>  
  
## <a name="server-environment-category"></a><span data-ttu-id="3b735-157">Categoría del entorno del servidor</span><span class="sxs-lookup"><span data-stu-id="3b735-157">Server Environment Category</span></span>  
 <span data-ttu-id="3b735-158">Vea las propiedades del entorno del servidor de la conexión actual en relación con el hardware del servidor y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3b735-158">View server environment properties for the current connection related to the server hardware and operating system.</span></span> <span data-ttu-id="3b735-159">No se pueden configurar las propiedades con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b735-159">The properties cannot be configured by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3b735-160">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="3b735-160">**Computer Name**</span></span>  
 <span data-ttu-id="3b735-161">El nombre del equipo servidor que ejecuta [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b735-161">The name of the server computer that is running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3b735-162">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="3b735-162">**Platform**</span></span>  
 <span data-ttu-id="3b735-163">El nombre del sistema operativo, el nombre del fabricante y la familia de CPU del servidor.</span><span class="sxs-lookup"><span data-stu-id="3b735-163">The operating system name, manufacturer name, and CPU family of the server.</span></span>  
  
 <span data-ttu-id="3b735-164">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="3b735-164">**Operating System**</span></span>  
 <span data-ttu-id="3b735-165">La versión de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows instalada en el servidor.</span><span class="sxs-lookup"><span data-stu-id="3b735-165">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows version installed on the server.</span></span>  
  
 <span data-ttu-id="3b735-166">**Procesadores**</span><span class="sxs-lookup"><span data-stu-id="3b735-166">**Processors**</span></span>  
 <span data-ttu-id="3b735-167">Número de procesadores del servidor.</span><span class="sxs-lookup"><span data-stu-id="3b735-167">The number of processors on the server.</span></span>  
  
 <span data-ttu-id="3b735-168">**Memoria del sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="3b735-168">**Operating System Memory**</span></span>  
 <span data-ttu-id="3b735-169">La cantidad total de memoria física del servidor, en megabytes.</span><span class="sxs-lookup"><span data-stu-id="3b735-169">The total amount of physical memory on the server, in megabytes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b735-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b735-170">See Also</span></span>  
 <span data-ttu-id="3b735-171">[Páginas de propiedades en SQL Server Management Studio](../ssms/property-pages-in-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3b735-171">[Property Pages in SQL Server Management Studio](../ssms/property-pages-in-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="3b735-172">Conectar al servidor &#40;Página Inicio de sesión&#41; Motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="3b735-172">Connect to Server &#40;Login Page&#41; Database Engine</span></span>](../ssms/f1-help/connect-to-server-login-page-database-engine.md)  
  
  
