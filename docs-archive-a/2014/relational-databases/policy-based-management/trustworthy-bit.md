---
title: Bit de confianza | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3198188a-2b59-4865-9560-10f760934b8e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 062a63dd52f4641a0ddfcbc20cb9bad3cce6dc61
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670992"
---
# <a name="trustworthy-bit"></a><span data-ttu-id="5fa5e-102">Bit de confianza</span><span class="sxs-lookup"><span data-stu-id="5fa5e-102">Trustworthy Bit</span></span>
  <span data-ttu-id="5fa5e-103">Esta regla determina si el rol dbo para una base de datos está asignado al rol fijo de servidor sysadmin y la base de datos tiene su bit de confianza establecido en ON.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-103">This rule determines whether the dbo role for a database is assigned to the sysadmin fixed server role and the database has its trustworthy bit set to ON.</span></span>  
  
 <span data-ttu-id="5fa5e-104">Si se cumplen estas condiciones, un usuario privilegiado de la base de datos puede elevar los privilegios al rol sysadmin.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-104">If these conditions are met, a privileged database user can elevate privileges to the sysadmin role.</span></span> <span data-ttu-id="5fa5e-105">En este rol, el usuario puede crear y ejecutar ensamblados no seguros que ponen en peligro el sistema.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-105">In this role, the user can create and run unsafe assemblies that compromise the system.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="5fa5e-106">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="5fa5e-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="5fa5e-107">Desactive el bit de confianza o revoque los permisos sysadmin del rol de la base de datos dbo.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-107">Turn off the trustworthy bit or revoke sysadmin permissions from the dbo database role.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="5fa5e-108">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="5fa5e-108">For More Information</span></span>  
 [<span data-ttu-id="5fa5e-109">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5fa5e-109">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="5fa5e-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5fa5e-110">See Also</span></span>  
 [<span data-ttu-id="5fa5e-111">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="5fa5e-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
