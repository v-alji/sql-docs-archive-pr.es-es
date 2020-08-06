---
title: Expiración de contraseña de inicio de sesión de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7e3bf9da-a436-433d-847a-47c30428cad3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 678e8e9c6b567014bdd49e89d043165bc48d168a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662854"
---
# <a name="sql-server-login-password-expiration"></a><span data-ttu-id="7b988-102">Expiración de contraseña de inicio de sesión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7b988-102">SQL Server Login Password Expiration</span></span>
  <span data-ttu-id="7b988-103">Esta regla comprueba si la "expiración de contraseña" de cada inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7b988-103">This rule checks whether "Password expiration" of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is enabled.</span></span> <span data-ttu-id="7b988-104">Si la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está habilitada y la versión del sistema operativo es anterior a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], un atacante podría aprovechar varias veces una contraseña de inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conocida.</span><span class="sxs-lookup"><span data-stu-id="7b988-104">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is enabled and if the operating system version is earlier than [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], an attacker could repeatedly exploit a known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login password.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="7b988-105">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="7b988-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="7b988-106">Recomendamos que actualice el sistema operativo a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b988-106">We recommend that you upgrade the operating system to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span></span>  
  
 <span data-ttu-id="7b988-107">Si la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se requiere en el entorno, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7b988-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is not required in your environment, use Windows Authentication.</span></span> <span data-ttu-id="7b988-108">Para obtener más información, vea [Elegir un modo de autenticación](../security/choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="7b988-108">For more information, see [Choose an Authentication Mode](../security/choose-an-authentication-mode.md).</span></span>  
  
 <span data-ttu-id="7b988-109">Habilite la "expiración de contraseña" para todos los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b988-109">Enable "Password expiration" for all the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="7b988-110">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) con el fin de configurar la directiva de contraseñas para el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b988-110">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="7b988-111">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="7b988-111">For More Information</span></span>  
 [<span data-ttu-id="7b988-112">Directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="7b988-112">Password Policy</span></span>](../security/password-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b988-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b988-113">See Also</span></span>  
 [<span data-ttu-id="7b988-114">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="7b988-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
