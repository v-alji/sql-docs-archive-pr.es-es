---
title: Agregar tablas a diagramas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
ms.assetid: 5440fdf7-ac04-4325-9f32-181f4cd402e5
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe5c1274ac390f4834bd8ac1088258061fc0406d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673430"
---
# <a name="add-tables-to-diagrams-visual-database-tools"></a><span data-ttu-id="09522-102">Agregar tablas a diagramas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="09522-102">Add Tables to Diagrams (Visual Database Tools)</span></span>
  <span data-ttu-id="09522-103">Puede agregar una tabla al diagrama de base de datos para editar su estructura o para relacionarla con otras tablas del diagrama.</span><span class="sxs-lookup"><span data-stu-id="09522-103">You can add a table to your database diagram to edit its structure or relate it to other tables in your diagram.</span></span> <span data-ttu-id="09522-104">Puede agregar tablas de base de datos existentes a un diagrama o insertar una tabla nueva aún no definida en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="09522-104">You can either add existing database tables to a diagram or insert a new table that has not yet been defined in the database.</span></span>  
  
### <a name="to-insert-a-new-table-into-a-diagram"></a><span data-ttu-id="09522-105">Para insertar una tabla nueva en un diagrama</span><span class="sxs-lookup"><span data-stu-id="09522-105">To insert a new table into a diagram</span></span>  
  
1.  <span data-ttu-id="09522-106">Asegúrese de que está conectado a la base de datos en la que desea crear la tabla.</span><span class="sxs-lookup"><span data-stu-id="09522-106">Make sure you are connected to the database in which you want to create the table.</span></span>  
  
     <span data-ttu-id="09522-107">Para crear una tabla en el diagrama actual, haga clic en el botón **Nueva tabla** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="09522-107">To create a table in your current diagram, click the **New Table** button on the toolbar.</span></span>  
  
     <span data-ttu-id="09522-108">O bien</span><span class="sxs-lookup"><span data-stu-id="09522-108">-or-</span></span>  
  
     <span data-ttu-id="09522-109">Haga clic con el botón derecho en el diagrama y seleccione **Nueva tabla**.</span><span class="sxs-lookup"><span data-stu-id="09522-109">Right-click in the diagram and select **New Table**.</span></span>  
  
2.  <span data-ttu-id="09522-110">Modifique o acepte el nombre de tabla asignado por el sistema en el cuadro de diálogo **Elegir nombre** y, luego, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="09522-110">Modify or accept the system-assigned table name, in the **Choose Name** dialog box, and then choose **OK**.</span></span>  
  
     <span data-ttu-id="09522-111">Aparecerá una tabla nueva en el diagrama, en la vista Estándar.</span><span class="sxs-lookup"><span data-stu-id="09522-111">A new table appears in the diagram in Standard view.</span></span>  
  
3.  <span data-ttu-id="09522-112">Escriba en la primera celda de la tabla nueva un nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="09522-112">In the first cell of the new table, type a column name.</span></span> <span data-ttu-id="09522-113">A continuación, presione la tecla TAB para pasar a la celda siguiente.</span><span class="sxs-lookup"><span data-stu-id="09522-113">Then press the TAB key to move to the next cell.</span></span>  
  
4.  <span data-ttu-id="09522-114">En **Tipo de datos**, seleccione el tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="09522-114">Under **Data Type**, select a data type for the column.</span></span> <span data-ttu-id="09522-115">Todas las columnas deben tener nombre y tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="09522-115">Each column must have a name and data type.</span></span>  
  
     <span data-ttu-id="09522-116">Puede definir otras propiedades de la columna en el Diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="09522-116">You can set the column's other properties in Table Designer.</span></span>  
  
5.  <span data-ttu-id="09522-117">Repita los pasos 3 y 4 para cada columna que desee agregar a la tabla.</span><span class="sxs-lookup"><span data-stu-id="09522-117">Repeat steps 3 and 4 for each column you want to add to the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09522-118">Cuando guarde el diagrama de base de datos, se agregará la nueva tabla a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="09522-118">When you save your database diagram, the new table will be added to your database.</span></span>  
  
### <a name="to-add-an-existing-table-to-a-diagram"></a><span data-ttu-id="09522-119">Para agregar una tabla existente a un diagrama</span><span class="sxs-lookup"><span data-stu-id="09522-119">To add an existing table to a diagram</span></span>  
  
1.  <span data-ttu-id="09522-120">Asegúrese de que está conectado a la base de datos cuyas tablas desea editar.</span><span class="sxs-lookup"><span data-stu-id="09522-120">Make sure you are connected to the database whose tables you want to edit.</span></span>  
  
2.  <span data-ttu-id="09522-121">Seleccione una tabla de la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="09522-121">Select a table in the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="09522-122">Arrastre la tabla al diagrama de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="09522-122">Drag the table into your database diagram.</span></span>  
  
4.  <span data-ttu-id="09522-123">Suelte el botón del mouse (ratón).</span><span class="sxs-lookup"><span data-stu-id="09522-123">Release the mouse button.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09522-124">Si hay relaciones entre la tabla seleccionada y otras tablas del diagrama, se dibujarán automáticamente las líneas de las relaciones.</span><span class="sxs-lookup"><span data-stu-id="09522-124">If relationships exist between the selected table and other tables in your diagram, relationship lines are automatically drawn.</span></span>  
  
### <a name="to-add-related-tables-to-a-diagram"></a><span data-ttu-id="09522-125">Para agregar tablas relacionadas a un diagrama</span><span class="sxs-lookup"><span data-stu-id="09522-125">To add related tables to a diagram</span></span>  
  
1.  <span data-ttu-id="09522-126">Seleccione una o más tablas con restricciones FOREIGN KEY en el diagrama de base de datos.</span><span class="sxs-lookup"><span data-stu-id="09522-126">Select one or more tables with foreign key constraints in the database diagram.</span></span>  
  
2.  <span data-ttu-id="09522-127">Haga clic con el botón derecho en cualquiera de las tablas seleccionadas y elija **Agregar tablas relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="09522-127">Right-click any of the selected tables and choose **Add Related Tables**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09522-128">Se agregan al diagrama tanto las tablas a las que hace referencia una restricción FOREIGN KEY de las tablas seleccionadas como las que hacen referencia a las tablas seleccionadas mediante una restricción FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="09522-128">Both those tables referenced by a foreign key constraint from the selected table(s) and those referencing the selected table(s) with a foreign key constraint are added to the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09522-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09522-129">See Also</span></span>  
 <span data-ttu-id="09522-130">[Trabajar con diagramas de base de datos &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="09522-130">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="09522-131">Trabajar con tablas en diagramas de base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="09522-131">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
