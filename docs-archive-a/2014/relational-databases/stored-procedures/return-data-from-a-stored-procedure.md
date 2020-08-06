---
title: Devolver datos de un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], returning data
- returning data from stored procedure
ms.assetid: 7a428ffe-cd87-4f42-b3f1-d26aa8312bf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 472ca5cf27f7e7ea2b18daa961c19faadcf2251f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678147"
---
# <a name="return-data-from-a-stored-procedure"></a><span data-ttu-id="7548f-102">Devolver datos de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="7548f-102">Return Data from a Stored Procedure</span></span>
  <span data-ttu-id="7548f-103">Existen dos formas de devolver conjuntos de resultados o datos de un procedimiento a un programa de llamada: parámetros de salida y códigos de retorno.</span><span class="sxs-lookup"><span data-stu-id="7548f-103">There are two ways of returning result sets or data from a procedure to a calling program: output parameters and return codes.</span></span> <span data-ttu-id="7548f-104">En este tema se proporciona información sobre ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="7548f-104">This topic provides information on both approaches.</span></span>  
  
## <a name="returning-data-using-an-output-parameter"></a><span data-ttu-id="7548f-105">Devolver datos mediante un parámetro de salida</span><span class="sxs-lookup"><span data-stu-id="7548f-105">Returning Data Using an Output Parameter</span></span>  
 <span data-ttu-id="7548f-106">Si especifica la palabra clave OUTPUT para un parámetro en la definición del procedimiento, este, al salir, podrá devolver el valor actual del parámetro al programa de llamada.</span><span class="sxs-lookup"><span data-stu-id="7548f-106">If you specify the OUTPUT keyword for a parameter in the procedure definition, the procedure can return the current value of the parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="7548f-107">Para guardar el valor del parámetro en una variable que pueda usarse en el programa de llamada, este último debe usar la palabra clave OUTPUT para ejecutar el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7548f-107">To save the value of the parameter in a variable that can be used in the calling program, the calling program must use the OUTPUT keyword when executing the procedure.</span></span> <span data-ttu-id="7548f-108">Para obtener más información sobre los tipos de datos se pueden usar como parámetros de salida, vea [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7548f-108">For more information about what data types can be used as output parameters, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
### <a name="examples-of-output-parameter"></a><span data-ttu-id="7548f-109">Ejemplos de parámetros de salida</span><span class="sxs-lookup"><span data-stu-id="7548f-109">Examples of Output Parameter</span></span>  
 <span data-ttu-id="7548f-110">En el ejemplo siguiente se muestra un procedimiento con un parámetro de entrada y otro de salida.</span><span class="sxs-lookup"><span data-stu-id="7548f-110">The following example shows a procedure with an input and an output parameter.</span></span> <span data-ttu-id="7548f-111">El parámetro `@SalesPerson` recibirá un valor de entrada especificado por el programa de llamada.</span><span class="sxs-lookup"><span data-stu-id="7548f-111">The `@SalesPerson` parameter would receive an input value specified by the calling program.</span></span> <span data-ttu-id="7548f-112">La instrucción SELECT usa el último valor del parámetro de entrada para obtener el valor de `SalesYTD` correcto.</span><span class="sxs-lookup"><span data-stu-id="7548f-112">The SELECT statement uses the value passed into the input parameter to obtain the correct `SalesYTD` value.</span></span> <span data-ttu-id="7548f-113">La instrucción SELECT también asigna el valor al parámetro de salida `@SalesYTD` , que devuelve el valor al programa de llamada cuando finaliza el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7548f-113">The SELECT statement also assigns the value to the `@SalesYTD` output parameter, which returns the value to the calling program when the procedure exits.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetEmployeeSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetEmployeeSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetEmployeeSalesYTD  
@SalesPerson nvarchar(50),  
@SalesYTD money OUTPUT  
AS    
  
    SET NOCOUNT ON;  
    SELECT @SalesYTD = SalesYTD  
    FROM Sales.SalesPerson AS sp  
    JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
    WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="7548f-114">El ejemplo siguiente se llama al procedimiento creado en el primer ejemplo y guarda el valor de salida devuelto desde el procedimiento llamado en la variable `@SalesYTD` , que es local para el programa de llamada.</span><span class="sxs-lookup"><span data-stu-id="7548f-114">The following example calls the procedure created in the first example and saves the output value returned from the called procedure in the `@SalesYTD` variable, which is local to the calling program.</span></span>  
  
```  
-- Declare the variable to receive the output value of the procedure.  
DECLARE @SalesYTDBySalesPerson money;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTDBySalesPerson  
EXECUTE Sales.uspGetEmployeeSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDBySalesPerson OUTPUT;  
-- Display the value returned by the procedure.  
PRINT 'Year-to-date sales for this employee is ' +   
    convert(varchar(10),@SalesYTDBySalesPerson);  
GO  
  
```  
  
 <span data-ttu-id="7548f-115">También es posible especificar los valores de entrada para los parámetros OUTPUT cuando se ejecuta el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7548f-115">Input values can also be specified for OUTPUT parameters when the procedure is executed.</span></span> <span data-ttu-id="7548f-116">Esto permite al procedimiento recibir un valor del programa de llamada, cambiarlo o realizar operaciones con él y, a continuación, devolver el nuevo valor al programa de llamada.</span><span class="sxs-lookup"><span data-stu-id="7548f-116">This allows the procedure to receive a value from the calling program, change or perform operations with the value, and then return the new value to the calling program.</span></span> <span data-ttu-id="7548f-117">En el ejemplo anterior, es posible asignar un valor a la variable `@SalesYTDBySalesPerson` antes de que el programa llame al procedimiento `Sales.uspGetEmployeeSalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="7548f-117">In the previous example, the `@SalesYTDBySalesPerson` variable can be assigned a value before the program calls the `Sales.uspGetEmployeeSalesYTD` procedure.</span></span> <span data-ttu-id="7548f-118">La instrucción de ejecución pasaría el valor de la variable `@SalesYTDBySalesPerson` en el parámetro OUTPUT `@SalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="7548f-118">The execute statement would pass the `@SalesYTDBySalesPerson` variable value into the `@SalesYTD` OUTPUT parameter.</span></span> <span data-ttu-id="7548f-119">Posteriormente, en el cuerpo del procedimiento, el valor se podría usar para realizar cálculos que generen un valor nuevo.</span><span class="sxs-lookup"><span data-stu-id="7548f-119">Then in the procedure body, the value could be used for calculations that generate a new value.</span></span> <span data-ttu-id="7548f-120">El nuevo valor se devolvería al procedimiento mediante el parámetro OUTPUT, actualizando el valor de la variable `@SalesYTDBySalesPerson` cuando finaliza el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7548f-120">The new value would be passed back out of the procedure through the OUTPUT parameter, updating the value in the `@SalesYTDBySalesPerson` variable when the procedure exits.</span></span> <span data-ttu-id="7548f-121">A esto se le suele denominar "capacidad de paso por referencia".</span><span class="sxs-lookup"><span data-stu-id="7548f-121">This is often referred to as "pass-by-reference capability."</span></span>  
  
 <span data-ttu-id="7548f-122">Si especifica OUTPUT para un parámetro cuando llama a un procedimiento y dicho parámetro no está definido mediante OUTPUT en la definición del procedimiento, se emite un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="7548f-122">If you specify OUTPUT for a parameter when you call a procedure and that parameter is not defined by using OUTPUT in the procedure definition, you get an error message.</span></span> <span data-ttu-id="7548f-123">No obstante, puede ejecutar un procedimiento con parámetros de salida y no especificar OUTPUT al ejecutar el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7548f-123">However, you can execute a procedure with output parameters and not specify OUTPUT when executing the procedure.</span></span> <span data-ttu-id="7548f-124">No se devuelve ningún error, pero no podrá utilizar el valor de salida en el programa que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="7548f-124">No error is returned, but you cannot use the output value in the calling program.</span></span>  
  
### <a name="using-the-cursor-data-type-in-output-parameters"></a><span data-ttu-id="7548f-125">Usar el tipo de datos de cursor en parámetros OUTPUT</span><span class="sxs-lookup"><span data-stu-id="7548f-125">Using the Cursor Data Type in OUTPUT Parameters</span></span>  
 [!INCLUDE[tsql](../../../includes/tsql-md.md)]<span data-ttu-id="7548f-126">los procedimientos solo pueden usar el `cursor` tipo de datos para los parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="7548f-126">procedures can use the `cursor` data type only for OUTPUT parameters.</span></span> <span data-ttu-id="7548f-127">Si `cursor` se especifica el tipo de datos para un parámetro, deben especificarse las palabras clave varying y output para ese parámetro en la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7548f-127">If the `cursor` data type is specified for a parameter, both the VARYING and OUTPUT keywords must be specified for that parameter in the procedure definition.</span></span> <span data-ttu-id="7548f-128">Un parámetro solo se puede especificar como OUTPUT, pero si se especifica la palabra clave VARYING en la declaración del parámetro, el tipo de datos debe ser `cursor` y también se debe especificar la palabra clave output.</span><span class="sxs-lookup"><span data-stu-id="7548f-128">A parameter can be specified as only OUTPUT but if the VARYING keyword is specified in the parameter declaration, the data type must be `cursor` and the OUTPUT keyword must also be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7548f-129">El tipo de datos `cursor` no se puede enlazar a variables de aplicación a través de las API de bases de datos tales como OLE DB, ODBC, ADO y DB-Library.</span><span class="sxs-lookup"><span data-stu-id="7548f-129">The `cursor` data type cannot be bound to application variables through the database APIs such as OLE DB, ODBC, ADO, and DB-Library.</span></span> <span data-ttu-id="7548f-130">Debido a que los parámetros OUTPUT deben estar enlazados antes de que una aplicación pueda ejecutar un procedimiento, dichos procedimientos con parámetros `cursor` OUTPUT no pueden llamarse desde las API de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="7548f-130">Because OUTPUT parameters must be bound before an application can execute a procedure, procedures with `cursor` OUTPUT parameters cannot be called from the database APIs.</span></span> <span data-ttu-id="7548f-131">Estos procedimientos solo pueden llamarse desde procesos por lotes, procedimientos o desencadenadores [!INCLUDE[tsql](../../../includes/tsql-md.md)] cuando la variable `cursor` OUTPUT esté asignada a una variable `cursor` local de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7548f-131">These procedures can be called from [!INCLUDE[tsql](../../../includes/tsql-md.md)] batches, procedures, or triggers only when the `cursor` OUTPUT variable is assigned to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] local `cursor` variable.</span></span>  
  
### <a name="rules-for-cursor-output-parameters"></a><span data-ttu-id="7548f-132">Reglas para parámetros de salida de cursor</span><span class="sxs-lookup"><span data-stu-id="7548f-132">Rules for Cursor Output Parameters</span></span>  
 <span data-ttu-id="7548f-133">Las siguientes reglas se aplican a los parámetros `cursor` OUTPUT cuando se ejecuta el procedimiento:</span><span class="sxs-lookup"><span data-stu-id="7548f-133">The following rules pertain to `cursor` output parameters when the procedure is executed:</span></span>  
  
-   <span data-ttu-id="7548f-134">Para un cursor de solo avance, las filas devueltas en el conjunto de resultados del cursor son solo aquellas filas que estén en la posición del cursor y hacia delante al concluir la ejecución del procedimiento, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7548f-134">For a forward-only cursor, the rows returned in the cursor's result set are only those rows at and beyond the position of the cursor at the conclusion of the procedure execution, for example:</span></span>  
  
    -   <span data-ttu-id="7548f-135">En un procedimiento de un conjunto de resultados llamado RS de 100 filas, se abre un cursor no desplazable.</span><span class="sxs-lookup"><span data-stu-id="7548f-135">A nonscrollable cursor is opened in a procedure on a result set named RS of 100 rows.</span></span>  
  
    -   <span data-ttu-id="7548f-136">El procedimiento captura las primeras 5 filas del conjunto de resultados RS.</span><span class="sxs-lookup"><span data-stu-id="7548f-136">The procedure fetches the first 5 rows of result set RS.</span></span>  
  
    -   <span data-ttu-id="7548f-137">El procedimiento vuelve a quien le llamó.</span><span class="sxs-lookup"><span data-stu-id="7548f-137">The procedure returns to its caller.</span></span>  
  
    -   <span data-ttu-id="7548f-138">El conjunto de resultados que RS devolvió a quien llamó está formado por las filas 6 a 100 de RS; el cursor del que llama se coloca antes de la primera fila de RS.</span><span class="sxs-lookup"><span data-stu-id="7548f-138">The result set RS returned to the caller consists of rows from 6 through 100 of RS, and the cursor in the caller is positioned before the first row of RS.</span></span>  
  
-   <span data-ttu-id="7548f-139">Para un cursor de solo avance, si el cursor se coloca antes de la primera fila cuando finalice el procedimiento, el conjunto de resultados completo se devuelve al proceso por lotes, procedimiento o desencadenador de llamada.</span><span class="sxs-lookup"><span data-stu-id="7548f-139">For a forward-only cursor, if the cursor is positioned before the first row when the procedure exits, the entire result set is returned to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="7548f-140">Cuando se devuelve, la posición del cursor se establece antes de la primera fila.</span><span class="sxs-lookup"><span data-stu-id="7548f-140">When returned, the cursor position is set before the first row.</span></span>  
  
-   <span data-ttu-id="7548f-141">Para un cursor de solo avance, si el cursor se coloca después del final de la última fila cuando finaliza el procedimiento almacenado, se devolverá un conjunto de resultados vacío al proceso por lotes, procedimiento o desencadenador de llamada.</span><span class="sxs-lookup"><span data-stu-id="7548f-141">For a forward-only cursor, if the cursor is positioned beyond the end of the last row when the procedure exits, an empty result set is returned to the calling batch, procedure, or trigger.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7548f-142">Un conjunto de resultados vacío no es lo mismo que un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="7548f-142">An empty result set is not the same as a null value.</span></span>  
  
-   <span data-ttu-id="7548f-143">Para un cursor desplazable, todas las filas del conjunto de resultados se devuelven al proceso por lotes, procedimiento o desencadenador de llamada cuando finaliza el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7548f-143">For a scrollable cursor, all the rows in the result set are returned to the calling batch, procedure, or trigger when the procedure exits.</span></span> <span data-ttu-id="7548f-144">Cuando se devuelve, la posición del cursor se deja en la posición de la última captura ejecutada en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7548f-144">When returned, the cursor position is left at the position of the last fetch executed in the procedure.</span></span>  
  
-   <span data-ttu-id="7548f-145">Para cualquier tipo de cursor, si se ha cerrado el cursor, se devuelve un valor NULL al proceso por lotes, procedimiento o desencadenador de llamada.</span><span class="sxs-lookup"><span data-stu-id="7548f-145">For any type of cursor, if the cursor is closed, then a null value is passed back to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="7548f-146">Esto también ocurrirá si se ha asignado un cursor a un parámetro, pero ese cursor nunca se abre.</span><span class="sxs-lookup"><span data-stu-id="7548f-146">This will also be the case if a cursor is assigned to a parameter, but that cursor is never opened.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7548f-147">El estado cerrado solo tiene importancia en el momento del retorno.</span><span class="sxs-lookup"><span data-stu-id="7548f-147">The closed state matters only at return time.</span></span> <span data-ttu-id="7548f-148">Por ejemplo, es válido cerrar un cursor a mitad del procedimiento, volver a abrirlo posteriormente en el procedimiento y devolver el conjunto de resultados de ese cursor al proceso por lotes, procedimiento o desencadenador de llamada.</span><span class="sxs-lookup"><span data-stu-id="7548f-148">For example, it is valid to close a cursor part of the way through the procedure, to open it again later in the procedure, and return that cursor's result set to the calling batch, procedure, or trigger.</span></span>  
  
### <a name="examples-of-cursor-output-parameters"></a><span data-ttu-id="7548f-149">Ejemplos de parámetros de salida de cursor</span><span class="sxs-lookup"><span data-stu-id="7548f-149">Examples of Cursor Output Parameters</span></span>  
 <span data-ttu-id="7548f-150">En el ejemplo siguiente, se crea un procedimiento que especifica un parámetro de salida, `@currency` _ `cursor` con el `cursor` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="7548f-150">In the following example, a procedure is created that specified an output parameter, `@currency`_`cursor` using the `cursor` data type.</span></span> <span data-ttu-id="7548f-151">A continuación, se llama al procedimiento desde un lote.</span><span class="sxs-lookup"><span data-stu-id="7548f-151">The procedure is then called in a batch.</span></span>  
  
 <span data-ttu-id="7548f-152">Primero, crea el procedimiento de declaración y, luego, abre un cursor en la tabla Currency.</span><span class="sxs-lookup"><span data-stu-id="7548f-152">First, create the procedure that declares and then opens a cursor on the Currency table.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspCurrencyCursor', 'P' ) IS NOT NULL  
    DROP PROCEDURE dbo.uspCurrencyCursor;  
GO  
CREATE PROCEDURE dbo.uspCurrencyCursor   
    @CurrencyCursor CURSOR VARYING OUTPUT  
AS  
    SET NOCOUNT ON;  
    SET @CurrencyCursor = CURSOR  
    FORWARD_ONLY STATIC FOR  
      SELECT CurrencyCode, Name  
      FROM Sales.Currency;  
    OPEN @CurrencyCursor;  
GO  
  
```  
  
 <span data-ttu-id="7548f-153">A continuación, se ejecuta un proceso por lotes que declara una variable cursor local, ejecuta el procedimiento para asignar el cursor a la variable local y, por último, captura las filas desde el cursor.</span><span class="sxs-lookup"><span data-stu-id="7548f-153">Next, execute a batch that declares a local cursor variable, executes the procedure to assign the cursor to the local variable, and then fetches the rows from the cursor.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @MyCursor CURSOR;  
EXEC dbo.uspCurrencyCursor @CurrencyCursor = @MyCursor OUTPUT;  
WHILE (@@FETCH_STATUS = 0)  
BEGIN;  
     FETCH NEXT FROM @MyCursor;  
END;  
CLOSE @MyCursor;  
DEALLOCATE @MyCursor;  
GO  
  
```  
  
## <a name="returning-data-using-a-return-code"></a><span data-ttu-id="7548f-154">Devolver datos con un código de retorno</span><span class="sxs-lookup"><span data-stu-id="7548f-154">Returning Data Using a Return Code</span></span>  
 <span data-ttu-id="7548f-155">Un procedimiento puede devolver un valor entero, denominado código de retorno, para indicar el estado de ejecución de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7548f-155">A procedure can return an integer value called a return code to indicate the execution status of a procedure.</span></span> <span data-ttu-id="7548f-156">Se especifica el código de retorno para un procedimiento mediante la instrucción RETURN.</span><span class="sxs-lookup"><span data-stu-id="7548f-156">You specify the return code for a procedure using the RETURN statement.</span></span> <span data-ttu-id="7548f-157">Al igual que con los parámetros OUTPUT, debe guardar el código de retorno en una variable cuando se ejecute el procedimiento a fin de usar su valor en el programa de llamada.</span><span class="sxs-lookup"><span data-stu-id="7548f-157">As with OUTPUT parameters, you must save the return code in a variable when the procedure is executed in order to use the return code value in the calling program.</span></span> <span data-ttu-id="7548f-158">Por ejemplo, la variable `@result` de asignación de tipo de datos `int` se utiliza para almacenar el código de retorno del procedimiento `my_proc` , como:</span><span class="sxs-lookup"><span data-stu-id="7548f-158">For example, the assignment variable `@result` of data type `int` is used to store the return code from the procedure `my_proc`, such as:</span></span>  
  
```  
DECLARE @result int;  
EXECUTE @result = my_proc;  
```  
  
 <span data-ttu-id="7548f-159">Los códigos de retorno suelen usarse en los bloques de control de flujo dentro de los procedimientos con el fin de establecer el valor del código de retorno para cada posible situación de error.</span><span class="sxs-lookup"><span data-stu-id="7548f-159">Return codes are commonly used in control-of-flow blocks within procedures to set the return code value for each possible error situation.</span></span> <span data-ttu-id="7548f-160">Puede usar la función @@ERROR después de una instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] para detectar si se produjo un error durante la ejecución de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="7548f-160">You can use the @@ERROR function after a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to detect whether an error occurred during the execution of the statement.</span></span>  
  
### <a name="examples-of-return-codes"></a><span data-ttu-id="7548f-161">Ejemplos de códigos de retorno</span><span class="sxs-lookup"><span data-stu-id="7548f-161">Examples of Return Codes</span></span>  
 <span data-ttu-id="7548f-162">El ejemplo siguiente muestra el procedimiento `usp_GetSalesYTD` con control de errores que establece valores del código de retorno especiales para varios errores.</span><span class="sxs-lookup"><span data-stu-id="7548f-162">The following example shows the `usp_GetSalesYTD` procedure with error handling that sets special return code values for various errors.</span></span> <span data-ttu-id="7548f-163">La tabla siguiente muestra el valor entero que asigna el procedimiento a cada error posible y el significado correspondiente de cada valor.</span><span class="sxs-lookup"><span data-stu-id="7548f-163">The following table shows the integer value that is assigned by the procedure to each possible error, and the corresponding meaning for each value.</span></span>  
  
|<span data-ttu-id="7548f-164">Valor de código de retorno</span><span class="sxs-lookup"><span data-stu-id="7548f-164">Return code value</span></span>|<span data-ttu-id="7548f-165">Significado</span><span class="sxs-lookup"><span data-stu-id="7548f-165">Meaning</span></span>|  
|-----------------------|-------------|  
|<span data-ttu-id="7548f-166">0</span><span class="sxs-lookup"><span data-stu-id="7548f-166">0</span></span>|<span data-ttu-id="7548f-167">Ejecución correcta.</span><span class="sxs-lookup"><span data-stu-id="7548f-167">Successful execution.</span></span>|  
|<span data-ttu-id="7548f-168">1</span><span class="sxs-lookup"><span data-stu-id="7548f-168">1</span></span>|<span data-ttu-id="7548f-169">No se ha especificado el valor del parámetro requerido.</span><span class="sxs-lookup"><span data-stu-id="7548f-169">Required parameter value is not specified.</span></span>|  
|<span data-ttu-id="7548f-170">2</span><span class="sxs-lookup"><span data-stu-id="7548f-170">2</span></span>|<span data-ttu-id="7548f-171">El valor del parámetro especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="7548f-171">Specified parameter value is not valid.</span></span>|  
|<span data-ttu-id="7548f-172">3</span><span class="sxs-lookup"><span data-stu-id="7548f-172">3</span></span>|<span data-ttu-id="7548f-173">Se ha producido un error al obtener el valor de venta.</span><span class="sxs-lookup"><span data-stu-id="7548f-173">Error has occurred getting sales value.</span></span>|  
|<span data-ttu-id="7548f-174">4</span><span class="sxs-lookup"><span data-stu-id="7548f-174">4</span></span>|<span data-ttu-id="7548f-175">Valor de venta NULL encontrado para el vendedor.</span><span class="sxs-lookup"><span data-stu-id="7548f-175">NULL sales value found for the salesperson.</span></span>|  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.usp_GetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.usp_GetSalesYTD;  
GO  
CREATE PROCEDURE Sales.usp_GetSalesYTD  
@SalesPerson nvarchar(50) = NULL,  -- NULL default value  
@SalesYTD money = NULL OUTPUT  
AS    
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
   BEGIN  
       PRINT 'ERROR: You must specify a last name for the sales person.'  
       RETURN(1)  
   END  
ELSE  
   BEGIN  
   -- Make sure the value is valid.  
   IF (SELECT COUNT(*) FROM HumanResources.vEmployee  
          WHERE LastName = @SalesPerson) = 0  
      RETURN(2)  
   END  
-- Get the sales for the specified name and   
-- assign it to the output parameter.  
SELECT @SalesYTD = SalesYTD   
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
-- Check for SQL Server errors.  
IF @@ERROR <> 0   
   BEGIN  
      RETURN(3)  
   END  
ELSE  
   BEGIN  
   -- Check to see if the ytd_sales value is NULL.  
     IF @SalesYTD IS NULL  
       RETURN(4)   
     ELSE  
      -- SUCCESS!!  
        RETURN(0)  
   END  
-- Run the stored procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the stored procedure with an input value.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTD  
EXECUTE Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
PRINT N'Year-to-date sales for this employee is ' +  
    CONVERT(varchar(10), @SalesYTDForSalesPerson);  
  
```  
  
 <span data-ttu-id="7548f-176">El ejemplo siguiente crea un programa para controlar los códigos de retorno devueltos desde el procedimiento `usp_GetSalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="7548f-176">The following example creates a program to handle the return codes that are returned from the `usp_GetSalesYTD` procedure.</span></span>  
  
```  
-- Declare the variables to receive the output value and return code   
-- of the procedure.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
  
-- Execute the procedure with a title_id value  
-- and save the output value and return code in variables.  
EXECUTE @ret_code = Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
--  Check the return codes.  
IF @ret_code = 0  
BEGIN  
   PRINT 'Procedure executed successfully'  
   -- Display the value returned by the procedure.  
   PRINT 'Year-to-date sales for this employee is ' + CONVERT(varchar(10),@SalesYTDForSalesPerson)  
END  
ELSE IF @ret_code = 1  
   PRINT 'ERROR: You must specify a last name for the sales person.'  
ELSE IF @ret_code = 2   
   PRINT 'EERROR: You must enter a valid last name for the sales person.'  
ELSE IF @ret_code = 3  
   PRINT 'ERROR: An error occurred getting sales value.'  
ELSE IF @ret_code = 4  
   PRINT 'ERROR: No sales recorded for this employee.'     
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="7548f-177">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7548f-177">See Also</span></span>  
 <span data-ttu-id="7548f-178">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7548f-178">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="7548f-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7548f-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span></span>  
 <span data-ttu-id="7548f-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7548f-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="7548f-181">[Cursores](../cursors.md) </span><span class="sxs-lookup"><span data-stu-id="7548f-181">[Cursors](../cursors.md) </span></span>  
 <span data-ttu-id="7548f-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7548f-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span></span>  
 [<span data-ttu-id="7548f-183">@@ERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7548f-183">@@ERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/error-transact-sql)  
  
  
