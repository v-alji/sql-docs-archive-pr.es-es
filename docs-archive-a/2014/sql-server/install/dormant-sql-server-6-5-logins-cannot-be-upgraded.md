---
title: No se pueden actualizar los inicios de sesión SQL Server 6,5 inactivos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- passwords [SQL Server], dormant logins
- dormant logins
- logins [SQL Server], upgrading dormant logins
- identifying dormant logins
- password hashes [SQL Server]
ms.assetid: ebe18a74-0375-4df4-b894-239f8fdabb64
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f78bca9bf2b99b2ab6f530613b64bc0e46c4001c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672474"
---
# <a name="dormant-sql-server-65-logins-cannot-be-upgraded"></a><span data-ttu-id="14ae7-102">No se pueden actualizar los inicios de sesión inactivos de SQL Server 6.5</span><span class="sxs-lookup"><span data-stu-id="14ae7-102">Dormant SQL Server 6.5 logins cannot be upgraded</span></span>
  <span data-ttu-id="14ae7-103">El Asesor de actualizaciones detectó un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuya contraseña no se puede actualizar directamente a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14ae7-103">Upgrade Advisor detected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login whose password cannot be directly upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="14ae7-104">Para habilitar este inicio de sesión, debe restablecer su contraseña.</span><span class="sxs-lookup"><span data-stu-id="14ae7-104">To enable this login, you must reset its password.</span></span> <span data-ttu-id="14ae7-105">Puede restablecer la contraseña utilizando ALTER LOGIN.</span><span class="sxs-lookup"><span data-stu-id="14ae7-105">You can reset the password by using ALTER LOGIN.</span></span>  
  
```  
ALTER LOGIN <login name> WITH PASSWORD = '<new password>' MUST_CHANGE  
```  
  
 <span data-ttu-id="14ae7-106">La nueva contraseña se validará con la directiva de complejidad de contraseñas del sistema, a menos que la comprobación de directivas esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="14ae7-106">The new password will be validated against your system's password complexity policy, unless policy checking is disabled.</span></span> <span data-ttu-id="14ae7-107">Se recomienda utilizar contraseñas complejas y no deshabilitar la comprobación de directivas.</span><span class="sxs-lookup"><span data-stu-id="14ae7-107">We recommend that you use complex passwords and not disable policy checking.</span></span> <span data-ttu-id="14ae7-108">La opción MUST_CHANGE obliga al usuario a seleccionar una contraseña nueva.</span><span class="sxs-lookup"><span data-stu-id="14ae7-108">The MUST_CHANGE option forces the user to select a new password.</span></span> <span data-ttu-id="14ae7-109">Esto no es necesario, pero es recomendable.</span><span class="sxs-lookup"><span data-stu-id="14ae7-109">This is not required, but it is recommended.</span></span>  
  
 <span data-ttu-id="14ae7-110">Puede identificar los inicios de sesión inactivos utilizando la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="14ae7-110">You can identify dormant logins by using the following query:</span></span>  
  
```  
SELECT * FROM sysxlogins WHERE (xstatus & 2048) = 2048;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="14ae7-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14ae7-111">See Also</span></span>  
 <span data-ttu-id="14ae7-112">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="14ae7-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="14ae7-113">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="14ae7-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
