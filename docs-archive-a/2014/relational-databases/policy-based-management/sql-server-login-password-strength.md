---
title: Seguridad de la contraseña de inicio de sesión de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b0862c3a-926b-490c-a37f-382e50146a3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5534748fbbf810539f2dcfc22239e4b987cf0f77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744636"
---
# <a name="sql-server-login-password-strength"></a><span data-ttu-id="e3ba9-102">Seguridad de la contraseña de inicio de sesión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3ba9-102">SQL Server Login Password Strength</span></span>
  <span data-ttu-id="e3ba9-103">Esta regla comprueba si "Exigir directivas de contraseñas" de cada inicio de sesión [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está habilitada.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-103">This rule checks whether "Enforce password policy" of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is enabled.</span></span> <span data-ttu-id="e3ba9-104">Si la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está habilitada y la versión del sistema operativo es anterior a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], un atacante podría aprovechar varias veces una contraseña de inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conocida.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-104">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is enabled and if the operating system version is earlier than [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], an attacker could repeatedly exploit a known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login password.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="e3ba9-105">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="e3ba9-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="e3ba9-106">Recomendamos que actualice el sistema operativo a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3ba9-106">We recommend that you upgrade the operating system to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span></span>  
  
 <span data-ttu-id="e3ba9-107">Si la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se requiere en el entorno, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e3ba9-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is not required in your environment, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="e3ba9-108">Habilite "Exigir directivas de contraseña" para todos los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3ba9-108">Enable "Enforce password policy" for all the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="e3ba9-109">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) con el fin de configurar la directiva de contraseñas para el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3ba9-109">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="e3ba9-110">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="e3ba9-110">For More Information</span></span>  
 [<span data-ttu-id="e3ba9-111">Directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="e3ba9-111">Password Policy</span></span>](../security/password-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="e3ba9-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3ba9-112">See Also</span></span>  
 [<span data-ttu-id="e3ba9-113">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="e3ba9-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
