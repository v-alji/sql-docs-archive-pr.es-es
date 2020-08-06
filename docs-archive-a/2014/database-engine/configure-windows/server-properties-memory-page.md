---
title: Propiedades del servidor (página Memoria) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.memory.f1
ms.assetid: 46a77d4e-ab92-49d3-a14b-423462e50715
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a000a4c670b36b08a34fd544cc5ff5e61c7bab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673892"
---
# <a name="server-properties-memory-page"></a><span data-ttu-id="265aa-102">Propiedades del servidor (página Memoria)</span><span class="sxs-lookup"><span data-stu-id="265aa-102">Server Properties (Memory Page)</span></span>
  <span data-ttu-id="265aa-103">Utilice esta página para ver o modificar las opciones de memoria del servidor.</span><span class="sxs-lookup"><span data-stu-id="265aa-103">Use this page to view or modify your server memory options.</span></span> <span data-ttu-id="265aa-104">Cuando **Cantidad mínima de memoria del servidor** está establecida en 0 y **Cantidad máxima de memoria del servidor** está establecida en 2147483647 MB, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede aprovechar la cantidad óptima de memoria en un momento dado, dependiendo de la cantidad de memoria que utilicen en ese momento el sistema operativo y otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="265aa-104">When **Minimum server memory** is set to 0 and **Maximum server memory** is set to 2147483647 MB, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can take advantage of the optimum amount of memory at any given time, subject to how much memory the operating system and other applications are currently using.</span></span> <span data-ttu-id="265aa-105">Al cambiar la carga del equipo y de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , también cambia la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="265aa-105">As the load on the computer and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] changes, so does the memory allocated.</span></span> <span data-ttu-id="265aa-106">Puede limitar aún más esta asignación de memoria dinámica a los valores máximos y mínimos que se especifican a continuación.</span><span class="sxs-lookup"><span data-stu-id="265aa-106">You can further limit this dynamic memory allocation to the minimum and maximum values specified below.</span></span>  
  
## <a name="options"></a><span data-ttu-id="265aa-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="265aa-107">Options</span></span>  
 <span data-ttu-id="265aa-108">**Cantidad mínima de memoria del servidor (en MB)**</span><span class="sxs-lookup"><span data-stu-id="265aa-108">**Minimum server memory (in MB)**</span></span>  
 <span data-ttu-id="265aa-109">Especifica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe empezar, al menos, con la cantidad mínima de memoria asignada y no debe liberar memoria por debajo de este valor.</span><span class="sxs-lookup"><span data-stu-id="265aa-109">Specifies that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should start with at least the minimum amount of allocated memory and not release memory below this value.</span></span> <span data-ttu-id="265aa-110">Establezca este valor basándose en el tamaño y la actividad de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="265aa-110">Set this value based on the size and activity of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="265aa-111">Establezca siempre la opción en un valor razonable para asegurarse de que el sistema operativo no requiere demasiada memoria de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y no impide el rendimiento de Windows.</span><span class="sxs-lookup"><span data-stu-id="265aa-111">Always set the option to a reasonable value to ensure that the operating system does not request too much memory from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and inhibit Windows performance.</span></span>  
  
 <span data-ttu-id="265aa-112">**Cantidad máxima de memoria del servidor (en MB)**</span><span class="sxs-lookup"><span data-stu-id="265aa-112">**Maximum server memory (in MB)**</span></span>  
 <span data-ttu-id="265aa-113">Especifica la cantidad máxima de memoria que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede asignar cuando se inicia y mientras se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="265aa-113">Specifies the maximum amount of memory [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can allocate when it starts and while it runs.</span></span> <span data-ttu-id="265aa-114">Puede establecer esta opción de configuración como un valor específico si sabe que se ejecutan varias aplicaciones al mismo tiempo que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y desea que estas aplicaciones tengan memoria suficiente para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="265aa-114">This configuration option can be set to a specific value if you know there are multiple applications running at the same time as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and you want to guarantee that these applications have sufficient memory to run.</span></span> <span data-ttu-id="265aa-115">Si estas otras aplicaciones, por ejemplo, los servidores web o de correo electrónico, solo solicitan memoria cuando la necesitan, no establezca la opción, ya que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suministrará memoria cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="265aa-115">If these other applications, such as Web or e-mail servers, request memory only as needed, then do not set the option, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will release memory to them as needed.</span></span> <span data-ttu-id="265aa-116">Sin embargo, a menudo las aplicaciones utilizan la memoria disponible cuando se inician y no solicitan más aunque sea necesario.</span><span class="sxs-lookup"><span data-stu-id="265aa-116">However, applications often use whatever memory is available when they start and do not request more if needed.</span></span> <span data-ttu-id="265aa-117">Si una aplicación con este comportamiento se ejecuta en el mismo equipo que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]simultáneamente, establezca la opción con un valor que garantice que la memoria que requiere la aplicación no está asignada por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="265aa-117">If an application that behaves in this manner runs on the same computer at the same time as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], set the option to a value that guarantees that the memory required by the application is not allocated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="265aa-118">La cantidad mínima de memoria que puede especificar para **memoria de servidor máxima** es 64 megabytes (MB) para sistemas de 32 bits y 128 MB para sistemas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="265aa-118">The minimum amounts of memory you can specify for **max server memory** are 64 megabytes (MB) for 32-bit systems and 128 MB for 64-bit systems.</span></span>  
  
 <span data-ttu-id="265aa-119">**Memoria de creación de índice (en KB, 0 = memoria dinámica)**</span><span class="sxs-lookup"><span data-stu-id="265aa-119">**Index creation memory (in KB, 0 = dynamic memory)**</span></span>  
 <span data-ttu-id="265aa-120">Especifica la cantidad de memoria (en KB) que se va a utilizar durante la ordenación en la creación de índices.</span><span class="sxs-lookup"><span data-stu-id="265aa-120">Specifies the amount of memory (in KB) to use during index creation sorts.</span></span> <span data-ttu-id="265aa-121">El valor predeterminado de cero permite la asignación dinámica y funcionará en la mayoría de los casos sin ajustes adicionales; sin embargo, el usuario puede escribir un valor diferente, entre 704 y 2147483647.</span><span class="sxs-lookup"><span data-stu-id="265aa-121">The default value of zero enables dynamic allocation and should work in most cases without additional adjustment; however, the user can enter a different value from 704 to 2147483647.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="265aa-122">No se admiten los valores de 1 a 703.</span><span class="sxs-lookup"><span data-stu-id="265aa-122">Values from 1 to 703 are not allowed.</span></span> <span data-ttu-id="265aa-123">Si se escribe un valor en este intervalo, el campo reemplazará el valor especificado con 704.</span><span class="sxs-lookup"><span data-stu-id="265aa-123">If a value in this range is entered, the field overrides the entered value with 704.</span></span>  
  
 <span data-ttu-id="265aa-124">**Cantidad mínima de memoria por consulta (en KB)**</span><span class="sxs-lookup"><span data-stu-id="265aa-124">**Minimum memory per query (in KB)**</span></span>  
 <span data-ttu-id="265aa-125">Especifica la cantidad de memoria (en KB) que se va a asignar para la ejecución de una consulta.</span><span class="sxs-lookup"><span data-stu-id="265aa-125">Specifies the amount of memory (in KB) to allocate for the execution of a query.</span></span> <span data-ttu-id="265aa-126">El usuario puede establecer el valor desde 512 hasta 2147483647 KB.</span><span class="sxs-lookup"><span data-stu-id="265aa-126">The user can set the value from 512 to 2147483647 KB.</span></span> <span data-ttu-id="265aa-127">El valor predeterminado es 1024 KB.</span><span class="sxs-lookup"><span data-stu-id="265aa-127">The default value is 1024 KB.</span></span>  
  
 <span data-ttu-id="265aa-128">**Valores configurados**</span><span class="sxs-lookup"><span data-stu-id="265aa-128">**Configured Values**</span></span>  
 <span data-ttu-id="265aa-129">Muestra los valores configurados para las opciones de este panel.</span><span class="sxs-lookup"><span data-stu-id="265aa-129">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="265aa-130">Si cambia estos valores, haga clic en **Valores actuales** para comprobar si los cambios han surtido efecto.</span><span class="sxs-lookup"><span data-stu-id="265aa-130">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="265aa-131">Si no tienen, deberá reiniciarse primero la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="265aa-131">If they have not, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted first.</span></span>  
  
 <span data-ttu-id="265aa-132">**Valores actuales**</span><span class="sxs-lookup"><span data-stu-id="265aa-132">**Running Values**</span></span>  
 <span data-ttu-id="265aa-133">Muestra los valores actuales de las opciones de este panel.</span><span class="sxs-lookup"><span data-stu-id="265aa-133">Shows the currently running values for the options on this pane.</span></span> <span data-ttu-id="265aa-134">Estos valores son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="265aa-134">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265aa-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="265aa-135">See Also</span></span>  
 <span data-ttu-id="265aa-136">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="265aa-136">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="265aa-137">Opciones de configuración de memoria del servidor</span><span class="sxs-lookup"><span data-stu-id="265aa-137">Server Memory Server Configuration Options</span></span>](server-memory-server-configuration-options.md)  
  
  