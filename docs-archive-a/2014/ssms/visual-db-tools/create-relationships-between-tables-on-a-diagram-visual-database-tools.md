---
title: Crear relaciones entre tablas en un diagrama (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- diagrams [SQL Server], designing
ms.assetid: 28e9630c-dff4-46cc-bb0e-fe77998b6ac2
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7d627a37f84dcb66b2129bb9c7dbc5890ccd46c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749577"
---
# <a name="create-relationships-between-tables-on-a-diagram-visual-database-tools"></a><span data-ttu-id="dbcbb-102">Crear relaciones entre tablas en un diagrama (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="dbcbb-102">Create Relationships Between Tables on a Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="dbcbb-103">Puede crear relaciones entre columnas de diferentes tablas en el Diseñador de diagramas si se arrastran las columnas entre las tablas.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-103">You can create relationships between columns in different tables in the Diagram Designer by dragging columns between tables.</span></span>  
  
### <a name="to-create-a-relationship-graphically"></a><span data-ttu-id="dbcbb-104">Para crear una relación gráficamente</span><span class="sxs-lookup"><span data-stu-id="dbcbb-104">To create a relationship graphically</span></span>  
  
1.  <span data-ttu-id="dbcbb-105">En el Diseñador de bases de datos, haga clic en el selector de fila de una o varias columnas de la base de datos que desea poner en relacionar con una columna de otra tabla.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-105">In Database Designer, click the row selector for one or more database columns that you want to relate to a column in another table.</span></span>  
  
2.  <span data-ttu-id="dbcbb-106">Arrastre las columnas seleccionadas hasta la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-106">Drag the selected column(s) to the related table.</span></span>  
  
3.  <span data-ttu-id="dbcbb-107">Aparecen dos cuadros de diálogo: **Relación de clave externa** y **Tablas y columnas**, esta última en primer plano.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-107">Two dialog boxes appear: **Foreign Key Relationship** and **Tables and Columns**, with the latter appearing in the foreground.</span></span>  
  
4.  <span data-ttu-id="dbcbb-108">**Nombre de la relación** incluye un nombre proporcionado por el sistema con el formato FK_*tablalocal*_*tablaexterna*.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-108">**Relationship name** has a system-provided name in the format FK_*localtable*_*foreigntable*.</span></span> <span data-ttu-id="dbcbb-109">Se puede modificar este valor.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-109">You may change this value.</span></span>  
  
5.  <span data-ttu-id="dbcbb-110">Compruebe que **Tabla de clave principal** especifica la tabla correcta.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-110">Verify that **Primary key table** specifies the correct table.</span></span>  
  
6.  <span data-ttu-id="dbcbb-111">En la cuadrícula se enumeran las columnas locales y las columnas externas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-111">The grid lists the local columns and their matching foreign columns.</span></span> <span data-ttu-id="dbcbb-112">Puede agregar o quitar columnas de la tabla, así como modificar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-112">You can add or remove table columns or change mappings.</span></span>  
  
7.  <span data-ttu-id="dbcbb-113">Elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-113">Choose **OK**.</span></span>  
  
     <span data-ttu-id="dbcbb-114">Aparecerá el cuadro de diálogo **Relación de clave externa** .</span><span class="sxs-lookup"><span data-stu-id="dbcbb-114">The **Foreign Key Relationship** dialog box appears.</span></span> <span data-ttu-id="dbcbb-115">**Relación seleccionada** muestra la relación que haya creado.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-115">**Selected Relationship** shows the relationship you have created.</span></span>  
  
8.  <span data-ttu-id="dbcbb-116">Cambie las propiedades de la relación en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-116">Change properties for the relationship in the grid.</span></span>  
  
9. <span data-ttu-id="dbcbb-117">Elija **Aceptar** para crear la relación.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-117">Choose **OK** to create the relationship.</span></span>  
  
     <span data-ttu-id="dbcbb-118">El Diseñador de bases de datos muestra una relación entre las columnas que haya elegido.</span><span class="sxs-lookup"><span data-stu-id="dbcbb-118">Database Designer shows a relationship between the columns you chose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbcbb-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbcbb-119">See Also</span></span>  
 <span data-ttu-id="dbcbb-120">[Cuadro de diálogo tablas y columnas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dbcbb-120">[Tables and Columns Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="dbcbb-121">[Restricciones UNIQUE y restricciones check](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="dbcbb-121">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="dbcbb-122">Trabajar con tablas en diagramas de base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="dbcbb-122">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
