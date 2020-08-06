---
title: Elementos XML (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- XMLA, elements
- XML for Analysis, elements
- elements [XML for Analysis]
ms.assetid: 40ab2360-efb6-4ba6-bf23-e84964e51008
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c1e5b046bfa57302baefc43a4da989be9c70e08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676254"
---
# <a name="xml-elements-xmla"></a><span data-ttu-id="8bb9a-102">Elementos XML (XMLA)</span><span class="sxs-lookup"><span data-stu-id="8bb9a-102">XML Elements (XMLA)</span></span>
  <span data-ttu-id="8bb9a-103">En los temas siguientes se describen las distintas categorías de elementos XML for Analysis (XMLA) admitidas por [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bb9a-103">The following topics describe the various XML for Analysis (XMLA) element categories supported by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8bb9a-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8bb9a-104">In This Section</span></span>  
  
|<span data-ttu-id="8bb9a-105">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8bb9a-105">Property</span></span>|<span data-ttu-id="8bb9a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bb9a-106">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="8bb9a-107">Encabezados &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="8bb9a-107">Headers &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/xml-elements-headers)|<span data-ttu-id="8bb9a-108">Describe los elementos que envía una aplicación o una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en el encabezado SOAP de un elemento SOAP Envelope para administrar las prestaciones a nivel de protocolo.</span><span class="sxs-lookup"><span data-stu-id="8bb9a-108">Describes those elements sent in the SOAP header of a SOAP envelope, either by an application or by an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, to manage protocol-level features.</span></span>|  
|[<span data-ttu-id="8bb9a-109">Métodos &#40;&#41;XMLA</span><span class="sxs-lookup"><span data-stu-id="8bb9a-109">Methods &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods)|<span data-ttu-id="8bb9a-110">Describe los elementos de nivel superior que envía una aplicación en un elemento SOAP Envelope a una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para recuperar datos o metadatos, o para ejecutar acciones en la instancia.</span><span class="sxs-lookup"><span data-stu-id="8bb9a-110">Describes the topmost elements sent by an application in a SOAP envelope to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to retrieve data or metadata, or to perform actions on the instance.</span></span>|  
|[<span data-ttu-id="8bb9a-111">Comandos &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="8bb9a-111">Commands &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/xml-elements-commands)|<span data-ttu-id="8bb9a-112">Describe los elementos que se envían dentro de un método XMLA para realizar una acción determinada.</span><span class="sxs-lookup"><span data-stu-id="8bb9a-112">Describes the elements sent within an XMLA method to perform a specific action.</span></span>|  
|[<span data-ttu-id="8bb9a-113">Objetos &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="8bb9a-113">Objects &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects)|<span data-ttu-id="8bb9a-114">Describe los elementos de nivel superior que recibe una aplicación en un elemento SOAP Envelope procedentes de una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en respuesta a un método XMLA.</span><span class="sxs-lookup"><span data-stu-id="8bb9a-114">Describes the topmost elements received by an application in a SOAP envelope from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance in response to an XMLA method.</span></span>|  
|[<span data-ttu-id="8bb9a-115">Propiedades &#40;&#41;XMLA</span><span class="sxs-lookup"><span data-stu-id="8bb9a-115">Properties &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/xml-elements-properties)|<span data-ttu-id="8bb9a-116">Describe los elementos secundarios de encabezados, métodos, objetos o comandos XMLA.</span><span class="sxs-lookup"><span data-stu-id="8bb9a-116">Describes the child elements for XMLA headers, methods, objects, or commands.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bb9a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bb9a-117">See Also</span></span>  
 <span data-ttu-id="8bb9a-118">[Tipos de datos XML &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/xml-data-types-xmla) </span><span class="sxs-lookup"><span data-stu-id="8bb9a-118">[XML Data Types &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/xml-data-types-xmla) </span></span>  
 [<span data-ttu-id="8bb9a-119">Desarrollar aplicaciones con Analysis Services Scripting Language &#40;ASSL&#41;</span><span class="sxs-lookup"><span data-stu-id="8bb9a-119">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
  
  
