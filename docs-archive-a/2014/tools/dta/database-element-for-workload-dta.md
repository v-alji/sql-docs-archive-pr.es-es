---
title: Database (DTA, elemento de Workload) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 112fca2a-37e5-4162-b2e7-b56eb8ab0c6f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2774bc7ed981c84c966a394c95347208cbc6d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743786"
---
# <a name="database-element-for-workload-dta"></a><span data-ttu-id="37ebe-102">Database (DTA, elemento de Workload)</span><span class="sxs-lookup"><span data-stu-id="37ebe-102">Database Element for Workload (DTA)</span></span>
  <span data-ttu-id="37ebe-103">Especifica la base de datos en la que se ubica la tabla de seguimiento de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37ebe-103">Specifies the database where the workload trace table is located.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ebe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37ebe-104">Syntax</span></span>  
  
```  
  
<Workload>  
  <Database>  
   ...code removed here...  
  </Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="37ebe-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="37ebe-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="37ebe-106">Característica</span><span class="sxs-lookup"><span data-stu-id="37ebe-106">Characteristic</span></span>|<span data-ttu-id="37ebe-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="37ebe-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="37ebe-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="37ebe-108">**Data type and length**</span></span>|<span data-ttu-id="37ebe-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="37ebe-109">None.</span></span>|  
|<span data-ttu-id="37ebe-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="37ebe-110">**Default value**</span></span>|<span data-ttu-id="37ebe-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="37ebe-111">None.</span></span>|  
|<span data-ttu-id="37ebe-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="37ebe-112">**Occurrence**</span></span>|<span data-ttu-id="37ebe-113">Una obligatoria si no se especifica ningún otro tipo de carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37ebe-113">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="37ebe-114">Es necesario especificar un elemento secundario `EventString`, `File` o `Database` para el elemento primario `Workload`, aunque solo se puede utilizar un tipo.</span><span class="sxs-lookup"><span data-stu-id="37ebe-114">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="37ebe-115">Por ejemplo, si se especifica una carga de trabajo con el `Database` elemento, no se puede especificar una carga de trabajo con el `File` elemento en el mismo archivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="37ebe-115">For example, if you specify a workload with the `Database` element, you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="37ebe-116">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="37ebe-116">Element Relationships</span></span>  
  
|<span data-ttu-id="37ebe-117">Relación</span><span class="sxs-lookup"><span data-stu-id="37ebe-117">Relationship</span></span>|<span data-ttu-id="37ebe-118">Elementos</span><span class="sxs-lookup"><span data-stu-id="37ebe-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="37ebe-119">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="37ebe-119">**Parent element**</span></span>|[<span data-ttu-id="37ebe-120">Workload &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="37ebe-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="37ebe-121">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="37ebe-121">**Child elements**</span></span>|[<span data-ttu-id="37ebe-122">Name &#40;DTA, elemento de Database&#41;</span><span class="sxs-lookup"><span data-stu-id="37ebe-122">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="37ebe-123">Schema &#40;DTA, elemento de Database&#41;</span><span class="sxs-lookup"><span data-stu-id="37ebe-123">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="37ebe-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37ebe-124">Remarks</span></span>  
 <span data-ttu-id="37ebe-125">Este elemento tiene el nombre **DatabaseDetailsTypecomplexType** en el esquema XML del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="37ebe-125">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="37ebe-126">No confunda este elemento `Database` con el que tiene al elemento `Configuration` como raíz primaria.</span><span class="sxs-lookup"><span data-stu-id="37ebe-126">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="37ebe-127">(Vea [Elemento Database de Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md)).</span><span class="sxs-lookup"><span data-stu-id="37ebe-127">(See [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).)</span></span>  
  
## <a name="example"></a><span data-ttu-id="37ebe-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37ebe-128">Example</span></span>  
 <span data-ttu-id="37ebe-129">Para obtener un ejemplo de uso de este `Database` elemento, vea el ejemplo de código del [elemento Workload &#40;DTA&#41;](workload-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="37ebe-129">For a usage example of this `Database` element, see the code example in [Workload Element &#40;DTA&#41;](workload-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ebe-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37ebe-130">See Also</span></span>  
 [<span data-ttu-id="37ebe-131">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="37ebe-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
