---
title: Propiedades del servidor (página Seguridad) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.security.f1
ms.assetid: b8a131c7-e7bd-4203-bf26-234f1ebfe622
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f45c0a04a0d7cc627901d8de24175f1d63a99fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677877"
---
# <a name="server-properties-security-page"></a><span data-ttu-id="b5a39-102">Propiedades del servidor (página Seguridad)</span><span class="sxs-lookup"><span data-stu-id="b5a39-102">Server Properties (Security Page)</span></span>
  <span data-ttu-id="b5a39-103">Utilice esta página para ver o modificar las opciones de seguridad del servidor.</span><span class="sxs-lookup"><span data-stu-id="b5a39-103">Use this page to view or modify your server security options.</span></span>  
  
## <a name="server-authentication"></a><span data-ttu-id="b5a39-104">Autenticación de servidor</span><span class="sxs-lookup"><span data-stu-id="b5a39-104">Server Authentication</span></span>  
 <span data-ttu-id="b5a39-105">**Modo de autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="b5a39-105">**Windows Authentication mode**</span></span>  
 <span data-ttu-id="b5a39-106">Utiliza la autenticación de Windows para validar las conexiones intentadas.</span><span class="sxs-lookup"><span data-stu-id="b5a39-106">Uses Windows Authentication to validate attempted connections.</span></span> <span data-ttu-id="b5a39-107">Si la contraseña de **sa** está en blanco cuando se cambia el modo de seguridad, se solicita al usuario que escriba una contraseña de **sa** .</span><span class="sxs-lookup"><span data-stu-id="b5a39-107">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b5a39-108">La Autenticación de Windows es mucho más segura que la Autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b5a39-108">Windows Authentication is much more secure than SQL Server Authentication.</span></span> <span data-ttu-id="b5a39-109">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="b5a39-109">When possible, you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="b5a39-110">**Modo de autenticación de Windows y SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b5a39-110">**SQL Server and Windows Authentication mode**</span></span>  
 <span data-ttu-id="b5a39-111">Utiliza autenticación de modo mixto para comprobar las conexiones intentadas, a efectos de compatibilidad con versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5a39-111">Uses mixed mode authentication to verify attempted connections, for backward compatibility with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b5a39-112">Si la contraseña de **sa** está en blanco cuando se cambia el modo de seguridad, se solicita al usuario que escriba una contraseña de **sa** .</span><span class="sxs-lookup"><span data-stu-id="b5a39-112">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5a39-113">El cambio de la configuración de seguridad requiere reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="b5a39-113">Changing the security configuration requires a restart of the service.</span></span> <span data-ttu-id="b5a39-114">Cuando se cambia la Autenticación de servidor al modo de autenticación de Windows y SQL Server, la cuenta SA no se habilita automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b5a39-114">When changing the Server Authentication to SQL Server and Windows Authentication mode the SA account is not automatically enabled.</span></span> <span data-ttu-id="b5a39-115">Para utilizar la cuenta SA, ejecute [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) con la opción ENABLE.</span><span class="sxs-lookup"><span data-stu-id="b5a39-115">To use the SA account, execute [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) with the ENABLE option.</span></span>  
  
## <a name="login-auditing"></a><span data-ttu-id="b5a39-116">Auditoría de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="b5a39-116">Login Auditing</span></span>  
 <span data-ttu-id="b5a39-117">**None**</span><span class="sxs-lookup"><span data-stu-id="b5a39-117">**None**</span></span>  
 <span data-ttu-id="b5a39-118">Desactiva la auditoría de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b5a39-118">Turns off login auditing.</span></span>  
  
 <span data-ttu-id="b5a39-119">**Solo inicios de sesión erróneos**</span><span class="sxs-lookup"><span data-stu-id="b5a39-119">**Failed logins only**</span></span>  
 <span data-ttu-id="b5a39-120">Solo realiza la auditoría de inicios de sesión incorrectos.</span><span class="sxs-lookup"><span data-stu-id="b5a39-120">Audits unsuccessful logins only.</span></span>  
  
 <span data-ttu-id="b5a39-121">**Solo inicios de sesión correctos**</span><span class="sxs-lookup"><span data-stu-id="b5a39-121">**Successful logins only**</span></span>  
 <span data-ttu-id="b5a39-122">Solo realiza la auditoría de inicios de sesión correctos.</span><span class="sxs-lookup"><span data-stu-id="b5a39-122">Audits successful logins only.</span></span>  
  
 <span data-ttu-id="b5a39-123">**Inicios de sesión correctos y erróneos**</span><span class="sxs-lookup"><span data-stu-id="b5a39-123">**Both failed and successful logins**</span></span>  
 <span data-ttu-id="b5a39-124">Realiza la auditoría de todos los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="b5a39-124">Audits all login attempts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5a39-125">El cambio del nivel de auditoría requiere reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="b5a39-125">Changing the audit level requires restarting the service.</span></span>  
  
## <a name="server-proxy-account"></a><span data-ttu-id="b5a39-126">Cuenta de proxy del servidor</span><span class="sxs-lookup"><span data-stu-id="b5a39-126">Server Proxy Account</span></span>  
 <span data-ttu-id="b5a39-127">**Habilitar cuenta de proxy del servidor**</span><span class="sxs-lookup"><span data-stu-id="b5a39-127">**Enable server proxy account**</span></span>  
 <span data-ttu-id="b5a39-128">Permite que **xp_cmdshell**use una cuenta.</span><span class="sxs-lookup"><span data-stu-id="b5a39-128">Enables an account for use by **xp_cmdshell**.</span></span> <span data-ttu-id="b5a39-129">Las cuentas de proxy permiten la suplantación de inicios de sesión, roles de servidor y roles de base de datos cuando se ejecuta un comando del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b5a39-129">Proxy accounts allow for the impersonation of logins, server roles, and database roles when an operating system command is being executed.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b5a39-130">El inicio de sesión que utiliza la cuenta de proxy del servidor debe tener asignados solo los privilegios mínimos necesarios para realizar el trabajo propuesto.</span><span class="sxs-lookup"><span data-stu-id="b5a39-130">The login used by the server proxy account should have the least privileges required to perform the intended work.</span></span> <span data-ttu-id="b5a39-131">Un usuario malicioso puede utilizar los privilegios excesivos en la cuenta de proxy para comprometer la seguridad del sistema.</span><span class="sxs-lookup"><span data-stu-id="b5a39-131">Excessive privileges for the proxy account could be used by a malicious user to compromise your system security.</span></span>  
  
 <span data-ttu-id="b5a39-132">**Cuenta de proxy**</span><span class="sxs-lookup"><span data-stu-id="b5a39-132">**Proxy account**</span></span>  
 <span data-ttu-id="b5a39-133">Especifique la cuenta de proxy que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b5a39-133">Specify the proxy account used.</span></span>  
  
 <span data-ttu-id="b5a39-134">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="b5a39-134">**Password**</span></span>  
 <span data-ttu-id="b5a39-135">Especifique la contraseña de la cuenta de proxy.</span><span class="sxs-lookup"><span data-stu-id="b5a39-135">Specify the password for the proxy account.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b5a39-136">Opciones</span><span class="sxs-lookup"><span data-stu-id="b5a39-136">Options</span></span>  
 <span data-ttu-id="b5a39-137">**Habilitar C2 audit tracing**</span><span class="sxs-lookup"><span data-stu-id="b5a39-137">**Enable C2 audit tracing**</span></span>  
 <span data-ttu-id="b5a39-138">Audita todos los intentos de obtener acceso a instrucciones y objetos, y registra dichos intentos en un archivo del directorio \MSSQL\Data para las instancias predeterminadas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o del directorio \MSSQL$*nombreDeInstancia*\Data para las instancias con nombre de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5a39-138">Audits all attempts to access statements and objects and records them to a file in the \MSSQL\Data directory for default instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or the \MSSQL$*instancename*\Data directory for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b5a39-139">Para obtener más información, vea [c2 audit mode (opción de configuración del servidor)](c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b5a39-139">For more information, see [c2 audit mode Server Configuration Option](c2-audit-mode-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="b5a39-140">**Encadenamiento de propiedad entre bases de datos**</span><span class="sxs-lookup"><span data-stu-id="b5a39-140">**Cross database ownership chaining**</span></span>  
 <span data-ttu-id="b5a39-141">Seleccione esta opción para permitir que la base de datos pueda ser el origen o destino de una cadena de propiedad entre bases de datos.</span><span class="sxs-lookup"><span data-stu-id="b5a39-141">Select to allow the database to be the source or target of a cross-database ownership chain.</span></span> <span data-ttu-id="b5a39-142">Para obtener más información, vea [cross db ownership chaining (opción de configuración del servidor)](cross-db-ownership-chaining-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b5a39-142">For more information, see [cross db ownership chaining Server Configuration Option](cross-db-ownership-chaining-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a39-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5a39-143">See Also</span></span>  
 [<span data-ttu-id="b5a39-144">Opciones de configuración de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b5a39-144">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
