---
title: Ejecutar procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- stored procedures [ODBC], running
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], executing
ms.assetid: 866b6dd3-2acd-4dfb-aeca-a0352b2d4c6a
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e5de6a9a13c95b417657a1d108403fa27abe34b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750845"
---
# <a name="running-stored-procedures"></a><span data-ttu-id="a01e1-102">Ejecutar procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="a01e1-102">Running Stored Procedures</span></span>
  <span data-ttu-id="a01e1-103">Un procedimiento almacenado es un objeto ejecutable almacenado en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="a01e1-103">A stored procedure is an executable object stored in a database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a01e1-104">admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a01e1-104">supports:</span></span>  
  
-   <span data-ttu-id="a01e1-105">Procedimientos almacenados:</span><span class="sxs-lookup"><span data-stu-id="a01e1-105">Stored procedures:</span></span>  
  
     <span data-ttu-id="a01e1-106">Una o más instrucciones SQL precompiladas en un procedimiento ejecutable único.</span><span class="sxs-lookup"><span data-stu-id="a01e1-106">One or more SQL statements precompiled into a single executable procedure.</span></span>  
  
-   <span data-ttu-id="a01e1-107">Procedimientos almacenados extendidos:</span><span class="sxs-lookup"><span data-stu-id="a01e1-107">Extended stored procedures:</span></span>  
  
     <span data-ttu-id="a01e1-108">Las bibliotecas de vínculos dinámicos (DLL) de C o C++ escritas en la API de Servicios abiertos de datos de SQL Server para los procedimientos almacenados extendidos.</span><span class="sxs-lookup"><span data-stu-id="a01e1-108">C or C++ dynamic-link libraries (DLL) written to the SQL Server Open Data Services API for extended stored procedures.</span></span> <span data-ttu-id="a01e1-109">La API de Servicios abiertos de datos amplía las capacidades de los procedimientos almacenados para incluir código C o C++.</span><span class="sxs-lookup"><span data-stu-id="a01e1-109">The Open Data Services API extends the capabilities of stored procedures to include C or C++ code.</span></span>  
  
 <span data-ttu-id="a01e1-110">Cuando se ejecutan instrucciones, llamar a un procedimiento almacenado en el origen de datos (en lugar de ejecutar o preparar directamente una instrucción en la aplicación cliente) puede proporcionar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a01e1-110">When executing statements, calling a stored procedure on the data source (instead of directly executing or preparing a statement in the client application) can provide:</span></span>  
  
-   <span data-ttu-id="a01e1-111">Rendimiento más alto</span><span class="sxs-lookup"><span data-stu-id="a01e1-111">Higher performance</span></span>  
  
     <span data-ttu-id="a01e1-112">Las instrucciones SQL se analizan y compilan cuando se crean los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="a01e1-112">SQL statements are parsed and compiled when procedures are created.</span></span> <span data-ttu-id="a01e1-113">Esta sobrecarga se reduce después cuando se ejecutan los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="a01e1-113">This overhead is then saved when the procedures are executed.</span></span>  
  
-   <span data-ttu-id="a01e1-114">Sobrecarga de red reducida</span><span class="sxs-lookup"><span data-stu-id="a01e1-114">Reduced network overhead</span></span>  
  
     <span data-ttu-id="a01e1-115">Ejecutar un procedimiento en lugar de enviar consultas complejas por la red puede reducir el tráfico de red.</span><span class="sxs-lookup"><span data-stu-id="a01e1-115">Executing a procedure instead of sending complex queries across the network can reduce network traffic.</span></span> <span data-ttu-id="a01e1-116">Si una aplicación ODBC utiliza la sintaxis ODBC {CALL} la sintaxis para ejecutar un procedimiento almacenado, el controlador ODBC realiza optimizaciones adicionales que eliminan la necesidad de convertir los datos de parámetros.</span><span class="sxs-lookup"><span data-stu-id="a01e1-116">If an ODBC application uses the ODBC { CALL } syntax to execute a stored procedure, the ODBC driver makes additional optimizations that eliminate the need to convert parameter data.</span></span>  
  
-   <span data-ttu-id="a01e1-117">Mayor coherencia </span><span class="sxs-lookup"><span data-stu-id="a01e1-117">Greater consistency</span></span>  
  
     <span data-ttu-id="a01e1-118">Si las reglas de una organización se implementan en un recurso central, como un procedimiento almacenado, se pueden codificar, probar y depurar una vez.</span><span class="sxs-lookup"><span data-stu-id="a01e1-118">If an organization's rules are implemented in a central resource, such as a stored procedure, they can be coded, tested, and debugged once.</span></span> <span data-ttu-id="a01e1-119">De esta forma, los programadores individuales pueden utilizar procedimientos almacenados probados en lugar de desarrollar sus propias implementaciones.</span><span class="sxs-lookup"><span data-stu-id="a01e1-119">Individual programmers can then use the tested stored procedures instead of developing their own implementations.</span></span>  
  
-   <span data-ttu-id="a01e1-120">Mayor precisión</span><span class="sxs-lookup"><span data-stu-id="a01e1-120">Greater accuracy</span></span>  
  
     <span data-ttu-id="a01e1-121">Dado que los procedimientos almacenados suelen estar desarrollados por programadores experimentados, tienden a ser más eficaces y a tener menos errores que el código desarrollado varias veces por programadores de diferentes niveles de competencia.</span><span class="sxs-lookup"><span data-stu-id="a01e1-121">Because stored procedures are usually developed by experienced programmers, they tend to be more efficient and have fewer errors than code developed multiple times by programmers of varying skill levels.</span></span>  
  
-   <span data-ttu-id="a01e1-122">Funcionalidad agregada</span><span class="sxs-lookup"><span data-stu-id="a01e1-122">Added functionality</span></span>  
  
     <span data-ttu-id="a01e1-123">Los procedimientos almacenados extendidos pueden utilizar las características de C y C++ disponibles en las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a01e1-123">Extended stored procedures can use C and C++ features not available in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="a01e1-124">Para obtener un ejemplo de cómo llamar a un procedimiento almacenado, vea [procesar códigos de retorno y parámetros de salida &#40;ODBC&#41;](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="a01e1-124">For an example of how to call a stored procedure, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a01e1-125">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a01e1-125">In This Section</span></span>  
  
-   [<span data-ttu-id="a01e1-126">Llamar a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="a01e1-126">Calling a Stored Procedure</span></span>](calling-a-stored-procedure.md)  
  
-   [<span data-ttu-id="a01e1-127">Procesar por lotes las llamadas a procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="a01e1-127">Batching Stored Procedure Calls</span></span>](batching-stored-procedure-calls.md)  
  
-   [<span data-ttu-id="a01e1-128">Procesar resultados de procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="a01e1-128">Processing Stored Procedure Results</span></span>](processing-stored-procedure-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="a01e1-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a01e1-129">See Also</span></span>  
 <span data-ttu-id="a01e1-130">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="a01e1-130">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="a01e1-131">Temas de procedimientos de ejecución de procedimientos almacenados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a01e1-131">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
  
