---
title: Especificar el contenido y el tipo de datos de la columna&#39;s (Asistente para minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifycontentdatatype.f1
ms.assetid: 7061f674-e806-46f2-8c15-e260a3c69a17
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66af7280e444036468b9cc33a131993524d3586d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675539"
---
# <a name="specify-the-column39s-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="53c26-102">Especificar el contenido y el tipo de datos de la columna&#39;s (Asistente para minería de datos)</span><span class="sxs-lookup"><span data-stu-id="53c26-102">Specify the Column&#39;s Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="53c26-103">Utilice la página **Especificar el contenido y el tipo de datos de las columnas** para modificar la columna y los tipos de contenido que ya ha especificado mediante el asistente.</span><span class="sxs-lookup"><span data-stu-id="53c26-103">Use the **Specify the Column's Content and Data Type** page to modify the column and content types that have already been set by the wizard.</span></span> <span data-ttu-id="53c26-104">El asistente utiliza los tipos de datos de las columnas de origen y las capacidades del algoritmo seleccionado para determinar los datos y los tipos de contenido predeterminados para cada columna.</span><span class="sxs-lookup"><span data-stu-id="53c26-104">The wizard uses the data types of the source columns and the capabilities of the selected algorithm to determine the default data and content types for each column.</span></span>  
  
 <span data-ttu-id="53c26-105">**Para más información:** [Asistente para minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Crear una estructura de minería de datos relacional](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="53c26-105">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="53c26-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="53c26-106">Options</span></span>  
 <span data-ttu-id="53c26-107">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="53c26-107">**Columns**</span></span>  
 <span data-ttu-id="53c26-108">Lista de las columnas definidas en la página **Especificar los datos de aprendizaje** del asistente.</span><span class="sxs-lookup"><span data-stu-id="53c26-108">A list of the columns that are defined in the **Specify the Training Data** page of the wizard.</span></span>  
  
 <span data-ttu-id="53c26-109">**Tipo de contenido**</span><span class="sxs-lookup"><span data-stu-id="53c26-109">**Content Type**</span></span>  
 <span data-ttu-id="53c26-110">El tipo de contenido que se asigna a cada columna.</span><span class="sxs-lookup"><span data-stu-id="53c26-110">The content type that is assigned to each column.</span></span> <span data-ttu-id="53c26-111">Haga clic dentro de una celda para cambiar el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="53c26-111">Click inside a cell to change the content type.</span></span> <span data-ttu-id="53c26-112">Para obtener más información sobre los tipos de contenido, vea [Tipos de contenido &#40;minería de datos&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="53c26-112">For more information about content types, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="53c26-113">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="53c26-113">**Data Type**</span></span>  
 <span data-ttu-id="53c26-114">Los tipos de datos que se asignan a cada columna.</span><span class="sxs-lookup"><span data-stu-id="53c26-114">The data types that are assigned to each column.</span></span> <span data-ttu-id="53c26-115">Haga clic dentro de una celda para cambiar el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="53c26-115">Click inside a cell to change the data type.</span></span> <span data-ttu-id="53c26-116">Para obtener más información sobre los tipos de datos, vea [Tipos de datos &#40;minería de datos&#41;](data-mining/data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="53c26-116">For more information about data types, see [Data Types &#40;Data Mining&#41;](data-mining/data-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="53c26-117">**Detectar**</span><span class="sxs-lookup"><span data-stu-id="53c26-117">**Detect**</span></span>  
 <span data-ttu-id="53c26-118">Haga clic en esta opción para detectar automáticamente los tipos de contenido discreto y continuo para una columna numérica.</span><span class="sxs-lookup"><span data-stu-id="53c26-118">Click to automatically detect the continuous and discrete content types for numeric column.</span></span> <span data-ttu-id="53c26-119">Esto no se aplica a estructuras de minería de datos que se basan en orígenes de datos OLAP.</span><span class="sxs-lookup"><span data-stu-id="53c26-119">This does not apply to mining structures that are based on OLAP data sources.</span></span> <span data-ttu-id="53c26-120">Para las estructuras de minería de datos OLAP, el asistente detecta automáticamente los tipos de contenido y elige un tipo que sea compatible con el algoritmo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="53c26-120">For OLAP mining structures, the wizard automatically detects content types and chooses a type that is compatible with the selected algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c26-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53c26-121">See Also</span></span>  
 <span data-ttu-id="53c26-122">[Finalización del asistente &#40;Asistente para minería de datos&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="53c26-122">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="53c26-123">[Asistente para minería de datos (ayuda F1) &#40;Analysis Services: minería de datos&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="53c26-123">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="53c26-124">Especificar los datos de entrenamiento &#40;Asistente para minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="53c26-124">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  
