---
title: Administrar servidores con SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], servers
- servers [SQL Server], administering
ms.assetid: 938bb035-e07a-4082-9f93-229d9feb6b06
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb2a6b9afba7d838cf71144f88ed7866c54ad796
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748503"
---
# <a name="administer-servers-with-sql-server-management-studio"></a><span data-ttu-id="f1be7-102">Administrar servidores con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1be7-102">Administer Servers with SQL Server Management Studio</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="f1be7-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]es un cliente administrativo completo e integrado diseñado para satisfacer los [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requisitos de administración de servidores del administrador.</span><span class="sxs-lookup"><span data-stu-id="f1be7-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] is a rich, integrated administrative client designed to meet the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] administrator's server management requirements.</span></span> <span data-ttu-id="f1be7-104">En [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], las tareas administrativas se realizan mediante el Explorador de objetos, que permite conectarse a cualquier servidor de la familia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y examinar de forma gráfica su contenido.</span><span class="sxs-lookup"><span data-stu-id="f1be7-104">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], administrative tasks are accomplished using Object Explorer, which allows you to connect to any server in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] family and graphically browse its contents.</span></span> <span data-ttu-id="f1be7-105">Un servidor puede ser una instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1be7-105">A server can be an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], or [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f1be7-106">Entre las herramientas que componen [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] se incluyen Servidores registrados, el Explorador de objetos, el Explorador de soluciones, el Explorador de plantillas, la página Detalles del Explorador de objetos y la ventana de documento.</span><span class="sxs-lookup"><span data-stu-id="f1be7-106">The tool components of [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] include Registered Servers, Object Explorer, Solution Explorer, Template Explorer, the Object Explorer Details page, and the document window.</span></span> <span data-ttu-id="f1be7-107">Para mostrar una herramienta, haga clic en su nombre en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="f1be7-107">To display a tool, on the **View** menu, click the tool name.</span></span> <span data-ttu-id="f1be7-108">Para mostrar el Editor de consultas, haga clic en el botón **Nueva consulta** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="f1be7-108">To display the Query Editor tool, click the **New Query** button on the toolbar.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f1be7-109">El tráfico de red entre [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] y [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no está cifrado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f1be7-109">Network traffic between [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is unencrypted by default.</span></span> <span data-ttu-id="f1be7-110">No trabaje con datos confidenciales (incluidas contraseñas) en [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] a menos que haya establecido una conexión cifrada.</span><span class="sxs-lookup"><span data-stu-id="f1be7-110">Do not work with sensitive data (including passwords) in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] unless you have established an encrypted connection.</span></span> <span data-ttu-id="f1be7-111">Para obtener más información, vea [Habilitar conexiones cifradas en el motor de base de datos &#40;Administrador de configuración de SQL Server&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="f1be7-111">For more information, see [Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span></span>  
  
 <span data-ttu-id="f1be7-112">Use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para:</span><span class="sxs-lookup"><span data-stu-id="f1be7-112">Use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="f1be7-113">Registrar servidores.</span><span class="sxs-lookup"><span data-stu-id="f1be7-113">Register servers.</span></span>  
  
-   <span data-ttu-id="f1be7-114">Conectarse a una instancia del [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssAS](../includes/ssas-md.md)], [!INCLUDE[ssRS](../includes/ssrs.md)] o [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1be7-114">Connect to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssAS](../includes/ssas-md.md)], [!INCLUDE[ssRS](../includes/ssrs.md)], or [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
-   <span data-ttu-id="f1be7-115">Configurar las propiedades del servidor.</span><span class="sxs-lookup"><span data-stu-id="f1be7-115">Configure server properties.</span></span>  
  
-   <span data-ttu-id="f1be7-116">Administrar la base de datos y objetos de [!INCLUDE[ssAS](../includes/ssas-md.md)] , tales como cubos, dimensiones y ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f1be7-116">Manage database and [!INCLUDE[ssAS](../includes/ssas-md.md)] objects such as cubes, dimensions, and assemblies.</span></span>  
  
-   <span data-ttu-id="f1be7-117">Crear objetos, tales como bases de datos, tablas, cubos, usuarios de base de datos e inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="f1be7-117">Create objects, such as databases, tables, cubes, database users, and logins.</span></span>  
  
-   <span data-ttu-id="f1be7-118">Administrar archivos y grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="f1be7-118">Manage files and filegroups.</span></span>  
  
-   <span data-ttu-id="f1be7-119">Adjuntar o separar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f1be7-119">Attach or detach databases.</span></span>  
  
-   <span data-ttu-id="f1be7-120">Iniciar herramientas de scripting.</span><span class="sxs-lookup"><span data-stu-id="f1be7-120">Launch scripting tools.</span></span>  
  
-   <span data-ttu-id="f1be7-121">Administrar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1be7-121">Manage security.</span></span>  
  
-   <span data-ttu-id="f1be7-122">Ver registros del sistema.</span><span class="sxs-lookup"><span data-stu-id="f1be7-122">View system logs.</span></span>  
  
-   <span data-ttu-id="f1be7-123">Supervisar la actividad actual.</span><span class="sxs-lookup"><span data-stu-id="f1be7-123">Monitor current activity.</span></span>  
  
-   <span data-ttu-id="f1be7-124">Configurar la replicación.</span><span class="sxs-lookup"><span data-stu-id="f1be7-124">Configure replication.</span></span>  
  
-   <span data-ttu-id="f1be7-125">Administrar índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="f1be7-125">Manage full-text indexes.</span></span>  
  
 <span data-ttu-id="f1be7-126">Para iniciar y detener [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , utilice el Administrador de configuración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1be7-126">To start and stop [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1be7-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1be7-127">See Also</span></span>  
 <span data-ttu-id="f1be7-128">[Usar SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="f1be7-128">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="f1be7-129">Ver o cambiar las propiedades del servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1be7-129">View or Change Server Properties &#40;SQL Server&#41;</span></span>](../database-engine/configure-windows/view-or-change-server-properties-sql-server.md)  
  
  
