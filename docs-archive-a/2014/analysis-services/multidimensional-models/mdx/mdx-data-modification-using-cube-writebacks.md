---
title: Usar reescrituras de cubos (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- writeback [Analysis Services], cubes
- cubes [Analysis Services], modifying
- modifying cubes
- UPDATE CUBE statement
- cubes [Analysis Services], writeback
ms.assetid: ae2385fc-7fa0-4f8e-98d7-dcb0a5f0eeea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3ac43e9206619117c1fc090a594ca32ccbeeeb31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671730"
---
# <a name="using-cube-writebacks-mdx"></a><span data-ttu-id="118f2-102">Usar reescrituras de cubos (MDX)</span><span class="sxs-lookup"><span data-stu-id="118f2-102">Using Cube Writebacks (MDX)</span></span>
  <span data-ttu-id="118f2-103">Los cubos pueden actualizarse mediante la instrucción [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) .</span><span class="sxs-lookup"><span data-stu-id="118f2-103">You update a cube by using the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement.</span></span> <span data-ttu-id="118f2-104">Esta instrucción permite actualizar una tupla con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="118f2-104">This statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="118f2-105">Para utilizar de forma eficaz la instrucción UPDATE CUBE a fin de actualizar, un cubo es preciso comprender la sintaxis de la instrucción, las condiciones de error que pueden generarse y el efecto de las actualizaciones en el cubo.</span><span class="sxs-lookup"><span data-stu-id="118f2-105">To effectively use the UPDATE CUBE statement to update a cube, you have to understand the syntax for the statement, the error conditions that can occur, and the affect that updates can have on a cube.</span></span>  
  
## <a name="update-cube-statement-syntax"></a><span data-ttu-id="118f2-106">Sintaxis de la instrucción UPDATE CUBE</span><span class="sxs-lookup"><span data-stu-id="118f2-106">UPDATE CUBE Statement Syntax</span></span>  
 <span data-ttu-id="118f2-107">La siguiente sintaxis describe la instrucción UPDATE CUBE:</span><span class="sxs-lookup"><span data-stu-id="118f2-107">The following syntax describes the UPDATE CUBE statement:</span></span>  
  
```  
UPDATE [CUBE] <Cube_Name> SET <tuple>.VALUE = <value> [,<tuple>.VALUE = <value>...]  
 [ USE_EQUAL_ALLOCATION | USE_EQUAL_INCREMENT |  
  USE_WEIGHTED_ALLOCATION [BY <weight value_expression>] |  
  USE_WEIGHTED_INCREMENT [BY <weight value_expression>] ]   
```  
  
 <span data-ttu-id="118f2-108">Si no se especifica un conjunto completo de coordenadas para la tupla, las que no se hayan especificado usarán el miembro predeterminado de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="118f2-108">If a full set of coordinates is not specified for the tuple, the unspecified coordinates will use the default member of the hierarchy.</span></span> <span data-ttu-id="118f2-109">La tupla identificada debe hacer referencia a una celda agregada con la función [Sum](/sql/mdx/sum-mdx) y no debe utilizar ningún miembro calculado como una de las coordenadas de la celda.</span><span class="sxs-lookup"><span data-stu-id="118f2-109">The tuple identified must reference a cell that is aggregated with the [Sum](/sql/mdx/sum-mdx) function, and must not use a calculated member as one of the cell's coordinates.</span></span>  
  
 <span data-ttu-id="118f2-110">Podría decirse que la instrucción UPDATE CUBE es una subrutina que genera una serie de operaciones de reescritura individuales en celdas atómicas.</span><span class="sxs-lookup"><span data-stu-id="118f2-110">You can think of the UPDATE CUBE statement as a subroutine that generates a series of individual writeback operations to atomic cells.</span></span> <span data-ttu-id="118f2-111">Todas estas operaciones de reescritura individuales se acumulan después en la suma especificada.</span><span class="sxs-lookup"><span data-stu-id="118f2-111">All these individual writeback operations then roll up into the specified sum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="118f2-112">Si las celdas actualizadas no se superponen, se puede utilizar la propiedad de la cadena de conexión `Update Isolation Level` para mejorar el rendimiento de UPDATE CUBE.</span><span class="sxs-lookup"><span data-stu-id="118f2-112">When updated cells do not overlap, the `Update Isolation Level` connection string property can be used to enhance performance for UPDATE CUBE.</span></span> <span data-ttu-id="118f2-113">Para obtener más información, vea <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="118f2-113">For more information, see <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="118f2-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="118f2-114">Example</span></span>  
 <span data-ttu-id="118f2-115">Puede probar UPDATE CUBE con el grupo de medida Sales Targets del cubo Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="118f2-115">You can test UPDATE CUBE using the Sales Targets measure group in the Adventure Works cube.</span></span> <span data-ttu-id="118f2-116">Este grupo de medida consta de las medidas agregadas mediante SUM, que es un requisito de UPDATE CUBE.</span><span class="sxs-lookup"><span data-stu-id="118f2-116">This measure group consists of measures aggregated by SUM, which is a requirement for UPDATE CUBE.</span></span>  
  
1.  <span data-ttu-id="118f2-117">Habilite la reescritura para el grupo de medida Sales Targets de la base de datos Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="118f2-117">Enable writeback for the Sales Targets measure group in the Adventure Works database.</span></span> <span data-ttu-id="118f2-118">En Management Studio, haga clic con el botón derecho en un grupo de medida, elija **Opciones de reescritura**y, después, elija **Habilitar reescritura**.</span><span class="sxs-lookup"><span data-stu-id="118f2-118">In Management Studio, right-click a measure group, point to **Write Back Options**, choose **Enable Writeback**.</span></span>  
  
     <span data-ttu-id="118f2-119">Debe ver una nueva tabla de reescritura en la carpeta Writeback.</span><span class="sxs-lookup"><span data-stu-id="118f2-119">You should see a new writeback table in the Writeback folder.</span></span> <span data-ttu-id="118f2-120">El nombre de la tabla es WriteTable_Fact Sales Quota.</span><span class="sxs-lookup"><span data-stu-id="118f2-120">The table name is WriteTable_Fact Sales Quota.</span></span>  
  
2.  <span data-ttu-id="118f2-121">Abra una ventana de consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="118f2-121">Open an MDX query window.</span></span> <span data-ttu-id="118f2-122">Ejecute la instrucción SELECT siguiente para ver el valor original:</span><span class="sxs-lookup"><span data-stu-id="118f2-122">Run the following select statement to view the original value:</span></span>  
  
    ```  
    SELECT [Measures].[Sales Amount Quota] on 0 ,  
    [Employee].[Employee Department].[Title].&[Sales Representative].children on 1  
    FROM [Adventure Works]  
  
    ```  
  
     <span data-ttu-id="118f2-123">Debe ver las cuotas de importe de venta para cada representante.</span><span class="sxs-lookup"><span data-stu-id="118f2-123">You should see sales amount quotas for each representative.</span></span>  
  
3.  <span data-ttu-id="118f2-124">Ejecute la instrucción UPDATE CUBE para reescribir un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="118f2-124">Run the update cube statement to write back a new value.</span></span> <span data-ttu-id="118f2-125">En este ejemplo, estamos estableciendo la cuota de importe de venta en 0.</span><span class="sxs-lookup"><span data-stu-id="118f2-125">In this example, we are setting the sales amount quota to 0.</span></span> <span data-ttu-id="118f2-126">Como el nuevo valor es 0, no especifique ningún método de asignación.</span><span class="sxs-lookup"><span data-stu-id="118f2-126">Because the new value is 0, do not specify an allocation method.</span></span>  
  
    ```  
    UPDATE CUBE [Adventure Works]   
    SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 0  
  
    ```  
  
4.  <span data-ttu-id="118f2-127">Vuelva a ejecutar la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="118f2-127">Re-run the SELECT statement.</span></span> <span data-ttu-id="118f2-128">Ahora debe ver cero para las cuotas.</span><span class="sxs-lookup"><span data-stu-id="118f2-128">You should now see zero for the quotas.</span></span>  
  
 <span data-ttu-id="118f2-129">El valor de reescritura está limitado a la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="118f2-129">The writeback value is constrained to the current session.</span></span> <span data-ttu-id="118f2-130">Para conservar el valor entre distintos usuarios y sesiones, procese la tabla de reescritura.</span><span class="sxs-lookup"><span data-stu-id="118f2-130">To persist the value across users and sessions, process the writeback table.</span></span> <span data-ttu-id="118f2-131">En Management Studio, haga clic con el botón derecho en WriteTable_Fact Sales Quota y elija **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="118f2-131">In Management Studio, right-click WriteTable_Fact Sales Quota and choose **Process**.</span></span>  
  
 <span data-ttu-id="118f2-132">Para especificar un método de asignación, el nuevo valor debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="118f2-132">To specify an allocation method, the new value must be greater than zero.</span></span> <span data-ttu-id="118f2-133">En este ejemplo, el nuevo valor de Sales Amount Quota es dos millones y el método de asignación distribuye la cantidad entre todos los representantes de ventas.</span><span class="sxs-lookup"><span data-stu-id="118f2-133">In this example, the new value for Sales Amount Quota is two million and the allocation method distributes the amount across all sales representatives.</span></span>  
  
```  
UPDATE CUBE [Adventure Works]   
SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 2000000   
USE_EQUAL_ALLOCATION  
```  
  
## <a name="error-conditions"></a><span data-ttu-id="118f2-134">Condiciones de error</span><span class="sxs-lookup"><span data-stu-id="118f2-134">Error Conditions</span></span>  
 <span data-ttu-id="118f2-135">En la siguiente tabla se describe lo que puede hacer que una operación de reescritura genere un error y el resultado de tales errores.</span><span class="sxs-lookup"><span data-stu-id="118f2-135">The following table describes both what can cause writebacks to fail and the result of those errors.</span></span>  
  
|<span data-ttu-id="118f2-136">Condición de error</span><span class="sxs-lookup"><span data-stu-id="118f2-136">Error Condition</span></span>|<span data-ttu-id="118f2-137">Resultado</span><span class="sxs-lookup"><span data-stu-id="118f2-137">Result</span></span>|  
|---------------------|------------|  
|<span data-ttu-id="118f2-138">La actualización incluye miembros de la misma dimensión que no pueden coexistir.</span><span class="sxs-lookup"><span data-stu-id="118f2-138">Update includes members from the same dimension that do not exist with one another.</span></span>|<span data-ttu-id="118f2-139">La actualización generará un error.</span><span class="sxs-lookup"><span data-stu-id="118f2-139">Update will fail.</span></span> <span data-ttu-id="118f2-140">El espacio del cubo no contendrá la celda a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="118f2-140">The cube space will not contain the referenced cell.</span></span>|  
|<span data-ttu-id="118f2-141">La actualización incluye una medida con origen en una medida de un tipo sin signo.</span><span class="sxs-lookup"><span data-stu-id="118f2-141">Update includes a measure sourced to a measure of an unsigned type.</span></span>|<span data-ttu-id="118f2-142">La actualización generará un error.</span><span class="sxs-lookup"><span data-stu-id="118f2-142">Update will fail.</span></span> <span data-ttu-id="118f2-143">Los incrementos exigen que la medida acepte valores negativos.</span><span class="sxs-lookup"><span data-stu-id="118f2-143">Increments require that the measure be able to take a negative value.</span></span>|  
|<span data-ttu-id="118f2-144">La actualización incluye una medida que agrega elementos distintos de Sum.</span><span class="sxs-lookup"><span data-stu-id="118f2-144">Update includes a measure that aggregates other than sum.</span></span>|<span data-ttu-id="118f2-145">Se genera un error.</span><span class="sxs-lookup"><span data-stu-id="118f2-145">An error is raised.</span></span>|  
|<span data-ttu-id="118f2-146">Se ha intentado realizar la actualización en un subcubo.</span><span class="sxs-lookup"><span data-stu-id="118f2-146">Update was tried on a subcube.</span></span>|<span data-ttu-id="118f2-147">Se genera un error.</span><span class="sxs-lookup"><span data-stu-id="118f2-147">An error is raised.</span></span>|  
  
## <a name="affect-of-cube-changes"></a><span data-ttu-id="118f2-148">Efecto de los cambios en el cubo</span><span class="sxs-lookup"><span data-stu-id="118f2-148">Affect of Cube Changes</span></span>  
 <span data-ttu-id="118f2-149">Los siguientes cambios no tienen ningún efecto sobre las reescrituras:</span><span class="sxs-lookup"><span data-stu-id="118f2-149">The following changes will not have an effect on a writeback:</span></span>  
  
-   <span data-ttu-id="118f2-150">Procesamiento de un cubo, los grupos de medida del cubo o las dimensiones del cubo.</span><span class="sxs-lookup"><span data-stu-id="118f2-150">Processing of a cube, the cube's measure groups, or the cube's dimensions.</span></span>  
  
-   <span data-ttu-id="118f2-151">Agregar atributos a una dimensión.</span><span class="sxs-lookup"><span data-stu-id="118f2-151">Adding attributes to any dimension.</span></span>  
  
-   <span data-ttu-id="118f2-152">Agregar una nueva dimensión.</span><span class="sxs-lookup"><span data-stu-id="118f2-152">Adding a new dimension.</span></span>  
  
-   <span data-ttu-id="118f2-153">Eliminar una dimensión que no incluye la reescritura.</span><span class="sxs-lookup"><span data-stu-id="118f2-153">Deleting a dimension that does not include the writeback.</span></span>  
  
-   <span data-ttu-id="118f2-154">Agregar, modificar o eliminar una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="118f2-154">Adding, modifying, or removing a hierarchy.</span></span>  
  
-   <span data-ttu-id="118f2-155">Agregar una nueva medida.</span><span class="sxs-lookup"><span data-stu-id="118f2-155">Adding a new measure.</span></span>  
  
 <span data-ttu-id="118f2-156">Los siguientes cambios no pueden llevarse a cabo sin eliminar los datos de la reescritura:</span><span class="sxs-lookup"><span data-stu-id="118f2-156">The following changes cannot be made without removing the writeback data:</span></span>  
  
-   <span data-ttu-id="118f2-157">Eliminar un atributo, o su jerarquía de atributos, si el atributo está incluido en la reescritura.</span><span class="sxs-lookup"><span data-stu-id="118f2-157">Deleting an attribute, or its attribute hierarchy, if the attribute is included in the writeback.</span></span> <span data-ttu-id="118f2-158">Esto incluye eliminar explícitamente el atributo, o su jerarquía de atributos, o bien eliminar la dimensión primaria del atributo.</span><span class="sxs-lookup"><span data-stu-id="118f2-158">This includes explicitly removing the attribute, or its attribute hierarchy, or removing the attribute's parent dimension.</span></span>  
  
-   <span data-ttu-id="118f2-159">Eliminar una medida incluida en la reescritura.</span><span class="sxs-lookup"><span data-stu-id="118f2-159">Deleting a measure included in the writeback.</span></span>  
  
-   <span data-ttu-id="118f2-160">Agregar un atributo sin un nivel `(All)` a una dimensión incluida en la reescritura.</span><span class="sxs-lookup"><span data-stu-id="118f2-160">Adding an attribute without an `(All)` level to a dimension included in the writeback.</span></span>  
  
-   <span data-ttu-id="118f2-161">Cambiar la granularidad de dimensión de una dimensión incluida en la reescritura.</span><span class="sxs-lookup"><span data-stu-id="118f2-161">Changing the dimension granularity for a dimension included in the writeback.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118f2-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="118f2-162">See Also</span></span>  
 [<span data-ttu-id="118f2-163">Modificar datos &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="118f2-163">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)  
  
  
