---
title: Descripción de la administración de ventanas de SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- autohide [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], tool windows
- push pin [SQL Server Management Studio]
- tool windows [SQL Server Management Studio]
ms.assetid: bebf8383-dcaf-466e-84f5-63b81c9cfe52
author: stevestein
ms.author: sstein
ms.openlocfilehash: 85e91dc146ea49cab3142115280e7e168275b981
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676805"
---
# <a name="understand-sql-server-management-studio-windows-management"></a><span data-ttu-id="b7cd3-102">Descripción de la administración de ventanas de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7cd3-102">Understand SQL Server Management Studio Windows Management</span></span>
  <span data-ttu-id="b7cd3-103">Las ventanas de herramientas de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] son un sistema muy funcional, flexible y eficaz que permite:</span><span class="sxs-lookup"><span data-stu-id="b7cd3-103">The tool windows in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] are a highly functional, flexible, and efficient system that allows you to:</span></span>  
  
-   <span data-ttu-id="b7cd3-104">Maximizar el área de trabajo del usuario para desarrollo y administración.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-104">Maximize the user workspace for development and management.</span></span>  
  
-   <span data-ttu-id="b7cd3-105">Reducir el número de ventanas sin utilizar que se muestran en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-105">Reduce the number of unused windows displayed at one time.</span></span>  
  
-   <span data-ttu-id="b7cd3-106">Personalizar fácilmente el entorno del usuario.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-106">Easily customize the user environment.</span></span>  
  
 <span data-ttu-id="b7cd3-107">La manipulación de ventanas es vital en el entorno de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7cd3-107">Manipulating windows is central to the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment.</span></span> <span data-ttu-id="b7cd3-108">Los usuarios pueden obtener acceso fácilmente a las herramientas y ventanas que usan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-108">Users can easily access the tools and windows they use frequently.</span></span> <span data-ttu-id="b7cd3-109">Además, pueden controlar cuánto espacio desean asignar a la distinta información. El entorno debe maximizar el espacio disponible para modificar consultas en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-109">Users can control how much space they want to allocate to different information, and the environment should maximize the space available for editing queries accordingly.</span></span> <span data-ttu-id="b7cd3-110">Las ventanas se pueden mover a ubicaciones diferentes de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-110">Windows can be moved to different locations on the screen.</span></span> <span data-ttu-id="b7cd3-111">Muchas ventanas se pueden desacoplar y arrastrar fuera del marco de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7cd3-111">Many windows can be undocked and dragged out of the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] frame.</span></span> <span data-ttu-id="b7cd3-112">Esto es muy útil cuando se utiliza más de un monitor.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-112">This is particularly useful when using more than one monitor.</span></span>  
  
 <span data-ttu-id="b7cd3-113">Para aumentar el área de edición mientras se conserva la funcionalidad, todas las ventanas ofrecen la característica Ocultar automáticamente, que muestra la ventana como una pestaña de una barra a lo largo del borde del entorno principal de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7cd3-113">To increase your editing space while maintaining functionality, all windows offer the Auto Hide feature, which displays the window as a tab within a bar along the border of the main [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment.</span></span> <span data-ttu-id="b7cd3-114">Cuando el puntero se coloca sobre una de estas pestañas, se muestra la ventana subyacente.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-114">When the pointer is placed over one of these tabs, the underlying window reveals itself.</span></span> <span data-ttu-id="b7cd3-115">La característica Ocultar automáticamente de una ventana puede alternarse si se hace clic en el botón **Ocultar automáticamente** , situado en la esquina superior derecha de la ventana y representado por un alfiler.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-115">Auto Hide for a window can be toggled by clicking the **Auto Hide** button, represented by a pushpin in the upper-right corner of the window.</span></span> <span data-ttu-id="b7cd3-116">También existe una opción **Ocultar todo automáticamente** en el menú **Ventana** .</span><span class="sxs-lookup"><span data-stu-id="b7cd3-116">There is also an **Auto Hide All** option on the **Window** menu.</span></span>  
  
 <span data-ttu-id="b7cd3-117">Algunos componentes pueden configurarse en modo con pestañas, donde los componentes aparecen como pestañas en la misma ubicación acoplada, o en modo de interfaz de múltiples documentos (MDI), donde cada documento tiene su propia ventana.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-117">Some components can be configured in either tabbed mode where components appear as tabs in the same docking location, or in multiple document interface (MDI) mode where each document has its own window.</span></span> <span data-ttu-id="b7cd3-118">Para configurar esta característica, en el menú **Herramientas** , haga clic en **Opciones**, en **Entorno**y, a continuación, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-118">To configure this feature, on the **Tools** menu, click **Options**, click **Environment**, and then click **General**.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b7cd3-119">Cuando un inicio de sesión (o un usuario de base de datos independiente) se conecta y se autentica, la conexión almacena la información de identidad del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-119">When a login (or a contained database user) connects and is authenticated, the connection stores identity information about the login.</span></span> <span data-ttu-id="b7cd3-120">Para un inicio de sesión con autenticación de Windows, esto incluye la información sobre la pertenencia a grupos de Windows.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-120">For a Windows Authentication login, this includes information about membership in Windows groups.</span></span> <span data-ttu-id="b7cd3-121">La identidad del inicio de sesión permanecerá autenticada mientras dure la conexión.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-121">The identity of the login remains authenticated as long as the connection is maintained.</span></span> <span data-ttu-id="b7cd3-122">Para aplicar cambios en la identidad, como un cambio o restablecimiento de contraseña de la pertenencia al grupo de Windows, el inicio de sesión debe cerrar sesión en la entidad de autenticación (Windows o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]) y volver a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-122">To force changes in the identity, such as a password reset or change in Windows group membership, the login must logoff from the authentication authority (Windows or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]), and log in again.</span></span> <span data-ttu-id="b7cd3-123">Los miembros del rol fijo de servidor **sysadmin** o cualquier inicio de sesión con el permiso **ALTER ANY CONNECTION** puede usar el comando **KILL** para finalizar una conexión y hacer que el inicio de sesión se vuelva a conectar.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-123">A member of the **sysadmin** fixed server role or any login with the **ALTER ANY CONNECTION** permission can use the **KILL** command to end a connection and force a login to reconnect.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b7cd3-124">puede reutilizar la información de conexión al abrir varias conexiones en las ventanas del Explorador de objetos y del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-124">can reuse connection information when opening multiple connections to Object Explorer and Query Editor windows.</span></span> <span data-ttu-id="b7cd3-125">Cierre todas las conexiones para forzar una reconexión.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-125">Close all connections to force reconnection.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b7cd3-126">Cuando un inicio de sesión (o un usuario de base de datos independiente) se conecta y se autentica, la conexión almacena en memoria caché información de identidad del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-126">When a login (or a contained database user) connects and is authenticated, the connection caches identity information about the login.</span></span> <span data-ttu-id="b7cd3-127">Para un inicio de sesión con autenticación de Windows, esto incluye la información sobre la pertenencia a grupos de Windows.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-127">For a Windows Authentication login, this includes information about membership in Windows groups.</span></span> <span data-ttu-id="b7cd3-128">La identidad del inicio de sesión permanecerá autenticada mientras dure la conexión.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-128">The identity of the login remains authenticated as long as the connection is maintained.</span></span> <span data-ttu-id="b7cd3-129">Para aplicar cambios en la identidad, como un cambio o restablecimiento de contraseña de la pertenencia al grupo de Windows, el inicio de sesión debe cerrar sesión en la entidad de autenticación (Windows o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]) y volver a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-129">To force changes in the identity, such as a password reset or change in Windows group membership, the login must logoff from the authentication authority (Windows or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]), and log in again.</span></span> <span data-ttu-id="b7cd3-130">Los miembros del rol fijo de servidor **sysadmin** o cualquier inicio de sesión con el permiso **ALTER ANY CONNECTION** puede usar el comando **KILL** para finalizar una conexión y hacer que el inicio de sesión se vuelva a conectar.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-130">A member of the **sysadmin** fixed server role or any login with the **ALTER ANY CONNECTION** permission can use the **KILL** command to end a connection and force a login to reconnect.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b7cd3-131">puede reutilizar la información de conexión al abrir varias conexiones en las ventanas del Explorador de objetos y del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-131">can reuse connection information when opening multiple connections to Object Explorer and Query Editor windows.</span></span> <span data-ttu-id="b7cd3-132">Cierre todas las conexiones para forzar una reconexión.</span><span class="sxs-lookup"><span data-stu-id="b7cd3-132">Close all connections to force reconnection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7cd3-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7cd3-133">See Also</span></span>  
 <span data-ttu-id="b7cd3-134">[Usar SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b7cd3-134">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="b7cd3-135">Entorno de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7cd3-135">The SQL Server Management Studio Environment</span></span>](the-sql-server-management-studio-environment.md)  
  
  