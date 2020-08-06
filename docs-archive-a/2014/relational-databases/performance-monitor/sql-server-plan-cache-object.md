---
title: Plan Cache (objeto de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Plan Cache object
- SQLServer:Plan Cache
ms.assetid: 225e2b02-8d2f-4f29-9eba-f5847c36ea99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 002cbe261c531c18bdbb2170da9694cc8abde89d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744660"
---
# <a name="sql-server-plan-cache-object"></a><span data-ttu-id="91e8e-102">Plan Cache (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91e8e-102">SQL Server, Plan Cache Object</span></span>
  <span data-ttu-id="91e8e-103">El objeto **Plan Cache** proporciona contadores para supervisar la forma en que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliza la memoria para almacenar objetos tales como procedimientos almacenados, instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc y preparadas, y desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="91e8e-103">The **Plan Cache** object provides counters to monitor how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses memory to store objects such as stored procedures, ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, and triggers.</span></span> <span data-ttu-id="91e8e-104">Se pueden supervisar simultáneamente múltiples instancias del objeto **Plan Cache** ; cada instancia representa un tipo distinto de plan para supervisar.</span><span class="sxs-lookup"><span data-stu-id="91e8e-104">Multiple instances of the **Plan Cache** object can be monitored at the same time, with each instance representing a different type of plan to monitor.</span></span>  
  
 <span data-ttu-id="91e8e-105">En esta tabla se describen los contadores de **SQLServer:Plan Cache**.</span><span class="sxs-lookup"><span data-stu-id="91e8e-105">This table describes are the **SQLServer:Plan Cache**counters.</span></span>  
  
|<span data-ttu-id="91e8e-106">Contadores de Plan Cache de SQL Server</span><span class="sxs-lookup"><span data-stu-id="91e8e-106">SQL Server Plan Cache counters</span></span>|<span data-ttu-id="91e8e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="91e8e-107">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="91e8e-108">**Frecuencia de aciertos de caché**</span><span class="sxs-lookup"><span data-stu-id="91e8e-108">**Cache Hit Ratio**</span></span>|<span data-ttu-id="91e8e-109">Proporción entre los aciertos de caché y las búsquedas.</span><span class="sxs-lookup"><span data-stu-id="91e8e-109">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="91e8e-110">**Recuentos de objetos de caché**</span><span class="sxs-lookup"><span data-stu-id="91e8e-110">**Cache Object Counts**</span></span>|<span data-ttu-id="91e8e-111">Número de objetos de caché que hay en la caché.</span><span class="sxs-lookup"><span data-stu-id="91e8e-111">Number of cache objects in the cache.</span></span>|  
|<span data-ttu-id="91e8e-112">**Páginas de caché**</span><span class="sxs-lookup"><span data-stu-id="91e8e-112">**Cache Pages**</span></span>|<span data-ttu-id="91e8e-113">Número de páginas de 8 KB utilizadas por los objetos de caché.</span><span class="sxs-lookup"><span data-stu-id="91e8e-113">Number of 8-kilobyte (KB) pages used by cache objects.</span></span>|  
|<span data-ttu-id="91e8e-114">**Objetos de caché en uso**</span><span class="sxs-lookup"><span data-stu-id="91e8e-114">**Cache Objects in use**</span></span>|<span data-ttu-id="91e8e-115">Número de objetos de caché que se están utilizando.</span><span class="sxs-lookup"><span data-stu-id="91e8e-115">Number of cache objects in use.</span></span>|  
  
 <span data-ttu-id="91e8e-116">Cada contador del objeto contiene las instancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="91e8e-116">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="91e8e-117">Instancia de Plan Cache</span><span class="sxs-lookup"><span data-stu-id="91e8e-117">Plan Cache instance</span></span>|<span data-ttu-id="91e8e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="91e8e-118">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="91e8e-119">**_Total**</span><span class="sxs-lookup"><span data-stu-id="91e8e-119">**_Total**</span></span>|<span data-ttu-id="91e8e-120">Información para todos los tipos de instancias de caché.</span><span class="sxs-lookup"><span data-stu-id="91e8e-120">Information for all types of cache instances.</span></span>|  
|<span data-ttu-id="91e8e-121">**Planes Sql**</span><span class="sxs-lookup"><span data-stu-id="91e8e-121">**Sql Plans**</span></span>|<span data-ttu-id="91e8e-122">Planes de consultas creados a partir de consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc, incluidas las consultas con parámetros, o a partir de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] preparadas mediante **sp_prepare** o **sp_cursorprepare**.</span><span class="sxs-lookup"><span data-stu-id="91e8e-122">Query plans produced from an ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] query, including auto-parameterized queries, or from [!INCLUDE[tsql](../../includes/tsql-md.md)] statements prepared using **sp_prepare** or **sp_cursorprepare**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="91e8e-123">almacena en caché los planes para las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc para su uso posterior si la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] idéntica se ejecuta más tarde.</span><span class="sxs-lookup"><span data-stu-id="91e8e-123">caches the plans for ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for later reuse if the identical [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is later executed.</span></span> <span data-ttu-id="91e8e-124">Las consultas con parámetros de usuario (aunque no se hayan preparado de manera explícita) también se supervisan como planes SQL preparados.</span><span class="sxs-lookup"><span data-stu-id="91e8e-124">User-parameterized queries (even if not explicitly prepared) are also monitored as Prepared SQL Plans.</span></span>|  
|<span data-ttu-id="91e8e-125">**Planes de objeto**</span><span class="sxs-lookup"><span data-stu-id="91e8e-125">**Object Plans**</span></span>|<span data-ttu-id="91e8e-126">Planes de consultas que se generan al crear un procedimiento almacenado, una función o un desencadenador.</span><span class="sxs-lookup"><span data-stu-id="91e8e-126">Query plans generated by creating a stored procedure, function, or trigger.</span></span>|  
|<span data-ttu-id="91e8e-127">**Árboles enlazados**</span><span class="sxs-lookup"><span data-stu-id="91e8e-127">**Bound Trees**</span></span>|<span data-ttu-id="91e8e-128">Árboles normalizados de vistas, reglas, columnas calculadas y restricciones de comprobación.</span><span class="sxs-lookup"><span data-stu-id="91e8e-128">Normalized trees for views, rules, computed columns, and check constraints.</span></span>|  
|<span data-ttu-id="91e8e-129">**Procedimientos almacenados extendidos**</span><span class="sxs-lookup"><span data-stu-id="91e8e-129">**Extended Stored Procedures**</span></span>|<span data-ttu-id="91e8e-130">Información de catálogo para los procedimientos almacenados extendidos.</span><span class="sxs-lookup"><span data-stu-id="91e8e-130">Catalog information for extended stores procedures.</span></span>|  
|<span data-ttu-id="91e8e-131">**Tablas temporales y variables de tabla**</span><span class="sxs-lookup"><span data-stu-id="91e8e-131">**Temporary Tables & Table Variables**</span></span>|<span data-ttu-id="91e8e-132">Información de caché relacionada con las tablas temporales y las variables de tabla.</span><span class="sxs-lookup"><span data-stu-id="91e8e-132">Cache information related to temporary tables and table variables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91e8e-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91e8e-133">See Also</span></span>  
 <span data-ttu-id="91e8e-134">[Opciones de configuración de memoria del servidor](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="91e8e-134">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="91e8e-135">[Buffer Manager (objeto de SQL Server)](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="91e8e-135">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="91e8e-136">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="91e8e-136">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
