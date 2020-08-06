---
title: Propiedades personalizadas de archivo sin formato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7e81f7e1-fac0-4b57-b145-8f1b9e4720bf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7614c03fbf44f37597e586549e306d01c28b523d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670463"
---
# <a name="raw-file-custom-properties"></a><span data-ttu-id="933e4-102">Propiedades personalizadas de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="933e4-102">Raw File Custom Properties</span></span>
  <span data-ttu-id="933e4-103">**Propiedades personalizadas de origen**</span><span class="sxs-lookup"><span data-stu-id="933e4-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="933e4-104">El origen de archivo sin formato tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="933e4-104">The Raw File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="933e4-105">En la tabla siguiente se describen las propiedades personalizadas del origen de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="933e4-105">The following table describes the custom properties of the Raw File source.</span></span> <span data-ttu-id="933e4-106">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="933e4-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="933e4-107">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="933e4-107">Property name</span></span>|<span data-ttu-id="933e4-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="933e4-108">Data Type</span></span>|<span data-ttu-id="933e4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="933e4-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="933e4-110">AccessMode</span><span class="sxs-lookup"><span data-stu-id="933e4-110">AccessMode</span></span>|<span data-ttu-id="933e4-111">Integer (enumeración)</span><span class="sxs-lookup"><span data-stu-id="933e4-111">Integer (enumeration)</span></span>|<span data-ttu-id="933e4-112">Modo que se usa para tener acceso a los datos sin formato.</span><span class="sxs-lookup"><span data-stu-id="933e4-112">The mode used to access the raw data.</span></span> <span data-ttu-id="933e4-113">Los valores posibles son `File name` (0) y `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="933e4-113">The possible values are `File name` (0) and `File name from variable` (1).</span></span> <span data-ttu-id="933e4-114">El valor predeterminado es `File name` (0).</span><span class="sxs-lookup"><span data-stu-id="933e4-114">The default value is `File name` (0).</span></span>|  
|<span data-ttu-id="933e4-115">FileName</span><span class="sxs-lookup"><span data-stu-id="933e4-115">FileName</span></span>|<span data-ttu-id="933e4-116">String</span><span class="sxs-lookup"><span data-stu-id="933e4-116">String</span></span>|<span data-ttu-id="933e4-117">Ruta de acceso y nombre del archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="933e4-117">The path and file name of the source file.</span></span>|  
  
 <span data-ttu-id="933e4-118">La salida y las columnas de salida del origen de archivo sin formato no tienen ninguna propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="933e4-118">The output and the output columns of the Raw File source have no custom properties.</span></span>  
  
 <span data-ttu-id="933e4-119">Para más información, consulte [Raw File Source](raw-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="933e4-119">For more information, see [Raw File Source](raw-file-source.md).</span></span>  
  
 <span data-ttu-id="933e4-120">**Propiedades personalizadas de los destinos**</span><span class="sxs-lookup"><span data-stu-id="933e4-120">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="933e4-121">El destino de archivo sin formato tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="933e4-121">The Raw File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="933e4-122">En la tabla siguiente se describen las propiedades personalizadas del destino de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="933e4-122">The following table describes the custom properties of the Raw File destination.</span></span> <span data-ttu-id="933e4-123">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="933e4-123">All properties are read/write.</span></span>  
  
|<span data-ttu-id="933e4-124">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="933e4-124">Property name</span></span>|<span data-ttu-id="933e4-125">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="933e4-125">Data Type</span></span>|<span data-ttu-id="933e4-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="933e4-126">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="933e4-127">AccessMode</span><span class="sxs-lookup"><span data-stu-id="933e4-127">AccessMode</span></span>|<span data-ttu-id="933e4-128">Integer (enumeración)</span><span class="sxs-lookup"><span data-stu-id="933e4-128">Integer (enumeration)</span></span>|<span data-ttu-id="933e4-129">Valor que especifica si la propiedad FileName contiene un nombre de archivo o el nombre de una variable que contiene un nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="933e4-129">A value that specifies whether the FileName property contains a file name, or the name of a variable that contains a file name.</span></span> <span data-ttu-id="933e4-130">Las opciones son `File name` (0) y `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="933e4-130">The options are `File name` (0) and `File name from variable` (1).</span></span>|  
|<span data-ttu-id="933e4-131">FileName</span><span class="sxs-lookup"><span data-stu-id="933e4-131">FileName</span></span>|<span data-ttu-id="933e4-132">String</span><span class="sxs-lookup"><span data-stu-id="933e4-132">String</span></span>|<span data-ttu-id="933e4-133">Nombre del archivo donde escribe el destino de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="933e4-133">The name of the file to which the Raw File destination writes.</span></span>|  
|<span data-ttu-id="933e4-134">WriteOption</span><span class="sxs-lookup"><span data-stu-id="933e4-134">WriteOption</span></span>|<span data-ttu-id="933e4-135">Integer (enumeración)</span><span class="sxs-lookup"><span data-stu-id="933e4-135">Integer (enumeration)</span></span>|<span data-ttu-id="933e4-136">Valor que especifica si el destino de archivo sin formato elimina un archivo existente que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="933e4-136">A value that specifies whether the Raw File destination deletes an existing file that has the same name.</span></span> <span data-ttu-id="933e4-137">Las opciones son `Create Always` (0), `Create Once` (1), `Truncate and Append` (3) y `Append` (2).</span><span class="sxs-lookup"><span data-stu-id="933e4-137">The options are `Create Always` (0), `Create Once` (1), `Truncate and Append` (3), and `Append` (2).</span></span> <span data-ttu-id="933e4-138">El valor predeterminado de esta propiedad es `Create Always` (0).</span><span class="sxs-lookup"><span data-stu-id="933e4-138">The default value of this property is `Create Always` (0).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="933e4-139">Una operación de anexión requiere que los metadatos de los datos anexados coincidan con los metadatos de los datos que ya están en el archivo.</span><span class="sxs-lookup"><span data-stu-id="933e4-139">An append operation requires the metadata of the appended data to match the metadata of the data already present in the file.</span></span>  
  
 <span data-ttu-id="933e4-140">La entrada y las columnas de entrada del destino de archivo sin formato no tienen ninguna propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="933e4-140">The input and the input columns of the Raw File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="933e4-141">Para más información, consulte [Raw File Destination](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="933e4-141">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="933e4-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="933e4-142">See Also</span></span>  
 [<span data-ttu-id="933e4-143">Common Properties</span><span class="sxs-lookup"><span data-stu-id="933e4-143">Common Properties</span></span>](../common-properties.md)  
  
  
