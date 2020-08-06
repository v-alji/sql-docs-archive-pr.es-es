---
title: Análisis de flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5654cb30-cad2-470c-97b3-59cb331033e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 184b53d3e982cd80d7c9c0909538a751585ae21d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670523"
---
# <a name="analysis-of-data-flow"></a><span data-ttu-id="6b558-102">Análisis de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="6b558-102">Analysis of Data Flow</span></span>
  <span data-ttu-id="6b558-103">Puede utilizar la [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md) `SSISDB` vista de base de datos para analizar el flujo de datos de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="6b558-103">You can use the [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md)`SSISDB` database view to analyze the data flow of packages.</span></span> <span data-ttu-id="6b558-104">Esta vista muestra una fila cada vez que un componente de flujo de datos envía datos a un componente de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="6b558-104">This view displays a row each time a data flow component sends data to a downstream component.</span></span> <span data-ttu-id="6b558-105">La información se puede utilizar para obtener una descripción más profunda de las filas que se envían a cada componente.</span><span class="sxs-lookup"><span data-stu-id="6b558-105">The information can be used to gain a deeper understanding of the rows that are sent to each component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b558-106">El nivel de registro se debe establecer en **Verbose** para capturar información en la vista catalog.execution_data_statistics.</span><span class="sxs-lookup"><span data-stu-id="6b558-106">The logging level must be set to **Verbose** in order to capture information with the catalog.execution_data_statistics view.</span></span>  
  
 <span data-ttu-id="6b558-107">El ejemplo siguiente muestra el número de filas enviadas entre los componentes de un paquete.</span><span class="sxs-lookup"><span data-stu-id="6b558-107">The following example displays the number of rows sent between components of a package.</span></span>  
  
```  
use SSISDB  
select package_name, task_name, source_component_name, destination_component_name, rows_sent  
from catalog.execution_data_statistics  
where execution_id = 132  
order by source_component_name, destination_component_name  
  
```  
  
 <span data-ttu-id="6b558-108">El ejemplo siguiente se calcula el número de filas por milisegundo enviadas por cada componente de una ejecución concreta.</span><span class="sxs-lookup"><span data-stu-id="6b558-108">The following example calculates the number of rows per millisecond sent by each component for a specific execution.</span></span> <span data-ttu-id="6b558-109">Los valores calculados son:</span><span class="sxs-lookup"><span data-stu-id="6b558-109">The calculated values are:</span></span>  
  
-   <span data-ttu-id="6b558-110">**total_rows** : suma de todas las filas enviadas por el componente.</span><span class="sxs-lookup"><span data-stu-id="6b558-110">**total_rows** - the sum of all the rows sent by the component</span></span>  
  
-   <span data-ttu-id="6b558-111">**wall_clock_time_ms**: tiempo de ejecución total transcurrido, en milisegundos, para cada componente.</span><span class="sxs-lookup"><span data-stu-id="6b558-111">**wall_clock_time_ms** - the total elapsed execution time, in milliseconds, for each component</span></span>  
  
-   <span data-ttu-id="6b558-112">**num_rows_per_millisecond**: número de filas por milisegundo enviadas por cada componente.</span><span class="sxs-lookup"><span data-stu-id="6b558-112">**num_rows_per_millisecond** - the number of rows per millisecond sent by each component</span></span>  
  
 <span data-ttu-id="6b558-113">La `HAVING` cláusula se usa para evitar un error de división por cero en los cálculos.</span><span class="sxs-lookup"><span data-stu-id="6b558-113">The `HAVING` clause is used to prevent a divide-by-zero error in the calculations.</span></span>  
  
```  
use SSISDB  
select source_component_name, destination_component_name,  
    sum(rows_sent) as total_rows,  
    DATEDIFF(ms,min(created_time),max(created_time)) as wall_clock_time_ms,  
    ((0.0+sum(rows_sent)) / (datediff(ms,min(created_time),max(created_time)))) as [num_rows_per_millisecond]  
from [catalog].[execution_data_statistics]  
where execution_id = 132  
group by source_component_name, destination_component_name  
having (datediff(ms,min(created_time),max(created_time))) > 0  
order by source_component_name desc  
  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="6b558-114">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6b558-114">Related Tasks</span></span>  
 [<span data-ttu-id="6b558-115">Depurar el flujo de datos</span><span class="sxs-lookup"><span data-stu-id="6b558-115">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="6b558-116">Herramientas para solucionar problemas de la ejecución de paquetes</span><span class="sxs-lookup"><span data-stu-id="6b558-116">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
## <a name="see-also"></a><span data-ttu-id="6b558-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b558-117">See Also</span></span>  
 [<span data-ttu-id="6b558-118">Datos de flujos de datos</span><span class="sxs-lookup"><span data-stu-id="6b558-118">Data in Data Flows</span></span>](data-flow/data-in-data-flows.md)  
  
  
