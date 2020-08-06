---
title: Transformación Muestreo de porcentaje | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.percentagesamplingtrans.f1
helpviewer_keywords:
- testing mining models
- sampling seeds [Integration Services]
- data mining [Analysis Services], sample data sets
- Percentage Sampling transformation
- sample data sets [Integration Services]
- datasets [Integration Services], sample
- training mining models
ms.assetid: 59767e52-f732-4b3f-8602-be50d0a64ef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e5fe41ecf4a2ca0f9d20eec2c8e10af8ed4cd47b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752321"
---
# <a name="percentage-sampling-transformation"></a><span data-ttu-id="fa937-102">Muestreo de porcentaje, transformación</span><span class="sxs-lookup"><span data-stu-id="fa937-102">Percentage Sampling Transformation</span></span>
  <span data-ttu-id="fa937-103">La transformación Muestreo de porcentaje crea un conjunto de datos de muestra seleccionando un porcentaje de las filas de entrada de transformación.</span><span class="sxs-lookup"><span data-stu-id="fa937-103">The Percentage Sampling transformation creates a sample data set by selecting a percentage of the transformation input rows.</span></span> <span data-ttu-id="fa937-104">El conjunto de datos de muestra es una selección aleatoria de filas de la entrada de transformación, de forma que la muestra resultante sea representativa de la entrada.</span><span class="sxs-lookup"><span data-stu-id="fa937-104">The sample data set is a random selection of rows from the transformation input, to make the resultant sample representative of the input.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa937-105">Además del porcentaje especificado, la transformación Muestreo de porcentaje utiliza un algoritmo para determinar si se debe incluir una fila en la salida de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fa937-105">In addition to the specified percentage, the Percentage Sampling transformation uses an algorithm to determine whether a row should be included in the sample output.</span></span> <span data-ttu-id="fa937-106">Esto significa que el número de filas de la salida de ejemplo podría no reflejar exactamente el porcentaje especificado.</span><span class="sxs-lookup"><span data-stu-id="fa937-106">This means that the number of rows in the sample output may not exactly reflect the specified percentage.</span></span> <span data-ttu-id="fa937-107">Por ejemplo, si especifica 10% para un conjunto de datos de entrada que tiene 25.000 filas, no se generará una muestra con exactamente 2.500 filas; la muestra puede tener unas pocas filas más o menos.</span><span class="sxs-lookup"><span data-stu-id="fa937-107">For example, specifying 10 percent for an input data set that has 25,000 rows may not generate a sample with 2,500 rows; the sample may have a few more or a few less rows.</span></span>  
  
 <span data-ttu-id="fa937-108">La transformación Muestreo de porcentaje es especialmente útil para la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="fa937-108">The Percentage Sampling transformation is especially useful for data mining.</span></span> <span data-ttu-id="fa937-109">Utilizando esta transformación, puede dividir de forma aleatoria un conjunto de datos en dos conjuntos de datos: uno para el entrenamiento del modelo de minería de datos y otro para probar el modelo.</span><span class="sxs-lookup"><span data-stu-id="fa937-109">By using this transformation, you can randomly divide a data set into two data sets: one for training the data mining model, and one for testing the model.</span></span>  
  
 <span data-ttu-id="fa937-110">La transformación Muestreo de porcentaje también es útil para crear conjuntos de datos de ejemplo de desarrollo de paquetes.</span><span class="sxs-lookup"><span data-stu-id="fa937-110">The Percentage Sampling transformation is also useful for creating sample data sets for package development.</span></span> <span data-ttu-id="fa937-111">Si aplica la transformación Muestreo de porcentaje a un flujo de datos, puede reducir uniformemente el tamaño de los conjuntos de datos conservando sus características.</span><span class="sxs-lookup"><span data-stu-id="fa937-111">By applying the Percentage Sampling transformation to a data flow, you can uniformly reduce the size of the data set while preserving its data characteristics.</span></span> <span data-ttu-id="fa937-112">El paquete de prueba podrá ejecutarse más rápido porque utilizará un conjunto de datos pequeño, pero representativo.</span><span class="sxs-lookup"><span data-stu-id="fa937-112">The test package can then run more quickly because it uses a small, but representative, data set.</span></span>  
  
## <a name="configuration-the-percentage-sampling-transformation"></a><span data-ttu-id="fa937-113">Configuración de la transformación Muestreo de porcentaje</span><span class="sxs-lookup"><span data-stu-id="fa937-113">Configuration the Percentage Sampling Transformation</span></span>  
 <span data-ttu-id="fa937-114">Puede especificar un valor de inicialización de muestreo para modificar el comportamiento del generador de números aleatorios utilizado por la transformación para seleccionar filas.</span><span class="sxs-lookup"><span data-stu-id="fa937-114">You can specify a sampling seed to modify the behavior of the random number generator that the transformation uses to select rows.</span></span> <span data-ttu-id="fa937-115">Si se usa el mismo valor de inicialización de muestreo, la transformación siempre creará la misma salida de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fa937-115">If the same sampling seed is used, the transformation always creates the same sample output.</span></span> <span data-ttu-id="fa937-116">Si no se especifica un valor de inicialización, la transformación utilizará el contador del sistema operativo para crear el número aleatorio.</span><span class="sxs-lookup"><span data-stu-id="fa937-116">If no seed is specified, the transformation uses the tick count of the operating system to create the random number.</span></span> <span data-ttu-id="fa937-117">Por tanto, puede elegir usar un valor de inicialización estándar cuando desee comprobar los resultados de la transformación durante el desarrollo y las pruebas de un paquete, y después usar un valor de inicialización aleatorio cuando el paquete pase a producción.</span><span class="sxs-lookup"><span data-stu-id="fa937-117">Therefore, you might choose to use a standard seed when you want to verify the transformation results during the development and testing of a package, and then change to use a random seed when the package is moved into production.</span></span>  
  
 <span data-ttu-id="fa937-118">Esta transformación es similar a la transformación Muestreo de fila, que crea a conjunto de datos de ejemplo seleccionando un número especificado de filas de entrada.</span><span class="sxs-lookup"><span data-stu-id="fa937-118">This transformation is similar to the Row Sampling transformation, which creates a sample data set by selecting a specified number of the input rows.</span></span> <span data-ttu-id="fa937-119">Para más información, consulte [Row Sampling Transformation](row-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="fa937-119">For more information, see [Row Sampling Transformation](row-sampling-transformation.md).</span></span>  
  
 <span data-ttu-id="fa937-120">La transformación Muestreo de porcentaje incluye la propiedad personalizada `SamplingValue`.</span><span class="sxs-lookup"><span data-stu-id="fa937-120">The Percentage Sampling transformation includes the `SamplingValue` custom property.</span></span> <span data-ttu-id="fa937-121">Esta propiedad se puede actualizar a través de una expresión de propiedad, al cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="fa937-121">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="fa937-122">Para más información, vea [Expresiones de Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Usar expresiones de propiedad en paquetes](../../expressions/use-property-expressions-in-packages.md) y [Propiedades personalizadas de transformación](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fa937-122">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="fa937-123">La transformación tiene una entrada y dos salidas.</span><span class="sxs-lookup"><span data-stu-id="fa937-123">The transformation has one input and two outputs.</span></span> <span data-ttu-id="fa937-124">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="fa937-124">It does not support an error output.</span></span>  
  
 <span data-ttu-id="fa937-125">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="fa937-125">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="fa937-126">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Muestreo de porcentaje** , vea [Percentage Sampling Transformation Editor](../../percentage-sampling-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="fa937-126">For more information about the properties that you can set in the **Percentage Sampling Transformation Editor** dialog box, see [Percentage Sampling Transformation Editor](../../percentage-sampling-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="fa937-127">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="fa937-127">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="fa937-128">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa937-128">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fa937-129">Common Properties</span><span class="sxs-lookup"><span data-stu-id="fa937-129">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="fa937-130">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="fa937-130">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="fa937-131">Para más información sobre cómo establecer propiedades, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="fa937-131">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
