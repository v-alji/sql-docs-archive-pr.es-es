---
title: ft notify bandwidth (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- ft notify bandwidth opion
- small memory buffers
- memory [SQL Server], buffers
ms.assetid: 9ca284c5-f3e0-4a67-a132-fff376ff0ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dc5839f699d55edf86c5e3e3f0eb001089a0a5dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748915"
---
# <a name="ft-notify-bandwidth-server-configuration-option"></a><span data-ttu-id="e833d-102">ft notify bandwidth (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="e833d-102">ft notify bandwidth Server Configuration Option</span></span>
  <span data-ttu-id="e833d-103">Utilice la opción **ft notify bandwidth** (ancho de banda de notificación de texto completo) para especificar el tamaño hasta el que pueden crecer los grupos de búferes de memoria pequeños.</span><span class="sxs-lookup"><span data-stu-id="e833d-103">Use the **ft notify bandwidth** option to specify the size to which the pool of small memory buffers can grow.</span></span> <span data-ttu-id="e833d-104">Los búferes de memoria pequeños tienen un tamaño de 64 kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="e833d-104">Small memory buffers are 64 kilobytes (KB) in size.</span></span> <span data-ttu-id="e833d-105">El valor del parámetro *max* especifica el número máximo de búferes que debería mantener el administrador de memoria de texto completo en un grupo de búferes pequeño.</span><span class="sxs-lookup"><span data-stu-id="e833d-105">The *max* parameter value specifies the maximum number of buffers that the full-text memory manager should maintain in a small buffer pool.</span></span> <span data-ttu-id="e833d-106">Si el `max` valor es cero, no hay ningún límite superior para el número de búferes que pueden estar en un grupo de búferes pequeño.</span><span class="sxs-lookup"><span data-stu-id="e833d-106">If the `max` value is zero, then there is no upper limit to the number of buffers that can be in a small buffer pool.</span></span>  
  
 <span data-ttu-id="e833d-107">El parámetro **min** especifica el número mínimo de búferes de memoria que deben mantenerse en el grupo de búferes de memoria pequeños.</span><span class="sxs-lookup"><span data-stu-id="e833d-107">The **min** parameter specifies the minimum number of memory buffers that must be maintained in the pool of small memory buffers.</span></span> <span data-ttu-id="e833d-108">Previa solicitud del administrador de memoria de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se liberan todos los grupos de búferes adicionales, aunque se mantiene este número mínimo de búferes.</span><span class="sxs-lookup"><span data-stu-id="e833d-108">Upon request from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory manager, all extra buffer pools will be released but this minimum number of buffers will be maintained.</span></span> <span data-ttu-id="e833d-109">Sin embargo, si el valor especificado de **min** es cero, se liberarán todos los búferes de memoria.</span><span class="sxs-lookup"><span data-stu-id="e833d-109">If, however, the **min** value specified is zero, then all memory buffers are released.</span></span>  
  
 <span data-ttu-id="e833d-110">Bajo ciertas circunstancias, el número de búferes asignados actualmente es menor que el valor especificado por el parámetro **min** .</span><span class="sxs-lookup"><span data-stu-id="e833d-110">Under certain circumstances the number of buffers currently allocated is less than the value specified by the **min** parameter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e833d-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e833d-111">See Also</span></span>  
 <span data-ttu-id="e833d-112">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e833d-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="e833d-113">[ft crawl bandwidth (opción de configuración del servidor)](ft-crawl-bandwidth-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="e833d-113">[ft crawl bandwidth Server Configuration Option](ft-crawl-bandwidth-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="e833d-114">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e833d-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
