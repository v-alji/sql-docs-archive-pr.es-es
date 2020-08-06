---
title: Seleccionar origen (cuadro de diálogo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.selectsource.f1
ms.assetid: d664c2e5-dd0c-4da8-b27d-aa4ee4fc0ffd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 535d211d6827477fcf029accc27a9000e8c695c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749753"
---
# <a name="select-source-dialog-box"></a><span data-ttu-id="a97cd-102">Seleccionar origen (cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="a97cd-102">Select Source Dialog Box</span></span>
  <span data-ttu-id="a97cd-103">Utilice este cuadro de diálogo para seleccionar el origen de las directivas que se van a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a97cd-103">Use this dialog box to select the source of the policies to be run.</span></span> <span data-ttu-id="a97cd-104">Para seleccionar uno o más archivos XML que contienen directivas, seleccione **Archivos**.</span><span class="sxs-lookup"><span data-stu-id="a97cd-104">To select one or more XML files that contain policies, select **Files**.</span></span> <span data-ttu-id="a97cd-105">Para ejecutar las directivas que se buscan en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], seleccione **Servidor**.</span><span class="sxs-lookup"><span data-stu-id="a97cd-105">To run the policies that are found on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], select **Server**.</span></span>  
  
 <span data-ttu-id="a97cd-106">Puede abrir este cuadro de diálogo de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="a97cd-106">You can open this dialog box in several ways.</span></span>  
  
 <span data-ttu-id="a97cd-107">**Para abrir este cuadro de diálogo**</span><span class="sxs-lookup"><span data-stu-id="a97cd-107">**To open this dialog box**</span></span>  
  
-   <span data-ttu-id="a97cd-108">En Servidores registrados, haga clic con el botón derecho en **Grupos de servidores locales** , en cualquier servidor de **Grupos de servidores locales**o en cualquier servidor de **Servidores de administración central**y seleccione **Evaluar directivas**.</span><span class="sxs-lookup"><span data-stu-id="a97cd-108">In Registered Servers, right-click **Local Server Groups** or any server under **Local Server Groups**, or any server under **Central Management Servers**, and then select **Evaluate Policies**.</span></span> <span data-ttu-id="a97cd-109">En la página **Selección de directiva** del cuadro de diálogo **Evaluar directivas** , haga clic en el botón Examinar ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="a97cd-109">In the **Policy Selection** page of the **Evaluate Policies** dialog box, click the Browse (**...**) button.</span></span>  
  
-   <span data-ttu-id="a97cd-110">En el Explorador de objetos, expanda **Administración**, expanda **Administración de directivas**, haga clic con el botón derecho en **Directivas**y, después, seleccione **Importar directiva**.</span><span class="sxs-lookup"><span data-stu-id="a97cd-110">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and select **Import Policy**.</span></span> <span data-ttu-id="a97cd-111">En el cuadro de diálogo **Importar** , haga clic en el botón Examinar ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="a97cd-111">In the **Import** dialog box, click the Browse (**...**) button.</span></span>  
  
-   <span data-ttu-id="a97cd-112">En el Explorador de objetos, haga clic con el botón derecho en un servidor, una base de datos o un objeto de base de datos, seleccione **Directivas**y, después, seleccione **Evaluar**.</span><span class="sxs-lookup"><span data-stu-id="a97cd-112">In Object Explorer, right-click a server, database, or database object, select **Policies**, and then select **Evaluate**.</span></span> <span data-ttu-id="a97cd-113">En la página **Selección de directiva** del cuadro de diálogo **Evaluar directivas** , haga clic en el botón Examinar ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="a97cd-113">In the **Policy Selection** page of the **Evaluate Policies** dialog box, click the Browse (**...**) button.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a97cd-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="a97cd-114">Options</span></span>  
 <span data-ttu-id="a97cd-115">**Archivos**</span><span class="sxs-lookup"><span data-stu-id="a97cd-115">**Files**</span></span>  
 <span data-ttu-id="a97cd-116">Seleccione uno o más archivos XML que contienen directivas.</span><span class="sxs-lookup"><span data-stu-id="a97cd-116">Select one or more XML files that contain policies.</span></span>  
  
 <span data-ttu-id="a97cd-117">**Server**</span><span class="sxs-lookup"><span data-stu-id="a97cd-117">**Server**</span></span>  
 <span data-ttu-id="a97cd-118">Permite seleccionar un servidor que contiene las directivas que se desean ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a97cd-118">Enables you to select a server that contains the policies that you want to run.</span></span>  
  
 <span data-ttu-id="a97cd-119">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="a97cd-119">**Server type**</span></span>  
 <span data-ttu-id="a97cd-120">Solo los servidores de [!INCLUDE[ssDE](../../includes/ssde-md.md)] contienen directivas.</span><span class="sxs-lookup"><span data-stu-id="a97cd-120">Only [!INCLUDE[ssDE](../../includes/ssde-md.md)] servers contain policies.</span></span> <span data-ttu-id="a97cd-121">Este cuadro es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a97cd-121">This box is read-only.</span></span>  
  
 <span data-ttu-id="a97cd-122">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="a97cd-122">**Server name**</span></span>  
 <span data-ttu-id="a97cd-123">Seleccione la instancia de servidor a la que va a conectarse.</span><span class="sxs-lookup"><span data-stu-id="a97cd-123">Select the server instance to connect to.</span></span> <span data-ttu-id="a97cd-124">De forma predeterminada, aparecerá la instancia de servidor a la que se ha conectado por última vez.</span><span class="sxs-lookup"><span data-stu-id="a97cd-124">By default, the server instance last connected to is displayed.</span></span>  
  
 <span data-ttu-id="a97cd-125">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="a97cd-125">**Authentication**</span></span>  
 <span data-ttu-id="a97cd-126">Dispone de dos modos de autenticación cuando se conecta a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97cd-126">Two authentication modes are available when you connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="a97cd-127">**Modo de autenticación de Windows (autenticación de Windows)**</span><span class="sxs-lookup"><span data-stu-id="a97cd-127">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="a97cd-128">El modo de autenticación de Windows permite que un usuario pueda conectarse a través de una cuenta de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="a97cd-128">Windows Authentication mode allows for a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="a97cd-129">**Autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a97cd-129">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="a97cd-130">Cuando un usuario se conecta con un nombre y una contraseña de inicio de sesión específicos desde una conexión que no es de confianza, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] realiza la autenticación y comprueba si se ha configurado una cuenta de inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y si la contraseña especificada coincide con la que se ha almacenado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a97cd-130">When a user connects with a specified login name and password from a nontrusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking whether a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and whether the specified password matches the one previously recorded.</span></span> <span data-ttu-id="a97cd-131">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no tiene configurada una cuenta de inicio de sesión, la autenticación no se realizará correctamente y el usuario recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="a97cd-131">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a97cd-132">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="a97cd-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="a97cd-133">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="a97cd-133">**User name**</span></span>  
 <span data-ttu-id="a97cd-134">Escriba el nombre de usuario con el que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="a97cd-134">Enter the user name to connect with.</span></span> <span data-ttu-id="a97cd-135">Esta opción solo está disponible si ha seleccionado la autenticación de Windows para conectarse.</span><span class="sxs-lookup"><span data-stu-id="a97cd-135">This option is available only if you have selected to connect by using Windows Authentication.</span></span>  
  
 <span data-ttu-id="a97cd-136">**Inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="a97cd-136">**Login**</span></span>  
 <span data-ttu-id="a97cd-137">Escriba el inicio de sesión con el que va a conectarse.</span><span class="sxs-lookup"><span data-stu-id="a97cd-137">Enter the login to connect with.</span></span> <span data-ttu-id="a97cd-138">Esta opción solo está disponible si ha seleccionado la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para conectarse.</span><span class="sxs-lookup"><span data-stu-id="a97cd-138">This option is available only if you have selected to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="a97cd-139">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="a97cd-139">**Password**</span></span>  
 <span data-ttu-id="a97cd-140">Escriba la contraseña del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="a97cd-140">Enter the password for the login.</span></span> <span data-ttu-id="a97cd-141">Esta opción solo es editable si ha seleccionado la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para conectarse.</span><span class="sxs-lookup"><span data-stu-id="a97cd-141">This option is editable only if you have selected to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97cd-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a97cd-142">See Also</span></span>  
 <span data-ttu-id="a97cd-143">[Nodo Administración de directivas &#40;Explorador de objetos&#41;](../../ssms/object/object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="a97cd-143">[Policy Management Node &#40;Object Explorer&#41;](../../ssms/object/object-explorer.md) </span></span>  
 [<span data-ttu-id="a97cd-144">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="a97cd-144">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
