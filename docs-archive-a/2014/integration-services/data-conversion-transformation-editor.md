---
title: Editor de transformación conversión de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontransformation.f1
helpviewer_keywords:
- Data Conversion Transformation Editor
ms.assetid: 7b4e4873-e8fe-4549-a965-65bebdb270bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4b893f04dcca2dd2a1a5874b55c1c1c608aaeb12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751373"
---
# <a name="data-conversion-transformation-editor"></a><span data-ttu-id="0c438-102">Editor de transformación Conversión de datos</span><span class="sxs-lookup"><span data-stu-id="0c438-102">Data Conversion Transformation Editor</span></span>
  <span data-ttu-id="0c438-103">Use el cuadro de diálogo **Editor de transformación Conversión de datos** para seleccionar las columnas que desea convertir, seleccione el tipo de datos al que desea convertir la columna y establezca los atributos de conversión.</span><span class="sxs-lookup"><span data-stu-id="0c438-103">Use the **Data Conversion Transformation Editor** dialog box to select the columns to convert, select the data type to which the column is converted, and set conversion attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c438-104">La `FastParse` propiedad de las columnas de salida de la transformación conversión de datos no está disponible en el **Editor de transformación conversión de datos**, pero se puede establecer mediante el **editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="0c438-104">The `FastParse` property of the output columns of the Data Conversion transformation is not available in the **Data Conversion Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="0c438-105">Para obtener más información acerca de esta propiedad, vea la sección sobre la transformación Conversión de datos en [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0c438-105">For more information on this property, see the Data Conversion Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="0c438-106">Para obtener más información acerca de la transformación Conversión de datos, vea [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="0c438-106">To learn more about the Data Conversion transformation, see [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0c438-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="0c438-107">Options</span></span>  
 <span data-ttu-id="0c438-108">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="0c438-108">**Available Input Columns**</span></span>  
 <span data-ttu-id="0c438-109">Seleccione, mediante las casillas, las columnas que desea convertir.</span><span class="sxs-lookup"><span data-stu-id="0c438-109">Select columns to convert by using the check boxes.</span></span> <span data-ttu-id="0c438-110">Las selecciones agregan columnas de entrada a la tabla que aparece debajo.</span><span class="sxs-lookup"><span data-stu-id="0c438-110">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="0c438-111">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="0c438-111">**Input Column**</span></span>  
 <span data-ttu-id="0c438-112">Seleccione las columnas que desea convertir en la lista de columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="0c438-112">Select columns to convert from the list of available input columns.</span></span> <span data-ttu-id="0c438-113">Su selección se refleja en las selecciones de las anteriores casillas.</span><span class="sxs-lookup"><span data-stu-id="0c438-113">Your selections are reflected in the check box selections above.</span></span>  
  
 <span data-ttu-id="0c438-114">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="0c438-114">**Output Alias**</span></span>  
 <span data-ttu-id="0c438-115">Escriba un alias para cada columna nueva.</span><span class="sxs-lookup"><span data-stu-id="0c438-115">Type an alias for each new column.</span></span> <span data-ttu-id="0c438-116">El valor predeterminado es `Copy of` seguido del nombre de la columna de entrada; no obstante, puede elegir un nombre descriptivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="0c438-116">The default is `Copy of` followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="0c438-117">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0c438-117">**Data Type**</span></span>  
 <span data-ttu-id="0c438-118">Seleccione en la lista un tipo de datos disponible.</span><span class="sxs-lookup"><span data-stu-id="0c438-118">Select an available data type from the list.</span></span> <span data-ttu-id="0c438-119">Para obtener más información, vea [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0c438-119">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="0c438-120">**Longitud**</span><span class="sxs-lookup"><span data-stu-id="0c438-120">**Length**</span></span>  
 <span data-ttu-id="0c438-121">Establezca la longitud de la columna para los datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="0c438-121">Set the column length for string data.</span></span>  
  
 <span data-ttu-id="0c438-122">**Precisión**</span><span class="sxs-lookup"><span data-stu-id="0c438-122">**Precision**</span></span>  
 <span data-ttu-id="0c438-123">Establezca la precisión para los datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="0c438-123">Set the precision for numeric data.</span></span>  
  
 <span data-ttu-id="0c438-124">**Escala**</span><span class="sxs-lookup"><span data-stu-id="0c438-124">**Scale**</span></span>  
 <span data-ttu-id="0c438-125">Establezca la escala para los datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="0c438-125">Set the scale for numeric data.</span></span>  
  
 <span data-ttu-id="0c438-126">**Página de códigos**</span><span class="sxs-lookup"><span data-stu-id="0c438-126">**Code page**</span></span>  
 <span data-ttu-id="0c438-127">Seleccione la página de códigos adecuada para las columnas de tipo DT_STR.</span><span class="sxs-lookup"><span data-stu-id="0c438-127">Select the appropriate code page for columns of type DT_STR.</span></span>  
  
 <span data-ttu-id="0c438-128">**Configurar la salida de errores**</span><span class="sxs-lookup"><span data-stu-id="0c438-128">**Configure error output**</span></span>  
 <span data-ttu-id="0c438-129">Especifique cómo controlar los errores de nivel de fila con el cuadro de diálogo [Configurar la salida de errores](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="0c438-129">Specify how to handle row-level errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c438-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c438-130">See Also</span></span>  
 <span data-ttu-id="0c438-131">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0c438-131">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="0c438-132">Convertir datos en un tipo de datos diferente mediante la transformación Conversión de datos</span><span class="sxs-lookup"><span data-stu-id="0c438-132">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>](data-flow/transformations/convert-data-type-by-using-data-conversion-transformation.md)  
  
  
