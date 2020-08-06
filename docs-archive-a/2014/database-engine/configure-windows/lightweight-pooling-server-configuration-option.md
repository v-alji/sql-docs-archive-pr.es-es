---
title: lightweight pooling (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default lightweight pooling
- decreasing overhead
- lightweight pooling option
- system overhead [SQL Server]
- performance [SQL Server], lightweight pooling
- context switching [SQL Server], lightweight pooling option
- excessive context switching [SQL Server]
- reducing overhead
- overhead [SQL Server]
ms.assetid: 2dc11b61-d065-4126-8e00-acf40390f9fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 549ff7451a31b48459b5a290b94ad406c3768a91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673895"
---
# <a name="lightweight-pooling-server-configuration-option"></a><span data-ttu-id="513e1-102">lightweight pooling (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="513e1-102">lightweight pooling Server Configuration Option</span></span>
  <span data-ttu-id="513e1-103">Use la opción **agrupación ligera** para proporcionar un medio de reducir la sobrecarga del sistema asociada al cambio de contexto excesivo que se puede observar a veces en entornos con multiprocesadores simétricos (SMP).</span><span class="sxs-lookup"><span data-stu-id="513e1-103">Use the **lightweight pooling** option to provide a means of reducing the system overhead associated with the excessive context switching sometimes seen in symmetric multiprocessing (SMP) environments.</span></span> <span data-ttu-id="513e1-104">Cuando hay un cambio de contexto excesivo, la opción de agrupación ligera puede proporcionar un mayor rendimiento al realizar el cambio de contexto insertado, lo que ayuda a reducir las transiciones de llamadas entre el usuario y el kernel.</span><span class="sxs-lookup"><span data-stu-id="513e1-104">When excessive context switching is present, lightweight pooling can provide better throughput by performing the context switching inline, thus helping to reduce user/kernel ring transitions.</span></span>  
  
 <span data-ttu-id="513e1-105">El modo de fibra se destina a determinadas situaciones en las que el cambio de contexto de los trabajadores de UMS es un cuello de botella decisivo para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="513e1-105">Fiber mode is intended for certain situations in which the context switching of the UMS workers are the critical bottleneck in performance.</span></span> <span data-ttu-id="513e1-106">Al ser esta situación inusual, el modo de fibra rara vez mejora el rendimiento o la escalabilidad en el sistema típico.</span><span class="sxs-lookup"><span data-stu-id="513e1-106">Because this is rare, fiber mode rarely enhances performance or scalability on the typical system.</span></span> <span data-ttu-id="513e1-107">El cambio de contexto mejorado de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] también ha reducido la necesidad del modo de fibra.</span><span class="sxs-lookup"><span data-stu-id="513e1-107">Improved context switching in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] has also reduced the need for fiber mode.</span></span> <span data-ttu-id="513e1-108">No se recomienda utilizar la programación en modo de fibra para un funcionamiento habitual.</span><span class="sxs-lookup"><span data-stu-id="513e1-108">We do not recommend that you use fiber mode scheduling for routine operation.</span></span> <span data-ttu-id="513e1-109">La razón es que puede reducir el rendimiento al impedir las ventajas normales del cambio de contexto, y que algunos componentes de porque algunos componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que utiliza Subproceso Almacenamiento Local (TLS) o los objetos poseídos por subproceso, como exclusiones mutuas (un tipo de objeto de kernel de Win32), no pueden funcionar correctamente en modo de fibra.</span><span class="sxs-lookup"><span data-stu-id="513e1-109">This is because it can decrease performance by inhibiting the regular benefits of context switching, and because some components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that use Thread Local Storage (TLS) or thread-owned objects, such as mutexes (a type of Win32 kernel object), cannot function correctly in fiber mode.</span></span>  
  
 <span data-ttu-id="513e1-110">Si establece el valor 1 para **agrupación ligera** , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cambiará a la programación en modo de fibra.</span><span class="sxs-lookup"><span data-stu-id="513e1-110">Setting **lightweight pooling** to 1 causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to switch to fiber mode scheduling.</span></span> <span data-ttu-id="513e1-111">El valor predeterminado para esta opción es 0.</span><span class="sxs-lookup"><span data-stu-id="513e1-111">The default value for this option is 0.</span></span>  
  
 <span data-ttu-id="513e1-112">**Agrupación ligera** es una opción avanzada.</span><span class="sxs-lookup"><span data-stu-id="513e1-112">The **lightweight pooling** option is an advanced option.</span></span> <span data-ttu-id="513e1-113">Si está usando el procedimiento almacenado del sistema **sp_configure** para cambiar la configuración, solo podrá cambiar el valor de **agrupación ligera** si **Mostrar opciones avanzadas** está establecido en 1.</span><span class="sxs-lookup"><span data-stu-id="513e1-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change **lightweight pooling** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="513e1-114">La configuración surte efecto cuando se reinicia el servidor.</span><span class="sxs-lookup"><span data-stu-id="513e1-114">The setting takes effect after the server is restarted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="513e1-115">La agrupación ligera no es compatible con [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 ni con [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span><span class="sxs-lookup"><span data-stu-id="513e1-115">Lightweight pooling is not supported for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span></span> [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] <span data-ttu-id="513e1-116">es compatible con la agrupación ligera.</span><span class="sxs-lookup"><span data-stu-id="513e1-116">provides full support for lightweight pooling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="513e1-117">No se admite la ejecución de Common Language Runtime (CLR) con "agrupación ligera".</span><span class="sxs-lookup"><span data-stu-id="513e1-117">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="513e1-118">Deshabilite una de las dos opciones: "clr enabled" o "agrupación ligera".</span><span class="sxs-lookup"><span data-stu-id="513e1-118">Disable one of two options: "clr enabled" or "lightweight pooling".</span></span> <span data-ttu-id="513e1-119">Entre las características que dependen de CLR y que no funcionan correctamente en modo de fibra se encuentran el tipo de datos de jerarquía, la replicación y la administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="513e1-119">Features that rely upon CLR and that do not work properly in fiber mode include the hierarchy data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="513e1-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="513e1-120">See Also</span></span>  
 <span data-ttu-id="513e1-121">[clr enabled (opción de configuración del servidor)](clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="513e1-121">[clr enabled Server Configuration Option](clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="513e1-122">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="513e1-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="513e1-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="513e1-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="513e1-124">clr enabled (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="513e1-124">clr enabled Server Configuration Option</span></span>](clr-enabled-server-configuration-option.md)  
  
  
