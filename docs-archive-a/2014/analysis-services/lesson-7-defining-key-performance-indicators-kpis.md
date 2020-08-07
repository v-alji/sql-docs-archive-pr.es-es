---
title: 'Lección 7: definir indicadores clave de rendimiento (KPI) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 36d53770-294f-43ab-8850-15d5351ff60c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87df6fd91a66505f124144cafd9a44c6e5e70e85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745471"
---
# <a name="lesson-7-defining-key-performance-indicators-kpis"></a><span data-ttu-id="df118-102">Lección 7: definir indicadores clave de rendimiento (KPI)</span><span class="sxs-lookup"><span data-stu-id="df118-102">Lesson 7: Defining Key Performance Indicators (KPIs)</span></span>
  <span data-ttu-id="df118-103">En esta lección, aprenderá a definir indicadores clave de rendimiento (KPI) en su proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df118-103">In this lesson, you learn to define Key Performance Indicators (KPIs) in your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="df118-104">Los KPI proporcionan un marco para definir cálculos del servidor que midan su negocio y estandarizar la forma en que aparezca la información resultante.</span><span class="sxs-lookup"><span data-stu-id="df118-104">KPIs provide a framework for defining server-side calculations that measure your business, and they standardize how the resulting information is displayed.</span></span> <span data-ttu-id="df118-105">Los KPI pueden aparecer en informes, portales y paneles, mediante las API de acceso a datos, y mediante herramientas de [!INCLUDE[msCoName](../includes/msconame-md.md)] y herramientas de terceros.</span><span class="sxs-lookup"><span data-stu-id="df118-105">KPIs can be displayed in reports, portals, and dashboards, through data access APIs, and through [!INCLUDE[msCoName](../includes/msconame-md.md)] tools and third-party tools.</span></span> <span data-ttu-id="df118-106">Los KPI son contenedores de metadatos alrededor de medidas normales y otras expresiones de Expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="df118-106">KPIs are metadata wrappers around regular measures and other Multidimensional Expressions (MDX) expressions.</span></span> <span data-ttu-id="df118-107">Para obtener más información, consulte [Indicadores clave de rendimiento &#40;KPI&#41; en modelos multidimensionales](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="df118-107">For more information, see [Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df118-108">Los proyectos completos para todas las lecciones de este tutorial están disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="df118-108">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="df118-109">Puede saltar a continuación a cualquier lección con el proyecto completado de la lección anterior como punto de partida.</span><span class="sxs-lookup"><span data-stu-id="df118-109">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="df118-110">[Haga clic aquí](https://go.microsoft.com/fwlink/?LinkID=221866) para descargar los proyectos de ejemplo que tienen que ver con este tutorial.</span><span class="sxs-lookup"><span data-stu-id="df118-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="df118-111">Esta lección contiene la siguiente tarea:</span><span class="sxs-lookup"><span data-stu-id="df118-111">This lesson contains the following task:</span></span>  
  
 [<span data-ttu-id="df118-112">Definir y examinar KPI</span><span class="sxs-lookup"><span data-stu-id="df118-112">Defining and Browsing KPIs</span></span>](lesson-7-1-defining-and-browsing-kpis.md)  
 <span data-ttu-id="df118-113">En esta tarea, se definen los KPI en la vista Formulario y, a continuación, se va a la vista Explorador para examinar los datos del cubo mediante los KPI.</span><span class="sxs-lookup"><span data-stu-id="df118-113">In this task, you define KPIs in the Form view and then switch to the Browser view to browse the cube data by using the KPIs.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="df118-114">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="df118-114">Next Lesson</span></span>  
 [<span data-ttu-id="df118-115">Lección 8: definir acciones</span><span class="sxs-lookup"><span data-stu-id="df118-115">Lesson 8: Defining Actions</span></span>](lesson-8-defining-actions.md)  
  
## <a name="see-also"></a><span data-ttu-id="df118-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df118-116">See Also</span></span>  
 <span data-ttu-id="df118-117">[Escenario de Analysis Services tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="df118-117">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="df118-118">[Modelo multidimensional &#40;tutorial de Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="df118-118">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="df118-119">Indicadores clave de rendimiento &#40;KPI&#41; en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="df118-119">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)  
  
  
