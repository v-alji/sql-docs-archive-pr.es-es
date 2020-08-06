---
title: EventString (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- EventString element
ms.assetid: f76c37b4-2f6e-4274-8ee2-87e89d98e8a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 981cd0be06fd0972426fcb2fa67b0c4143cf9178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748435"
---
# <a name="eventstring-element-dta"></a><span data-ttu-id="9edee-102">EventString (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="9edee-102">EventString Element (DTA)</span></span>
  <span data-ttu-id="9edee-103">Especifica una carga de trabajo de scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] directamente en el archivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="9edee-103">Specifies a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload directly in the XML input file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9edee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9edee-104">Syntax</span></span>  
  
```  
  
<Workload>  
    <EventString Weight="...">  
    ...code removed here...  
    </EventString>  
</Workload>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="9edee-105">Atributos del elemento</span><span class="sxs-lookup"><span data-stu-id="9edee-105">Element Attributes</span></span>  
  
|<span data-ttu-id="9edee-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="9edee-106">Attribute</span></span>|<span data-ttu-id="9edee-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9edee-107">Description</span></span>|  
|---------------|-----------------|  
|`Weight`|<span data-ttu-id="9edee-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9edee-108">Optional.</span></span> <span data-ttu-id="9edee-109">Especifica el factor de peso de la consulta (un factor de importancia) del evento especificado.</span><span class="sxs-lookup"><span data-stu-id="9edee-109">Specifies the query weight factor (a factor of importance) for the specified event.</span></span> <span data-ttu-id="9edee-110">Utilice un tipo de datos `float` para especificar el peso.</span><span class="sxs-lookup"><span data-stu-id="9edee-110">Use a `float` data type to specify the weight.</span></span> <span data-ttu-id="9edee-111">Por ejemplo, `Weight`="100,01".</span><span class="sxs-lookup"><span data-stu-id="9edee-111">For example, `Weight`="100.01".</span></span> <span data-ttu-id="9edee-112">El valor mínimo que se puede especificar para `Weight` es "0".</span><span class="sxs-lookup"><span data-stu-id="9edee-112">The minimum value you can specify for `Weight` is "0".</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="9edee-113">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="9edee-113">Element Characteristics</span></span>  
  
|<span data-ttu-id="9edee-114">Característica</span><span class="sxs-lookup"><span data-stu-id="9edee-114">Characteristic</span></span>|<span data-ttu-id="9edee-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9edee-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9edee-116">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="9edee-116">**Data type and length**</span></span>|<span data-ttu-id="9edee-117">`string`, la longitud es ilimitada.</span><span class="sxs-lookup"><span data-stu-id="9edee-117">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="9edee-118">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="9edee-118">**Default value**</span></span>|<span data-ttu-id="9edee-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9edee-119">None.</span></span>|  
|<span data-ttu-id="9edee-120">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="9edee-120">**Occurrence**</span></span>|<span data-ttu-id="9edee-121">Una obligatoria si no se especifica ningún otro tipo de carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9edee-121">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="9edee-122">Es necesario especificar un elemento secundario `EventString`, `File` o `Database` para el elemento primario `Workload`, aunque solo se puede utilizar un tipo.</span><span class="sxs-lookup"><span data-stu-id="9edee-122">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="9edee-123">Por ejemplo, si se especifica una carga de trabajo con el elemento `EventString`, no se puede especificar una carga de trabajo con el elemento `File` en el mismo archivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="9edee-123">For example, if you specify a workload with the `EventString` element, then you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="9edee-124">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="9edee-124">Element Relationships</span></span>  
  
|<span data-ttu-id="9edee-125">Relación</span><span class="sxs-lookup"><span data-stu-id="9edee-125">Relationship</span></span>|<span data-ttu-id="9edee-126">Elementos</span><span class="sxs-lookup"><span data-stu-id="9edee-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="9edee-127">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="9edee-127">**Parent element**</span></span>|[<span data-ttu-id="9edee-128">Workload &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="9edee-128">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="9edee-129">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="9edee-129">**Child elements**</span></span>|<span data-ttu-id="9edee-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9edee-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9edee-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9edee-131">Example</span></span>  
 <span data-ttu-id="9edee-132">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML con carga de trabajo insertada &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="9edee-132">For a usage example of this element, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md) .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9edee-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9edee-133">See Also</span></span>  
 [<span data-ttu-id="9edee-134">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="9edee-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
