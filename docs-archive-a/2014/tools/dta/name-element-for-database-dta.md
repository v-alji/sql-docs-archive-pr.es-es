---
title: Name (DTA, elemento de Database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: e871c4fa-3b57-46cf-b4f8-e3be86f92dc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: c692e31b9175bf05dcfb0504ea79e98cbb82f36b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743767"
---
# <a name="name-element-for-database-dta"></a><span data-ttu-id="9ad1b-102">Name (DTA, elemento de Database)</span><span class="sxs-lookup"><span data-stu-id="9ad1b-102">Name Element for Database (DTA)</span></span>
  <span data-ttu-id="9ad1b-103">Especifica el nombre de la base de datos que se desea optimizar.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-103">Specifies the name of a database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ad1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ad1b-104">Syntax</span></span>  
  
```  
  
<Server>  
    <Database>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="9ad1b-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="9ad1b-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="9ad1b-106">Característica</span><span class="sxs-lookup"><span data-stu-id="9ad1b-106">Characteristic</span></span>|<span data-ttu-id="9ad1b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ad1b-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9ad1b-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="9ad1b-108">**Data type and length**</span></span>|<span data-ttu-id="9ad1b-109">`string`, longitud ilimitada.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="9ad1b-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="9ad1b-110">**Default value**</span></span>|<span data-ttu-id="9ad1b-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-111">None.</span></span>|  
|<span data-ttu-id="9ad1b-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="9ad1b-112">**Occurrence**</span></span>|<span data-ttu-id="9ad1b-113">Se requiere una vez por elemento `Database`.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-113">Required once per `Database` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="9ad1b-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="9ad1b-114">Element Relationships</span></span>  
  
|<span data-ttu-id="9ad1b-115">Relación</span><span class="sxs-lookup"><span data-stu-id="9ad1b-115">Relationship</span></span>|<span data-ttu-id="9ad1b-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="9ad1b-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="9ad1b-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="9ad1b-117">**Parent element**</span></span>|[<span data-ttu-id="9ad1b-118">Elemento Database para servidor &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="9ad1b-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="9ad1b-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="9ad1b-119">**Child elements**</span></span>|<span data-ttu-id="9ad1b-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9ad1b-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ad1b-121">Example</span></span>  
 <span data-ttu-id="9ad1b-122">Para obtener un ejemplo del uso de este elemento, vea [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="9ad1b-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ad1b-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ad1b-123">See Also</span></span>  
 [<span data-ttu-id="9ad1b-124">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="9ad1b-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
