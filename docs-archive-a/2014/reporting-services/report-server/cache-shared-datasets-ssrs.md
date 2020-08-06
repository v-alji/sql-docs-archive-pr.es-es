---
title: Almacenar en caché conjuntos de datos compartidos (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4acb1bbe-1c04-4979-b893-dc1b1c5039b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5b08149b075ae3fd267baf2dad0ca342457958c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674608"
---
# <a name="cache-shared-datasets-ssrs"></a><span data-ttu-id="61aa0-102">Almacenar en caché conjuntos de datos compartidos (SSRS)</span><span class="sxs-lookup"><span data-stu-id="61aa0-102">Cache Shared Datasets (SSRS)</span></span>
  <span data-ttu-id="61aa0-103">Los resultados de las consultas para un conjunto de datos compartido se pueden copiar en una memoria caché para proporcionar datos coherentes a varios informes y mejorar el tiempo de respuesta de la consulta del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="61aa0-103">Query results for a shared dataset can be copied to a cache to provide consistent data for multiple reports and to improve response time for the dataset query.</span></span> <span data-ttu-id="61aa0-104">Al igual que los informes, puede configurar un conjunto de datos compartido que se va a almacenar en memoria caché al usarse por primera vez o especificando una programación.</span><span class="sxs-lookup"><span data-stu-id="61aa0-104">Like reports, you can configure a shared dataset to be cached on first use or by specifying a schedule.</span></span>  
  
 <span data-ttu-id="61aa0-105">Un conjunto de datos compartido puede estar incluido en varios informes o como parte de las definiciones de componentes.</span><span class="sxs-lookup"><span data-stu-id="61aa0-105">A shared dataset can be included in multiple reports or as part of component definitions.</span></span> <span data-ttu-id="61aa0-106">Al almacenar en memoria caché el conjunto de datos compartido, proporciona un conjunto coherente de datos para todos los informes que lo utilizan y también reduce el número de veces que la consulta del conjunto de datos se ejecuta con el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="61aa0-106">By caching the shared dataset, you provide a consistent set of data for all reports that use it, and also reduce the number of times that the dataset query runs against the external data source.</span></span>  
  
 <span data-ttu-id="61aa0-107">La siguiente lista proporciona ejemplos de cuándo almacenar en memoria caché un conjunto de datos compartido:</span><span class="sxs-lookup"><span data-stu-id="61aa0-107">The following list provides examples of when to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="61aa0-108">La consulta tarda bastante tiempo en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="61aa0-108">The query takes a substantial amount of time to run.</span></span>  
  
-   <span data-ttu-id="61aa0-109">La consulta acepta parámetros, pero el número de combinaciones de parámetros es pequeño la mayor parte del tiempo.</span><span class="sxs-lookup"><span data-stu-id="61aa0-109">The query takes parameters, but most of the time, the number of parameter combinations is small.</span></span> <span data-ttu-id="61aa0-110">Cada combinación crea resultados de la consulta almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="61aa0-110">Each combination creates cached query results.</span></span>  
  
-   <span data-ttu-id="61aa0-111">La consulta se ejecuta en momentos predecibles del día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="61aa0-111">The query runs at predictable times of the day, week, or month.</span></span>  
  
-   <span data-ttu-id="61aa0-112">La consulta se ejecuta como resultado de una referencia del conjunto de datos compartido en un informe que se entrega a través del correo electrónico, donde es probable que un número grande de personas haga clic en el vínculo en un breve intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="61aa0-112">The query runs as the result of a shared dataset reference in a report that is delivered via e-mail, where a large number of people are likely to click the link in a short span of time.</span></span>  
  
-   <span data-ttu-id="61aa0-113">La siguiente lista proporciona ejemplos de cuándo no almacenar en memoria caché un conjunto de datos compartido:</span><span class="sxs-lookup"><span data-stu-id="61aa0-113">The following list provides examples of when not to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="61aa0-114">Los resultados de la consulta siempre deben incluir los datos más recientes.</span><span class="sxs-lookup"><span data-stu-id="61aa0-114">The query results must always include the most recent data.</span></span>  
  
-   <span data-ttu-id="61aa0-115">La consulta se ejecuta rápidamente.</span><span class="sxs-lookup"><span data-stu-id="61aa0-115">The query runs quickly.</span></span>  
  
-   <span data-ttu-id="61aa0-116">La consulta se ejecuta con poca frecuencia.</span><span class="sxs-lookup"><span data-stu-id="61aa0-116">The query runs infrequently.</span></span>  
  
-   <span data-ttu-id="61aa0-117">La consulta acepta parámetros, el número de combinaciones de parámetros es grande y ninguna combinación es más probable que otra.</span><span class="sxs-lookup"><span data-stu-id="61aa0-117">The query takes parameters, the number of parameter combinations is large, and no combination is more likely than another.</span></span>  
  
-   <span data-ttu-id="61aa0-118">El origen de datos en el que se basa el conjunto de datos compartido tiene credenciales integradas de Windows o hay que proporcionarlas.</span><span class="sxs-lookup"><span data-stu-id="61aa0-118">The data source that the shared dataset is based on has Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="61aa0-119">El filtro del conjunto de datos compartido o la consulta contienen una expresión con una referencia al usuario de la colección global.</span><span class="sxs-lookup"><span data-stu-id="61aa0-119">The shared dataset filter or the query contains an expression with a reference to the global collection User.</span></span>  
  
 <span data-ttu-id="61aa0-120">Si un usuario elige valores para los parámetros de informe que difieren de los valores predeterminados que están especificados para el conjunto de resultados almacenado en memoria caché, la consulta del conjunto de datos se ejecuta activamente y los resultados almacenados en la memoria caché no se utilizan para esa consulta.</span><span class="sxs-lookup"><span data-stu-id="61aa0-120">If a user chooses report parameter values that differ from the default values that are specified for the cached result set, the dataset query runs actively and the cached results are not used for that query.</span></span>  
  
## <a name="caching-shared-datasets"></a><span data-ttu-id="61aa0-121">Almacenamiento en caché de conjuntos de datos compartido</span><span class="sxs-lookup"><span data-stu-id="61aa0-121">Caching Shared Datasets</span></span>  
 <span data-ttu-id="61aa0-122">Para habilitar el almacenamiento en caché para un conjunto de datos compartido, debe seleccionar la opción de memoria caché en el conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="61aa0-122">To enable caching for a shared dataset, you must select the cache option on the shared dataset.</span></span> <span data-ttu-id="61aa0-123">Una vez habilitado el almacenamiento en caché, los resultados de la consulta para un conjunto de datos compartido se copian en la memoria caché cuando se usan por primera vez.</span><span class="sxs-lookup"><span data-stu-id="61aa0-123">After caching is enabled, the query results for a shared dataset are copied to the cache on first use.</span></span> <span data-ttu-id="61aa0-124">Si el conjunto de datos compartido tiene parámetros, cada combinación de parámetros crea una nueva entrada en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="61aa0-124">If the shared dataset has parameters, each combination of parameters creates a new entry in the cache.</span></span>  
  
 <span data-ttu-id="61aa0-125">Mientras los resultados de la consulta para una combinación de parámetros concreta estén en la memoria caché, cada informe que se inicie para procesarse y que incluya una referencia al conjunto de datos compartido con esos valores de parámetros utilizará los datos de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="61aa0-125">While the query results for a specific parameter combination are in the cache, each report that is launched for processing and that includes a reference to the shared dataset with those parameter values will use the cached data.</span></span>  
  
 <span data-ttu-id="61aa0-126">Puede especificar cuánto tiempo se mantendrán los datos en la memoria caché antes de que expiren.</span><span class="sxs-lookup"><span data-stu-id="61aa0-126">You can specify how long to keep data in the cache before it expires.</span></span> <span data-ttu-id="61aa0-127">Para más información, vea [Página de almacenamiento en caché, conjuntos de datos compartidos &#40;Administrador de informes&#41;](../caching-page-shared-datasets-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="61aa0-127">For more information, see [Caching Page, Shared Datasets &#40;Report Manager&#41;](../caching-page-shared-datasets-report-manager.md).</span></span>  
  
## <a name="preloading-the-cache"></a><span data-ttu-id="61aa0-128">Cargar previamente la memoria caché</span><span class="sxs-lookup"><span data-stu-id="61aa0-128">Preloading the Cache</span></span>  
 <span data-ttu-id="61aa0-129">Puede cargar previamente la memoria caché creando un plan de actualización de caché.</span><span class="sxs-lookup"><span data-stu-id="61aa0-129">You can preload the cache by creating a cache refresh plan.</span></span> <span data-ttu-id="61aa0-130">Con un plan de actualización, puede especificar la frecuencia de la actualización de la memoria caché utilizando una programación específica de los elementos o una programación compartida.</span><span class="sxs-lookup"><span data-stu-id="61aa0-130">With a refresh plan, you can specify how often to refresh the cache by using an item-specific schedule or a shared schedule.</span></span> <span data-ttu-id="61aa0-131">Para evitar varias entradas en la memoria caché para el mismo elemento, la programación que especifique debería permitir suficiente tiempo para el procesamiento de las consultas en el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="61aa0-131">To avoid multiple cache entries for the same item, the schedule that you specify should allow enough time for query processing on the external data source.</span></span> <span data-ttu-id="61aa0-132">Por ejemplo, si la consulta tarda 20 minutos en ejecutarse, la programación de la actualización debería ser mayor de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="61aa0-132">For example, if the query takes 20 minutes to run, the refresh schedule should be greater than 20 minutes.</span></span> <span data-ttu-id="61aa0-133">Para obtener más información, vea [Schedules](../subscriptions/schedules.md).</span><span class="sxs-lookup"><span data-stu-id="61aa0-133">For more information, see [Schedules](../subscriptions/schedules.md).</span></span>  
  
 <span data-ttu-id="61aa0-134">Para crear un plan de actualización de caché para un conjunto de datos compartido, se aplican las siguientes condiciones.</span><span class="sxs-lookup"><span data-stu-id="61aa0-134">To create a cache refresh plan for a shared dataset, the following conditions apply.</span></span>  
  
-   <span data-ttu-id="61aa0-135">El conjunto de datos compartido se debe habilitar para el almacenamiento en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="61aa0-135">The shared dataset must be enabled for caching.</span></span>  
  
-   <span data-ttu-id="61aa0-136">El origen de datos compartido del que el conjunto de datos compartido depende no puede utilizar credenciales integradas de Windows ni credenciales que deban proporcionarse.</span><span class="sxs-lookup"><span data-stu-id="61aa0-136">The shared data source that the shared dataset depends on cannot use Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="61aa0-137">Si el conjunto de datos compartido tiene parámetros, debe especificar valores predeterminados estáticos para cada parámetro que no esté marcado como de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="61aa0-137">If the shared dataset has parameters, you must specify static default values for each parameter that is not marked read-only.</span></span> <span data-ttu-id="61aa0-138">Los parámetros de solo lectura siempre utilizarán el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="61aa0-138">Read-only parameters will always use the default value.</span></span> <span data-ttu-id="61aa0-139">Si desea almacenar en memoria caché un conjunto de datos compartido para varias combinaciones de parámetros, debe crear un plan de actualización de caché independiente para cada combinación de valores.</span><span class="sxs-lookup"><span data-stu-id="61aa0-139">To cache a shared dataset for multiple combinations of parameters, you must create a separate cache refresh plan for each combination of values.</span></span> <span data-ttu-id="61aa0-140">Los parámetros no pueden contener referencias a otros conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="61aa0-140">Parameters cannot contain references to other datasets.</span></span>  
  
-   <span data-ttu-id="61aa0-141">Cada plan de actualización de caché está asociado solo a un conjunto de datos compartido o informe.</span><span class="sxs-lookup"><span data-stu-id="61aa0-141">Each cache refresh plan is associated with only one shared dataset or report.</span></span>  
  
-   <span data-ttu-id="61aa0-142">Debe tener los permisos ReadPolicy y UpdatePolicy en el conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="61aa0-142">You must have ReadPolicy and UpdatePolicy permissions on the shared dataset.</span></span>  
  
 <span data-ttu-id="61aa0-143">Los planes de actualización de memoria caché se aplican a los conjuntos de datos compartidos y a los informes.</span><span class="sxs-lookup"><span data-stu-id="61aa0-143">Cache refresh plans apply to both shared datasets and reports.</span></span> <span data-ttu-id="61aa0-144">Para más información, vea [Opciones de actualización de memoria caché &#40;Administrador de informes&#41;](../cache-refresh-options-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="61aa0-144">For more information, see [Cache Refresh Options &#40;Report Manager&#41;](../cache-refresh-options-report-manager.md).</span></span>  
  
## <a name="conditions-that-cause-cache-expiration"></a><span data-ttu-id="61aa0-145">Situaciones que pueden provocar la expiración de la memoria caché</span><span class="sxs-lookup"><span data-stu-id="61aa0-145">Conditions that Cause Cache Expiration</span></span>  
 <span data-ttu-id="61aa0-146">Las siguientes condiciones pueden hacer que una memoria caché del conjunto de datos compartido deje de ser válida.</span><span class="sxs-lookup"><span data-stu-id="61aa0-146">The following conditions can cause a shared dataset cache to become not valid.</span></span>  
  
-   <span data-ttu-id="61aa0-147">Una condición de programación expira.</span><span class="sxs-lookup"><span data-stu-id="61aa0-147">A schedule condition expires.</span></span> <span data-ttu-id="61aa0-148">La memoria caché expira o llega la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="61aa0-148">The cache times out or the expiration time occurs.</span></span>  
  
-   <span data-ttu-id="61aa0-149">Se elimina una programación compartida.</span><span class="sxs-lookup"><span data-stu-id="61aa0-149">A shared schedule is deleted.</span></span>  
  
-   <span data-ttu-id="61aa0-150">Cambios en una programación compartida.</span><span class="sxs-lookup"><span data-stu-id="61aa0-150">Changes to a shared schedule.</span></span> <span data-ttu-id="61aa0-151">Las programaciones compartidas se pueden pausar, lo que también afecta al momento en que una memoria caché expira.</span><span class="sxs-lookup"><span data-stu-id="61aa0-151">Shared schedules can be paused, which also affects when a cache expires.</span></span>  
  
-   <span data-ttu-id="61aa0-152">La definición de la consulta para el conjunto de datos compartido cambia.</span><span class="sxs-lookup"><span data-stu-id="61aa0-152">The query definition for the shared dataset changes.</span></span>  
  
-   <span data-ttu-id="61aa0-153">Las credenciales del origen de datos compartido del que el conjunto de datos compartido depende cambian.</span><span class="sxs-lookup"><span data-stu-id="61aa0-153">The credentials for the shared data source that the shared dataset depends on change.</span></span>  
  
-   <span data-ttu-id="61aa0-154">Las opciones de memoria caché para el conjunto de datos compartido cambian.</span><span class="sxs-lookup"><span data-stu-id="61aa0-154">The cache options for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="61aa0-155">Los valores predeterminados para los parámetros de solo lectura para el conjunto de datos compartido cambian.</span><span class="sxs-lookup"><span data-stu-id="61aa0-155">The default values for read-only parameters for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="61aa0-156">Los filtros que forman parte de la definición del conjunto de datos compartido cambian.</span><span class="sxs-lookup"><span data-stu-id="61aa0-156">The filters that are part of the shared dataset definition change.</span></span>  
  
-   <span data-ttu-id="61aa0-157">El conjunto de datos compartido se elimina del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="61aa0-157">The shared dataset is deleted from the report server.</span></span> <span data-ttu-id="61aa0-158">Cuando se elimina un conjunto de datos compartido, también se eliminan las copias en caché asociadas y los planes de actualización de memoria caché.</span><span class="sxs-lookup"><span data-stu-id="61aa0-158">When a shared dataset is deleted, associated cached copies and cache refresh plans are also deleted.</span></span>  
  
 <span data-ttu-id="61aa0-159">Las actualizaciones de los planes de actualización de memoria caché para los conjuntos de datos compartidos no afectan a los informes que ya se estén procesando.</span><span class="sxs-lookup"><span data-stu-id="61aa0-159">Updates to cache refresh plans for shared datasets do not affect reports that are already being processed.</span></span> <span data-ttu-id="61aa0-160">La actualización de un plan de actualización de caché solo afecta a las versiones futuras de los informes que hagan referencia al conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="61aa0-160">Updating a cache refresh plan affects only future launches of reports that reference the shared dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61aa0-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61aa0-161">See Also</span></span>  
 [<span data-ttu-id="61aa0-162">Administración de conjuntos de datos compartidos</span><span class="sxs-lookup"><span data-stu-id="61aa0-162">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
