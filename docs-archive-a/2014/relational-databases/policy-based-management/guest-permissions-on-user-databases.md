---
title: Permisos de invitado en bases de datos de usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 540f1c6d-df51-497e-958a-3a0f429d2920
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 344c5fd0639876998f1585c32fac5f7599f664e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663450"
---
# <a name="guest-permissions-on-user-databases"></a><span data-ttu-id="ad431-102">Permisos de invitado en bases de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="ad431-102">Guest Permissions on User Databases</span></span>
  <span data-ttu-id="ad431-103">Esta regla determina si el usuario invitado tiene permiso de acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ad431-103">This rule determines whether the guest user has permission to access the database.</span></span> <span data-ttu-id="ad431-104">Esta regla solo se aplica a las bases de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="ad431-104">This rule applies to user databases only.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="ad431-105">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="ad431-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="ad431-106">Revoque el permiso del usuario invitado para tener acceso a la base de datos si no se requiere.</span><span class="sxs-lookup"><span data-stu-id="ad431-106">Revoke the guest user permission to access the database if it is not required.</span></span>  
  
 <span data-ttu-id="ad431-107">El usuario guest no puede quitarse, pero puede deshabilitarse si revoca su permiso CONNECT; para ello, ejecute REVOKE CONNECT FROM GUEST en cualquier base de datos que no sea master, tempdb ni msdb.</span><span class="sxs-lookup"><span data-stu-id="ad431-107">The guest user cannot be dropped, but guest user can be disabled by revoking its CONNECT permission by executing REVOKE CONNECT FROM GUEST within any database other than master, tempdb, or msdb.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ad431-108">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="ad431-108">For More Information</span></span>  
 [<span data-ttu-id="ad431-109">Proteger SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad431-109">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ad431-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad431-110">See Also</span></span>  
 [<span data-ttu-id="ad431-111">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="ad431-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
