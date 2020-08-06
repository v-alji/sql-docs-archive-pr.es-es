---
title: Copiar una vista de un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clipboards [data mining]
- Mining Model Viewer [Analysis Services], clipboards
- copying mining models to clipboard
ms.assetid: 768372db-e5b4-4990-b459-03d854fd9a6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 36d4d372bd235cd1cc0c043ff98151091e242269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743701"
---
# <a name="copy-a-view-of-a-mining-model"></a><span data-ttu-id="9783c-102">Copiar una vista de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="9783c-102">Copy a View of a Mining Model</span></span>
  <span data-ttu-id="9783c-103">La pestaña **Visor de modelos de minería de datos** del Diseñador de minería de datos de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] utiliza un visor separado para cada tipo de modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="9783c-103">The **Mining Model Viewer** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] uses a separate viewer for each type of mining model.</span></span> <span data-ttu-id="9783c-104">Varios de los visores tienen componentes cuyo contenido se puede copiar al Portapapeles, y desde ahí, pegar el contenido en un documento o en un software de tratamiento de imágenes.</span><span class="sxs-lookup"><span data-stu-id="9783c-104">Several of the viewers have components from which you can copy the contents to the Clipboard, and from there paste the contents into a document or into image manipulation software.</span></span> <span data-ttu-id="9783c-105">Los componentes que permiten realizar esta funcionalidad son:</span><span class="sxs-lookup"><span data-stu-id="9783c-105">The following components make this functionality available:</span></span>  
  
-   <span data-ttu-id="9783c-106">Diagrama del clúster en el Visor de clústeres de [!INCLUDE[msCoName](../../includes/msconame-md.md)] y el Visor de clústeres de secuencia de [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9783c-106">Cluster Diagram in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cluster Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="9783c-107">Árbol de decisión en el Visor de árboles de [!INCLUDE[msCoName](../../includes/msconame-md.md)] y el Visor de series temporales de [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9783c-107">Decision Tree in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series Viewer</span></span>  
  
-   <span data-ttu-id="9783c-108">Transiciones de estado en el Visor de clústeres de secuencia de [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9783c-108">State Transitions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="9783c-109">Red de dependencias en el Visor de reglas de asociación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] , Visor Bayes naive de [!INCLUDE[msCoName](../../includes/msconame-md.md)] y Visor de árboles de [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9783c-109">Dependency Network in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer, and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer</span></span>  
  
-   <span data-ttu-id="9783c-110">Contenido del modelo de minería de datos, del panel Detalles de nodo del Visor de árbol de contenido genérico de [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9783c-110">Mining model content, from the Node Details pane of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer</span></span>  
  
 <span data-ttu-id="9783c-111">Puede copiar la representación completa del modelo de minería de datos o solo la parte que está visible en el visor.</span><span class="sxs-lookup"><span data-stu-id="9783c-111">You can copy the complete representation of the mining model, or just the part that is visible in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="9783c-112">Al copiar un modelo usando el visor, no se crea un objeto de modelo nuevo.</span><span class="sxs-lookup"><span data-stu-id="9783c-112">When you copy a model using the viewer, it does not create a new model object.</span></span> <span data-ttu-id="9783c-113">Para crear un modelo nuevo, debe usar el asistente o el Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="9783c-113">To create a new model, you must use either the wizard, or the Data Mining Designer,.</span></span> <span data-ttu-id="9783c-114">Para obtener más información, vea [Realizar una copia de un modelo de minería de datos](make-a-copy-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="9783c-114">For more information, see [Make a Copy of a Mining Model](make-a-copy-of-a-mining-model.md).</span></span>  
  
### <a name="to-copy-the-complete-model-to-the-clipboard"></a><span data-ttu-id="9783c-115">Para copiar el modelo completo en el portapapeles</span><span class="sxs-lookup"><span data-stu-id="9783c-115">To copy the complete model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="9783c-116">En la lista **Modelo de minería de datos** en la pestaña **Visor de modelos de minería de datos** , seleccione el modelo de minería de datos que desee ver.</span><span class="sxs-lookup"><span data-stu-id="9783c-116">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="9783c-117">Seleccione la pestaña adecuada, por ejemplo, la pestaña **Red de dependencias** y, a continuación, haga clic en **Copiar todo el gráfico** en la barra de herramientas de esa pestaña.</span><span class="sxs-lookup"><span data-stu-id="9783c-117">Select the appropriate tab, such as the **Dependency Network** tab, and then click **Copy Entire Graph** on the toolbar of that tab.</span></span>  
  
### <a name="to-copy-the-visible-piece-of-the-model-to-the-clipboard"></a><span data-ttu-id="9783c-118">Para copiar en el Portapapeles la parte visible del modelo</span><span class="sxs-lookup"><span data-stu-id="9783c-118">To copy the visible piece of the model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="9783c-119">En la lista **Modelo de minería de datos** en la pestaña **Visor de modelos de minería de datos** , seleccione el modelo de minería de datos que desee ver.</span><span class="sxs-lookup"><span data-stu-id="9783c-119">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="9783c-120">Seleccione la pestaña adecuada, por ejemplo, la pestaña **Red de dependencias** y, a continuación, acerque o aleje para ver el modelo en el nivel que desee.</span><span class="sxs-lookup"><span data-stu-id="9783c-120">Select the appropriate tab, such as the **Dependency Network** tab, and then zoom in or out to view the model at the level that you want.</span></span>  
  
3.  <span data-ttu-id="9783c-121">Haga clic en **Copiar vista del gráfico** en la barra de herramientas de la pestaña seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9783c-121">Click **Copy Graph View** on the toolbar of the selected tab.</span></span>  
  
### <a name="to-copy-the-mining-model-content-to-the-clipboard"></a><span data-ttu-id="9783c-122">Para copiar el contenido del modelo de minería de datos en el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="9783c-122">To copy the mining model content to the Clipboard</span></span>  
  
1.  <span data-ttu-id="9783c-123">En la lista **Modelo de minería de datos** en la pestaña **Visor de modelos de minería de datos** , seleccione el modelo de minería de datos que desee ver.</span><span class="sxs-lookup"><span data-stu-id="9783c-123">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="9783c-124">En la lista desplegable **Visor** , seleccione **Visor de árbol de contenido genérico de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="9783c-124">From the **Viewer** drop-down list, select **Microsoft Generic Content Tree Viewer**.</span></span>  
  
3.  <span data-ttu-id="9783c-125">En el panel **Título del nodo (id. único)** , haga clic en un nodo.</span><span class="sxs-lookup"><span data-stu-id="9783c-125">In the **Node Caption (Unique ID)** pane, click a node.</span></span>  
  
4.  <span data-ttu-id="9783c-126">Haga clic con el botón derecho en el panel **Detalles del nodo** y, después, seleccione **Seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="9783c-126">Right-click the **Node Details** pane and then select **Select All**.</span></span>  
  
5.  <span data-ttu-id="9783c-127">Haga clic con el botón derecho en el panel **Detalles del nodo** de nuevo y seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="9783c-127">Right-click the **Node Details** pane again and select **Copy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9783c-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9783c-128">See Also</span></span>  
 [<span data-ttu-id="9783c-129">Tareas y procedimientos del Visor de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="9783c-129">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
  
