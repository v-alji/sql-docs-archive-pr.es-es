---
title: Directiva de contraseñas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- ALTER LOGIN statement
- passwords [SQL Server], policy enforcement
- logins [SQL Server], passwords
- CHECK_EXPIRATION option
- complex passwords [SQL Server]
- passwords [SQL Server], expiration
- manual bad password count resets
- MUST_CHANGE option
- expiration [SQL Server]
- expired password [SQL Server]
- symbols [SQL Server]
- NetValidatePasswordPolicy() API
- passwords [SQL Server]
- password policy [SQL Server]
- resetting bad password counts
- security [SQL Server], passwords
- CHECK_POLICY option
- passwords [SQL Server], symbols
- bad password counts
- passwords [SQL Server], complexity
- characters [SQL Server], password policies
ms.assetid: c0040c0a-a18f-45b9-9c40-0625685649b1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 902c46b4609a32139450843414a3c4d97b52fcf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669553"
---
# <a name="password-policy"></a><span data-ttu-id="0d2fb-102">Directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="0d2fb-102">Password Policy</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0d2fb-103">puede usar los mecanismos de directiva de contraseñas de Windows.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-103">can use Windows password policy mechanisms.</span></span> <span data-ttu-id="0d2fb-104">La directiva de contraseñas se aplica a un inicio de sesión que usa la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y a un usuario con contraseña de una base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-104">The password policy applies to a login that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication, and to a contained database user with password.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0d2fb-105">puede aplicar las mismas directivas de complejidad y expiración que se usan en Windows a las contraseñas que se usan en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d2fb-105">can apply the same complexity and expiration policies used in Windows to passwords used inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0d2fb-106">Esta funcionalidad depende de la API `NetValidatePasswordPolicy` .</span><span class="sxs-lookup"><span data-stu-id="0d2fb-106">This functionality depends on the `NetValidatePasswordPolicy` API.</span></span>  
  
## <a name="password-complexity"></a><span data-ttu-id="0d2fb-107">Complejidad de las contraseñas</span><span class="sxs-lookup"><span data-stu-id="0d2fb-107">Password Complexity</span></span>  
 <span data-ttu-id="0d2fb-108">Las directivas de complejidad de contraseñas están diseñadas para impedir ataques por fuerza bruta mediante el aumento del número de contraseñas posibles.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-108">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="0d2fb-109">Cuando se aplica la directiva de complejidad de contraseñas, se exige que las nuevas contraseñas cumplan las siguientes directrices:</span><span class="sxs-lookup"><span data-stu-id="0d2fb-109">When password complexity policy is enforced, new passwords must meet the following guidelines:</span></span>  
  
-   <span data-ttu-id="0d2fb-110">La contraseña no debe contener el nombre de la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-110">The password does not contain the account name of the user.</span></span>  
  
-   <span data-ttu-id="0d2fb-111">La contraseña debe tener una longitud de ocho caracteres como mínimo.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-111">The password is at least eight characters long.</span></span>  
  
-   <span data-ttu-id="0d2fb-112">La contraseña debe contener caracteres de tres de las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="0d2fb-112">The password contains characters from three of the following four categories:</span></span>  
  
    -   <span data-ttu-id="0d2fb-113">Letras en mayúsculas del alfabeto Latín (de la A a la Z)</span><span class="sxs-lookup"><span data-stu-id="0d2fb-113">Latin uppercase letters (A through Z)</span></span>  
  
    -   <span data-ttu-id="0d2fb-114">Letras en minúsculas del alfabeto Latín (de la "a" a la "z")</span><span class="sxs-lookup"><span data-stu-id="0d2fb-114">Latin lowercase letters (a through z)</span></span>  
  
    -   <span data-ttu-id="0d2fb-115">Dígitos en base 10 (del 0 al 9)</span><span class="sxs-lookup"><span data-stu-id="0d2fb-115">Base 10 digits (0 through 9)</span></span>  
  
    -   <span data-ttu-id="0d2fb-116">Caracteres que no sean alfanuméricos, como signo de admiración (!), signo de moneda ($), signo de almohadilla (#) o porcentaje (%).</span><span class="sxs-lookup"><span data-stu-id="0d2fb-116">Non-alphanumeric characters such as: exclamation point (!), dollar sign ($), number sign (#), or percent (%).</span></span>  
  
 <span data-ttu-id="0d2fb-117">Las contraseñas pueden tener hasta 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-117">Passwords can be up to 128 characters long.</span></span> <span data-ttu-id="0d2fb-118">Se recomienda utilizar contraseñas lo más largas y complejas posible.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-118">You should use passwords that are as long and complex as possible.</span></span>  
  
## <a name="password-expiration"></a><span data-ttu-id="0d2fb-119">Expiración de las contraseñas</span><span class="sxs-lookup"><span data-stu-id="0d2fb-119">Password Expiration</span></span>  
 <span data-ttu-id="0d2fb-120">Las directivas de expiración de contraseñas se utilizan para administrar la duración de una contraseña.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-120">Password expiration policies are used to manage the lifespan of a password.</span></span> <span data-ttu-id="0d2fb-121">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aplica la directiva de expiración de contraseñas, se recuerda a los usuarios que cambien las contraseñas antiguas, y las cuentas con contraseñas que han expirado se deshabilitan.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-121">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enforces password expiration policy, users are reminded to change old passwords, and accounts that have expired passwords are disabled.</span></span>  
  
## <a name="policy-enforcement"></a><span data-ttu-id="0d2fb-122">Aplicación de las directivas</span><span class="sxs-lookup"><span data-stu-id="0d2fb-122">Policy Enforcement</span></span>  
 <span data-ttu-id="0d2fb-123">La aplicación de la directiva de contraseñas se puede configurar independientemente para cada inicio de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-123">The enforcement of password policy can be configured separately for each SQL Server login.</span></span> <span data-ttu-id="0d2fb-124">Use [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) para configurar las opciones de la directiva de contraseñas de un inicio de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-124">Use [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy options of a SQL Server login.</span></span> <span data-ttu-id="0d2fb-125">Se aplican las siguientes reglas a la configuración de la aplicación de directivas de contraseñas:</span><span class="sxs-lookup"><span data-stu-id="0d2fb-125">The following rules apply to the configuration of password policy enforcement:</span></span>  
  
-   <span data-ttu-id="0d2fb-126">Cuando el valor de CHECK_POLICY se cambia a ON, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d2fb-126">When CHECK_POLICY is changed to ON, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="0d2fb-127">CHECK_EXPIRATION también se establece en ON, salvo que se haya establecido de forma explícita en OFF.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-127">CHECK_EXPIRATION is also set to ON unless it is explicitly set to OFF.</span></span>  
  
    -   <span data-ttu-id="0d2fb-128">El historial de contraseñas se inicializa con el valor del hash de contraseña actual.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-128">The password history is initialized with the value of the current password hash.</span></span>  
  
    -   <span data-ttu-id="0d2fb-129">**Duración de bloqueo de cuenta**, **Umbral de bloqueo de cuenta**y **Restablecer recuento de bloqueos de cuentas tras** también están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-129">**Account lockout duration**, **account lockout threshold**, and **reset account lockout counter after** are also enabled.</span></span>  
  
-   <span data-ttu-id="0d2fb-130">Cuando el valor de CHECK_POLICY se cambia a OFF, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d2fb-130">When CHECK_POLICY is changed to OFF, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="0d2fb-131">La opción CHECK_EXPIRATION también se cambia a OFF.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-131">CHECK_EXPIRATION is also set to OFF.</span></span>  
  
    -   <span data-ttu-id="0d2fb-132">Se borra el historial de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-132">The password history is cleared.</span></span>  
  
    -   <span data-ttu-id="0d2fb-133">Se restablece el valor de `lockout_time` .</span><span class="sxs-lookup"><span data-stu-id="0d2fb-133">The value of `lockout_time` is reset.</span></span>  
  
 <span data-ttu-id="0d2fb-134">Algunas combinaciones de opciones de directiva no se admiten.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-134">Some combinations of policy options are not supported.</span></span>  
  
-   <span data-ttu-id="0d2fb-135">Si se especifica MUST_CHANGE, CHECK_EXPIRATION y CHECK_POLICY, deben establecerse en ON.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-135">If MUST_CHANGE is specified, CHECK_EXPIRATION and CHECK_POLICY must be set to ON.</span></span> <span data-ttu-id="0d2fb-136">Si no es así, la instrucción producirá un error.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-136">Otherwise, the statement will fail.</span></span>  
  
-   <span data-ttu-id="0d2fb-137">Si CHECK_POLICY se establece en OFF, CHECK_EXPIRATION no puede establecerse en ON.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-137">If CHECK_POLICY is set to OFF, CHECK_EXPIRATION cannot be set to ON.</span></span> <span data-ttu-id="0d2fb-138">Una instrucción ALTER LOGIN con esta combinación de opciones dará error.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-138">An ALTER LOGIN statement that has this combination of options will fail.</span></span>  
  
 <span data-ttu-id="0d2fb-139">Establecer CHECK_POLICY = ON impide la creación de las contraseñas que sean:</span><span class="sxs-lookup"><span data-stu-id="0d2fb-139">Setting CHECK_POLICY = ON will prevent the creation of passwords that are:</span></span>  
  
-   <span data-ttu-id="0d2fb-140">NULL o vacías</span><span class="sxs-lookup"><span data-stu-id="0d2fb-140">Null or empty</span></span>  
  
-   <span data-ttu-id="0d2fb-141">Iguales al nombre del equipo o el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="0d2fb-141">Same as name of computer or login</span></span>  
  
-   <span data-ttu-id="0d2fb-142">Una de las siguientes: "password", "admin", "administrator", "sa", "sysadmin"</span><span class="sxs-lookup"><span data-stu-id="0d2fb-142">Any of the following: "password", "admin", "administrator", "sa", "sysadmin"</span></span>  
  
 <span data-ttu-id="0d2fb-143">La directiva de seguridad se podría establecer en Windows o se podría recibir del dominio.</span><span class="sxs-lookup"><span data-stu-id="0d2fb-143">The security policy might be set in Windows, or might be received from the domain.</span></span> <span data-ttu-id="0d2fb-144">Para ver la directiva de contraseñas en el equipo, use el complemento de MMC Directiva de seguridad local (**secpol.msc**).</span><span class="sxs-lookup"><span data-stu-id="0d2fb-144">To view the password policy on the computer, use the Local Security Policy MMC snap-in (**secpol.msc**).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0d2fb-145">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0d2fb-145">Related Tasks</span></span>  
 [<span data-ttu-id="0d2fb-146">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d2fb-146">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
 [<span data-ttu-id="0d2fb-147">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d2fb-147">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
 [<span data-ttu-id="0d2fb-148">CREATE USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d2fb-148">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
 [<span data-ttu-id="0d2fb-149">ALTER USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d2fb-149">ALTER USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-user-transact-sql)  
  
 [<span data-ttu-id="0d2fb-150">Crear un inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="0d2fb-150">Create a Login</span></span>](authentication-access/create-a-login.md)  
  
 [<span data-ttu-id="0d2fb-151">Crear un usuario de base de datos</span><span class="sxs-lookup"><span data-stu-id="0d2fb-151">Create a Database User</span></span>](authentication-access/create-a-database-user.md)  
  
## <a name="related-content"></a><span data-ttu-id="0d2fb-152">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="0d2fb-152">Related Content</span></span>  
 [<span data-ttu-id="0d2fb-153">Contraseñas seguras</span><span class="sxs-lookup"><span data-stu-id="0d2fb-153">Strong Passwords</span></span>](strong-passwords.md)  
  
  
