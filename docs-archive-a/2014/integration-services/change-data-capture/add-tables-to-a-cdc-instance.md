---
title: Agregar tablas a una instancia CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- addTabs
ms.assetid: ad260e19-c021-4035-9311-c02fc96ceaea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: edcd84db9e3c464334d407987cb3567f78edd44e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744280"
---
# <a name="add-tables-to-a-cdc-instance"></a><span data-ttu-id="3f4b3-102">Agregar tablas a una instancia CDC</span><span class="sxs-lookup"><span data-stu-id="3f4b3-102">Add Tables to a CDC Instance</span></span>
  <span data-ttu-id="3f4b3-103">Use el cuadro de diálogo Selección de tablas para agregar tablas adicionales del origen de Oracle a la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-103">Use the Table Selection dialog box to add additional tables from the Oracle source to the CDC instance.</span></span> <span data-ttu-id="3f4b3-104">Las tablas seleccionadas se agregarán a la lista de la pestaña **Tablas** del editor de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-104">The tables selected are added to the list in the **Tables** tab of the Properties editor.</span></span>  
  
 <span data-ttu-id="3f4b3-105">De forma predeterminada, no se incluye ninguna tabla en la lista de tablas de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-105">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="3f4b3-106">Puede activar la casilla **(Seleccionar todo)** o buscar tablas específicas.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-106">You can select the **(Select All)** check box or search for specific tables.</span></span>  
  
 <span data-ttu-id="3f4b3-107">**Para buscar tablas específicas**</span><span class="sxs-lookup"><span data-stu-id="3f4b3-107">**To search for specific tables**</span></span>  
 <span data-ttu-id="3f4b3-108">Escriba los criterios de búsqueda como se indica aquí y, después, haga clic en **Buscar**:</span><span class="sxs-lookup"><span data-stu-id="3f4b3-108">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="3f4b3-109">**Esquema**: seleccione un esquema de base de datos de la lista.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-109">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="3f4b3-110">En la lista solo se incluirán las tablas que tengan dicho esquema.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-110">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="3f4b3-111">**Patrón de nombre de tabla**: escriba cualquier cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-111">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="3f4b3-112">Solo se mostrarán las tablas que incluyan la cadena de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-112">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f4b3-113">Puede especificar criterios en uno o ambos campos.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-113">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="3f4b3-114">**Mostrar las 1000 primeras tablas coincidentes**: de forma predeterminada, esta casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-114">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="3f4b3-115">Limita la presentación a las 1000 primeras tablas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-115">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="3f4b3-116">Si se desactiva la casilla, se mostrarán todas las tablas que cumplan los criterios.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-116">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="3f4b3-117">Si hay un gran número de tablas, se puede tardar mucho tiempo en mostrar la lista.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-117">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="3f4b3-118">**Para seleccionar las tablas que se van a incluir en la instancia CDC**</span><span class="sxs-lookup"><span data-stu-id="3f4b3-118">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="3f4b3-119">Haga clic en la casilla situada junto a cualquiera de las tablas que quiera incluir y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-119">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="3f4b3-120">Las tablas se agregarán a la lista de la página **Seleccionar tablas y columnas** del Asistente para nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-120">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="3f4b3-121">Haga clic en **Cerrar** para cerrar el cuadro de diálogo sin agregar ninguna tabla.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-121">Click **Close** to close the dialog box without adding any tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f4b3-122">Si selecciona una tabla que incluye un tipo de datos no admitido, verá un mensaje de error y la tabla no se incluirá.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-122">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f4b3-123">Puede ver la lista de tablas en el visor.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-123">You can view the list of tables in the viewer.</span></span> <span data-ttu-id="3f4b3-124">Cuando se usa el visor, la información es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-124">When using the viewer the information is read only.</span></span> <span data-ttu-id="3f4b3-125">El visor también incluye una lista de las columnas capturadas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3f4b3-125">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="3f4b3-126">Para obtener información acerca de cómo obtener acceso al visor, vea [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="3f4b3-126">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4b3-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f4b3-127">See Also</span></span>  
 <span data-ttu-id="3f4b3-128">[Cómo editar las propiedades de la instancia CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="3f4b3-128">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 <span data-ttu-id="3f4b3-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="3f4b3-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="3f4b3-130">Seleccionar tablas de Oracle para capturar cambios </span><span class="sxs-lookup"><span data-stu-id="3f4b3-130">Select Oracle Tables for Capturing Changes</span></span>](select-oracle-tables-for-capturing-changes.md)  
  
  
