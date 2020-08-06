---
title: MSSQLSERVER_21879 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21879 (Database Engine error)
ms.assetid: fcfab735-05ca-423a-89f1-fdee7e2ed8c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 08c5d4f45faf94d555ed7acedd90cc55ec4791ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747010"
---
# <a name="mssqlserver_21879"></a><span data-ttu-id="1ce22-102">MSSQLSERVER_21879</span><span class="sxs-lookup"><span data-stu-id="1ce22-102">MSSQLSERVER_21879</span></span>
    
## <a name="details"></a><span data-ttu-id="1ce22-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1ce22-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ce22-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="1ce22-104">Product Name</span></span>|<span data-ttu-id="1ce22-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ce22-105">SQL Server</span></span>|  
|<span data-ttu-id="1ce22-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1ce22-106">Event ID</span></span>|<span data-ttu-id="1ce22-107">21879</span><span class="sxs-lookup"><span data-stu-id="1ce22-107">21879</span></span>|  
|<span data-ttu-id="1ce22-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="1ce22-108">Event Source</span></span>|<span data-ttu-id="1ce22-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1ce22-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1ce22-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1ce22-110">Component</span></span>|<span data-ttu-id="1ce22-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1ce22-111">SQLEngine</span></span>|  
|<span data-ttu-id="1ce22-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1ce22-112">Symbolic Name</span></span>|<span data-ttu-id="1ce22-113">SQLErrorNum21879</span><span class="sxs-lookup"><span data-stu-id="1ce22-113">SQLErrorNum21879</span></span>|  
|<span data-ttu-id="1ce22-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1ce22-114">Message Text</span></span>|<span data-ttu-id="1ce22-115">No se puede consultar al servidor redireccionado "%s" para el publicador original "%s" y la base de datos del publicador "%s" para determinar el nombre del servidor remoto; error %d, mensaje de error "%s".</span><span class="sxs-lookup"><span data-stu-id="1ce22-115">Unable to query the redirected server '%s' for original publisher '%s' and publisher database '%s' to determine the name of the remote server; Error %d, Error message '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1ce22-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1ce22-116">Explanation</span></span>  
 <span data-ttu-id="1ce22-117">`sp_validate_redirected_publisher` usa un servidor vinculado temporal que crea para conectarse al publicador redirigido a fin de detectar el nombre del servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="1ce22-117">`sp_validate_redirected_publisher` uses a temporary linked server that it creates to connect to the redirected publisher in order to discover the name of the remote server.</span></span> <span data-ttu-id="1ce22-118">Se devuelve el error 21879 si se produce un error en la consulta de servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="1ce22-118">Error 21879 is returned when the linked server query fails.</span></span> <span data-ttu-id="1ce22-119">La llamada para solicitar el nombre del servidor remoto normalmente es el primer uso del servidor vinculado temporal, por lo que si hay problemas de conectividad es probable que aparezcan primero con esta llamada.</span><span class="sxs-lookup"><span data-stu-id="1ce22-119">The call to request the remote server name is typically the first use of the temporary linked server, so if there are connectivity problems they are likely to appear first with this call.</span></span> <span data-ttu-id="1ce22-120">Esta llamada remota simplemente ejecuta `@@servername` de selección en el servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="1ce22-120">This remote call simply executes select `@@servername` at the remote server.</span></span>  
  
 <span data-ttu-id="1ce22-121">El servidor vinculado que se usa para consultar el publicador redirigido usa el modo de seguridad, el inicio de sesión y la contraseña suministrados cuando `sp_adddistpublisher` se llamó para el publicador original.</span><span class="sxs-lookup"><span data-stu-id="1ce22-121">The linked server used to query the redirected publisher uses the security mode, login, and password supplied when `sp_adddistpublisher` was called for the original publisher.</span></span>  
  
-   <span data-ttu-id="1ce22-122">Si se usó la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (modo 0 de seguridad), se usan el inicio de sesión y la contraseña especificados para conectarse al servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="1ce22-122">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication was used (security mode 0) then the login and password specified are used to connect to the remote server.</span></span>  
  
-   <span data-ttu-id="1ce22-123">Si se usó la autenticación de Windows (modo de seguridad 1), se usa una conexión de confianza para la conexión.</span><span class="sxs-lookup"><span data-stu-id="1ce22-123">If Windows authentication was used (security mode 1) a trusted connection is used for the connection.</span></span>  
  
    -   <span data-ttu-id="1ce22-124">Si un usuario llama a `sp_validate_redirected_publisher` explícitamente, el inicio de sesión de Windows en el que se ejecuta el usuario se usa para la conexión.</span><span class="sxs-lookup"><span data-stu-id="1ce22-124">If `sp_validate_redirected_publisher` is called explicitly by a user, the Windows login that the user is running under is used for the connection.</span></span>  
  
    -   <span data-ttu-id="1ce22-125">Si un agente de replicación de `sp_validate_redirected_` llama al publicador de `sp_get_redirected_publisher`se usa el inicio de sesión de Windows asociado al agente.</span><span class="sxs-lookup"><span data-stu-id="1ce22-125">If `sp_validate_redirected_`publisher is called by a replication agent from `sp_get_redirected_publisher`, the Windows login associated with the agent is used.</span></span>  
  
 <span data-ttu-id="1ce22-126">El error 21879 puede indicar que `sp_validate_redirected_publisher` se llamó con un inicio de sesión desconocido en el publicador de destino redirigido.</span><span class="sxs-lookup"><span data-stu-id="1ce22-126">Error 21879 can indicate that `sp_validate_redirected_publisher` was called using a login that is not known at the redirected target publisher.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ce22-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1ce22-127">User Action</span></span>  
 <span data-ttu-id="1ce22-128">Compruebe que el inicio de sesión de autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o el inicio de sesión de autenticación de Windows es válido en todas las réplicas de grupo de disponibilidad y que tiene suficiente autenticación para obtener acceso a las tablas de metadatos de suscripciones (syssubscriptions y sysmergesubscriptions) en la base de datos del publicador.</span><span class="sxs-lookup"><span data-stu-id="1ce22-128">Make certain that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication login or the Windows authentication login is valid at all of the availability group replicas and has sufficient authorization to access the subscription metadata tables (syssubscriptions and sysmergesubscriptions) in the publisher database.</span></span>  
  
 <span data-ttu-id="1ce22-129">Existen consideraciones especiales cuando se devuelve el error 21879 desde una llamada a `sp_get_redirected_publisher` que inició un agente de replicación en un nodo distinto del distribuidor; como un agente de mezcla que se ejecute en un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="1ce22-129">There are special considerations when error 21879 is returned from a call to `sp_get_redirected_publisher` that is initiated by a replication agent running on a node other that the distributor; such as a merge agent running at a subscriber.</span></span> <span data-ttu-id="1ce22-130">Si se usa la autenticación de Windows para la conexión al publicador redirigido, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se debe configurar para la autenticación Kerberos a fin de que la conexión se establezca correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ce22-130">If Windows authentication is used for the connection to the redirected publisher, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be configured for Kerberos authentication for the connection to be successfully established.</span></span> <span data-ttu-id="1ce22-131">Cuando se usa la autenticación de Windows y no se configura [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación Kerberos, un agente de mezcla que se ejecute en el suscriptor recibe el error 18456 que indica que se produjo un error en el inicio de sesión de "NT AUTHORITY\ANONYMOUS LOGON".</span><span class="sxs-lookup"><span data-stu-id="1ce22-131">When Windows authentication is used and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not configured for Kerberos authentication, error 18456 indicating that the 'NT AUTHORITY\ANONYMOUS LOGON' login failed, is received by a merge agent running at a subscriber.</span></span> <span data-ttu-id="1ce22-132">Hay tres formas posibles de solucionar este problema:</span><span class="sxs-lookup"><span data-stu-id="1ce22-132">There are three possible ways to address this issue:</span></span>  
  
-   <span data-ttu-id="1ce22-133">Configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1ce22-133">Configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for Kerberos authentication.</span></span> <span data-ttu-id="1ce22-134">Vea **Utilizar la autenticación Kerberos con SQL Server** en Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ce22-134">See **Kerberos Authentication and SQL Server** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
-   <span data-ttu-id="1ce22-135">Use `sp_changedistpublisher` para cambiar el modo de seguridad asociado con el publicador original en MSdistpublishers, así como para especificar un inicio de sesión y una contraseña que se usarán para la conexión.</span><span class="sxs-lookup"><span data-stu-id="1ce22-135">Use `sp_changedistpublisher` to change the security mode associated with the original publisher in MSdistpublishers, as well as to specify a login and password to use for the connection.</span></span>  
  
-   <span data-ttu-id="1ce22-136">Especifique el parámetro de línea de comandos *BypassPublisherValidation* en la línea de comandos del agente de mezcla para omitir la validación cuando `sp_get_redirected_publisher` se llama a en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="1ce22-136">Specify the command line parameter *BypassPublisherValidation* on the merge agent command line to bypass validation when `sp_get_redirected_publisher` is called at the distributor.</span></span>  
  
  
