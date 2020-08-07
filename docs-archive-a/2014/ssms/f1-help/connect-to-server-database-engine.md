---
title: Conectar al servidor (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectoserverunknownservertype.f1
- sql12.swb.connection.login.sqlserver.f1
- sql12.swb.connection.login.sqlce.f1
- sql12.swb.manageSS2k.f1
- sql12.swb.connecttoce.f1
- sql12.swb.connecttoce.connectionproperties.f1
ms.assetid: ee9017b4-8a19-4360-9003-9e6484082d41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca227d1a3bbc13160962ba2fcad23ff011c950f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746698"
---
# <a name="connect-to-server-database-engine"></a><span data-ttu-id="19142-102">Conectar al servidor (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="19142-102">Connect to Server (Database Engine)</span></span>
  <span data-ttu-id="19142-103">Use este cuadro de diálogo para ver o especificar opciones cuando se conecte a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19142-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="19142-104">En la mayoría de los casos, para conectarse, puede escribir el nombre del servidor de base de datos en el cuadro **Nombre del servidor** y hacer clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="19142-104">In most cases, you can connect by entering the computer name of the database server in the **Server name** box and then clicking **Connect**.</span></span> <span data-ttu-id="19142-105">Si se está conectando a [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], use el nombre del equipo seguido de **\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="19142-105">If you are connecting to [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], use the computer name followed by **\sqlexpress**.</span></span>  
  
 <span data-ttu-id="19142-106">Hay diversos factores que pueden afectar a la capacidad de conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19142-106">Many factors can affect your ability to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="19142-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="19142-107">Options</span></span>  
 <span data-ttu-id="19142-108">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="19142-108">**Server type**</span></span>  
 <span data-ttu-id="19142-109">Al registrar un servidor desde el Explorador de objetos, seleccione el tipo de servidor al que se conectará: [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19142-109">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="19142-110">El resto del cuadro de diálogo muestra simplemente las opciones que se aplican al tipo de servidor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="19142-110">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="19142-111">Cuando se registra un servidor desde Servidores registrados, el cuadro **Tipo de servidor** es de solo lectura y coincide con el tipo de servidor que se muestra en el componente Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="19142-111">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="19142-112">Para registrar un tipo de servidor distinto, seleccione [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)]o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] desde la barra de herramientas Servidores registrados antes de comenzar a registrar un nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="19142-112">To register a different type of server, select [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="19142-113">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="19142-113">**Server name**</span></span>  
 <span data-ttu-id="19142-114">Seleccione la instancia de servidor a la que va a conectarse.</span><span class="sxs-lookup"><span data-stu-id="19142-114">Select the server instance to connect to.</span></span> <span data-ttu-id="19142-115">De forma predeterminada, aparecerá la instancia de servidor a la que se ha conectado por última vez.</span><span class="sxs-lookup"><span data-stu-id="19142-115">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19142-116">Para conectarse a una instancia de usuarios activos de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , use el protocolo Canalizaciones con nombre especificando el nombre de canalización, como np:\\\\.\pipe\3C3DF6B1-2262-47\tsql\query. Para más información, consulte la documentación de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="19142-116">To connect to an active user instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] connect using named pipes protocol specifying the pipe name, such as np:\\\\.\pipe\3C3DF6B1-2262-47\tsql\query For more information, see the [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="19142-117">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="19142-117">**Authentication**</span></span>  
 <span data-ttu-id="19142-118">Dispone de dos modos de autenticación al conectarse a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19142-118">Two authentication modes are available when connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="19142-119">**Modo de autenticación de Windows (autenticación de Windows)**</span><span class="sxs-lookup"><span data-stu-id="19142-119">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="19142-120">El modo de autenticación de Windows permite al usuario conectarse mediante una cuenta de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="19142-120">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="19142-121">**Autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="19142-121">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="19142-122">Cuando un usuario se conecta con un nombre y una contraseña de inicio de sesión determinados desde una conexión no confiable, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] realiza la autenticación y comprueba si se configuró una cuenta de inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y si la contraseña especificada coincide con la almacenada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="19142-122">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="19142-123">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no tiene configurada una cuenta de inicio de sesión, la autenticación no se realizará correctamente y el usuario recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="19142-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="19142-124">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="19142-124">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="19142-125">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="19142-125">**User name**</span></span>  
 <span data-ttu-id="19142-126">Escriba el nombre de usuario con el que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="19142-126">Enter the user name to connect with.</span></span> <span data-ttu-id="19142-127">Esta opción solo está disponible si ha seleccionado la autenticación de Windows para conectarse.</span><span class="sxs-lookup"><span data-stu-id="19142-127">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="19142-128">**Inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="19142-128">**Login**</span></span>  
 <span data-ttu-id="19142-129">Escriba el inicio de sesión con el que va a conectarse.</span><span class="sxs-lookup"><span data-stu-id="19142-129">Enter the login to connect with.</span></span> <span data-ttu-id="19142-130">Esta opción solo está disponible si ha seleccionado la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para conectarse.</span><span class="sxs-lookup"><span data-stu-id="19142-130">This option is only available if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="19142-131">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="19142-131">**Password**</span></span>  
 <span data-ttu-id="19142-132">Escriba la contraseña del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="19142-132">Enter the password for the login.</span></span> <span data-ttu-id="19142-133">Esta opción solo es editable si ha seleccionado la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para conectarse.</span><span class="sxs-lookup"><span data-stu-id="19142-133">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="19142-134">**Conexión**</span><span class="sxs-lookup"><span data-stu-id="19142-134">**Connect**</span></span>  
 <span data-ttu-id="19142-135">Haga clic aquí para conectarse al servidor seleccionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="19142-135">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="19142-136">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="19142-136">**Options**</span></span>  
 <span data-ttu-id="19142-137">Haga clic aquí para que se muestren las opciones adicionales de conexión al servidor, como registrar un servidor y recordar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="19142-137">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
