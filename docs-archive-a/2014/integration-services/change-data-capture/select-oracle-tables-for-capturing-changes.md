---
title: Seleccionar tablas de Oracle para capturar cambios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selOraTabDia
ms.assetid: 2e295dc8-999d-4c4d-96cc-1519674b47a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e9064789dce83ff7d3917ed026c861743142e048
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747713"
---
# <a name="select-oracle-tables-for-capturing-changes"></a><span data-ttu-id="de91d-102">Seleccionar tablas de Oracle para capturar cambios</span><span class="sxs-lookup"><span data-stu-id="de91d-102">Select Oracle Tables for Capturing Changes</span></span>
  <span data-ttu-id="de91d-103">Use este cuadro de diálogo para seleccionar las tablas incluidas en la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="de91d-103">Use this dialog box to select the tables that are included in the CDC instance.</span></span> <span data-ttu-id="de91d-104">Las tablas seleccionadas se agregarán a la lista de la página **Seleccionar tablas y columnas** del Asistente para nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="de91d-104">The tables selected are added to the list in the **Select Tables and Columns** page of the New Instance wizard.</span></span> <span data-ttu-id="de91d-105">Puede hacer lo siguiente en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="de91d-105">You can do the following in this dialog box.</span></span>  
  
 <span data-ttu-id="de91d-106">De forma predeterminada, no se incluye ninguna tabla en la lista de tablas de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="de91d-106">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="de91d-107">Puede activar la casilla situada en la parte superior de la columna de casilla para seleccionar todas las tablas o buscar determinadas tablas.</span><span class="sxs-lookup"><span data-stu-id="de91d-107">You can select the check box at the top of the check box column to select all of the tables or search for specific tables.</span></span>  
  
 <span data-ttu-id="de91d-108">**Para buscar tablas específicas**</span><span class="sxs-lookup"><span data-stu-id="de91d-108">**To search for specific tables**</span></span>  
 <span data-ttu-id="de91d-109">Escriba los criterios de búsqueda como se indica aquí y, después, haga clic en **Buscar**:</span><span class="sxs-lookup"><span data-stu-id="de91d-109">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="de91d-110">**Esquema**: seleccione un esquema de base de datos de la lista.</span><span class="sxs-lookup"><span data-stu-id="de91d-110">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="de91d-111">En la lista solo se incluirán las tablas que tengan dicho esquema.</span><span class="sxs-lookup"><span data-stu-id="de91d-111">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="de91d-112">**Patrón de nombre de tabla**: escriba cualquier cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="de91d-112">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="de91d-113">Solo se mostrarán las tablas que incluyan la cadena de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="de91d-113">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de91d-114">Puede especificar criterios en uno o ambos campos.</span><span class="sxs-lookup"><span data-stu-id="de91d-114">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="de91d-115">**Mostrar las 1000 primeras tablas coincidentes**: de forma predeterminada, esta casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="de91d-115">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="de91d-116">Limita la presentación a las 1000 primeras tablas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="de91d-116">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="de91d-117">Si se desactiva la casilla, se mostrarán todas las tablas que cumplan los criterios.</span><span class="sxs-lookup"><span data-stu-id="de91d-117">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="de91d-118">Si hay un gran número de tablas, se puede tardar mucho tiempo en mostrar la lista.</span><span class="sxs-lookup"><span data-stu-id="de91d-118">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="de91d-119">**Para seleccionar las tablas que se van a incluir en la instancia CDC**</span><span class="sxs-lookup"><span data-stu-id="de91d-119">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="de91d-120">Haga clic en la casilla situada junto a cualquiera de las tablas que quiera incluir y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="de91d-120">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="de91d-121">Las tablas se agregarán a la lista de la página **Seleccionar tablas y columnas** del Asistente para nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="de91d-121">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="de91d-122">Haga clic en **Cerrar** para cerrar el cuadro de diálogo sin agregar ninguna tabla adicional.</span><span class="sxs-lookup"><span data-stu-id="de91d-122">Click **Close** to close the dialog box without adding any additional tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de91d-123">Si selecciona una tabla que incluye un tipo de datos no admitido, verá un mensaje de error y la tabla no se incluirá.</span><span class="sxs-lookup"><span data-stu-id="de91d-123">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de91d-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de91d-124">See Also</span></span>  
 <span data-ttu-id="de91d-125">[Cómo crear la instancia de base de datos de cambios de SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="de91d-125">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="de91d-126">Seleccione las columnas y tablas de Oracle </span><span class="sxs-lookup"><span data-stu-id="de91d-126">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
