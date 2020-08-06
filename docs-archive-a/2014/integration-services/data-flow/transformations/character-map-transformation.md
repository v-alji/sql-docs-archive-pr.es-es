---
title: Transformación Mapa de caracteres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactertrans.f1
helpviewer_keywords:
- mutually exclusive mapping [Integration Services]
- mapping data [Integration Services]
- string functions
- Character Map transformation [Integration Services]
ms.assetid: e0f50eb6-b893-400f-bb8c-fb3072cc2620
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5fc31e1a3500a7a7b023e43a968e70e5b438dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674239"
---
# <a name="character-map-transformation"></a><span data-ttu-id="b70dd-102">Transformación Mapa de caracteres</span><span class="sxs-lookup"><span data-stu-id="b70dd-102">Character Map Transformation</span></span>
  <span data-ttu-id="b70dd-103">La transformación Mapa de caracteres se aplica a funciones de cadena que operan sobre datos de caracteres, como la conversión de minúsculas a mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="b70dd-103">The Character Map transformation applies string functions, such as conversion from lowercase to uppercase, to character data.</span></span> <span data-ttu-id="b70dd-104">Esta transformación solo opera en datos de columnas con un tipo de datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="b70dd-104">This transformation operates only on column data with a string data type.</span></span>  
  
 <span data-ttu-id="b70dd-105">La transformación Mapa de caracteres puede convertir datos de columna in situ o agregar una columna a la salida de transformación y colocar los datos convertidos en la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="b70dd-105">The Character Map transformation can convert column data in place or add a column to the transformation output and put the converted data in the new column.</span></span> <span data-ttu-id="b70dd-106">Puede aplicar distintos conjuntos de operaciones de asignación a la misma columna de entrada y colocar los resultados en columnas diferentes.</span><span class="sxs-lookup"><span data-stu-id="b70dd-106">You can apply different sets of mapping operations to the same input column and put the results in different columns.</span></span> <span data-ttu-id="b70dd-107">Por ejemplo, puede convertir la misma columna a mayúsculas y minúsculas, y almacenar el resultado en dos columnas diferentes.</span><span class="sxs-lookup"><span data-stu-id="b70dd-107">For example, you can convert the same column to uppercase and lowercase and put the results in two different columns.</span></span>  
  
 <span data-ttu-id="b70dd-108">En algunas situaciones, la asignación puede provocar un truncamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="b70dd-108">Mapping can, under some circumstances, cause data to be truncated.</span></span> <span data-ttu-id="b70dd-109">Por ejemplo, se puede producir un truncamiento cuando se asignan caracteres de un byte a caracteres representados con varios bytes.</span><span class="sxs-lookup"><span data-stu-id="b70dd-109">For example, truncation can occur when single-byte characters are mapped to characters with a multibyte representation.</span></span> <span data-ttu-id="b70dd-110">La transformación Mapa de caracteres incluye una salida de error que se puede usar para dirigir los datos truncados a otra salida distinta.</span><span class="sxs-lookup"><span data-stu-id="b70dd-110">The Character Map transformation includes an error output, which can be used to direct truncated data to separate output.</span></span> <span data-ttu-id="b70dd-111">Para más información, vea [Control de errores en los datos](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="b70dd-111">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="b70dd-112">Esta transformación tiene una entrada, una salida y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="b70dd-112">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="mapping-operations"></a><span data-ttu-id="b70dd-113">Operaciones de asignación</span><span class="sxs-lookup"><span data-stu-id="b70dd-113">Mapping Operations</span></span>  
 <span data-ttu-id="b70dd-114">En la siguiente tabla se describen las operaciones de asignación admitidas por la transformación Mapa de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b70dd-114">The following table describes the mapping operations that the Character Map transformation supports.</span></span>  
  
|<span data-ttu-id="b70dd-115">Operación</span><span class="sxs-lookup"><span data-stu-id="b70dd-115">Operation</span></span>|<span data-ttu-id="b70dd-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b70dd-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b70dd-117">Inversión de byte</span><span class="sxs-lookup"><span data-stu-id="b70dd-117">Byte reversal</span></span>|<span data-ttu-id="b70dd-118">Invierte el orden de los bytes.</span><span class="sxs-lookup"><span data-stu-id="b70dd-118">Reverses byte order.</span></span>|  
|<span data-ttu-id="b70dd-119">Formato completo</span><span class="sxs-lookup"><span data-stu-id="b70dd-119">Full width</span></span>|<span data-ttu-id="b70dd-120">Asigna caracteres de formato medio a caracteres de formato completo.</span><span class="sxs-lookup"><span data-stu-id="b70dd-120">Maps half-width characters to full-width characters.</span></span>|  
|<span data-ttu-id="b70dd-121">Formato medio</span><span class="sxs-lookup"><span data-stu-id="b70dd-121">Half width</span></span>|<span data-ttu-id="b70dd-122">Asigna caracteres de formato completo a caracteres de formato medio.</span><span class="sxs-lookup"><span data-stu-id="b70dd-122">Maps full-width characters to half-width characters.</span></span>|  
|<span data-ttu-id="b70dd-123">Hiragana</span><span class="sxs-lookup"><span data-stu-id="b70dd-123">Hiragana</span></span>|<span data-ttu-id="b70dd-124">Asigna caracteres katakana a caracteres hiragana.</span><span class="sxs-lookup"><span data-stu-id="b70dd-124">Maps katakana characters to hiragana characters.</span></span>|  
|<span data-ttu-id="b70dd-125">Katakana</span><span class="sxs-lookup"><span data-stu-id="b70dd-125">Katakana</span></span>|<span data-ttu-id="b70dd-126">Asigna caracteres hiragana a caracteres katakana.</span><span class="sxs-lookup"><span data-stu-id="b70dd-126">Maps hiragana characters to katakana characters.</span></span>|  
|<span data-ttu-id="b70dd-127">Utilización lingüística de mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="b70dd-127">Linguistic casing</span></span>|<span data-ttu-id="b70dd-128">Aplica la utilización lingüística de mayúsculas y minúsculas en lugar de las reglas del sistema.</span><span class="sxs-lookup"><span data-stu-id="b70dd-128">Applies linguistic casing instead of the system rules.</span></span> <span data-ttu-id="b70dd-129">La utilización lingüística de mayúsculas y minúsculas se refiere a la funcionalidad ofrecida por la API de Win32 para la asignación de caracteres Unicode simples del turco y otras configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="b70dd-129">Linguistic casing refers to functionality provided by the Win32 API for Unicode simple case mapping of Turkic and other locales.</span></span>|  
|<span data-ttu-id="b70dd-130">Minúsculas</span><span class="sxs-lookup"><span data-stu-id="b70dd-130">Lowercase</span></span>|<span data-ttu-id="b70dd-131">Conversión de caracteres a minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b70dd-131">Converts characters to lowercase.</span></span>|  
|<span data-ttu-id="b70dd-132">Chino simplificado</span><span class="sxs-lookup"><span data-stu-id="b70dd-132">Simplified Chinese</span></span>|<span data-ttu-id="b70dd-133">Asigna caracteres de chino tradicional a caracteres de chino simplificado.</span><span class="sxs-lookup"><span data-stu-id="b70dd-133">Maps traditional Chinese characters to simplified Chinese characters.</span></span>|  
|<span data-ttu-id="b70dd-134">Chino tradicional</span><span class="sxs-lookup"><span data-stu-id="b70dd-134">Traditional Chinese</span></span>|<span data-ttu-id="b70dd-135">Asigna caracteres de chino simplificado a caracteres de chino tradicional.</span><span class="sxs-lookup"><span data-stu-id="b70dd-135">Maps simplified Chinese characters to traditional Chinese characters.</span></span>|  
|<span data-ttu-id="b70dd-136">Uppercase</span><span class="sxs-lookup"><span data-stu-id="b70dd-136">Uppercase</span></span>|<span data-ttu-id="b70dd-137">Conversión de caracteres a mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="b70dd-137">Converts characters to uppercase.</span></span>|  
  
## <a name="mutually-exclusive-mapping-operations"></a><span data-ttu-id="b70dd-138">Operaciones de asignación mutuamente exclusivas</span><span class="sxs-lookup"><span data-stu-id="b70dd-138">Mutually Exclusive Mapping Operations</span></span>  
 <span data-ttu-id="b70dd-139">En una transformación pueden realizarse varias operaciones.</span><span class="sxs-lookup"><span data-stu-id="b70dd-139">More than one operation can be performed in a transformation.</span></span> <span data-ttu-id="b70dd-140">Sin embargo, algunas operaciones son mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="b70dd-140">However, some mapping operations are mutually exclusive.</span></span> <span data-ttu-id="b70dd-141">La siguiente tabla enumera las restricciones que se aplican al usar varias operaciones sobre la misma columna.</span><span class="sxs-lookup"><span data-stu-id="b70dd-141">The following table lists restrictions that apply when you use multiple operations on the same column.</span></span> <span data-ttu-id="b70dd-142">Las operaciones sobre las columnas Operación A y Operación B son mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="b70dd-142">Operations in the columns Operation A and Operation B are mutually exclusive.</span></span>  
  
|<span data-ttu-id="b70dd-143">Operación A</span><span class="sxs-lookup"><span data-stu-id="b70dd-143">Operation A</span></span>|<span data-ttu-id="b70dd-144">Operación B</span><span class="sxs-lookup"><span data-stu-id="b70dd-144">Operation B</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b70dd-145">Minúsculas</span><span class="sxs-lookup"><span data-stu-id="b70dd-145">Lowercase</span></span>|<span data-ttu-id="b70dd-146">Uppercase</span><span class="sxs-lookup"><span data-stu-id="b70dd-146">Uppercase</span></span>|  
|<span data-ttu-id="b70dd-147">Hiragana</span><span class="sxs-lookup"><span data-stu-id="b70dd-147">Hiragana</span></span>|<span data-ttu-id="b70dd-148">Katakana</span><span class="sxs-lookup"><span data-stu-id="b70dd-148">Katakana</span></span>|  
|<span data-ttu-id="b70dd-149">Formato medio</span><span class="sxs-lookup"><span data-stu-id="b70dd-149">Half width</span></span>|<span data-ttu-id="b70dd-150">Formato completo</span><span class="sxs-lookup"><span data-stu-id="b70dd-150">Full width</span></span>|  
|<span data-ttu-id="b70dd-151">Chino tradicional</span><span class="sxs-lookup"><span data-stu-id="b70dd-151">Traditional Chinese</span></span>|<span data-ttu-id="b70dd-152">Chino simplificado</span><span class="sxs-lookup"><span data-stu-id="b70dd-152">Simplified Chinese</span></span>|  
|<span data-ttu-id="b70dd-153">Minúsculas</span><span class="sxs-lookup"><span data-stu-id="b70dd-153">Lowercase</span></span>|<span data-ttu-id="b70dd-154">Hiragana, katakana, formato medio, formato completo</span><span class="sxs-lookup"><span data-stu-id="b70dd-154">Hiragana, katakana, half width, full width</span></span>|  
|<span data-ttu-id="b70dd-155">Uppercase</span><span class="sxs-lookup"><span data-stu-id="b70dd-155">Uppercase</span></span>|<span data-ttu-id="b70dd-156">Hiragana, katakana, formato medio, formato completo</span><span class="sxs-lookup"><span data-stu-id="b70dd-156">Hiragana, katakana, half width, full width</span></span>|  
  
## <a name="configuration-of-the-character-map-transformation"></a><span data-ttu-id="b70dd-157">Configuración de la transformación Mapa de caracteres</span><span class="sxs-lookup"><span data-stu-id="b70dd-157">Configuration of the Character Map Transformation</span></span>  
 <span data-ttu-id="b70dd-158">Puede configurar la transformación Mapa de caracteres de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="b70dd-158">You configure the Character Map transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="b70dd-159">Especificar las columnas que desea convertir.</span><span class="sxs-lookup"><span data-stu-id="b70dd-159">Specify the columns to convert.</span></span>  
  
-   <span data-ttu-id="b70dd-160">Especificar las operaciones que desea aplicar a cada columna.</span><span class="sxs-lookup"><span data-stu-id="b70dd-160">Specify the operations to apply to each column.</span></span>  
  
 <span data-ttu-id="b70dd-161">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b70dd-161">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b70dd-162">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Mapa de caracteres** , vea [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b70dd-162">For more information about the properties that you can set in the **Character Map Transformation Editor** dialog box, see [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="b70dd-163">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b70dd-163">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="b70dd-164">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b70dd-164">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b70dd-165">Common Properties</span><span class="sxs-lookup"><span data-stu-id="b70dd-165">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="b70dd-166">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="b70dd-166">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="b70dd-167">Para obtener más información sobre cómo establecer valores de propiedades, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b70dd-167">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b70dd-168">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="b70dd-168">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="b70dd-169">Ordenación de datos para las transformaciones Mezclar y Combinación de mezcla</span><span class="sxs-lookup"><span data-stu-id="b70dd-169">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
  
