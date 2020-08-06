---
title: MSSQLSERVER_916 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 916 (Database Engine error)
ms.assetid: 73eb6581-99fe-49a5-9b42-e239d7ffe27f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ee67c1e2f67c3c7903c67082ec3793d9d9820061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672034"
---
# <a name="mssqlserver_916"></a><span data-ttu-id="62a82-102">MSSQLSERVER_916</span><span class="sxs-lookup"><span data-stu-id="62a82-102">MSSQLSERVER_916</span></span>
    
## <a name="details"></a><span data-ttu-id="62a82-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="62a82-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="62a82-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="62a82-104">Product Name</span></span>|<span data-ttu-id="62a82-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="62a82-105">SQL Server</span></span>|  
|<span data-ttu-id="62a82-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="62a82-106">Event ID</span></span>|<span data-ttu-id="62a82-107">916</span><span class="sxs-lookup"><span data-stu-id="62a82-107">916</span></span>|  
|<span data-ttu-id="62a82-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="62a82-108">Event Source</span></span>|<span data-ttu-id="62a82-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="62a82-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="62a82-110">Componente</span><span class="sxs-lookup"><span data-stu-id="62a82-110">Component</span></span>|<span data-ttu-id="62a82-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="62a82-111">SQLEngine</span></span>|  
|<span data-ttu-id="62a82-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="62a82-112">Symbolic Name</span></span>|<span data-ttu-id="62a82-113">NOTUSER</span><span class="sxs-lookup"><span data-stu-id="62a82-113">NOTUSER</span></span>|  
|<span data-ttu-id="62a82-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="62a82-114">Message Text</span></span>|<span data-ttu-id="62a82-115">La entidad de seguridad de servidor "%.\*ls" no puede tener acceso a la base de datos "%.\*ls" en el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="62a82-115">The server principal "%.\*ls" is not able to access the database "%.\*ls" under the current security context.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="62a82-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="62a82-116">Explanation</span></span>  
 <span data-ttu-id="62a82-117">El inicio de sesión no tiene los permisos suficientes para conectar a la base de datos denominada.</span><span class="sxs-lookup"><span data-stu-id="62a82-117">The login does not have sufficient permissions to connect to the named database.</span></span> <span data-ttu-id="62a82-118">Los inicios de sesión que se puedan conectar a esta instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], pero que no tengan los permisos correspondientes en una base de datos, reciben los permisos del usuario guest.</span><span class="sxs-lookup"><span data-stu-id="62a82-118">Logins that can connect to this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but that do not have specific permissions in a database receive the permissions of the guest user.</span></span> <span data-ttu-id="62a82-119">Se trata de una medida de seguridad para evitar que los usuarios de una base de datos se conecten a otras en las que no tienen privilegios.</span><span class="sxs-lookup"><span data-stu-id="62a82-119">This is a security measure to prevent users in one database from connecting to other databases where they do not have privileges.</span></span> <span data-ttu-id="62a82-120">Este mensaje de error se puede producir cuando el usuario guest no dispone del permiso CONNECT para la base de datos denominada y no se ha establecido la propiedad TRUSTWORTHY.</span><span class="sxs-lookup"><span data-stu-id="62a82-120">This error message can occur when the guest user does not have CONNECT permission to the named database and the trustworthy property is not set.</span></span> <span data-ttu-id="62a82-121">Este mensaje de error se puede producir cuando el usuario guest no dispone del permiso CONNECT para la base de datos denominada.</span><span class="sxs-lookup"><span data-stu-id="62a82-121">This error message can occur when the guest user does not have CONNECT permission to the named database.</span></span>  
  
 <span data-ttu-id="62a82-122">Cuando se deniega o revoca el permiso CONNECT para la base de datos msdb, es posible que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] reciba este error si el Explorador de objetos intenta mostrar el estado de la administración basada en directivas de cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="62a82-122">When CONNECT permission to the msdb database is denied or revoked, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] can receive this error when Object Explorer tries to show the Policy Based Management status of each database.</span></span> <span data-ttu-id="62a82-123">El Explorador de objetos se sirve de los permisos del inicio de sesión actual para realizar consultas sobre esta información a la base de datos msdb, lo cual produce el error.</span><span class="sxs-lookup"><span data-stu-id="62a82-123">Object Explorer uses the permissions of the current login to query the msdb database for this information, which causes the error.</span></span> <span data-ttu-id="62a82-124">También se produce el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="62a82-124">The following error message also occurs:</span></span>  
  
 <span data-ttu-id="62a82-125">Error al recuperar datos para esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="62a82-125">Failed to retrieve data for this request.</span></span> <span data-ttu-id="62a82-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span><span class="sxs-lookup"><span data-stu-id="62a82-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="62a82-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="62a82-127">User Action</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="62a82-128">Antes de sortear esta medida de seguridad, asegúrese de que comprende perfectamente qué significa que los usuarios se autentiquen en varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="62a82-128">Before circumventing this security measure be sure to have a clear understanding of users are authenticated in various databases.</span></span> <span data-ttu-id="62a82-129">Los siguientes métodos pueden permitir a los usuarios con permisos en una base de datos conectarse a otras, lo cual podría exponer los datos a usuarios malintencionados.</span><span class="sxs-lookup"><span data-stu-id="62a82-129">The following methods may allow users that have permissions in one database to connect to other databases which could expose data to a malicious user.</span></span> <span data-ttu-id="62a82-130">Cuando se habilitan las bases de datos independientes, los siguientes pasos permiten a los propietarios de una base de datos conceder acceso a la otra base de datos de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62a82-130">When contained databases are enabled, the following steps can allow database owners in one database to grant access to other database on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="62a82-131">Puede conectarse a la base de datos mediante uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="62a82-131">You can connect to the database in one of the following ways:</span></span>  
  
-   <span data-ttu-id="62a82-132">Otorgue el acceso de inicio de sesión específico a la base de datos denominada.</span><span class="sxs-lookup"><span data-stu-id="62a82-132">Grant the specific login access to the named database.</span></span> <span data-ttu-id="62a82-133">En el siguiente ejemplo se concede el inicio de sesión para el acceso de `Adventure-Works\Larry` a la base de datos `msdb`.</span><span class="sxs-lookup"><span data-stu-id="62a82-133">The following example grants the login `Adventure-Works\Larry` access to the `msdb` database.</span></span>  
  
     <span data-ttu-id="62a82-134">USE msdb ;</span><span class="sxs-lookup"><span data-stu-id="62a82-134">USE msdb ;</span></span>  
  
     <span data-ttu-id="62a82-135">GO</span><span class="sxs-lookup"><span data-stu-id="62a82-135">GO</span></span>  
  
     <span data-ttu-id="62a82-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span><span class="sxs-lookup"><span data-stu-id="62a82-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span></span>  
  
-   <span data-ttu-id="62a82-137">Otorgue el permiso CONNECT a la base de datos denominada en el mensaje de error del usuario guest.</span><span class="sxs-lookup"><span data-stu-id="62a82-137">Grant the CONNECT permission to the database named in the error message for the guest user.</span></span> <span data-ttu-id="62a82-138">En el siguiente ejemplo se concede el permiso `CONNECT` para la base de datos `msdb` al usuario `guest`.</span><span class="sxs-lookup"><span data-stu-id="62a82-138">The following example grants the `CONNECT` permission to the `msdb` database for the user `guest`.</span></span>  
  
     <span data-ttu-id="62a82-139">USE msdb ;</span><span class="sxs-lookup"><span data-stu-id="62a82-139">USE msdb ;</span></span>  
  
     <span data-ttu-id="62a82-140">GO</span><span class="sxs-lookup"><span data-stu-id="62a82-140">GO</span></span>  
  
     <span data-ttu-id="62a82-141">GRANT CONNECT TO guest ;</span><span class="sxs-lookup"><span data-stu-id="62a82-141">GRANT CONNECT TO guest ;</span></span>  
  
-   <span data-ttu-id="62a82-142">Habilite la propiedad TRUSTWORTHY en la base de datos que ha autenticado al usuario.</span><span class="sxs-lookup"><span data-stu-id="62a82-142">Enable the TRUSTWORTHY property on the database that has authenticated the user.</span></span>  
  
     `ALTER DATABASE AdventureWorks SET TRUSTWORTHY ON;`  
  
  
