---
title: Procedimientos recomendados para llamar a procedimientos almacenados compilados de forma nativa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f39fc1c7-cfec-4a95-97f6-6b95954694bb
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d07d0e290d1fbd9b324235e64734a399bf7801d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663469"
---
# <a name="best-practices-for-calling-natively-compiled-stored-procedures"></a><span data-ttu-id="ad821-102">Prácticas recomendadas para llamar a un procedimiento almacenado compilado de forma nativa</span><span class="sxs-lookup"><span data-stu-id="ad821-102">Best Practices for Calling Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="ad821-103">Los procedimientos almacenados compilados de forma nativa:</span><span class="sxs-lookup"><span data-stu-id="ad821-103">Natively compiled stored procedures are:</span></span>  
  
-   <span data-ttu-id="ad821-104">Se suelen usar en componentes esenciales para el rendimiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ad821-104">Used typically in performance-critical parts of an application.</span></span>  
  
-   <span data-ttu-id="ad821-105">Se ejecutan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="ad821-105">Frequently executed.</span></span>  
  
-   <span data-ttu-id="ad821-106">Se espera que sean muy rápidos.</span><span class="sxs-lookup"><span data-stu-id="ad821-106">Expected to be very fast.</span></span>  
  
 <span data-ttu-id="ad821-107">La ventaja de rendimiento que supone emplear un procedimiento almacenado compilado de forma nativa aumenta con el número de filas y la cantidad de lógica que procesa el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ad821-107">The performance benefit of using a natively compiled stored procedure increases with the number of rows and the amount of logic that is processed by the procedure.</span></span> <span data-ttu-id="ad821-108">Por ejemplo, un procedimiento almacenado compilado de forma nativa tendrá mejor rendimiento si usa uno o varios de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad821-108">For example, a natively compiled stored procedure will exhibit better performance if it uses one or more of the following:</span></span>  
  
-   <span data-ttu-id="ad821-109">Agregación.</span><span class="sxs-lookup"><span data-stu-id="ad821-109">Aggregation.</span></span>  
  
-   <span data-ttu-id="ad821-110">Combinaciones de bucles anidados.</span><span class="sxs-lookup"><span data-stu-id="ad821-110">Nested-loops joins.</span></span>  
  
-   <span data-ttu-id="ad821-111">Operaciones de inserción, actualización y eliminación de varias instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ad821-111">Multi-statement select, insert, update, and delete operations.</span></span>  
  
-   <span data-ttu-id="ad821-112">Expresiones complejas.</span><span class="sxs-lookup"><span data-stu-id="ad821-112">Complex expressions.</span></span>  
  
-   <span data-ttu-id="ad821-113">Lógica de procedimientos, como instrucciones condicionales y bucles.</span><span class="sxs-lookup"><span data-stu-id="ad821-113">Procedural logic, such as conditional statements and loops.</span></span>  
  
 <span data-ttu-id="ad821-114">Si solo necesita procesar una única fila, el uso de un procedimiento almacenado compilado de forma nativa quizás no proporcione ventajas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ad821-114">If you need to process only a single row, using a natively compiled stored procedure may not provide a performance benefit.</span></span>  
  
 <span data-ttu-id="ad821-115">Para evitar que el servidor tenga que asignar nombres de parámetro y convertir tipos:</span><span class="sxs-lookup"><span data-stu-id="ad821-115">To avoid the server having to map parameter names and convert types:</span></span>  
  
-   <span data-ttu-id="ad821-116">Haga corresponder los tipos de parámetros pasados al procedimiento con los tipos de la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ad821-116">Match the types of the parameters passed to the procedure with the types in the procedure definition.</span></span>  
  
-   <span data-ttu-id="ad821-117">Use parámetros ordinales (anónimos) cuando llame a procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="ad821-117">Use ordinal (nameless) parameters when calling natively compiled stored procedures.</span></span> <span data-ttu-id="ad821-118">Para que la ejecución sea más eficaz, no utilice parámetros con nombre.</span><span class="sxs-lookup"><span data-stu-id="ad821-118">For the most efficient execution, do not use named parameters.</span></span>  
  
 <span data-ttu-id="ad821-119">El uso de parámetros con nombre (ineficaces) con procedimientos almacenados compilados de forma nativa se puede detectar con el XEvent `hekaton_slow_parameter_passing`, con `reason=named_parameters`.</span><span class="sxs-lookup"><span data-stu-id="ad821-119">Use of (inefficient) named parameters with natively compiled stored procedures can be detected through the XEvent `hekaton_slow_parameter_passing`, with `reason=named_parameters`.</span></span>  
  
 <span data-ttu-id="ad821-120">Asimismo, puede detectar el uso de tipos no coincidentes a través del mismo XEvent `hekaton_slow_parameter_passing`, con `reason=parameter_conversion`.</span><span class="sxs-lookup"><span data-stu-id="ad821-120">Similarly, you can detect use of mismatched types through the same XEvent `hekaton_slow_parameter_passing`, with `reason=parameter_conversion`.</span></span>  
  
 <span data-ttu-id="ad821-121">Puesto que necesitará implementar lógica de reintentos cuando use tablas optimizadas para memoria (en varios escenarios), y como necesitará evitar ciertas limitaciones de la característica, puede ser conveniente crear un procedimiento almacenado de [!INCLUDE[tsql](../../includes/tsql-md.md)] interpretado por el contenedor.</span><span class="sxs-lookup"><span data-stu-id="ad821-121">Because you will need to implement retry logic when using memory-optimized tables (in many scenarios), and because you will need to work around certain feature limitations, you may want to create a wrapper interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure.</span></span> <span data-ttu-id="ad821-122">Para obtener un ejemplo, vea [instrucciones para la lógica de reintento para las transacciones en tablas optimizadas para memoria](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ad821-122">For an example, see [Guidelines for Retry Logic for Transactions on Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad821-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad821-123">See Also</span></span>  
 [<span data-ttu-id="ad821-124">Procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="ad821-124">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
