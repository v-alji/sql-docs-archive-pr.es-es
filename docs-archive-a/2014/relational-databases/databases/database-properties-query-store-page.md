---
title: Propiedades de base de datos (página del Almacén de consultas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql13.swb.databaseproperties.querystore.f1
ms.assetid: da47d75e-291a-4305-acef-4b0aaf5215da
author: stevestein
ms.author: sstein
ms.openlocfilehash: bab0d9b697e9ad9ec4b27f320d26b9b9edb5944e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747020"
---
# <a name="database-properties-query-store-page"></a><span data-ttu-id="44bb9-102">Propiedades de base de datos (página del Almacén de consultas)</span><span class="sxs-lookup"><span data-stu-id="44bb9-102">Database Properties (Query Store Page)</span></span>
  <span data-ttu-id="44bb9-103">Obtenga acceso a esta página desde la base de datos principal y úsela para configurar y modificar las propiedades del almacén de consultas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44bb9-103">Access this page from the principal database, and use it to configure and to modify the properties of the database query store.</span></span> <span data-ttu-id="44bb9-104">Estas opciones también se pueden configurar mediante las [opciones ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="44bb9-104">These options can also be configure by using the [ALTER DATABASE SET options](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span> <span data-ttu-id="44bb9-105">Para información sobre el almacén de consultas, vea [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="44bb9-105">For information about the query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="44bb9-106">**Se aplica a**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44bb9-106">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span></span>|  
  
## <a name="options"></a><span data-ttu-id="44bb9-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="44bb9-107">Options</span></span>  
 <span data-ttu-id="44bb9-108">Habilitar</span><span class="sxs-lookup"><span data-stu-id="44bb9-108">Enable</span></span>  
 <span data-ttu-id="44bb9-109">Habilita y deshabilita el almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="44bb9-109">Enables and disables the query store.</span></span>  
  
 <span data-ttu-id="44bb9-110">Modo de operación</span><span class="sxs-lookup"><span data-stu-id="44bb9-110">Operation Mode</span></span>  
 <span data-ttu-id="44bb9-111">Los valores válidos son READ_ONLY y READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="44bb9-111">Valid values are READ_ONLY and READ_WRITE.</span></span> <span data-ttu-id="44bb9-112">En el modo READ_WRITE, el almacén de consultas recopila y continúa el plan de consultas y la información de estadística del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="44bb9-112">In READ_WRITE mode, the query store collects and persists query plan and runtime execution statistics information.</span></span> <span data-ttu-id="44bb9-113">En el modo READ_ONLY, la información se puede leer del almacén de consultas, pero no se agrega información nueva.</span><span class="sxs-lookup"><span data-stu-id="44bb9-113">In READ_ONLY mode, information can be read from the query store, but new information is not added.</span></span> <span data-ttu-id="44bb9-114">Si se ha agotado el espacio máximo del almacén de consultas, el almacén de consultas cambiará su modo de operación a READ_ONLY.</span><span class="sxs-lookup"><span data-stu-id="44bb9-114">If the maximum allocated space of the query store has been exhausted, the query store will change its operation mode to READ_ONLY.</span></span>  
  
 <span data-ttu-id="44bb9-115">Modo de operación (real)</span><span class="sxs-lookup"><span data-stu-id="44bb9-115">Operation Mode (Actual)</span></span>  
 <span data-ttu-id="44bb9-116">Obtiene el modo de operación real del almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="44bb9-116">Gets the actual operation mode of the query store.</span></span>  
  
 <span data-ttu-id="44bb9-117">Modo de operación (solicitado)</span><span class="sxs-lookup"><span data-stu-id="44bb9-117">Operation Mode (Requested)</span></span>  
 <span data-ttu-id="44bb9-118">Obtiene y establece el modo de operación que desea del almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="44bb9-118">Gets and sets the desired operation mode of the query store.</span></span>  
  
 <span data-ttu-id="44bb9-119">Intervalo del vaciado de datos (minutos)</span><span class="sxs-lookup"><span data-stu-id="44bb9-119">Data Flush Interval (Minutes)</span></span>  
 <span data-ttu-id="44bb9-120">Determina la frecuencia con la que los datos escritos en el almacén de consultas se conservan en el disco.</span><span class="sxs-lookup"><span data-stu-id="44bb9-120">Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="44bb9-121">Para optimizar el rendimiento, los datos recopilados por el almacén de consultas se escriben de manera asincrónica en el disco.</span><span class="sxs-lookup"><span data-stu-id="44bb9-121">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="44bb9-122">Se configura la frecuencia con la que se produce esta transferencia asincrónica.</span><span class="sxs-lookup"><span data-stu-id="44bb9-122">The frequency at which this asynchronous transfer occurs is configured.</span></span>  
  
 <span data-ttu-id="44bb9-123">Intervalo de la recopilación de estadísticas</span><span class="sxs-lookup"><span data-stu-id="44bb9-123">Statistics Collection Interval</span></span>  
 <span data-ttu-id="44bb9-124">Obtiene y establece el valor del intervalo de la recopilación de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="44bb9-124">Gets and sets the statistics collection interval value.</span></span>  
  
 <span data-ttu-id="44bb9-125">Tamaño máximo (MB)</span><span class="sxs-lookup"><span data-stu-id="44bb9-125">Max Size (MB)</span></span>  
 <span data-ttu-id="44bb9-126">Obtiene y establece el espacio asignado total al almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="44bb9-126">Gets and sets the total space allocated to the query store.</span></span>  
  
 <span data-ttu-id="44bb9-127">Umbral de consultas obsoletas (días)</span><span class="sxs-lookup"><span data-stu-id="44bb9-127">Stale Query Threshold (Days)</span></span>  
 <span data-ttu-id="44bb9-128">Obtiene y establece el umbral de consultas obsoletas.</span><span class="sxs-lookup"><span data-stu-id="44bb9-128">Gets and sets the stale query threshold.</span></span> <span data-ttu-id="44bb9-129">Configure el argumento STALE_QUERY_THRESHOLD_DAYS para especificar el número de días en que se conservarán los datos en el almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="44bb9-129">Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>  
  
 <span data-ttu-id="44bb9-130">Depurar datos de consulta</span><span class="sxs-lookup"><span data-stu-id="44bb9-130">Purge Query Data</span></span>  
 <span data-ttu-id="44bb9-131">Quita el contenido del almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="44bb9-131">Removes the contents of the query store.</span></span>  
  
 <span data-ttu-id="44bb9-132">Gráficos circulares</span><span class="sxs-lookup"><span data-stu-id="44bb9-132">Pie Charts</span></span>  
 <span data-ttu-id="44bb9-133">En el gráfico de la izquierda se muestra el consumo total del archivo de la base de datos en el disco y la parte del archivo que se rellena con los datos del almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="44bb9-133">The left chart shows the total database file consumption on the disk, and the portion of the file which is filled with the query store data.</span></span>  
  
 <span data-ttu-id="44bb9-134">En el gráfico de la derecha se muestra la parte de la cuota del almacén de consultas que se ha consumido actualmente.</span><span class="sxs-lookup"><span data-stu-id="44bb9-134">The right chart shows the portion of the query store quota which is currently used up.</span></span> <span data-ttu-id="44bb9-135">Observe que no se muestra la cuota en el gráfico de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="44bb9-135">Note that the quota is not shown in the left chart.</span></span> <span data-ttu-id="44bb9-136">La cuota puede superar el tamaño actual de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44bb9-136">The quota may exceed the current size of the database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44bb9-137">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44bb9-137">Remarks</span></span>  
 <span data-ttu-id="44bb9-138">La característica del almacén de consultas ofrece a los DBA conocimientos sobre el rendimiento y la elección del plan de consultas.</span><span class="sxs-lookup"><span data-stu-id="44bb9-138">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="44bb9-139">Esta característica simplifica la solución de problemas de rendimiento al permitirle encontrar rápidamente diferencias de rendimiento provocadas por cambios en los planes de consulta.</span><span class="sxs-lookup"><span data-stu-id="44bb9-139">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="44bb9-140">Captura automáticamente un historial de consultas, planes y estadísticas en tiempo de ejecución, y los conserva para su revisión.</span><span class="sxs-lookup"><span data-stu-id="44bb9-140">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="44bb9-141">Separa los datos por ventanas de tiempo, lo que permite ver patrones de uso la base de datos y comprender cuándo se produjeron cambios del plan de consultas en el servidor.</span><span class="sxs-lookup"><span data-stu-id="44bb9-141">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="44bb9-142">El almacén de consultas se puede configurar con esta página de propiedades de base de datos de almacén de consultas o mediante la opción [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="44bb9-142">The query store can be configured by using this query store database property page, or by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span> <span data-ttu-id="44bb9-143">El almacén de consultas presenta información mediante un cuadro de diálogo [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="44bb9-143">The query store presents information by using a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] dialog box.</span></span> <span data-ttu-id="44bb9-144">Para más información sobre el almacén de consultas, vea [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="44bb9-144">For more information about query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44bb9-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44bb9-145">See Also</span></span>  
 <span data-ttu-id="44bb9-146">[Query Store Stored Procedures &#40;Transact-SQL&#41; (Procedimientos almacenados del Almacén de consultas &#40;Transact-SQL&#41;)](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44bb9-146">[Query Store Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="44bb9-147">Query Store Catalog Views (Vistas de catálogo del almacén de consultas) &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="44bb9-147">Query Store Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/query-store-catalog-views-transact-sql)  
  
  
