---
title: Página de almacenamiento en caché, conjuntos de recursos compartidos (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eac372e9-d2a1-48a8-bbe5-09d101df16ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62d899964911a6f2d35e59d49d925ff80013af42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672805"
---
# <a name="caching-page-shared-datasets-report-manager"></a><span data-ttu-id="8ada3-102">Página de almacenamiento en caché, conjuntos de datos compartidos (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="8ada3-102">Caching Page, Shared Datasets (Report Manager)</span></span>
  <span data-ttu-id="8ada3-103">Use la página Propiedades de almacenamiento en caché para establecer las opciones de memoria caché de un conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="8ada3-103">Use the Caching properties page to set the cache options for a shared dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ada3-104">Esta característica no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ada3-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8ada3-105">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="8ada3-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="8ada3-106">Navegación</span><span class="sxs-lookup"><span data-stu-id="8ada3-106">Navigation</span></span>  
 <span data-ttu-id="8ada3-107">Use el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ada3-107">Use the following procedure to navigate to this location in the user interface.</span></span>  
  
### <a name="to-open-the-caching-properties-page-for-a-shared-dataset"></a><span data-ttu-id="8ada3-108">Para abrir la página Propiedades de almacenamiento en caché para un conjunto de datos compartido</span><span class="sxs-lookup"><span data-stu-id="8ada3-108">To open the Caching properties page for a shared dataset</span></span>  
  
1.  <span data-ttu-id="8ada3-109">Abra el Administrador de informes y busque el informe para el que desea configurar las propiedades del conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="8ada3-109">Open Report Manager, and locate the report for which you want to configure shared dataset properties.</span></span>  
  
2.  <span data-ttu-id="8ada3-110">Señale al conjunto de datos compartido y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8ada3-110">Point to the shared dataset, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="8ada3-111">En la lista desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="8ada3-111">In the drop-down list, click **Manage**.</span></span> <span data-ttu-id="8ada3-112">Se abrirá la página Propiedades generales correspondiente al informe.</span><span class="sxs-lookup"><span data-stu-id="8ada3-112">The General properties page for the report opens.</span></span>  
  
4.  <span data-ttu-id="8ada3-113">Haga clic en la pestaña de **almacenamiento en caché** .</span><span class="sxs-lookup"><span data-stu-id="8ada3-113">Click the **Caching** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8ada3-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="8ada3-114">Options</span></span>  
 <span data-ttu-id="8ada3-115">**Almacenar en caché conjunto de datos compartido**</span><span class="sxs-lookup"><span data-stu-id="8ada3-115">**Cache shared dataset**</span></span>  
 <span data-ttu-id="8ada3-116">Coloca una copia temporal de los datos en una memoria caché cuando un usuario abre por primera vez un informe que usa este conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="8ada3-116">Places a temporary copy of the data in a cache when a user first opens a report that uses this shared dataset.</span></span> <span data-ttu-id="8ada3-117">Los usuarios siguientes que ejecuten el informe dentro del período de almacenamiento en caché reciben la copia en caché de los datos.</span><span class="sxs-lookup"><span data-stu-id="8ada3-117">Subsequent users who run the report within the caching period receive the cached copy of the data.</span></span> <span data-ttu-id="8ada3-118">El almacenamiento en memoria caché suele mejorar el rendimiento porque los datos se devuelven desde la memoria caché en lugar de ejecutarse de nuevo la consulta del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="8ada3-118">Caching usually improves performance because the data is returned from the cache instead of running the dataset query again.</span></span>  
  
 <span data-ttu-id="8ada3-119">**Expirar la memoria caché después de este número de minutos**</span><span class="sxs-lookup"><span data-stu-id="8ada3-119">**Expire the cache after a number of minutes**</span></span>  
 <span data-ttu-id="8ada3-120">Especifique el número de minutos durante los que guardar la copia en caché de los datos.</span><span class="sxs-lookup"><span data-stu-id="8ada3-120">Specify the number of minutes to save the cached copy of the data.</span></span> <span data-ttu-id="8ada3-121">Tan pronto como expire una copia temporal, los datos ya no se devolverán de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8ada3-121">As soon as a temporary copy expires, the data is no longer returned from the cache.</span></span> <span data-ttu-id="8ada3-122">La próxima vez que un usuario abra un informe que use este conjunto de datos compartido, la consulta del conjunto de datos se ejecutará y el servidor de informes colocará de nuevo una copia de los datos actualizados en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8ada3-122">The next time a user opens a report that uses this shared dataset, the dataset query runs and the report server places a copy of the refreshed data back in the cache.</span></span>  
  
 <span data-ttu-id="8ada3-123">**Expirar la memoria caché según la siguiente programación.**</span><span class="sxs-lookup"><span data-stu-id="8ada3-123">**Expire the cache on the following schedule**</span></span>  
 <span data-ttu-id="8ada3-124">Programe el tiempo en el que los datos en caché dejarán de ser válidos y se quitarán de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8ada3-124">Schedule the time when the cached data is no longer valid and is removed from the cache.</span></span> <span data-ttu-id="8ada3-125">La programación puede ser compartida o puede ser una específica solamente para el conjunto de datos compartido actual.</span><span class="sxs-lookup"><span data-stu-id="8ada3-125">The schedule can be a shared schedule or one that is specific for only the current shared dataset.</span></span>  
  
 <span data-ttu-id="8ada3-126">**Programación específica del conjunto de datos**</span><span class="sxs-lookup"><span data-stu-id="8ada3-126">**Dataset-specific schedule**</span></span>  
 <span data-ttu-id="8ada3-127">Especifique una programación que solo use este conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="8ada3-127">Specify a schedule that is used only by this dataset.</span></span>  
  
 <span data-ttu-id="8ada3-128">**Programación compartida**</span><span class="sxs-lookup"><span data-stu-id="8ada3-128">**Shared schedule**</span></span>  
 <span data-ttu-id="8ada3-129">Especifique una programación que se comparta entre los informes, suscripciones y otros conjuntos de datos compartidos.</span><span class="sxs-lookup"><span data-stu-id="8ada3-129">Specify a schedule that is shared among reports, subscriptions, and other shared datasets.</span></span>  
  
 <span data-ttu-id="8ada3-130">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="8ada3-130">**Apply**</span></span>  
 <span data-ttu-id="8ada3-131">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="8ada3-131">Save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ada3-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ada3-132">See Also</span></span>  
 <span data-ttu-id="8ada3-133">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="8ada3-133">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="8ada3-134">[Administrador de informes la ayuda F1](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="8ada3-134">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="8ada3-135">[Almacenar en caché conjuntos de recursos compartidos &#40;SSRS&#41;](report-server/cache-shared-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8ada3-135">[Cache Shared Datasets &#40;SSRS&#41;](report-server/cache-shared-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="8ada3-136">Programaciones</span><span class="sxs-lookup"><span data-stu-id="8ada3-136">Schedules</span></span>](subscriptions/schedules.md)  
  
  
