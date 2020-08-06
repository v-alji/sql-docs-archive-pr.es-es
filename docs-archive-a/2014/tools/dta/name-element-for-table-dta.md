---
title: Name (DTA, elemento de Table) | Microsoft Docs
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
ms.assetid: 422a755f-ee52-4863-b1aa-f4ef1b8fd0bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8fa8481cf8990fb63995abcb6300cd9a352c859a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675093"
---
# <a name="name-element-for-table-dta"></a><span data-ttu-id="28f8b-102">Name (DTA, elemento de Table)</span><span class="sxs-lookup"><span data-stu-id="28f8b-102">Name Element for Table (DTA)</span></span>
  <span data-ttu-id="28f8b-103">Especifica el nombre de una tabla para optimizar.</span><span class="sxs-lookup"><span data-stu-id="28f8b-103">Specifies a table name for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28f8b-104">Syntax</span></span>  
  
```  
  
<Schema>  
    <Table>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="28f8b-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="28f8b-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="28f8b-106">Característica</span><span class="sxs-lookup"><span data-stu-id="28f8b-106">Characteristic</span></span>|<span data-ttu-id="28f8b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="28f8b-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="28f8b-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="28f8b-108">**Data type and length**</span></span>|<span data-ttu-id="28f8b-109">`string`, entre 1 y 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="28f8b-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="28f8b-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="28f8b-110">**Default value**</span></span>|<span data-ttu-id="28f8b-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="28f8b-111">None.</span></span>|  
|<span data-ttu-id="28f8b-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="28f8b-112">**Occurrence**</span></span>|<span data-ttu-id="28f8b-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="28f8b-113">Required.</span></span> <span data-ttu-id="28f8b-114">Una por cada elemento `Table`.</span><span class="sxs-lookup"><span data-stu-id="28f8b-114">Once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="28f8b-115">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="28f8b-115">Element Relationships</span></span>  
  
|<span data-ttu-id="28f8b-116">Relación</span><span class="sxs-lookup"><span data-stu-id="28f8b-116">Relationship</span></span>|<span data-ttu-id="28f8b-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="28f8b-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="28f8b-118">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="28f8b-118">**Parent element**</span></span>|[<span data-ttu-id="28f8b-119">Table &#40;DTA, elemento de Schema&#41;</span><span class="sxs-lookup"><span data-stu-id="28f8b-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="28f8b-120">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="28f8b-120">**Child elements**</span></span>|<span data-ttu-id="28f8b-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="28f8b-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="28f8b-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28f8b-122">Example</span></span>  
 <span data-ttu-id="28f8b-123">Para obtener un ejemplo de uso, vea [Server &#40;DTA, elemento&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="28f8b-123">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f8b-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28f8b-124">See Also</span></span>  
 [<span data-ttu-id="28f8b-125">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="28f8b-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
