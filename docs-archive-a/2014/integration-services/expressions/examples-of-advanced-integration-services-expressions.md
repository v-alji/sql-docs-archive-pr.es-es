---
title: Ejemplos de expresiones avanzadas de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- functions [Integration Services]
- operators [Integration Services]
- expressions [Integration Services], examples
- examples [Integration Services]
ms.assetid: c7794ba3-0de5-466b-ae8a-9ddd27360049
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb1e8dc6f9bffd22c917414f80f6ba9f257b25b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672211"
---
# <a name="examples-of-advanced-integration-services-expressions"></a><span data-ttu-id="a97a4-102">Ejemplos de expresiones avanzadas de Integration Services</span><span class="sxs-lookup"><span data-stu-id="a97a4-102">Examples of Advanced Integration Services Expressions</span></span>
  <span data-ttu-id="a97a4-103">Esta sección proporciona ejemplos de expresiones avanzadas que combinan varios operadores y varias funciones.</span><span class="sxs-lookup"><span data-stu-id="a97a4-103">This section provides examples of advanced expressions that combine multiple operators and functions.</span></span> <span data-ttu-id="a97a4-104">Si se usa una expresión en una restricción de precedencia o en la transformación División condicional, su evaluación debe devolver un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="a97a4-104">If an expression is used in a precedence constraint or the Conditional Split transformation, it must evaluate to a Boolean.</span></span> <span data-ttu-id="a97a4-105">Sin embargo, esta restricción no se aplica a las expresiones usadas en expresiones de propiedades, variables, la transformación Columna derivada o el contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="a97a4-105">That restriction, however, does not apply to expressions used in property expressions, variables, the Derived Column transformation, or the For Loop container.</span></span>  
  
 <span data-ttu-id="a97a4-106">Los siguientes ejemplos usan las bases de datos de **AdventureWorks** y [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97a4-106">The following examples use the **AdventureWorks** and the [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="a97a4-107">Cada ejemplo identifica las tablas que utiliza.</span><span class="sxs-lookup"><span data-stu-id="a97a4-107">Each example identifies the tables it uses.</span></span>  
  
## <a name="boolean-expressions"></a><span data-ttu-id="a97a4-108">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="a97a4-108">Boolean Expressions</span></span>  
  
-   <span data-ttu-id="a97a4-109">En este ejemplo se utiliza la tabla **Product** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-109">This example uses the **Product** table.</span></span> <span data-ttu-id="a97a4-110">La evaluación de la expresión busca la entrada del mes en la columna **SellStartDate** y devuelve TRUE si el mes es junio o un mes posterior.</span><span class="sxs-lookup"><span data-stu-id="a97a4-110">The expression evaluates the month entry in the **SellStartDate** column and returns TRUE if the month is June or later.</span></span>  
  
    ```  
    DATEPART("mm",SellStartDate) > 6  
    ```  
  
-   <span data-ttu-id="a97a4-111">En este ejemplo se utiliza la tabla **Product** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-111">This example uses the **Product** table.</span></span> <span data-ttu-id="a97a4-112">La expresión evalúa el resultado redondeado de dividir la columna **ListPrice** por la columna **StandardCost** y devuelve TRUE si el resultado es mayor que 1,5.</span><span class="sxs-lookup"><span data-stu-id="a97a4-112">The expression evaluates the rounded result of dividing the **ListPrice** column by the **StandardCost** column, and returns TRUE if the result is greater than 1.5.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) > 1.50  
    ```  
  
-   <span data-ttu-id="a97a4-113">En este ejemplo se utiliza la tabla **Product** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-113">This example uses the **Product** table.</span></span> <span data-ttu-id="a97a4-114">La expresión devuelve TRUE si las tres operaciones devuelven TRUE.</span><span class="sxs-lookup"><span data-stu-id="a97a4-114">The expression returns TRUE if all three operations evaluate to TRUE.</span></span> <span data-ttu-id="a97a4-115">Si la columna **Size** y la variable **BikeSize** tienen tipos de datos incompatibles, la expresión requiere una conversión explícita, como se indica en el segundo ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a97a4-115">If the **Size** column and the **BikeSize** variable have incompatible data types, the expression requires an explicit cast as shown the second example.</span></span> <span data-ttu-id="a97a4-116">La conversión a DT_WSTR incluye la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="a97a4-116">The cast to DT_WSTR includes the length of the string.</span></span>  
  
    ```  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE && Size != @BikeSize  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE  && Size != (DT_WSTR,10)@BikeSize  
    ```  
  
-   <span data-ttu-id="a97a4-117">En este ejemplo se utiliza la tabla **CurrencyRate** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-117">This example uses the **CurrencyRate** table.</span></span> <span data-ttu-id="a97a4-118">La expresión compara valores de tablas y variables.</span><span class="sxs-lookup"><span data-stu-id="a97a4-118">The expression compares values in tables and variables.</span></span> <span data-ttu-id="a97a4-119">Devuelve TRUE si las entradas de la columna **FromCurrencyCode** o **ToCurrencyCode** son iguales a los valores de la variable y si el valor de **AverageRate** es mayor que el valor de **EndOfDayRate**.</span><span class="sxs-lookup"><span data-stu-id="a97a4-119">It returns TRUE if entries in the **FromCurrencyCode** or **ToCurrencyCode** columns are equal to variable values and if the value in **AverageRate** is greater that the value in **EndOfDayRate**.</span></span>  
  
    ```  
    (FromCurrencyCode == @FromCur || ToCurrencyCode == @ToCur) && AverageRate > EndOfDayRate  
    ```  
  
-   <span data-ttu-id="a97a4-120">En este ejemplo se utiliza la tabla **Currency** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-120">This example uses the **Currency** table.</span></span> <span data-ttu-id="a97a4-121">La expresión devuelve TRUE si el primer carácter de la columna **Name** no es a o A.</span><span class="sxs-lookup"><span data-stu-id="a97a4-121">The expression returns TRUE if the first character in the **Name** column is not a or A.</span></span>  
  
    ```  
    SUBSTRING(UPPER(Name),1,1) != "A"  
    ```  
  
     <span data-ttu-id="a97a4-122">La siguiente expresión proporciona los mismos resultados, pero es mucho más eficaz porque solo se convierte a mayúsculas un carácter.</span><span class="sxs-lookup"><span data-stu-id="a97a4-122">The following expression provides the same results, but it is more efficient because only one character is converted to uppercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Name,1,1)) != "A"  
    ```  
  
## <a name="non-boolean-expressions"></a><span data-ttu-id="a97a4-123">Expresiones no booleanas</span><span class="sxs-lookup"><span data-stu-id="a97a4-123">Non-Boolean Expressions</span></span>  
 <span data-ttu-id="a97a4-124">Las expresiones no booleanas se usan en la transformación Columna derivada, en expresiones de propiedades y en el contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="a97a4-124">Non-Boolean expressions are used in the Derived Column transformation, property expressions, and the For Loop container.</span></span>  
  
-   <span data-ttu-id="a97a4-125">En este ejemplo se utiliza la tabla **Contact** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-125">This example uses the **Contact** table.</span></span> <span data-ttu-id="a97a4-126">La expresión quita los espacios iniciales y finales de las columnas **FirstName**, **MiddleName**y **LastName** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-126">The expression removes leading and trailing spaces from the **FirstName**, **MiddleName**, and **LastName** columns.</span></span> <span data-ttu-id="a97a4-127">Extrae la primera letra de la columna **MiddleName** si no es NULL, concatena la inicial del segundo nombre y los valores de **FirstName** y **LastName**, e inserta los espacios apropiados entre los valores.</span><span class="sxs-lookup"><span data-stu-id="a97a4-127">It extracts the first letter of the **MiddleName** column if it is not null, concatenates the middle initial and the values in **FirstName** and **LastName**, and inserts appropriate spaces between values.</span></span>  
  
    ```  
    TRIM(FirstName) + " " + (!ISNULL(MiddleName) ? SUBSTRING(MiddleName,1,1) + " " : "") + TRIM(LastName)  
    ```  
  
-   <span data-ttu-id="a97a4-128">En este ejemplo se utiliza la tabla **Contact** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-128">This example uses the **Contact** table.</span></span> <span data-ttu-id="a97a4-129">La expresión valida las entradas de la columna **Salutation** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-129">The expression validates entries in the **Salutation** column.</span></span> <span data-ttu-id="a97a4-130">Devuelve una entrada **Salutation** o una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="a97a4-130">It returns a **Salutation** entry or an empty string.</span></span>  
  
    ```  
    (Salutation == "Sr." || Salutation == "Ms." || Salutation == "Sra." || Salutation == "Mr.") ? Salutation : ""  
    ```  
  
-   <span data-ttu-id="a97a4-131">En este ejemplo se utiliza la tabla **Product** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-131">This example uses the **Product** table.</span></span> <span data-ttu-id="a97a4-132">La expresión convierte el primer carácter de la columna **Color** a mayúsculas y convierte los demás caracteres a minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a97a4-132">The expression converts the first character in the **Color** column to uppercase and converts remaining characters to lowercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Color,1,1)) + LOWER(SUBSTRING(Color,2,15))  
    ```  
  
-   <span data-ttu-id="a97a4-133">En este ejemplo se utiliza la tabla **Product** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-133">This example uses the **Product** table.</span></span> <span data-ttu-id="a97a4-134">La expresión calcula el número de meses que se ha vendido un producto y devuelve la cadena "Unknown" si la columna **SellStartDate** o **SellEndDate** contiene NULL.</span><span class="sxs-lookup"><span data-stu-id="a97a4-134">The expression calculates the number of months a product has been sold and returns the string "Unknown" if either the **SellStartDate** or the **SellEndDate** column contains NULL.</span></span>  
  
    ```  
    !(ISNULL(SellStartDate)) && !(ISNULL(SellEndDate)) ? (DT_WSTR,2)DATEDIFF("mm",SellStartDate,SellEndDate) : "Unknown"  
    ```  
  
-   <span data-ttu-id="a97a4-135">En este ejemplo se utiliza la tabla **Product** .</span><span class="sxs-lookup"><span data-stu-id="a97a4-135">This example uses the **Product** table.</span></span> <span data-ttu-id="a97a4-136">La expresión calcula el margen de beneficio de la columna **StandardCost** y redondea el resultado a una precisión de dos.</span><span class="sxs-lookup"><span data-stu-id="a97a4-136">The expression calculates the markup on the **StandardCost** column and rounds the result to a precision of two.</span></span> <span data-ttu-id="a97a4-137">El resultado se presenta como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="a97a4-137">The result is presented as a percentage.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) * 100  
    ```  
  
## <a name="related-tasks"></a><span data-ttu-id="a97a4-138">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a97a4-138">Related Tasks</span></span>  
 [<span data-ttu-id="a97a4-139">Usar una expresión en un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="a97a4-139">Use an Expression in a Data Flow Component</span></span>](../use-an-expression-in-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="a97a4-140">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="a97a4-140">Related Content</span></span>  
 <span data-ttu-id="a97a4-141">Artículo técnico, sobre la [referencia rápida de expresiones de SSIS](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet), en pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="a97a4-141">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet), on pragmaticworks.com</span></span>  
  
  
