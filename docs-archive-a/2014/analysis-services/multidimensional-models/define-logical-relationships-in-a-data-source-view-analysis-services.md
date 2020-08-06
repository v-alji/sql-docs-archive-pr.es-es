---
title: Definir relaciones lógicas en una vista del origen de datos (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding relationships
- relationships [Analysis Services], data source views
- data source views [Analysis Services], relationships
ms.assetid: a20d6dae-e769-4131-8a59-7ef56f174220
author: minewiskan
ms.author: owend
ms.openlocfilehash: c46c2b360a4528aeb0eb88348d0d1242b22d8ef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673379"
---
# <a name="define-logical-relationships-in-a-data-source-view-analysis-services"></a><span data-ttu-id="0b21d-102">Definir relaciones lógicas en una vista del origen de datos (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="0b21d-102">Define Logical Relationships in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="0b21d-103">El Asistente para vistas del origen de datos y el Diseñador de vistas del origen de datos definen automáticamente las relaciones entre las tablas agregadas a una vista del origen de datos (DSV), en función de las relaciones de la base de datos subyacente o de los criterios de coincidencia de nombres que se especifiquen.</span><span class="sxs-lookup"><span data-stu-id="0b21d-103">The Data Source View Wizard and Data Source View Designer automatically define relationships between tables added to a data source view (DSV) based on underlying database relationships or name matching criteria you specify.</span></span>  
  
 <span data-ttu-id="0b21d-104">En caso de que esté trabajando con datos de varios orígenes de datos, puede que necesite definir manualmente relaciones lógicas en la DSV para complementar las relaciones definidas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0b21d-104">In cases where you are working with data from multiple data sources, you may need to manually define logical relationships in the DSV to supplement those relationships that are defined automatically.</span></span> <span data-ttu-id="0b21d-105">Las relaciones son necesarias en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para identificar las tablas de hechos y dimensiones, para construir consultas para la recuperación de datos y metadatos de orígenes de datos subyacentes, y para usar las características avanzadas de Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="0b21d-105">Relationships are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to identify fact and dimension tables, to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="0b21d-106">En el Diseñador de vistas del origen de datos puede definir los siguientes tipos de relaciones:</span><span class="sxs-lookup"><span data-stu-id="0b21d-106">You can define the following types of relationships in Data Source View Designer:</span></span>  
  
-   <span data-ttu-id="0b21d-107">Una relación de una tabla con otra en el mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0b21d-107">A relationship from one table to another table in the same data source.</span></span>  
  
-   <span data-ttu-id="0b21d-108">Una relación de una tabla consigo misma, como en una relación de elementos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="0b21d-108">A relationship from one table to itself, as in a parent-child relationship.</span></span>  
  
-   <span data-ttu-id="0b21d-109">Una relación de una tabla de un origen de datos con otra tabla de un origen de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="0b21d-109">A relationship from one table in a data source to another table in a different data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b21d-110">Las relaciones definidas en una DSV son lógicas y es posible que no reflejen las relaciones reales definidas en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="0b21d-110">The relationships defined in a DSV are logical and may not reflect the actual relationships defined in the underlying data source.</span></span> <span data-ttu-id="0b21d-111">Puede crear relaciones en el Diseñador de vistas del origen de datos que no existan en el origen de datos subyacente, y quitar las relaciones creadas por el Diseñador de vistas del origen de datos a partir de relaciones de clave externa existentes en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="0b21d-111">You can create relationships in Data Source View Designer that do not exist in the underlying data source, and remove relationships created by Data Source View Designer from existing foreign key relationships in the underlying data source.</span></span>  
  
 <span data-ttu-id="0b21d-112">Las relaciones incluyen una dirección.</span><span class="sxs-lookup"><span data-stu-id="0b21d-112">Relationships are directed.</span></span> <span data-ttu-id="0b21d-113">A cada valor de la columna de origen le corresponde un valor de la columna de destino.</span><span class="sxs-lookup"><span data-stu-id="0b21d-113">For every value in the source column, there is a corresponding value in the destination column.</span></span> <span data-ttu-id="0b21d-114">En un diagrama de la vista del origen de datos, como el diagrama que aparece en el panel **Diagrama** , una flecha sobre la línea entre dos tablas indica la dirección de la relación.</span><span class="sxs-lookup"><span data-stu-id="0b21d-114">In a data source view diagram, such as the diagrams displayed in the **Diagram** pane, an arrow on the line between two tables indicates the direction of the relationship.</span></span>  
  
 <span data-ttu-id="0b21d-115">Este tema incluye las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="0b21d-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="0b21d-116">Para agregar una relación entre tablas, consultas con nombre o vistas</span><span class="sxs-lookup"><span data-stu-id="0b21d-116">To add a relationship between tables, named queries, or views</span></span>](#bkmk_addRel)  
  
 [<span data-ttu-id="0b21d-117">Para ver o modificar una relación en el panel Diagrama</span><span class="sxs-lookup"><span data-stu-id="0b21d-117">To view or modify a relationship in the Diagram pane</span></span>](#bkmk_diagrampane)  
  
 [<span data-ttu-id="0b21d-118">Para ver o modificar una relación en el panel Tablas</span><span class="sxs-lookup"><span data-stu-id="0b21d-118">To view or modify a relationship in the Tables pane</span></span>](#bkmk_tablespane)  
  
##  <a name="to-add-a-relationship-between-tables-named-queries-or-views"></a><a name="bkmk_addRel"></a><span data-ttu-id="0b21d-119">Para agregar una relación entre tablas, consultas con nombre o vistas</span><span class="sxs-lookup"><span data-stu-id="0b21d-119">To add a relationship between tables, named queries, or views</span></span>  
  
1.  <span data-ttu-id="0b21d-120">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto o conéctese a la base de datos que contiene la vista del origen de datos en que desea agregar una relación lógica.</span><span class="sxs-lookup"><span data-stu-id="0b21d-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to add a logical relationship.</span></span>  
  
2.  <span data-ttu-id="0b21d-121">En el Explorador de soluciones, expanda la carpeta **Vistas del origen de datos** y, después, haga doble clic en la vista del origen de datos para abrirla en el **Diseñador de vistas del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="0b21d-121">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view to open it in **Data Source View Designer**.</span></span>  
  
3.  <span data-ttu-id="0b21d-122">Haga clic con el botón derecho en la tabla, vista o consulta con nombre a la que quiere agregar la relación en el panel **Tablas** y, después, haga clic en **Nueva relación**.</span><span class="sxs-lookup"><span data-stu-id="0b21d-122">Right-click the table, named query or view to which you want to add a relationship in either the **Tables** pane and then click **New Relationship**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b21d-123">Para buscar una tabla, vista o consulta con nombre, puede usar la opción **Buscar tabla** haciendo clic en el menú **Vista del origen de datos** o haciendo clic con el botón derecho en un área abierta de los paneles **Tablas** o **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="0b21d-123">To locate a table, view or named query, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
4.  <span data-ttu-id="0b21d-124">En el cuadro de diálogo **Especificar relación** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b21d-124">In the **Specify Relationship** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0b21d-125">Seleccione la tabla, vista o consulta con nombre adecuada en la lista **Tabla de origen (de clave externa)** .</span><span class="sxs-lookup"><span data-stu-id="0b21d-125">Select the appropriate table, named query, or view in the **Source (foreign key) table** list.</span></span>  
  
    2.  <span data-ttu-id="0b21d-126">Seleccione la tabla, vista o consulta con nombre adecuada en la lista **Tabla de destino (de clave principal)** .</span><span class="sxs-lookup"><span data-stu-id="0b21d-126">Select the appropriate table, named query, or view in the **Destination (primary key) table** lists.</span></span>  
  
    3.  <span data-ttu-id="0b21d-127">Seleccione columnas en las listas **Columnas de origen** y **Columnas de destino** para crear una relación entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="0b21d-127">Select columns from the **Source Columns** and **Destination Columns** lists to create a relationship between the two tables.</span></span>  
  
         <span data-ttu-id="0b21d-128">Si, al hacer un muestreo de los datos de la tabla, vista o consulta con nombre subyacente, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detecta que ha definido la relación en la dirección equivocada (de la clave principal a la clave externa en lugar de la clave externa a la principal), se le solicitará que invierta el orden.</span><span class="sxs-lookup"><span data-stu-id="0b21d-128">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects, by sampling the data in the underlying table, view, or named query, that you have defined the relationship in the wrong direction (from the primary key to the foreign key rather than from the foreign key to the primary key), you will be prompted to reverse the order.</span></span> <span data-ttu-id="0b21d-129">Para invertir el orden rápidamente, haga clic en **Invertir**.</span><span class="sxs-lookup"><span data-stu-id="0b21d-129">To quickly reverse the order, click **Reverse**.</span></span>  
  
         <span data-ttu-id="0b21d-130">Si [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detecta que ya existe una relación para las columnas que ha seleccionado, se le indicará.</span><span class="sxs-lookup"><span data-stu-id="0b21d-130">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects that a relationship already exists for the columns you have selected, you will be prompted.</span></span> <span data-ttu-id="0b21d-131">No se pueden definir relaciones duplicadas.</span><span class="sxs-lookup"><span data-stu-id="0b21d-131">You cannot define duplicate relationships.</span></span>  
  
    4.  <span data-ttu-id="0b21d-132">Si lo desea, en el cuadro **Descripción** , escriba una descripción de la relación.</span><span class="sxs-lookup"><span data-stu-id="0b21d-132">Optionally, in the **Description** box, type a description for the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-diagram-pane"></a><a name="bkmk_diagrampane"></a><span data-ttu-id="0b21d-133">Para ver o modificar una relación en el panel Diagrama</span><span class="sxs-lookup"><span data-stu-id="0b21d-133">To view or modify a relationship in the Diagram pane</span></span>  
  
-   <span data-ttu-id="0b21d-134">En el panel **Diagrama** del **Diseñador de vistas del origen de datos**, haga clic con el botón derecho en la relación que quiere ver y haga clic en **Editar relación** (o simplemente haga doble clic en la flecha de la relación).</span><span class="sxs-lookup"><span data-stu-id="0b21d-134">In the **Diagram** pane in **Data Source View Designer**, right-click the relationship that you want to view and click **Edit Relationship** (or simply double-click the relationship arrow).</span></span>  <span data-ttu-id="0b21d-135">Use el cuadro de diálogo **Editar relación** para modificar la relación.</span><span class="sxs-lookup"><span data-stu-id="0b21d-135">Use the **Edit Relationship** dialog box to modify the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-tables-pane"></a><a name="bkmk_tablespane"></a><span data-ttu-id="0b21d-136">Para ver o modificar una relación en el panel tablas</span><span class="sxs-lookup"><span data-stu-id="0b21d-136">To view or modify a relationship in the Tables pane</span></span>  
  
1.  <span data-ttu-id="0b21d-137">En el panel **Tablas** del **Diseñador de vistas del origen de datos**, busque y expanda la tabla, vista o consulta con nombre que contiene la relación que desea ver o modificar.</span><span class="sxs-lookup"><span data-stu-id="0b21d-137">In the **Tables** pane in **Data Source View Designer**, locate and then expand the table, view or named query containing the relationship that you wish to view or modify.</span></span>  
  
2.  <span data-ttu-id="0b21d-138">Expanda la carpeta **Relaciones** .</span><span class="sxs-lookup"><span data-stu-id="0b21d-138">Expand the **Relationships** folder.</span></span>  <span data-ttu-id="0b21d-139">Las relaciones entre la tabla, vista o consulta con nombre seleccionada y las demás tablas, vistas y consultas con nombre se muestran con la columna de relaciones enumerada.</span><span class="sxs-lookup"><span data-stu-id="0b21d-139">The relationships between the selected table, view or named query and other tables, views and named queries appear with the relationship column listed.</span></span>  
  
3.  <span data-ttu-id="0b21d-140">Haga clic con el botón derecho en la relación que quiere modificar y, después, haga clic en **Editar relación**.</span><span class="sxs-lookup"><span data-stu-id="0b21d-140">Right-click the relationship you want to modify, and then click **Edit Relationship**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b21d-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b21d-141">See Also</span></span>  
 [<span data-ttu-id="0b21d-142">Vistas del origen de datos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="0b21d-142">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
