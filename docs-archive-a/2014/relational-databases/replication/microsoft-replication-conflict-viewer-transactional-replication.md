---
title: Visor de conflictos de replicación de Microsoft (Replicación transaccional) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.cvqueued.f1
ms.assetid: eec59d8e-cadb-4623-a31f-9f42ec09c97f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cc3f2ea3d1d2b29fba9c9d9121e23bf4bcd88bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661946"
---
# <a name="microsoft-replication-conflict-viewer-transactional-replication"></a><span data-ttu-id="3b7b7-102">Visor de conflictos de replicación de Microsoft (Replicación transaccional)</span><span class="sxs-lookup"><span data-stu-id="3b7b7-102">Microsoft Replication Conflict Viewer (Transactional Replication)</span></span>
  <span data-ttu-id="3b7b7-103">El Visor de conflictos de replicación permite ver los conflictos surgidos durante la sincronización de la replicación transaccional punto a punto y la replicación transaccional con suscripciones de actualización en cola.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-103">The Replication Conflict Viewer enables you to view conflicts that have occurred during synchronization for peer-to-peer transactional replication and transactional replication with queued updating subscriptions.</span></span> <span data-ttu-id="3b7b7-104">Para obtener más información, vea [Ver conflictos de datos para publicaciones transaccionales &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="3b7b7-104">For more information, see [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b7b7-105">El Visor de conflictos de replicación muestra los conflictos que se producen durante la replicación de mezcla y la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-105">The Replication Conflict Viewer displays conflicts that occur in merge replication and in transactional replication.</span></span> <span data-ttu-id="3b7b7-106">Para la replicación transaccional, puede utilizarse el Visor de conflictos de replicación para ver los datos de los conflictos, pero no puede elegir una resolución distinta para el conflicto.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-106">For transactional replication, you can use Replication Conflict Viewer to view conflict data, but you cannot choose a different resolution for the conflict.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3b7b7-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="3b7b7-107">Options</span></span>  
 <span data-ttu-id="3b7b7-108">El Visor de conflictos de replicación está dividido en dos secciones.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-108">The Replication Conflict Viewer is divided into two sections.</span></span> <span data-ttu-id="3b7b7-109">La sección superior del cuadro de diálogo muestra la lista de conflictos de la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-109">The upper section of the dialog box shows the conflict list for the selected table.</span></span> <span data-ttu-id="3b7b7-110">Si hace clic en un elemento de la lista de conflictos, se mostrarán los detalles del conflicto en la sección inferior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-110">When you click an item in the conflict list, the details of the conflict are displayed in the lower section of the dialog box.</span></span>  
  
 <span data-ttu-id="3b7b7-111">Los datos del conflicto de la sección inferior se muestran en las dos columnas correspondientes (**Ganador del conflicto** y **Perdedor del conflicto**).</span><span class="sxs-lookup"><span data-stu-id="3b7b7-111">The conflict data in the lower section is displayed in two corresponding columns (**Conflict Winner** and **Conflict Loser**).</span></span> <span data-ttu-id="3b7b7-112">Si el conflicto se produce entre datos actualizados y eliminados, es posible que no haya datos que mostrar en el lado eliminado del conflicto.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-112">If the conflict is between updated and deleted data, there may be no data to show for the deleted side of the conflict.</span></span> <span data-ttu-id="3b7b7-113">En este caso, el Visor de conflictos de replicación muestra un mensaje en una de las columnas en el que indica que se eliminó la fila en una ubicación y se actualizó en otra.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-113">In this case, the Replication Conflict Viewer displays a message in one of the columns, indicating the row was deleted at one location and updated at another.</span></span> <span data-ttu-id="3b7b7-114">También indica la resolución recomendada.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-114">It also indicates the suggested resolution.</span></span>  
  
 <span data-ttu-id="3b7b7-115">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-115">**Database**</span></span>  
 <span data-ttu-id="3b7b7-116">Elija una base de datos que contenga publicaciones con conflictos.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-116">Choose a database that includes publications with conflicts.</span></span>  
  
 <span data-ttu-id="3b7b7-117">**Publicación**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-117">**Publication**</span></span>  
 <span data-ttu-id="3b7b7-118">Elija una publicación que contenga tablas con conflictos.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-118">Choose a publication that includes tables with conflicts.</span></span>  
  
 <span data-ttu-id="3b7b7-119">**Tabla**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-119">**Table**</span></span>  
 <span data-ttu-id="3b7b7-120">Elija una tabla que contenga conflictos.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-120">Choose a table that includes conflicts.</span></span>  
  
 <span data-ttu-id="3b7b7-121">**Definir filtro**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-121">**Define Filter**</span></span>  
 <span data-ttu-id="3b7b7-122">Haga clic para abrir el cuadro de diálogo **Definir filtros** .</span><span class="sxs-lookup"><span data-stu-id="3b7b7-122">Click to open the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="3b7b7-123">**Aplicar o quitar filtro**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-123">**Apply or Remove Filter**</span></span>  
 <span data-ttu-id="3b7b7-124">Haga clic para aplicar o quitar un filtro definido en el cuadro de diálogo **Definir filtros** .</span><span class="sxs-lookup"><span data-stu-id="3b7b7-124">Click to apply or remove a filter that has been defined in the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="3b7b7-125">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-125">**Select All**</span></span>  
 <span data-ttu-id="3b7b7-126">Haga clic para seleccionar todos los conflictos mostrados en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-126">Click to select all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="3b7b7-127">**Seleccione ninguno**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-127">**Select None**</span></span>  
 <span data-ttu-id="3b7b7-128">Haga clic para anular la selección de todos los conflictos mostrados en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-128">Click to deselect all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="3b7b7-129">**Remove**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-129">**Remove**</span></span>  
 <span data-ttu-id="3b7b7-130">Haga clic en esta opción para quitar los conflictos seleccionados del visor y los metadatos asociados de las tablas del sistema de replicación.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-130">Click to remove selected conflicts from the viewer and their associated metadata from the replication system tables.</span></span>  
  
 <span data-ttu-id="3b7b7-131">**Mostrar todas las columnas**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-131">**Show all columns**</span></span>  
 <span data-ttu-id="3b7b7-132">Seleccione esta opción para mostrar todas las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-132">Select to show all columns of the table.</span></span>  
  
 <span data-ttu-id="3b7b7-133">**Mostrar las primeras cinco columnas y el resto de las columnas con datos en conflicto**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-133">**Show first five columns and other columns with conflicting data**</span></span>  
 <span data-ttu-id="3b7b7-134">Seleccione esta opción para mostrar las cinco primeras columnas y otras columnas con conflictos.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-134">Select to display the first five columns and any columns that have conflicts.</span></span> <span data-ttu-id="3b7b7-135">Resulta útil si las tablas presentan un número elevado de columnas y solo desea ver las columnas más importantes para solucionar el conflicto.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-135">This is helpful when the table has a large number of columns, but you want to see only the columns most relevant to resolving the conflict.</span></span> <span data-ttu-id="3b7b7-136">Las cinco primeras columnas se incluyen en esta vista, como campos que identifican una fila, como la clave principal o campos de nombre, que con frecuencia se encuentran entre las cinco primeras columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-136">The first five columns are always included in this view, as fields that identify a row, such as the primary key or name fields, are often among the first columns of the table.</span></span>  
  
 <span data-ttu-id="3b7b7-137">**Mostrar información de columna** (**...**)</span><span class="sxs-lookup"><span data-stu-id="3b7b7-137">**Display Column Information** (**...**)</span></span>  
 <span data-ttu-id="3b7b7-138">Haga clic para ver la información de la columna: **Nombre de tabla**, **Nombre de columna**, **Tipo de datos**y **Valor de columna**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-138">Click to view column information: **Table Name**, **Column Name**, **Data Type**, and **Column Value**.</span></span>  
  
 <span data-ttu-id="3b7b7-139">**Registrar los detalles de este conflicto**</span><span class="sxs-lookup"><span data-stu-id="3b7b7-139">**Log the details of the conflict**</span></span>  
 <span data-ttu-id="3b7b7-140">Active esta casilla para registrar los detalles del conflicto en un archivo.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-140">Check this box to log the details of the conflict to a file.</span></span> <span data-ttu-id="3b7b7-141">Para especificar la ubicación del archivo, señale el menú **Ver** y haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-141">To specify a location for the file, point to the **View** menu and click **Options**.</span></span> <span data-ttu-id="3b7b7-142">Escriba un valor o haga clic en el botón de búsqueda (**...**) y navegue hasta encontrar el archivo adecuado.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-142">Enter a value, or click the browse (**...**) and navigate to the appropriate file.</span></span> <span data-ttu-id="3b7b7-143">Haga clic en **Aceptar** para salir del cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="3b7b7-143">Click **OK** to exit the **Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b7b7-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b7b7-144">See Also</span></span>  
 <span data-ttu-id="3b7b7-145">[Detección de conflictos en la replicación punto a punto](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span><span class="sxs-lookup"><span data-stu-id="3b7b7-145">[Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span></span>  
 [<span data-ttu-id="3b7b7-146">Ver conflictos de datos para publicaciones transaccionales &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3b7b7-146">View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;</span></span>](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)  
  
  
