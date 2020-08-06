---
title: Objetos de ASSL y características de objeto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- reference exceptions [Analysis Services Scripting Language]
- ASSL, objects
- inheritance [Analysis Services Scripting Language]
- localized names [Analysis Services Scripting Language]
- objects [Analysis Services Scripting Language]
- names [Analysis Services Scripting Language]
- Analysis Services Scripting Language, objects
- expansion [Analysis Services Scripting Language]
ms.assetid: 6e5c28b5-c0bc-4ccd-82e5-e174bbb71386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d57bb421a7f486983476a6549a5121ce88ee9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675018"
---
# <a name="assl-objects-and-object-characteristics"></a><span data-ttu-id="0c350-102">Objetos y características de objetos ASSL</span><span class="sxs-lookup"><span data-stu-id="0c350-102">ASSL Objects and Object Characteristics</span></span>
  <span data-ttu-id="0c350-103">Los objetos en ASSL (Analysis Services Scripting Language) siguen instrucciones concretas con respecto a los grupos de objetos, herencia, nomenclatura, expansión y procesamiento.</span><span class="sxs-lookup"><span data-stu-id="0c350-103">Objects in Analysis Services Scripting Language (ASSL) follow specific guidelines in regards to object groups, inheritance, naming, expansion, and processing.</span></span>  
  
## <a name="object-groups"></a><span data-ttu-id="0c350-104">Grupos de objetos</span><span class="sxs-lookup"><span data-stu-id="0c350-104">Object Groups</span></span>  
 <span data-ttu-id="0c350-105">Todos los [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objetos tienen una representación XML.</span><span class="sxs-lookup"><span data-stu-id="0c350-105">All [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objects have an XML representation.</span></span> <span data-ttu-id="0c350-106">Los objetos están divididos en dos grupos:</span><span class="sxs-lookup"><span data-stu-id="0c350-106">The objects are divided into two groups:</span></span>  
  
 <span data-ttu-id="0c350-107">**Objetos principales**</span><span class="sxs-lookup"><span data-stu-id="0c350-107">**Major objects**</span></span>  
 <span data-ttu-id="0c350-108">Los objetos principales se pueden crear, modificar y eliminar de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="0c350-108">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="0c350-109">Los objetos principales incluyen:</span><span class="sxs-lookup"><span data-stu-id="0c350-109">Major objects include:</span></span>  
  
-   <span data-ttu-id="0c350-110">Servidores</span><span class="sxs-lookup"><span data-stu-id="0c350-110">Servers</span></span>  
  
-   <span data-ttu-id="0c350-111">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="0c350-111">Databases</span></span>  
  
-   <span data-ttu-id="0c350-112">Dimensions</span><span class="sxs-lookup"><span data-stu-id="0c350-112">Dimensions</span></span>  
  
-   <span data-ttu-id="0c350-113">Cubos</span><span class="sxs-lookup"><span data-stu-id="0c350-113">Cubes</span></span>  
  
-   <span data-ttu-id="0c350-114">Grupos de medida</span><span class="sxs-lookup"><span data-stu-id="0c350-114">Measure groups</span></span>  
  
-   <span data-ttu-id="0c350-115">Particiones</span><span class="sxs-lookup"><span data-stu-id="0c350-115">Partitions</span></span>  
  
-   <span data-ttu-id="0c350-116">Perspectivas</span><span class="sxs-lookup"><span data-stu-id="0c350-116">Perspectives</span></span>  
  
-   <span data-ttu-id="0c350-117">Modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="0c350-117">Mining models</span></span>  
  
-   <span data-ttu-id="0c350-118">Roles</span><span class="sxs-lookup"><span data-stu-id="0c350-118">Roles</span></span>  
  
-   <span data-ttu-id="0c350-119">Comandos asociados a un servidor o base de datos</span><span class="sxs-lookup"><span data-stu-id="0c350-119">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="0c350-120">Orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="0c350-120">Data sources</span></span>  
  
 <span data-ttu-id="0c350-121">Los objetos principales cuentan con las siguientes propiedades para realizar el seguimiento de su historial y estado.</span><span class="sxs-lookup"><span data-stu-id="0c350-121">Major objects have the following properties to track their history and status.</span></span>  
  
-   `CreatedTimestamp`  
  
-   `LastSchemaUpdate`  
  
-   <span data-ttu-id="0c350-122">`LastProcessed` (donde corresponda)</span><span class="sxs-lookup"><span data-stu-id="0c350-122">`LastProcessed` (where appropriate)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c350-123">La clasificación de un objeto como un objeto principal afecta a la manera en que una instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] trata ese objeto y la manera en que se trata ese objeto en el lenguaje de definición de objeto.</span><span class="sxs-lookup"><span data-stu-id="0c350-123">The classification of an object as a major object affects how an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] treats that object and how that object is handled in the object definition language.</span></span> <span data-ttu-id="0c350-124">Sin embargo, esta clasificación no garantiza que las herramientas de administración y desarrollo de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] permitirán la creación, modificación o eliminación independiente de estos objetos.</span><span class="sxs-lookup"><span data-stu-id="0c350-124">However, this classification does not guarantee that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] management and development tools will allow the independent creation, modification, or deletion of these objects.</span></span>  
  
 <span data-ttu-id="0c350-125">**Objetos secundarios**</span><span class="sxs-lookup"><span data-stu-id="0c350-125">**Minor objects**</span></span>  
 <span data-ttu-id="0c350-126">Los objetos secundarios solo se pueden crear, modificar o eliminar como parte de la creación, modificación o eliminación del objeto principal primario.</span><span class="sxs-lookup"><span data-stu-id="0c350-126">Minor objects can only be created, altered, or deleted as part of creating, altering, or deleting the parent major object.</span></span> <span data-ttu-id="0c350-127">Los objetos secundarios incluyen:</span><span class="sxs-lookup"><span data-stu-id="0c350-127">Minor objects include:</span></span>  
  
-   <span data-ttu-id="0c350-128">Jerarquías y niveles</span><span class="sxs-lookup"><span data-stu-id="0c350-128">Hierarchies and levels</span></span>  
  
-   <span data-ttu-id="0c350-129">Atributos</span><span class="sxs-lookup"><span data-stu-id="0c350-129">Attributes</span></span>  
  
-   <span data-ttu-id="0c350-130">Medidas</span><span class="sxs-lookup"><span data-stu-id="0c350-130">Measures</span></span>  
  
-   <span data-ttu-id="0c350-131">Columnas de modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="0c350-131">Mining model columns</span></span>  
  
-   <span data-ttu-id="0c350-132">Comandos asociados a un cubo</span><span class="sxs-lookup"><span data-stu-id="0c350-132">Commands associated with a cube</span></span>  
  
-   <span data-ttu-id="0c350-133">Agregaciones</span><span class="sxs-lookup"><span data-stu-id="0c350-133">Aggregations</span></span>  
  
## <a name="object-expansion"></a><span data-ttu-id="0c350-134">Expansión de objetos</span><span class="sxs-lookup"><span data-stu-id="0c350-134">Object Expansion</span></span>  
 <span data-ttu-id="0c350-135">La restricción `ObjectExpansion` se puede usar para controlar el grado de expansión para XML de ASSL que devuelve el servidor.</span><span class="sxs-lookup"><span data-stu-id="0c350-135">The `ObjectExpansion` restriction can be used to control the degree of expansion of ASSL XML returned by the server.</span></span> <span data-ttu-id="0c350-136">Esta restricción tiene las opciones que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c350-136">This restriction has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="0c350-137">Valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="0c350-137">Enumeration value</span></span>|<span data-ttu-id="0c350-138">Permitido para\<Alter></span><span class="sxs-lookup"><span data-stu-id="0c350-138">Allowed for \<Alter></span></span>|<span data-ttu-id="0c350-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c350-139">Description</span></span>|  
|-----------------------|---------------------------|-----------------|  
|<span data-ttu-id="0c350-140">*ReferenceOnly*</span><span class="sxs-lookup"><span data-stu-id="0c350-140">*ReferenceOnly*</span></span>|<span data-ttu-id="0c350-141">No</span><span class="sxs-lookup"><span data-stu-id="0c350-141">no</span></span>|<span data-ttu-id="0c350-142">Devuelve solamente el nombre, identificador y marca de tiempo para el objeto solicitado y para todos los objetos principales contenidos de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="0c350-142">Returns only the name, ID, and timestamp for the requested object and for all contained major objects recursively.</span></span>|  
|<span data-ttu-id="0c350-143">*ObjectProperties*</span><span class="sxs-lookup"><span data-stu-id="0c350-143">*ObjectProperties*</span></span>|<span data-ttu-id="0c350-144">sí</span><span class="sxs-lookup"><span data-stu-id="0c350-144">yes</span></span>|<span data-ttu-id="0c350-145">Expande el objeto solicitado y los objetos secundarios contenidos, pero no devuelve los objetos principales contenidos.</span><span class="sxs-lookup"><span data-stu-id="0c350-145">Expands the requested object and minor contained objects, but does not return major contained objects.</span></span>|  
|<span data-ttu-id="0c350-146">*ExpandObject*</span><span class="sxs-lookup"><span data-stu-id="0c350-146">*ExpandObject*</span></span>|<span data-ttu-id="0c350-147">No</span><span class="sxs-lookup"><span data-stu-id="0c350-147">no</span></span>|<span data-ttu-id="0c350-148">Igual que *ObjectProperties*, pero también devuelve el nombre, identificador y marca de tiempo de los objetos principales contenidos.</span><span class="sxs-lookup"><span data-stu-id="0c350-148">Same as *ObjectProperties*, but also returns the name, ID, and timestamp for contained major objects.</span></span>|  
|<span data-ttu-id="0c350-149">*ExpandFull*</span><span class="sxs-lookup"><span data-stu-id="0c350-149">*ExpandFull*</span></span>|<span data-ttu-id="0c350-150">sí</span><span class="sxs-lookup"><span data-stu-id="0c350-150">yes</span></span>|<span data-ttu-id="0c350-151">Expande totalmente el objeto solicitado y todos los objetos contenidos de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="0c350-151">Fully expands the requested object and all contained objects recursively.</span></span>|  
  
 <span data-ttu-id="0c350-152">Esta sección de referencia de ASSL describe la representación *ExpandFull* .</span><span class="sxs-lookup"><span data-stu-id="0c350-152">This ASSL reference section describes the *ExpandFull* representation.</span></span> <span data-ttu-id="0c350-153">Todos los demás niveles `ObjectExpansion` se derivan de este nivel.</span><span class="sxs-lookup"><span data-stu-id="0c350-153">All other `ObjectExpansion` levels are derived from this level.</span></span>  
  
## <a name="object-processing"></a><span data-ttu-id="0c350-154">Procesamiento de objetos</span><span class="sxs-lookup"><span data-stu-id="0c350-154">Object Processing</span></span>  
 <span data-ttu-id="0c350-155">ASSL incluye elementos o propiedades de solo lectura (por ejemplo, `LastProcessed`) que se pueden leer desde la instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], pero que se omiten cuando los scripts de comando se envían a la instancia.</span><span class="sxs-lookup"><span data-stu-id="0c350-155">ASSL includes read-only elements or properties (for example, `LastProcessed`) that can be read from the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance, but which are omitted when command scripts are submitted to the instance.</span></span> [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="0c350-156">omite los valores modificados de los elementos de solo lectura sin advertencias o errores.</span><span class="sxs-lookup"><span data-stu-id="0c350-156">ignores modified values for read-only elements without warning or error.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="0c350-157">también omite las propiedades que no son adecuadas o que son irrelevantes sin provocar errores de validación.</span><span class="sxs-lookup"><span data-stu-id="0c350-157">also ignores inappropriate or irrelevant properties without raising validation errors.</span></span> <span data-ttu-id="0c350-158">Por ejemplo, el elemento X únicamente debería estar presente cuando el elemento Y tiene un valor determinado.</span><span class="sxs-lookup"><span data-stu-id="0c350-158">For example, the X element should only be present when the Y element has a particular value.</span></span> <span data-ttu-id="0c350-159">La instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] omite el elemento X en lugar de validar ese elemento con el valor del elemento Y.</span><span class="sxs-lookup"><span data-stu-id="0c350-159">The [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance ignores the X element instead of validating that element against the value of the Y element.</span></span>  
  
  
