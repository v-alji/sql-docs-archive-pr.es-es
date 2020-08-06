---
title: Ayuda del Administrador de configuración de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, help
ms.assetid: 6e909911-39a6-469b-b22a-3afdfd08a30b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 10a6d6052fe109892f975774a1ed65b818ef0581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748430"
---
# <a name="sql-server-configuration-manager-help"></a><span data-ttu-id="0a6dd-102">Ayuda del Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a6dd-102">SQL Server Configuration Manager Help</span></span>
  <span data-ttu-id="0a6dd-103">Use el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para configurar los servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y la conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="0a6dd-103">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and configure network connectivity.</span></span> <span data-ttu-id="0a6dd-104">Para crear o administrar objetos de base de datos, configurar la seguridad y escribir consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] , use la herramienta [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a6dd-104">To create or manage database objects, configure security, and write [!INCLUDE[tsql](../../includes/tsql-md.md)] queries, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0a6dd-105">Para obtener más información acerca de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vea los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a6dd-105">For more information about [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="0a6dd-106">En esta sección se incluyen los temas de la Ayuda F1 para los cuadros de diálogo del Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a6dd-106">This section contains the F1 Help topics for the dialogs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0a6dd-107">Configuration Manager no puede configurar versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a6dd-107">Configuration Manager cannot configure versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="services"></a><span data-ttu-id="0a6dd-108">Servicios</span><span class="sxs-lookup"><span data-stu-id="0a6dd-108">Services</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0a6dd-109">administra los servicios relacionados con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a6dd-109">Configuration Manager manages services that are related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0a6dd-110">Aunque muchas de estas tareas se pueden llevar a cabo utilizando el cuadro de diálogo Servicios de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, es importante tener en cuenta que el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] realiza operaciones adicionales en los servicios que administra, como aplicar los permisos correctos cuando se cambia la cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="0a6dd-110">Although many of these tasks can be accomplished using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services dialog, is important to note that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager performs additional operations on the services it manages, such as applying the correct permissions when the service account is changed.</span></span> <span data-ttu-id="0a6dd-111">Si se usa el cuadro de diálogo normal de los servicios de Windows para configurar cualquiera de los servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , pueden producirse errores de funcionamiento en el servicio.</span><span class="sxs-lookup"><span data-stu-id="0a6dd-111">Using the normal Windows Services dialog to configure any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services might cause the service to malfunction.</span></span>  
  
 <span data-ttu-id="0a6dd-112">Utilice el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para las siguientes tareas relacionadas con los servicios:</span><span class="sxs-lookup"><span data-stu-id="0a6dd-112">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks for services:</span></span>  
  
-   <span data-ttu-id="0a6dd-113">Iniciar, detener y pausar los servicios</span><span class="sxs-lookup"><span data-stu-id="0a6dd-113">Start, stop, and pause services</span></span>  
  
-   <span data-ttu-id="0a6dd-114">Configurar los servicios para que se inicien de forma automática o manual, para deshabilitarlos o para cambiar otras opciones de los servicios</span><span class="sxs-lookup"><span data-stu-id="0a6dd-114">Configure services to start automatically or manually, disable the services, or change other service settings</span></span>  
  
-   <span data-ttu-id="0a6dd-115">Cambiar las contraseñas de las cuentas utilizadas por los servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a6dd-115">Change the passwords for the accounts used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services</span></span>  
  
-   <span data-ttu-id="0a6dd-116">Iniciar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con marcas de seguimiento (parámetros de línea de comandos)</span><span class="sxs-lookup"><span data-stu-id="0a6dd-116">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using trace flags (command line parameters)</span></span>  
  
-   <span data-ttu-id="0a6dd-117">Ver las propiedades de los servicios</span><span class="sxs-lookup"><span data-stu-id="0a6dd-117">View the properties of services</span></span>  
  
## <a name="sql-server-network-configuration"></a><span data-ttu-id="0a6dd-118">Configuración de red de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a6dd-118">SQL Server Network Configuration</span></span>  
 <span data-ttu-id="0a6dd-119">Utilice el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para llevar a cabo las siguientes tareas relacionadas con los servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en este equipo:</span><span class="sxs-lookup"><span data-stu-id="0a6dd-119">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks related to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services on this computer:</span></span>  
  
-   <span data-ttu-id="0a6dd-120">Habilitar o deshabilitar un protocolo de red de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a6dd-120">Enable or disable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network protocol</span></span>  
  
-   <span data-ttu-id="0a6dd-121">Configurar un protocolo de red de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a6dd-121">Configure a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network protocol</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a6dd-122">Para obtener un tutorial breve sobre cómo configurar protocolos y conectar al [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], vea [Tutorial: Introducción al motor de base de datos](../../relational-databases/tutorial-getting-started-with-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="0a6dd-122">For a short tutorial about how to configure protocols and connect to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], see [Tutorial: Getting Started with the Database Engine](../../relational-databases/tutorial-getting-started-with-the-database-engine.md).</span></span>  
  
## <a name="sql-server-native-client-configuration"></a><span data-ttu-id="0a6dd-123">Configuración de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="0a6dd-123">SQL Server Native Client Configuration</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0a6dd-124">se conectan a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante la biblioteca de red de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="0a6dd-124">clients connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client network library.</span></span> <span data-ttu-id="0a6dd-125">Utilice el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para llevar a cabo las siguientes tareas relacionadas con las aplicaciones cliente en este equipo:</span><span class="sxs-lookup"><span data-stu-id="0a6dd-125">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks related to client applications on this computer:</span></span>  
  
-   <span data-ttu-id="0a6dd-126">Para las aplicaciones cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en este equipo, especificar el orden de los protocolos al conectarse a instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a6dd-126">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client applications on this computer, specify the protocol order, when connecting to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="0a6dd-127">Configurar los protocolos de conexión de cliente.</span><span class="sxs-lookup"><span data-stu-id="0a6dd-127">Configure client connection protocols.</span></span>  
  
-   <span data-ttu-id="0a6dd-128">Para las aplicaciones cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , crear alias para las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], de forma que los clientes puedan conectarse usando una cadena de conexión personalizada.</span><span class="sxs-lookup"><span data-stu-id="0a6dd-128">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client applications, create aliases for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], so that clients can connect using a custom connection string.</span></span>  
  
 <span data-ttu-id="0a6dd-129">Para obtener más información acerca de cada una de estas tareas, vea la Ayuda F1 de cada tarea.</span><span class="sxs-lookup"><span data-stu-id="0a6dd-129">For more information about each of these tasks, see F1 help for each task.</span></span>  
  
#### <a name="to-open-sql-server-configuration-manager"></a><span data-ttu-id="0a6dd-130">Para abrir el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a6dd-130">To open SQL Server Configuration Manager</span></span>  
  
-   <span data-ttu-id="0a6dd-131">En el menú **Inicio** , seleccione **Todos los programas**, **Microsoft SQL Server** (versión), **Herramientas de configuración**y, después, haga clic en **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0a6dd-131">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server** (version), point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a6dd-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a6dd-132">See Also</span></span>  
 <span data-ttu-id="0a6dd-133">[Servicios SQL Server](../../../2014/tools/configuration-manager/sql-server-services.md) </span><span class="sxs-lookup"><span data-stu-id="0a6dd-133">[SQL Server Services](../../../2014/tools/configuration-manager/sql-server-services.md) </span></span>  
 <span data-ttu-id="0a6dd-134">[SQL Server configuración de red](sql-server-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0a6dd-134">[SQL Server Network Configuration](sql-server-network-configuration.md) </span></span>  
 <span data-ttu-id="0a6dd-135">[Configuración de SQL Native Client 11,0](../../../2014/tools/configuration-manager/sql-native-client-11-0-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0a6dd-135">[SQL Native Client 11.0 Configuration](../../../2014/tools/configuration-manager/sql-native-client-11-0-configuration.md) </span></span>  
 [<span data-ttu-id="0a6dd-136">Elegir un protocolo de red</span><span class="sxs-lookup"><span data-stu-id="0a6dd-136">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
