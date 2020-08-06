---
title: Hacer una copia de un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], copying
- mining models [Analysis Services], creating
- mining models [Analysis Services], how-to topics
- copying mining models
ms.assetid: 7975bb02-f188-49a0-b7de-5b9b216254ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: a05eb75210ce9f601aeca515cd299f4204908705
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662368"
---
# <a name="make-a-copy-of-a-mining-model"></a><span data-ttu-id="d49b4-102">Realizar una copia de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d49b4-102">Make a Copy of a Mining Model</span></span>
  <span data-ttu-id="d49b4-103">La creación de una copia de un modelo de minería de datos resulta útil para crear rápidamente varios modelos de minería de datos basados en los mismos datos.</span><span class="sxs-lookup"><span data-stu-id="d49b4-103">Creating a copy of a mining model is useful when you want to quickly create several mining models that are based on the same data.</span></span> <span data-ttu-id="d49b4-104">Una vez copiado el modelo, puede modificar la nueva copia de este si cambia los parámetros o agrega un filtro.</span><span class="sxs-lookup"><span data-stu-id="d49b4-104">After you copy the model, you can then edit the new copy by changing parameters or adding a filter.</span></span>  
  
 <span data-ttu-id="d49b4-105">Por ejemplo, si tiene una tabla Customers que está vinculada a una tabla de compras, puede crear copias para generar modelos de minería de datos independientes para cada dato demográfico de los clientes, filtrando por atributos como la edad o la región.</span><span class="sxs-lookup"><span data-stu-id="d49b4-105">For example, if you have a Customers table that is linked to a table of purchases, you could create copies to generate separate mining models for each customer demographic, filtering on attributes such as age or region.</span></span>  
  
 <span data-ttu-id="d49b4-106">Para más información sobre cómo copiar el contenido del modelo (como la representación gráfica o los patrones del modelo) en el Portapapeles para usarlo en otros programas, vea [Copiar una vista de un modelo de minería de datos](copy-a-view-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="d49b4-106">For information about how to copy the content of the model (such as the graphical representation or the model patterns) to the Clipboard for use in other programs, see [Copy a View of a Mining Model](copy-a-view-of-a-mining-model.md).</span></span>  
  
### <a name="to-create-a-related-mining-model"></a><span data-ttu-id="d49b4-107">Para crear un modelo de minería relacionado</span><span class="sxs-lookup"><span data-stu-id="d49b4-107">To create a related mining model</span></span>  
  
1.  <span data-ttu-id="d49b4-108">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], en el Explorador de soluciones, haga clic en la estructura de minería de datos que contiene el modelo de minería.</span><span class="sxs-lookup"><span data-stu-id="d49b4-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model.</span></span>  
  
2.  <span data-ttu-id="d49b4-109">Haga clic en la pestaña **Modelos de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="d49b4-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="d49b4-110">Seleccione el modelo y haga clic con el botón secundario del mouse para abrir el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="d49b4-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="d49b4-111">O bien</span><span class="sxs-lookup"><span data-stu-id="d49b4-111">-or-</span></span>  
  
     <span data-ttu-id="d49b4-112">Seleccione el modelo.</span><span class="sxs-lookup"><span data-stu-id="d49b4-112">Select the model.</span></span> <span data-ttu-id="d49b4-113">En el menú **Modelo de minería de datos** , seleccione **Nuevo modelo de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="d49b4-113">On the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="d49b4-114">Escriba un nombre para el nuevo modelo de minería de datos y seleccione un algoritmo.</span><span class="sxs-lookup"><span data-stu-id="d49b4-114">Type a name for the new mining model, and select an algorithm.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-the-filter-on-the-copied-mining-model"></a><span data-ttu-id="d49b4-115">Para modificar el filtro en el modelo de minería de datos copiado</span><span class="sxs-lookup"><span data-stu-id="d49b4-115">To edit the filter on the copied mining model</span></span>  
  
1.  <span data-ttu-id="d49b4-116">Seleccione el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d49b4-116">Select the mining model.</span></span>  
  
2.  <span data-ttu-id="d49b4-117">En la ventana **propiedades** , haga clic en el cuadro de texto de la propiedad **filtro** y haga clic en el botón compilar **(...)** .</span><span class="sxs-lookup"><span data-stu-id="d49b4-117">In the **Properties** window, click the text box for the **Filter** property, and the click the build **(...)** button.</span></span>  
  
3.  <span data-ttu-id="d49b4-118">Cambiar las condiciones de los filtros.</span><span class="sxs-lookup"><span data-stu-id="d49b4-118">Change the filter conditions.</span></span>  
  
     <span data-ttu-id="d49b4-119">Para más información sobre cómo usar los cuadros de diálogo del editor de filtros, vea [Aplicar un filtro a un modelo de minería de datos](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="d49b4-119">For more information about how to use the filter editor dialog boxes, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
4.  <span data-ttu-id="d49b4-120">En la ventana **propiedades** , en el `AlgorithmParameters` cuadro de texto, haga clic en **parámetros de establecer**y cambie los parámetros del algoritmo, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="d49b4-120">In the **Properties** window, in the `AlgorithmParameters` text box, click **Setalgorithm parameters**, and change algorithm parameters, if desired.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d49b4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d49b4-121">See Also</span></span>  
 <span data-ttu-id="d49b4-122">[Filtros para modelos de minería de datos &#40;Analysis Services-minería de datos&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d49b4-122">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="d49b4-123">[Tareas y procedimientos del modelo de minería de datos](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="d49b4-123">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="d49b4-124">Eliminar un filtro de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d49b4-124">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
