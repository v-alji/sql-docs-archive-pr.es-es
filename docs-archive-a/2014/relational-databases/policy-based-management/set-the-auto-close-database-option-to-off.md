---
title: Establecer en OFF la opción de base de datos AUTO_CLOSE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: e6b03364-263a-4ec4-9794-de9869d396ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: db6cf5a3f82c3493a8732958594743104fccc968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749745"
---
# <a name="set-the-auto_close-database-option-to-off"></a><span data-ttu-id="71aef-102">Establecer en OFF la opción de base de datos AUTO_CLOSE</span><span class="sxs-lookup"><span data-stu-id="71aef-102">Set the AUTO_CLOSE Database Option to OFF</span></span>
  <span data-ttu-id="71aef-103">Esta regla comprueba si la opción AUTO_ CLOSE está establecida en OFF.</span><span class="sxs-lookup"><span data-stu-id="71aef-103">This rule checks whether the AUTO_ CLOSE option is set OFF.</span></span> <span data-ttu-id="71aef-104">Cuando AUTO_CLOSE se establece en ON, esta opción puede producir la degradación del rendimiento en las bases de datos a las que se tiene acceso con frecuencia debido a la mayor sobrecarga que supone la apertura y el cierre de la base de datos después de cada conexión.</span><span class="sxs-lookup"><span data-stu-id="71aef-104">When AUTO_CLOSE is set ON, this option can cause performance degradation on frequently accessed databases because of the increased overhead of opening and closing the database after each connection.</span></span> <span data-ttu-id="71aef-105">AUTO_CLOSE también vacía la memoria caché de procedimientos después de cada conexión.</span><span class="sxs-lookup"><span data-stu-id="71aef-105">AUTO_CLOSE also flushes the procedure cache after each connection.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="71aef-106">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="71aef-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="71aef-107">Si se tiene acceso a una base de datos con frecuencia, establezca la opción AUTO_CLOSE en OFF para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="71aef-107">If a database is accessed frequently, set the AUTO_CLOSE option to OFF for the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="71aef-108">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="71aef-108">For More Information</span></span>  
 [<span data-ttu-id="71aef-109">Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71aef-109">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="71aef-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71aef-110">See Also</span></span>  
 [<span data-ttu-id="71aef-111">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="71aef-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
