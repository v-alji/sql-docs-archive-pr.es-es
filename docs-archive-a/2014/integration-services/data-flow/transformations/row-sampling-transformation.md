---
title: Transformación Muestreo de fila | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowsamplingtrans.f1
helpviewer_keywords:
- sampling seeds [Integration Services]
- random seeds
- random sampling
- sample data sets [Integration Services]
- Row Sampling transformation
- packages [Integration Services], samples
- datasets [Integration Services], sample
ms.assetid: b6caafd3-30b2-4368-82af-a44611d4cd39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c56f07d9fafa03752ef8c6572a13c6ad7c02a8c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752314"
---
# <a name="row-sampling-transformation"></a><span data-ttu-id="2f541-102">Muestreo de fila, transformación</span><span class="sxs-lookup"><span data-stu-id="2f541-102">Row Sampling Transformation</span></span>
  <span data-ttu-id="2f541-103">La transformación Muestreo de fila se usa para obtener un subconjunto seleccionado aleatoriamente de un conjunto de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="2f541-103">The Row Sampling transformation is used to obtain a randomly selected subset of an input dataset.</span></span> <span data-ttu-id="2f541-104">Puede especificar el tamaño exacto del ejemplo de salida y especificar un valor de inicialización para el generador de números aleatorios.</span><span class="sxs-lookup"><span data-stu-id="2f541-104">You can specify the exact size of the output sample, and specify a seed for the random number generator.</span></span>  
  
 <span data-ttu-id="2f541-105">Hay muchas aplicaciones para el muestreo aleatorio.</span><span class="sxs-lookup"><span data-stu-id="2f541-105">There are many applications for random sampling.</span></span> <span data-ttu-id="2f541-106">Por ejemplo, una compañía que desea seleccionar aleatoriamente 50 empleados que recibirán los premios de una lotería podría aplicar la transformación Muestreo de fila a la base de datos de empleados para generar el número exacto de ganadores.</span><span class="sxs-lookup"><span data-stu-id="2f541-106">For example, a company that wanted to randomly select 50 employees to receive prizes in a lottery could use the Row Sampling transformation on the employee database to generate the exact number of winners.</span></span>  
  
 <span data-ttu-id="2f541-107">La transformación Muestreo de fila también es útil durante el desarrollo de paquetes para crear un conjunto de datos pequeño pero representativo.</span><span class="sxs-lookup"><span data-stu-id="2f541-107">The Row Sampling transformation is also useful during package development for creating a small but representative dataset.</span></span> <span data-ttu-id="2f541-108">Puede probar la ejecución del paquete y la transformación de datos con datos representativos. Tardará menos tiempo, ya que usará una muestra aleatoria en lugar del conjunto de datos completo.</span><span class="sxs-lookup"><span data-stu-id="2f541-108">You can test package execution and data transformation with richly representative data, but more quickly because a random sample is used instead of the full dataset.</span></span> <span data-ttu-id="2f541-109">Como el conjunto de datos de ejemplo utilizado por el paquete de prueba tiene siempre el mismo tamaño, al usar el subconjunto de ejemplo también resulta más fácil identificar posibles problemas de rendimiento del paquete.</span><span class="sxs-lookup"><span data-stu-id="2f541-109">Because the sample dataset used by the test package is always the same size, using the sample subset also makes it easier to identify performance problems in the package.</span></span>  
  
 <span data-ttu-id="2f541-110">Esta transformación es similar a la transformación Muestreo de porcentaje, que crea un conjunto de datos de ejemplo seleccionando un porcentaje de las filas de entrada.</span><span class="sxs-lookup"><span data-stu-id="2f541-110">This transformation is similar to the Percentage Sampling transformation, which creates a sample dataset by selecting a percentage of the input rows.</span></span> <span data-ttu-id="2f541-111">Consulte [Percentage Sampling Transformation](percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="2f541-111">See [Percentage Sampling Transformation](percentage-sampling-transformation.md).</span></span>  
  
## <a name="configuring-the-row-sampling-transformation"></a><span data-ttu-id="2f541-112">Configurar la transformación Muestreo de fila</span><span class="sxs-lookup"><span data-stu-id="2f541-112">Configuring the Row Sampling Transformation</span></span>  
 <span data-ttu-id="2f541-113">La transformación Muestreo de fila crea un conjunto de datos de ejemplo seleccionando un número especificado de las filas de entrada de la transformación.</span><span class="sxs-lookup"><span data-stu-id="2f541-113">The Row Sampling transformation creates a sample dataset by selecting a specified number of the transformation input rows.</span></span> <span data-ttu-id="2f541-114">Como la selección de filas de la entrada de transformación es aleatoria, la muestra resultante es representativa de la entrada.</span><span class="sxs-lookup"><span data-stu-id="2f541-114">Because the selection of rows from the transformation input is random, the resultant sample is representative of the input.</span></span> <span data-ttu-id="2f541-115">También puede especificar el valor de inicialización que usará el generador de números aleatorios; dicho valor afectará al modo en que la transformación seleccionará filas.</span><span class="sxs-lookup"><span data-stu-id="2f541-115">You can also specify the seed that is used by the random number generator, to affect how the transformation selects rows.</span></span>  
  
 <span data-ttu-id="2f541-116">Si se utiliza el mismo valor de inicialización aleatorio en la misma entrada de la transformación, siempre se creará la misma salida de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f541-116">Using the same random seed on the same transformation input always creates the same sample output.</span></span> <span data-ttu-id="2f541-117">Si no se especifica un valor de inicialización, la transformación utilizará el contador del sistema operativo para crear el número aleatorio.</span><span class="sxs-lookup"><span data-stu-id="2f541-117">If no seed is specified, the transformation uses the tick count of the operating system to create the random number.</span></span> <span data-ttu-id="2f541-118">Por tanto, puede usar el mismo valor de inicialización durante las pruebas, para comprobar los resultados de la transformación durante el desarrollo y las pruebas del paquete, y después cambiarlo por un valor de inicialización aleatorio cuando el paquete pase a producción.</span><span class="sxs-lookup"><span data-stu-id="2f541-118">Therefore, you could use the same seed during testing, to verify the transformation results during the development and testing of the package, and then change to a random seed when the package is moved into production.</span></span>  
  
 <span data-ttu-id="2f541-119">La transformación Muestreo de fila incluye la propiedad personalizada `SamplingValue`.</span><span class="sxs-lookup"><span data-stu-id="2f541-119">The Row Sampling transformation includes the `SamplingValue` custom property.</span></span> <span data-ttu-id="2f541-120">Esta propiedad se puede actualizar a través de una expresión de propiedad, al cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="2f541-120">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="2f541-121">Para más información, vea [Expresiones de Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Usar expresiones de propiedad en paquetes](../../expressions/use-property-expressions-in-packages.md) y [Propiedades personalizadas de transformación](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2f541-121">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="2f541-122">Esta transformación tiene una entrada y dos salidas.</span><span class="sxs-lookup"><span data-stu-id="2f541-122">This transformation has one input and two outputs.</span></span> <span data-ttu-id="2f541-123">No tiene ninguna salida de error.</span><span class="sxs-lookup"><span data-stu-id="2f541-123">It has no error output.</span></span>  
  
 <span data-ttu-id="2f541-124">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="2f541-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="2f541-125">Para obtener más información sobre las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Muestreo de fila**, vea [Editor de transformación Muestreo de fila &#40;página Muestreo&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span><span class="sxs-lookup"><span data-stu-id="2f541-125">For more information about the properties that you can set in the **Row Sampling Transformation Editor** dialog box, see [Row Sampling Transformation Editor &#40;Sampling Page&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span></span>  
  
 <span data-ttu-id="2f541-126">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="2f541-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="2f541-127">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f541-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="2f541-128">Common Properties</span><span class="sxs-lookup"><span data-stu-id="2f541-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="2f541-129">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="2f541-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="2f541-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="2f541-130">Related Tasks</span></span>  
 [<span data-ttu-id="2f541-131">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="2f541-131">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
  
