---
title: Usar el Asistente para indización de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextindexingwizard.selecttablecolumns.f1
- sql12.swb.fulltextindexingwizard.welcome.f1
- sql12.swb.fulltextindexingwizard.selectacatalog.f1
- sql12.swb.fulltextindexingwizard.progress.f1
- sql12.swb.fulltextindexingwizard.selectorcreatepopschedules.f1
- sql12.swb.fulltextindexingwizard.selectatableorview.f1
- sql12.swb.fulltextindexingwizard.selectchangetracking.f1
- sql12.swb.fulltextindexingwizard.selectanindex.f1
- sql12.swb.fulltextindexingwizard.summary.f1
helpviewer_keywords:
- Full-Text Indexing Wizard
- full-text search [SQL Server], Full-Text Indexing Wizard
ms.assetid: 3e9d9605-6525-4781-9168-fdaa06db3459
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ef8a23c4d85cbe47bf6bdb47eb3f45723f1559d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745168"
---
# <a name="use-the-full-text-indexing-wizard"></a><span data-ttu-id="247ff-102">Usar el Asistente para indización de texto completo</span><span class="sxs-lookup"><span data-stu-id="247ff-102">Use the Full-Text Indexing Wizard</span></span>
  <span data-ttu-id="247ff-103">El Asistente para indización de texto completo le guía por una serie de pasos diseñados para ayudarle a crear un índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-103">The Full-Text Indexing Wizard walks you through a series of steps designed to help you create a full-text index.</span></span>  
  
#### <a name="to-use-the-full-text-indexing-wizard"></a><span data-ttu-id="247ff-104">Para usar el Asistente para indización de texto completo</span><span class="sxs-lookup"><span data-stu-id="247ff-104">To use the Full-Text Indexing wizard</span></span>  
  
1.  <span data-ttu-id="247ff-105">En el Explorador de objetos, haga clic con el botón derecho en la tabla en la que quiere crear un índice de texto completo, seleccione **Índice de texto completo**y, luego, haga clic en **Definir índice de texto completo**.</span><span class="sxs-lookup"><span data-stu-id="247ff-105">In Object Explorer, right-click the table on which you want to create a full-text index, point to **Full-Text index**, and then click **Define Full-Text Index**.</span></span>  
  
     <span data-ttu-id="247ff-106">**Índice único**</span><span class="sxs-lookup"><span data-stu-id="247ff-106">**Unique Index**</span></span>  
     <span data-ttu-id="247ff-107">Seleccione un índice de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="247ff-107">Select an index from the drop down list.</span></span> <span data-ttu-id="247ff-108">El índice deberá ser un índice de columna de una sola clave, único y que no admita valores NULL.</span><span class="sxs-lookup"><span data-stu-id="247ff-108">The index must be a single-key-column, unique, non-nullable index.</span></span> <span data-ttu-id="247ff-109">Seleccione el índice de clave única más pequeño para la clave única de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-109">Select the smallest unique key index for the full-text unique key.</span></span> <span data-ttu-id="247ff-110">Para obtener mejores resultados, se recomienda utilizar un índice clúster.</span><span class="sxs-lookup"><span data-stu-id="247ff-110">For best performance, a clustered index is recommended.</span></span>  
  
     <span data-ttu-id="247ff-111">**Columnas disponibles**</span><span class="sxs-lookup"><span data-stu-id="247ff-111">**Available Columns**</span></span>  
     <span data-ttu-id="247ff-112">Para incluir una columna en el índice, active la casilla situada junto al nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="247ff-112">To include a column in the index, select the check box next to the column name.</span></span> <span data-ttu-id="247ff-113">Las columnas que no son aptas para la indización de texto completo aparecen en gris con las casillas deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="247ff-113">Columns that are not eligible for full-text indexing appear in grey with their check boxes disabled.</span></span>  
  
     <span data-ttu-id="247ff-114">**Idioma del separador de palabras**</span><span class="sxs-lookup"><span data-stu-id="247ff-114">**Language for Word Breaker**</span></span>  
     <span data-ttu-id="247ff-115">Seleccione un idioma en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="247ff-115">Select a language from the drop-down list.</span></span> <span data-ttu-id="247ff-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizará esta opción para identificar los separadores de palabras correctos para el índice.</span><span class="sxs-lookup"><span data-stu-id="247ff-116">This choice will be used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to identify the correct word breakers for the index.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="247ff-117">usa separadores de palabras para identificar límites de palabras en los datos indexados de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-117">uses word breakers to identify word boundaries in the full-text indexed data.</span></span>  
  
     <span data-ttu-id="247ff-118">**Columna de tipo**</span><span class="sxs-lookup"><span data-stu-id="247ff-118">**Type Column**</span></span>  
     <span data-ttu-id="247ff-119">Seleccione el nombre de la columna que incluye el tipo de documento de la columna que se va a incluir en el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-119">Select the name of the column that holds the document type of column being full-text indexed.</span></span>  
  
     <span data-ttu-id="247ff-120">La **columna tipo** solo se habilita cuando la columna mencionada en la columna **columnas disponibles** es del tipo `varbinary(max)` o `image` .</span><span class="sxs-lookup"><span data-stu-id="247ff-120">The  **Type Column** is only enabled when the column named in the **Available Columns** column is of type `varbinary(max)` or `image`.</span></span>  
  
     <span data-ttu-id="247ff-121">**Semántica estadística**</span><span class="sxs-lookup"><span data-stu-id="247ff-121">**Statistical Semantics**</span></span>  
     <span data-ttu-id="247ff-122">Seleccione si desea habilitar la indización semántica para la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="247ff-122">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="247ff-123">Para obtener más información, vea [Búsqueda semántica &#40;SQL Server&#41;](semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="247ff-123">For more information, see [Semantic Search &#40;SQL Server&#41;](semantic-search-sql-server.md).</span></span>  
  
     <span data-ttu-id="247ff-124">Si selecciona **Idioma** antes de seleccionar **Semántica estadística**y el idioma seleccionado no tiene un modelo semántico asociado, la casilla **Semántica estadística** está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="247ff-124">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="247ff-125">Si selecciona **Semántica estadística** antes de seleccionar **Idioma**, los idiomas disponibles en el cuadro combinado desplegable estarán limitados a aquellos para los que exista un modelo de idioma semántico.</span><span class="sxs-lookup"><span data-stu-id="247ff-125">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
2.  <span data-ttu-id="247ff-126">Seleccione las opciones de seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="247ff-126">Select the change tracking options.</span></span>  
  
     <span data-ttu-id="247ff-127">**Automáticamente**</span><span class="sxs-lookup"><span data-stu-id="247ff-127">**Automatically**</span></span>  
     <span data-ttu-id="247ff-128">Seleccione este botón de opción para que el índice de texto completo se actualice automáticamente cuando se produzcan cambios en los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="247ff-128">Select this radio button to have the full-text index updated automatically as changes occur to the underlying data.</span></span>  
  
     <span data-ttu-id="247ff-129">**Manualmente**</span><span class="sxs-lookup"><span data-stu-id="247ff-129">**Manually**</span></span>  
     <span data-ttu-id="247ff-130">Seleccione este botón de opción si no desea que el índice de texto completo se actualice automáticamente cuando se produzcan cambios en los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="247ff-130">Select this radio button if you do not want the full-text index to be updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="247ff-131">Los cambios en los datos se mantienen;</span><span class="sxs-lookup"><span data-stu-id="247ff-131">Changes to the underlying data are maintained.</span></span> <span data-ttu-id="247ff-132">sin embargo, para aplicarlos al índice de texto completo es necesario iniciar o programar este proceso manualmente.</span><span class="sxs-lookup"><span data-stu-id="247ff-132">However, to apply the changes to the full-text index you must start or schedule this process manually.</span></span>  
  
     <span data-ttu-id="247ff-133">**No realizar seguimiento de cambios**</span><span class="sxs-lookup"><span data-stu-id="247ff-133">**Do not track changes**</span></span>  
     <span data-ttu-id="247ff-134">Seleccione este botón de opción si no desea que el índice de texto completo se actualice con los cambios en los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="247ff-134">Select this radio button if you do not want the full-text index to be updated with changes to the underlying data.</span></span>  
  
     <span data-ttu-id="247ff-135">**Iniciar llenado completo al crear el índice**</span><span class="sxs-lookup"><span data-stu-id="247ff-135">**Start full population when index is created**</span></span>  
     <span data-ttu-id="247ff-136">Seleccione este botón de opción para iniciar un llenado completo tras la finalización correcta de este asistente.</span><span class="sxs-lookup"><span data-stu-id="247ff-136">Select this radio button to kick off a full population at the successful completion of this wizard.</span></span> <span data-ttu-id="247ff-137">De esta forma, se creará la estructura del índice de texto completo en el catálogo y se llenará con los datos indizados de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-137">This will consist of creating the full-text index structure in the catalog and populating it with full-text indexed data.</span></span>  
  
3.  <span data-ttu-id="247ff-138">Seleccione el catálogo, el grupo de archivos de índice y la lista de palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="247ff-138">Select the catalog, index filegroup and stoplist.</span></span>  
  
     <span data-ttu-id="247ff-139">**Seleccionar catálogo de texto completo**</span><span class="sxs-lookup"><span data-stu-id="247ff-139">**Select full-text catalog**</span></span>  
     <span data-ttu-id="247ff-140">Seleccione un catálogo de texto completo de la lista.</span><span class="sxs-lookup"><span data-stu-id="247ff-140">Select a full-text catalog from the list.</span></span> <span data-ttu-id="247ff-141">El catálogo predeterminado de la base de datos será el elemento seleccionado de manera predeterminada en la lista.</span><span class="sxs-lookup"><span data-stu-id="247ff-141">The default catalog for the database will be the selected item by default in the list.</span></span> <span data-ttu-id="247ff-142">Si no hay catálogos disponibles, la lista estará deshabilitada y la casilla **Crear un nuevo catálogo** estará activada y deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="247ff-142">If no catalogs are available, the list will be disabled, and the **Create a new catalog** checkbox will be checked and disabled.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="247ff-143">**Creación de un catálogo**</span><span class="sxs-lookup"><span data-stu-id="247ff-143">**Create a new catalog**</span></span>|<span data-ttu-id="247ff-144">Seleccione esta opción para crear un nuevo catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-144">Select to create a new full-text catalog.</span></span>|  
  
     <span data-ttu-id="247ff-145">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="247ff-145">**Name**</span></span>  
     <span data-ttu-id="247ff-146">Escriba un nombre para el nuevo catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-146">Enter a name for the new full-text catalog.</span></span>  
  
     <span data-ttu-id="247ff-147">**Establecer como catálogo predeterminado**</span><span class="sxs-lookup"><span data-stu-id="247ff-147">**Set as default catalog**</span></span>  
     <span data-ttu-id="247ff-148">Seleccione esta opción para hacer que el catálogo sea el valor predeterminado para esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="247ff-148">Select to make the catalog the default for this database.</span></span>  
  
     <span data-ttu-id="247ff-149">**Distinción de acentos**</span><span class="sxs-lookup"><span data-stu-id="247ff-149">**Accent sensitivity**</span></span>  
     <span data-ttu-id="247ff-150">Especifique si el nuevo catálogo distinguirá acentos.</span><span class="sxs-lookup"><span data-stu-id="247ff-150">Specify whether the new catalog will be accent-sensitive or accent-insensitive.</span></span> <span data-ttu-id="247ff-151">Si la base de datos distingue acentos, la opción **Con distinción** estará seleccionada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="247ff-151">If the database is accent-sensitive, **Sensitive** will be selected by default.</span></span>  
  
     <span data-ttu-id="247ff-152">**Seleccionar grupo de archivos de índice**</span><span class="sxs-lookup"><span data-stu-id="247ff-152">**Select index filegroup**</span></span>  
     <span data-ttu-id="247ff-153">Especifique el grupo de archivos en el que crear el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-153">Specify the filegroup on which to create the full-text index.</span></span>  
  
     <span data-ttu-id="247ff-154">Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="247ff-154">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="247ff-155">Value</span><span class="sxs-lookup"><span data-stu-id="247ff-155">Value</span></span>|<span data-ttu-id="247ff-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="247ff-156">Description</span></span>|  
    |-----------|-----------------|  
    |**\<default>**|<span data-ttu-id="247ff-157">Si la tabla o la vista no tienen particiones, seleccione este valor para usar el mismo grupo de archivos que la tabla o vista subyacente.</span><span class="sxs-lookup"><span data-stu-id="247ff-157">If the table or view is not partitioned, select to use the same filegroup as the underlying table or view.</span></span> <span data-ttu-id="247ff-158">Si la tabla o la vista tienen particiones, se usa el grupo de archivos principal.</span><span class="sxs-lookup"><span data-stu-id="247ff-158">If the table or view is partitioned, the primary filegroup is used.</span></span>|  
    |<span data-ttu-id="247ff-159">**PRINCIPAL**</span><span class="sxs-lookup"><span data-stu-id="247ff-159">**PRIMARY**</span></span>|<span data-ttu-id="247ff-160">Seleccione este valor para usar el grupo de archivos principal para el nuevo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-160">Select to use the primary filegroup for the new full-text index.</span></span>|  
    |<span data-ttu-id="247ff-161">*grupo de archivos predeterminado especificado por el usuario*</span><span class="sxs-lookup"><span data-stu-id="247ff-161">*user-specified default filegroup*</span></span>|<span data-ttu-id="247ff-162">Si existe una lista de palabras irrelevantes predeterminada definida por el usuario, seleccione su nombre en la lista con el fin de utilizar ese grupo de archivos para el nuevo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-162">If a user-defined default stoplist exists, select its name from the list to use that filegroup for the new full-text index.</span></span>|  
  
     <span data-ttu-id="247ff-163">**Seleccionar lista de palabras irrelevantes de texto completo**</span><span class="sxs-lookup"><span data-stu-id="247ff-163">**Select full-text stoplist**</span></span>  
     <span data-ttu-id="247ff-164">Especifique una lista de palabras irrelevantes para usarla en el índice de texto completo, o deshabilite el uso de la lista de palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="247ff-164">Specify a stoplist to use for the full-text index, or disable stoplist use.</span></span>  
  
     <span data-ttu-id="247ff-165">En [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] y versiones posteriores, las palabras irrelevantes se administran en bases de datos que usan objetos denominados listas de palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="247ff-165">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="247ff-166">Una *lista de palabras irrelevantes* es una lista de palabras que, cuando se asocia a un índice de texto completo, se aplica a las consultas de texto completo en ese índice.</span><span class="sxs-lookup"><span data-stu-id="247ff-166">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span> <span data-ttu-id="247ff-167">Para obtener más información, vea [Configurar y administrar palabras irrelevantes y listas de palabras irrelevantes para la búsqueda de texto completo](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="247ff-167">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span></span>  
  
     <span data-ttu-id="247ff-168">Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="247ff-168">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="247ff-169">Value</span><span class="sxs-lookup"><span data-stu-id="247ff-169">Value</span></span>|<span data-ttu-id="247ff-170">Descripción</span><span class="sxs-lookup"><span data-stu-id="247ff-170">Description</span></span>|  
    |-----------|-----------------|  
    |**\<system>**|<span data-ttu-id="247ff-171">Seleccione este valor para utilizar la lista de palabras irrelevantes del sistema en el nuevo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-171">Select to use the system stoplist on the new full-text index.</span></span> <span data-ttu-id="247ff-172">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="247ff-172">This is the default</span></span>|  
    |**\<off>**|<span data-ttu-id="247ff-173">Seleccione este valor para deshabilitar las listas de palabras irrelevantes para el nuevo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-173">Select to disable stoplists for the new full-text index.</span></span>|  
    |<span data-ttu-id="247ff-174">*user-defined-stoplist-name*</span><span class="sxs-lookup"><span data-stu-id="247ff-174">*user-defined-stoplist-name*</span></span>|<span data-ttu-id="247ff-175">La lista muestra el nombre de cada lista de palabras irrelevantes definida por el usuario, si hay alguna, que se haya creado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="247ff-175">The list displays the name of each user-defined stoplist, if any, that has been created on the database.</span></span> <span data-ttu-id="247ff-176">Seleccione la lista de palabras irrelevantes definida por el usuario que desee para utilizarla para el nuevo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-176">Select any user-defined stoplist to use for the new full-text index.</span></span>|  
  
4.  <span data-ttu-id="247ff-177">Opcionalmente, defina la programación de rellenado.</span><span class="sxs-lookup"><span data-stu-id="247ff-177">Optionally, define the population schedule.</span></span> <span data-ttu-id="247ff-178">Las operaciones de indización comenzarán inmediatamente, a menos que se hayan programado para que se ejecuten posteriormente.</span><span class="sxs-lookup"><span data-stu-id="247ff-178">Indexing operations will begin immediately unless they have been scheduled for future execution.</span></span> <span data-ttu-id="247ff-179">Las programaciones se crearán inmediatamente, aunque no se ejecuten hasta la hora programada.</span><span class="sxs-lookup"><span data-stu-id="247ff-179">Schedules will be created immediately, although they will not run until their scheduled time.</span></span>  
  
     <span data-ttu-id="247ff-180">**Nueva programación de tabla**</span><span class="sxs-lookup"><span data-stu-id="247ff-180">**New Table Schedule**</span></span>  
     <span data-ttu-id="247ff-181">Permite definir una programación de llenado para una tabla.</span><span class="sxs-lookup"><span data-stu-id="247ff-181">Define a population schedule for a table.</span></span>  
  
     <span data-ttu-id="247ff-182">**Nueva programación de catálogo**</span><span class="sxs-lookup"><span data-stu-id="247ff-182">**New Catalog Schedule**</span></span>  
     <span data-ttu-id="247ff-183">Permite definir una programación de llenado para un catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-183">Define a population schedule for a full-text catalog.</span></span>  
  
     <span data-ttu-id="247ff-184">**Edición**</span><span class="sxs-lookup"><span data-stu-id="247ff-184">**Edit**</span></span>  
     <span data-ttu-id="247ff-185">Permite editar una programación.</span><span class="sxs-lookup"><span data-stu-id="247ff-185">Edit a schedule.</span></span>  
  
     <span data-ttu-id="247ff-186">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="247ff-186">**Delete**</span></span>  
     <span data-ttu-id="247ff-187">Permite eliminar una programación.</span><span class="sxs-lookup"><span data-stu-id="247ff-187">Delete a schedule.</span></span>  
  
5.  <span data-ttu-id="247ff-188">Vea o controle el progreso del Asistente para indización de texto completo.</span><span class="sxs-lookup"><span data-stu-id="247ff-188">View or control the progress of the Full-Text Indexing Wizard.</span></span>  
  
     <span data-ttu-id="247ff-189">**Detención**</span><span class="sxs-lookup"><span data-stu-id="247ff-189">**Stop**</span></span>  
     <span data-ttu-id="247ff-190">Interrumpe la operación actual e impide que el asistente lleve a cabo operaciones de texto completo posteriores durante esta sesión.</span><span class="sxs-lookup"><span data-stu-id="247ff-190">Interrupts the current operation and prevents subsequent full-text operations from being performed by the wizard during this session.</span></span>  
  
     <span data-ttu-id="247ff-191">**Report**</span><span class="sxs-lookup"><span data-stu-id="247ff-191">**Report**</span></span>  
     <span data-ttu-id="247ff-192">Cuando finalice la ejecución de todas las operaciones, haga clic en este botón para obtener acceso a un informe sobre las operaciones efectuadas.</span><span class="sxs-lookup"><span data-stu-id="247ff-192">When all of the operations have finished executing, click this button to access a report on the operations performed.</span></span> <span data-ttu-id="247ff-193">Puede ver el informe, imprimirlo en un archivo, copiarlo al portapapeles o enviarlo por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="247ff-193">You can view the report, print it to a file, copy it to the clipboard, or e-mail the report.</span></span>  
  
  
