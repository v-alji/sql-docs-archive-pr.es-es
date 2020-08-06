---
title: Transformación Columna derivada | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntrans.f1
helpviewer_keywords:
- multiple derived columns
- expressions [Integration Services], derived columns
- derived columns
- columns [Integration Services], derivations
- Derived Column transformation
ms.assetid: 8eba755e-8e48-4233-bd1e-09a46bf2692f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bbdc46f2e67b1b859fcfa446c584373cfbeca0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663032"
---
# <a name="derived-column-transformation"></a><span data-ttu-id="178f4-102">Transformación Columna derivada</span><span class="sxs-lookup"><span data-stu-id="178f4-102">Derived Column Transformation</span></span>
  <span data-ttu-id="178f4-103">La transformación Columna derivada crea nuevos valores de columna aplicando expresiones a las columnas de entrada de la transformación.</span><span class="sxs-lookup"><span data-stu-id="178f4-103">The Derived Column transformation creates new column values by applying expressions to transformation input columns.</span></span> <span data-ttu-id="178f4-104">Una expresión puede contener cualquier combinación variables, funciones, operadores y columnas de la entrada de transformación.</span><span class="sxs-lookup"><span data-stu-id="178f4-104">An expression can contain any combination of variables, functions, operators, and columns from the transformation input.</span></span> <span data-ttu-id="178f4-105">El resultado puede agregarse como una nueva columna o insertarse en una columna existente como un valor de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="178f4-105">The result can be added as a new column or inserted into an existing column as a replacement value.</span></span> <span data-ttu-id="178f4-106">La transformación Columna derivada puede definir varias columnas derivadas, y cualquier variable o columna de entrada puede aparecer en varias expresiones.</span><span class="sxs-lookup"><span data-stu-id="178f4-106">The Derived Column transformation can define multiple derived columns, and any variable or input columns can appear in multiple expressions.</span></span>  
  
 <span data-ttu-id="178f4-107">Puede utilizar esta transformación para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="178f4-107">You can use this transformation to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="178f4-108">Concatenar datos de distintas columnas en una columna derivada.</span><span class="sxs-lookup"><span data-stu-id="178f4-108">Concatenate data from different columns into a derived column.</span></span> <span data-ttu-id="178f4-109">Por ejemplo, puede combinar valores de las columnas **FirstName** y **LastName** en una sola columna derivada, denominada **FullName**, mediante la expresión `FirstName + " " + LastName`.</span><span class="sxs-lookup"><span data-stu-id="178f4-109">For example, you can combine values from the **FirstName** and **LastName** columns into a single derived column named **FullName**, by using the expression `FirstName + " " + LastName`.</span></span>  
  
-   <span data-ttu-id="178f4-110">Extraer caracteres de datos de cadena mediante funciones como SUBSTRING y después almacenar el resultado en una columna derivada.</span><span class="sxs-lookup"><span data-stu-id="178f4-110">Extract characters from string data by using functions such as SUBSTRING, and then store the result in a derived column.</span></span> <span data-ttu-id="178f4-111">Por ejemplo, puede extraer de la columna **FirstName** la inicial del nombre de una persona mediante la expresión `SUBSTRING(FirstName,1,1)`.</span><span class="sxs-lookup"><span data-stu-id="178f4-111">For example, you can extract a person's initial from the **FirstName** column, by using the expression `SUBSTRING(FirstName,1,1)`.</span></span>  
  
-   <span data-ttu-id="178f4-112">Aplicar funciones matemáticas a datos numéricos y almacenar el resultado en una columna derivada.</span><span class="sxs-lookup"><span data-stu-id="178f4-112">Apply mathematical functions to numeric data and store the result in a derived column.</span></span> <span data-ttu-id="178f4-113">Por ejemplo, puede cambiar la longitud y la precisión de una columna numérica, **SalesTax**, a un número con dos cifras decimales mediante la expresión `ROUND(SalesTax, 2)`.</span><span class="sxs-lookup"><span data-stu-id="178f4-113">For example, you can change the length and precision of a numeric column, **SalesTax**, to a number with two decimal places, by using the expression `ROUND(SalesTax, 2)`.</span></span>  
  
-   <span data-ttu-id="178f4-114">Crear expresiones que comparen columnas de entrada y variables.</span><span class="sxs-lookup"><span data-stu-id="178f4-114">Create expressions that compare input columns and variables.</span></span> <span data-ttu-id="178f4-115">Por ejemplo, puede comparar la variable **Version** con los datos de la columna **ProductVersion**y, en función del resultado de la comparación, usar el valor de **Version** o **ProductVersion**mediante la expresión `ProductVersion == @Version? ProductVersion : @Version`.</span><span class="sxs-lookup"><span data-stu-id="178f4-115">For example, you can compare the variable **Version** against the data in the column **ProductVersion**, and depending on the comparison result, use the value of either **Version** or **ProductVersion**, by using the expression `ProductVersion == @Version? ProductVersion : @Version`.</span></span>  
  
-   <span data-ttu-id="178f4-116">Extraer partes de un valor datetime.</span><span class="sxs-lookup"><span data-stu-id="178f4-116">Extract parts of a datetime value.</span></span> <span data-ttu-id="178f4-117">Por ejemplo, puede utilizar las funciones GETDATE y DATEPART para extraer el año actual mediante la expresión `DATEPART("year",GETDATE())`.</span><span class="sxs-lookup"><span data-stu-id="178f4-117">For example, you can use the GETDATE and DATEPART functions to extract the current year, by using the expression `DATEPART("year",GETDATE())`.</span></span>  
  
-   <span data-ttu-id="178f4-118">Convierta las cadenas de fecha a un formato específico mediante una expresión.</span><span class="sxs-lookup"><span data-stu-id="178f4-118">Convert date strings to a specific format using an expression.</span></span>  
  
## <a name="configuration-of-the-derived-column-transformation"></a><span data-ttu-id="178f4-119">Configuración de la transformación Columna derivada</span><span class="sxs-lookup"><span data-stu-id="178f4-119">Configuration of the Derived Column Transformation</span></span>  
 <span data-ttu-id="178f4-120">Puede configurar la transformación Columna derivada de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="178f4-120">You can configure the Derived column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="178f4-121">Proporcionar una expresión para cada columna de entrada o nueva columna que se vaya a modificar.</span><span class="sxs-lookup"><span data-stu-id="178f4-121">Provide an expression for each input column or new column that will be changed.</span></span> <span data-ttu-id="178f4-122">Para más información, vea [Expresiones de Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="178f4-122">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="178f4-123">Si una expresión hace referencia a una columna de entrada sobrescrita por la transformación Columna derivada, la expresión utiliza el valor original de la columna, no el valor derivado.</span><span class="sxs-lookup"><span data-stu-id="178f4-123">If an expression references an input column that is overwritten by the Derived Column transformation, the expression uses the original value of the column, not the derived value.</span></span>  
  
-   <span data-ttu-id="178f4-124">Si agrega resultados a columnas nuevas y el tipo de datos es `string`, especifique una página de códigos.</span><span class="sxs-lookup"><span data-stu-id="178f4-124">If adding results to new columns and the data type is `string`, specify a code page.</span></span> <span data-ttu-id="178f4-125">Para más información, consulte [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="178f4-125">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="178f4-126">La transformación Columna derivada incluye la propiedad personalizada FriendlyExpression.</span><span class="sxs-lookup"><span data-stu-id="178f4-126">The Derived Column transformation includes the FriendlyExpression custom property.</span></span> <span data-ttu-id="178f4-127">Esta propiedad se puede actualizar a través de una expresión de propiedad, al cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="178f4-127">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="178f4-128">Para obtener más información, vea [Usar expresiones de propiedad en paquetes](../../expressions/use-property-expressions-in-packages.md)y [Propiedades personalizadas de transformación](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="178f4-128">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="178f4-129">Esta transformación tiene una entrada, una salida normal y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="178f4-129">This transformation has one input, one regular output, and one error output.</span></span>  
  
 <span data-ttu-id="178f4-130">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="178f4-130">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="178f4-131">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Columna derivada** , vea [Derived Column Transformation Editor](../../derived-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="178f4-131">For more information about the properties that you can set in the **Derived Column Transformation Editor** dialog box, see [Derived Column Transformation Editor](../../derived-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="178f4-132">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="178f4-132">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="178f4-133">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="178f4-133">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="178f4-134">Common Properties</span><span class="sxs-lookup"><span data-stu-id="178f4-134">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="178f4-135">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="178f4-135">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="178f4-136">Para obtener más información sobre cómo establecer valores de propiedades, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="178f4-136">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="178f4-137">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="178f4-137">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="178f4-138">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="178f4-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="178f4-139">Derivar valores de columna mediante la transformación Columna derivada</span><span class="sxs-lookup"><span data-stu-id="178f4-139">Derive Column Values by Using the Derived Column Transformation</span></span>](derived-column-transformation.md)  
  
## <a name="related-content"></a><span data-ttu-id="178f4-140">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="178f4-140">Related Content</span></span>  
 <span data-ttu-id="178f4-141">Artículo técnico, sobre [ejemplos de expresiones SSIS](https://go.microsoft.com/fwlink/?LinkId=220761), en social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="178f4-141">Technical article, [SSIS Expression Examples](https://go.microsoft.com/fwlink/?LinkId=220761), on social.technet.microsoft.com</span></span>  
  
 <span data-ttu-id="178f4-142">Blog, [cómo dividir datos de columna mediante SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span><span class="sxs-lookup"><span data-stu-id="178f4-142">Blog, [How to Split Column Data using SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span></span>  
  
  
