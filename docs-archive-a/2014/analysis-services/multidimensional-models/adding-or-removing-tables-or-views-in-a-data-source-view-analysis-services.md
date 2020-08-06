---
title: Agregar o quitar tablas o vistas en una vista del origen de datos (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.tablespane.f1
helpviewer_keywords:
- deleting tables
- tables [Analysis Services]
- removing tables
- adding tables
- data source views [Analysis Services], tables
- tables [Analysis Services], data source views
ms.assetid: 98307d04-6548-4d7d-9244-2371dd165249
author: minewiskan
ms.author: owend
ms.openlocfilehash: da1bc2b1ac0af7576cfe3c3593b451f78d6a9fae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677251"
---
# <a name="adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services"></a><span data-ttu-id="5dbf1-102">Agregar o quitar tablas o vistas en una vista del origen de datos (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="5dbf1-102">Adding or Removing Tables or Views in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="5dbf1-103">Después de crear una vista del origen de datos (DSV) en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], puede modificarla en el Diseñador de vistas del origen de datos agregando o quitando tablas y columnas, incluidas las tablas y columnas procedentes de otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-103">After you have created a data source view (DSV) in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can modify it in Data Source View Designer by adding or removing tables and columns, including tables and columns from another data source.</span></span>  
  
 <span data-ttu-id="5dbf1-104">Para abrir la DSV en el Diseñador de vistas del origen de datos, haga doble clic en la vista en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-104">To open the DSV in Data Source View Designer, you double-click the DSV in Solution Explorer.</span></span> <span data-ttu-id="5dbf1-105">Una vez que abra la DSV, puede usar el comando **Agregar o quitar tablas** en la barra de botones o en el menú para modificar o ampliar la DSV.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-105">Once you open the DSV, you can use the **Add/Remove Tables** command on the button bar or menu to modify or extend the DSV.</span></span> <span data-ttu-id="5dbf1-106">También puede trabajar con objetos del diagrama.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-106">You can also work with the objects in the diagram.</span></span> <span data-ttu-id="5dbf1-107">Por ejemplo, puede seleccionar un objeto y luego usar la tecla Supr del teclado para quitar el objeto.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-107">For example, you can select an object and then use the Delete key on your keyboard to remove an object.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="5dbf1-108">Tenga cuidado al quitar una tabla.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-108">Use caution when removing a table.</span></span> <span data-ttu-id="5dbf1-109">Al quitar una tabla se eliminan todas las columnas y relaciones asociadas de la DSV y se invalidan todos los objetos enlazados a esa tabla.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-109">Removing a table deletes all the associated columns and relationships from the DSV and invalidates all objects bound to that table.</span></span>  
  
## <a name="selecting-tables-or-views-to-add-or-remove"></a><span data-ttu-id="5dbf1-110">Seleccionar las tablas o vistas que se van a agregar o quitar</span><span class="sxs-lookup"><span data-stu-id="5dbf1-110">Selecting Tables or Views to Add or Remove</span></span>  
 <span data-ttu-id="5dbf1-111">El cuadro de diálogo **Agregar o quitar tablas** le permite mover tablas o vistas entre las listas **Objetos disponibles** y **Objetos incluidos** .</span><span class="sxs-lookup"><span data-stu-id="5dbf1-111">Using the **Add/Remove Tables** dialog box, you can move tables or views between the **Available objects** and **Included objects** lists.</span></span> <span data-ttu-id="5dbf1-112">La lista **Objetos disponibles** incluye inicialmente las tablas o vistas del origen de datos principal que no están ya incluidas en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-112">The **Available objects** list initially includes any tables or views in the primary data source that are not already in the data source view.</span></span> <span data-ttu-id="5dbf1-113">Si el origen de datos principal admite la función `OPENROWSET`, también puede agregar tablas o vistas de otros orígenes de datos de la base de datos o el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-113">If the primary data source supports the `OPENROWSET` function, you can also add tables or views from other data sources in the project or database.</span></span>  
  
 <span data-ttu-id="5dbf1-114">Si se agrega o se quita una tabla de una DSV, también se agrega o se quita la tabla del diagrama seleccionado actualmente en la DSV.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-114">Adding or removing a table to the DSV also adds or removes the table to the currently selected diagram in the DSV.</span></span> <span data-ttu-id="5dbf1-115">Para obtener más información sobre los diagramas, vea [Trabajar con diagramas en el Diseñador de vistas del origen de datos &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="5dbf1-115">For more information on diagrams, see [Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span></span>  
  
 <span data-ttu-id="5dbf1-116">Después de mover una tabla a la lista **Objetos incluidos** del cuadro de diálogo **Agregar o quitar tablas** , puede agregar todas las tablas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-116">After you move a table to the **Included objects** list in the **Add/Remove Tables** dialog box, you can add all related tables.</span></span> <span data-ttu-id="5dbf1-117">Esta operación agrega las tablas según las restricciones de clave externa del origen de datos, si existen.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-117">This operation adds tables according to foreign key constraints in the data source, if such constraints exist.</span></span> <span data-ttu-id="5dbf1-118">Si no existen restricciones de clave externa, puede usar la propiedad `NameMatchingCriteria` de la vista del origen de datos para determinar las relaciones mediante la especificación de un criterio de coincidencia de los nombres de columna de las tablas para generar relaciones probables.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-118">If foreign key constraints do not exist, you can use the `NameMatchingCriteria` property of the data source view to determine relationships by specifying a criterion for matching column names in tables to generate likely relationships.</span></span> <span data-ttu-id="5dbf1-119">Si `NameMatchingCriteria` se especifica la propiedad para la vista del origen de datos, haga clic en **Agregar tablas relacionadas** para agregar las tablas del origen de datos que tienen nombres de columna coincidentes.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-119">If the `NameMatchingCriteria`property is specified for the data source view, click **Add Related Tables** to add tables from the data source that have matching column names.</span></span> <span data-ttu-id="5dbf1-120">Para obtener más información sobre cómo establecer la `NameMatchingCriteria` propiedad, vea [vistas del origen de datos en modelos multidimensionales](data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="5dbf1-120">For more information about setting the `NameMatchingCriteria` property, see [Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5dbf1-121">Agregar o quitar objetos de una vista del origen de datos no afecta al origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="5dbf1-121">Adding or removing objects in a data source view does not affect the underlying data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dbf1-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5dbf1-122">See Also</span></span>  
 <span data-ttu-id="5dbf1-123">[Vistas del origen de datos en modelos multidimensionales](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="5dbf1-123">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="5dbf1-124">Trabajar con diagramas en el Diseñador de vistas del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5dbf1-124">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
  
