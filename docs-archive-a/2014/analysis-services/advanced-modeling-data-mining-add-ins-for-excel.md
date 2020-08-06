---
title: Modelado avanzado (complementos de minería de datos para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures, creating
ms.assetid: 042270a3-6ec7-4b52-b2ba-2adb6c4740d5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 771eb6111765b558995ee3b0eb98196c63951567
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670232"
---
# <a name="advanced-modeling-data-mining-add-ins-for-excel"></a><span data-ttu-id="604a5-102">Modelado avanzado (Complementos de minería de datos para Excel)</span><span class="sxs-lookup"><span data-stu-id="604a5-102">Advanced Modeling (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="604a5-103">Puede utilizar las opciones de modelado de datos **avanzadas** para crear estructuras y modelos de minería de datos personalizados con parámetros distintos de los creados por los asistentes.</span><span class="sxs-lookup"><span data-stu-id="604a5-103">You can use the **Advanced** data modeling options to create custom data mining structures and models with parameters different from those created by the wizards.</span></span> <span data-ttu-id="604a5-104">Los dos asistentes descritos en esta sección le ayudan a crear una estructura de minería de datos completamente nueva y un nuevo modelo de minería de datos para aplicarlos a una estructura de minería de datos existente.</span><span class="sxs-lookup"><span data-stu-id="604a5-104">The two wizards described in this section help you create a completely new data mining structure, and a new mining model to apply to an existing data mining structure.</span></span>  
  
## <a name="create-mining-structure"></a><span data-ttu-id="604a5-105">Crear estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="604a5-105">Create Mining Structure</span></span>  
 <span data-ttu-id="604a5-106">![Botón Crear estructura de minería de datos, cinta de opciones Minería de datos](media/dmc-createstruct.gif "Botón Crear estructura de minería de datos, cinta de opciones Minería de datos")</span><span class="sxs-lookup"><span data-stu-id="604a5-106">![Create Mining Structure button, Data Mining ribbon](media/dmc-createstruct.gif "Create Mining Structure button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="604a5-107">El **Asistente para crear estructuras de minería** de datos le ayuda a crear una nueva estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="604a5-107">The **Create Mining Structure Wizard** helps you build a new data mining structure.</span></span> <span data-ttu-id="604a5-108">Una estructura es una colección de datos extraídos de un origen de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="604a5-108">A structure is a collection of data extracted from a specified data source.</span></span>  <span data-ttu-id="604a5-109">Una estructura de minería de datos se puede actualizar con datos nuevos en el origen, pero al crear la estructura de minería de datos, debe definir tipos y nombres de datos que especifiquen cómo se utilizarán los datos para el análisis.</span><span class="sxs-lookup"><span data-stu-id="604a5-109">A mining structure can be updated with new data at the source, but when you create the mining structure, you define data types and names that define how the data is used for analysis.</span></span>  
  
 <span data-ttu-id="604a5-110">Puede utilizar los siguientes orígenes de datos para generar la estructura: una tabla de Excel, un intervalo de Excel o los datos en un origen de datos externo que ya se haya definido como una vista de origen de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="604a5-110">You can use the following data sources to build your structure: an Excel table, an Excel range, or any data in an external data source that has already been defined as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source view.</span></span>  
  
 <span data-ttu-id="604a5-111">Para cada estructura, tiene la opción de apartar algunos de los datos que se utilizarán para las pruebas y la validación.</span><span class="sxs-lookup"><span data-stu-id="604a5-111">For each structure, you have the option of setting aside some of the data to use for testing and validation.</span></span> <span data-ttu-id="604a5-112">Al crear este *conjunto de datos de exclusión* al configurar los orígenes de datos, puede asegurarse de que todos los modelos basados en la estructura puedan usar un conjunto de datos coherente para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="604a5-112">By creating this *holdout data set* when you set up your data sources, you can ensure that all models that are based on the structure are able to use a consistent data set for testing.</span></span>  
  
 <span data-ttu-id="604a5-113">Una vez creada una estructura de minería de datos, puede agregar varios modelos para aplicar distintos métodos de análisis.</span><span class="sxs-lookup"><span data-stu-id="604a5-113">After you have created a mining structure, you can add multiple models to apply different methods of analysis.</span></span>  
  
 <span data-ttu-id="604a5-114">Para obtener más información acerca de cómo utilizar el **Asistente para crear estructuras de minería**de datos, vea [create mining Structure &#40;SQL Server complementos de minería de datos&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="604a5-114">For more information about how to use the **Create Mining Structure Wizard**, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="add-model-to-structure"></a><span data-ttu-id="604a5-115">Agregar modelo a estructura</span><span class="sxs-lookup"><span data-stu-id="604a5-115">Add Model to Structure</span></span>  
 <span data-ttu-id="604a5-116">![Botón Agregar un modelo a una estructura](media/dmc-addmodel.gif "Botón Agregar un modelo a una estructura")</span><span class="sxs-lookup"><span data-stu-id="604a5-116">![Add Model to Structure button](media/dmc-addmodel.gif "Add Model to Structure button")</span></span>  
  
 <span data-ttu-id="604a5-117">Cuando se agrega un modelo nuevo a una estructura, se analizan los datos mediante un algoritmo diferente o con otros parámetros.</span><span class="sxs-lookup"><span data-stu-id="604a5-117">When you add a new model to a structure, you analyze the data by using a different algorithm, or with different parameters.</span></span> <span data-ttu-id="604a5-118">Esta opción es especialmente útil si desea crear un modelo mediante uno de los algoritmos que no se exponen en las herramientas del Cliente de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="604a5-118">This option is particularly useful if you want to create a model using one of the algorithms not exposed in the Data Mining Client tools.</span></span>  
  
 <span data-ttu-id="604a5-119">Por ejemplo, puede usar los algoritmos que admite [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="604a5-119">For example, you can use any of the algorithms supported by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], such as:</span></span>  
  
-   <span data-ttu-id="604a5-120">Regresión lineal</span><span class="sxs-lookup"><span data-stu-id="604a5-120">Linear regression</span></span>  
  
-   <span data-ttu-id="604a5-121">Agrupación en clústeres de secuencia</span><span class="sxs-lookup"><span data-stu-id="604a5-121">Sequence clustering</span></span>  
  
-   <span data-ttu-id="604a5-122">Análisis de asociación en conjuntos de datos anidados</span><span class="sxs-lookup"><span data-stu-id="604a5-122">Association analysis on nested data sets</span></span>  
  
 <span data-ttu-id="604a5-123">Para ver qué tipo de estructuras de minería de datos están disponibles, puede examinar los modelos y las estructuras almacenados en haciendo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] clic en **administrar modelos** o en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="604a5-123">To see what kind of mining structures are available, you can browse the models and structures stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] by clicking either **Manage Models** or **Browse**.</span></span>  
  
 <span data-ttu-id="604a5-124">Está limitado a las estructuras de minería de datos que se crearon durante la sesión actual o a las estructuras de minería de datos que se guardaron en una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="604a5-124">You are limited to data mining structures that were created during the current session, or mining structures that were saved to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="604a5-125">Para obtener más información, vea [Agregar un modelo a una estructura &#40;complementos de minería de datos para Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="604a5-125">For more information, see [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604a5-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="604a5-126">See Also</span></span>  
 <span data-ttu-id="604a5-127">[Administrar modelos &#40;SQL Server complementos de minería de datos&#41;](manage-models-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="604a5-127">[Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="604a5-128">Examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="604a5-128">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
