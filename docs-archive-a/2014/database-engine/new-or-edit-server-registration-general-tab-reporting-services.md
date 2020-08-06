---
title: Nuevo o editar el registro de servidor (pestaña general) (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.reportserver.f1
ms.assetid: 5f899a8e-52ef-46b5-b7a9-f200ccd9f724
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 195756498dcefe4686d4b06e758dba9919c0b304
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676656"
---
# <a name="new-or-edit-server-registration-general-tab-reporting-services"></a><span data-ttu-id="19e8d-102">Nuevo o Editar propiedades de registro de servidor (pestaña General de Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="19e8d-102">New or Edit Server Registration (General Tab) (Reporting Services)</span></span>
  <span data-ttu-id="19e8d-103">Utilice esta pestaña para especificar opciones cuando registre una instancia de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19e8d-103">Use this tab to specify options when registering an instance of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="19e8d-104">Para obtener acceso a esta página, en Servidores registrados, haga clic en **Reporting Services** , en la barra de herramientas de **Servidores registrados** haga clic con el botón derecho en cualquier grupo de servidores registrados como, por ejemplo, **Reporting Services**, seleccione **Nuevo**y haga clic en **Registro de servidor**.</span><span class="sxs-lookup"><span data-stu-id="19e8d-104">To access this page, in Registered Servers, click **Reporting Services** on the **Registered Servers** toolbar, right-click any registered servers group such as **Reporting Services**, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="19e8d-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="19e8d-105">Options</span></span>  
 <span data-ttu-id="19e8d-106">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="19e8d-106">**Server type**</span></span>  
 <span data-ttu-id="19e8d-107">Cuando se registra un servidor desde servidores registrados, el cuadro **tipo de servidor** es de solo lectura y coincide con el tipo de servidor que se muestra en el panel **servidores registrados** .</span><span class="sxs-lookup"><span data-stu-id="19e8d-107">When a server is registered from Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in the **Registered Servers** pane.</span></span> <span data-ttu-id="19e8d-108">Para registrar un tipo de servidor diferente, haga clic en el servidor que desee en la barra de herramientas de **Servidores registrados** antes de comenzar a registrar un nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="19e8d-108">To register a different type of server, click the server you want on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="19e8d-109">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="19e8d-109">**Server name**</span></span>  
 <span data-ttu-id="19e8d-110">Especifique la instancia de servidor de informes a la que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="19e8d-110">Specify the report server instance to connect to.</span></span> <span data-ttu-id="19e8d-111">En [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], puede tener acceso al servidor de informes a través de su nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="19e8d-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], you can access a report server through its instance name.</span></span> <span data-ttu-id="19e8d-112">Puede tener una instancia de servidor de informes para cada instancia de SQL Server que instale.</span><span class="sxs-lookup"><span data-stu-id="19e8d-112">You can have one report server instance for each SQL Server instance that you install.</span></span> <span data-ttu-id="19e8d-113">Si utiliza la instancia predeterminada, escriba el nombre de la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="19e8d-113">If you are using the default instance, type the name of the SQL Server instance.</span></span> <span data-ttu-id="19e8d-114">Si utiliza una instancia con nombre, especifique la instancia con nombre para conectar al servidor de informes en el formato MSSQL$InstanceName.</span><span class="sxs-lookup"><span data-stu-id="19e8d-114">If you are using a named instance, specify the named instance to connect to the report server in the format MSSQL$InstanceName.</span></span>  
  
 <span data-ttu-id="19e8d-115">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="19e8d-115">**Authentication**</span></span>  
 <span data-ttu-id="19e8d-116">La autenticación del servidor de informes se realiza a través de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="19e8d-116">Authentication to a report server is made through Internet Information Services (IIS).</span></span> <span data-ttu-id="19e8d-117">Seleccione uno de los siguientes modos de autenticación al conectarse a Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="19e8d-117">Select from one of the following authentication modes when connecting to Reporting Services:</span></span>  
  
 <span data-ttu-id="19e8d-118">**Modo de autenticación de Windows (autenticación de Windows)**</span><span class="sxs-lookup"><span data-stu-id="19e8d-118">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="19e8d-119">Se conecta a una instancia de servidor de informes usando sus credenciales de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="19e8d-119">Connect to the report server instance using your [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows credentials.</span></span>  
  
 <span data-ttu-id="19e8d-120">**Autenticación básica**</span><span class="sxs-lookup"><span data-stu-id="19e8d-120">**Basic Authentication**</span></span>  
 <span data-ttu-id="19e8d-121">Conéctese mediante la **Autenticación básica** si la instalación de Reporting Services está configurada para usar la Autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="19e8d-121">Connect using **Basic Authentication** if your Reporting Services installation is configured to use Basic Authentication.</span></span>  
  
 <span data-ttu-id="19e8d-122">**Autenticación de formularios**</span><span class="sxs-lookup"><span data-stu-id="19e8d-122">**Forms Authentication**</span></span>  
 <span data-ttu-id="19e8d-123">Conéctese mediante la **Autenticación de formularios** si la instalación de Reporting Services está configurada para usar una extensión de autenticación personalizada.</span><span class="sxs-lookup"><span data-stu-id="19e8d-123">Connect using **Forms Authentication** if your Reporting Services installation is configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="19e8d-124">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="19e8d-124">**User Name**</span></span>  
 <span data-ttu-id="19e8d-125">Escriba el nombre de inicio de sesión que se va a usar en la conexión.</span><span class="sxs-lookup"><span data-stu-id="19e8d-125">Enter the login name to use for the connection.</span></span> <span data-ttu-id="19e8d-126">Esta opción solo se encuentra disponible si ha seleccionado **Autenticación básica** o **Autenticación de formularios**.</span><span class="sxs-lookup"><span data-stu-id="19e8d-126">This option is only available if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="19e8d-127">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="19e8d-127">**Password**</span></span>  
 <span data-ttu-id="19e8d-128">Escriba la contraseña del nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="19e8d-128">Enter the password for the user name.</span></span> <span data-ttu-id="19e8d-129">Esta opción solo se puede editar si ha seleccionado **Autenticación básica** o **Autenticación de formularios**.</span><span class="sxs-lookup"><span data-stu-id="19e8d-129">This option is only editable if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="19e8d-130">**Recordar contraseña**</span><span class="sxs-lookup"><span data-stu-id="19e8d-130">**Remember password**</span></span>  
 <span data-ttu-id="19e8d-131">Guarda la contraseña que ha escrito.</span><span class="sxs-lookup"><span data-stu-id="19e8d-131">Store the password you have entered.</span></span> <span data-ttu-id="19e8d-132">Esta opción solo se encuentra disponible si ha seleccionado **Autenticación básica** o **Autenticación de formularios**.</span><span class="sxs-lookup"><span data-stu-id="19e8d-132">This option is only available if you have clicked **Basic** or **Forms Authentication**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19e8d-133"> Si ha guardado la contraseña y ya no quiere conservarla, desactive esta casilla y luego haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="19e8d-133">If you have stored the password and want to stop storing it, clear this check box and then click **Save**.</span></span>  
  
 <span data-ttu-id="19e8d-134">**Nombre del servidor registrado**</span><span class="sxs-lookup"><span data-stu-id="19e8d-134">**Registered server name**</span></span>  
 <span data-ttu-id="19e8d-135">El nombre que desea que aparezca en Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="19e8d-135">The name you want to appear in Registered Servers.</span></span> <span data-ttu-id="19e8d-136">Este nombre no tiene que coincidir con el cuadro **Nombre del servidor** .</span><span class="sxs-lookup"><span data-stu-id="19e8d-136">This name does not have to match the name in the **Server name** box.</span></span>  
  
 <span data-ttu-id="19e8d-137">**Descripción del servidor registrado**</span><span class="sxs-lookup"><span data-stu-id="19e8d-137">**Registered server description**</span></span>  
 <span data-ttu-id="19e8d-138">Escriba una descripción opcional del servidor.</span><span class="sxs-lookup"><span data-stu-id="19e8d-138">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="19e8d-139">**Test**</span><span class="sxs-lookup"><span data-stu-id="19e8d-139">**Test**</span></span>  
 <span data-ttu-id="19e8d-140">Haga clic para probar la conexión al servidor seleccionado en **Nombre del servidor**.</span><span class="sxs-lookup"><span data-stu-id="19e8d-140">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="19e8d-141">**Guardar**</span><span class="sxs-lookup"><span data-stu-id="19e8d-141">**Save**</span></span>  
 <span data-ttu-id="19e8d-142">Haga clic aquí para guardar la configuración del servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="19e8d-142">Click to save the registered server settings.</span></span>  
  
  
