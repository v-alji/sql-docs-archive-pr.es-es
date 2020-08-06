---
title: Especificar parámetros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- parameters [SQL Server], stored procedures
- stored procedures [SQL Server], parameters
- output parameters [SQL Server]
- input parameters [SQL Server]
ms.assetid: 902314fe-5f9c-4d0d-a0b7-27e67c9c70ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: d93a04281839c4db26cbab16ac166af3cdb7c9a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678146"
---
# <a name="specify-parameters"></a><span data-ttu-id="b2f01-102">Especificar parámetros</span><span class="sxs-lookup"><span data-stu-id="b2f01-102">Specify Parameters</span></span>
  <span data-ttu-id="b2f01-103">Al especificar parámetros de procedimiento, los programas de llamada pueden pasar valores en el cuerpo del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-103">By specifying procedure parameters, calling programs are able to pass values into the body of the procedure.</span></span> <span data-ttu-id="b2f01-104">Estos valores se pueden usar para distintos fines durante la ejecución del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-104">Those values can be used for a variety of purposes during procedure execution.</span></span> <span data-ttu-id="b2f01-105">Los parámetros de procedimiento también pueden devolver valores al programa de llamada si el parámetro se marca como OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="b2f01-105">Procedure parameters can also return values to the calling program if the parameter is marked as an OUTPUT parameter.</span></span>  
  
 <span data-ttu-id="b2f01-106">Un procedimiento puede tener un máximo de 2100 parámetros; cada uno con un nombre, un tipo de datos y una dirección asignados.</span><span class="sxs-lookup"><span data-stu-id="b2f01-106">A procedure can have a maximum of 2100 parameters; each assigned a name, data type, and direction.</span></span> <span data-ttu-id="b2f01-107">Opcionalmente, a los parámetros se les pueden asignar valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b2f01-107">Optionally, parameters can be assigned default values.</span></span>  
  
 <span data-ttu-id="b2f01-108">En la siguiente sección se proporciona información acerca de cómo pasar valores en parámetros y cómo se usa cada uno de los atributos de parámetro durante una llamada a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-108">The following section provides information about passing values into parameters and about how each of the parameter attributes is used during a procedure call.</span></span>  
  
## <a name="passing-values-into-parameters"></a><span data-ttu-id="b2f01-109">Pasar valores en parámetros</span><span class="sxs-lookup"><span data-stu-id="b2f01-109">Passing Values into Parameters</span></span>  
 <span data-ttu-id="b2f01-110">Los valores de parámetro suministrados con una llamada a procedimiento deben ser constantes o una variable; no se puede usar un nombre de función como valor de parámetro.</span><span class="sxs-lookup"><span data-stu-id="b2f01-110">The parameter values supplied with a procedure call must be constants or a variable; a function name cannot be used as a parameter value.</span></span> <span data-ttu-id="b2f01-111">Las variables pueden ser definidas por el usuario o ser variables del sistema, como \@\@spid.</span><span class="sxs-lookup"><span data-stu-id="b2f01-111">Variables can be user-defined or system variables such as \@\@spid.</span></span>  
  
 <span data-ttu-id="b2f01-112">En los siguientes ejemplos se muestra cómo se pasan valores de parámetros al `uspGetWhereUsedProductID`del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-112">The following examples demonstrate passing parameter values to the procedure `uspGetWhereUsedProductID`.</span></span> <span data-ttu-id="b2f01-113">Ilustran cómo pasar parámetros como constantes y variables y también cómo usar una variable para pasar el valor de una función.</span><span class="sxs-lookup"><span data-stu-id="b2f01-113">They illustrate how to pass parameters as constants and variables and also how to use a variable to pass the value of a function.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Passing values as constants.  
EXEC dbo.uspGetWhereUsedProductID 819, '20050225';  
GO  
-- Passing values as variables.  
DECLARE @ProductID int, @CheckDate datetime;  
SET @ProductID = 819;  
SET @CheckDate = '20050225';  
EXEC dbo.uspGetWhereUsedProductID @ProductID, @CheckDate;  
GO  
-- Try to use a function as a parameter value.  
-- This produces an error message.  
EXEC dbo.uspGetWhereUsedProductID 819, GETDATE();  
GO  
-- Passing the function value as a variable.  
DECLARE @CheckDate datetime;  
SET @CheckDate = GETDATE();  
EXEC dbo.uspGetWhereUsedProductID 819, @CheckDate;  
GO  
```  
  
## <a name="specifying-parameter-names"></a><span data-ttu-id="b2f01-114">Especificar nombres de parámetro</span><span class="sxs-lookup"><span data-stu-id="b2f01-114">Specifying Parameter Names</span></span>  
 <span data-ttu-id="b2f01-115">Al crear un procedimiento y declarar un nombre de parámetro, dicho nombre debe comenzar con un único carácter \@ y debe ser único en el ámbito del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-115">When creating a procedure and declaring a parameter name, the parameter name must begin with a single \@ character and must be unique in the scope of the procedure.</span></span>  
  
 <span data-ttu-id="b2f01-116">La asignación de nombres de forma explícita a los parámetros y la asignación de los valores adecuados para cada uno en una llamada a procedimiento permite proporcionar los parámetros en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="b2f01-116">Explicitly naming the parameters and assigning the appropriate values to each parameter in a procedure call allows the parameters to be supplied in any order.</span></span> <span data-ttu-id="b2f01-117">Por ejemplo, si el procedimiento **my_proc** espera tres parámetros llamados **\@first**, **\@second** y **\@third**, los valores pasados al procedimiento pueden asignarse a los nombres de los parámetros; por ejemplo: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span><span class="sxs-lookup"><span data-stu-id="b2f01-117">For example, if the procedure **my_proc** expects three parameters named **\@first**, **\@second**, and **\@third**, the values passed to the procedure can be assigned to the parameter names, such as: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2f01-118">Si un valor de parámetro se proporciona con el formato **\@parámetro =** _valor_, todos los parámetros posteriores se deben proporcionar de esta manera.</span><span class="sxs-lookup"><span data-stu-id="b2f01-118">If one parameter value is supplied in the form **\@parameter =**_value_, all subsequent parameters must be supplied in this manner.</span></span> <span data-ttu-id="b2f01-119">Si los valores de parámetro no se pasan con el formato **\@parámetro =** _valor_, los valores se deben proporcionar en el orden idéntico (de izquierda a derecha) en el que los parámetros se enumeran en la instrucción CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="b2f01-119">If the parameter values are not passed in the form **\@parameter =**_value_, the values must be supplied in the identical order (left to right) as the parameters are listed in the CREATE PROCEDURE statement.</span></span>  
> 
> [!WARNING]
>  <span data-ttu-id="b2f01-120">Cualquier parámetro pasado con el formato **\@parámetro =** _valor_ con el parámetro mal escrito, provocará que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] genere un error e impida la ejecución del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-120">Any parameter passed in the form **\@parameter =**_value_ with the parameter misspelled, will cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate an error and prevent procedure execution.</span></span>  
  
## <a name="specifying-parameter-data-types"></a><span data-ttu-id="b2f01-121">Especificar los tipos de datos de parámetro</span><span class="sxs-lookup"><span data-stu-id="b2f01-121">Specifying Parameter Data Types</span></span>  
 <span data-ttu-id="b2f01-122">Los parámetros se deben definir con un tipo de datos cuando se declaran en una instrucción CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="b2f01-122">Parameters must be defined with a data type when they are declared in a CREATE PROCEDURE statement.</span></span> <span data-ttu-id="b2f01-123">El tipo de datos de un parámetro determina el tipo y el rango de valores que se aceptan para él cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-123">The data type of a parameter determines the type and range of values that are accepted for the parameter when the procedure is called.</span></span> <span data-ttu-id="b2f01-124">Por ejemplo, si define un parámetro con un tipo de datos `tinyint`, solo se aceptan valores numéricos del intervalo comprendido entre 0 y 255 cuando se pasan en dicho parámetro.</span><span class="sxs-lookup"><span data-stu-id="b2f01-124">For example, if you define a parameter with a `tinyint` data type, only numeric values ranging from 0 to 255 are accepted when passed into that parameter.</span></span> <span data-ttu-id="b2f01-125">Se devuelve un error si, para ejecutar un procedimiento, se usa un valor incompatible con el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="b2f01-125">An error is returned if a procedure is executed with a value incompatible with the data type.</span></span>  
  
## <a name="specifying-parameter-default-values"></a><span data-ttu-id="b2f01-126">Especificar valores predeterminados de parámetro</span><span class="sxs-lookup"><span data-stu-id="b2f01-126">Specifying Parameter Default Values</span></span>  
 <span data-ttu-id="b2f01-127">Un parámetro se considera opcional si tiene un valor predeterminado especificado cuando se declara.</span><span class="sxs-lookup"><span data-stu-id="b2f01-127">A parameter is considered optional if the parameter has a default value specified when it is declared.</span></span> <span data-ttu-id="b2f01-128">No es necesario proporcionar un valor para un parámetro opcional de una llamada a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-128">It is not necessary to provide a value for an optional parameter in a procedure call.</span></span>  
  
 <span data-ttu-id="b2f01-129">El valor predeterminado de un parámetro se usa cuando:</span><span class="sxs-lookup"><span data-stu-id="b2f01-129">The default value of a parameter is used when:</span></span>  
  
-   <span data-ttu-id="b2f01-130">No existe ningún valor especificado en la llama a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-130">No value for the parameter is specified in the procedure call.</span></span>  
  
-   <span data-ttu-id="b2f01-131">Se especifica la palabra clave DEFAULT como valor en la llamada a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-131">The DEFAULT keyword is specified as the value in the procedure call.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b2f01-132">Si el valor predeterminado es una cadena de caracteres con signos de puntuación o espacios en blanco incrustados, o bien si empieza por un número (por ejemplo, 6xxx), deberá estar delimitado por comillas simples y rectas.</span><span class="sxs-lookup"><span data-stu-id="b2f01-132">If the default value is a character string that contains embedded blanks or punctuation, or if it starts with a number (for example, 6xxx), it must be enclosed in single, straight quotation marks.</span></span>  
  
 <span data-ttu-id="b2f01-133">Si no se puede especificar ningún valor correctamente como predeterminado para el parámetro, especifique NULL como el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b2f01-133">If no value can be specified appropriately as a default for the parameter, specify NULL as the default.</span></span> <span data-ttu-id="b2f01-134">Es aconsejable que el procedimiento devuelva un mensaje personalizado si el procedimiento se ejecuta sin un valor para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="b2f01-134">It is a good idea to have the procedure return a customized message if the procedure is executed without a value for the parameter.</span></span>  
  
 <span data-ttu-id="b2f01-135">En el ejemplo siguiente se crea el procedimiento `usp_GetSalesYTD` con un parámetro de entrada, `@SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="b2f01-135">The following example creates the `usp_GetSalesYTD` procedure with one input parameter, `@SalesPerson`.</span></span> <span data-ttu-id="b2f01-136">Se asigna NULL como valor predeterminado para el parámetro y se usa en las instrucciones de control de errores para devolver un mensaje de error personalizado en los casos en que se ejecute el procedimiento sin que el parámetro `@SalesPerson` tenga un valor.</span><span class="sxs-lookup"><span data-stu-id="b2f01-136">NULL is assigned as the default value for the parameter and is used in error handling statements to return a custom error message for cases when the procedure is executed without a value for the `@SalesPerson` parameter.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetSalesYTD  
@SalesPerson nvarchar(50) = NULL  -- NULL default value  
AS   
    SET NOCOUNT ON;   
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
BEGIN  
   PRINT 'ERROR: You must specify the last name of the sales person.'  
   RETURN  
END  
-- Get the sales for the specified sales person and   
-- assign it to the output parameter.  
SELECT SalesYTD  
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="b2f01-137">En el ejemplo siguiente se ejecuta el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-137">The following example executes the procedure.</span></span> <span data-ttu-id="b2f01-138">La primera instrucción ejecuta el procedimiento sin especificar ningún valor de entrada.</span><span class="sxs-lookup"><span data-stu-id="b2f01-138">The first statement executes the procedure without specifying an input value.</span></span> <span data-ttu-id="b2f01-139">Esto hace que las instrucciones de control de errores del procedimiento devuelvan el mensaje de error personalizado.</span><span class="sxs-lookup"><span data-stu-id="b2f01-139">This causes the error handling statements in the procedure to return the custom error message.</span></span> <span data-ttu-id="b2f01-140">La segunda instrucción proporciona un valor de entrada y devuelve el conjunto de resultados esperado.</span><span class="sxs-lookup"><span data-stu-id="b2f01-140">The second statement supplies an input value and returns the expected result set.</span></span>  
  
```  
-- Run the procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the procedure with an input value.  
EXEC Sales.usp_GetSalesYTD N'Blythe';  
GO  
```  
  
 <span data-ttu-id="b2f01-141">Aunque los parámetros para los que se hayan especificado valores predeterminados se pueden omitir, solo se puede truncar la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="b2f01-141">Although parameters for which defaults have been supplied can be omitted, the list of parameters can only be truncated.</span></span> <span data-ttu-id="b2f01-142">Por ejemplo, si un procedimiento tiene cinco parámetros, los parámetros cuarto y quinto se pueden omitir.</span><span class="sxs-lookup"><span data-stu-id="b2f01-142">For example, if a procedure has five parameters, both the fourth and the fifth parameters can be omitted.</span></span> <span data-ttu-id="b2f01-143">Pero el cuarto parámetro no puede omitirse cuando se incluye el quinto parámetro, a menos que los parámetros se proporcionen con el formato **\@parámetro =** _valor_.</span><span class="sxs-lookup"><span data-stu-id="b2f01-143">However the fourth parameter cannot be skipped as long as the fifth parameter is included, unless the parameters are supplied in the form **\@parameter =**_value_.</span></span>  
  
## <a name="specifying-parameter-direction"></a><span data-ttu-id="b2f01-144">Especificar la dirección de parámetro</span><span class="sxs-lookup"><span data-stu-id="b2f01-144">Specifying Parameter Direction</span></span>  
 <span data-ttu-id="b2f01-145">La dirección de un parámetro es de entrada, el valor se pasa al cuerpo del procedimiento, o de salida, el procedimiento devuelve un valor al programa de llamada.</span><span class="sxs-lookup"><span data-stu-id="b2f01-145">The direction of a parameter is either input, a value is passed into the body of the procedure, or output, the procedure returns a value to the calling program.</span></span> <span data-ttu-id="b2f01-146">El valor predeterminado es un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="b2f01-146">The default is an input parameter.</span></span>  
  
 <span data-ttu-id="b2f01-147">Para especificar un parámetro de salida, se debe indicar la palabra clave OUTPUT en la definición del parámetro en la instrucción CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="b2f01-147">To specify an output parameter, the OUTPUT keyword must be specified in the definition of the parameter in the CREATE PROCEDURE statement.</span></span> <span data-ttu-id="b2f01-148">El procedimiento devuelve el valor actual del parámetro de salida al programa de llamada cuando se abandona el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-148">The procedure returns the current value of the output parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="b2f01-149">El programa de llamada también debe usar la palabra clave OUTPUT al ejecutar el procedimiento, a fin de guardar el valor del parámetro en una variable que se pueda usar en el programa de llamada.</span><span class="sxs-lookup"><span data-stu-id="b2f01-149">The calling program must also use the OUTPUT keyword when executing the procedure to save the parameter's value in a variable that can be used in the calling program.</span></span>  
  
 <span data-ttu-id="b2f01-150">El siguiente ejemplo crea el procedimiento `Production.usp`_`GetList` , que devuelve una lista de productos con precios que no superan un importe especificado.</span><span class="sxs-lookup"><span data-stu-id="b2f01-150">The following example creates the `Production.usp`_`GetList` procedure, which returns a list of products that have prices that do not exceed a specified amount.</span></span> <span data-ttu-id="b2f01-151">El ejemplo muestra la utilización de varias instrucciones SELECT y varios parámetros OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="b2f01-151">The example shows using multiple SELECT statements and multiple OUTPUT parameters.</span></span> <span data-ttu-id="b2f01-152">Los parámetros OUTPUT permiten a un procedimiento externo, un proceso por lotes o más de una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] tener acceso a un conjunto de valores durante la ejecución del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f01-152">OUTPUT parameters allow an external procedure, a batch, or more than one [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to access a value set during the procedure execution.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'Production.uspGetList', 'P' ) IS NOT NULL   
    DROP PROCEDURE Production.uspGetList;  
GO  
CREATE PROCEDURE Production.uspGetList @Product varchar(40)   
    , @MaxPrice money   
    , @ComparePrice money OUTPUT  
    , @ListPrice money OUT  
AS  
    SET NOCOUNT ON;  
    SELECT p.[Name] AS Product, p.ListPrice AS 'List Price'  
    FROM Production.Product AS p  
    JOIN Production.ProductSubcategory AS s   
      ON p.ProductSubcategoryID = s.ProductSubcategoryID  
    WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice;  
-- Populate the output variable @ListPprice.  
SET @ListPrice = (SELECT MAX(p.ListPrice)  
        FROM Production.Product AS p  
        JOIN  Production.ProductSubcategory AS s   
          ON p.ProductSubcategoryID = s.ProductSubcategoryID  
        WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice);  
-- Populate the output variable @compareprice.  
SET @ComparePrice = @MaxPrice;  
GO  
  
```  
  
 <span data-ttu-id="b2f01-153">Ejecute `usp_GetList` para obtener una lista de los productos de [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] (Bicicletas) que cuestan menos de 700 USD.</span><span class="sxs-lookup"><span data-stu-id="b2f01-153">Execute `usp_GetList` to return a list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] products (Bikes) that cost less than $700.</span></span> <span data-ttu-id="b2f01-154">Los parámetros OUTPUT **\@cost** y **\@compareprices** se usan con el lenguaje de control de flujo para devolver un mensaje en la ventana **Messages** (Mensajes).</span><span class="sxs-lookup"><span data-stu-id="b2f01-154">The OUTPUT parameters **\@cost** and **\@compareprices** are used with control-of-flow language to return a message in the **Messages** window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b2f01-155">La variable OUTPUT debe definirse durante la creación del procedimiento y también durante el uso de la variable.</span><span class="sxs-lookup"><span data-stu-id="b2f01-155">The OUTPUT variable must be defined during the procedure creation and also during the use of the variable.</span></span> <span data-ttu-id="b2f01-156">El nombre del parámetro y de la variable no tienen por qué coincidir.</span><span class="sxs-lookup"><span data-stu-id="b2f01-156">The parameter name and variable name do not have to match.</span></span> <span data-ttu-id="b2f01-157">Pero el tipo de datos y la posición de los parámetros deben coincidir (a menos que se use **\@listprice=** _variable_).</span><span class="sxs-lookup"><span data-stu-id="b2f01-157">However, the data type and parameter positioning must match (unless **\@listprice=** _variable_ is used).</span></span>  
  
```  
DECLARE @ComparePrice money, @Cost money ;  
EXECUTE Production.uspGetList '%Bikes%', 700,   
    @ComparePrice OUT,   
    @Cost OUTPUT  
IF @Cost <= @ComparePrice   
BEGIN  
    PRINT 'These products can be purchased for less than   
    $'+RTRIM(CAST(@ComparePrice AS varchar(20)))+'.'  
END  
ELSE  
    PRINT 'The prices for all products in this category exceed   
    $'+ RTRIM(CAST(@ComparePrice AS varchar(20)))+'.';  
  
```  
  
 <span data-ttu-id="b2f01-158">Éste es el conjunto de resultados parciales:</span><span class="sxs-lookup"><span data-stu-id="b2f01-158">Here is the partial result set:</span></span>  
  
```  
Product                                            List Price  
-------------------------------------------------- ------------------  
Road-750 Black, 58                                 539.99  
Mountain-500 Silver, 40                            564.99  
Mountain-500 Silver, 42                            564.99  
...  
Road-750 Black, 48                                 539.99  
Road-750 Black, 52                                 539.99  
  
(14 row(s) affected)  
  
These items can be purchased for less than $700.00.  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2f01-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2f01-159">See Also</span></span>  
 [<span data-ttu-id="b2f01-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b2f01-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
