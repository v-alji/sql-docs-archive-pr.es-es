---
title: Acceso de red a un extremo de creación de reflejo de la base de datos
description: Obtenga información acerca de cómo permitir el acceso de red authenticatino de Windows a un extremo de creación de reflejo de la base de datos para SQL Server.
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 28c8fec5-5feb-4c84-8d72-f2bd1ae3b40d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d1d8786d128ef2cc99fe571e33f89c4c4e7699c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675506"
---
# <a name="allow-network-access-to-a-database-mirroring-endpoint-using-windows-authentication-sql-server"></a><span data-ttu-id="103dc-103">Permitir el acceso de red a un extremo de creación de reflejo de la base de datos mediante la autenticación de Windows (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="103dc-103">Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication (SQL Server)</span></span>
  <span data-ttu-id="103dc-104">Si utiliza la autenticación de Windows para conectar los extremos de creación de reflejo de la base de datos de dos instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , se requiere la configuración manual de las cuentas de inicio de sesión en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="103dc-104">Using Windows Authentication for connecting the database mirroring endpoints of two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requires manual configuration of login accounts under the following conditions:</span></span>  
  
-   <span data-ttu-id="103dc-105">Si las instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se ejecutan como servicios bajo diferentes cuentas de dominio (en el mismo dominio o en dominios de confianza), el inicio de sesión de cada cuenta debe crearse en **master** en cada una de las instancias de los servidores remotos y se deben conceder permisos CONNECT a ese inicio de sesión en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="103dc-105">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as services under different domain accounts (in the same or trusted domains), the login of each account must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span>  
  
-   <span data-ttu-id="103dc-106">Si las instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se ejecutan con la cuenta de servicio de red, el inicio de sesión de cada cuenta de equipo host (*NombreDeDominio***\\***NombreDeEquipo$* ) se debe crear en **master** en cada una de las instancias de los servidores remotos, y a ese inicio de sesión se le deben conceder permisos CONNECT en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="103dc-106">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as the Network Service account, the login of the each host computer account (*DomainName***\\***ComputerName$*) must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span> <span data-ttu-id="103dc-107">Esto se debe a que una instancia de servidor que se ejecuta en la cuenta Servicio de red se autentica mediante la cuenta de dominio del equipo host.</span><span class="sxs-lookup"><span data-stu-id="103dc-107">This is because a server instance running under the Network Service account authenticates using the domain account of the host computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="103dc-108">Asegúrese de que exista un extremo para cada instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="103dc-108">Ensure that an endpoint exists for each of the server instances.</span></span> <span data-ttu-id="103dc-109">Para obtener más información, vea [Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="103dc-109">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
### <a name="to-configure-logins-for-windows-authentication"></a><span data-ttu-id="103dc-110">Para configurar inicios de sesión para la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="103dc-110">To configure logins for Windows Authentication</span></span>  
  
1.  <span data-ttu-id="103dc-111">Para la cuenta de usuario de cada instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], cree un inicio de sesión en las demás instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="103dc-111">For the user account of each instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], create a login on the other instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="103dc-112">Utilice una instrucción [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) con la cláusula FROM WINDOWS.</span><span class="sxs-lookup"><span data-stu-id="103dc-112">Use a [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) statement with the FROM WINDOWS clause.</span></span>  
  
     <span data-ttu-id="103dc-113">Para obtener más información, vea [Crear un inicio de sesión](../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="103dc-113">For more information, see [Create a Login](../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
2.  <span data-ttu-id="103dc-114">Asimismo, para asegurarse de que el usuario de inicio de sesión tiene acceso al extremo, utilice la instrucción [GRANT](/sql/t-sql/statements/grant-transact-sql) para conceder permisos de conexión en el extremo para el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="103dc-114">Also, to ensure that the login user has access to the endpoint, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement to grant connect permissions on the endpoint to the login.</span></span> <span data-ttu-id="103dc-115">Tenga en cuenta que si el usuario es un administrador, no es necesario que conceda permisos de conexión al extremo.</span><span class="sxs-lookup"><span data-stu-id="103dc-115">Note that granting connect permissions to the endpoint is unnecessary if the user is an Administrator.</span></span>  
  
     <span data-ttu-id="103dc-116">Para más información, consulte [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="103dc-116">For more information, see [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="103dc-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="103dc-117">Example</span></span>  
 <span data-ttu-id="103dc-118">En el ejemplo siguiente de [!INCLUDE[tsql](../includes/tsql-md.md)] se crea un inicio de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para una cuenta de usuario denominada `Otheruser` que pertenece a un dominio denominado `Adomain`.</span><span class="sxs-lookup"><span data-stu-id="103dc-118">The following [!INCLUDE[tsql](../includes/tsql-md.md)] example creates a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login for a user account named `Otheruser` that belongs to a domain called `Adomain`.</span></span> <span data-ttu-id="103dc-119">En el ejemplo se concede a este usuario permiso para conectarse a un extremo para la creación de reflejo de base de datos ya existente llamado `Mirroring_Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="103dc-119">The example then grants this user connect permissions to a pre-existing database mirroring endpoint named `Mirroring_Endpoint`.</span></span>  
  
```  
USE master;  
GO  
CREATE LOGIN [Adomain\Otheruser] FROM WINDOWS;  
GO  
GRANT CONNECT on ENDPOINT::Mirroring_Endpoint TO [Adomain\Otheruser];  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="103dc-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="103dc-120">See Also</span></span>  
 <span data-ttu-id="103dc-121">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="103dc-121">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="103dc-122">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="103dc-122">[Database Mirroring &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="103dc-123">[Seguridad de transporte para la creación de reflejo de la base de datos y Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="103dc-123">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span></span>  
 [<span data-ttu-id="103dc-124">El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="103dc-124">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
  
  
