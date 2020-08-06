---
title: 'Lección 6: definir cálculos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e0a1e354-e879-4eb8-bb2b-6c3809e32cb6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e0b3f7e925a11146204dc6c55e9ddd6820ecb802
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671773"
---
# <a name="lesson-6-defining-calculations"></a><span data-ttu-id="ff654-102">Lección 6: Definir cálculos</span><span class="sxs-lookup"><span data-stu-id="ff654-102">Lesson 6: Defining Calculations</span></span>
  <span data-ttu-id="ff654-103">En esta lección, aprenderá a definir cálculos, que son scripts o expresiones de Expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="ff654-103">In this lesson, you learn to define calculations, which are Multidimensional Expressions (MDX) expressions or scripts.</span></span> <span data-ttu-id="ff654-104">Los cálculos le permiten definir miembros calculados, conjuntos con nombre y ejecutar otros comandos de script para ampliar las capacidades de un cubo de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff654-104">Calculations enable you to define calculated members, named sets, and execute other script commands to extend the capabilities of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span> <span data-ttu-id="ff654-105">Por ejemplo, puede ejecutar un comando de script para definir un subcubo y, a continuación, asignar un cálculo a las celdas del subcubo.</span><span class="sxs-lookup"><span data-stu-id="ff654-105">For example, you can run a script command to define a subcube and then assign a calculation to the cells in the subcube.</span></span>  
  
 <span data-ttu-id="ff654-106">Al definir un nuevo cálculo en el Diseñador de cubos, el cálculo se agrega al panel **Organizador de script** de la pestaña **Cálculos** del Diseñador de cubos, y los campos del tipo de cálculo en cuestión aparecen en un formulario de cálculos en el panel de las **expresiones de cálculo** .</span><span class="sxs-lookup"><span data-stu-id="ff654-106">When you define a new calculation in Cube Designer, the calculation is added to the **Script Organizer** pane of the **Calculations** tab of Cube Designer, and the fields for the particular calculation type are displayed in a calculations form in the **Calculation Expressions** pane.</span></span> <span data-ttu-id="ff654-107">Los cálculos se ejecutan en el orden en el que aparecen en el panel **Organizador de script** .</span><span class="sxs-lookup"><span data-stu-id="ff654-107">Calculations are executed in the order in which they are listed in the **Script Organizer** pane.</span></span> <span data-ttu-id="ff654-108">Para reorganizar los cálculos, haga clic con el botón derecho en un cálculo determinado y seleccione **Subir** o **Bajar**, o haga clic en un cálculo determinado y use los iconos **Subir** o **Bajar** en la barra de herramientas de la pestaña **Cálculos** .</span><span class="sxs-lookup"><span data-stu-id="ff654-108">You can reorder the calculations by right-clicking on a particular calculation and then selecting **Move Up** or **Move Down**, or by clicking a particular calculation and then using the **Move Up** or **Move Down** icons on the toolbar of the **Calculations** tab.</span></span>  
  
 <span data-ttu-id="ff654-109">En la pestaña **Cálculos** , puede agregar nuevos cálculos y ver o editar cálculos existentes en las vistas siguientes del panel de las **expresiones de cálculo** :</span><span class="sxs-lookup"><span data-stu-id="ff654-109">On the **Calculations** tab, you can add new calculations and view or edit existing calculations in the following views in the **Calculation Expressions** pane:</span></span>  
  
-   <span data-ttu-id="ff654-110">Vista de formulario.</span><span class="sxs-lookup"><span data-stu-id="ff654-110">Form view.</span></span> <span data-ttu-id="ff654-111">Esta vista muestra las expresiones y propiedades de un comando único en formato de gráfico.</span><span class="sxs-lookup"><span data-stu-id="ff654-111">This view shows the expressions and properties for a single command in a graphical format.</span></span> <span data-ttu-id="ff654-112">Al editar un script MDX, un cuadro de expresión rellena la vista de formulario.</span><span class="sxs-lookup"><span data-stu-id="ff654-112">When you edit an MDX script, an expression box fills the Form view.</span></span>  
  
-   <span data-ttu-id="ff654-113">Vista de script.</span><span class="sxs-lookup"><span data-stu-id="ff654-113">Script view.</span></span> <span data-ttu-id="ff654-114">Esta vista muestra todos los scripts de cálculo en un editor de código, lo que le permite cambiar fácilmente los scripts de cálculo.</span><span class="sxs-lookup"><span data-stu-id="ff654-114">This view displays all calculation scripts in a code editor, which lets you easily change the calculation scripts.</span></span> <span data-ttu-id="ff654-115">Cuando el panel de las **expresiones de cálculo** está en la Vista de script, el **Organizador de script** estará oculto.</span><span class="sxs-lookup"><span data-stu-id="ff654-115">When the **Calculation Expressions** pane is in Script view, the **Script Organizer** is hidden.</span></span> <span data-ttu-id="ff654-116">La Vista de script proporciona codificación de color, coincidencia de paréntesis, autocompletar y regiones de código MDX.</span><span class="sxs-lookup"><span data-stu-id="ff654-116">The Script view provides color coding, parenthesis matching, auto-complete, and MDX code regions.</span></span> <span data-ttu-id="ff654-117">Puede expandir o contraer las regiones de código MDX para facilitar la edición.</span><span class="sxs-lookup"><span data-stu-id="ff654-117">You can expand or collapse the MDX code regions to make editing easier.</span></span>  
  
 <span data-ttu-id="ff654-118">Para cambiar de una vista a otra en el panel de las **expresiones de cálculo** , haga clic en **Vista de formulario** o **Vista de script** en la barra de herramientas de la pestaña **Cálculos** .</span><span class="sxs-lookup"><span data-stu-id="ff654-118">To switch between these views in the **Calculation Expressions** pane, click **Form View** or **Script View** on the toolbar of the **Calculations** tab.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff654-119">Si [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] detecta un error de sintaxis en algún cálculo, la vista de formulario no aparecerá hasta que el error se haya corregido en la Vista de script.</span><span class="sxs-lookup"><span data-stu-id="ff654-119">If [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] detects a syntax error in any calculation, the Form view will not display until the error is corrected in the Script view.</span></span>  
  
 <span data-ttu-id="ff654-120">También puede utilizar el Asistente de Business Intelligence para agregar determinados cálculos a un cubo.</span><span class="sxs-lookup"><span data-stu-id="ff654-120">You can also use the Business Intelligence Wizard to add certain calculations to a cube.</span></span> <span data-ttu-id="ff654-121">Por ejemplo, puede utilizar este asistente para agregar inteligencia de tiempo a un cubo, lo que significa definir miembros calculados para cálculos relacionados con el tiempo como, por ejemplo, períodos hasta fecha, medias móviles o crecimiento entre períodos.</span><span class="sxs-lookup"><span data-stu-id="ff654-121">For example, you can use this wizard to add time intelligence to a cube, which means defining calculated members for time-related calculations such as period-to-date, moving averages, or period over period growth.</span></span> <span data-ttu-id="ff654-122">Para obtener más información, vea [Definir cálculos de inteligencia de tiempo mediante el Asistente de Business Intelligence](multidimensional-models/define-time-intelligence-calculations-using-the-business-intelligence-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="ff654-122">For more information, see [Define Time Intelligence Calculations using the Business Intelligence Wizard](multidimensional-models/define-time-intelligence-calculations-using-the-business-intelligence-wizard.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ff654-123">En la pestaña **Cálculos** , el script de cálculo empieza por el comando CALCULATE.</span><span class="sxs-lookup"><span data-stu-id="ff654-123">On the **Calculations** tab, the calculation script starts with the CALCULATE command.</span></span> <span data-ttu-id="ff654-124">El comando CALCULATE controla la agregación de las celdas en el cubo y solo debería editar este comando si intenta especificar manualmente la forma en que se deberían agregar las celdas del cubo.</span><span class="sxs-lookup"><span data-stu-id="ff654-124">The CALCULATE command controls the aggregation of the cells in the cube and you should edit this command only if you intend to manually specify how the cube cells should be aggregated.</span></span>  
  
 <span data-ttu-id="ff654-125">Para obtener más información, consulte [Cálculos](multidimensional-models-olap-logical-cube-objects/calculations.md)y [Cálculos en modelos multidimensionales](multidimensional-models/calculations-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="ff654-125">For more information, see [Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md), and [Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff654-126">Los proyectos completos para todas las lecciones de este tutorial están disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="ff654-126">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="ff654-127">Puede saltar a continuación a cualquier lección con el proyecto completado de la lección anterior como punto de partida.</span><span class="sxs-lookup"><span data-stu-id="ff654-127">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="ff654-128">[Haga clic aquí](https://go.microsoft.com/fwlink/?LinkID=221866) para descargar los proyectos de ejemplo que tienen que ver con este tutorial.</span><span class="sxs-lookup"><span data-stu-id="ff654-128">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="ff654-129">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="ff654-129">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="ff654-130">Definir miembros calculados</span><span class="sxs-lookup"><span data-stu-id="ff654-130">Defining Calculated Members</span></span>](lesson-6-1-defining-calculated-members.md)  
 <span data-ttu-id="ff654-131">En esta tarea, aprenderá a definir miembros calculados.</span><span class="sxs-lookup"><span data-stu-id="ff654-131">In this task, you learn to define calculated members.</span></span>  
  
 [<span data-ttu-id="ff654-132">Definir conjuntos con nombre</span><span class="sxs-lookup"><span data-stu-id="ff654-132">Defining Named Sets</span></span>](lesson-6-2-defining-named-sets.md)  
 <span data-ttu-id="ff654-133">En esta tarea, aprenderá a definir conjuntos con nombre.</span><span class="sxs-lookup"><span data-stu-id="ff654-133">In this task, you learn to define named sets.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="ff654-134">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="ff654-134">Next Lesson</span></span>  
 [<span data-ttu-id="ff654-135">Lección 7: Definir indicadores clave de rendimiento &#40;KPI&#41;</span><span class="sxs-lookup"><span data-stu-id="ff654-135">Lesson 7: Defining Key Performance Indicators &#40;KPIs&#41;</span></span>](lesson-7-defining-key-performance-indicators-kpis.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff654-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff654-136">See Also</span></span>  
 <span data-ttu-id="ff654-137">[Escenario de Analysis Services tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ff654-137">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="ff654-138">[Modelo multidimensional &#40;tutorial de Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ff654-138">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="ff654-139">[Crear conjuntos con nombre](multidimensional-models/create-named-sets.md) </span><span class="sxs-lookup"><span data-stu-id="ff654-139">[Create Named Sets](multidimensional-models/create-named-sets.md) </span></span>  
 [<span data-ttu-id="ff654-140">Crear miembros calculados</span><span class="sxs-lookup"><span data-stu-id="ff654-140">Create Calculated Members</span></span>](multidimensional-models/create-calculated-members.md)  
  
  