---
title: Referencia de expresiones (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: bb16e4ab-b13f-48f2-8cfe-1851656875ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7854aa2cc256d63fe93ddb049486e782bfaa0e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671400"
---
# <a name="expression-reference-report-builder-and-ssrs"></a><span data-ttu-id="79727-102">Referencia de expresiones (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="79727-102">Expression Reference (Report Builder and SSRS)</span></span>
  <span data-ttu-id="79727-103">Las expresiones de informe admiten diversas referencias a funciones integradas y colecciones integradas.</span><span class="sxs-lookup"><span data-stu-id="79727-103">Report expressions support a variety of references to built-in functions and built-in collections.</span></span> <span data-ttu-id="79727-104">Las expresiones deben tener una sintaxis válida de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] para que un informe se pueda publicar o procesar.</span><span class="sxs-lookup"><span data-stu-id="79727-104">Expressions must have valid [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] syntax before a report can be published or processed.</span></span>  
  
 <span data-ttu-id="79727-105">Para desarrollar expresiones complejas o expresiones que utilizan código personalizado o ensamblados personalizados, recomendamos utilizar el Diseñador de informes en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79727-105">To develop complex expressions or expressions that use custom code or custom assemblies, we recommend that you use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="79727-106">Para obtener más información, vea [Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)subyacente.</span><span class="sxs-lookup"><span data-stu-id="79727-106">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="79727-107">Utilice los temas de esta sección como ayuda para escribir expresiones simples en un informe.</span><span class="sxs-lookup"><span data-stu-id="79727-107">Use the topics in this section to help write simple expressions in a report.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79727-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="79727-108">In This Section</span></span>  
 [<span data-ttu-id="79727-109">Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-109">Data Types in Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="79727-110">Usar constantes en expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-110">Constants in Expressions &#40;Report Builder and SSRS&#41;</span></span>](constants-in-expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="79727-111">Usar operadores en expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-111">Operators in Expressions &#40;Report Builder and SSRS&#41;</span></span>](operators-in-expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="79727-112">Colecciones integradas en expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-112">Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-in-expressions-report-builder.md)  
  
 [<span data-ttu-id="79727-113">Referencias a campos globales y de usuario integrados &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-113">Built-in Globals and Users References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-built-in-globals-and-users-references-report-builder.md)  
  
 [<span data-ttu-id="79727-114">Usar referencias a la colección de parámetros &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-114">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
 [<span data-ttu-id="79727-115">Referencias a la colección de campos de conjunto de datos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-115">Dataset Fields Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-dataset-fields-collection-references-report-builder.md)  
  
 [<span data-ttu-id="79727-116">Usar referencias a las colecciones DataSources y DataSets &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-116">DataSources and DataSets Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-datasources-and-datasets-references-report-builder.md)  
  
 [<span data-ttu-id="79727-117">Referencias a las colecciones de variables de informe y de grupo &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-117">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  
  
 [<span data-ttu-id="79727-118">Usar referencias a la colección ReportItems &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-118">ReportItems Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-reportitems-collection-references-report-builder.md)  
  
## <a name="see-also"></a><span data-ttu-id="79727-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79727-119">See Also</span></span>  
 [<span data-ttu-id="79727-120">Expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79727-120">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
