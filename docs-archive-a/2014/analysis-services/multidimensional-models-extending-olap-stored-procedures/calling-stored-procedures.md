---
title: Llamar a procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- stored procedures [Analysis Services], calling
- MDX queries [Analysis Services]
- CALL statement
ms.assetid: 96a9660d-875b-4ee4-b339-90020b1d9895
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c9da6edef576a6ab25c183cbc87ff95cc056845
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746042"
---
# <a name="calling-stored-procedures"></a><span data-ttu-id="c70d0-102">Llamar a procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="c70d0-102">Calling Stored Procedures</span></span>
  <span data-ttu-id="c70d0-103">Se puede llamar a los procedimientos almacenados desde el servidor o desde la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="c70d0-103">Stored procedures can be called on the server or from client application.</span></span> <span data-ttu-id="c70d0-104">En cualquier caso, los procedimientos almacenados siempre se ejecutan en el servidor, ya sea en el contexto del servidor o de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="c70d0-104">In either case, stored procedures always run on the server, either the context of the server or of a database.</span></span> <span data-ttu-id="c70d0-105">No se requieren permisos específicos para ejecutar un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="c70d0-105">There are no special permissions required to execute a stored procedure.</span></span> <span data-ttu-id="c70d0-106">Cuando un ensamblado agrega un procedimiento almacenado al contexto del servidor o de la base de datos, cualquier usuario puede ejecutarlo, siempre que el rol del usuario permita las acciones que efectúa el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="c70d0-106">Once a stored procedure is added by an assembly to the server or database context, any user can execute the stored procedure as long as the role for the user permits the actions performed by the stored procedure.</span></span>  
  
 <span data-ttu-id="c70d0-107">La llamada a un procedimiento almacenado en MDX se realiza del mismo modo que la llamada a una función MDX intrínseca.</span><span class="sxs-lookup"><span data-stu-id="c70d0-107">Calling a stored procedure in MDX is done in the same manner as calling an intrinsic MDX function.</span></span> <span data-ttu-id="c70d0-108">Para un procedimiento almacenado que no toma parámetros, se utilizan el nombre del procedimiento y unos paréntesis vacíos, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="c70d0-108">For a stored procedure that takes no parameters, the name of the procedure and an empty pair of parentheses are used, as shown here:</span></span>  
  
```  
MyStoredProcedure()  
```  
  
 <span data-ttu-id="c70d0-109">Si el procedimiento almacenado toma uno o más parámetros, éstos se proporcionan por orden, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="c70d0-109">If the stored procedure takes one or more parameters, then the parameters are supplied, in order, separated by commas.</span></span> <span data-ttu-id="c70d0-110">En el siguiente ejemplo se muestra un ejemplo de procedimiento almacenado con tres parámetros:</span><span class="sxs-lookup"><span data-stu-id="c70d0-110">The following example demonstrates a sample stored procedure with three parameters:</span></span>  
  
```  
MyStoredProcedure("Parameter1", 2, 800)  
```  
  
## <a name="calling-stored-procedures-in-mdx-queries"></a><span data-ttu-id="c70d0-111">Llamar a procedimientos almacenados en consultas MDX</span><span class="sxs-lookup"><span data-stu-id="c70d0-111">Calling Stored Procedures in MDX Queries</span></span>  
 <span data-ttu-id="c70d0-112">En todas las consultas MDX, el procedimiento almacenado debe devolver el tipo sintácticamente correcto que requiere una expresión MDX.</span><span class="sxs-lookup"><span data-stu-id="c70d0-112">In all MDX queries, the stored procedure must return the syntactically correct type required by an MDX expression.</span></span> <span data-ttu-id="c70d0-113">Si un procedimiento almacenado no devuelve el tipo correcto, se produce un error de MDX.</span><span class="sxs-lookup"><span data-stu-id="c70d0-113">If a stored procedure does not return the correct type, an MDX error occurs.</span></span> <span data-ttu-id="c70d0-114">En los siguientes ejemplos se muestran procedimientos almacenados que devuelven un conjunto, un miembro y el resultado de una operación matemática.</span><span class="sxs-lookup"><span data-stu-id="c70d0-114">The following examples demonstrate stored procedures that return a set, a member, and the result of a mathematical operation.</span></span>  
  
### <a name="returning-a-set"></a><span data-ttu-id="c70d0-115">Devolver un conjunto</span><span class="sxs-lookup"><span data-stu-id="c70d0-115">Returning a Set</span></span>  
 <span data-ttu-id="c70d0-116">En los siguientes ejemplos se implementa un procedimiento almacenado llamado MySproc, que devuelve un conjunto.</span><span class="sxs-lookup"><span data-stu-id="c70d0-116">The following examples implement a stored procedure, called MySproc, that returns a set.</span></span> <span data-ttu-id="c70d0-117">En el primer ejemplo, MySproc devuelve el conjunto directamente en la expresión SELECT.</span><span class="sxs-lookup"><span data-stu-id="c70d0-117">In the first example, MySproc returns the set directly in the SELECT expression.</span></span> <span data-ttu-id="c70d0-118">En los dos ejemplos siguientes, MySproc devuelve el conjunto como argumento de las funciones Crossjoin y DrilldownLevel.</span><span class="sxs-lookup"><span data-stu-id="c70d0-118">In the second two examples, MySproc returns the set as an argument for the Crossjoin and DrilldownLevel functions.</span></span>  
  
```  
SELECT MySetProcedure(a,b,c) ON 0 FROM Sales  
SELECT Crossjoin(MySetProcedure(a,b,c)) ON 0 FROM Sales  
SELECT DrilldownLevel(MySetProcedure(a,b,c)) ON 0 FROM Sales  
```  
  
### <a name="returning-a-member"></a><span data-ttu-id="c70d0-119">Devolver un miembro</span><span class="sxs-lookup"><span data-stu-id="c70d0-119">Returning a Member</span></span>  
 <span data-ttu-id="c70d0-120">En el siguiente ejemplo se muestra una función MySproc que devuelve un miembro:</span><span class="sxs-lookup"><span data-stu-id="c70d0-120">The following example shows a function MySproc function that returns a member:</span></span>  
  
```  
SELECT Descendants(MySproc(a,b,c),3) ON 0 FROM Sales  
```  
  
### <a name="returning-the-result-of-a-math-operation"></a><span data-ttu-id="c70d0-121">Devolver el resultado de una operación matemática</span><span class="sxs-lookup"><span data-stu-id="c70d0-121">Returning the Result of a Math Operation</span></span>  
  
```  
SELECT Country.Members on 0, MySproc(Measures.Sales) ON 1 FROM Sales  
```  
  
## <a name="calling-stored-procedures-with-the-call-statement"></a><span data-ttu-id="c70d0-122">Llamar a procedimientos almacenados con la instrucción Call</span><span class="sxs-lookup"><span data-stu-id="c70d0-122">Calling Stored Procedures with the Call Statement</span></span>  
 <span data-ttu-id="c70d0-123">Se puede llamar a los procedimientos almacenados fuera del contexto de una consulta MDX mediante la instrucción `Call` de MDX.</span><span class="sxs-lookup"><span data-stu-id="c70d0-123">Stored procedures can be called outside of the context of an MDX query using the MDX `Call` statement.</span></span>  
  
 <span data-ttu-id="c70d0-124">Utilice este método para crear instancias de los efectos secundarios de una consulta almacenada o para que la aplicación obtenga los resultados de una consulta almacenada.</span><span class="sxs-lookup"><span data-stu-id="c70d0-124">You can use this method to either instantiate the side effects of a stored query or for the application to get the results of a stored query.</span></span> <span data-ttu-id="c70d0-125">Un uso común de la instrucción `Call` sería utilizar objetos de administración de análisis (AMO) para realizar funciones administrativas que no devuelven un resultado.</span><span class="sxs-lookup"><span data-stu-id="c70d0-125">A common use of the `Call` statement would be to use Analysis Management Objects (AMO) to perform administrative functions that do not have a return result.</span></span> <span data-ttu-id="c70d0-126">Por ejemplo, el comando siguiente llama a un procedimiento almacenado:</span><span class="sxs-lookup"><span data-stu-id="c70d0-126">For example, the following command calls a stored procedure:</span></span>  
  
```  
Call MyStoredProcedure(a,b,c)  
```  
  
 <span data-ttu-id="c70d0-127">El único tipo admitido que devuelve un procedimiento almacenado en una instrucción `Call` es un conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="c70d0-127">The only supported type returned from stored procedure in a `Call` statement is a rowset.</span></span> <span data-ttu-id="c70d0-128">La serialización para un conjunto de filas se define mediante XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="c70d0-128">The serialization for a rowset is defined by XML for Analysis.</span></span> <span data-ttu-id="c70d0-129">Si un procedimiento almacenado en una instrucción `Call` devuelve cualquier otro tipo, se omite y no se devuelve en XML a la aplicación que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="c70d0-129">If a stored procedure in a `Call` statement returns any other type, it is ignored and not returned in XML to the calling application.</span></span> <span data-ttu-id="c70d0-130">Para obtener más información acerca de los conjuntos de filas de XML for Analysis, vea el tema sobre conjuntos de filas del esquema de XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="c70d0-130">For more information about XML for Analysis rowsets, see, XML for Analysis Schema Rowsets.</span></span>  
  
 <span data-ttu-id="c70d0-131">Si un procedimiento almacenado devuelve un conjunto de filas de .NET, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] convierte el resultado en el servidor en un conjunto de filas de XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="c70d0-131">If a stored procedure returns a .NET rowset, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] converts the result on the server to an XML for Analysis rowset.</span></span> <span data-ttu-id="c70d0-132">Un procedimiento almacenado siempre devuelve el conjunto de filas de XML for Analysis de la función `Call`.</span><span class="sxs-lookup"><span data-stu-id="c70d0-132">The XML for Analysis rowset is always returned by a stored procedure in the `Call` function.</span></span> <span data-ttu-id="c70d0-133">Si un conjunto de datos contiene características que no se pueden expresar en el conjunto de filas de XML for Analysis, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="c70d0-133">If a dataset contains features that cannot be expressed in the XML for Analysis rowset, a failure results.</span></span>  
  
 <span data-ttu-id="c70d0-134">También se pueden utilizar procedimientos que devuelven valores nulos (por ejemplo, subrutinas de Visual Basic) con la palabra clave CALL.</span><span class="sxs-lookup"><span data-stu-id="c70d0-134">Procedures that return void values (for example, subroutines in Visual Basic) can also be employed with the CALL keyword.</span></span> <span data-ttu-id="c70d0-135">Por ejemplo, si desea utilizar la función MyVoidFunction() en una instrucción MDX, se utilizaría la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="c70d0-135">If, for example, you wanted to use the function MyVoidFunction() in an MDX statement, the following syntax would be employed:</span></span>  
  
```  
CALL(MyVoidFunction)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c70d0-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c70d0-136">See Also</span></span>  
 <span data-ttu-id="c70d0-137">[Administración de ensamblados de modelos multidimensionales](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="c70d0-137">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="c70d0-138">Definir procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="c70d0-138">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
