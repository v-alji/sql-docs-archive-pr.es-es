---
title: Propiedades personalizadas del origen XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eb29b28c-3159-41ec-b3d7-fce5b2f2be55
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e152b23b4f59ca46cb8272ca677dc1161b3efec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676066"
---
# <a name="xml-source-custom-properties"></a><span data-ttu-id="2b1c8-102">Propiedades personalizadas del origen XML</span><span class="sxs-lookup"><span data-stu-id="2b1c8-102">XML Source Custom Properties</span></span>
  <span data-ttu-id="2b1c8-103">El origen XML tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-103">The XML source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="2b1c8-104">En la tabla siguiente se describen las propiedades personalizadas del origen XML.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-104">The following table describes the custom properties of the XML source.</span></span> <span data-ttu-id="2b1c8-105">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-105">All properties are read/write.</span></span>  
  
|<span data-ttu-id="2b1c8-106">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="2b1c8-106">Property name</span></span>|<span data-ttu-id="2b1c8-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2b1c8-107">Data Type</span></span>|<span data-ttu-id="2b1c8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b1c8-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="2b1c8-109">AccessMode</span><span class="sxs-lookup"><span data-stu-id="2b1c8-109">AccessMode</span></span>|<span data-ttu-id="2b1c8-110">Entero</span><span class="sxs-lookup"><span data-stu-id="2b1c8-110">Integer</span></span>|<span data-ttu-id="2b1c8-111">Modo que se usa para tener acceso los datos XML.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-111">The mode used to access the XML data.</span></span>|  
|<span data-ttu-id="2b1c8-112">UseInlineSchema</span><span class="sxs-lookup"><span data-stu-id="2b1c8-112">UseInlineSchema</span></span>|<span data-ttu-id="2b1c8-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="2b1c8-113">Boolean</span></span>|<span data-ttu-id="2b1c8-114">Valor que indica si se usa una definición de esquema insertada dentro del origen XML.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-114">A value that indicates whether to use an inline schema definition within the XML source.</span></span> <span data-ttu-id="2b1c8-115">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-115">The default value of this property is `False`.</span></span>|  
|<span data-ttu-id="2b1c8-116">XMLDATA</span><span class="sxs-lookup"><span data-stu-id="2b1c8-116">XMLData</span></span>|<span data-ttu-id="2b1c8-117">String</span><span class="sxs-lookup"><span data-stu-id="2b1c8-117">String</span></span>|<span data-ttu-id="2b1c8-118">Archivo o variables desde las que recuperar los datos XML.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-118">The file or variables from which to retrieve the XML data.</span></span><br /><br /> <span data-ttu-id="2b1c8-119">Puede especificar el valor de esta propiedad con una expresión de propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-119">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="2b1c8-120">XMLSchemaDefinition</span><span class="sxs-lookup"><span data-stu-id="2b1c8-120">XMLSchemaDefinition</span></span>|<span data-ttu-id="2b1c8-121">String</span><span class="sxs-lookup"><span data-stu-id="2b1c8-121">String</span></span>|<span data-ttu-id="2b1c8-122">Ruta de acceso y nombre del archivo de definición de esquema (.xsd).</span><span class="sxs-lookup"><span data-stu-id="2b1c8-122">The path and file name of the schema definition file (.xsd).</span></span><br /><br /> <span data-ttu-id="2b1c8-123">Puede especificar el valor de esta propiedad con una expresión de propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-123">The value of this property can be specified by using a property expression.</span></span>|  
  
 <span data-ttu-id="2b1c8-124">En la tabla siguiente se describen las propiedades personalizadas de la salida del origen XML.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-124">The following table describes the custom properties of the output of the XML source.</span></span> <span data-ttu-id="2b1c8-125">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-125">All properties are read/write.</span></span>  
  
|<span data-ttu-id="2b1c8-126">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="2b1c8-126">Property name</span></span>|<span data-ttu-id="2b1c8-127">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2b1c8-127">Data Type</span></span>|<span data-ttu-id="2b1c8-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b1c8-128">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="2b1c8-129">RowsetID</span><span class="sxs-lookup"><span data-stu-id="2b1c8-129">RowsetID</span></span>|<span data-ttu-id="2b1c8-130">String</span><span class="sxs-lookup"><span data-stu-id="2b1c8-130">String</span></span>|<span data-ttu-id="2b1c8-131">Valor que identifica el conjunto de filas asociado a la salida.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-131">A value that identifies the rowset associated with the output.</span></span>|  
  
 <span data-ttu-id="2b1c8-132">La salida y las columnas de salida del origen XML no tienen ninguna propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="2b1c8-132">The output columns of the XML source have no custom properties.</span></span>  
  
 <span data-ttu-id="2b1c8-133">Para más información, consulte [XML Source](xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="2b1c8-133">For more information, see [XML Source](xml-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b1c8-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b1c8-134">See Also</span></span>  
 [<span data-ttu-id="2b1c8-135">Common Properties</span><span class="sxs-lookup"><span data-stu-id="2b1c8-135">Common Properties</span></span>](../common-properties.md)  
  
  
