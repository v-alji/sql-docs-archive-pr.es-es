---
title: ft crawl bandwidth (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- large memory buffers
- memory [SQL Server], buffers
- ft crawl bandwidth option
ms.assetid: e5864ad9-92f5-43b5-95de-46d68ded8694
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 33821ff1fdbc4248c71906d8307a8164a7f64d24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750137"
---
# <a name="ft-crawl-bandwidth-server-configuration-option"></a><span data-ttu-id="e73f6-102">ft crawl bandwidth (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="e73f6-102">ft crawl bandwidth Server Configuration Option</span></span>
  <span data-ttu-id="e73f6-103">Utilice la opción **ft crawl bandwidth** (ancho de banda de notificación de texto completo) para especificar el tamaño hasta donde puede crecer un grupo de búferes de memoria de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="e73f6-103">Use the **ft crawl bandwidth** option to specify the size to which the pool of large memory buffers can grow.</span></span> <span data-ttu-id="e73f6-104">Los búferes de memoria de gran tamaño tienen 4 MB.</span><span class="sxs-lookup"><span data-stu-id="e73f6-104">Large memory buffers are 4 megabytes (MB) in size.</span></span> <span data-ttu-id="e73f6-105">El valor del parámetro **max** especifica el máximo de búferes que debe mantener el administrador de memoria de texto completo en un grupo de búferes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="e73f6-105">The **max** parameter value specifies the maximum number of buffers that the full-text memory manager should maintain in a large buffer pool.</span></span> <span data-ttu-id="e73f6-106">Si el valor de **max** es cero, no habrá ningún límite superior para el número de búferes que pueden estar en un grupo de búferes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="e73f6-106">If the **max** value is zero, then there is no upper limit to the number of buffers that can be in a large buffer pool.</span></span>  
  
 <span data-ttu-id="e73f6-107">El parámetro **min** especifica el número mínimo de búferes de memoria que deben mantenerse en el grupo de búferes de memoria de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="e73f6-107">The **min** parameter specifies the minimum number of memory buffers that must be maintained in the pool of large memory buffers.</span></span> <span data-ttu-id="e73f6-108">Previa solicitud del administrador de memoria de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se liberan todos los grupos de búferes adicionales, aunque se mantiene este número mínimo de búferes.</span><span class="sxs-lookup"><span data-stu-id="e73f6-108">Upon request from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory manager, all extra buffer pools will be released but this minimum number of buffers will be maintained.</span></span> <span data-ttu-id="e73f6-109">Sin embargo, si el valor especificado de **min** es cero, se liberarán todos los búferes de memoria.</span><span class="sxs-lookup"><span data-stu-id="e73f6-109">If, however, the **min** value specified is zero, then all memory buffers are released.</span></span>  
  
 <span data-ttu-id="e73f6-110">Bajo ciertas circunstancias, el número de búferes asignados actualmente es menor que el valor especificado por el parámetro **min** .</span><span class="sxs-lookup"><span data-stu-id="e73f6-110">Under certain circumstances, the number of buffers currently allocated is less than the value specified by the **min** parameter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e73f6-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e73f6-111">See Also</span></span>  
 <span data-ttu-id="e73f6-112">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e73f6-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="e73f6-113">[Opción de configuración del servidor Ancho de banda para notificación de texto completo](ft-notify-bandwidth-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="e73f6-113">[ft notify bandwidth Server Configuration Option](ft-notify-bandwidth-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="e73f6-114">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e73f6-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
