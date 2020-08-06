---
title: Especificar los datos de entrenamiento (Asistente para minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytrainingdata.f1
ms.assetid: cb04deeb-0f89-4bba-b3f1-efccada16825
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87a802256d287a3e8e9e7fb65bbd91687cb71a4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675536"
---
# <a name="specify-the-training-data-data-mining-wizard"></a><span data-ttu-id="3eeb0-102">Especificar los datos de entrenamiento (Asistente para minería de datos)</span><span class="sxs-lookup"><span data-stu-id="3eeb0-102">Specify the Training Data (Data Mining Wizard)</span></span>
  <span data-ttu-id="3eeb0-103">Utilice la página **Especificar los datos de aprendizaje** para identificar las columnas que se van a incluir en la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-103">Use the **Specify the Training Data** page to identify which columns to include in the mining structure.</span></span> <span data-ttu-id="3eeb0-104">Puede seleccionar columnas para que se incluyan en la estructura aunque no las utilice en todos los modelos.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-104">You can select columns to include in the structure even if you do not use them in all models.</span></span> <span data-ttu-id="3eeb0-105">Por ejemplo, si desea obtener detalles de las columnas del modelo de minería, puede incluirlas en la estructura pero no en el modelo.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-105">For example, if you want to drill through to the columns from the mining model, you can include them in the structure but not in the model.</span></span>  
  
 <span data-ttu-id="3eeb0-106">Se requiere al lo menos una columna de clave para cada tabla que está incluida en la estructura.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-106">At least one key column is required for each table that is included in the structure.</span></span> <span data-ttu-id="3eeb0-107">La columna elegida como clave depende de que la tabla sea una tabla de casos o una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-107">The column that you pick as the key depends on whether the table is a case table or a nested table.</span></span> <span data-ttu-id="3eeb0-108">Si la tabla es una tabla anidada, la clave es a menudo también la columna de predicción, no la clave externa relacional.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-108">If the table is a nested table, the key is often also the predictable column, not the relational foreign key.</span></span> <span data-ttu-id="3eeb0-109">Para más información sobre las claves anidadas, vea [Tablas anidadas &#40;Analysis Services - Minería de datos&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3eeb0-109">To learn about nested keys, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3eeb0-110">Los diferentes algoritmos de minería utilizan las claves de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-110">Different mining algorithms use keys differently.</span></span> <span data-ttu-id="3eeb0-111">Para más información sobre los diferentes tipos de claves, vea [Tipos de contenido &#40;minería de datos&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3eeb0-111">To learn about the different kinds of keys, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="3eeb0-112">**Para más información:** [Estructuras de minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Columnas del modelo de minería de datos](data-mining/mining-model-columns.md), [Asistente para minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Crear una estructura de minería de datos relacional](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="3eeb0-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="3eeb0-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="3eeb0-113">Options</span></span>  
 <span data-ttu-id="3eeb0-114">**Tablas y columnas**</span><span class="sxs-lookup"><span data-stu-id="3eeb0-114">**Tables/Columns**</span></span>  
 <span data-ttu-id="3eeb0-115">Muestra las tablas y columnas seleccionadas en la página anterior del asistente.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-115">Displays the tables and columns that you selected on the previous page of the wizard.</span></span>  
  
 **\<check box>**  
 <span data-ttu-id="3eeb0-116">Seleccione las columnas que desea incluir en la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-116">Select the columns to include in the mining structure.</span></span>  
  
 <span data-ttu-id="3eeb0-117">Si su origen de datos incluye tablas anidadas o vistas múltiples, expanda la lista de columnas para ver las tablas anidadas.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-117">If your data source includes nested tables or multiple views, expand the column list to view the nested tables.</span></span>  
  
 <span data-ttu-id="3eeb0-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="3eeb0-118">**Key**</span></span>  
 <span data-ttu-id="3eeb0-119">Seleccione esta opción para utilizar la columna como un identificador único para los datos.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-119">Select to use the column as a unique identifier for the data.</span></span>  
  
 <span data-ttu-id="3eeb0-120">Para una tabla de casos, la clave es normalmente el identificador único.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-120">For a case table, the key is usually the unique identifier.</span></span>  
  
 <span data-ttu-id="3eeb0-121">Para la tabla anidada, la **Clave** indica el identificador de una fila en el contexto del caso asociado.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-121">For nested table, the **Key** indicates the identifier of a row in the context of the associated case.</span></span>  
  
 <span data-ttu-id="3eeb0-122">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="3eeb0-122">**Input**</span></span>  
 <span data-ttu-id="3eeb0-123">Seleccione esta opción para utilizar la columna para crear predicciones.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-123">Select to use the column in creating predictions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3eeb0-124">Esta columna solo está disponible cuando se crea un modelo de minería junto con la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-124">This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="3eeb0-125">**Predicción**</span><span class="sxs-lookup"><span data-stu-id="3eeb0-125">**Predictable**</span></span>  
 <span data-ttu-id="3eeb0-126">Seleccione esta opción para permitir que la tabla o la columna se puedan predecir a partir de una entrada futura adicional.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-126">Select to enable the table or column to be predicted based on additional future input.</span></span>  
  
 <span data-ttu-id="3eeb0-127">Si también marca una tabla anidada como de predicción, la tabla anidada completa se convierte en una tabla de predicción.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-127">If you also mark a nested table as predictable, the whole nested table becomes predictable.</span></span> <span data-ttu-id="3eeb0-128">Si ninguna columna de la tabla anidada está marcada como de entrada o predicción, la tabla anidada aparecerá en la estructura de minería de datos, pero se omitirá en el modelo.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-128">If no columns in the nested table are marked as input or predictable, the nested table will appear in the mining structure, but will be ignored in the model.</span></span>  
  
 <span data-ttu-id="3eeb0-129">**Nota** : esta columna solo está disponible cuando se crea un modelo de minería junto con la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-129">**Note** This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="3eeb0-130">**Sugerir**</span><span class="sxs-lookup"><span data-stu-id="3eeb0-130">**Suggest**</span></span>  
 <span data-ttu-id="3eeb0-131">Haga clic para abrir el cuadro de diálogo **Sugerir columnas relacionadas** , que realiza un análisis de una muestra de datos para identificar las columnas de entrada más relacionadas con la columna **Predicción** seleccionada según la entropía.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-131">Click to open the **Suggest Related Columns** dialog box, which performs an analysis on a sample of data to identify input columns that show the greatest relationship to the selected **Predictable** column based on entropy.</span></span> <span data-ttu-id="3eeb0-132">Este análisis también se aplica a las columnas de la tabla anidada o a las estructuras de minería basadas en orígenes OLAP.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-132">This analysis also applies to nested table columns or mining structures that are based on OLAP sources.</span></span>  
  
 <span data-ttu-id="3eeb0-133">**Nota** : esta columna solo está disponible cuando se crea un modelo de minería junto con la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="3eeb0-133">**Note** This column only available when you are creating a mining model together with the mining structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eeb0-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3eeb0-134">See Also</span></span>  
 <span data-ttu-id="3eeb0-135">[Asistente para minería de datos (ayuda F1) &#40;Analysis Services: minería de datos&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="3eeb0-135">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="3eeb0-136">[Sugerir columnas relacionadas &#40;Asistente para minería de datos&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="3eeb0-136">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="3eeb0-137">[Especificar tipos de tablas &#40;Asistente para minería de datos&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="3eeb0-137">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="3eeb0-138">Especifique el contenido y el tipo de datos de la columna &#40;Asistente para minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="3eeb0-138">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
