---
title: Manipular datos UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- CAST function
- data deletions [CLR integration]
- data insertions [CLR integration]
- CONVERT function
- data updates [CLR integration]
- comparing data
- updating data [CLR integration]
- removing data
- IsByteOrdered property
- variables [CLR integration]
- data manipulation [CLR integration]
- user-defined types [CLR integration], data manipulation
- deleting data
- UDTs [CLR integration], data manipulation
- invoking UDT methods
- inserting data
ms.assetid: 51b1a5f2-7591-4e11-bfe2-d88e0836403f
author: rothja
ms.author: jroth
ms.openlocfilehash: 75810a2ffd92130e45025f742d43ba7917d73992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745331"
---
# <a name="manipulating-udt-data"></a><span data-ttu-id="756f5-102">Manipular datos UDT</span><span class="sxs-lookup"><span data-stu-id="756f5-102">Manipulating UDT Data</span></span>
  [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="756f5-103">no proporciona ninguna sintaxis especializada para las instrucciones INSERT, UPDATE o DELETE al modificar datos en columnas de tipo definido por el usuario (UDT).</span><span class="sxs-lookup"><span data-stu-id="756f5-103">provides no specialized syntax for INSERT, UPDATE, or DELETE statements when modifying data in user-defined type (UDT) columns.</span></span> <span data-ttu-id="756f5-104">Para convertir los tipos de datos nativos al tipo UDT, se utilizan las funciones CAST o CONVERT de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="756f5-104">The [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST or CONVERT functions are used to cast native data types to the UDT type.</span></span>  
  
## <a name="inserting-data-in-a-udt-column"></a><span data-ttu-id="756f5-105">Insertar datos en una columna UDT</span><span class="sxs-lookup"><span data-stu-id="756f5-105">Inserting Data in a UDT Column</span></span>  
 <span data-ttu-id="756f5-106">Las [!INCLUDE[tsql](../../includes/tsql-md.md)] instrucciones siguientes insertan tres filas de datos de ejemplo en la tabla **Points** .</span><span class="sxs-lookup"><span data-stu-id="756f5-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements insert three rows of sample data into the **Points** table.</span></span> <span data-ttu-id="756f5-107">El tipo de datos **Point** consta de valores enteros X e y que se exponen como propiedades del UDT.</span><span class="sxs-lookup"><span data-stu-id="756f5-107">The **Point** data type consists of X and Y integer values that are exposed as properties of the UDT.</span></span> <span data-ttu-id="756f5-108">Debe utilizar la función CAST o CONVERT para convertir los valores X e y delimitados por comas en el tipo de **punto** .</span><span class="sxs-lookup"><span data-stu-id="756f5-108">You must use either the CAST or CONVERT function to cast the comma-delimited X and Y values to the **Point** type.</span></span> <span data-ttu-id="756f5-109">Las dos primeras instrucciones utilizan la función CONVERT para convertir un valor de cadena en el tipo de **punto** y la tercera instrucción usa la función CAST:</span><span class="sxs-lookup"><span data-stu-id="756f5-109">The first two statements use the CONVERT function to convert a string value to the **Point** type, and the third statement uses the CAST function:</span></span>  
  
```  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '3,4'));  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '1,5'));  
INSERT INTO dbo.Points (PointValue) VALUES (CAST ('1,99' AS Point));  
```  
  
## <a name="selecting-data"></a><span data-ttu-id="756f5-110">Seleccionar datos</span><span class="sxs-lookup"><span data-stu-id="756f5-110">Selecting Data</span></span>  
 <span data-ttu-id="756f5-111">La siguiente instrucción SELECT selecciona el valor binario del UDT.</span><span class="sxs-lookup"><span data-stu-id="756f5-111">The following SELECT statement selects the binary value of the UDT.</span></span>  
  
```  
SELECT ID, PointValue FROM dbo.Points  
```  
  
 <span data-ttu-id="756f5-112">Para ver la salida mostrada en un formato legible, llame al `ToString` método del UDT **Point** , que convierte el valor en su representación de cadena.</span><span class="sxs-lookup"><span data-stu-id="756f5-112">To see the output displayed in a readable format, call the `ToString` method of the **Point** UDT, which converts the value to its string representation.</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="756f5-113">Esto produce el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="756f5-113">This produces the following results.</span></span>  
  
```  
IDPointValue  
----------  
13,4  
21,5  
31,99  
```  
  
 <span data-ttu-id="756f5-114">También puede utilizar las funciones CAST y CONVERT de [!INCLUDE[tsql](../../includes/tsql-md.md)] para lograr los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="756f5-114">You can also use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST and CONVERT functions to achieve the same results.</span></span>  
  
```  
SELECT ID, CAST(PointValue AS varchar)   
FROM dbo.Points;  
  
SELECT ID, CONVERT(varchar, PointValue)   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="756f5-115">El UDT **Point** expone sus coordenadas X e y como propiedades, que puede seleccionar individualmente.</span><span class="sxs-lookup"><span data-stu-id="756f5-115">The **Point** UDT exposes its X and Y coordinates as properties, which you can then select individually.</span></span> <span data-ttu-id="756f5-116">La siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] selecciona las coordenadas X e Y por separado:</span><span class="sxs-lookup"><span data-stu-id="756f5-116">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects the X and Y coordinates separately:</span></span>  
  
```  
SELECT ID, PointValue.X AS xVal, PointValue.Y AS yVal   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="756f5-117">Las propiedades X e Y devuelven un valor entero, que se muestra en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="756f5-117">The X and Y properties return an integer value, which is displayed in the result set.</span></span>  
  
```  
IDxValyVal  
----------  
134  
215  
3199  
```  
  
## <a name="working-with-variables"></a><span data-ttu-id="756f5-118">Trabajar con variables</span><span class="sxs-lookup"><span data-stu-id="756f5-118">Working with Variables</span></span>  
 <span data-ttu-id="756f5-119">Puede trabajar con variables si utiliza la instrucción DECLARE para asignar una variable a un tipo UDT.</span><span class="sxs-lookup"><span data-stu-id="756f5-119">You can work with variables using the DECLARE statement to assign a variable to a UDT type.</span></span> <span data-ttu-id="756f5-120">Las instrucciones siguientes asignan un valor mediante la instrucción SET de [!INCLUDE[tsql](../../includes/tsql-md.md)] y muestran los resultados con una llamada al método `ToString` del UDT en la variable:</span><span class="sxs-lookup"><span data-stu-id="756f5-120">The following statements assign a value using the [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement and display the results by calling the UDT's `ToString` method on the variable:</span></span>  
  
```  
DECLARE @PointValue Point;  
SET @PointValue = (SELECT PointValue FROM dbo.Points  
    WHERE ID = 2);  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="756f5-121">El conjunto de resultados muestra el valor variable:</span><span class="sxs-lookup"><span data-stu-id="756f5-121">The result set displays the variable value:</span></span>  
  
```  
PointValue  
----------  
-1,5  
```  
  
 <span data-ttu-id="756f5-122">Las siguientes instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] logran el mismo resultado utilizando SELECT en lugar de SET para la asignación de variable:</span><span class="sxs-lookup"><span data-stu-id="756f5-122">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements achieve the same result using SELECT rather than SET for the variable assignment:</span></span>  
  
```  
DECLARE @PointValue Point;  
SELECT @PointValue = PointValue FROM dbo.Points  
    WHERE ID = 2;  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="756f5-123">La diferencia entre el uso de SELECT y SET para la asignación de variable es que SELECT permite asignar varias variables en una instrucción SELECT, mientras que la sintaxis de SET exige que cada asignación de variable tenga su propia instrucción SET.</span><span class="sxs-lookup"><span data-stu-id="756f5-123">The difference between using SELECT and SET for variable assignment is that SELECT allows you to assign multiple variables in one SELECT statement, whereas the SET syntax requires each variable assignment to have its own SET statement.</span></span>  
  
## <a name="comparing-data"></a><span data-ttu-id="756f5-124">Comparar datos</span><span class="sxs-lookup"><span data-stu-id="756f5-124">Comparing Data</span></span>  
 <span data-ttu-id="756f5-125">Puede utilizar operadores de comparación para comparar valores del UDT si ha establecido la propiedad `IsByteOrdered` en `true` al definir la clase.</span><span class="sxs-lookup"><span data-stu-id="756f5-125">You can use comparison operators to compare values in your UDT if you have set the `IsByteOrdered` property to `true` when defining the class.</span></span> <span data-ttu-id="756f5-126">Para obtener más información, vea [crear un tipo definido por el usuario](creating-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="756f5-126">For more information, see [Creating a User-Defined Type](creating-user-defined-types.md).</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Points   
FROM dbo.Points  
WHERE PointValue > CONVERT(Point, '2,2');  
```  
  
 <span data-ttu-id="756f5-127">Puede comparar valores internos del UDT sin tener en cuenta el valor `IsByteOrdered` si los propios valores son comparables.</span><span class="sxs-lookup"><span data-stu-id="756f5-127">You can compare internal values of the UDT regardless of the `IsByteOrdered` setting if the values themselves are comparable.</span></span> <span data-ttu-id="756f5-128">La siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] selecciona filas donde X es mayor que Y:</span><span class="sxs-lookup"><span data-stu-id="756f5-128">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects rows where X is greater than Y:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points  
WHERE PointValue.X < PointValue.Y;  
```  
  
 <span data-ttu-id="756f5-129">También puede utilizar operadores de comparación con variables, tal como se muestra en esta consulta que busca un PointValue correspondiente.</span><span class="sxs-lookup"><span data-stu-id="756f5-129">You can also use comparison operators with variables, as shown in this query that searches for a matching PointValue.</span></span>  
  
```  
DECLARE @ComparePoint Point;  
SET @ComparePoint = CONVERT(Point, '3,4');  
SELECT ID, PointValue.ToString() AS MatchingPoint   
FROM dbo.Points  
WHERE PointValue = @ComparePoint;  
```  
  
## <a name="invoking-udt-methods"></a><span data-ttu-id="756f5-130">Invocar métodos del UDT</span><span class="sxs-lookup"><span data-stu-id="756f5-130">Invoking UDT Methods</span></span>  
 <span data-ttu-id="756f5-131">También puede invocar métodos que se definen en el UDT en [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="756f5-131">You can also invoke methods that are defined in your UDT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="756f5-132">La clase **Point** contiene tres métodos, `Distance` , `DistanceFrom` y `DistanceFromXY` .</span><span class="sxs-lookup"><span data-stu-id="756f5-132">The **Point** class contains three methods, `Distance`, `DistanceFrom`, and `DistanceFromXY`.</span></span> <span data-ttu-id="756f5-133">Para ver las listas de código que definen estos tres métodos, vea [codificar tipos definidos por el usuario](creating-user-defined-types-coding.md).</span><span class="sxs-lookup"><span data-stu-id="756f5-133">For the code listings defining these three methods, see [Coding User-Defined Types](creating-user-defined-types-coding.md).</span></span>  
  
 <span data-ttu-id="756f5-134">La siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] llama al método `PointValue.Distance`:</span><span class="sxs-lookup"><span data-stu-id="756f5-134">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement calls the `PointValue.Distance` method:</span></span>  
  
```  
SELECT ID, PointValue.X AS [Point.X],   
    PointValue.Y AS [Point.Y],  
    PointValue.Distance() AS DistanceFromZero   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="756f5-135">Los resultados se muestran en la `Distance` columna:</span><span class="sxs-lookup"><span data-stu-id="756f5-135">The results are displayed in the `Distance` column:</span></span>  
  
```  
IDXYDistance  
------------------------  
1345  
2155.09901951359278  
319999.0050503762308  
```  
  
 <span data-ttu-id="756f5-136">El `DistanceFrom` método toma un argumento de tipo de datos **Point** y muestra la distancia desde el punto especificado hasta PointValue:</span><span class="sxs-lookup"><span data-stu-id="756f5-136">The `DistanceFrom` method takes an argument of **Point** data type, and displays the distance from the specified point to the PointValue:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Pnt,  
   PointValue.DistanceFrom(CONVERT(Point, '1,99')) AS DistanceFromPoint  
FROM dbo.Points;  
```  
  
 <span data-ttu-id="756f5-137">La salida muestra los resultados del método `DistanceFrom` en cada fila de la tabla:</span><span class="sxs-lookup"><span data-stu-id="756f5-137">The results display the results of the `DistanceFrom` method for each row in the table:</span></span>  
  
```  
ID PntDistanceFromPoint  
---------------------  
13,495.0210502993942  
21,594  
31,990  
```  
  
 <span data-ttu-id="756f5-138">El método `DistanceFromXY` toma los puntos de forma individual como argumentos:</span><span class="sxs-lookup"><span data-stu-id="756f5-138">The `DistanceFromXY` method takes the points individually as arguments:</span></span>  
  
```  
SELECT ID, PointValue.X as X, PointValue.Y as Y,   
PointValue.DistanceFromXY(1, 99) AS DistanceFromXY   
FROM dbo.Points  
```  
  
 <span data-ttu-id="756f5-139">El conjunto de resultados es el mismo que en el método `DistanceFrom`.</span><span class="sxs-lookup"><span data-stu-id="756f5-139">The result set is the same as the `DistanceFrom` method.</span></span>  
  
## <a name="updating-data-in-a-udt-column"></a><span data-ttu-id="756f5-140">Actualizar datos en una columna UDT</span><span class="sxs-lookup"><span data-stu-id="756f5-140">Updating Data in a UDT Column</span></span>  
 <span data-ttu-id="756f5-141">Para actualizar datos en una columna UDT, utilice la instrucción UPDATE de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="756f5-141">To update data in a UDT column, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement.</span></span> <span data-ttu-id="756f5-142">También puede utilizar un método del UDT para actualizar el estado del objeto.</span><span class="sxs-lookup"><span data-stu-id="756f5-142">You can also use a method of the UDT to update the state of the object.</span></span> <span data-ttu-id="756f5-143">La siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] actualiza una única fila en la tabla:</span><span class="sxs-lookup"><span data-stu-id="756f5-143">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates a single row in the table:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = CAST('1,88' AS Point)  
WHERE ID = 3  
```  
  
 <span data-ttu-id="756f5-144">También puede actualizar los elementos UDT por separado.</span><span class="sxs-lookup"><span data-stu-id="756f5-144">You can also update UDT elements separately.</span></span> <span data-ttu-id="756f5-145">La siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] solo actualiza la coordenada Y:</span><span class="sxs-lookup"><span data-stu-id="756f5-145">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates only the Y coordinate:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="756f5-146">Si el UDT se ha definido con el orden de bytes establecido en `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] puede evaluar la columna UDT en una cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="756f5-146">If the UDT has been defined with byte ordering set to `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] can evaluate the UDT column in a WHERE clause.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = '4,5'  
WHERE PointValue = '3,4';  
```  
  
### <a name="updating-limitations"></a><span data-ttu-id="756f5-147">Limitaciones de la actualización</span><span class="sxs-lookup"><span data-stu-id="756f5-147">Updating Limitations</span></span>  
 <span data-ttu-id="756f5-148">No puede actualizar varias propiedades a la vez mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="756f5-148">You cannot update multiple properties at once using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="756f5-149">Por ejemplo, la siguiente instrucción UPDATE genera un error porque no puede utilizar dos veces el mismo nombre de columna en una instrucción UPDATE.</span><span class="sxs-lookup"><span data-stu-id="756f5-149">For example, the following UPDATE statement fails with an error because you cannot use the same column name twice in one UDATE statement.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.X = 5, PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="756f5-150">Para actualizar individualmente cada punto, debe crear un método mutador en el ensamblado UDT de Point.</span><span class="sxs-lookup"><span data-stu-id="756f5-150">To update each point individually, you would need to create a mutator method in the Point UDT assembly.</span></span> <span data-ttu-id="756f5-151">A continuación, puede invocar el método mutador para actualizar el objeto en una instrucción UPDATE de [!INCLUDE[tsql](../../includes/tsql-md.md)], como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="756f5-151">You can then invoke the mutator method to update the object in a [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement, as in the following:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.SetXY(5, 99)  
WHERE ID = 3  
```  
  
## <a name="deleting-data-in-a-udt-column"></a><span data-ttu-id="756f5-152">Eliminar datos en una columna UDT</span><span class="sxs-lookup"><span data-stu-id="756f5-152">Deleting Data in a UDT Column</span></span>  
 <span data-ttu-id="756f5-153">Para eliminar datos en un UDT, utilice la instrucción DELETE de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="756f5-153">To delete data in a UDT, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span> <span data-ttu-id="756f5-154">La siguiente instrucción elimina todas las filas de la tabla que coinciden con los criterios especificadas en la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="756f5-154">The following statement deletes all rows in the table that match the criteria specified in the WHERE clause.</span></span> <span data-ttu-id="756f5-155">Si omite la cláusula WHERE de una instrucción DELETE, se eliminarán todas las filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="756f5-155">If you omit the WHERE clause in a DELETE statement, all rows in the table will be deleted.</span></span>  
  
```  
DELETE FROM dbo.Points  
WHERE PointValue = CAST('1,99' AS Point)  
```  
  
 <span data-ttu-id="756f5-156">Utilice la instrucción UPDATE si desea quitar los valores de una columna UDT y conservar los valores de otra fila intactos.</span><span class="sxs-lookup"><span data-stu-id="756f5-156">Use the UPDATE statement if you want to remove the values in a UDT column while leaving other row values intact.</span></span> <span data-ttu-id="756f5-157">En este ejemplo se establece PointValue en NULL.</span><span class="sxs-lookup"><span data-stu-id="756f5-157">This example sets the PointValue to null.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = null  
WHERE ID = 2  
```  
  
## <a name="see-also"></a><span data-ttu-id="756f5-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="756f5-158">See Also</span></span>  
 [<span data-ttu-id="756f5-159">Trabajar con tipos definidos por el usuario en SQL Server</span><span class="sxs-lookup"><span data-stu-id="756f5-159">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
