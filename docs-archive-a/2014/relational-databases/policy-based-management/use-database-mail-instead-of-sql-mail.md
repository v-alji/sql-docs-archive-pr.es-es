---
title: Usar Correo electrónico de base de datos en lugar de SQL Mail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b08df7be-d8be-4184-a661-38ec0ac85cd1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a6a957b65975645bdeb9f55faee4e650b53718b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670981"
---
# <a name="use-database-mail-instead-of-sql-mail"></a><span data-ttu-id="6e355-102">Usar Correo electrónico de base de datos en lugar de SQL Mail</span><span class="sxs-lookup"><span data-stu-id="6e355-102">Use Database Mail Instead of SQL Mail</span></span>
  <span data-ttu-id="6e355-103">Esta regla comprueba la vista de catálogo sys.configurations para determinar si la opción de configuración de todo el servidor SQL Mail XPs está establecida en ON.</span><span class="sxs-lookup"><span data-stu-id="6e355-103">This rule checks the sys.configurations catalog view to determine whether the SQL Mail XPs server-wide configuration option is set to ON.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="6e355-104">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="6e355-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="6e355-105">SQL Mail se quitará en una versión futura de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e355-105">SQL Mail will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6e355-106">Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan.</span><span class="sxs-lookup"><span data-stu-id="6e355-106">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span> <span data-ttu-id="6e355-107">Para enviar correo, utilice el Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="6e355-107">To send mail, use Database Mail.</span></span>  
  
 <span data-ttu-id="6e355-108">SQL Mail se ejecuta en proceso para el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e355-108">SQL Mail runs in-process to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="6e355-109">Si SQL Mail se bloquea, también se bloquea el servidor.</span><span class="sxs-lookup"><span data-stu-id="6e355-109">If SQL Mail goes down, so does the server.</span></span> <span data-ttu-id="6e355-110">Correo electrónico de base de datos se ejecuta fuera de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en un proceso independiente, es escalable y no requiere instalar los componentes de cliente MAPI extendido en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="6e355-110">Database Mail runs outside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a separate process, is scalable, and does not require Extended MAPI client components to be installed on the production server.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="6e355-111">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="6e355-111">For More Information</span></span>  
 [<span data-ttu-id="6e355-112">Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="6e355-112">Database Mail</span></span>](../database-mail/database-mail.md)  
  
## <a name="see-also"></a><span data-ttu-id="6e355-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e355-113">See Also</span></span>  
 [<span data-ttu-id="6e355-114">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="6e355-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
