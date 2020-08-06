---
title: Permisos públicos de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 9a276caa-ea38-473d-92bc-26302bfcf660
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7913c4715f47b8105b72b1c817dbe77e52d40539
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749754"
---
# <a name="server-public-permissions"></a><span data-ttu-id="c367e-102">Permisos públicos de servidor</span><span class="sxs-lookup"><span data-stu-id="c367e-102">Server public Permissions</span></span>
  <span data-ttu-id="c367e-103">Esta regla determina si el rol de servidor public tiene permisos de servidor.</span><span class="sxs-lookup"><span data-stu-id="c367e-103">This rule determines whether the public server role has server permissions.</span></span> <span data-ttu-id="c367e-104">Cada inicio de sesión que se crea en el servidor es miembro del rol de servidor public.</span><span class="sxs-lookup"><span data-stu-id="c367e-104">Every login that is created on the server is a member of the public server role.</span></span> <span data-ttu-id="c367e-105">Si esta condición se cumple, cada inicio de sesión en el servidor tendrá los permisos de servidor.</span><span class="sxs-lookup"><span data-stu-id="c367e-105">If this condition is met, every login on the server will have server permissions.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="c367e-106">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="c367e-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="c367e-107">No conceda permisos de servidor al rol de servidor public.</span><span class="sxs-lookup"><span data-stu-id="c367e-107">Do not grant server permissions to the server public role.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c367e-108">Una vez completada la instalación, el rol **Public** tiene `CONNECT` permiso en todos los extremos excepto en la **conexión de administrador dedicada**.</span><span class="sxs-lookup"><span data-stu-id="c367e-108">After setup completes the **PUBLIC** role has `CONNECT` permission on all the endpoints except the **Dedicated Admin Connection**.</span></span> <span data-ttu-id="c367e-109">Esto es normal y habitualmente no se debe cambiar.</span><span class="sxs-lookup"><span data-stu-id="c367e-109">This is normal and should not be normally changed.</span></span> <span data-ttu-id="c367e-110">(El acceso se controla mediante el permiso `CONNECT SQL` que se concede automáticamente cuando se crean nuevos inicios de sesión).</span><span class="sxs-lookup"><span data-stu-id="c367e-110">(Access is controlled by using the `CONNECT SQL` permission which is automatically granted when new logins are created.)</span></span>  
  
### <a name="for-more-information"></a><span data-ttu-id="c367e-111">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="c367e-111">For more information</span></span>  
 [<span data-ttu-id="c367e-112">Proteger SQL Server</span><span class="sxs-lookup"><span data-stu-id="c367e-112">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
  
