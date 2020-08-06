---
title: Cuadro de diálogo crear o editar relación (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.createrelationship.f1
helpviewer_keywords:
- Create Relationship dialog box
ms.assetid: da3c7074-623e-4ddf-a707-d3276a47cf1c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4edae3f78ac6b764d91e1be97787fe59d49421db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671272"
---
# <a name="create-or-edit-relationship-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="59d8d-102">Cuadro de diálogo Crear o Editar relación (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="59d8d-102">Create or Edit Relationship Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="59d8d-103">Use el cuadro de diálogo **Crear/Editar relación** en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para definir o modificar una relación en una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="59d8d-103">Use the **Create/Edit Relationship** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a relationship in a data source view.</span></span> <span data-ttu-id="59d8d-104">Puede mostrar el cuadro de diálogo **Crear relación/Editar relación** de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="59d8d-104">You can display the **Create/Edit Relationship** dialog box by:</span></span>  
  
-   <span data-ttu-id="59d8d-105">Haciendo clic en **Nueva relación** en el panel **Barra de herramientas** del **Diseñador de vistas del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="59d8d-105">Clicking **New Relationship** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="59d8d-106">Haciendo clic con el botón derecho en una tabla de los paneles **Tablas** o **Diagrama** del **Diseñador de vistas del origen de datos** y seleccionando **Nueva relación**.</span><span class="sxs-lookup"><span data-stu-id="59d8d-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Relationship**.</span></span>  
  
-   <span data-ttu-id="59d8d-107">Haciendo clic con el botón derecho en el panel **Diagrama** del **Diseñador de vistas del origen de datos** y seleccionando **Editar relación**.</span><span class="sxs-lookup"><span data-stu-id="59d8d-107">Right-clicking a relationship in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Relationship**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59d8d-108"> Puede crear relaciones en el **Diseñador de vistas del origen de datos** que no existen en el origen de datos subyacente y eliminar relaciones creadas mediante el **Diseñador de vistas del origen de datos** a partir de relaciones de clave externa en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="59d8d-108">You can create relationships in **Data Source View Designer** that do not exist in the underlying data source, and remove relationships created by **Data Source View Designer** from existing foreign key relationships in the underlying data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="59d8d-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="59d8d-109">Options</span></span>  
 <span data-ttu-id="59d8d-110">**Tabla de origen (de clave externa)**</span><span class="sxs-lookup"><span data-stu-id="59d8d-110">**Source (foreign key) table**</span></span>  
 <span data-ttu-id="59d8d-111">Seleccione la tabla o consulta con nombre que contiene la referencia a una o varias columnas de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="59d8d-111">Select the table or named query that contains the reference to one or more columns in the destination table.</span></span>  
  
 <span data-ttu-id="59d8d-112">**Tabla de destino (de clave principal)**</span><span class="sxs-lookup"><span data-stu-id="59d8d-112">**Destination (primary key) table**</span></span>  
 <span data-ttu-id="59d8d-113">Seleccione la tabla que contiene una o varias columnas a las que la tabla de origen hace referencia.</span><span class="sxs-lookup"><span data-stu-id="59d8d-113">Select the table that contains one or more columns referenced by the source table.</span></span> <span data-ttu-id="59d8d-114">Para autocombinaciones, seleccione la misma tabla seleccionada en la **Tabla de origen (de clave externa)**.</span><span class="sxs-lookup"><span data-stu-id="59d8d-114">For self-joins, select the same table selected in **Source (foreign key) table**.</span></span>  
  
 <span data-ttu-id="59d8d-115">**Columnas de origen**</span><span class="sxs-lookup"><span data-stu-id="59d8d-115">**Source columns**</span></span>  
 <span data-ttu-id="59d8d-116">Seleccione las columnas que hacen referencia a columnas de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="59d8d-116">Select the columns that reference columns in the destination table.</span></span>  
  
 <span data-ttu-id="59d8d-117">**Columnas de destino**</span><span class="sxs-lookup"><span data-stu-id="59d8d-117">**Destination columns**</span></span>  
 <span data-ttu-id="59d8d-118">Seleccione las columnas a las que hacen referencia las columnas de la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="59d8d-118">Select the columns that are referenced by columns in the source table.</span></span>  
  
 <span data-ttu-id="59d8d-119">**Viceversa**</span><span class="sxs-lookup"><span data-stu-id="59d8d-119">**Reverse**</span></span>  
 <span data-ttu-id="59d8d-120">Haga clic para invertir la dirección de la relación.</span><span class="sxs-lookup"><span data-stu-id="59d8d-120">Click to reverse the direction of the relationship.</span></span>  
  
 <span data-ttu-id="59d8d-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="59d8d-121">**Description**</span></span>  
 <span data-ttu-id="59d8d-122">Escriba una descripción opcional para la relación.</span><span class="sxs-lookup"><span data-stu-id="59d8d-122">Type an optional description for the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59d8d-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59d8d-123">See Also</span></span>  
 <span data-ttu-id="59d8d-124">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="59d8d-124">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="59d8d-125">Diseñador de vistas del origen de datos &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="59d8d-125">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
