---
title: 'Lección 8: definir acciones | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 15459396-83c9-48a0-b10a-99ae38768c79
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d4daaed3f1992478b309529fc15e2e903a27920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748385"
---
# <a name="lesson-8-defining-actions"></a><span data-ttu-id="8a255-102">Lección 8: definir acciones</span><span class="sxs-lookup"><span data-stu-id="8a255-102">Lesson 8: Defining Actions</span></span>
  <span data-ttu-id="8a255-103">En esta lección, aprenderá a definir acciones en el proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8a255-103">In this lesson, you will learn to define actions in your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="8a255-104">Una acción es solo una instrucción de Expresiones multidimensionales (MDX) que se almacena en [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y que se puede incorporar en las aplicaciones cliente e iniciarse por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8a255-104">An action is just a Multidimensional Expressions (MDX) statement that is stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and which can be incorporated into client applications and started by a user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a255-105">Los proyectos completos para todas las lecciones de este tutorial están disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="8a255-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="8a255-106">Puede saltar a continuación a cualquier lección con el proyecto completado de la lección anterior como punto de partida.</span><span class="sxs-lookup"><span data-stu-id="8a255-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="8a255-107">[Haga clic aquí](https://go.microsoft.com/fwlink/?LinkID=221866) para descargar los proyectos de ejemplo que tienen que ver con este tutorial.</span><span class="sxs-lookup"><span data-stu-id="8a255-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="8a255-108">admite los tipos de acciones descritos en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="8a255-108">supports the types of actions that are described in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a255-109">CommandLine</span><span class="sxs-lookup"><span data-stu-id="8a255-109">CommandLine</span></span>|<span data-ttu-id="8a255-110">Ejecuta un comando en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="8a255-110">Executes a command at the command prompt</span></span>|  
|<span data-ttu-id="8a255-111">Dataset</span><span class="sxs-lookup"><span data-stu-id="8a255-111">Dataset</span></span>|<span data-ttu-id="8a255-112">Devuelve un conjunto de datos a una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="8a255-112">Returns a dataset to a client application.</span></span>|  
|<span data-ttu-id="8a255-113">Obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="8a255-113">Drillthrough</span></span>|<span data-ttu-id="8a255-114">Devuelve una instrucción de obtención de detalles como una expresión, que el cliente ejecuta para devolver un conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="8a255-114">Returns a drillthrough statement as an expression, which the client executes to return a rowset</span></span>|  
|<span data-ttu-id="8a255-115">Html</span><span class="sxs-lookup"><span data-stu-id="8a255-115">Html</span></span>|<span data-ttu-id="8a255-116">Ejecuta un script HTML en un explorador de Internet.</span><span class="sxs-lookup"><span data-stu-id="8a255-116">Executes an HTML script in an Internet browser</span></span>|  
|<span data-ttu-id="8a255-117">Propietario</span><span class="sxs-lookup"><span data-stu-id="8a255-117">Proprietary</span></span>|<span data-ttu-id="8a255-118">Ejecuta una operación con una interfaz que no aparece en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="8a255-118">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="8a255-119">Informe</span><span class="sxs-lookup"><span data-stu-id="8a255-119">Report</span></span>|<span data-ttu-id="8a255-120">Envía una solicitud parametrizada basada en una dirección URL a un servidor de informes y devuelve un informe a una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="8a255-120">Submits a parameterized URL-based request to a report server and returns a report to a client application.</span></span>|  
|<span data-ttu-id="8a255-121">Conjunto de filas</span><span class="sxs-lookup"><span data-stu-id="8a255-121">Rowset</span></span>|<span data-ttu-id="8a255-122">Devuelve un conjunto de filas a una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="8a255-122">Returns a rowset to a client application.</span></span>|  
|<span data-ttu-id="8a255-123">Instrucción</span><span class="sxs-lookup"><span data-stu-id="8a255-123">Statement</span></span>|<span data-ttu-id="8a255-124">Ejecuta un comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8a255-124">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="8a255-125">URL</span><span class="sxs-lookup"><span data-stu-id="8a255-125">URL</span></span>|<span data-ttu-id="8a255-126">Muestra una página web dinámica en un explorador de Internet.</span><span class="sxs-lookup"><span data-stu-id="8a255-126">Displays a dynamic Web page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="8a255-127">Las acciones permiten a los usuarios iniciar una aplicación o realizar otros pasos en el contexto de un elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8a255-127">Actions let users start an application or perform other steps within the context of a selected item.</span></span> <span data-ttu-id="8a255-128">Para obtener más información, vea [Acciones &#40;Analysis Services - Datos multidimensionales&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Acciones en modelos multidimensionales](multidimensional-models/actions-in-multidimensional-models.md)</span><span class="sxs-lookup"><span data-stu-id="8a255-128">For more information, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a255-129">Para obtener ejemplos de acciones, vea los ejemplos de acciones en la pestaña Plantillas del panel Herramientas de cálculo o en los ejemplos del almacenamiento de datos de ejemplo [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW.</span><span class="sxs-lookup"><span data-stu-id="8a255-129">For examples of actions, see the action examples on the Templates tab in the Calculation Tools pane or in the examples in the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW sample data warehouse.</span></span> <span data-ttu-id="8a255-130">Para obtener más información sobre cómo instalar esta base de datos, vea [Instalar los datos y proyectos de ejemplo para el tutorial de modelado multidimensional de Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="8a255-130">For more information about installing this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>  
  
 <span data-ttu-id="8a255-131">Esta lección incluye la tarea siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a255-131">This lesson includes the following task:</span></span>  
  
 [<span data-ttu-id="8a255-132">Definir y usar una acción de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="8a255-132">Defining and Using a Drillthrough Action</span></span>](lesson-8-1-defining-and-using-a-drillthrough-action.md)  
 <span data-ttu-id="8a255-133">En esta tarea, se define, utiliza y modifica una acción de obtención de detalles a través de la relación de dimensión de hecho definida anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="8a255-133">In this task, you define, use, and then modify a drillthrough action through the fact dimension relationship that you defined earlier in this tutorial.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="8a255-134">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="8a255-134">Next Lesson</span></span>  
 [<span data-ttu-id="8a255-135">Lección 9: definir perspectivas y traducciones</span><span class="sxs-lookup"><span data-stu-id="8a255-135">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="8a255-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a255-136">See Also</span></span>  
 <span data-ttu-id="8a255-137">[Escenario de Analysis Services tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="8a255-137">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="8a255-138">[Modelo multidimensional &#40;tutorial de Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="8a255-138">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="8a255-139">[Acciones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8a255-139">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="8a255-140">Acciones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="8a255-140">Actions in Multidimensional Models</span></span>](multidimensional-models/actions-in-multidimensional-models.md)  
  
  
