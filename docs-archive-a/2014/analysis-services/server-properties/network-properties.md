---
title: Propiedades de red | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LingerTimeout property
- EnableNagleAlgorithm property
- MinPendingAcceptExCount property
- MaxPendingSendCount property
- EnableBinaryXML property
- MinPendingReceiveCount property
- MaxCompletedReceiveCount property
- DisableNonblockingMode property
- RequestSizeThreshold property
- CompressionLevel property
- ReceiveBufferSize property
- EnableCompression property
- ServerSendTimeout property
- IPV4Support property
- MaxPendingReceiveCount property
- MaxPendingAcceptExCount property
- IPV6Support property
- MaxAllowedRequestSize property
- ServerReceiveTimeout property
- EnableLingerOnClose property
- InitialConnectTimeout property
- SendBufferSize property
- ScatterReceiveMultiplier property
- network properties [Analysis Services]
ms.assetid: ef4251e2-abe5-4c5b-9868-7549782d0244
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10ad5bbbcffdfc3d3c4fefe3111e4c4425919915
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672303"
---
# <a name="network-properties"></a><span data-ttu-id="7daa5-102">Propiedades de red</span><span class="sxs-lookup"><span data-stu-id="7daa5-102">Network Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="7daa5-103">admite las propiedades de servidor descritas en las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="7daa5-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="7daa5-104">Para obtener más información sobre las propiedades de servidor adicionales y cómo establecerlas, vea [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="7daa5-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="7daa5-105">**Se aplica a:** modo de servidor multidimensional y tabular</span><span class="sxs-lookup"><span data-stu-id="7daa5-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="general"></a><span data-ttu-id="7daa5-106">General</span><span class="sxs-lookup"><span data-stu-id="7daa5-106">General</span></span>  
 `ListenOnlyOnLocalConnections`  
 <span data-ttu-id="7daa5-107">Una propiedad booleana que identifica si se va a escuchar solo en conexiones locales, por ejemplo localhost.</span><span class="sxs-lookup"><span data-stu-id="7daa5-107">A Boolean property that identifies whether to listen only on local connections, for example localhost.</span></span>  
  
## <a name="listener"></a><span data-ttu-id="7daa5-108">Agente de escucha</span><span class="sxs-lookup"><span data-stu-id="7daa5-108">Listener</span></span>  
 `IPV4Support`  
 <span data-ttu-id="7daa5-109">Una propiedad de entero de 32 bits con signo que define la compatibilidad con el protocolo IPv4.</span><span class="sxs-lookup"><span data-stu-id="7daa5-109">A signed 32-bit integer property that defines support for IPv4 protocol.</span></span> <span data-ttu-id="7daa5-110">Esta propiedad tiene uno de los valores descritos en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="7daa5-110">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="7daa5-111">Value</span><span class="sxs-lookup"><span data-stu-id="7daa5-111">Value</span></span>|<span data-ttu-id="7daa5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7daa5-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7daa5-113">*0*</span><span class="sxs-lookup"><span data-stu-id="7daa5-113">*0*</span></span>|<span data-ttu-id="7daa5-114">IPv4 deshabilitado; los clientes no pueden conectarse.</span><span class="sxs-lookup"><span data-stu-id="7daa5-114">IPv4 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="7daa5-115">*1*</span><span class="sxs-lookup"><span data-stu-id="7daa5-115">*1*</span></span>|<span data-ttu-id="7daa5-116">(Predeterminado) IPv4 es obligatorio; el servidor no se iniciará si no puede escuchar a IPv4.</span><span class="sxs-lookup"><span data-stu-id="7daa5-116">(Default) IPv4 is required; server won't start if it cannot listen to IPv4.</span></span>|  
|<span data-ttu-id="7daa5-117">*2*</span><span class="sxs-lookup"><span data-stu-id="7daa5-117">*2*</span></span>|<span data-ttu-id="7daa5-118">IPv4 es opcional; el servidor intenta escuchar a IPv4 pero se inicia en caso de no poder hacerlo.</span><span class="sxs-lookup"><span data-stu-id="7daa5-118">IPv4 is optional; server tries to listen to IPv4 but starts even if unable to.</span></span>|  
  
 `IPV6Support`  
 <span data-ttu-id="7daa5-119">Una propiedad de entero de 32 bits con signo que define la compatibilidad con el protocolo IPv6.</span><span class="sxs-lookup"><span data-stu-id="7daa5-119">A signed 32-bit integer property that defines support for IPv6 protocol.</span></span> <span data-ttu-id="7daa5-120">Esta propiedad tiene uno de los valores descritos en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="7daa5-120">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="7daa5-121">Value</span><span class="sxs-lookup"><span data-stu-id="7daa5-121">Value</span></span>|<span data-ttu-id="7daa5-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="7daa5-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7daa5-123">*0*</span><span class="sxs-lookup"><span data-stu-id="7daa5-123">*0*</span></span>|<span data-ttu-id="7daa5-124">IPv6 deshabilitado; los clientes no pueden conectarse.</span><span class="sxs-lookup"><span data-stu-id="7daa5-124">IPv6 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="7daa5-125">*1*</span><span class="sxs-lookup"><span data-stu-id="7daa5-125">*1*</span></span>|<span data-ttu-id="7daa5-126">(Predeterminado) IPv6 es obligatorio; el servidor no se iniciará si no puede escuchar a IPv6.</span><span class="sxs-lookup"><span data-stu-id="7daa5-126">(Default) IPv6 is required; server won't start if it cannot listen to IPv6.</span></span>|  
|<span data-ttu-id="7daa5-127">*2*</span><span class="sxs-lookup"><span data-stu-id="7daa5-127">*2*</span></span>|<span data-ttu-id="7daa5-128">IPv4 es opcional; el servidor intenta escuchar a IPv6 pero se inicia en caso de no poder hacerlo.</span><span class="sxs-lookup"><span data-stu-id="7daa5-128">IPv6 is optional; server tries to listen to IPv6 but starts even if unable to.</span></span>|  
  
 `MaxAllowedRequestSize`  
 <span data-ttu-id="7daa5-129">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-129">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RequestSizeThreshold`  
 <span data-ttu-id="7daa5-130">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-130">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerReceiveTimeout`  
 <span data-ttu-id="7daa5-131">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-131">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerSendTimeout`  
 <span data-ttu-id="7daa5-132">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-132">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="requests"></a><span data-ttu-id="7daa5-133">Requests</span><span class="sxs-lookup"><span data-stu-id="7daa5-133">Requests</span></span>  
 `EnableBinaryXML`  
 <span data-ttu-id="7daa5-134">Una propiedad booleana que especifica si el servidor reconoce el formato XML binario de las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="7daa5-134">A Boolean property that specifies whether the server will recognize requests binary xml format.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="7daa5-135">Una propiedad booleana que especifica si la compresión está habilitada para las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="7daa5-135">A Boolean property that specifies whether compression is enabled for requests.</span></span>  
  
## <a name="responses"></a><span data-ttu-id="7daa5-136">Respuestas</span><span class="sxs-lookup"><span data-stu-id="7daa5-136">Responses</span></span>  
 `CompressionLevel`  
 <span data-ttu-id="7daa5-137">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-137">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `EnableBinaryXML`  
 <span data-ttu-id="7daa5-138">Una propiedad booleana que especifica si el servidor está habilitado para respuestas XML binarias.</span><span class="sxs-lookup"><span data-stu-id="7daa5-138">A Boolean property that specifies whether the server is enabled for binary xml responses.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="7daa5-139">Una propiedad booleana que especifica si la compresión está habilitada para respuestas a solicitudes de cliente.</span><span class="sxs-lookup"><span data-stu-id="7daa5-139">A Boolean property that specifies whether compression is enabled for responses to client requests.</span></span>  
  
## <a name="tcp"></a><span data-ttu-id="7daa5-140">TCP</span><span class="sxs-lookup"><span data-stu-id="7daa5-140">TCP</span></span>  
 `InitialConnectTimeout`  
 <span data-ttu-id="7daa5-141">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxCompletedReceiveCount`  
 <span data-ttu-id="7daa5-142">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingAcceptExCount`  
 <span data-ttu-id="7daa5-143">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-143">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingReceiveCount`  
 <span data-ttu-id="7daa5-144">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingSendCount`  
 <span data-ttu-id="7daa5-145">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-145">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingAcceptExCount`  
 <span data-ttu-id="7daa5-146">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingReceiveCount`  
 <span data-ttu-id="7daa5-147">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ScatterReceiveMultiplier`  
 <span data-ttu-id="7daa5-148">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ DisableNonblockingMode`  
 <span data-ttu-id="7daa5-149">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ EnableLingerOnClose`  
 <span data-ttu-id="7daa5-150">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\EnableNagleAlgorithm`  
 <span data-ttu-id="7daa5-151">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ LingerTimeout`  
 <span data-ttu-id="7daa5-152">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ ReceiveBufferSize`  
 <span data-ttu-id="7daa5-153">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-153">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ SendBufferSize`  
 <span data-ttu-id="7daa5-154">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7daa5-154">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7daa5-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7daa5-155">See Also</span></span>  
 <span data-ttu-id="7daa5-156">[Configurar las propiedades del servidor en Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="7daa5-156">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="7daa5-157">Determinar el modo de servidor de una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7daa5-157">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
