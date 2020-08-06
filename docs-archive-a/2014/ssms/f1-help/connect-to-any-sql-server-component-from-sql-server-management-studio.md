---
title: Conéctese a cualquier componente de SQL Server desde SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], SQL Server Management Studio
- saving connections
- components [SQL Server], connections
- SQL Server Management Studio [SQL Server], connections
ms.assetid: 5eeb41bd-b25b-4d3b-a005-a7d9e4b5978e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cd3e185ea6f289a2a6db46cdca2cb310fefbcf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746697"
---
# <a name="connect-to-any-sql-server-component-from-sql-server-management-studio"></a><span data-ttu-id="53257-102">Conectar a un componente de SQL Server desde SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="53257-102">Connect to Any SQL Server Component from SQL Server Management Studio</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="53257-103">proporciona funcionalidad para administrar todos los componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53257-103">provides functionality for managing every component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="53257-104">Utilice [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para conectarse a:</span><span class="sxs-lookup"><span data-stu-id="53257-104">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to connect to:</span></span>  
  
-   <span data-ttu-id="53257-105">Una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53257-105">An instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="53257-106">.</span><span class="sxs-lookup"><span data-stu-id="53257-106">.</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]<span data-ttu-id="53257-107">.</span><span class="sxs-lookup"><span data-stu-id="53257-107">.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="53257-108">.</span><span class="sxs-lookup"><span data-stu-id="53257-108">.</span></span>  
  
 <span data-ttu-id="53257-109">Aunque [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] permite trabajar con consultas sin necesidad de establecer primero una conexión a un origen de datos, la mayoría de las demás tareas necesitan una conexión.</span><span class="sxs-lookup"><span data-stu-id="53257-109">Although [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] allows you to work with queries without first establishing a connection to a data source, most other tasks require a connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="53257-110">proporciona el cuadro de diálogo **Conectar al servidor** para configurar las propiedades de conexión a los componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53257-110">provides the **Connect to Server** dialog box to configure connection properties to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="53257-111">Cuando se inicia [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , aparece el cuadro de diálogo **Conectar al servidor** , que le pide que se conecte a un servidor.</span><span class="sxs-lookup"><span data-stu-id="53257-111">When [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] starts, it opens the **Connect to Server** dialog box and prompts you to connect to a server.</span></span> <span data-ttu-id="53257-112">El cuadro de diálogo **Conectar al servidor** conserva la configuración de conexión de la última vez que se utilizó.</span><span class="sxs-lookup"><span data-stu-id="53257-112">The **Connect to Server** dialog box retains the connection settings from the last time it was used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53257-113">Es posible desactivar esta característica con el fin de que no se inicie ninguna conexión automáticamente.</span><span class="sxs-lookup"><span data-stu-id="53257-113">This feature can be turned off so no connection is automatically initiated.</span></span> <span data-ttu-id="53257-114">Para más información, consulte [Opciones de inicio del servicio de motor de base de datos](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="53257-114">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
## <a name="saving-connections"></a><span data-ttu-id="53257-115">guardar conexiones</span><span class="sxs-lookup"><span data-stu-id="53257-115">Saving Connections</span></span>  
 <span data-ttu-id="53257-116">Puede guardar las conexiones a servidores concretos en Servidores registrados o en proyectos del Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="53257-116">You can save connections to specific servers in Registered Servers, or you can save connections in projects with Solution Explorer.</span></span>  
  
### <a name="saving-connections-in-registered-servers"></a><span data-ttu-id="53257-117">Guardar las conexiones en Servidores registrados</span><span class="sxs-lookup"><span data-stu-id="53257-117">Saving Connections in Registered Servers</span></span>  
 <span data-ttu-id="53257-118">Al registrar un servidor, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] guarda la información de conexión en Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="53257-118">When you register a server, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] saves the connection information in Registered Servers.</span></span> <span data-ttu-id="53257-119">Para conectarse a un servidor registrado, haga doble clic en su nombre en Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="53257-119">To connect to a registered server, double-click the server name in Registered Servers.</span></span> <span data-ttu-id="53257-120">A continuación, el Explorador de objetos iniciará una conexión al servidor.</span><span class="sxs-lookup"><span data-stu-id="53257-120">Object Explorer then opens a connection to the server.</span></span>  
  
### <a name="saving-connections-in-solution-explorer"></a><span data-ttu-id="53257-121">Guardar las conexiones en el Explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="53257-121">Saving Connections in Solution Explorer</span></span>  
 <span data-ttu-id="53257-122">El Explorador de soluciones permite almacenar consultas, scripts, conexiones y otra información asociada en un proyecto.</span><span class="sxs-lookup"><span data-stu-id="53257-122">Solution Explorer allows you to store related queries, scripts, connections, and other associated information in a project.</span></span> <span data-ttu-id="53257-123">Cada proyecto de script contiene un nodo denominado **Conexiones**en el que es posible guardar una o más conexiones.</span><span class="sxs-lookup"><span data-stu-id="53257-123">Each script project contains a node called **Connections**, where you can save one or more connections.</span></span> <span data-ttu-id="53257-124">Para agregar una conexión, haga clic con el botón derecho en **Conexiones**y, a continuación, haga clic en **Nueva conexión**.</span><span class="sxs-lookup"><span data-stu-id="53257-124">To add a connection, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="53257-125">Para obtener acceso a una conexión guardada, expanda **Conexiones** y haga doble clic en la conexión.</span><span class="sxs-lookup"><span data-stu-id="53257-125">To access a saved connection, expand **Connections** and double-click the connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="53257-126">abre una ventana de consulta asociada a esa conexión.</span><span class="sxs-lookup"><span data-stu-id="53257-126">opens a query window associated with that connection.</span></span> <span data-ttu-id="53257-127">Una vez guardados, los scripts conservan la asociación a una conexión concreta.</span><span class="sxs-lookup"><span data-stu-id="53257-127">When saved, scripts retain their association to a specific connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53257-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53257-128">See Also</span></span>  
 <span data-ttu-id="53257-129">[Usar SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="53257-129">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="53257-130">Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="53257-130">Object Explorer</span></span>](../object/object-explorer.md)  
  
  
