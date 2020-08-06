---
title: Editor de rutas de flujo de datos (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.patheditor.general.f1
helpviewer_keywords:
- Data Flow Path Editor dialog box
ms.assetid: 72a9ff1d-3748-41d1-a9b2-63f4a77bba24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71eca61b1454e2e8cb811bbe450f584191ae77b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744811"
---
# <a name="data-flow-path-editor-general-page"></a><span data-ttu-id="a0cf8-102">Editor de rutas de flujo de datos (página General)</span><span class="sxs-lookup"><span data-stu-id="a0cf8-102">Data Flow Path Editor (General Page)</span></span>
  <span data-ttu-id="a0cf8-103">Utilice el cuadro de diálogo **Editor de rutas de flujo de datos** para establecer propiedades de ruta, ver metadatos de columna y administrar los visores de datos adjuntados a la ruta.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-103">Use the **Data Flow Path Editor** dialog box to set path properties, view column metadata, and manage the data viewers attached to the path.</span></span>  
  
 <span data-ttu-id="a0cf8-104">Utilice el nodo **General** del cuadro de diálogo **Editor de rutas de flujo de datos** para nombrar y describir la ruta, y para especificar las opciones de anotación de ruta.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-104">Use the **General** node of the **Data Flow Path Editor** dialog box to name and describe the path, and to specify the options for path annotation.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a0cf8-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="a0cf8-105">Options</span></span>  
 <span data-ttu-id="a0cf8-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-106">**Name**</span></span>  
 <span data-ttu-id="a0cf8-107">Proporcione un nombre único para la ruta.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-107">Provide a unique name for the path.</span></span>  
  
 <span data-ttu-id="a0cf8-108">**ID**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-108">**ID**</span></span>  
 <span data-ttu-id="a0cf8-109">El identificador de linaje de la ruta.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-109">The lineage identifier of the path.</span></span> <span data-ttu-id="a0cf8-110">Esta propiedad es de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-110">This property is read-only.</span></span>  
  
 <span data-ttu-id="a0cf8-111">**IdentificationString**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-111">**IdentificationString**</span></span>  
 <span data-ttu-id="a0cf8-112">La cadena que identifica la ruta.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-112">The string that identifies the path.</span></span> <span data-ttu-id="a0cf8-113">Se automáticamente a partir del nombre especificado con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-113">Automatically generated from the name entered above.</span></span>  
  
 <span data-ttu-id="a0cf8-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-114">**Description**</span></span>  
 <span data-ttu-id="a0cf8-115">Describe la ruta.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-115">Describe the path.</span></span>  
  
 <span data-ttu-id="a0cf8-116">**PathAnnotation**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-116">**PathAnnotation**</span></span>  
 <span data-ttu-id="a0cf8-117">Especificar el tipo de anotación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-117">Specify the type of annotation to use.</span></span> <span data-ttu-id="a0cf8-118">Elija **Nunca** para deshabilitar anotaciones, **AsNeeded** para habilitar anotaciones a petición, **SourceName** para realizar anotaciones automáticamente utilizando el valor de la opción **SourceName** y **PathName** para realizar anotaciones automáticamente utilizando el valor de la propiedad **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="a0cf8-118">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **SourceName** to automatically annotate using the value of the **SourceName** option, and **PathName** to automatically annotate using the value of the **Name** property.</span></span>  
  
 <span data-ttu-id="a0cf8-119">**DestinationName**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-119">**DestinationName**</span></span>  
 <span data-ttu-id="a0cf8-120">Muestra la entrada que es el final de la ruta.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-120">Displays the input that is the end of the path.</span></span>  
  
 <span data-ttu-id="a0cf8-121">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-121">**SourceName**</span></span>  
 <span data-ttu-id="a0cf8-122">Muestra la salida que es el inicio de la ruta.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-122">Displays the output that is the start of the path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0cf8-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0cf8-123">See Also</span></span>  
 <span data-ttu-id="a0cf8-124">[Editor de rutas de flujo de datos &#40;página de metadatos&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span><span class="sxs-lookup"><span data-stu-id="a0cf8-124">[Data Flow Path Editor &#40;Metadata Page&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span></span>  
 <span data-ttu-id="a0cf8-125">[Editor de rutas de flujo de datos &#40;página visores de datos&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span><span class="sxs-lookup"><span data-stu-id="a0cf8-125">[Data Flow Path Editor &#40;Data Viewers Page&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span></span>  
 <span data-ttu-id="a0cf8-126">[Flujo de datos](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="a0cf8-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="a0cf8-127">Usar anotaciones en paquetes</span><span class="sxs-lookup"><span data-stu-id="a0cf8-127">Use Annotations in Packages</span></span>](use-annotations-in-packages.md)  
  
  
