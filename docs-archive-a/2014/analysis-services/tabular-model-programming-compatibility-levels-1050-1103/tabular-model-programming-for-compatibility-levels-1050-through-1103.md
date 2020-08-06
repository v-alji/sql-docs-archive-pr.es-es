---
title: Programación de modelos tabulares | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 0ceb461e-12c1-44ea-97ac-b99bf308676b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2565ed28a882750ab9b37beadbce698d3a0abb19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752377"
---
# <a name="tabular-model-programming"></a><span data-ttu-id="47f3c-102">Programación de modelo tabular</span><span class="sxs-lookup"><span data-stu-id="47f3c-102">Tabular Model Programming</span></span>
  <span data-ttu-id="47f3c-103">Los modelos tabulares utilizan estructuras relacionales para modelar los datos de Analysis Services utilizados por aplicaciones analíticas y de informes.</span><span class="sxs-lookup"><span data-stu-id="47f3c-103">Tabular models use relational constructs to model the Analysis Services data used by analytical and reporting applications.</span></span> <span data-ttu-id="47f3c-104">Estos modelos se ejecutan en una instancia de Analysis Services configurada para el modo tabular, usando un motor de análisis en memoria para el almacenamiento y recorridos de tabla rápidos que agregan y calculan datos conforme se solicitan.</span><span class="sxs-lookup"><span data-stu-id="47f3c-104">These models run on an Analysis Service instance that is configured for tabular mode, using an in-memory analytics engine for storage and fast table scans that aggregate and calculate data as it is requested.</span></span>  
  
 <span data-ttu-id="47f3c-105">Mediante programación, los objetos con los que se trabaja en AMO, ADOMD.NET, XMLA u OLE DB son fundamental los mismos para las soluciones tanto tabulares como multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="47f3c-105">Programmatically, the objects you work with in AMO, ADOMD.NET, XMLA, or OLE DB are fundamentally the same for both tabular and multidimensional solutions.</span></span> <span data-ttu-id="47f3c-106">Si los requisitos de la solución personalizada de BI se satisfacen mejor mediante una base de datos de modelo tabular, puede usar cualquiera de las bibliotecas de cliente e interfaces de programación de Analysis Services para integrar la aplicación con modelos tabulares en una instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="47f3c-106">If the requirements of your custom BI solution are best met by a tabular model database, you can use any of the Analysis Services client libraries and programming interfaces to integrate your application with tabular models on an Analysis Services instance.</span></span> <span data-ttu-id="47f3c-107">Para consultar y calcular datos de modelo tabulares, puede utilizar DAX o MDX incrustado en el código.</span><span class="sxs-lookup"><span data-stu-id="47f3c-107">To query and calculate tabular model data, you can use either embedded MDX or DAX in your code.</span></span>  
  
 <span data-ttu-id="47f3c-108">Esta sección proporciona más información sobre cómo se puede trabajar mediante programación con entidades de modelo tabular y sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="47f3c-108">This section provides more information about how you can programmatically work with tabular model entities and their properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47f3c-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="47f3c-109">In This Section</span></span>  
 [<span data-ttu-id="47f3c-110">Anotaciones de CSDL para Business Intelligence &#40;CSDLBI&#41;</span><span class="sxs-lookup"><span data-stu-id="47f3c-110">CSDL Annotations for Business Intelligence &#40;CSDLBI&#41;</span></span>](/analysis-services/csdlbi/csdl-annotations-for-business-intelligence-csdlbi)  
  
 [<span data-ttu-id="47f3c-111">Descripción del modelo de objetos tabulares</span><span class="sxs-lookup"><span data-stu-id="47f3c-111">Understanding the Tabular Object Model</span></span>](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
 [<span data-ttu-id="47f3c-112">Referencia técnica para las anotaciones de Business Intelligence en CSDL</span><span class="sxs-lookup"><span data-stu-id="47f3c-112">Technical Reference for BI Annotations to CSDL</span></span>](/analysis-services/csdlbi/technical-reference-for-bi-annotations-to-csdl)  
  
 [<span data-ttu-id="47f3c-113">Interfaz IMDEmbedded</span><span class="sxs-lookup"><span data-stu-id="47f3c-113">IMDEmbedded Interface</span></span>](imdembeddeddata-interface.md)  
  
## <a name="see-also"></a><span data-ttu-id="47f3c-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47f3c-114">See Also</span></span>  
 <span data-ttu-id="47f3c-115">[Modelado tabular &#40;&#41;tabular de SSAS](../tabular-models/tabular-models-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="47f3c-115">[Tabular Modeling &#40;SSAS Tabular&#41;](../tabular-models/tabular-models-ssas.md) </span></span>  
 [<span data-ttu-id="47f3c-116">Diseñador de modelos tabulares &#40;&#41;tabular de SSAS</span><span class="sxs-lookup"><span data-stu-id="47f3c-116">Tabular Model Designer &#40;SSAS Tabular&#41;</span></span>](../tabular-model-designer-ssas-tabular.md)  
  
  
