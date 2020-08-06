---
title: Seleccionar la dimensión de cubo de origen (Asistente para minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.selectsourcecube.f1
ms.assetid: 556e216b-5e21-4160-967d-4c57591fbab4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6295a5312b4501236e0ce8f5776fc43c0d014581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669882"
---
# <a name="select-the-source-cube-dimension-data-mining-wizard"></a><span data-ttu-id="b5e77-102">Seleccionar la dimensión de cubo de origen (Asistente para minería de datos)</span><span class="sxs-lookup"><span data-stu-id="b5e77-102">Select the Source Cube Dimension (Data Mining Wizard)</span></span>
  <span data-ttu-id="b5e77-103">Utilice la página **Seleccionar la dimensión de cubo de origen** para seleccionar la dimensión desde el cubo que contiene los casos que desea analizar.</span><span class="sxs-lookup"><span data-stu-id="b5e77-103">Use the **Select the Source Cube Dimension** page to select the dimension from the cube that contains the cases you want to analyze.</span></span> <span data-ttu-id="b5e77-104">Por ejemplo, si crea un modelo que analiza el comportamiento adquisitivo de los clientes basándose en los datos demográficos, seleccionaría la dimensión de cliente, que suele contener un registro único para cada cliente y diferentes atributos que representan datos demográficos, como el género, la ubicación o los ingresos.</span><span class="sxs-lookup"><span data-stu-id="b5e77-104">For example, if you are building a model that analyzes the purchasing behavior of customers based on demographics, you would select the Customer dimension, which typically contains a unique record for each customer and various attributes that represent demographics, such as gender, location, or income.</span></span> <span data-ttu-id="b5e77-105">Más adelante en el asistente tendrá la oportunidad de agregar una tabla relacionada con esta tabla de casos: por ejemplo, puede agregar una tabla anidada que muestre los productos que ha comprado el cliente.</span><span class="sxs-lookup"><span data-stu-id="b5e77-105">Later in the wizard you will have the opportunity to add a table that is related to this case table: for example, you might add a nested table that shows which products the customer has purchased.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5e77-106">Esta página aparecerá solo si ha seleccionado **A partir de un cubo existente** en la página **Seleccionar el método de definición** del asistente.</span><span class="sxs-lookup"><span data-stu-id="b5e77-106">This page will appear only if you have selected **From existing cube** on the **Select the Definition Method** page of the wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b5e77-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="b5e77-107">Options</span></span>  
 <span data-ttu-id="b5e77-108">**Seleccione una dimensión de cubo de origen**</span><span class="sxs-lookup"><span data-stu-id="b5e77-108">**Select a Source Cube Dimension**</span></span>  
 <span data-ttu-id="b5e77-109">Seleccione la dimensión del cubo que proporcionará los datos de origen para su estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b5e77-109">Select the dimension of the cube that will provide the source data for your mining structure.</span></span>  
  
## <a name="choosing-a-dimension"></a><span data-ttu-id="b5e77-110">Elegir una dimensión</span><span class="sxs-lookup"><span data-stu-id="b5e77-110">Choosing a Dimension</span></span>  
 <span data-ttu-id="b5e77-111">Dado que solamente puede seleccionar una dimensión para usar en el modelo, es importante comprender la estructura del cubo y seleccionar la dimensión que proporciona la mejor información para el modelo.</span><span class="sxs-lookup"><span data-stu-id="b5e77-111">Because you can select only one dimension for use in your model, it is important that you understand the cube structure and select the dimension that provides the best information for your model.</span></span> <span data-ttu-id="b5e77-112">Si no sabe qué dimensión debe usar, puede resultar útil examinar el cubo y revisar los campos y los datos incluidos en ellos mediante el Diseñador de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="b5e77-112">If you are not sure which dimension to use, it might be helpful to browse the cube and review the fields and the data in them by using Dimension Designer.</span></span> <span data-ttu-id="b5e77-113">Para más información, vea [Examinar los datos de dimensiones en el Diseñador de dimensiones](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b5e77-113">For more information, see [Browse Dimension Data in Dimension Designer](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span></span>  
  
 <span data-ttu-id="b5e77-114">Si no conoce las dimensiones en general, vea [Introducción a las dimensiones &#40;Analysis Services - Datos multidimensionales&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b5e77-114">If you are unfamiliar with dimensions in general, see [Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="b5e77-115">Para obtener más información acerca del tipo de datos que suele incluir una sola dimensión, incluidos los atributos y las medidas que pueden resultar útiles para la minería de datos, vea [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="b5e77-115">For more information about the type of information that is typically contained in a single dimension, including attributes and measures that might be useful for data mining, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
 <span data-ttu-id="b5e77-116">Si la dimensión que elige no contiene todos los atributos relacionados que necesita para crear el modelo de minería de datos, es posible que deba modificarla.</span><span class="sxs-lookup"><span data-stu-id="b5e77-116">If the dimension that you choose does not contain all of the related attributes that you need to build the data mining model, you might need to modify the dimension.</span></span> <span data-ttu-id="b5e77-117">Para más información, vea [Definir dimensiones de base de datos](multidimensional-models/define-database-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="b5e77-117">For more information, see [Define Database Dimensions](multidimensional-models/define-database-dimensions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e77-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5e77-118">See Also</span></span>  
 <span data-ttu-id="b5e77-119">[Asistente para minería de datos (ayuda F1) &#40;Analysis Services: minería de datos&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b5e77-119">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="b5e77-120">[Crear la estructura de minería de datos &#40;Asistente para minería de datos&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="b5e77-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="b5e77-121">Seleccione la clave de caso &#40;Asistente para minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="b5e77-121">Select the Case Key &#40;Data Mining Wizard&#41;</span></span>](select-the-case-key-data-mining-wizard.md)  
  
  
