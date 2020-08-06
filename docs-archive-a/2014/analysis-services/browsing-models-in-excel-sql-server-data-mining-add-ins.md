---
title: Examinar modelos en Excel (complementos de minería de datos de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- browse models
- mining models, viewing
ms.assetid: a8cca1d7-602a-449a-875c-99da564965bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: c992f1f61112478a85276b6596da0137ccd5c9be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670090"
---
# <a name="browsing-models-in-excel-sql-server-data-mining-add-ins"></a><span data-ttu-id="6eb9c-102">Examinar modelos en Excel (Complementos de minería de datos de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6eb9c-102">Browsing Models in Excel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="6eb9c-103">![Examinar modelo, cinta de opciones Minería de datos](media/dmc-browse.gif "Examinar modelo, cinta de opciones Minería de datos")</span><span class="sxs-lookup"><span data-stu-id="6eb9c-103">![Browse Model button in Data Mining ribbon](media/dmc-browse.gif "Browse Model button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="6eb9c-104">La exploración visual del modelo es, por lo general, la forma más rápida y fácil de conocer las reglas y relaciones que se identifican mediante análisis.</span><span class="sxs-lookup"><span data-stu-id="6eb9c-104">Visually exploring the model is usually the fastest and easiest way to get an understanding of the rules and relationships discovered by analysis.</span></span> <span data-ttu-id="6eb9c-105">Con el Cliente de minería de datos para Excel, puede examinar tanto los modelos provisionales que se han creado en la sesión actual de Excel, como los modelos almacenados en una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6eb9c-105">By using the Data Mining Client for Excel, you can browse both temporary models created during the current Excel session, and models stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6eb9c-106">Para examinar un modelo, se selecciona un modelo y la estructura asociada en una lista de modelos disponibles, y el complemento elige automáticamente el visor adecuado para el algoritmo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6eb9c-106">To browse a model, you select a model and its associated structure from a list of available models, and the add-in automatically picks the viewer that is appropriate for that data mining algorithm.</span></span> <span data-ttu-id="6eb9c-107">Puede obtener detalles de las tendencias más interesantes, filtrar el modelo completo de minería de datos y copiar gráficos y datos en Excel o Visio.</span><span class="sxs-lookup"><span data-stu-id="6eb9c-107">You can drill into the most interesting trends, filter the completed data mining model, and copy graphs and data to Excel or to Visio.</span></span>  
  
## <a name="using-the-browse-model-wizard"></a><span data-ttu-id="6eb9c-108">Usar el Asistente para examinar modelos</span><span class="sxs-lookup"><span data-stu-id="6eb9c-108">Using the Browse Model Wizard</span></span>  
  
1.  <span data-ttu-id="6eb9c-109">Haga clic en la pestaña **minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="6eb9c-109">Click the **Data Mining** tab.</span></span>  
  
2.  <span data-ttu-id="6eb9c-110">En el grupo **uso del modelo** , haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="6eb9c-110">In the **Model Usage** group, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="6eb9c-111">En el cuadro de diálogo **Seleccionar modelo** , elija un modelo de minería de datos en la lista y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6eb9c-111">In the **Select Model** dialog box, choose a mining model from the list, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="6eb9c-112">El asistente abre una ventana **examinar** que es adecuada para el tipo de modelo que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6eb9c-112">The wizard opens a **Browse** window that is appropriate for the type of model that you selected.</span></span>  
  
## <a name="list-of-data-mining-viewers"></a><span data-ttu-id="6eb9c-113">Lista de visores de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6eb9c-113">List of Data Mining Viewers</span></span>  
 <span data-ttu-id="6eb9c-114">En función del algoritmo de minería de datos que se haya utilizado al crear el modelo, la ventana **examinar** tendrá un aspecto un poco diferente.</span><span class="sxs-lookup"><span data-stu-id="6eb9c-114">Depending on the data mining algorithm that you used when you created the model, the **Browse** window will look a bit different.</span></span> <span data-ttu-id="6eb9c-115">Puede incluir gráficos para ayudar a interpretar los resultados, leyendas que contienen detalles adicionales y controles para interactuar con los datos.</span><span class="sxs-lookup"><span data-stu-id="6eb9c-115">It can include graphs to help interpret the results, legends that contain additional detail, and controls for interacting with the data.</span></span>  
  
 <span data-ttu-id="6eb9c-116">Los temas siguientes proporcionan instrucciones sobre cómo usar cada uno de los visores y se incluyen sugerencias sobre cómo interpretar gráficos complejos y sobre cómo cambiar, copiar o trabajar con los resultados.</span><span class="sxs-lookup"><span data-stu-id="6eb9c-116">The following topics provide guidance in how to use each of the viewers, including tips on interpreting the complex graphs, and how to change, copy, or work with the results.</span></span>  
  
 [<span data-ttu-id="6eb9c-117">Examinar un modelo de reglas de asociación</span><span class="sxs-lookup"><span data-stu-id="6eb9c-117">Browsing an Association Rules Model</span></span>](browsing-an-association-rules-model.md)  
  
 [<span data-ttu-id="6eb9c-118">Examinar un modelo de clústeres</span><span class="sxs-lookup"><span data-stu-id="6eb9c-118">Browsing a Clustering Model</span></span>](browsing-a-clustering-model.md)  
  
 [<span data-ttu-id="6eb9c-119">Examinar un modelo de árboles de decisión</span><span class="sxs-lookup"><span data-stu-id="6eb9c-119">Browsing a Decision Trees Model</span></span>](browsing-a-decision-trees-model.md)  
  
 [<span data-ttu-id="6eb9c-120">Examinar un modelo de pronóstico</span><span class="sxs-lookup"><span data-stu-id="6eb9c-120">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
 [<span data-ttu-id="6eb9c-121">Examinar un modelo Bayes naive</span><span class="sxs-lookup"><span data-stu-id="6eb9c-121">Browsing a Naive Bayes Model</span></span>](browsing-a-naive-bayes-model.md)  
  
 [<span data-ttu-id="6eb9c-122">Examinar un modelo de red neuronal</span><span class="sxs-lookup"><span data-stu-id="6eb9c-122">Browsing a Neural Network Model</span></span>](browsing-a-neural-network-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="6eb9c-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6eb9c-123">See Also</span></span>  
 <span data-ttu-id="6eb9c-124">[Ver modelos de minería de datos en Visio &#40;complementos de minería de datos&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="6eb9c-124">[Viewing Data Mining Models in Visio &#40;Data Mining Add-ins&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="6eb9c-125">Administrar modelos &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="6eb9c-125">Manage Models &#40;SQL Server Data Mining Add-ins&#41;</span></span>](manage-models-sql-server-data-mining-add-ins.md)  
  
  
