---
title: Propiedades del servidor (página Procesadores) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.processor.f1
ms.assetid: cc1581a2-492b-41f0-bda5-17909b65c4f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4d241f01de7ac961832e77bb09483cff275deb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673881"
---
# <a name="server-properties-processors-page"></a><span data-ttu-id="8d784-102">Propiedades del servidor (página Procesadores)</span><span class="sxs-lookup"><span data-stu-id="8d784-102">Server Properties (Processors Page)</span></span>
  <span data-ttu-id="8d784-103">Utilice esta página para ver o modificar las opciones del procesador.</span><span class="sxs-lookup"><span data-stu-id="8d784-103">Use this page to view or modify your processor options.</span></span> <span data-ttu-id="8d784-104">Los valores de configuración de la afinidad del procesador solo se habilitan si hay más de un procesador instalado.</span><span class="sxs-lookup"><span data-stu-id="8d784-104">Processor affinity settings are only enabled when more than one processor is installed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d784-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="8d784-105">Options</span></span>  
 <span data-ttu-id="8d784-106">**Afinidad del procesador**</span><span class="sxs-lookup"><span data-stu-id="8d784-106">**Processor Affinity**</span></span>  
 <span data-ttu-id="8d784-107">Asigna procesadores a subprocesos específicos para eliminar las recargas de procesador y reducir la migración de subprocesos entre los procesadores.</span><span class="sxs-lookup"><span data-stu-id="8d784-107">Assigns processors to specific threads to eliminating processor reloads and reduce thread migration across processors.</span></span> <span data-ttu-id="8d784-108">Para obtener más información, vea [affinity mask (opción de configuración del servidor)](affinity-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="8d784-108">For more information, see [affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="8d784-109">**Afinidad de E/S**</span><span class="sxs-lookup"><span data-stu-id="8d784-109">**I/O Affinity**</span></span>  
 <span data-ttu-id="8d784-110">Enlaza las E/S de disco de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con un subconjunto determinado de CPU.</span><span class="sxs-lookup"><span data-stu-id="8d784-110">Binds [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disk I/Os to a specified subset of CPUs.</span></span> <span data-ttu-id="8d784-111">Para obtener más información, vea [affinity I/O mask (opción de configuración del servidor)](affinity-input-output-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="8d784-111">For more information, see [affinity Input-Output mask Server Configuration Option](affinity-input-output-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="8d784-112">**Establecer automáticamente máscara de afinidad de procesador para todos los procesadores**</span><span class="sxs-lookup"><span data-stu-id="8d784-112">**Automatically set processor affinity mask for all processors**</span></span>  
 <span data-ttu-id="8d784-113">Permite a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] definir la afinidad de los procesadores.</span><span class="sxs-lookup"><span data-stu-id="8d784-113">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the processor affinity.</span></span>  
  
 <span data-ttu-id="8d784-114">**Establecer automáticamente máscara de afinidad de E/S para todos los procesadores**</span><span class="sxs-lookup"><span data-stu-id="8d784-114">**Automatically set I/O affinity mask for all processors**</span></span>  
 <span data-ttu-id="8d784-115">Permite a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] definir la afinidad de E/S.</span><span class="sxs-lookup"><span data-stu-id="8d784-115">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the I/O affinity.</span></span>  
  
 <span data-ttu-id="8d784-116">**Número máximo de subprocesos de trabajo**</span><span class="sxs-lookup"><span data-stu-id="8d784-116">**Maximum worker threads**</span></span>  
 <span data-ttu-id="8d784-117">0 permite a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] establecer de forma dinámica el número de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8d784-117">0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to dynamically set the number of worker threads.</span></span> <span data-ttu-id="8d784-118">Este valor es el más adecuado para la mayor parte de los sistemas.</span><span class="sxs-lookup"><span data-stu-id="8d784-118">This setting is best for most systems.</span></span> <span data-ttu-id="8d784-119">No obstante, según la configuración del sistema, definir esta opción en un valor específico puede mejorar, a veces, el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8d784-119">However, depending on your system configuration, setting this option to a specific value sometimes improves performance.</span></span> <span data-ttu-id="8d784-120">Para más información, consulte [Establecer la opción de configuración del servidor Máximo de subprocesos de trabajo](configure-the-max-worker-threads-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="8d784-120">For more information, see [Configure the max worker threads Server Configuration Option](configure-the-max-worker-threads-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="8d784-121">**Aumentar la prioridad de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8d784-121">**Boost SQL Server priority**</span></span>  
 <span data-ttu-id="8d784-122">Especifica si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe ejecutarse con una prioridad de programación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows mayor que la de los demás procesos del mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="8d784-122">Specifies whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="8d784-123">Para más información, consulte [Establecer la opción de configuración del servidor Aumento de prioridad](configure-the-priority-boost-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="8d784-123">For more information, see [Configure the priority boost Server Configuration Option](configure-the-priority-boost-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="8d784-124">**Usar fibras de Windows (agrupación ligera)**</span><span class="sxs-lookup"><span data-stu-id="8d784-124">**Use Windows fibers (lightweight pooling)**</span></span>  
 <span data-ttu-id="8d784-125">Utiliza fibras de Windows en lugar de subprocesos para el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d784-125">Use Windows fibers instead of threads for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="8d784-126">Esta opción no está disponible en Windows 2003 Server Edition.</span><span class="sxs-lookup"><span data-stu-id="8d784-126">Note that this is only available in Windows 2003 Server Edition.</span></span> <span data-ttu-id="8d784-127">Para obtener más información, consulte [lightweight pooling (opción de configuración del servidor)](lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="8d784-127">For more information, see [lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="8d784-128">**Valores configurados**</span><span class="sxs-lookup"><span data-stu-id="8d784-128">**Configured Values**</span></span>  
 <span data-ttu-id="8d784-129">Muestra los valores configurados para las opciones de este panel.</span><span class="sxs-lookup"><span data-stu-id="8d784-129">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="8d784-130">Si cambia estos valores, haga clic en **Valores actuales** para comprobar si los cambios han surtido efecto.</span><span class="sxs-lookup"><span data-stu-id="8d784-130">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="8d784-131">Si no tienen, deberá reiniciarse primero la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d784-131">If they have not, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted first.</span></span>  
  
 <span data-ttu-id="8d784-132">**Valores actuales**</span><span class="sxs-lookup"><span data-stu-id="8d784-132">**Running Values**</span></span>  
 <span data-ttu-id="8d784-133">Presenta los valores actuales de las opciones de este panel.</span><span class="sxs-lookup"><span data-stu-id="8d784-133">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="8d784-134">Estos valores son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8d784-134">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d784-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d784-135">See Also</span></span>  
 [<span data-ttu-id="8d784-136">Opciones de configuración de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8d784-136">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
