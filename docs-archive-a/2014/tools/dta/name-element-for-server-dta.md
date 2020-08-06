---
title: Name (DTA, elemento de Server) | Microsoft Docs
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
ms.assetid: 4c94754d-6d62-4357-8ce7-f107ebf90c71
author: stevestein
ms.author: sstein
ms.openlocfilehash: 202258c3c87f8a35d1ee30b19880f5e9423fa394
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675096"
---
# <a name="name-element-for-server-dta"></a><span data-ttu-id="ed5d4-102">Name (DTA, elemento de Server)</span><span class="sxs-lookup"><span data-stu-id="ed5d4-102">Name Element for Server (DTA)</span></span>
  <span data-ttu-id="ed5d4-103">Contiene el nombre del servidor en el que residen las bases de datos que se desean optimizar.</span><span class="sxs-lookup"><span data-stu-id="ed5d4-103">Contains the name of the server where the databases you want to tune reside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed5d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed5d4-104">Syntax</span></span>  
  
```  
  
...code removed here...  
<Server>  
    <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="ed5d4-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="ed5d4-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="ed5d4-106">Característica</span><span class="sxs-lookup"><span data-stu-id="ed5d4-106">Characteristic</span></span>|<span data-ttu-id="ed5d4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed5d4-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ed5d4-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="ed5d4-108">**Data type and length**</span></span>|<span data-ttu-id="ed5d4-109">`string`, entre 1 y 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="ed5d4-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="ed5d4-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="ed5d4-110">**Default value**</span></span>|<span data-ttu-id="ed5d4-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ed5d4-111">None.</span></span>|  
|<span data-ttu-id="ed5d4-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="ed5d4-112">**Occurrence**</span></span>|<span data-ttu-id="ed5d4-113">Una obligatoria por elemento **Server** .</span><span class="sxs-lookup"><span data-stu-id="ed5d4-113">Required once per **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="ed5d4-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="ed5d4-114">Element Relationships</span></span>  
  
|<span data-ttu-id="ed5d4-115">Relación</span><span class="sxs-lookup"><span data-stu-id="ed5d4-115">Relationship</span></span>|<span data-ttu-id="ed5d4-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="ed5d4-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="ed5d4-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="ed5d4-117">**Parent element**</span></span>|[<span data-ttu-id="ed5d4-118">Server &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="ed5d4-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="ed5d4-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="ed5d4-119">**Child elements**</span></span>|<span data-ttu-id="ed5d4-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ed5d4-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ed5d4-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed5d4-121">Example</span></span>  
 <span data-ttu-id="ed5d4-122">Para obtener un ejemplo de cómo se usa el elemento **Name** , vea [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="ed5d4-122">For an example of how this **Name** element is used, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5d4-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed5d4-123">See Also</span></span>  
 [<span data-ttu-id="ed5d4-124">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="ed5d4-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
