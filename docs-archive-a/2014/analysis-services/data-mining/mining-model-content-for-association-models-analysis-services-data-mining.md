---
title: Contenido del modelo de minería de datos para los modelos de asociación (Analysis Services-minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- mining model content, association models
- rules [Data Mining]
- associations [Analysis Services]
ms.assetid: d5849bcb-4b8f-4f71-9761-7dc5bb465224
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8904ce155526aee595db19094fd2bad48770e83e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671829"
---
# <a name="mining-model-content-for-association-models-analysis-services---data-mining"></a><span data-ttu-id="14f3c-102">Contenido del modelo de minería de datos para los modelos de asociación (Analysis Services - Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="14f3c-102">Mining Model Content for Association Models (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="14f3c-103">En este tema se describe el contenido del modelo de minería de datos específico de los modelos que utilizan el algoritmo Reglas de asociación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14f3c-103">This topic describes mining model content that is specific to models that use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span> <span data-ttu-id="14f3c-104">Para obtener una explicación de terminología general y de estadística relacionada con el contenido del modelo de minería de datos válida para todos los tipos de modelo, vea [Contenido del modelo de minería de datos &#40;Analysis Services - Minería de datos&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="14f3c-104">For an explanation of general and statistical terminology related to mining model content that applies to all model types, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="understanding-the-structure-of-an-association-model"></a><span data-ttu-id="14f3c-105">Descripción de la estructura de un modelo de asociación</span><span class="sxs-lookup"><span data-stu-id="14f3c-105">Understanding the Structure of an Association Model</span></span>  
 <span data-ttu-id="14f3c-106">Un modelo de asociación tiene una estructura simple.</span><span class="sxs-lookup"><span data-stu-id="14f3c-106">An association model has a simple structure.</span></span> <span data-ttu-id="14f3c-107">Cada modelo tiene un único nodo primario que representa el modelo y sus metadatos, y cada nodo primario tiene una lista plana de conjuntos de elementos y reglas.</span><span class="sxs-lookup"><span data-stu-id="14f3c-107">Each model has a single parent node that represents the model and its metadata, and each parent node has a flat list of itemsets and rules.</span></span> <span data-ttu-id="14f3c-108">Estos conjuntos de elementos y reglas no se organizan como árboles, sino que se ordenan con los conjuntos de elementos en primer lugar y las reglas en segundo, como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="14f3c-108">The itemsets and rules are not organized in trees, they are ordered with itemsets first and rules next as shown in the following diagram.</span></span>  
  
 <span data-ttu-id="14f3c-109">![estructura del contenido del modelo para los modelos de asociación](../media/modelcontentstructure-assoc.gif "estructura del contenido del modelo para los modelos de asociación")</span><span class="sxs-lookup"><span data-stu-id="14f3c-109">![structure of model content for association models](../media/modelcontentstructure-assoc.gif "structure of model content for association models")</span></span>  
  
 <span data-ttu-id="14f3c-110">Cada conjunto de elementos está incluido en su propio nodo (NODE_TYPE = 7).</span><span class="sxs-lookup"><span data-stu-id="14f3c-110">Each itemset is contained in its own node (NODE_TYPE = 7).</span></span> <span data-ttu-id="14f3c-111">El *nodo* incluye la definición del conjunto de elementos, el número de casos que contienen dicho conjunto y otro tipo de información.</span><span class="sxs-lookup"><span data-stu-id="14f3c-111">The *node* includes the definition of the itemset, the number of cases that contain this itemset, and other information.</span></span>  
  
 <span data-ttu-id="14f3c-112">Cada regla también está incluida en su propio nodo (NODE_TYPE = 8).</span><span class="sxs-lookup"><span data-stu-id="14f3c-112">Each rule is also contained in its own node (NODE_TYPE = 8).</span></span> <span data-ttu-id="14f3c-113">Una *regla* describe un patrón general para la asociación de los elementos.</span><span class="sxs-lookup"><span data-stu-id="14f3c-113">A *rule* describes a general pattern for how items are associated.</span></span> <span data-ttu-id="14f3c-114">Una regla es similar a una instrucción IF-THEN.</span><span class="sxs-lookup"><span data-stu-id="14f3c-114">A rule is like an IF-THEN statement.</span></span> <span data-ttu-id="14f3c-115">El lado izquierdo de la regla muestra una condición o conjunto de condiciones existentes.</span><span class="sxs-lookup"><span data-stu-id="14f3c-115">The left-hand side of the rule shows an existing condition or set of conditions.</span></span> <span data-ttu-id="14f3c-116">El lado derecho de la regla muestra el elemento del conjunto de datos que está normalmente asociado a las condiciones del lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-116">The right-hand side of the rule shows the item in your data set that is usually associated with the conditions on the left side.</span></span>  
  
 <span data-ttu-id="14f3c-117">**Nota** : si desea extraer las reglas o los conjuntos de datos, puede usar una consulta que devuelva únicamente los tipos de nodos deseados.</span><span class="sxs-lookup"><span data-stu-id="14f3c-117">**Note** If you want to extract either the rules or the itemsets, you can use a query to return only the node types that you want.</span></span> <span data-ttu-id="14f3c-118">Para más información, vea [Ejemplos de consultas del modelo de asociación](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="14f3c-118">For more information, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
## <a name="model-content-for-an-association-model"></a><span data-ttu-id="14f3c-119">Contenido del modelo para un modelo de asociación</span><span class="sxs-lookup"><span data-stu-id="14f3c-119">Model Content for an Association Model</span></span>  
 <span data-ttu-id="14f3c-120">Esta sección solo proporciona detalles y ejemplos para las columnas del contenido del modelo de minería de datos que son relevantes para los modelos de asociación.</span><span class="sxs-lookup"><span data-stu-id="14f3c-120">This section provides detail and examples only for those columns in the mining model content that are relevant for association models.</span></span>  
  
 <span data-ttu-id="14f3c-121">Para obtener información sobre las columnas de uso general en el conjunto de filas de esquema, como MODEL_CATALOG y MODEL_NAME, vea [Contenido del modelo de minería de datos &#40;Analysis Services - Minería de datos&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="14f3c-121">For information about the general-purpose columns in the schema rowset, such as MODEL_CATALOG and MODEL_NAME, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="14f3c-122">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="14f3c-122">MODEL_CATALOG</span></span>  
 <span data-ttu-id="14f3c-123">Nombre de la base de datos en la que se almacena el modelo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-123">Name of the database where the model is stored.</span></span>  
  
 <span data-ttu-id="14f3c-124">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="14f3c-124">MODEL_NAME</span></span>  
 <span data-ttu-id="14f3c-125">Nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-125">Name of the model.</span></span>  
  
 <span data-ttu-id="14f3c-126">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="14f3c-126">ATTRIBUTE_NAME</span></span>  
 <span data-ttu-id="14f3c-127">Nombres de los atributos que corresponden a este nodo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-127">The names of the attributes that correspond to this node.</span></span>  
  
 <span data-ttu-id="14f3c-128">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="14f3c-128">NODE_NAME</span></span>  
 <span data-ttu-id="14f3c-129">El nombre del nodo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-129">The name of the node.</span></span> <span data-ttu-id="14f3c-130">Para un modelo de asociación, esta columna contendrá el mismo valor que NODE_UNIQUE_NAME.</span><span class="sxs-lookup"><span data-stu-id="14f3c-130">For an association model, this column contains the same value as NODE_UNIQUE_NAME.</span></span>  
  
 <span data-ttu-id="14f3c-131">NODE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="14f3c-131">NODE_UNIQUE_NAME</span></span>  
 <span data-ttu-id="14f3c-132">Nombre único del nodo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-132">The unique name of the node.</span></span>  
  
 <span data-ttu-id="14f3c-133">NODE_TYPE</span><span class="sxs-lookup"><span data-stu-id="14f3c-133">NODE_TYPE</span></span>  
 <span data-ttu-id="14f3c-134">Un modelo de asociación genera únicamente los tipos de nodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="14f3c-134">A association model outputs only the following node types:</span></span>  
  
|<span data-ttu-id="14f3c-135">Identificador del tipo de nodo</span><span class="sxs-lookup"><span data-stu-id="14f3c-135">Node Type ID</span></span>|<span data-ttu-id="14f3c-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="14f3c-136">Type</span></span>|  
|------------------|----------|  
|<span data-ttu-id="14f3c-137">1 (Modelo)</span><span class="sxs-lookup"><span data-stu-id="14f3c-137">1 (Model)</span></span>|<span data-ttu-id="14f3c-138">Raíz o nodo primario.</span><span class="sxs-lookup"><span data-stu-id="14f3c-138">Root or parent node.</span></span>|  
|<span data-ttu-id="14f3c-139">7 (Conjunto de elementos)</span><span class="sxs-lookup"><span data-stu-id="14f3c-139">7 (Itemset)</span></span>|<span data-ttu-id="14f3c-140">Conjunto de elementos o colección de pares de atributo-valor.</span><span class="sxs-lookup"><span data-stu-id="14f3c-140">An itemset, or collection of attribute-value pairs.</span></span> <span data-ttu-id="14f3c-141">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="14f3c-141">Examples:</span></span><br /><br /> `Product 1 = Existing, Product 2 = Existing`<br /><br /> <span data-ttu-id="14f3c-142">or</span><span class="sxs-lookup"><span data-stu-id="14f3c-142">or</span></span><br /><br /> <span data-ttu-id="14f3c-143">`Gender = Male`.</span><span class="sxs-lookup"><span data-stu-id="14f3c-143">`Gender = Male`.</span></span>|  
|<span data-ttu-id="14f3c-144">8 (Regla)</span><span class="sxs-lookup"><span data-stu-id="14f3c-144">8 (Rule)</span></span>|<span data-ttu-id="14f3c-145">Regla que define cómo se relacionan entre sí los elementos.</span><span class="sxs-lookup"><span data-stu-id="14f3c-145">A rule defining how items relate to each other.</span></span><br /><br /> <span data-ttu-id="14f3c-146">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="14f3c-146">Example:</span></span><br /><br /> <span data-ttu-id="14f3c-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span><span class="sxs-lookup"><span data-stu-id="14f3c-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span></span>|  
  
 <span data-ttu-id="14f3c-148">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="14f3c-148">NODE_CAPTION</span></span>  
 <span data-ttu-id="14f3c-149">Etiqueta o título asociado al nodo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-149">A label or a caption associated with the node.</span></span>  
  
 <span data-ttu-id="14f3c-150">**Nodo de conjunto de elementos** Una lista de elementos separados por comas.</span><span class="sxs-lookup"><span data-stu-id="14f3c-150">**Itemset node** A comma-separated list of items.</span></span>  
  
 <span data-ttu-id="14f3c-151">**Nodo de regla** Contiene los lados derecho e izquierdo de la regla.</span><span class="sxs-lookup"><span data-stu-id="14f3c-151">**Rule node** Contains the left and right-hand sides of the rule.</span></span>  
  
 <span data-ttu-id="14f3c-152">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="14f3c-152">CHILDREN_CARDINALITY</span></span>  
 <span data-ttu-id="14f3c-153">Indica el número de elementos secundarios del nodo actual.</span><span class="sxs-lookup"><span data-stu-id="14f3c-153">Indicates the number of children of the current node.</span></span>  
  
 <span data-ttu-id="14f3c-154">**Nodo primario** : indica el número total de conjuntos de elementos más las reglas.</span><span class="sxs-lookup"><span data-stu-id="14f3c-154">**Parent node** Indicates the total number of itemsets plus rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14f3c-155">Para obtener un análisis del recuento de conjuntos de elementos y reglas, vea la columna NODE_DESCRIPTION para el nodo raíz del modelo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-155">To get a breakdown of the count for itemsets and rules, see the NODE_DESCRIPTION for the root node of the model.</span></span>  
  
 <span data-ttu-id="14f3c-156">**Nodo de conjunto de elementos o de regla** : siempre 0.</span><span class="sxs-lookup"><span data-stu-id="14f3c-156">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="14f3c-157">PARENT_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="14f3c-157">PARENT_UNIQUE_NAME</span></span>  
 <span data-ttu-id="14f3c-158">Nombre único del nodo primario del nodo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-158">The unique name of the node's parent.</span></span>  
  
 <span data-ttu-id="14f3c-159">**Nodo primario** Siempre es NULL.</span><span class="sxs-lookup"><span data-stu-id="14f3c-159">**Parent node** Always NULL.</span></span>  
  
 <span data-ttu-id="14f3c-160">**Nodo de conjunto de elementos o de regla** : siempre 0.</span><span class="sxs-lookup"><span data-stu-id="14f3c-160">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="14f3c-161">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14f3c-161">NODE_DESCRIPTION</span></span>  
 <span data-ttu-id="14f3c-162">Descripción breve y fácil de comprender del contenido del nodo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-162">A user-friendly description of the contents of the node.</span></span>  
  
 <span data-ttu-id="14f3c-163">**Nodo primario** Incluye una lista separada por comas con la siguiente información sobre el modelo:</span><span class="sxs-lookup"><span data-stu-id="14f3c-163">**Parent node** Includes a comma-separated list of the following information about the model:</span></span>  
  
|<span data-ttu-id="14f3c-164">Elemento</span><span class="sxs-lookup"><span data-stu-id="14f3c-164">Item</span></span>|<span data-ttu-id="14f3c-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="14f3c-165">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="14f3c-166">ITEMSET_COUNT</span><span class="sxs-lookup"><span data-stu-id="14f3c-166">ITEMSET_COUNT</span></span>|<span data-ttu-id="14f3c-167">Recuento de todos los conjuntos de elementos del modelo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-167">Count of all itemsets in model.</span></span>|  
|<span data-ttu-id="14f3c-168">RULE_COUNT</span><span class="sxs-lookup"><span data-stu-id="14f3c-168">RULE_COUNT</span></span>|<span data-ttu-id="14f3c-169">Recuento de todas las reglas del modelo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-169">Count of all rules in model.</span></span>|  
|<span data-ttu-id="14f3c-170">MIN_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="14f3c-170">MIN_SUPPORT</span></span>|<span data-ttu-id="14f3c-171">Soporte mínimo para cualquier conjunto de elementos único.</span><span class="sxs-lookup"><span data-stu-id="14f3c-171">The minimum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="14f3c-172">**Nota** Este valor puede ser diferente del valor establecido para el parámetro *MINIMUM _SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="14f3c-172">**Note** This value might differ from the value that you set for the *MINIMUM _SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="14f3c-173">MAX_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="14f3c-173">MAX_SUPPORT</span></span>|<span data-ttu-id="14f3c-174">Soporte máximo para cualquier conjunto de elementos único.</span><span class="sxs-lookup"><span data-stu-id="14f3c-174">The maximum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="14f3c-175">**Nota** Este valor puede ser diferente del valor establecido para el parámetro *MAXIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="14f3c-175">**Note** This value might differ from the value that you set for the *MAXIMUM_SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="14f3c-176">MIN_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="14f3c-176">MIN_ITEMSET_SIZE</span></span>|<span data-ttu-id="14f3c-177">Tamaño del conjunto de elementos más pequeño, representado como recuento de elementos.</span><span class="sxs-lookup"><span data-stu-id="14f3c-177">The size of the smallest itemset, represented as a count of items.</span></span><br /><br /> <span data-ttu-id="14f3c-178">Un valor de 0 indica que el estado `Missing` se trató como un elemento independiente.</span><span class="sxs-lookup"><span data-stu-id="14f3c-178">A value of 0 indicates that the `Missing` state was treated as an independent item.</span></span><br /><br /> <span data-ttu-id="14f3c-179">**Nota** El valor predeterminado del parámetro *MINIMUM_ITEMSET_SIZE* es 1.</span><span class="sxs-lookup"><span data-stu-id="14f3c-179">**Note** The default value of the *MINIMUM_ITEMSET_SIZE* parameter is 1.</span></span>|  
|<span data-ttu-id="14f3c-180">MAX_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="14f3c-180">MAX_ITEMSET_SIZE</span></span>|<span data-ttu-id="14f3c-181">Indica el tamaño del conjunto de elementos más grande que se encontró.</span><span class="sxs-lookup"><span data-stu-id="14f3c-181">Indicates the size of the largest itemset that was found.</span></span><br /><br /> <span data-ttu-id="14f3c-182">**Nota** Este valor está restringido por el valor establecido para el parámetro *MAX_ITEMSET_SIZE* al crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-182">**Note** This value is constrained by the value that you set for the *MAX_ITEMSET_SIZE* parameter when you created the model.</span></span> <span data-ttu-id="14f3c-183">Este tamaño nunca puede superar dicho valor; sin embargo, puede ser menor.</span><span class="sxs-lookup"><span data-stu-id="14f3c-183">This value can never exceed that value; however, it can be less.</span></span> <span data-ttu-id="14f3c-184">El valor predeterminado es 3.</span><span class="sxs-lookup"><span data-stu-id="14f3c-184">The default value is 3.</span></span>|  
|<span data-ttu-id="14f3c-185">MIN_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="14f3c-185">MIN_PROBABILITY</span></span>|<span data-ttu-id="14f3c-186">Probabilidad mínima detectada para cualquier conjunto de elementos o regla únicos del modelo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-186">The minimum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="14f3c-187">Ejemplo: 0,400390625</span><span class="sxs-lookup"><span data-stu-id="14f3c-187">Example: 0.400390625</span></span><br /><br /> <span data-ttu-id="14f3c-188">**Nota** En los conjuntos de elementos, este valor es siempre mayor que el establecido para el parámetro *MINIMUM_PROBABILITY* al crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-188">**Note** For itemsets, this value is always greater than the value that you set for the *MINIMUM_PROBABILITY* parameter when you created the model.</span></span>|  
|<span data-ttu-id="14f3c-189">MAX_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="14f3c-189">MAX_PROBABILITY</span></span>|<span data-ttu-id="14f3c-190">Probabilidad máxima detectada para cualquier conjunto de elementos o regla únicos del modelo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-190">The maximum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="14f3c-191">Ejemplo: 1</span><span class="sxs-lookup"><span data-stu-id="14f3c-191">Example: 1</span></span><br /><br /> <span data-ttu-id="14f3c-192">**Nota** : no hay ningún parámetro para restringir la probabilidad máxima de los conjuntos de elementos.</span><span class="sxs-lookup"><span data-stu-id="14f3c-192">**Note** There is no parameter to constrain maximum probability of itemsets.</span></span> <span data-ttu-id="14f3c-193">Si quiere eliminar los elementos que son demasiado frecuentes, use el parámetro *MAXIMUM_SUPPORT* en su lugar.</span><span class="sxs-lookup"><span data-stu-id="14f3c-193">If you want to eliminate items that are too frequent, use the *MAXIMUM_SUPPORT* parameter instead.</span></span>|  
|<span data-ttu-id="14f3c-194">MIN_LIFT</span><span class="sxs-lookup"><span data-stu-id="14f3c-194">MIN_LIFT</span></span>|<span data-ttu-id="14f3c-195">Cantidad mínima de elevación proporcionada por el modelo para cualquier conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="14f3c-195">The minimum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="14f3c-196">Ejemplo: 0,14309369632511</span><span class="sxs-lookup"><span data-stu-id="14f3c-196">Example: 0.14309369632511</span></span><br /><br /> <span data-ttu-id="14f3c-197">Nota: Conocer la elevación mínima puede ayudar a determinar si la elevación para cualquier conjunto de elementos es importante.</span><span class="sxs-lookup"><span data-stu-id="14f3c-197">Note: Knowing the minimum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
|<span data-ttu-id="14f3c-198">MAX_LIFT</span><span class="sxs-lookup"><span data-stu-id="14f3c-198">MAX_LIFT</span></span>|<span data-ttu-id="14f3c-199">Cantidad máxima de elevación proporcionada por el modelo para cualquier conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="14f3c-199">The maximum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="14f3c-200">Ejemplo: 1,95758227647523 **Nota** : conocer la elevación máxima puede ayudar a determinar si la elevación para cualquier conjunto de elementos es importante.</span><span class="sxs-lookup"><span data-stu-id="14f3c-200">Example: 1.95758227647523 **Note** Knowing the maximum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
  
 <span data-ttu-id="14f3c-201">**Nodo de conjunto de elementos** Los nodos de conjunto de elementos contienen una lista de los elementos, mostrados como una cadena de texto separada por comas.</span><span class="sxs-lookup"><span data-stu-id="14f3c-201">**Itemset node** Itemset nodes contain a list of the items, displayed as a comma-separated text string.</span></span>  
  
 <span data-ttu-id="14f3c-202">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="14f3c-202">Example:</span></span>  
  
 `Touring Tire = Existing, Water Bottle = Existing`  
  
 <span data-ttu-id="14f3c-203">Esto significa que las cubiertas Touring y las botellas de agua se adquirieron juntas.</span><span class="sxs-lookup"><span data-stu-id="14f3c-203">This means touring tires and water bottles were purchased together.</span></span>  
  
 <span data-ttu-id="14f3c-204">**Nodo de regla** Los nodos de regla contienen el lado izquierdo y el derecho de la regla, separados por una flecha.</span><span class="sxs-lookup"><span data-stu-id="14f3c-204">**Rule node** Rule nodes contains a left-hand and right-hand side of the rule, separated by an arrow.</span></span>  
  
 <span data-ttu-id="14f3c-205">Ejemplo: `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span><span class="sxs-lookup"><span data-stu-id="14f3c-205">Example: `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span></span>  
  
 <span data-ttu-id="14f3c-206">Esto significa que si alguien compró una cubierta Touring y una botella de agua, es probable que también comprase una gorra de ciclismo (cycling cup).</span><span class="sxs-lookup"><span data-stu-id="14f3c-206">This means that if someone bought a touring tire and a water bottle, they were also likely to buy a cycling cap.</span></span>  
  
 <span data-ttu-id="14f3c-207">NODE_RULE</span><span class="sxs-lookup"><span data-stu-id="14f3c-207">NODE_RULE</span></span>  
 <span data-ttu-id="14f3c-208">Fragmento de XML que describe la regla o el conjunto de elementos que está incrustado en el nodo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-208">An XML fragment that describes the rule or itemset that is embedded in the node.</span></span>  
  
 <span data-ttu-id="14f3c-209">**Nodo primario** : en blanco.</span><span class="sxs-lookup"><span data-stu-id="14f3c-209">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="14f3c-210">**Nodo de conjunto de elementos** : en blanco.</span><span class="sxs-lookup"><span data-stu-id="14f3c-210">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="14f3c-211">**Nodo de regla** El fragmento XML incluye información útil adicional sobre la regla, como el soporte, la confianza y el número de elementos, así como el identificador del nodo que representa el lado izquierdo de la regla.</span><span class="sxs-lookup"><span data-stu-id="14f3c-211">**Rule node** The XML fragment includes additional useful information about the rule, such as support, confidence, and the number of items, and the ID of the node that represents the left-hand side of the rule.</span></span>  
  
 <span data-ttu-id="14f3c-212">MARGINAL_RULE</span><span class="sxs-lookup"><span data-stu-id="14f3c-212">MARGINAL_RULE</span></span>  
 <span data-ttu-id="14f3c-213">: en blanco.</span><span class="sxs-lookup"><span data-stu-id="14f3c-213">Blank.</span></span>  
  
 <span data-ttu-id="14f3c-214">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="14f3c-214">NODE_PROBABILITY</span></span>  
 <span data-ttu-id="14f3c-215">Puntuación de confianza o probabilidad asociada al conjunto de elementos o a la regla.</span><span class="sxs-lookup"><span data-stu-id="14f3c-215">A probability or confidence score associated with the itemset or rule.</span></span>  
  
 <span data-ttu-id="14f3c-216">**Nodo primario** : siempre 0.</span><span class="sxs-lookup"><span data-stu-id="14f3c-216">**Parent node** Always 0.</span></span>  
  
 <span data-ttu-id="14f3c-217">**Nodo de conjunto de elementos** : probabilidad del conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="14f3c-217">**Itemset node** Probability of the itemset.</span></span>  
  
 <span data-ttu-id="14f3c-218">**Nodo de regla** : valor de confianza para la regla.</span><span class="sxs-lookup"><span data-stu-id="14f3c-218">**Rule node** Confidence value for the rule.</span></span>  
  
 <span data-ttu-id="14f3c-219">MARGINAL_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="14f3c-219">MARGINAL_PROBABILITY</span></span>  
 <span data-ttu-id="14f3c-220">Igual que NODE_PROBABILITY.</span><span class="sxs-lookup"><span data-stu-id="14f3c-220">Same as NODE_PROBABILITY.</span></span>  
  
 <span data-ttu-id="14f3c-221">NODE_DISTRIBUTION</span><span class="sxs-lookup"><span data-stu-id="14f3c-221">NODE_DISTRIBUTION</span></span>  
 <span data-ttu-id="14f3c-222">Esta tabla contiene información muy diferente, dependiendo de si el nodo es un conjunto de elementos o una regla.</span><span class="sxs-lookup"><span data-stu-id="14f3c-222">The table contains very different information, depending on whether the node is an itemset or a rule.</span></span>  
  
 <span data-ttu-id="14f3c-223">**Nodo primario** : en blanco.</span><span class="sxs-lookup"><span data-stu-id="14f3c-223">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="14f3c-224">**Nodo de conjunto de elementos** : muestra el nombre de cada elemento del conjunto de elementos, junto con un valor de soporte y probabilidad.</span><span class="sxs-lookup"><span data-stu-id="14f3c-224">**Itemset node** Lists each item in the itemset together with a probability and support value.</span></span> <span data-ttu-id="14f3c-225">Por ejemplo, si el conjunto de elementos contiene dos productos, se muestra el nombre de cada uno junto con el recuento de casos que incluyen cada producto.</span><span class="sxs-lookup"><span data-stu-id="14f3c-225">For example, if the itemset contains two products, the name of each product is listed, together with the count of cases that include each product.</span></span>  
  
 <span data-ttu-id="14f3c-226">**Nodo de regla** : contiene dos filas.</span><span class="sxs-lookup"><span data-stu-id="14f3c-226">**Rule node** Contains two rows.</span></span> <span data-ttu-id="14f3c-227">La primera fila muestra el atributo del lado derecho de la regla, que es el elemento predicho, junto con una puntuación de confianza.</span><span class="sxs-lookup"><span data-stu-id="14f3c-227">The first row shows the attribute from the right-hand side of the rule, which is the predicted item, together with a confidence score.</span></span>  
  
 <span data-ttu-id="14f3c-228">La segunda fila es única para los modelos de asociación; contiene un puntero al conjunto de elementos del lado derecho de la regla.</span><span class="sxs-lookup"><span data-stu-id="14f3c-228">The second row is unique to association models; it contains a pointer to the itemset on the right-hand side of the rule.</span></span> <span data-ttu-id="14f3c-229">El puntero se representa en la columna ATTRIBUTE_VALUE como identificador del conjunto de elementos que contiene únicamente el elemento del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="14f3c-229">The pointer is represented in the ATTRIBUTE_VALUE column as the ID of the itemset that contains only the right-hand item.</span></span>  
  
 <span data-ttu-id="14f3c-230">Por ejemplo, si la regla es `If {A,B} Then {C}`, la tabla contiene el nombre del elemento `{C}`y el identificador del nodo que contiene el conjunto de elementos para el elemento C.</span><span class="sxs-lookup"><span data-stu-id="14f3c-230">For example, if the rule is `If {A,B} Then {C}`, the table contains the name of the item `{C}`, and the ID of the node that contains the itemset for item C.</span></span>  
  
 <span data-ttu-id="14f3c-231">Este puntero es útil porque permite determinar a partir del nodo de conjunto de elementos cuántos casos en total incluyen el producto del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="14f3c-231">This pointer is useful because you can determine from the itemset node how many cases in all include the right-hand side product.</span></span> <span data-ttu-id="14f3c-232">Los casos que están sujetos a la regla `If {A,B} Then {C}` son un subconjunto de los casos incluidos en el conjunto de elementos para `{C}`.</span><span class="sxs-lookup"><span data-stu-id="14f3c-232">The cases that are subject to the rule `If {A,B} Then {C}` are a subset of the cases listed in the itemset for `{C}`.</span></span>  
  
 <span data-ttu-id="14f3c-233">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="14f3c-233">NODE_SUPPORT</span></span>  
 <span data-ttu-id="14f3c-234">Número de casos que admiten este nodo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-234">The number of cases that support this node.</span></span>  
  
 <span data-ttu-id="14f3c-235">**Nodo primario** : número de casos del modelo.</span><span class="sxs-lookup"><span data-stu-id="14f3c-235">**Parent node** Number of cases in the model.</span></span>  
  
 <span data-ttu-id="14f3c-236">**Nodo de conjunto de elementos** : número de casos que contienen todos los elementos del conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="14f3c-236">**Itemset node** Number of cases that contains all items in the itemset.</span></span>  
  
 <span data-ttu-id="14f3c-237">**Nodo de regla** : número de casos que contienen todos los elementos incluidos en la regla.</span><span class="sxs-lookup"><span data-stu-id="14f3c-237">**Rule node** The number of cases that contain all items included in the rule.</span></span>  
  
 <span data-ttu-id="14f3c-238">MSOLAP_MODEL_COLUMN</span><span class="sxs-lookup"><span data-stu-id="14f3c-238">MSOLAP_MODEL_COLUMN</span></span>  
 <span data-ttu-id="14f3c-239">Contiene información diferente dependiendo de si el nodo es un conjunto de elementos o una regla.</span><span class="sxs-lookup"><span data-stu-id="14f3c-239">Contains different information depending on whether the node is an itemset or rule.</span></span>  
  
 <span data-ttu-id="14f3c-240">**Nodo primario** : en blanco.</span><span class="sxs-lookup"><span data-stu-id="14f3c-240">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="14f3c-241">**Nodo de conjunto de elementos** : en blanco.</span><span class="sxs-lookup"><span data-stu-id="14f3c-241">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="14f3c-242">**Nodo de regla** El identificador del conjunto de elementos que contiene los elementos del lado izquierdo de la regla.</span><span class="sxs-lookup"><span data-stu-id="14f3c-242">**Rule node** The ID of the itemset that contains the items in the left-hand side of the rule.</span></span> <span data-ttu-id="14f3c-243">Por ejemplo, si la regla es `If {A,B} Then {C}`, esta columna incluye el identificador del conjunto de elementos que contiene únicamente `{A,B}`.</span><span class="sxs-lookup"><span data-stu-id="14f3c-243">For example, if the rule is `If {A,B} Then {C}`, this column contains the ID of the itemset that contains only `{A,B}`.</span></span>  
  
 <span data-ttu-id="14f3c-244">MSOLAP_NODE_SCORE</span><span class="sxs-lookup"><span data-stu-id="14f3c-244">MSOLAP_NODE_SCORE</span></span>  
 <span data-ttu-id="14f3c-245">**Nodo primario** : en blanco.</span><span class="sxs-lookup"><span data-stu-id="14f3c-245">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="14f3c-246">**Nodo de conjunto de elementos** : puntuación de importancia para el conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="14f3c-246">**Itemset node** Importance score for the itemset.</span></span>  
  
 <span data-ttu-id="14f3c-247">**Nodo de regla** : puntuación de importancia para la regla.</span><span class="sxs-lookup"><span data-stu-id="14f3c-247">**Rule node** Importance score for the rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14f3c-248">La importancia se calcula de forma diferente para los conjuntos de elementos y para las reglas.</span><span class="sxs-lookup"><span data-stu-id="14f3c-248">Importance is calculated differently for itemsets and rules.</span></span> <span data-ttu-id="14f3c-249">Para más información, vea [Referencia técnica del algoritmo de asociación de Microsoft](microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="14f3c-249">For more information, see [Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="14f3c-250">MSOLAP_NODE_SHORT_CAPTION</span><span class="sxs-lookup"><span data-stu-id="14f3c-250">MSOLAP_NODE_SHORT_CAPTION</span></span>  
 <span data-ttu-id="14f3c-251">: en blanco.</span><span class="sxs-lookup"><span data-stu-id="14f3c-251">Blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f3c-252">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14f3c-252">See Also</span></span>  
 <span data-ttu-id="14f3c-253">[Contenido del modelo de minería de datos &#40;Analysis Services:&#41;de minería de datos](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="14f3c-253">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="14f3c-254">[Algoritmo de Asociación de Microsoft](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="14f3c-254">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 [<span data-ttu-id="14f3c-255">Ejemplos de consultas del modelo de asociación</span><span class="sxs-lookup"><span data-stu-id="14f3c-255">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
  
