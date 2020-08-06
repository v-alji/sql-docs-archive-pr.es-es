---
title: Schema (DTA, elemento de Database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Schema element
ms.assetid: d932e59c-953f-4ab4-934d-b6baf344835c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7653177878f3a832abd2d1ca266bc5feb17b9a29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663878"
---
# <a name="schema-element-for-database-dta"></a><span data-ttu-id="8ff47-102">Schema (DTA, elemento de Database)</span><span class="sxs-lookup"><span data-stu-id="8ff47-102">Schema Element for Database (DTA)</span></span>
  <span data-ttu-id="8ff47-103">Especifica el esquema de la base de datos que se desea optimizar.</span><span class="sxs-lookup"><span data-stu-id="8ff47-103">Specifies the schema of the database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff47-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ff47-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here...  
    <Schema>...</Schema>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="8ff47-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="8ff47-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="8ff47-106">Característica</span><span class="sxs-lookup"><span data-stu-id="8ff47-106">Characteristic</span></span>|<span data-ttu-id="8ff47-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ff47-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8ff47-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="8ff47-108">**Data type and length**</span></span>|<span data-ttu-id="8ff47-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8ff47-109">None.</span></span>|  
|<span data-ttu-id="8ff47-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="8ff47-110">**Default value**</span></span>|<span data-ttu-id="8ff47-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8ff47-111">None.</span></span>|  
|<span data-ttu-id="8ff47-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="8ff47-112">**Occurrence**</span></span>|<span data-ttu-id="8ff47-113">Una obligatoria para el elemento **Database** especificado en el elemento **Server** .</span><span class="sxs-lookup"><span data-stu-id="8ff47-113">Required once for the **Database** element that is specified under the **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="8ff47-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="8ff47-114">Element Relationships</span></span>  
  
|<span data-ttu-id="8ff47-115">Relación</span><span class="sxs-lookup"><span data-stu-id="8ff47-115">Relationship</span></span>|<span data-ttu-id="8ff47-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="8ff47-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="8ff47-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="8ff47-117">**Parent element**</span></span>|[<span data-ttu-id="8ff47-118">Elemento Database para servidor &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="8ff47-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="8ff47-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="8ff47-119">**Child elements**</span></span>|[<span data-ttu-id="8ff47-120">Name &#40;DTA, elemento de Schema&#41;</span><span class="sxs-lookup"><span data-stu-id="8ff47-120">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)<br /><br /> [<span data-ttu-id="8ff47-121">Table &#40;DTA, elemento de Schema&#41;</span><span class="sxs-lookup"><span data-stu-id="8ff47-121">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="8ff47-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ff47-122">Example</span></span>  
 <span data-ttu-id="8ff47-123">Para obtener un ejemplo del uso de este elemento, vea [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="8ff47-123">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff47-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ff47-124">See Also</span></span>  
 [<span data-ttu-id="8ff47-125">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="8ff47-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
