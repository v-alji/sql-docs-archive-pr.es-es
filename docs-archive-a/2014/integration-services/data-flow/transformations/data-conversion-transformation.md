---
title: Transformación Conversión de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontrans.f1
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: fd515bbc-6f49-4d0c-ae7f-6ea3c3f24a1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57b1f70c070cdf81dc0bc899ed365d048db26cc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663037"
---
# <a name="data-conversion-transformation"></a><span data-ttu-id="f5a20-102">Conversión de datos, transformación</span><span class="sxs-lookup"><span data-stu-id="f5a20-102">Data Conversion Transformation</span></span>
  <span data-ttu-id="f5a20-103">La transformación Conversión de datos convierte los datos de una columna de entrada a otro tipo de datos diferente y después los copia a una nueva columna de salida.</span><span class="sxs-lookup"><span data-stu-id="f5a20-103">The Data Conversion transformation converts the data in an input column to a different data type and then copies it to a new output column.</span></span> <span data-ttu-id="f5a20-104">Por ejemplo, un paquete puede extraer los datos de diferentes orígenes y después usar esta transformación para convertir las columnas al tipo de datos necesario para el almacén de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="f5a20-104">For example, a package can extract data from multiple sources, and then use this transformation to convert columns to the data type required by the destination data store.</span></span> <span data-ttu-id="f5a20-105">Puede aplicar múltiples conversiones a una sola columna de entrada.</span><span class="sxs-lookup"><span data-stu-id="f5a20-105">You can apply multiple conversions to a single input column.</span></span>  
  
 <span data-ttu-id="f5a20-106">Un paquete puede utilizar esta transformación para realizar las siguientes conversiones de tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="f5a20-106">Using this transformation, a package can perform the following types of data conversions:</span></span>  
  
-   <span data-ttu-id="f5a20-107">Cambiar el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f5a20-107">Change the data type.</span></span> <span data-ttu-id="f5a20-108">Para obtener más información, vea [Integration Services Data Types](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f5a20-108">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f5a20-109">Si va a convertir datos a un tipo de datos de fecha o de fecha y hora, la fecha de la columna de salida tiene el formato ISO, aunque las preferencias de la configuración regional especifiquen un formato diferente.</span><span class="sxs-lookup"><span data-stu-id="f5a20-109">If you are converting data to a date or a datetime data type, the date in the output column is in the ISO format, although the locale preference may specify a different format.</span></span>  
  
-   <span data-ttu-id="f5a20-110">Establecer la longitud de la columna de los datos de cadena así como la precisión y la escala de los datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="f5a20-110">Set the column length of string data and the precision and scale on numeric data.</span></span> <span data-ttu-id="f5a20-111">Para más información, vea [Precisión, escala y longitud &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f5a20-111">For more information, see [Precision, Scale, and Length &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span></span>  
  
-   <span data-ttu-id="f5a20-112">Especificar una página de códigos.</span><span class="sxs-lookup"><span data-stu-id="f5a20-112">Specify a code page.</span></span> <span data-ttu-id="f5a20-113">Para más información, consulte [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="f5a20-113">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f5a20-114">Al copiar datos entre columnas con un tipo de datos de cadena, las dos columnas deben usar la misma página de códigos.</span><span class="sxs-lookup"><span data-stu-id="f5a20-114">When copying between columns with a string data type, the two columns must use the same code page.</span></span>  
  
 <span data-ttu-id="f5a20-115">Si la longitud de una columna de salida de datos de tipo cadena es menor que la longitud de la columna de entrada correspondiente, se truncarán los datos de salida.</span><span class="sxs-lookup"><span data-stu-id="f5a20-115">If the length of an output column of string data is shorter than the length of its corresponding input column, the output data is truncated.</span></span> <span data-ttu-id="f5a20-116">Para más información, vea [Control de errores en los datos](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="f5a20-116">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="f5a20-117">Esta transformación tiene una entrada, una salida y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="f5a20-117">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f5a20-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f5a20-118">Related Tasks</span></span>  
 <span data-ttu-id="f5a20-119">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f5a20-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="f5a20-120">Para más información sobre cómo usar la transformación Conversión de datos en el Diseñador SSIS, vea [Convertir datos en un tipo de datos diferente mediante la transformación Conversión de datos](data-conversion-transformation.md) y [Editor de transformación Conversión de datos](../../data-conversion-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f5a20-120">For information about using the Data Conversion Transformation in the SSIS Designer, see [Convert Data to a Different Data Type by Using the Data Conversion Transformation](data-conversion-transformation.md) and [Data Conversion Transformation Editor](../../data-conversion-transformation-editor.md).</span></span> <span data-ttu-id="f5a20-121">Para más información sobre cómo establecer las propiedades de esta transformación mediante programación, vea [Propiedades comunes](../../common-properties.md) y [Propiedades personalizadas de transformación](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f5a20-121">For information about setting properties of this transformation programmatically, see [Common Properties](../../common-properties.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="f5a20-122">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f5a20-122">Related Content</span></span>  
 <span data-ttu-id="f5a20-123">Entrada de blog, sobre la [comparación de rendimiento entre las técnicas de conversión de tipos de datos en SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="f5a20-123">Blog entry, [Performance Comparison between Data Type Conversion Techniques in SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a20-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5a20-124">See Also</span></span>  
 <span data-ttu-id="f5a20-125">[Análisis rápido](../../fast-parse.md) </span><span class="sxs-lookup"><span data-stu-id="f5a20-125">[Fast Parse](../../fast-parse.md) </span></span>  
 <span data-ttu-id="f5a20-126">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="f5a20-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="f5a20-127">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="f5a20-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
