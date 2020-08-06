---
title: Propiedades personalizadas de archivo plano | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f2caeab-784c-4b0c-9b3e-6a88d1ccdbf9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b906e9268bf3a74ffcf5661953397ad7a24b77a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751318"
---
# <a name="flat-file-custom-properties"></a><span data-ttu-id="6b294-102">Propiedades personalizadas de archivo plano</span><span class="sxs-lookup"><span data-stu-id="6b294-102">Flat File Custom Properties</span></span>
  <span data-ttu-id="6b294-103">**Propiedades personalizadas de origen**</span><span class="sxs-lookup"><span data-stu-id="6b294-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="6b294-104">El origen de archivo plano tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6b294-104">The Flat File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="6b294-105">En la tabla siguiente se describen las propiedades personalizadas del origen de archivo plano.</span><span class="sxs-lookup"><span data-stu-id="6b294-105">The following table describes the custom properties of the Flat File source.</span></span> <span data-ttu-id="6b294-106">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="6b294-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="6b294-107">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="6b294-107">Property name</span></span>|<span data-ttu-id="6b294-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6b294-108">Data Type</span></span>|<span data-ttu-id="6b294-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b294-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="6b294-110">FileNameColumnName</span><span class="sxs-lookup"><span data-stu-id="6b294-110">FileNameColumnName</span></span>|<span data-ttu-id="6b294-111">String</span><span class="sxs-lookup"><span data-stu-id="6b294-111">String</span></span>|<span data-ttu-id="6b294-112">Nombre de una columna de salida que contiene el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="6b294-112">The name of an output column that contains the file name.</span></span> <span data-ttu-id="6b294-113">Si no se especifica ningún nombre, se generará ninguna columna de salida que contenga el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="6b294-113">If no name is specified, no output column containing the file name will be generated.</span></span><br /><br /> <span data-ttu-id="6b294-114">Nota: Esta propiedad no está disponible en el **Editor de origen de archivos planos**, pero se puede establecer mediante el **Editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="6b294-114">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
|<span data-ttu-id="6b294-115">RetainNulls</span><span class="sxs-lookup"><span data-stu-id="6b294-115">RetainNulls</span></span>|<span data-ttu-id="6b294-116">Boolean</span><span class="sxs-lookup"><span data-stu-id="6b294-116">Boolean</span></span>|<span data-ttu-id="6b294-117">Valor que especifica si retener los valores Null del archivo de origen como tales cuando el motor de canalización de transformación de datos procesa los datos.</span><span class="sxs-lookup"><span data-stu-id="6b294-117">A value that specifies whether to retain Null values from the source file as Null values when the data is processed by the Data Transformation Pipeline engine.</span></span> <span data-ttu-id="6b294-118">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="6b294-118">The default value of this property is `False`.</span></span>|  
  
 <span data-ttu-id="6b294-119">La salida del origen de archivo plano no tiene ninguna propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="6b294-119">The output of the Flat File source has no custom properties.</span></span>  
  
 <span data-ttu-id="6b294-120">En la tabla siguiente se describen las propiedades personalizadas de las columnas de salida del origen de archivo plano.</span><span class="sxs-lookup"><span data-stu-id="6b294-120">The following table describes the custom properties of the output columns of the Flat File source.</span></span> <span data-ttu-id="6b294-121">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="6b294-121">All properties are read/write.</span></span>  
  
|<span data-ttu-id="6b294-122">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="6b294-122">Property name</span></span>|<span data-ttu-id="6b294-123">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6b294-123">Data Type</span></span>|<span data-ttu-id="6b294-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b294-124">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="6b294-125">FastParse</span><span class="sxs-lookup"><span data-stu-id="6b294-125">FastParse</span></span>|<span data-ttu-id="6b294-126">Boolean</span><span class="sxs-lookup"><span data-stu-id="6b294-126">Boolean</span></span>|<span data-ttu-id="6b294-127">Valor que indica si la columna usa las rutinas de análisis más rápidas que no distinguen la configuración regional y permiten un análisis rápido que DTS proporciona, o las rutinas de análisis estándar que sí distinguen la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="6b294-127">A value that indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that DTS provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="6b294-128">Para obtener más información, consulte [Fast Parse](../fast-parse.md) y [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="6b294-128">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span> <span data-ttu-id="6b294-129">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="6b294-129">The default value of this property is `False`.</span></span><br /><br /> <span data-ttu-id="6b294-130">Nota: Esta propiedad no está disponible en el **Editor de origen de archivos planos**, pero se puede establecer mediante el **Editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="6b294-130">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
  
 <span data-ttu-id="6b294-131">Para más información, consulte [Flat File Source](flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="6b294-131">For more information, see [Flat File Source](flat-file-source.md).</span></span>  
  
 <span data-ttu-id="6b294-132">**Propiedades personalizadas de los destinos**</span><span class="sxs-lookup"><span data-stu-id="6b294-132">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="6b294-133">El destino de archivo plano tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6b294-133">The Flat File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="6b294-134">En la tabla siguiente se describen las propiedades personalizadas del destino Archivo plano.</span><span class="sxs-lookup"><span data-stu-id="6b294-134">The following table describes the custom properties of the Flat File destination.</span></span> <span data-ttu-id="6b294-135">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="6b294-135">All properties are read/write.</span></span>  
  
|<span data-ttu-id="6b294-136">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="6b294-136">Property name</span></span>|<span data-ttu-id="6b294-137">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6b294-137">Data Type</span></span>|<span data-ttu-id="6b294-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b294-138">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="6b294-139">Encabezado</span><span class="sxs-lookup"><span data-stu-id="6b294-139">Header</span></span>|<span data-ttu-id="6b294-140">String</span><span class="sxs-lookup"><span data-stu-id="6b294-140">String</span></span>|<span data-ttu-id="6b294-141">Bloque de texto que se inserta en el archivo antes de que se escriban datos.</span><span class="sxs-lookup"><span data-stu-id="6b294-141">A block of text that is inserted in the file before any data is written.</span></span><br /><br /> <span data-ttu-id="6b294-142">Puede especificar el valor de esta propiedad con una expresión de propiedad.</span><span class="sxs-lookup"><span data-stu-id="6b294-142">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="6b294-143">Sobrescribir</span><span class="sxs-lookup"><span data-stu-id="6b294-143">Overwrite</span></span>|<span data-ttu-id="6b294-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="6b294-144">Boolean</span></span>|<span data-ttu-id="6b294-145">Valor que especifica si sobrescribir o anexar a un archivo de destino existente que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="6b294-145">A value that specifies whether to overwrite or append to an existing destination file that has the same name.</span></span> <span data-ttu-id="6b294-146">El valor predeterminado de esta propiedad es `True`.</span><span class="sxs-lookup"><span data-stu-id="6b294-146">The default value of this property is `True`.</span></span>|  
  
 <span data-ttu-id="6b294-147">La entrada y las columnas de entrada del destino de archivo plano no tienen ninguna propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="6b294-147">The input and the input columns of the Flat File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="6b294-148">Para más información, consulte [Flat File Destination](flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="6b294-148">For more information, see [Flat File Destination](flat-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b294-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b294-149">See Also</span></span>  
 [<span data-ttu-id="6b294-150">Common Properties</span><span class="sxs-lookup"><span data-stu-id="6b294-150">Common Properties</span></span>](../common-properties.md)  
  
  
