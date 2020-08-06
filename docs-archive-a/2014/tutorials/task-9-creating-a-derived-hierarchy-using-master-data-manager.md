---
title: 'Tarea 9: crear una jerarquía derivada mediante Master Data Manager | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3bd2ec05-933f-4947-b1fe-c9226961eb7d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 5c85750e4556722c6e6a5edbccb4a3c82c119a74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751577"
---
# <a name="task-9-creating-a-derived-hierarchy-using-master-data-manager"></a><span data-ttu-id="77261-102">Tarea 9: Creación de una jerarquía derivada mediante Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="77261-102">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>
  <span data-ttu-id="77261-103">En esta tarea, creará una jerarquía derivada mediante Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="77261-103">In this task, you create a derived hierarchy by using Master Data Manager.</span></span> <span data-ttu-id="77261-104">Esta jerarquía derivada se deriva de las relaciones de atributo basado en dominio entre las entidades **proveedor** y **Estado** .</span><span class="sxs-lookup"><span data-stu-id="77261-104">This derived hierarchy is derived from the domain-based attribute relationships between the **Supplier** and **State** entities.</span></span>  
  
1.  <span data-ttu-id="77261-105">Cambie a la Página principal de **Master Data Manager** haciendo clic en **SQL Server 2012 Master Data Services** en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="77261-105">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
2.  <span data-ttu-id="77261-106">Haga clic en **Administración del sistema** en la sección **Tareas administrativas** .</span><span class="sxs-lookup"><span data-stu-id="77261-106">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="77261-107">Mantenga el mouse sobre **administrar** en la barra de menús y haga clic en **jerarquías derivadas**.</span><span class="sxs-lookup"><span data-stu-id="77261-107">Hover the mouse over **Manage** on the menu bar, and click **Derived Hierarchies**.</span></span>  
  
     <span data-ttu-id="77261-108">![Menú Administrar - Jerarquías derivadas seleccionadas](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Menú Administrar - Jerarquías derivadas seleccionadas")</span><span class="sxs-lookup"><span data-stu-id="77261-108">![Manage Menu - Derived Hierarchies Selected](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Manage Menu - Derived Hierarchies Selected")</span></span>  
  
4.  <span data-ttu-id="77261-109">Haga clic en el botón **Agregar jerarquía derivada (+)** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="77261-109">Click **Add Derived Hierarchy (+)** button on the toolbar.</span></span>  
  
     <span data-ttu-id="77261-110">![Botón Agregar jerarquía derivada](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Botón Agregar jerarquía derivada")</span><span class="sxs-lookup"><span data-stu-id="77261-110">![Add Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Add Derived Hierarchy Button")</span></span>  
  
5.  <span data-ttu-id="77261-111">Escriba **SuppliersInState** para el **nombre de la jerarquía derivada**.</span><span class="sxs-lookup"><span data-stu-id="77261-111">Type **SuppliersInState** for the **Derived hierarchy name**.</span></span>  
  
6.  <span data-ttu-id="77261-112">Haga clic en el botón **Guardar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="77261-112">Click **Save** button on the toolbar.</span></span>  
  
     <span data-ttu-id="77261-113">![Botón Guardar jerarquía derivada](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Botón Guardar jerarquía derivada")</span><span class="sxs-lookup"><span data-stu-id="77261-113">![Save Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Save Derived Hierarchy Button")</span></span>  
  
7.  <span data-ttu-id="77261-114">Arrastre **proveedor** desde **niveles disponibles: SuppliersInState** a **niveles actuales: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="77261-114">Drag **Supplier** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span>  
  
     <span data-ttu-id="77261-115">![Entidades y jerarquías disponibles en el nivel actual](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Entidades y jerarquías disponibles en el nivel actual")</span><span class="sxs-lookup"><span data-stu-id="77261-115">![Avialble Entities and Hierarchies to Current Level](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Avialble Entities and Hierarchies to Current Level")</span></span>  
  
8.  <span data-ttu-id="77261-116">Arrastre **Estado** desde **niveles disponibles: SuppliersInState** a **niveles actuales: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="77261-116">Drag **State** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span> <span data-ttu-id="77261-117">La pantalla debe tener los **niveles actuales** , tal como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="77261-117">The screen should have **Current Levels** as shown in the following picture.</span></span>  
  
     <span data-ttu-id="77261-118">![Niveles actuales y vista previa de la jerarquía derivada](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Niveles actuales y vista previa de la jerarquía derivada")</span><span class="sxs-lookup"><span data-stu-id="77261-118">![Current Levels and Preview of Derived Hierarchy](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Current Levels and Preview of Derived Hierarchy")</span></span>  
  
9. <span data-ttu-id="77261-119">En la ventana de **vista previa** , expanda **NY {Nueva York}** y debería ver un proveedor en ese estado, tal como se muestra en la imagen anterior.</span><span class="sxs-lookup"><span data-stu-id="77261-119">In the **Preview** window, expand **NY { New York}** and you should see one supplier in that state as shown in the preceding image.</span></span>  
  
10. <span data-ttu-id="77261-120">Cambie a la Página principal de **Master Data Manager** haciendo clic en **SQL Server 2012 Master Data Services** en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="77261-120">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
11. <span data-ttu-id="77261-121">Haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="77261-121">Click **Explorer**.</span></span>  
  
12. <span data-ttu-id="77261-122">Mantenga el mouse sobre las **jerarquías** y haga clic en **derived: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="77261-122">Hover the mouse over **Hierarchies** and click **Derived:SuppliersInState**.</span></span>  
  
     <span data-ttu-id="77261-123">![Jerarquías- Menú Derived:SuppliersInState](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Jerarquías- Menú Derived:SuppliersInState")</span><span class="sxs-lookup"><span data-stu-id="77261-123">![Hierarchies - Derived:SuppliersInState Menu](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Hierarchies - Derived:SuppliersInState Menu")</span></span>  
  
13. <span data-ttu-id="77261-124">Haga clic en cualquier nodo de **Estado** en la **vista de árbol** y debería ver los proveedores en ese estado en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="77261-124">Click on any **state** node in the **tree view** and you should see the suppliers in that state in the right pane.</span></span>  
  
     <span data-ttu-id="77261-125">![Jerarquía derivada en el Explorador](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Jerarquía derivada en el Explorador")</span><span class="sxs-lookup"><span data-stu-id="77261-125">![Derived Hierarchy in Explorer](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Derived Hierarchy in Explorer")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="77261-126">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="77261-126">Next Step</span></span>  
 [<span data-ttu-id="77261-127">Lección 5: Automatización de la limpieza y la búsqueda de coincidencias con SSIS</span><span class="sxs-lookup"><span data-stu-id="77261-127">Lesson 5: Automating the Cleansing and Matching using SSIS</span></span>](../../2014/tutorials/lesson-5-automating-the-cleansing-and-matching-using-ssis.md)  
  
  
