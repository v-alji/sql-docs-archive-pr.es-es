---
title: Diseñar diagramas de base de datos (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65536
- vdt.DatabaseDesigner
helpviewer_keywords:
- Database Diagram Designer
- Visual Database Tools [SQL Server], database diagrams
- database diagrams [SQL Server], designing
- diagrams [SQL Server], designing
ms.assetid: 6d2c14e1-3d73-4d10-ae5b-7f2b5d6c4ea8
author: stevestein
ms.author: sstein
ms.openlocfilehash: bb4cbc518b6878ed8fb6e9f7d5d2d00803ab4d62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744965"
---
# <a name="design-database-diagrams-visual-database-tools"></a><span data-ttu-id="391b7-102">Diseñar diagramas de base de datos (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="391b7-102">Design Database Diagrams (Visual Database Tools)</span></span>
  <span data-ttu-id="391b7-103">El Diseñador de bases de datos es una herramienta visual que permite diseñar y ver una base de datos a la que está conectado.</span><span class="sxs-lookup"><span data-stu-id="391b7-103">The Database Designer is a visual tool that allows you to design and visualize a database to which you are connected.</span></span> <span data-ttu-id="391b7-104">Cuando diseña una base de datos, puede utilizar el Diseñador de bases de datos para crear, editar o eliminar tablas, columnas, claves, índices, relaciones y restricciones.</span><span class="sxs-lookup"><span data-stu-id="391b7-104">When designing a database, you can use Database Designer to create, edit, or delete tables, columns, keys, indexes, relationships, and constraints.</span></span> <span data-ttu-id="391b7-105">Para ver una base de datos, puede crear uno o varios diagramas que muestren algunas o todas las tablas, columnas, claves y relaciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="391b7-105">To visualize a database, you can create one or more diagrams illustrating some or all of the tables, columns, keys, and relationships in it.</span></span>  
  
 <span data-ttu-id="391b7-106">![Diagrama de base de datos en el que se ilustran las relaciones de tabla](../../database-engine/media//dv3w7c1.gif "Diagrama de base de datos en el que se ilustran las relaciones de tabla")</span><span class="sxs-lookup"><span data-stu-id="391b7-106">![Database diagram illustrating table relationships](../../database-engine/media//dv3w7c1.gif "Database diagram illustrating table relationships")</span></span>  
  
 <span data-ttu-id="391b7-107">Para cualquier base de datos, puede crear tantos diagramas de base de datos como desee; cada tabla de base de datos puede aparecer en un número cualquiera de diagramas.</span><span class="sxs-lookup"><span data-stu-id="391b7-107">For any database, you can create as many database diagrams as you like; each database table can appear on any number of diagrams.</span></span> <span data-ttu-id="391b7-108">De este modo, puede crear diagramas distintos para ver partes diferentes de la base de datos o resaltar diversos aspectos del diseño.</span><span class="sxs-lookup"><span data-stu-id="391b7-108">Thus, you can create different diagrams to visualize different portions of the database, or to accentuate different aspects of the design.</span></span> <span data-ttu-id="391b7-109">Por ejemplo, puede crear un diagrama grande que muestre todas las tablas con sus columnas y también puede crear un diagrama más pequeño que muestre todas las tablas sin mostrar las columnas.</span><span class="sxs-lookup"><span data-stu-id="391b7-109">For example, you can create a large diagram showing all tables and columns, and you can create a smaller diagram showing all tables without showing the columns.</span></span>  
  
 <span data-ttu-id="391b7-110">Cada diagrama de base de datos que crea se almacena en la base de datos asociada.</span><span class="sxs-lookup"><span data-stu-id="391b7-110">Each database diagram you create is stored in the associated database.</span></span>  
  
## <a name="tables-and-columns-in-a-database-diagram"></a><span data-ttu-id="391b7-111">Tablas y columnas de un diagrama de base de datos</span><span class="sxs-lookup"><span data-stu-id="391b7-111">Tables and Columns in a Database Diagram</span></span>  
 <span data-ttu-id="391b7-112">En un diagrama de base de datos, cada tabla puede aparecer con tres características distintas: una barra de título, un selector de fila y un conjunto de columnas de propiedades.</span><span class="sxs-lookup"><span data-stu-id="391b7-112">Within a database diagram, each table can appear with three distinct features: a title bar, a row selector, and a set of property columns.</span></span>  
  
 <span data-ttu-id="391b7-113">**Barra de título** La barra de título muestra el nombre de la tabla</span><span class="sxs-lookup"><span data-stu-id="391b7-113">**Title Bar** The title bar shows the name of the table</span></span>  
  
 <span data-ttu-id="391b7-114">Si ha modificado una tabla y no la ha guardado todavía, aparecerá un asterisco (\*) al final del nombre de la tabla que indica que hay cambios no guardados.</span><span class="sxs-lookup"><span data-stu-id="391b7-114">If you have modified a table and have not yet saved it, an asterisk (\*) appears at the end of the table name to indicate unsaved changes.</span></span> <span data-ttu-id="391b7-115">Para información sobre cómo guardar tablas y diagramas modificados, consulte [Trabajar con diagramas de base de datos &#40;Visual Database Tools&#41;](visual-database-tools.md)</span><span class="sxs-lookup"><span data-stu-id="391b7-115">For information about saving modified tables and diagrams, see [Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md)</span></span>  
  
 <span data-ttu-id="391b7-116">**Selector de fila** Puede hacer clic en el selector de fila para seleccionar una columna de base de datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="391b7-116">**Row Selector** You can click the row selector to select a database column in the table.</span></span> <span data-ttu-id="391b7-117">El selector de fila muestra un símbolo de clave si la columna se encuentra en la clave principal de la tabla.</span><span class="sxs-lookup"><span data-stu-id="391b7-117">The row selector displays a key symbol if the column is in the table's primary key.</span></span> <span data-ttu-id="391b7-118">Para obtener información sobre las claves principales, consulte [restricciones de clave principal y externa](../../relational-databases/tables/primary-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="391b7-118">For information about primary keys, see [Primary and Foreign Key Constraints](../../relational-databases/tables/primary-and-foreign-key-constraints.md).</span></span>  
  
 <span data-ttu-id="391b7-119">**Columnas de propiedades** El conjunto de columnas de propiedades solo es visible en determinadas vistas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="391b7-119">**Property Columns** The set of property columns is visible only in the certain views of your table.</span></span> <span data-ttu-id="391b7-120">Dispone de cinco vistas diferentes para ver una tabla, que le ayudan a controlar el tamaño y el diseño del diagrama.</span><span class="sxs-lookup"><span data-stu-id="391b7-120">You can view a table in any of five different views to help you manage the size and layout of your diagram.</span></span>  
  
 <span data-ttu-id="391b7-121">Para más información sobre las vistas de tabla, consulte [Personalizar la cantidad de información mostrada en los diagramas &#40;Visual Database Tools&#41;](customize-the-amount-of-information-displayed-in-diagrams-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="391b7-121">For more information about table views, see [Customize the Amount of Information Displayed in Diagrams &#40;Visual Database Tools&#41;](customize-the-amount-of-information-displayed-in-diagrams-visual-database-tools.md).</span></span>  
  
## <a name="relationships-in-a-database-diagram"></a><span data-ttu-id="391b7-122">Relaciones de un diagrama de base de datos</span><span class="sxs-lookup"><span data-stu-id="391b7-122">Relationships in a Database Diagram</span></span>  
 <span data-ttu-id="391b7-123">En un diagrama de base de datos, cada relación puede aparecer con tres características distintas: los extremos, un estilo de línea y las tablas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="391b7-123">Within a database diagram, each relationship can appear with three distinct features: endpoints, a line style, and related tables.</span></span>  
  
 <span data-ttu-id="391b7-124">**Extremos** Los extremos de la línea indican si la relación es de uno a uno o de uno a varios.</span><span class="sxs-lookup"><span data-stu-id="391b7-124">**Endpoints** The endpoints of the line indicate whether the relationship is one-to-one or one-to-many.</span></span> <span data-ttu-id="391b7-125">Si una relación tiene una clave en un extremo y un símbolo en forma de ocho en el otro extremo, se trata de una relación de uno a varios.</span><span class="sxs-lookup"><span data-stu-id="391b7-125">If a relationship has a key at one endpoint and a figure-eight at the other, it is a one-to-many relationship.</span></span> <span data-ttu-id="391b7-126">Si una relación tiene una clave en cada extremo, se trata de una relación de uno a uno.</span><span class="sxs-lookup"><span data-stu-id="391b7-126">If a relationship has a key at each endpoint, it is a one-to-one relationship.</span></span>  
  
 <span data-ttu-id="391b7-127">**Estilo de línea** La línea en sí misma (no sus extremos) indica si el sistema de administración de bases de datos (DBMS) exige integridad referencial para la relación cuando se agregan datos nuevos a la tabla de clave externa.</span><span class="sxs-lookup"><span data-stu-id="391b7-127">**Line Style** The line itself (not its endpoints) indicates whether the Database Management System (DBMS) enforces referential integrity for the relationship when new data is added to the foreign-key table.</span></span> <span data-ttu-id="391b7-128">Si la línea aparece sólida, el DBMS exige integridad referencial para la relación cuando se agregan o modifican filas en la tabla de clave externa.</span><span class="sxs-lookup"><span data-stu-id="391b7-128">If the line appears solid, the DBMS enforces referential integrity for the relationship when rows are added or modified in the foreign-key table.</span></span> <span data-ttu-id="391b7-129">Si la línea aparece punteada, el DBMS no exige integridad referencial para la relación cuando se agregan o modifican filas en la tabla de clave externa.</span><span class="sxs-lookup"><span data-stu-id="391b7-129">If the line appears dotted, the DBMS does not enforce referential integrity for the relationship when rows are added or modified in the foreign-key table.</span></span>  
  
 <span data-ttu-id="391b7-130">**Tablas relacionadas** Una relación de clave externa entre dos tablas se indica mediante una línea de relación entre ellas.</span><span class="sxs-lookup"><span data-stu-id="391b7-130">**Related Tables** The relationship line indicates that a foreign-key relationship exists between one table and another.</span></span> <span data-ttu-id="391b7-131">En el caso de una relación de uno a varios, la tabla de clave externa es la tabla situada cerca del símbolo en forma de ocho de la línea.</span><span class="sxs-lookup"><span data-stu-id="391b7-131">For a one-to-many relationship, the foreign-key table is the table near the line's figure-eight symbol.</span></span> <span data-ttu-id="391b7-132">Si ambos extremos de la línea están conectados a la misma tabla, la relación es reflexiva.</span><span class="sxs-lookup"><span data-stu-id="391b7-132">If both endpoints of the line attach to the same table, the relationship is a reflexive relationship.</span></span> <span data-ttu-id="391b7-133">Para más información, consulte [Dibujar relaciones reflexivas &#40;Visual Database Tools&#41;](draw-reflexive-relationships-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="391b7-133">For more information, see [Draw Reflexive Relationships &#40;Visual Database Tools&#41;](draw-reflexive-relationships-visual-database-tools.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="391b7-134">En esta sección</span><span class="sxs-lookup"><span data-stu-id="391b7-134">In this Section</span></span>  
 [<span data-ttu-id="391b7-135">Descripción de la propiedad de un diagrama de base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="391b7-135">Understand Database Diagram Ownership &#40;Visual Database Tools&#41;</span></span>](understand-database-diagram-ownership-visual-database-tools.md)  
  
 [<span data-ttu-id="391b7-136">Desplazarse por el Diseñador de diagramas de base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="391b7-136">Navigate in Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](navigate-in-database-diagram-designer-visual-database-tools.md)  
  
 [<span data-ttu-id="391b7-137">Configurar el Diseñador de diagramas de base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="391b7-137">Set Up Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](set-up-database-diagram-designer-visual-database-tools.md)  
  
 [<span data-ttu-id="391b7-138">Actualizar diagramas de base de datos de ediciones anteriores &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="391b7-138">Upgrade Database Diagrams from Previous Editions &#40;Visual Database Tools&#41;</span></span>](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md)  
  
 [<span data-ttu-id="391b7-139">Abrir el Diseñador de diagramas de base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="391b7-139">Open Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](open-database-diagram-designer-visual-database-tools.md)  
  
## <a name="see-also"></a><span data-ttu-id="391b7-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="391b7-140">See Also</span></span>  
 <span data-ttu-id="391b7-141">[Trabajar con diagramas de base de datos &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="391b7-141">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="391b7-142">[Trabajar con tablas en diagramas de base de datos &#40;Visual Database Tools&#41;](work-with-tables-in-database-diagram-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="391b7-142">[Work with Tables in Database Diagram &#40;Visual Database Tools&#41;](work-with-tables-in-database-diagram-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="391b7-143">Trabajar con el diseño de diagramas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="391b7-143">Work with Diagram Layout &#40;Visual Database Tools&#41;</span></span>](work-with-diagram-layout-visual-database-tools.md)  
  
  