---
title: 'Lección 3: Configuración de la distribución | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f248984a-0b59-4c2f-a56d-31f8dafe72b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 52b284b6186e599b7afe73bd37ab0a8348ec38da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749230"
---
# <a name="lesson-3-configuring-distribution"></a><span data-ttu-id="01446-102">Lección 3: Configurar la distribución</span><span class="sxs-lookup"><span data-stu-id="01446-102">Lesson 3: Configuring Distribution</span></span>
  <span data-ttu-id="01446-103">En esta lección configurará la distribución en el publicador y establecerá los permisos requeridos en las bases de datos de publicación y distribución.</span><span class="sxs-lookup"><span data-stu-id="01446-103">In this lesson, you will configure distribution at the Publisher and set the required permissions on the publication and distribution databases.</span></span> <span data-ttu-id="01446-104">Si ya ha configurado el distribuidor, debe deshabilitar la publicación y distribución antes de iniciar esta lección.</span><span class="sxs-lookup"><span data-stu-id="01446-104">If you have already configured the Distributor, you must first disable publishing and distribution before you begin this lesson.</span></span> <span data-ttu-id="01446-105">No lo haga si debe mantener una topología de replicación existente.</span><span class="sxs-lookup"><span data-stu-id="01446-105">Do not do this if you must retain an existing replication topology.</span></span>  
  
 <span data-ttu-id="01446-106">En este tutorial no se contempla la configuración de un publicador con un distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="01446-106">Configuring a Publisher with a remote Distributor is outside the scope of this tutorial.</span></span>  
  
### <a name="configuring-distribution-at-the-publisher"></a><span data-ttu-id="01446-107">Configurar la distribución en el publicador</span><span class="sxs-lookup"><span data-stu-id="01446-107">Configuring distribution at the Publisher</span></span>  
  
1.  <span data-ttu-id="01446-108">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="01446-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="01446-109">Haga clic con el botón derecho en la carpeta **Replicación** y luego haga clic en **Configurar distribución**.</span><span class="sxs-lookup"><span data-stu-id="01446-109">Right-click the **Replication** folder and click **Configure Distribution**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="01446-110">Si se ha conectado con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando **localhost** en lugar del nombre real del servidor, aparecerá una advertencia indicando que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se puede conectar con el servidor **'localhost'**.</span><span class="sxs-lookup"><span data-stu-id="01446-110">If you have connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using **localhost** rather than the actual server name you will be prompted with a warning that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is unable to connect to server **'localhost'**.</span></span> <span data-ttu-id="01446-111">Haga clic en **Aceptar** en el cuadro de diálogo de advertencia.</span><span class="sxs-lookup"><span data-stu-id="01446-111">Click **OK** on the warning dialog.</span></span> <span data-ttu-id="01446-112">En el cuadro de diálogo **Conectar al servidor** , cambie el **Nombre del servidor** de **localhost** al nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="01446-112">In the **Connect to Server** dialog change the **Server name** from **localhost** to the name of your server.</span></span> <span data-ttu-id="01446-113">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="01446-113">Click **Connect**.</span></span>  
  
     <span data-ttu-id="01446-114">Se iniciará el Asistente para configurar la distribución.</span><span class="sxs-lookup"><span data-stu-id="01446-114">The Distribution Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="01446-115">En la página **distribuidor** , seleccione **'** _\<ServerName>_ **' actuará como su propio distribuidor; SQL Server creará una base de datos y un registro de distribución**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="01446-115">On the **Distributor** page, select **'**_\<ServerName>_**' will act as its own Distributor; SQL Server will create a distribution database and log**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="01446-116">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se está ejecutando, en la página [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Inicio del Agente** , seleccione **Sí**, configurar el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servicio del Agente para que se inicie automáticamente.</span><span class="sxs-lookup"><span data-stu-id="01446-116">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running, on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Agent Start** page, select **Yes**, configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically.</span></span> <span data-ttu-id="01446-117">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="01446-117">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="01446-118">Escriba **\\\\** \<_Machine_Name> _**\repldata** en el cuadro de texto **carpeta de instantáneas** , donde \<*Machine_Name> \* es el nombre del publicador y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="01446-118">Enter **\\\\**\<_Machine_Name>_**\repldata** in the **Snapshot folder** text box, where \<*Machine_Name>\* is the name of the Publisher, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="01446-119">Acepte los valores predeterminados en las páginas restantes del asistente.</span><span class="sxs-lookup"><span data-stu-id="01446-119">Accept the default values on the remaining pages of the wizard.</span></span>  
  
7.  <span data-ttu-id="01446-120">Haga clic en **Finalizar** para habilitar la distribución.</span><span class="sxs-lookup"><span data-stu-id="01446-120">Click **Finish** to enable distribution.</span></span>  
  
### <a name="setting-database-permissions-at-the-publisher"></a><span data-ttu-id="01446-121">Establecer permisos de base de datos en el publicador</span><span class="sxs-lookup"><span data-stu-id="01446-121">Setting database permissions at the Publisher</span></span>  
  
1.  <span data-ttu-id="01446-122">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda **seguridad**, haga clic con el botón secundario en **inicios de sesión**y seleccione **nuevo inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="01446-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Security**, right-click **Logins**, and then select **New Login**.</span></span>  
  
2.  <span data-ttu-id="01446-123">En la página **General** , haga clic en **Buscar**, escriba \<_Machine_Name> _**\ repl_snapshot** en el cuadro **Escriba el nombre del objeto que desea seleccionar** , donde \<*Machine_Name> \* es el nombre del servidor del publicador local, haga clic en **Comprobar nombres**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="01446-123">On the **General** page, click **Search**, enter \<_Machine_Name>_**\repl_snapshot** in the **Enter the object name to select** box, where \<*Machine_Name>\* is the name of the local Publisher server, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="01446-124">En la página **asignación de usuarios** , en la lista **usuarios asignados a este inicio de sesión** , seleccione las bases de datos de **distribución** y de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01446-124">On the **User Mapping** page, in the **Users mapped to this login** list select both the **distribution** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] databases.</span></span>  
  
     <span data-ttu-id="01446-125">En la lista **pertenencia al rol** de la base de datos, seleccione el `db_owner` rol para el inicio de sesión de las dos bases de datos.</span><span class="sxs-lookup"><span data-stu-id="01446-125">In the **Database role membership** list select the `db_owner` role for the login for both databases.</span></span>  
  
4.  <span data-ttu-id="01446-126">Haga clic en **Aceptar** para crear el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="01446-126">Click **OK** to create the login.</span></span>  
  
5.  <span data-ttu-id="01446-127">Repita los pasos 1 a 4 para crear un inicio de sesión para la cuenta local de repl_logreader.</span><span class="sxs-lookup"><span data-stu-id="01446-127">Repeat steps 1-4 to create a login for the local repl_logreader account.</span></span> <span data-ttu-id="01446-128">Este inicio de sesión también se debe asignar a usuarios que son miembros del `db_owner` rol fijo de base de datos en las bases de datos de **distribución** y **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="01446-128">This login must also be mapped to users that are members of the `db_owner` fixed database role in the **distribution** and **AdventureWorks** databases.</span></span>  
  
6.  <span data-ttu-id="01446-129">Repita los pasos 1 a 4 para crear un inicio de sesión para la cuenta local de repl_distribution.</span><span class="sxs-lookup"><span data-stu-id="01446-129">Repeat steps 1-4 to create a login for the local repl_distribution account.</span></span> <span data-ttu-id="01446-130">Este inicio de sesión debe estar asignado a un usuario que sea miembro del `db_owner` rol fijo de base de datos en la base de datos de **distribución** .</span><span class="sxs-lookup"><span data-stu-id="01446-130">This login must be mapped to a user that is a member of the `db_owner` fixed database role in the **distribution** database.</span></span>  
  
7.  <span data-ttu-id="01446-131">Repita los pasos 1 a 4 para crear un inicio de sesión para la cuenta local de repl_merge.</span><span class="sxs-lookup"><span data-stu-id="01446-131">Repeat steps 1-4 to create a login for the local repl_merge account.</span></span> <span data-ttu-id="01446-132">Este inicio de sesión debe contar con asignaciones de usuario en las bases de datos **distribution** y **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="01446-132">This login must have user mappings in the **distribution** and **AdventureWorks** databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01446-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01446-133">See Also</span></span>  
 <span data-ttu-id="01446-134">[Configurar distribución](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="01446-134">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="01446-135">Modelo de seguridad del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="01446-135">Replication Agent Security Model</span></span>](security/replication-agent-security-model.md)  
  
  
