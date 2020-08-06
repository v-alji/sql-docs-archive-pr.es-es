---
title: Propiedades de memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LowMemoryLimit property
- MinimumAllocatedMemory property
- MidMemoryPrice property
- MemoryHeapType property
- memory [Analysis Services]
- DefaultPagesCountToReuse property
- TotalMemoryLimit property
- SessionMemoryLimit property
- VirtualMemoryLimit property
- WaitCountIfHighMemory property
- HighMemoryPrice property
- HeapTypeForObjects property
ms.assetid: 085f5195-7b2c-411a-9813-0ff5c6066d13
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f2d2e56c9a951cee27752bd57d55d185a9b6618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752381"
---
# <a name="memory-properties"></a><span data-ttu-id="d0774-102">Propiedades de memoria</span><span class="sxs-lookup"><span data-stu-id="d0774-102">Memory Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="d0774-103">admite las propiedades de memoria de servidor que aparecen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="d0774-103">supports the server memory properties listed in the following table.</span></span> <span data-ttu-id="d0774-104">Para obtener información orientativa acerca de estas propiedades, vea la [Guía de operaciones de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="d0774-104">For guidance in setting these properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 <span data-ttu-id="d0774-105">Los valores comprendidos entre 1 y 100 representan porcentajes de **Memoria física total** o de **Espacio de direcciones virtuales**, lo que sea menor.</span><span class="sxs-lookup"><span data-stu-id="d0774-105">Values between 1 and 100 represent percentages of **Total Physical Memory** or **Virtual Address Space**, whichever is less.</span></span> <span data-ttu-id="d0774-106">Los valores superiores a 100 representan límites de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="d0774-106">Values over 100 represent memory limits in bytes.</span></span>  
  
 <span data-ttu-id="d0774-107">**Se aplica a:** Modo de servidor multidimensional y tabular, a menos que se indique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="d0774-107">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d0774-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d0774-108">Properties</span></span>  
 `LowMemoryLimit`  
 <span data-ttu-id="d0774-109">Una propiedad numérica de 64 bits con signo, de punto flotante y de doble precisión que define el punto en el que el servidor tiene poca memoria, expresada como porcentaje de la memoria física total.</span><span class="sxs-lookup"><span data-stu-id="d0774-109">A signed 64-bit double-precision floating-point number property that defines the point at which the server is low on memory, expressed as percentage of total physical memory.</span></span> <span data-ttu-id="d0774-110">Cuando se alcanza este límite, la instancia comenzará lentamente a limpiar cachés de la memoria cerrando las sesiones expiradas y descargando los cálculos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d0774-110">When this limit is reached, the instance will start to slowly clear memory out of caches by closing expired sessions and unloading unused calculations.</span></span> <span data-ttu-id="d0774-111">El servidor no liberará memoria por debajo de este límite.</span><span class="sxs-lookup"><span data-stu-id="d0774-111">The server will not release memory below this limit.</span></span> <span data-ttu-id="d0774-112">El valor predeterminado es 65, lo que indica que el límite de memoria baja es el 65% de la memoria física o del espacio de direcciones virtuales, lo que sea menor.</span><span class="sxs-lookup"><span data-stu-id="d0774-112">The default value is 65; which indicates the low memory limit is 65% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 `TotalMemoryLimit`  
 <span data-ttu-id="d0774-113">Define un umbral que, cuando se alcanza, hace que el servidor desasigne memoria de forma más enérgica.</span><span class="sxs-lookup"><span data-stu-id="d0774-113">Defines a threshold that when reached, causes the server to deallocate memory more aggressively.</span></span> <span data-ttu-id="d0774-114">El valor predeterminado es el 80% de la memoria física o el espacio de direcciones virtuales, lo que sea menor.</span><span class="sxs-lookup"><span data-stu-id="d0774-114">The default value 80% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 <span data-ttu-id="d0774-115">Tenga en cuenta que `TotalMemoryLimit` siempre debe ser menor que `HardMemoryLimit`</span><span class="sxs-lookup"><span data-stu-id="d0774-115">Note that `TotalMemoryLimit` must always be less than `HardMemoryLimit`</span></span>  
  
 `HardMemoryLimit`  
 <span data-ttu-id="d0774-116">Especifica un umbral de memoria a partir del cual la instancia finaliza enérgicamente las sesiones de usuario activas para reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="d0774-116">Specifies a memory threshold after which the instance aggressively terminates active user sessions to reduce memory usage.</span></span> <span data-ttu-id="d0774-117">Todas las sesiones finalizadas recibirán un error indicando que la cancelación se ha debido a la presión de memoria.</span><span class="sxs-lookup"><span data-stu-id="d0774-117">All terminated sessions will receive an error about being cancelled by memory pressure.</span></span> <span data-ttu-id="d0774-118">El valor predeterminado, cero (0), significa que `HardMemoryLimit` se establecerá en un valor intermedio comprendido entre `TotalMemoryLimit` y la memoria física total del sistema; si la memoria física del sistema es mayor que el espacio de direcciones virtuales del proceso, se usará dicho espacio para calcular `HardMemoryLimit`.</span><span class="sxs-lookup"><span data-stu-id="d0774-118">The default value, zero (0), means the `HardMemoryLimit` will be set to a midway value between `TotalMemoryLimit` and the total physical memory of the system; if the physical memory of the system is larger than the virtual address space of the process, then virtual address space will be used instead to calculate `HardMemoryLimit`.</span></span>  
  
 `VirtualMemoryLimit`  
 <span data-ttu-id="d0774-119">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-119">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `VertiPaqPagingPolicy`  
 <span data-ttu-id="d0774-120">Especifica el comportamiento de la paginación en caso de que el servidor se quede sin apenas memoria.</span><span class="sxs-lookup"><span data-stu-id="d0774-120">Specifies the paging behavior in the event the server runs low on memory.</span></span> <span data-ttu-id="d0774-121">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0774-121">Valid values are as follows:</span></span>  
  
 <span data-ttu-id="d0774-122">Cero (**0**) deshabilita la paginación.</span><span class="sxs-lookup"><span data-stu-id="d0774-122">Zero (**0**) disables paging.</span></span> <span data-ttu-id="d0774-123">Si la memoria es insuficiente, el procesamiento genera un error de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="d0774-123">If memory is insufficient, processing fails with an out-of-memory error.</span></span> <span data-ttu-id="d0774-124">Si ha deshabilitado la paginación, debe otorgar privilegios de Windows a la cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="d0774-124">If you disable paging, you must grant Windows privileges to the service account.</span></span> <span data-ttu-id="d0774-125">Para obtener instrucciones, vea [Configurar las cuentas de servicio &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d0774-125">See [Configure Service Accounts &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md) for instructions.</span></span>  
  
 <span data-ttu-id="d0774-126">**1** es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d0774-126">**1** is the default.</span></span> <span data-ttu-id="d0774-127">Esta propiedad habilita la paginación en disco mediante el archivo de paginación del sistema operativo (pagefile.sys).</span><span class="sxs-lookup"><span data-stu-id="d0774-127">This property enables paging to disk using the operating system page file (pagefile.sys).</span></span>  
  
 <span data-ttu-id="d0774-128">Cuando `VertiPaqPagingPolicy` se establece en 1, es menos probable que se produzcan errores en el procesamiento debido a restricciones de memoria, ya que el servidor intentará paginar en el disco utilizando el método especificado.</span><span class="sxs-lookup"><span data-stu-id="d0774-128">When `VertiPaqPagingPolicy` is set to 1, processing is less likely to fail due to memory constraints because the server will try to page to disk using the method that you specified.</span></span> <span data-ttu-id="d0774-129">Establecer la propiedad `VertiPaqPagingPolicy` no garantiza que no se producirán errores de memoria.</span><span class="sxs-lookup"><span data-stu-id="d0774-129">Setting the `VertiPaqPagingPolicy` property does not guarantee that memory errors will never happen.</span></span> <span data-ttu-id="d0774-130">Pueden seguir produciéndose errores de memoria insuficiente en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="d0774-130">Out of memory errors can still occur under the following conditions:</span></span>  
  
-   <span data-ttu-id="d0774-131">No hay suficiente memoria para todos los diccionarios.</span><span class="sxs-lookup"><span data-stu-id="d0774-131">There is not enough memory for all dictionaries.</span></span> <span data-ttu-id="d0774-132">Durante el procesamiento, Analysis Services bloquea los diccionarios de cada columna en memoria, y todos juntos no pueden superar el valor especificado en `VertiPaqMemoryLimit`.</span><span class="sxs-lookup"><span data-stu-id="d0774-132">During processing, Analysis Services locks the dictionaries for each column in memory, and all of these together cannot be more than the value specified for `VertiPaqMemoryLimit`.</span></span>  
  
-   <span data-ttu-id="d0774-133">No hay espacio suficiente en las direcciones virtuales para alojar el proceso.</span><span class="sxs-lookup"><span data-stu-id="d0774-133">There is insufficient virtual address space to accommodate the process.</span></span>  
  
 <span data-ttu-id="d0774-134">Para resolver problemas persistentes de memoria insuficiente, puede intentar rediseñar el modelo a fin de reducir la cantidad de datos que necesita procesar o agregar más memoria física al equipo.</span><span class="sxs-lookup"><span data-stu-id="d0774-134">To resolve persistent out of memory errors, you can either try to redesign the model to reduce the amount of data that needs processing, or you can add more physical memory to the computer.</span></span>  
  
 <span data-ttu-id="d0774-135">Se aplica solo al modo de servidor tabular.</span><span class="sxs-lookup"><span data-stu-id="d0774-135">Applies to tabular server mode only.</span></span>  
  
 `VertiPaqMemoryLimit`  
 <span data-ttu-id="d0774-136">Si se permite la paginación en el disco, esta propiedad especifica el nivel de consumo de memoria (como porcentaje de la memoria total) en el que comienza la paginación.</span><span class="sxs-lookup"><span data-stu-id="d0774-136">If paging to disk is allowed, this property specifies the level of memory consumption (as a percentage of total memory) at which paging starts.</span></span> <span data-ttu-id="d0774-137">El valor predeterminado es 60.</span><span class="sxs-lookup"><span data-stu-id="d0774-137">The default is 60.</span></span> <span data-ttu-id="d0774-138">Si el consumo de memoria es inferior al 60 por ciento, el servidor no paginará en el disco.</span><span class="sxs-lookup"><span data-stu-id="d0774-138">If memory consumption is less than 60 percent, the server will not page to disk.</span></span>  
  
 <span data-ttu-id="d0774-139">Esta propiedad depende de `VertiPaqPagingPolicyProperty`, que se debe establecer en 1 para que se produzca la paginación.</span><span class="sxs-lookup"><span data-stu-id="d0774-139">This property depends on the `VertiPaqPagingPolicyProperty`, which must be set to 1 in order for paging to occur.</span></span>  
  
 <span data-ttu-id="d0774-140">Se aplica solo al modo de servidor tabular.</span><span class="sxs-lookup"><span data-stu-id="d0774-140">Applies to tabular server mode only.</span></span>  
  
 `HighMemoryPrice`  
 <span data-ttu-id="d0774-141">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryHeapType`  
 <span data-ttu-id="d0774-142">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="d0774-143">Se aplica solo al modo de servidor multidimensional.</span><span class="sxs-lookup"><span data-stu-id="d0774-143">Applies to multidimensional server mode only.</span></span>  
  
 `HeapTypeForObjects`  
 <span data-ttu-id="d0774-144">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="d0774-145">Se aplica solo al modo de servidor multidimensional.</span><span class="sxs-lookup"><span data-stu-id="d0774-145">Applies to multidimensional server mode only.</span></span>  
  
 `DefaultPagesCountToReuse`  
 <span data-ttu-id="d0774-146">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `HandleIA64AlignmentFaults`  
 <span data-ttu-id="d0774-147">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MidMemoryPrice`  
 <span data-ttu-id="d0774-148">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinimumAllocatedMemory`  
 <span data-ttu-id="d0774-149">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PreAllocate`  
 <span data-ttu-id="d0774-150">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SessionMemoryLimit`  
 <span data-ttu-id="d0774-151">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `WaitCountIfHighMemory`  
 <span data-ttu-id="d0774-152">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0774-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0774-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d0774-153">See Also</span></span>  
 <span data-ttu-id="d0774-154">[Configurar las propiedades del servidor en Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="d0774-154">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="d0774-155">Determinar el modo de servidor de una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d0774-155">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
