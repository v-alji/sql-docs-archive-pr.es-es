---
title: Ver recomendaciones de optimización | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: e4e690c9-434f-4b01-b4de-0b905323ddd6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d938767d874edd8f14bdaa91c0cf52023478f53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747353"
---
# <a name="viewing-tuning-recommendations"></a><span data-ttu-id="718c6-102">Ver recomendaciones de optimización</span><span class="sxs-lookup"><span data-stu-id="718c6-102">Viewing Tuning Recommendations</span></span>
  <span data-ttu-id="718c6-103"> En esta tarea, se utiliza la sesión de optimización que creó en [Optimizar una carga de trabajo](lesson-1-1-tuning-a-workload.md).</span><span class="sxs-lookup"><span data-stu-id="718c6-103">This task uses the tuning session that you created in [Tuning a Workload](lesson-1-1-tuning-a-workload.md).</span></span> <span data-ttu-id="718c6-104">Después de optimizar la [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] base de datos mediante el script de script. SQL, el [!INCLUDE[tsql](../../includes/tsql-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] Asistente para la optimización de muestra los resultados en la pestaña **recomendaciones** . La siguiente tarea presenta la pestaña **recomendaciones** de la [!INCLUDE[ssDE](../../includes/ssde-md.md)] interfaz gráfica de usuario (GUI) del Asistente para la optimización de y le guía para explorar la información que proporciona sobre los resultados de la sesión de optimización.</span><span class="sxs-lookup"><span data-stu-id="718c6-104">After you have tuned the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using the MyScript.sql [!INCLUDE[tsql](../../includes/tsql-md.md)] script, [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor displays its results on the **Recommendations** tab. The following task introduces the **Recommendations** tab of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor graphical user interface (GUI) and guides you to explore the information it provides about the tuning session results.</span></span>  
  
### <a name="view-tuning-recommendations"></a><span data-ttu-id="718c6-105">Ver las recomendaciones de optimización</span><span class="sxs-lookup"><span data-stu-id="718c6-105">View tuning recommendations</span></span>  
  
1.  <span data-ttu-id="718c6-106">Inicie el Asistente para la optimización de [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="718c6-106">Start [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor.</span></span> <span data-ttu-id="718c6-107">Consulte [Iniciar el Asistente para la optimización de motor de base de datos](../../relational-databases/performance/database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="718c6-107">See [Launching Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="718c6-108">Asegúrese de conectarse a la misma instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que ha usado en la práctica [Optimizar una carga de trabajo](lesson-1-1-tuning-a-workload.md).</span><span class="sxs-lookup"><span data-stu-id="718c6-108">Make sure that you connect to the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that you used in the practice [Tuning a Workload](lesson-1-1-tuning-a-workload.md).</span></span>  
  
2.  <span data-ttu-id="718c6-109">Haga doble clic en **MySession** en el panel **Monitor de sesión** .</span><span class="sxs-lookup"><span data-stu-id="718c6-109">Double-click **MySession** in the **Session Monitor** pane.</span></span> [!INCLUDE[ssDE](../../includes/ssde-md.md)]<span data-ttu-id="718c6-110">Carga la información de sesión de la sesión de optimización anterior y muestra la pestaña **recomendaciones** . tenga en cuenta que el Asistente para la [!INCLUDE[ssDE](../../includes/ssde-md.md)] optimización de no realizó recomendaciones de **partición** porque aceptó todos los valores predeterminados de la opción de optimización y no se ha seleccionado **ninguna partición** en la pestaña **Opciones de optimización** .</span><span class="sxs-lookup"><span data-stu-id="718c6-110">Tuning Advisor loads the session information from your previous tuning session and displays the **Recommendations** tab. Note that [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor made no **Partition Recommendations** because you accepted all the tuning option defaults and **No partitioning** was selected on the **Tuning Options** tab.</span></span>  
  
3.  <span data-ttu-id="718c6-111">En la pestaña **Recomendaciones** , utilice la barra de desplazamiento situada en la parte inferior de la página con pestañas para ver todas las columnas de **Recomendaciones de índices** .</span><span class="sxs-lookup"><span data-stu-id="718c6-111">On the **Recommendations** tab, use the scroll bar at the bottom of the tabbed page to view all of the **Index Recommendations** columns.</span></span> <span data-ttu-id="718c6-112">Cada fila representa un objeto de base de datos (índices o vistas indizadas) que el Asistente para la optimización de [!INCLUDE[ssDE](../../includes/ssde-md.md)] recomienda quitar o crear.</span><span class="sxs-lookup"><span data-stu-id="718c6-112">Each row represents a database object (indexes or indexed views) that [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor recommends be dropped or created.</span></span> <span data-ttu-id="718c6-113">Desplácese hasta la columna situada más a la derecha y haga clic en **Definición**.</span><span class="sxs-lookup"><span data-stu-id="718c6-113">Scroll to the right-most column and click a **Definition**.</span></span> [!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="718c6-114">muestra la ventana **Vista previa de script SQL** , donde se puede ver el script [!INCLUDE[tsql](../../includes/tsql-md.md)] que creará o quitará el objeto de base de datos de esa fila.</span><span class="sxs-lookup"><span data-stu-id="718c6-114">Tuning Advisor displays a **SQL Script Preview** window where you can view the [!INCLUDE[tsql](../../includes/tsql-md.md)] script that creates or drops the database object on that row.</span></span> <span data-ttu-id="718c6-115">Haga clic en **Cerrar** para cerrar la ventana de vista previa.</span><span class="sxs-lookup"><span data-stu-id="718c6-115">Click **Close** to close the preview window.</span></span>  
  
     <span data-ttu-id="718c6-116">Si le resulta difícil encontrar una **Definición** que contenga un vínculo, haga clic para desactivar la casilla **Mostrar objetos existentes** al final de la página con pestañas. Esto hará que el número de filas mostradas disminuya.</span><span class="sxs-lookup"><span data-stu-id="718c6-116">If you are having difficulty locating a **Definition** that contains a link, click to clear the **Show existing objects** check box at the bottom of the tabbed page, which will decrease the number of rows displayed.</span></span> <span data-ttu-id="718c6-117">Cuando desactive esta casilla, el Asistente para la optimización de [!INCLUDE[ssDE](../../includes/ssde-md.md)] solamente mostrará los objetos para los que haya generado una recomendación.</span><span class="sxs-lookup"><span data-stu-id="718c6-117">When you clear this checkbox, [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor shows you only the objects for which it has generated a recommendation.</span></span> <span data-ttu-id="718c6-118">Active la casilla **Mostrar objetos existentes** para ver todos los objetos de base de datos que existen actualmente en la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="718c6-118">Select the **Show existing objects** check box to view all the database objects that currently exist in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="718c6-119">Utilice la barra de desplazamiento situada en la parte derecha de la página con pestañas para ver todos los objetos.</span><span class="sxs-lookup"><span data-stu-id="718c6-119">Use the scroll bar at the right side of the tabbed page to view all of the objects.</span></span>  
  
4.  <span data-ttu-id="718c6-120">Haga clic con el botón derecho en la cuadrícula del panel **Recomendaciones de índices** .</span><span class="sxs-lookup"><span data-stu-id="718c6-120">Right-click the grid in the **Index Recommendations** pane.</span></span> <span data-ttu-id="718c6-121">Este menú contextual permite seleccionar y anular la selección de recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="718c6-121">This right-click menu enables you to select and deselect recommendations.</span></span> <span data-ttu-id="718c6-122">También permite cambiar la fuente del texto de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="718c6-122">It also enables you to change the font for the grid text.</span></span>  
  
5.  <span data-ttu-id="718c6-123">En el menú **Acciones** , haga clic en **Guardar recomendaciones** para guardar todas las recomendaciones en un script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="718c6-123">On the **Actions** menu, click **Save Recommendations** to save all of the recommendations into one [!INCLUDE[tsql](../../includes/tsql-md.md)] script.</span></span> <span data-ttu-id="718c6-124">Llame `MySessionRecommendations.sql` al script.</span><span class="sxs-lookup"><span data-stu-id="718c6-124">Name the script `MySessionRecommendations.sql`.</span></span>  
  
     <span data-ttu-id="718c6-125">Abra el script MySessionRecommendations.sql en el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para verla.</span><span class="sxs-lookup"><span data-stu-id="718c6-125">Open the MySessionRecommendations.sql script in the Query Editor of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to view it.</span></span> <span data-ttu-id="718c6-126">Podría aplicar las recomendaciones a la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] ejecutando el script en el Editor de consultas; pero no lo haga.</span><span class="sxs-lookup"><span data-stu-id="718c6-126">You could apply the recommendations to the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database by executing the script in the Query Editor, but do not do this.</span></span> <span data-ttu-id="718c6-127">Cierre el script en el Editor de consultas sin ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="718c6-127">Close the script in Query Editor without running it.</span></span>  
  
     <span data-ttu-id="718c6-128">También podría aplicar las recomendaciones haciendo clic en **Aplicar recomendaciones** en el menú **Acciones** del Asistente para la optimización de [!INCLUDE[ssDE](../../includes/ssde-md.md)] ; pero no lo haga en esta práctica.</span><span class="sxs-lookup"><span data-stu-id="718c6-128">As an alternative, you could also apply the recommendations by clicking **Apply Recommendations** on the **Actions** menu of [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor, but do not apply these recommendations now in this practice.</span></span>  
  
6.  <span data-ttu-id="718c6-129">Si hay más de una recomendación en la pestaña **Recomendaciones** , borre algunas de las filas que enumeran objetos de base de datos en la cuadrícula **Recomendaciones de índices** .</span><span class="sxs-lookup"><span data-stu-id="718c6-129">If more than one recommendation exists on the **Recommendations** tab, clear some of the rows that list database objects in the **Index Recommendations** grid.</span></span>  
  
7.  <span data-ttu-id="718c6-130">En el menú **Acciones** , haga clic en **Evaluar recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="718c6-130">On the **Actions** menu, click **Evaluate Recommendations**.</span></span> [!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="718c6-131">crea una nueva sesión de optimización en la que puede evaluar un subconjunto de las recomendaciones originales de MySession.</span><span class="sxs-lookup"><span data-stu-id="718c6-131">Tuning Advisor creates a new tuning session where you can evaluate a subset of the original recommendations from MySession.</span></span>  
  
8.  <span data-ttu-id="718c6-132">Escriba `EvaluateMySession` para el nuevo **nombre de sesión**y haga clic en el botón **Iniciar análisis** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="718c6-132">Type `EvaluateMySession` for your new **Session name**, and click the **Start Analysis** button on the toolbar.</span></span> <span data-ttu-id="718c6-133">Puede repetir los pasos 2 y 3 con esta nueva sesión de optimización para ver las recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="718c6-133">You can repeat Steps 2 and 3 for this new tuning session to view its recommendations.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="718c6-134">Resumen</span><span class="sxs-lookup"><span data-stu-id="718c6-134">Summary</span></span>  
 <span data-ttu-id="718c6-135">Ha visto el contenido de la pestaña **Recomendaciones** para la sesión de optimización MySession y ha evaluado un subconjunto de recomendaciones en la nueva sesión de optimización EvaluateMySession.</span><span class="sxs-lookup"><span data-stu-id="718c6-135">You have viewed the contents of the **Recommendations** tab for the MySession tuning session and evaluated a subset of its recommendations in the new EvaluateMySession tuning session.</span></span>  
  
 <span data-ttu-id="718c6-136">Evaluar un subconjunto de recomendaciones de optimización puede ser necesario si tiene que cambiar las opciones de optimización después de ejecutar una sesión.</span><span class="sxs-lookup"><span data-stu-id="718c6-136">Evaluating a subset of tuning recommendations may be necessary if you find you must change tuning options after you run a session.</span></span> <span data-ttu-id="718c6-137">Por ejemplo, si solicita al Asistente para la optimización de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que tenga en cuenta las vistas indizadas cuando especifique opciones de optimización para una sesión, pero, después de que la recomendación se genere, decide usar las vistas indizadas de nuevo,</span><span class="sxs-lookup"><span data-stu-id="718c6-137">For example, if you ask [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor to consider indexed views when you specify tuning options for a session, but after the recommendation is generated you decide against using indexed views.</span></span> <span data-ttu-id="718c6-138">Después, puede usar la opción **evaluar recomendaciones** del menú **acciones** para que [!INCLUDE[ssDE](../../includes/ssde-md.md)] el Asistente para la optimización de vuelva a evaluar la sesión sin tener en cuenta las vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="718c6-138">You can then use the **Evaluate Recommendations** option on the **Actions** menu to have [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor re-evaluate the session without considering indexed views.</span></span> <span data-ttu-id="718c6-139">Cuando utilice la opción **Evaluar recomendaciones** , las recomendaciones generadas previamente se aplicarán hipotéticamente al diseño físico actual para lograr el diseño físico de la segunda sesión de optimización.</span><span class="sxs-lookup"><span data-stu-id="718c6-139">When you use the **Evaluate Recommendations** option the previously generated recommendations are hypothetically applied to the current physical design to arrive at the physical design for the second tuning session.</span></span>  
  
 <span data-ttu-id="718c6-140">La pestaña **Informes** , que se describe en la siguiente tarea de la lección, muestra más información sobre los resultados de optimización.</span><span class="sxs-lookup"><span data-stu-id="718c6-140">More tuning result information can be viewed in the **Reports** tab, which is described in the next task of this lesson.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="718c6-141">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="718c6-141">Next Task in Lesson</span></span>  
 [<span data-ttu-id="718c6-142">Ver informes de optimización</span><span class="sxs-lookup"><span data-stu-id="718c6-142">Viewing Tuning Reports</span></span>](lesson-1-3-viewing-tuning-reports.md)  
  
  