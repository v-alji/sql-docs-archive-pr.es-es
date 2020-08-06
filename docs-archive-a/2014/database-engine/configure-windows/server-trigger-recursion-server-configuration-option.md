---
title: server trigger recursion (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- recursive triggers [SQL Server]
- triggers [SQL Server], recursive
- server trigger recursion option
ms.assetid: da4c25f5-d04c-4951-a3db-409e71a1b468
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 23a4997bd1a6f8b2c04af34d5cdc3229575901a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749467"
---
# <a name="server-trigger-recursion-server-configuration-option"></a><span data-ttu-id="186a3-102">server trigger recursion (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="186a3-102">server trigger recursion Server Configuration Option</span></span>
  <span data-ttu-id="186a3-103">Use la opción **server trigger recursion** para especificar si se permite la activación repetida de los desencadenadores del servidor.</span><span class="sxs-lookup"><span data-stu-id="186a3-103">Use the **server trigger recursion** option to specify whether to allow server-level triggers to fire recursively.</span></span> <span data-ttu-id="186a3-104">Cuando esta opción se establece en 1 (activada), se permite esta activación repetida.</span><span class="sxs-lookup"><span data-stu-id="186a3-104">When this option is set to 1 (ON), server-level triggers will be allowed to fire recursively.</span></span> <span data-ttu-id="186a3-105">Cuando el valor es 0 (desactivada), los desencadenadores del servidor no pueden activarse repetidamente.</span><span class="sxs-lookup"><span data-stu-id="186a3-105">When set to 0 (OFF), server-level triggers cannot be fired recursively.</span></span> <span data-ttu-id="186a3-106">Cuando la opción server trigger recursion se establece en 0 (desactivada), solo se impide la recursividad directa.</span><span class="sxs-lookup"><span data-stu-id="186a3-106">Only direct recursion is prevented when the server trigger recursion option is set to 0 (OFF).</span></span> <span data-ttu-id="186a3-107">(Para deshabilitar la recursividad indirecta, establezca la opción **nested triggers** en 0). El valor predeterminado para esta opción es 1 (activada).</span><span class="sxs-lookup"><span data-stu-id="186a3-107">(To disable indirect recursion, set the **nested triggers** option to 0.) The default value for this option is 1 (ON).</span></span> <span data-ttu-id="186a3-108">El valor surte efecto inmediatamente (sin necesidad de reiniciar el servidor).</span><span class="sxs-lookup"><span data-stu-id="186a3-108">The setting takes effect immediately (without a server restart).</span></span>  
  
 <span data-ttu-id="186a3-109">Para obtener más información, vea [Crear desencadenadores anidado](../../relational-databases/triggers/create-nested-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="186a3-109">For more information, see [Create Nested Triggers](../../relational-databases/triggers/create-nested-triggers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="186a3-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="186a3-110">See Also</span></span>  
 <span data-ttu-id="186a3-111">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="186a3-111">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="186a3-112">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="186a3-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="186a3-113">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="186a3-113">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
