---
title: Segmentar el cubo de origen (Asistente para minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.slicesourcecube.f1
ms.assetid: 16485608-d3b9-49ee-8baa-948038cdd7ec
author: minewiskan
ms.author: owend
ms.openlocfilehash: 762248d4c2a268ac36b0dfa3ffeba20123017017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748283"
---
# <a name="slice-source-cube-data-mining-wizard"></a><span data-ttu-id="e2389-102">Segmentar el cubo de origen (Asistente para minería de datos)</span><span class="sxs-lookup"><span data-stu-id="e2389-102">Slice Source Cube (Data Mining Wizard)</span></span>
  <span data-ttu-id="e2389-103">Puede utilizar el cuadro de diálogo **Segmentar el cubo de origen** para restringir los datos usados para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="e2389-103">You can use the **Slice Source Cube** dialog box to restrict the data used to train the model.</span></span> <span data-ttu-id="e2389-104">Un cubo suele contener datos relacionados con muchas dimensiones y atributos diferentes, como todas las tiendas, todas las regiones y todos los productos.</span><span class="sxs-lookup"><span data-stu-id="e2389-104">Typically a cube contains data related to many different dimensions and attributes, such as all stores, all regions, and all products.</span></span> <span data-ttu-id="e2389-105">No resulta práctico entrenar un modelo en combinaciones ilimitadas de atributos, por lo que debe utilizar este cuadro de diálogo para elegir un conjunto específico que se empleará para entrenar un modelo.</span><span class="sxs-lookup"><span data-stu-id="e2389-105">It is not practical to train a model on unlimited combinations of attributes, so you use this dialog box to choose a specific set to use in training a model.</span></span>  
  
 <span data-ttu-id="e2389-106">Por ejemplo, en el cubo de AdventureWorks, puede segmentar por una línea de producto, una región o un año determinados para obtener una parte de los datos.</span><span class="sxs-lookup"><span data-stu-id="e2389-106">For example, in the AdventureWorks cube, you might slice by a particular product line, region, or year, to get a portion of the data.</span></span>  
  
 <span data-ttu-id="e2389-107">Si no está familiarizado con los segmentos y los cubos, se recomienda que revise los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="e2389-107">If you are unfamiliar with slices and cubes, we recommend that you review these articles:</span></span>  
  
-   [<span data-ttu-id="e2389-108">Establezca la propiedad segmento de partición &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e2389-108">Set the Partition Slice Property &#40;Analysis Services&#41;</span></span>](multidimensional-models/set-the-partition-slice-property-analysis-services.md)  
  
-   [<span data-ttu-id="e2389-109">Crear y administrar una partición local &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e2389-109">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](multidimensional-models/create-and-manage-a-local-partition-analysis-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="e2389-110">Tenga en cuenta que las funciones MDX dinámicas (como [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) o [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) no son compatibles con la propiedad Slice para particiones.</span><span class="sxs-lookup"><span data-stu-id="e2389-110">Note that dynamic MDX functions (such as [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) or [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) are not supported in the Slice property for partitions.</span></span> <span data-ttu-id="e2389-111">Debe definir el segmento utilizando tuplas explícitas o referencias de miembro.</span><span class="sxs-lookup"><span data-stu-id="e2389-111">You must define the slice by using explicit tuples or member references.</span></span>  
>   
>  <span data-ttu-id="e2389-112">Por ejemplo, en lugar de usar [: &#40;intervalo&#41; &#40;MDX&#41;](/sql/mdx/range-mdx) para definir un intervalo, necesitaría enumerar cada miembro por los años específicos.</span><span class="sxs-lookup"><span data-stu-id="e2389-112">For example, rather than using  [: &#40;Range&#41; &#40;MDX&#41;](/sql/mdx/range-mdx) to define a range, you would need to enumerate each member by the specific years.</span></span>  
>   
>  <span data-ttu-id="e2389-113">Si necesita definir un segmento complejo, se recomienda definir las tuplas del segmento con un script Alter de XMLA.</span><span class="sxs-lookup"><span data-stu-id="e2389-113">If you need to define a complex slice, we recommend that you define the tuples in the slice by using an XMLA Alter script.</span></span> <span data-ttu-id="e2389-114">Después, puede usar la herramienta de línea de comandos ascmd o la tarea SSIS [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) para ejecutar el script y crear el conjunto de miembros especificado inmediatamente antes de procesar la partición.</span><span class="sxs-lookup"><span data-stu-id="e2389-114">Then, you can use either the ascmd command-line tool or the SSIS [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) to run the script and create the specified set of members immediately before you process the partition.</span></span>  
  
 <span data-ttu-id="e2389-115">**Para más información:** [Asistente para minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Crear una estructura de minería de datos relacional](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="e2389-115">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="e2389-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="e2389-116">Options</span></span>  
 <span data-ttu-id="e2389-117">**Dimensión**</span><span class="sxs-lookup"><span data-stu-id="e2389-117">**Dimension**</span></span>  
 <span data-ttu-id="e2389-118">Seleccione la dimensión que desea segmentar.</span><span class="sxs-lookup"><span data-stu-id="e2389-118">Select the dimension that you want to slice.</span></span>  
  
 <span data-ttu-id="e2389-119">**Hierarchy**</span><span class="sxs-lookup"><span data-stu-id="e2389-119">**Hierarchy**</span></span>  
 <span data-ttu-id="e2389-120">Seleccione la jerarquía que desea segmentar.</span><span class="sxs-lookup"><span data-stu-id="e2389-120">Select the hierarchy that you want to slice.</span></span> <span data-ttu-id="e2389-121">Puede elegir cualquier nivel de una jerarquía, pero los atributos utilizados en el modelo solo estarán en el nivel que elija.</span><span class="sxs-lookup"><span data-stu-id="e2389-121">You can choose any level of a hierarchy, but the attributes used in the model will be only at the level that you choose.</span></span>  
  
 <span data-ttu-id="e2389-122">Por ejemplo, si elige la jerarquía Geography y selecciona Country como nivel, no puede crear un modelo que use City como atributo.</span><span class="sxs-lookup"><span data-stu-id="e2389-122">For example, if you choose the Geography hierarchy, and select Country as the level, you cannot build a model that uses City as the attributes.</span></span> <span data-ttu-id="e2389-123">Por el contrario, si elige City como el nivel de la jerarquía para segmentar, no puede crear un modelo de minería de datos basado en Country.</span><span class="sxs-lookup"><span data-stu-id="e2389-123">Conversely, if you choose City as the level of the hierarchy on which to slice, you cannot create a mining model based on Country.</span></span>  
  
 <span data-ttu-id="e2389-124">**Operador**</span><span class="sxs-lookup"><span data-stu-id="e2389-124">**Operator**</span></span>  
 <span data-ttu-id="e2389-125">Seleccione el operador que desea utilizar para generar una expresión de segmentación.</span><span class="sxs-lookup"><span data-stu-id="e2389-125">Select the operator to use in building a slice expression.</span></span>  
  
 <span data-ttu-id="e2389-126">Por ejemplo, si elige Geography como jerarquía, puede seleccionar el operador = y, a continuación, escribir "Europe" como filtro para obtener datos del cubo solo para Europa.</span><span class="sxs-lookup"><span data-stu-id="e2389-126">For example, if you chose Geography as the hierarchy, you could select the operator = and then type "Europe" as the filter, to get cube data for Europe only.</span></span>  
  
 <span data-ttu-id="e2389-127">**Expresión de filtro**</span><span class="sxs-lookup"><span data-stu-id="e2389-127">**Filter Expression**</span></span>  
 <span data-ttu-id="e2389-128">Escriba una expresión que se usará como criterio para filtrar el cubo en la dimensión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e2389-128">Type an expression to use as a criterion when filtering the cube on the selected dimension.</span></span>  
  
 <span data-ttu-id="e2389-129">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="e2389-129">**Parameters**</span></span>  
 <span data-ttu-id="e2389-130">Esta opción no se utiliza para los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="e2389-130">This option is not used for data mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2389-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2389-131">See Also</span></span>  
 <span data-ttu-id="e2389-132">[Finalización del asistente &#40;Asistente para minería de datos&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="e2389-132">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="e2389-133">[Asistente para minería de datos (ayuda F1) &#40;Analysis Services: minería de datos&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e2389-133">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="e2389-134">Especificar el uso de la columna del modelo de minería de datos &#40;Asistente para minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="e2389-134">Specify Mining Model Column Usage &#40;Data Mining Wizard&#41;</span></span>](specify-mining-model-column-usage-data-mining-wizard.md)  
  
  
