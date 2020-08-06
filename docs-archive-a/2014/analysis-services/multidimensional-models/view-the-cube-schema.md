---
title: Ver el esquema de cubo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 82fc715c-e08e-447d-8fc8-9c9005f145f0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e7d324db1e0c41588694031d3c121fdb47233f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749502"
---
# <a name="view-the-cube-schema"></a><span data-ttu-id="6a935-102">Ver el esquema del cubo</span><span class="sxs-lookup"><span data-stu-id="6a935-102">View the Cube Schema</span></span>
  <span data-ttu-id="6a935-103">El panel **Vista del origen de datos** de la pestaña **Estructura de cubo** del **Diseñador de cubos** muestra el esquema del cubo.</span><span class="sxs-lookup"><span data-stu-id="6a935-103">The **Data Source View** pane of the **Cube Structure** tab in **Cube Designer** displays the cube schema.</span></span> <span data-ttu-id="6a935-104">El esquema es el conjunto de tablas de las que se derivan las medidas y las dimensiones de un cubo.</span><span class="sxs-lookup"><span data-stu-id="6a935-104">The schema is the set of tables from which the measures and dimensions for a cube are derived.</span></span> <span data-ttu-id="6a935-105">Cada esquema de cubo se compone de una o varias tablas de hechos y una o varias tablas de dimensiones en las que se basan las medidas y las dimensiones del cubo.</span><span class="sxs-lookup"><span data-stu-id="6a935-105">Every cube schema consists of one or more fact tables and one or more dimension tables on which the measures and dimensions in the cube are based.</span></span>  
  
 <span data-ttu-id="6a935-106">El panel **Vista del origen de datos** de la pestaña **Estructura de cubo** muestra un diagrama de la vista del origen de datos en la que se basa el cubo.</span><span class="sxs-lookup"><span data-stu-id="6a935-106">The **Data Source View** pane of the **Cube Structure** tab displays a diagram of the data source view on which the cube is based.</span></span> <span data-ttu-id="6a935-107">Este diagrama es un subconjunto del diagrama principal de la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6a935-107">This diagram is a subset of the main diagram of the data source view.</span></span> <span data-ttu-id="6a935-108">Puede ocultar y mostrar tablas en el panel **Vista del origen de datos** y ver los diagramas existentes.</span><span class="sxs-lookup"><span data-stu-id="6a935-108">You can hide and show tables in the **Data Source View** pane and view any existing diagrams.</span></span> <span data-ttu-id="6a935-109">Sin embargo, no puede realizar cambios (como agregar nuevas relaciones o consultas con nombre) al esquema subyacente.</span><span class="sxs-lookup"><span data-stu-id="6a935-109">However, you cannot make changes (such as adding new relationships or named queries) to the underlying schema.</span></span> <span data-ttu-id="6a935-110">Para realizar cambios en el esquema, use el Diseñador de vistas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6a935-110">To make changes to the schema, use Data Source View Designer.</span></span>  
  
 <span data-ttu-id="6a935-111">Al crear un cubo, el diagrama que se muestra en el panel **Vista del origen de datos** de la pestaña **Estructura de cubo** es inicialmente el mismo que el diagrama **Mostrar todas las tablas** de la vista del origen de datos para el proyecto o la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6a935-111">When you create a cube, the diagram displayed in the **Data Source View** pane of the **Cube Structure** tab is initially the same as the **Show All Tables** diagram in the data source view for the project or database.</span></span> <span data-ttu-id="6a935-112">Puede reemplazar este diagrama por cualquier diagrama existente en la vista del origen de datos y realizar ajustes en el panel **Vista del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="6a935-112">You can replace this diagram with any existing diagram in the data source view and make adjustments in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="6a935-113">Cuando se trabaja con el diagrama en el **Diseñador de cubos**, los comandos que actúan sobre la pestaña o sobre cualquier objeto seleccionado en la pestaña están disponibles en el menú **Vista del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="6a935-113">While you work with the diagram in **Cube Designer**, commands that act on the tab or on any selected object in the tab are available on the **Data Source View** menu.</span></span> <span data-ttu-id="6a935-114">También puede hacer clic con el botón secundario en el fondo del diagrama o en cualquier objeto del diagrama para usar comandos que actúan sobre el diagrama o el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6a935-114">You can also right-click the background of the diagram or any object in the diagram to use commands that act on the diagram or selected object.</span></span> <span data-ttu-id="6a935-115">Puede:</span><span class="sxs-lookup"><span data-stu-id="6a935-115">You can:</span></span>  
  
-   <span data-ttu-id="6a935-116">Cambiar entre el formato de diagrama y el de árbol.</span><span class="sxs-lookup"><span data-stu-id="6a935-116">Switch between diagram and tree formats.</span></span>  
  
-   <span data-ttu-id="6a935-117">Organizar, buscar, mostrar y ocultar tablas.</span><span class="sxs-lookup"><span data-stu-id="6a935-117">Arrange, find, show, and hide tables.</span></span>  
  
-   <span data-ttu-id="6a935-118">Mostrar nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="6a935-118">Show friendly names.</span></span>  
  
-   <span data-ttu-id="6a935-119">Cambiar de diseño.</span><span class="sxs-lookup"><span data-stu-id="6a935-119">Switch layouts.</span></span>  
  
-   <span data-ttu-id="6a935-120">Cambiar la ampliación (zoom).</span><span class="sxs-lookup"><span data-stu-id="6a935-120">Change the magnification.</span></span>  
  
-   <span data-ttu-id="6a935-121">Ver las propiedades.</span><span class="sxs-lookup"><span data-stu-id="6a935-121">View properties.</span></span>  
  
 <span data-ttu-id="6a935-122">Además, puede realizar las acciones que se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a935-122">Additionally, you can perform the actions listed in the following table:</span></span>  
  
|<span data-ttu-id="6a935-123">A</span><span class="sxs-lookup"><span data-stu-id="6a935-123">To</span></span>|<span data-ttu-id="6a935-124">Haga esto</span><span class="sxs-lookup"><span data-stu-id="6a935-124">Do this</span></span>|  
|--------|-------------|  
|<span data-ttu-id="6a935-125">Usar un diagrama desde la vista del origen de datos del cubo</span><span class="sxs-lookup"><span data-stu-id="6a935-125">Use a diagram from the data source view of the cube</span></span>|<span data-ttu-id="6a935-126">En el menú **Vista del origen de datos** , seleccione **Copiar diagrama desde**y, a continuación, haga clic en el diagrama de la vista del origen de datos que desea usar.</span><span class="sxs-lookup"><span data-stu-id="6a935-126">On the **Data Source View** menu, point to **Copy Diagram from**, and then click the data source view diagram you want to use.</span></span><br /><br /> <span data-ttu-id="6a935-127">o bien</span><span class="sxs-lookup"><span data-stu-id="6a935-127">- or -</span></span><br /><br /> <span data-ttu-id="6a935-128">Haga clic con el botón derecho en el fondo del panel **Vista del origen de datos** , seleccione **Copiar diagrama desde**y, después, haga clic en el diagrama de la vista del origen de datos que prefiera.</span><span class="sxs-lookup"><span data-stu-id="6a935-128">Right-click the background of the **Data Source View** pane, point to **Copy Diagram from**, and then click the diagram in the data source view that you want.</span></span> <span data-ttu-id="6a935-129">Este método crea una copia independiente del diagrama, de modo que los cambios que realice en la pestaña **Generador de cubos** no aparecen en el diagrama original.</span><span class="sxs-lookup"><span data-stu-id="6a935-129">This method creates an independent copy of the diagram, so any changes you make on the **Cube Builder** tab do not appear in the original diagram.</span></span>|  
|<span data-ttu-id="6a935-130">Mostrar solo las tablas usadas en el cubo</span><span class="sxs-lookup"><span data-stu-id="6a935-130">Show only the tables that are used in the cube</span></span>|<span data-ttu-id="6a935-131">En el menú **Vista del origen de datos** , haga clic en **Mostrar solo tablas usadas**.</span><span class="sxs-lookup"><span data-stu-id="6a935-131">On the **Data Source View** menu, click **Show Only Used Tables**.</span></span><br /><br /> <span data-ttu-id="6a935-132">o bien</span><span class="sxs-lookup"><span data-stu-id="6a935-132">- or -</span></span><br /><br /> <span data-ttu-id="6a935-133">Haga clic con el botón derecho en el fondo del panel **Vista del origen de datos** y, después, haga clic en **Mostrar solo tablas usadas**.</span><span class="sxs-lookup"><span data-stu-id="6a935-133">Right-click the background of the **Data Source View** pane, and then click **Show Only Used Tables**.</span></span>|  
|<span data-ttu-id="6a935-134">Editar el esquema de la vista del origen de datos</span><span class="sxs-lookup"><span data-stu-id="6a935-134">Edit the data source view schema</span></span>|<span data-ttu-id="6a935-135">En el menú **Vista del origen de datos** , haga clic en **Editar vista del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="6a935-135">On the **Data Source View** menu, click **Edit Data Source View**.</span></span><br /><br /> <span data-ttu-id="6a935-136">o bien</span><span class="sxs-lookup"><span data-stu-id="6a935-136">- or -</span></span><br /><br /> <span data-ttu-id="6a935-137">Haga clic con el botón derecho en el fondo del panel **Vista del origen de datos** y, después, haga clic en **Editar vista del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="6a935-137">Right-click the background of the **Data Source View** pane, and then click **Edit Data Source View**.</span></span>|  
  
  