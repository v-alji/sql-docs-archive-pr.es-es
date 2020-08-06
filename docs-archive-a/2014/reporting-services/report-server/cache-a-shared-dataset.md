---
title: Almacenar en caché un conjunto de datos compartido | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c2d8c81a-da1e-4a8a-9845-fff9a0903d24
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d4757d82425368efcb6a0a555c6cfe1deacf48c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674603"
---
# <a name="cache-a-shared-dataset"></a><span data-ttu-id="b9e34-102">Almacenar en caché un conjunto de datos compartido</span><span class="sxs-lookup"><span data-stu-id="b9e34-102">Cache a Shared Dataset</span></span>
  <span data-ttu-id="b9e34-103">Una manera de mejorar el rendimiento es configurar las propiedades de almacenamiento en caché para un conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="b9e34-103">One way to improve performance is to configure caching properties for a shared dataset.</span></span> <span data-ttu-id="b9e34-104">Cuando un conjunto de datos compartido se almacena en memoria caché, se guarda una copia de los resultados de la consulta durante un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="b9e34-104">When a shared dataset is cached, a copy of the query results is saved for a specified period of time.</span></span> <span data-ttu-id="b9e34-105">El primer usuario que solicite un informe que utilice el conjunto de datos compartido debe esperar a que los resultados de la consulta y todo el procesamiento se completen antes de ver el informe.</span><span class="sxs-lookup"><span data-stu-id="b9e34-105">The first user who requests a report that uses the shared dataset must wait for the query results and all processing to complete before viewing the report.</span></span> <span data-ttu-id="b9e34-106">Los usuarios subsiguientes que solicitan el informe dentro del período de almacenamiento en caché experimentarán mejor rendimiento porque la consulta y el procesamiento ya se han producido.</span><span class="sxs-lookup"><span data-stu-id="b9e34-106">Subsequent users who request the report within the caching period will experience improved performance because the query and processing has already occurred.</span></span> <span data-ttu-id="b9e34-107">También puede especificar un plan de actualización de la memoria caché para ejecutar la consulta y almacenar en memoria caché los resultados hasta que expire la memoria caché especificada.</span><span class="sxs-lookup"><span data-stu-id="b9e34-107">You can also specify a cache refresh plan to run the query and cache the results until the specified cache expiration.</span></span>  
  
 <span data-ttu-id="b9e34-108">Los usuarios que ejecutan informes basados en un conjunto de datos compartido o los planes de actualización de la memoria caché crean la memoria caché de consulta y, en ambos casos, la memoria caché está disponible en función de sus opciones de expiración.</span><span class="sxs-lookup"><span data-stu-id="b9e34-108">Users running reports based on a shared dataset or cache refresh plans create the query cache and in both cases, the cache is available based on the cache expiration options.</span></span>  
  
 <span data-ttu-id="b9e34-109">Hay restricciones en los tipos de conjuntos de datos compartidos que puede almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b9e34-109">There are restrictions on the types of shared datasets that you can cache.</span></span> <span data-ttu-id="b9e34-110">Por ejemplo, los resultados de la consulta no pueden estar almacenados en memoria caché si los datos varían en función de la identidad del usuario o si los datos se recuperan usando el token de seguridad del usuario que solicita el informe.</span><span class="sxs-lookup"><span data-stu-id="b9e34-110">For example, the query results cannot be cached if the data varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="b9e34-111">Para más información, vea [Almacenar en caché conjuntos de datos compartidos &#40;SSRS&#41;](cache-shared-datasets-ssrs.md) e [Informes almacenados en caché &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b9e34-111">For more information, see [Cache Shared Datasets &#40;SSRS&#41;](cache-shared-datasets-ssrs.md) and [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="b9e34-112">Para programar la expiración de un informe en caché</span><span class="sxs-lookup"><span data-stu-id="b9e34-112">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="b9e34-113">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b9e34-113">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="b9e34-114">En el Administrador de informes, navegue al conjunto de datos compartidos para el que desea establecer propiedades de almacenamiento en caché, mantenga el mouse sobre el elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b9e34-114">In Report Manager, navigate to the shared dataset for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="b9e34-115">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="b9e34-115">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="b9e34-116">En el marco de la izquierda, haga clic en la pestaña **Almacenando en caché**.</span><span class="sxs-lookup"><span data-stu-id="b9e34-116">In the left frame, click **Caching**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b9e34-117">Si ve el error **Las credenciales usadas para ejecutar este conjunto de datos compartidos no están almacenadas**, la opción Almacenar en caché conjunto de datos compartido se deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="b9e34-117">If you see the error **Credentials used to run the shared dataset are not stored**, the cache shared dataset option will be disabled.</span></span> <span data-ttu-id="b9e34-118">Tiene que modificar el origen de datos para almacenar las credenciales o modificar el conjunto de datos compartido para utilizar un origen de datos diferente que almacene las credenciales.</span><span class="sxs-lookup"><span data-stu-id="b9e34-118">You need modify the data source to store credentials or modify the shared dataset to use a different data source that does store credentials.</span></span>  
  
5.  <span data-ttu-id="b9e34-119">Seleccione **Almacenar en caché conjunto de datos compartido**.</span><span class="sxs-lookup"><span data-stu-id="b9e34-119">Select **Cache share dataset**.</span></span>  
  
6.  <span data-ttu-id="b9e34-120">Seleccione la opción para que la memoria caché expire después de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="b9e34-120">Select the option to expire the cache after 30 minutes.</span></span> <span data-ttu-id="b9e34-121">También puede elegir que la memoria caché expire en una programación especificada.</span><span class="sxs-lookup"><span data-stu-id="b9e34-121">You can also choose for the cache to expire on a specified schedule.</span></span>  
  
7.  <span data-ttu-id="b9e34-122">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b9e34-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9e34-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9e34-123">See Also</span></span>  
 [<span data-ttu-id="b9e34-124">Administración de conjuntos de datos compartidos</span><span class="sxs-lookup"><span data-stu-id="b9e34-124">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
