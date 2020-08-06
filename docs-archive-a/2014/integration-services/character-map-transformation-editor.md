---
title: Editor de transformación mapa de caracteres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactermaptransformation.f1
helpviewer_keywords:
- Character Map Transformation Editor
ms.assetid: 3f1dbcf9-9cca-4606-bdcc-7ea6ad48cdf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c6cdcdba448dafc6ccf03774d4f611dee704b823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670501"
---
# <a name="character-map-transformation-editor"></a><span data-ttu-id="d56b4-102">Editor de transformación Mapa de caracteres</span><span class="sxs-lookup"><span data-stu-id="d56b4-102">Character Map Transformation Editor</span></span>
  <span data-ttu-id="d56b4-103">Use el cuadro de diálogo **Editor de transformación Mapa de caracteres** para seleccionar las funciones de cadena que se van a aplicar a datos de columna y para especificar si la asignación es una modificación en contexto o se agrega como una columna nueva.</span><span class="sxs-lookup"><span data-stu-id="d56b4-103">Use the **Character Map Transformation Editor** dialog box to select the string functions to apply to column data and to specify whether mapping is an in-place change or added as a new column.</span></span>  
  
 <span data-ttu-id="d56b4-104">Para obtener más información acerca de la transformación Mapa de caracteres, vea [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="d56b4-104">To learn more about the Character Map transformation, see [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d56b4-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="d56b4-105">Options</span></span>  
 <span data-ttu-id="d56b4-106">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="d56b4-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="d56b4-107">Use las casillas para seleccionar las columnas que se van a transformar con las funciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="d56b4-107">Use the check boxes to select the columns to transform using string functions.</span></span> <span data-ttu-id="d56b4-108">Las selecciones aparecen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="d56b4-108">Your selections appear in the table below.</span></span>  
  
 <span data-ttu-id="d56b4-109">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="d56b4-109">**Input Column**</span></span>  
 <span data-ttu-id="d56b4-110">Muestra las columnas de entrada seleccionadas de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="d56b4-110">View input columns selected from the table above.</span></span> <span data-ttu-id="d56b4-111">También puede cambiar o quitar una selección utilizando la lista de columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="d56b4-111">You can also change or remove a selection by using the list of available input columns.</span></span>  
  
 <span data-ttu-id="d56b4-112">**Destino**</span><span class="sxs-lookup"><span data-stu-id="d56b4-112">**Destination**</span></span>  
 <span data-ttu-id="d56b4-113">Especifique si se guardan los resultados de las operaciones de cadena en contexto, utilizando la columna existente, o se guardan los datos modificados como una columna nueva.</span><span class="sxs-lookup"><span data-stu-id="d56b4-113">Specify whether to save the results of the string operations in place, using the existing column, or to save the modified data as a new column.</span></span>  
  
|<span data-ttu-id="d56b4-114">Value</span><span class="sxs-lookup"><span data-stu-id="d56b4-114">Value</span></span>|<span data-ttu-id="d56b4-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d56b4-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d56b4-116">Nueva columna</span><span class="sxs-lookup"><span data-stu-id="d56b4-116">New column</span></span>|<span data-ttu-id="d56b4-117">Guardar los datos en una columna nueva.</span><span class="sxs-lookup"><span data-stu-id="d56b4-117">Save the data in a new column.</span></span> <span data-ttu-id="d56b4-118">Asigne el nombre de columna en **Alias de salida**.</span><span class="sxs-lookup"><span data-stu-id="d56b4-118">Assign the column name under **Output Alias**.</span></span>|  
|<span data-ttu-id="d56b4-119">Modificación en contexto</span><span class="sxs-lookup"><span data-stu-id="d56b4-119">In-place change</span></span>|<span data-ttu-id="d56b4-120">Guardar los datos modificados en la columna existente.</span><span class="sxs-lookup"><span data-stu-id="d56b4-120">Save the modified data in the existing column.</span></span>|  
  
 <span data-ttu-id="d56b4-121">**operación**</span><span class="sxs-lookup"><span data-stu-id="d56b4-121">**Operation**</span></span>  
 <span data-ttu-id="d56b4-122">Seleccione de la lista las funciones de cadena que se aplicarán a los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="d56b4-122">Select from the list the string functions to apply to column data.</span></span>  
  
|<span data-ttu-id="d56b4-123">Value</span><span class="sxs-lookup"><span data-stu-id="d56b4-123">Value</span></span>|<span data-ttu-id="d56b4-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="d56b4-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d56b4-125">Minúsculas</span><span class="sxs-lookup"><span data-stu-id="d56b4-125">Lowercase</span></span>|<span data-ttu-id="d56b4-126">Convertir en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d56b4-126">Convert to lower case.</span></span>|  
|<span data-ttu-id="d56b4-127">Uppercase</span><span class="sxs-lookup"><span data-stu-id="d56b4-127">Uppercase</span></span>|<span data-ttu-id="d56b4-128">Convertir en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="d56b4-128">Convert to upper case.</span></span>|  
|<span data-ttu-id="d56b4-129">Inversión de byte</span><span class="sxs-lookup"><span data-stu-id="d56b4-129">Byte reversal</span></span>|<span data-ttu-id="d56b4-130">Convertir invirtiendo el orden de los bytes.</span><span class="sxs-lookup"><span data-stu-id="d56b4-130">Convert by reversing byte order.</span></span>|  
|<span data-ttu-id="d56b4-131">Hiragana</span><span class="sxs-lookup"><span data-stu-id="d56b4-131">Hiragana</span></span>|<span data-ttu-id="d56b4-132">Convertir caracteres japoneses katakana en caracteres hiragana.</span><span class="sxs-lookup"><span data-stu-id="d56b4-132">Convert Japanese katakana characters to hiragana.</span></span>|  
|<span data-ttu-id="d56b4-133">Katakana</span><span class="sxs-lookup"><span data-stu-id="d56b4-133">Katakana</span></span>|<span data-ttu-id="d56b4-134">Convertir caracteres japoneses hiragana en caracteres katakana.</span><span class="sxs-lookup"><span data-stu-id="d56b4-134">Convert Japanese hiragana characters to katakana.</span></span>|  
|<span data-ttu-id="d56b4-135">Formato medio</span><span class="sxs-lookup"><span data-stu-id="d56b4-135">Half width</span></span>|<span data-ttu-id="d56b4-136">Convertir caracteres de formato completo en formato medio.</span><span class="sxs-lookup"><span data-stu-id="d56b4-136">Convert full-width characters to half width.</span></span>|  
|<span data-ttu-id="d56b4-137">Formato completo</span><span class="sxs-lookup"><span data-stu-id="d56b4-137">Full width</span></span>|<span data-ttu-id="d56b4-138">Convertir caracteres de formato medio en formato completo.</span><span class="sxs-lookup"><span data-stu-id="d56b4-138">Convert half-width characters to full width.</span></span>|  
|<span data-ttu-id="d56b4-139">Utilización lingüística de mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="d56b4-139">Linguistic casing</span></span>|<span data-ttu-id="d56b4-140">Aplicar reglas lingüísticas de mayúsculas y minúsculas (asignación de caracteres Unicode simples del turco y otras configuraciones regionales) en vez de otras reglas del sistema.</span><span class="sxs-lookup"><span data-stu-id="d56b4-140">Apply linguistic rules of casing (Unicode simple case mapping for Turkic and other locales) instead of the system rules.</span></span>|  
|<span data-ttu-id="d56b4-141">Chino simplificado</span><span class="sxs-lookup"><span data-stu-id="d56b4-141">Simplified Chinese</span></span>|<span data-ttu-id="d56b4-142">Convertir caracteres de chino tradicional en chino simplificado.</span><span class="sxs-lookup"><span data-stu-id="d56b4-142">Convert traditional Chinese characters to simplified Chinese.</span></span>|  
|<span data-ttu-id="d56b4-143">Chino tradicional</span><span class="sxs-lookup"><span data-stu-id="d56b4-143">Traditional Chinese</span></span>|<span data-ttu-id="d56b4-144">Convertir caracteres de chino simplificado en chino tradicional.</span><span class="sxs-lookup"><span data-stu-id="d56b4-144">Convert simplified Chinese characters to traditional Chinese.</span></span>|  
  
 <span data-ttu-id="d56b4-145">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="d56b4-145">**Output Alias**</span></span>  
 <span data-ttu-id="d56b4-146">Escriba un alias para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="d56b4-146">Type an alias for each output column.</span></span> <span data-ttu-id="d56b4-147">El valor predeterminado es **Copy of** seguido del nombre de la columna de entrada; no obstante, puede elegir un nombre descriptivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="d56b4-147">The default is **Copy of** followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="d56b4-148">**Configurar la salida de errores**</span><span class="sxs-lookup"><span data-stu-id="d56b4-148">**Configure Error Output**</span></span>  
 <span data-ttu-id="d56b4-149">Use el cuadro de diálogo [Configurar la salida de errores](../../2014/integration-services/configure-error-output.md) para especificar las opciones de control de errores de esta transformación.</span><span class="sxs-lookup"><span data-stu-id="d56b4-149">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for this transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d56b4-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d56b4-150">See Also</span></span>  
 [<span data-ttu-id="d56b4-151">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="d56b4-151">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
