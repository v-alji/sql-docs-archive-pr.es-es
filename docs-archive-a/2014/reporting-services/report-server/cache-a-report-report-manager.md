---
title: Almacenar en caché un informe (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- cache [Reporting Services]
- cached reports [Reporting Services]
- schedules [Reporting Services], report expiration
- expiration [Reporting Services]
ms.assetid: 723d1cb0-c2e7-4763-8690-a6a7a8bbbb90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e359e6c7a40b267979137ef2b3a285667a6fdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674604"
---
# <a name="cache-a-report-report-manager"></a><span data-ttu-id="6583d-102">Almacenar en caché un informe (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="6583d-102">Cache a Report (Report Manager)</span></span>
  <span data-ttu-id="6583d-103">Una manera de mejorar el rendimiento es configurar las propiedades de almacenamiento en caché para un informe.</span><span class="sxs-lookup"><span data-stu-id="6583d-103">One way to improve performance is to configure caching properties for a report.</span></span> <span data-ttu-id="6583d-104">Cuando un informe se almacena en memoria caché, se guarda una copia del informe representado durante un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="6583d-104">When a report is cached, a copy of the rendered report is saved for a short period of time.</span></span> <span data-ttu-id="6583d-105">El primer usuario que solicita el informe debe esperar para que se complete todo el procesamiento antes de ver el informe.</span><span class="sxs-lookup"><span data-stu-id="6583d-105">The first user who requests the report must wait for all processing to complete before viewing the report.</span></span> <span data-ttu-id="6583d-106">Los usuarios posteriores que soliciten el informe dentro del período de almacenamiento en caché pueden verlo de forma inmediata porque el procesamiento ya se ha producido.</span><span class="sxs-lookup"><span data-stu-id="6583d-106">Subsequent users who request the report within the caching period can view it right away because processing has already occurred.</span></span>  
  
 <span data-ttu-id="6583d-107">Hay restricciones en los tipos de informes que puede almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="6583d-107">There are restrictions on the types of reports that you can cache.</span></span> <span data-ttu-id="6583d-108">Por ejemplo, un informe no puede estar almacenado en memoria caché si el resultado del informe varía dependiendo de la identidad del usuario o si los datos se recuperan usando el token de seguridad del usuario que solicita el informe.</span><span class="sxs-lookup"><span data-stu-id="6583d-108">For example, a report cannot be cached if report output varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="6583d-109">Para más información, vea [Informes almacenados en caché &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6583d-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="6583d-110">Para programar la expiración de un informe en caché</span><span class="sxs-lookup"><span data-stu-id="6583d-110">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="6583d-111">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="6583d-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="6583d-112">En el Administrador de informes, navegue hasta la página **Contenido** .</span><span class="sxs-lookup"><span data-stu-id="6583d-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="6583d-113">Navegue hasta el informe para el que desea establecer propiedades de almacenando en memoria caché, mantenga el mouse sobre el elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6583d-113">Navigate to the report for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="6583d-114">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="6583d-114">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="6583d-115">En el marco izquierdo, haga clic en **Opciones de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="6583d-115">In the left frame, click the **Processing Options**.</span></span>  
  
5.  <span data-ttu-id="6583d-116">En la página, seleccione **Ejecutar este informe siempre con los datos más recientes**.</span><span class="sxs-lookup"><span data-stu-id="6583d-116">On the page, select **Always run this report with the most recent data**.</span></span>  
  
6.  <span data-ttu-id="6583d-117">Seleccione una de las siguientes dos opciones de caché y configure la expiración como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="6583d-117">Select one of the following two cache options and configure expiration as follows:</span></span>  
  
    -   <span data-ttu-id="6583d-118">Para configurar que una copia en caché expire después de un período determinado, haga clic en **Almacenar en caché una copia temporal del informe. La copia expirará después de un número determinado de minutos**.</span><span class="sxs-lookup"><span data-stu-id="6583d-118">To configure a cached copy to expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes**.</span></span> <span data-ttu-id="6583d-119">Escriba el número de minutos para la expiración del informe.</span><span class="sxs-lookup"><span data-stu-id="6583d-119">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="6583d-120">Para configurar que una copia en caché expire de acuerdo con una programación, haga clic en **Guardar en caché una copia temporal del informe. La copia del informe debe expirar según la siguiente programación.**</span><span class="sxs-lookup"><span data-stu-id="6583d-120">To configure a cached copy to expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="6583d-121">Haga clic en **Configurar**, o seleccione una programación compartida para controlar la expiración del informe.</span><span class="sxs-lookup"><span data-stu-id="6583d-121">Click **Configure**, or select a shared schedule to control report expiration</span></span>  
  
7.  <span data-ttu-id="6583d-122">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6583d-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6583d-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6583d-123">See Also</span></span>  
 <span data-ttu-id="6583d-124">[Establecer las propiedades del procesamiento de informes](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="6583d-124">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="6583d-125">Informes almacenados en caché &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6583d-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
