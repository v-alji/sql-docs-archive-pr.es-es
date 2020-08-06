---
title: Modificar las cuentas de servicios de controlador y de cliente | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 44a73ddb-18ad-415c-bfbe-126ab2e3290b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62a054749f1d53323bde5c9d05a1e7632b1dda85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747368"
---
# <a name="modify-the-controller-and-client-services-accounts"></a><span data-ttu-id="de730-102">Modificar las cuentas de servicios de controlador y de cliente</span><span class="sxs-lookup"><span data-stu-id="de730-102">Modify the Controller and Client Services Accounts</span></span>
  <span data-ttu-id="de730-103">En este tema, aprenderá a modificar las cuentas de servicio del cliente y Distributed Replay Controller; y, a continuación, volverá a aplicar las listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="de730-103">In this topic, you will learn how to modify the Distributed Replay controller and client service accounts, and then reapply the access control lists (ACLs).</span></span>  
  
### <a name="to-start-or-stop-the-distributed-replay-services-using-computer-management"></a><span data-ttu-id="de730-104">Iniciar o detener los servicios de Distributed Replay utilizando Administración de equipos</span><span class="sxs-lookup"><span data-stu-id="de730-104">To start or stop the Distributed Replay services using Computer Management</span></span>  
  
1.  <span data-ttu-id="de730-105">En el equipo en el que se instalan los servicios de Distributed Replay, desde el símbolo del sistema, escriba `dcomcnfg`.</span><span class="sxs-lookup"><span data-stu-id="de730-105">On the computer on which the Distributed Replay services are installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
2.  <span data-ttu-id="de730-106">Haga doble clic en **servicios**, desplácese hacia abajo y haga clic con el botón secundario en \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<service name> \*\*y, a continuación, haga clic en **iniciar** o **detener**.</span><span class="sxs-lookup"><span data-stu-id="de730-106">Double-click **Services**, scroll down and right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<service name>**, and then click **Start** or **Stop**.</span></span>  
  
### <a name="to-modify-the-distributed-replay-controller-service"></a><span data-ttu-id="de730-107">Para modificar el servicio Distributed Replay Controller</span><span class="sxs-lookup"><span data-stu-id="de730-107">To modify the Distributed Replay controller service</span></span>  
  
1.  <span data-ttu-id="de730-108">En el equipo del controlador, detenga el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="de730-108">On the controller computer, stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="de730-109">En **Servicios**, haga clic con el botón derecho en **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller**y luego seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="de730-109">Under **Services**, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller**, and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="de730-110">En la ventana **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller** , en la pestaña **Iniciar sesión** , seleccione **Esta cuenta**, escriba la nueva cuenta de inicio de sesión o haga clic en **Examinar** para buscarla y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="de730-110">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
     <span data-ttu-id="de730-111">**Importante**: Al configurar Distributed Replay Controller, puede especificar una o más cuentas de usuario que se usarán para ejecutar los servicios Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="de730-111">**Important**: When you configure Distributed Replay Controller, you can specify one or more user accounts that will be used to run the Distributed Replay Client services.</span></span> <span data-ttu-id="de730-112">La lista siguiente es una relación de las cuentas admitidas:</span><span class="sxs-lookup"><span data-stu-id="de730-112">The following is the list of supported accounts:</span></span>  
  
    -   <span data-ttu-id="de730-113">Cuenta de usuario de dominio</span><span class="sxs-lookup"><span data-stu-id="de730-113">Domain user account</span></span>  
  
    -   <span data-ttu-id="de730-114">Cuenta de usuario local creada por el usuario</span><span class="sxs-lookup"><span data-stu-id="de730-114">User created local user account</span></span>  
  
    -   <span data-ttu-id="de730-115">Administrador</span><span class="sxs-lookup"><span data-stu-id="de730-115">Administrator</span></span>  
  
    -   <span data-ttu-id="de730-116">Cuenta virtual y MSA (cuenta de servicio administrada)</span><span class="sxs-lookup"><span data-stu-id="de730-116">Virtual account and MSA (Managed Service Account)</span></span>  
  
    -   <span data-ttu-id="de730-117">Network Services, servicios locales y sistema</span><span class="sxs-lookup"><span data-stu-id="de730-117">Network Services, Local Services, and System</span></span>  
  
     <span data-ttu-id="de730-118">No se aceptan cuentas de grupo (locales o de dominio) y otras cuentas integradas (como Todos).</span><span class="sxs-lookup"><span data-stu-id="de730-118">Group accounts (local or domain) and other built-in accounts (like Everyone) are not accepted.</span></span>  
  
4.  <span data-ttu-id="de730-119">Inicie el servicio Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="de730-119">Start the Distributed Replay controller service.</span></span>  
  
### <a name="to-modify-the-distributed-replay-client-service"></a><span data-ttu-id="de730-120">Para modificar el servicio Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="de730-120">To modify the Distributed Replay client service</span></span>  
  
1.  <span data-ttu-id="de730-121">Antes de modificar el servicio Distributed Replay Client, asegúrese de que la cuenta del servicio de cliente que va a cambiar se especificó durante la instalación (en el parámetro CTLRUSERS en el equipo del controlador).</span><span class="sxs-lookup"><span data-stu-id="de730-121">Before you modify the Distributed Replay client service, make sure the client service account you are changing was specified during setup (in the CTLRUSERS parameter on the controller computer).</span></span> <span data-ttu-id="de730-122">Si la cuenta de servicio de cliente que va a cambiar no se especificó durante la configuración, primero debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="de730-122">If the client service account you are changing was not specified during setup, you must perform the following steps first:</span></span>  
  
    1.  <span data-ttu-id="de730-123">Detenga el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="de730-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
    2.  <span data-ttu-id="de730-124">En el equipo del controlador en el que esté instalado el servicio del controlador, desde el símbolo del sistema, escriba `dcomcnfg`.</span><span class="sxs-lookup"><span data-stu-id="de730-124">On the controller computer on which the controller service is installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
    3.  <span data-ttu-id="de730-125">En la ventana **Servicios de componentes**, vaya a **Raíz de consola -> Servicios de componentes -> Equipos -> Mi PC -> DCOM Config ->DReplayController**.</span><span class="sxs-lookup"><span data-stu-id="de730-125">In the **Component Services** window, navigate to **Console Root -> Component Services -> Computers -> My Computer -> DCOM Config ->DReplayController**.</span></span>  
  
    4.  <span data-ttu-id="de730-126">Haga clic con el botón derecho en **DReplayController**y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="de730-126">Right-click **DReplayController**, and then click **Properties**.</span></span>  
  
    5.  <span data-ttu-id="de730-127">En la ventana **Propiedades de DReplayController** , en la pestaña **Seguridad** , haga clic en **Editar** en la sección **Permisos de inicio y activación** .</span><span class="sxs-lookup"><span data-stu-id="de730-127">In the **DReplayController Properties** window, on the **Security** tab, click **Edit** in the **Launch and Activation Permissions** section.</span></span>  
  
    6.  <span data-ttu-id="de730-128">Conceda a la nueva cuenta de inicio de sesión del servicio de cliente los permisos **Activación local y remota** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="de730-128">Grant the new client service logon account **Local and Remote activation** permissions, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="de730-129">Haga clic en **Editar** en la sección **Permisos de acceso** y conceda a la nueva cuenta de inicio de sesión del servicio cliente los permisos **Acceso local y remoto** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="de730-129">Click **Edit** in the **Access Permissions** section, and grant the new client service logon account **Local and Remote access** permissions, and then click **OK**.</span></span>  
  
    8.  <span data-ttu-id="de730-130">Haga clic en **Aceptar** para cerrar la ventana **Propiedades de DReplayController** .</span><span class="sxs-lookup"><span data-stu-id="de730-130">Click **OK** to close the **DReplayController Properties** window.</span></span>  
  
    9. <span data-ttu-id="de730-131">En el equipo del controlador, agregue la cuenta de inicio de sesión de servicio de cliente cambiada al grupo **Usuarios COM distribuidos** .</span><span class="sxs-lookup"><span data-stu-id="de730-131">On the controller computer, add the changed client service logon account to the **Distributed COM Users** group.</span></span>  
  
    10. <span data-ttu-id="de730-132">Inicie el servicio SQL Server Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="de730-132">Start the SQL Server Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="de730-133">Detenga el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="de730-133">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay client service.</span></span>  
  
3.  <span data-ttu-id="de730-134">En la ventana **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client** , en la pestaña **Iniciar sesión** , seleccione **Esta cuenta**, escriba la nueva cuenta de inicio de sesión o haga clic en **Examinar** para buscarla y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="de730-134">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="de730-135">Inicie el servicio Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="de730-135">Start the Distributed Replay client service.</span></span>  
  
  
