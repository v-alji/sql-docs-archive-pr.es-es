---
title: max full-text crawl range (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- crawls [full-text search]
- max full-text crawl range option
ms.assetid: a49de86b-0891-4dcd-89c0-ead30aab00e0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1dbd9e44518b6e849a06a76e21fc605172fd2ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744302"
---
# <a name="max-full-text-crawl-range-server-configuration-option"></a><span data-ttu-id="cb36b-102">max full-text crawl range (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="cb36b-102">max full-text crawl range Server Configuration Option</span></span>
  <span data-ttu-id="cb36b-103">La opción **max full-text crawl range** (tamaño máximo de rastreo de texto completo) sirve para optimizar el uso de la CPU, lo que mejora el rendimiento durante un rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="cb36b-103">Use the **max full-text crawl range** option to optimize CPU utilization, which improves crawl performance during a full crawl.</span></span> <span data-ttu-id="cb36b-104">Con esta opción, puede especificar el número de particiones que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe usar durante un rastreo de índice completo.</span><span class="sxs-lookup"><span data-stu-id="cb36b-104">Using this option, you can specify the number of partitions that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should use during a full index crawl.</span></span> <span data-ttu-id="cb36b-105">Por ejemplo, si hay muchas CPU y su uso no es óptimo, puede aumentar el valor máximo de esta opción.</span><span class="sxs-lookup"><span data-stu-id="cb36b-105">For example, if there are many CPUs and their utilization is not optimal, you can increase the maximum value of this option.</span></span> <span data-ttu-id="cb36b-106">Además de esta opción, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliza otros factores, como el número de filas de la tabla y el número de CPU, para determinar el número real de particiones utilizadas.</span><span class="sxs-lookup"><span data-stu-id="cb36b-106">In addition to this option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses a number of other factors, such as the number of rows in the table and the number of CPUs, to determine the actual number of partitions used.</span></span>  
  
 <span data-ttu-id="cb36b-107">El valor predeterminado de esta opción es 4, el valor mínimo es 1 y el valor máximo es 256.</span><span class="sxs-lookup"><span data-stu-id="cb36b-107">The default value of this option is 4; the minimum value is 1, and the maximum value is 256.</span></span> <span data-ttu-id="cb36b-108">Los cambios realizados en esta opción solo afectan a los rastreos subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="cb36b-108">Changes made to this option affect only subsequent crawls.</span></span> <span data-ttu-id="cb36b-109">Los cambios en la configuración de esta opción no afectarán a los rastreos en curso.</span><span class="sxs-lookup"><span data-stu-id="cb36b-109">Crawls in process will not be affected by a change in this option setting.</span></span>  
  
 <span data-ttu-id="cb36b-110">La opción **max full-text crawl range** es una opción avanzada.</span><span class="sxs-lookup"><span data-stu-id="cb36b-110">The **max full-text crawl range** option is an advanced option.</span></span> <span data-ttu-id="cb36b-111">Si está usando el procedimiento almacenado del sistema **sp_configure** para cambiar la configuración, solo podrá cambiar el valor de **max full-text crawl range** si **show advanced options** está establecido en 1.</span><span class="sxs-lookup"><span data-stu-id="cb36b-111">If you are using the **sp_configure** system stored procedure to change the setting, you can change **max full-text crawl range** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="cb36b-112">La configuración surte efecto inmediatamente, sin necesidad de reiniciar un servidor.</span><span class="sxs-lookup"><span data-stu-id="cb36b-112">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb36b-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb36b-113">See Also</span></span>  
 <span data-ttu-id="cb36b-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cb36b-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="cb36b-115">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cb36b-115">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="cb36b-116">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb36b-116">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
