---
title: Índice de texto completo (cuadro de diálogo, Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextindex
ms.assetid: ef45b585-2567-4abe-b421-9fd0994e0146
author: stevestein
ms.author: sstein
ms.openlocfilehash: f98d3bf43707caedd8c9d0a01349f36d5a5bfbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750402"
---
# <a name="full-text-index-dialog-box-visual-database-tools"></a><span data-ttu-id="1c9f2-102">Índice de texto completo (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1c9f2-102">Full-Text Index Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="1c9f2-103">Este cuadro de diálogo permite crear un índice de texto completo para realizar búsquedas de texto completo en columnas basadas en texto de las tablas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-103">This dialog box allows you to create a full-text index, for full-text searches on text-based columns in your database tables.</span></span> <span data-ttu-id="1c9f2-104">Un índice de texto completo se basa en un índice normal, por lo que deberá crear primero este último.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-104">A full-text index relies on a regular index, so you must create that first.</span></span> <span data-ttu-id="1c9f2-105">El índice normal debe crearse en una sola columna sin valores NULL, y es conveniente elegir una columna con valores más pequeños que una con valores más grandes.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-105">The regular index must be created on a single, non-null column; it is best to choose a column with small values rather than a column with large ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c9f2-106">Para crear un índice de texto completo, debe crear primero un catálogo de texto completo para la base de datos mediante una herramienta externa, como [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o el Administrador corporativo.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-106">To create a full-text index, you must first create a full-text catalog for the database using an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c9f2-107">La funcionalidad de índice de texto completo no está disponible en todas las ediciones de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c9f2-107">Full-text index functionality is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1c9f2-108">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="1c9f2-108">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1c9f2-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="1c9f2-109">Options</span></span>  
 <span data-ttu-id="1c9f2-110">**Índice de texto completo seleccionado**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-110">**Selected Full-Text Index**</span></span>  
 <span data-ttu-id="1c9f2-111">Muestra los índices de texto completo existentes.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-111">Lists existing full-text indexes.</span></span> <span data-ttu-id="1c9f2-112">Seleccione un índice para mostrar sus propiedades en la cuadrícula situada a la derecha.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-112">Select an index to show its properties in the grid to the right.</span></span> <span data-ttu-id="1c9f2-113">Si la lista está vacía, no se han definido relaciones de texto completo para la tabla.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-113">If the list is empty, no full-text relationships have been defined for the table.</span></span>  
  
 <span data-ttu-id="1c9f2-114">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-114">**Add**</span></span>  
 <span data-ttu-id="1c9f2-115">Crea un nuevo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-115">Create a new full-text index.</span></span>  
  
 <span data-ttu-id="1c9f2-116">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-116">**Delete**</span></span>  
 <span data-ttu-id="1c9f2-117">Elimina el índice de texto seleccionado en la lista **Índice de texto completo seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="1c9f2-117">Delete the full-text index selected in the **Selected Full-Text Index** list.</span></span>  
  
 <span data-ttu-id="1c9f2-118">**Categoría General**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-118">**General Category**</span></span>  
 <span data-ttu-id="1c9f2-119">Expandido, muestra **Columnas** y **Nombre de catálogo de texto completo**.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-119">When expanded, shows **Columns** and **Full-text Catalog Name**.</span></span>  
  
 <span data-ttu-id="1c9f2-120">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-120">**Columns**</span></span>  
 <span data-ttu-id="1c9f2-121">Muestra una lista separada por comas de los nombres de las columnas en las que se pueden realizar búsquedas de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-121">Displays a comma-separated list of the names of full-text-searchable columns.</span></span> <span data-ttu-id="1c9f2-122">Para ver la lista completa, haga clic en el botón de puntos suspensivos ( **...** ) situado a la izquierda del campo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-122">To see the complete list, click the ellipsis button (**...**) to the left of the property field.</span></span>  
  
 <span data-ttu-id="1c9f2-123">**Full-Text Catalog Name**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-123">**Full-Text Catalog Name**</span></span>  
 <span data-ttu-id="1c9f2-124">Muestra el nombre del catálogo de texto completo en el que se almacena el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-124">Displays the name of the full-text catalog on which this full-text index is stored.</span></span> <span data-ttu-id="1c9f2-125">Para guardar el índice en un catálogo diferente, haga clic en el nombre del catálogo y elija otro catálogo en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-125">To store the index on a different catalog, click the catalog name and choose another from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c9f2-126">El catálogo debe crearse primero en una herramienta externa, como [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o el Administrador corporativo.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-126">The catalog must be created first in an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
 <span data-ttu-id="1c9f2-127">**Categoría Identidad**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-127">**Identity Category**</span></span>  
 <span data-ttu-id="1c9f2-128">Expandido, muestra el campo de nombre de este índice.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-128">When expanded, shows the name field for this index.</span></span>  
  
 <span data-ttu-id="1c9f2-129">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-129">**Name**</span></span>  
 <span data-ttu-id="1c9f2-130">Muestra el nombre especificado por el sistema para este índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-130">Displays the system-specified name for this full-text index.</span></span>  
  
 <span data-ttu-id="1c9f2-131">**Categoría Diseñador de tablas**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-131">**Table Designer Category**</span></span>  
 <span data-ttu-id="1c9f2-132">Expandido, muestra las propiedades que definen la actuación del índice.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-132">When expanded, shows properties that dictate how the index performs.</span></span>  
  
 <span data-ttu-id="1c9f2-133">**Activo**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-133">**Active**</span></span>  
 <span data-ttu-id="1c9f2-134">Indica si actualmente es posible realizar una búsqueda de texto completo mediante este índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-134">Indicates whether you can currently perform a full-text search using this full-text index.</span></span>  
  
 <span data-ttu-id="1c9f2-135">**Configuración de control de cambios**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-135">**Change Tracking Setting**</span></span>  
 <span data-ttu-id="1c9f2-136">Describe el estado del seguimiento de cambios de este índice: Manual, Automático o Desactivado.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-136">Describes the status of change tracking for this index: Manual, Auto, or Off.</span></span>  
  
 <span data-ttu-id="1c9f2-137">**Rastreo completado**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-137">**Crawl Completed**</span></span>  
 <span data-ttu-id="1c9f2-138">Muestra si ha finalizado el rastreo más reciente.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-138">Shows whether the most recent crawl has been completed.</span></span> <span data-ttu-id="1c9f2-139">Si el valor de esta propiedad es No, el proceso de rastreo estará en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-139">If this property value is No, a crawl is currently in progress.</span></span>  
  
 <span data-ttu-id="1c9f2-140">**Fecha final del rastreo actual y último**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-140">**End Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="1c9f2-141">Muestra la fecha y la hora en que terminó el rastreo más reciente.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-141">Displays the date and time that the most recent crawl ended.</span></span>  
  
 <span data-ttu-id="1c9f2-142">**Errores del rastreo actual o último**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-142">**Errors In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="1c9f2-143">Muestra el número de errores del rastreo actual o del más reciente.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-143">Displays the number of errors in current or most recent crawl.</span></span>  
  
 <span data-ttu-id="1c9f2-144">**Versión de índice**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-144">**Index Version**</span></span>  
 <span data-ttu-id="1c9f2-145">Muestra la versión de la tabla del esquema en el momento en que se inició el rastreo.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-145">Displays the schema version of table at time the crawl started.</span></span>  
  
 <span data-ttu-id="1c9f2-146">**Filas del rastreo actual o último**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-146">**Rows In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="1c9f2-147">Muestra el número de filas actualizadas en el rastreo actual o en el más reciente.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-147">Displays the number of rows updated in the current or most recent crawl.</span></span>  
  
 <span data-ttu-id="1c9f2-148">**Fecha de inicio y hora del rastreo actual y último**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-148">**Start Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="1c9f2-149">Muestra la fecha y la hora en que se inició el rastreo actual o el más reciente.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-149">Displays the date and time that the current or most recent crawl started.</span></span>  
  
 <span data-ttu-id="1c9f2-150">**Marca de tiempo para el rastreo siguiente**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-150">**Time Stamp For Next Crawl**</span></span>  
 <span data-ttu-id="1c9f2-151">Muestra la fecha y la hora en que se va a iniciar el siguiente rastreo.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-151">Displays the date and time that the next crawl will start.</span></span>  
  
 <span data-ttu-id="1c9f2-152">**Tipo de rastreo actual o último**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-152">**Type Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="1c9f2-153">Muestra el tipo al que pertenece el rastreo actual o el más reciente: Completo, Incremental, Actualización o Autopropagación.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-153">Displays the type of the current or most recent crawl: Full, Incremental, Update, or Auto Propagation.</span></span>  
  
 <span data-ttu-id="1c9f2-154">**Nombre de índice único**</span><span class="sxs-lookup"><span data-stu-id="1c9f2-154">**Unique Index Name**</span></span>  
 <span data-ttu-id="1c9f2-155">Muestra una lista con todos los nombres de las columnas de esta base de datos que tienen índices únicos de una sola columna.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-155">Displays a list of all of the names of columns in this database that have unique single-column indexes.</span></span> <span data-ttu-id="1c9f2-156">Estas columnas se pueden utilizar para crear un índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-156">These columns can be used to create a full-text index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c9f2-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c9f2-157">See Also</span></span>  
 <span data-ttu-id="1c9f2-158">[Usar el Asistente para indización de texto completo](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="1c9f2-158">[Use the Full-Text Indexing Wizard](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span></span>  
 [<span data-ttu-id="1c9f2-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1c9f2-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
  
