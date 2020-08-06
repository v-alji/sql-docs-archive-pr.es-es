---
title: Superposición correcta de la máscara de afinidad y de salida de entrada de afinidad | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1a0da6df-57ff-4f3f-aae9-2fbc4897508c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486b4441a20db7630082344fb1f277bba053f3ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752121"
---
# <a name="correct-affinity-mask-and-affinity-input-output-mask-overlap"></a><span data-ttu-id="b1f49-102">Superposición correcta de la máscara de afinidad y de salida de entrada de afinidad</span><span class="sxs-lookup"><span data-stu-id="b1f49-102">Correct Affinity Mask and Affinity Input Output Mask Overlap</span></span>
  <span data-ttu-id="b1f49-103">Esta regla comprueba si la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiene uno o varios procesadores que están asignados para usarse con las opciones de máscara de afinidad y de máscara de afinidad de E/S.</span><span class="sxs-lookup"><span data-stu-id="b1f49-103">This rule checks whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one or more processors that are assigned to be used with both the affinity mask and the affinity I/O mask options.</span></span> <span data-ttu-id="b1f49-104">En un equipo con más de un procesador, las opciones de máscara de afinidad y de máscara de afinidad de E/S se utilizan para designar qué CPU usa [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1f49-104">On a computer that has more than one processor, the affinity mask and the affinity I/O mask options are used to designate which CPUs are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b1f49-105">Al habilitar una CPU con la máscara de afinidad y con la máscara de afinidad de E/S, se puede ralentizar el rendimiento al exigir que el procesador se use demasiado.</span><span class="sxs-lookup"><span data-stu-id="b1f49-105">Enabling a CPU with both the affinity mask and the affinity I/O mask can slow performance by forcing the processor to be overused.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b1f49-106">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="b1f49-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b1f49-107">Al especificar las opciones de máscara de afinidad o de máscara de afinidad de E/S, debería especificar ambas, pero habilitar cada CPU únicamente una vez.</span><span class="sxs-lookup"><span data-stu-id="b1f49-107">When you specify either the affinity mask or the affinity I/O mask options, you should specify both, but only enable each CPU no more than once.</span></span>  
  
 <span data-ttu-id="b1f49-108">No habilite la misma CPU en ambas opciones de máscara de afinidad y de máscara de afinidad de E/S.</span><span class="sxs-lookup"><span data-stu-id="b1f49-108">Do not enable the same CPU in both the affinity mask option and the affinity I/O mask option.</span></span> <span data-ttu-id="b1f49-109">Los bits que corresponden a cada CPU deberían estar en alguno de los estados siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1f49-109">The bits that correspond to each CPU should be in one of the following states:</span></span>  
  
-   <span data-ttu-id="b1f49-110">0 tanto en la opción de máscara de afinidad de E/S como en la opción máscara de afinidad.</span><span class="sxs-lookup"><span data-stu-id="b1f49-110">0 in both the affinity mask option and the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="b1f49-111">0 en la opción de máscara de afinidad y 1 en la opción de máscara de afinidad de E/S.</span><span class="sxs-lookup"><span data-stu-id="b1f49-111">0 in the affinity mask option and 1 in the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="b1f49-112">1 en la opción de máscara de afinidad y 0 en la opción de máscara de afinidad de E/S.</span><span class="sxs-lookup"><span data-stu-id="b1f49-112">1 in the affinity mask option and 0 in the affinity I/O mask option</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="b1f49-113">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="b1f49-113">For More Information</span></span>  
 [<span data-ttu-id="b1f49-114">affinity mask (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="b1f49-114">affinity mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="b1f49-115">affinity Input-Output mask (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="b1f49-115">affinity Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-input-output-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="b1f49-116">affinity64 mask (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="b1f49-116">affinity64 mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="b1f49-117">affinity64 I/O mask (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="b1f49-117">affinity64 Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-input-output-mask-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1f49-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1f49-118">See Also</span></span>  
 [<span data-ttu-id="b1f49-119">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="b1f49-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
