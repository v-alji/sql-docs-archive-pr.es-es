---
title: Propiedades del catálogo de texto completo (página tablas y vistas) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.tablesviews.f1
ms.assetid: 2d45fcd2-0f0f-4167-9027-316d6696c106
author: rothja
ms.author: jroth
ms.openlocfilehash: eb4d968af6c550d19fbb8934b5d76a1bd63cb8da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749427"
---
# <a name="full-text-catalog-properties-tables-and-views-page"></a><span data-ttu-id="8a480-102">Propiedades del catálogo de texto completo (Tablas/página Vistas)</span><span class="sxs-lookup"><span data-stu-id="8a480-102">Full-Text Catalog Properties (Tables and Views Page)</span></span>
  <span data-ttu-id="8a480-103">Utilice esta página de diálogo para ver o modificar las tablas y vistas asignadas al catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8a480-103">Use this dialog page to view or modify the tables and views that are assigned to the full-text catalog.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="8a480-104">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8a480-104">UI element list</span></span>  
 <span data-ttu-id="8a480-105">**Todos los objetos de tabla o de vista que se pueden elegir en esta base de datos**</span><span class="sxs-lookup"><span data-stu-id="8a480-105">**All eligible table/view objects in this database**</span></span>  
 <span data-ttu-id="8a480-106">Muestra las tablas y vistas que disponen de un único índice definido, pero que todavía no forman parte del catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8a480-106">Lists the tables and views that have a unique index defined on them, but are not already a part of the full-text catalog.</span></span> <span data-ttu-id="8a480-107">Para seleccionar una tabla o vista y asignarla al catálogo, seleccione los elementos en el cuadro de lista y presione el botón "->".</span><span class="sxs-lookup"><span data-stu-id="8a480-107">To select a table or view and assign it to the catalog, select the items in the list box and press the "->" button.</span></span>  
  
 <span data-ttu-id="8a480-108">**Objetos de tabla o vista asignados al catálogo**</span><span class="sxs-lookup"><span data-stu-id="8a480-108">**Table/view objects assigned to the catalog**</span></span>  
 <span data-ttu-id="8a480-109">Muestra las tablas y vistas actualmente asignadas al catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="8a480-109">Lists the tables and views that are currently assigned to the full-text catalog</span></span>  
  
## <a name="selected-object-properties"></a><span data-ttu-id="8a480-110">Propiedades de los objetos seleccionados</span><span class="sxs-lookup"><span data-stu-id="8a480-110">Selected Object Properties</span></span>  
 <span data-ttu-id="8a480-111">**Propiedades de los objetos seleccionados**</span><span class="sxs-lookup"><span data-stu-id="8a480-111">**Selected object properties**</span></span>  
 <span data-ttu-id="8a480-112">Muestra las propiedades del objeto seleccionado en el cuadro de lista de objetos asignados al catálogo.</span><span class="sxs-lookup"><span data-stu-id="8a480-112">Displays the properties of the selected object in the list box of objects assigned to the catalog.</span></span>  
  
 <span data-ttu-id="8a480-113">**Índice único**</span><span class="sxs-lookup"><span data-stu-id="8a480-113">**Unique Index**</span></span>  
 <span data-ttu-id="8a480-114">Muestra los índices únicos disponibles de la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="8a480-114">Lists the available unique indexes of the table or view.</span></span>  
  
 <span data-ttu-id="8a480-115">**La tabla está habilitada para texto completo**</span><span class="sxs-lookup"><span data-stu-id="8a480-115">**Table is full-text enabled**</span></span>  
 <span data-ttu-id="8a480-116">Active esta casilla para habilitar el índice de texto completo en la tabla.</span><span class="sxs-lookup"><span data-stu-id="8a480-116">Select this check box to enable the full-text index on the table.</span></span> <span data-ttu-id="8a480-117">Desactive esta casilla para deshabilitar el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8a480-117">Clear the check box to disable the full-text index.</span></span>  
  
## <a name="eligible-columns-grid"></a><span data-ttu-id="8a480-118">Cuadrícula de columnas elegibles</span><span class="sxs-lookup"><span data-stu-id="8a480-118">Eligible Columns Grid</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a480-119">**Columnas disponibles**</span><span class="sxs-lookup"><span data-stu-id="8a480-119">**Available Columns**</span></span>|<span data-ttu-id="8a480-120">Muestra todas las columnas con indización de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8a480-120">Displays all the columns that are full-text indexed.</span></span> <span data-ttu-id="8a480-121">Active una casilla para agregar una columna al índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8a480-121">Select a check box to add a column to the full-text index.</span></span>|  
|<span data-ttu-id="8a480-122">**Idioma del separador de palabras**</span><span class="sxs-lookup"><span data-stu-id="8a480-122">**Language for Word Breaker**</span></span>|<span data-ttu-id="8a480-123">Muestra el idioma del separador de palabras.</span><span class="sxs-lookup"><span data-stu-id="8a480-123">Displays the language of the word breaker.</span></span>|  
|<span data-ttu-id="8a480-124">**Columna Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="8a480-124">**Data Type Column**</span></span>|<span data-ttu-id="8a480-125">Muestra el nombre de la columna de la tabla que contiene el tipo de documento de la columna mostrada en **columnas disponibles** si la columna es una columna de tipo `varbinary(max)` o `image` .</span><span class="sxs-lookup"><span data-stu-id="8a480-125">Lists the name of the column in the table that holds the document type of the column listed in **Available Columns** if the column is a `varbinary(max)` or `image` column.</span></span>|  
|<span data-ttu-id="8a480-126">**Semántica estadística**</span><span class="sxs-lookup"><span data-stu-id="8a480-126">**Statistical Semantics**</span></span>|<span data-ttu-id="8a480-127">Seleccione si desea habilitar la indización semántica para la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8a480-127">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="8a480-128">Para obtener más información, vea [Búsqueda semántica &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8a480-128">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="8a480-129">Si selecciona **Idioma** antes de seleccionar **Semántica estadística**y el idioma seleccionado no tiene un modelo semántico asociado, la casilla **Semántica estadística** está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="8a480-129">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="8a480-130">Si selecciona **Semántica estadística** antes de seleccionar **Idioma**, los idiomas disponibles en el cuadro combinado desplegable estarán limitados a aquellos para los que exista un modelo de idioma semántico.</span><span class="sxs-lookup"><span data-stu-id="8a480-130">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="track-changes"></a><span data-ttu-id="8a480-131">Seguimiento de cambios</span><span class="sxs-lookup"><span data-stu-id="8a480-131">Track Changes</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a480-132">**Automático**</span><span class="sxs-lookup"><span data-stu-id="8a480-132">**Automatic**</span></span>|<span data-ttu-id="8a480-133">El índice de texto completo se actualiza automáticamente cuando los datos de la tabla subyacente se modifican, se agregan o se eliminan.</span><span class="sxs-lookup"><span data-stu-id="8a480-133">The full-text index is automatically updated when the data in the underlying table is modified, added, or deleted.</span></span>|  
|<span data-ttu-id="8a480-134">**Manual**</span><span class="sxs-lookup"><span data-stu-id="8a480-134">**Manual**</span></span>|<span data-ttu-id="8a480-135">Cuando se modifican, se agregan o se eliminan datos en los datos indizados, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] realiza un seguimiento de los cambios.</span><span class="sxs-lookup"><span data-stu-id="8a480-135">When data is modified, added, or deleted in the indexed data, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tracks the changes.</span></span> <span data-ttu-id="8a480-136">Cuando está activado el seguimiento de cambios **Manual** , el índice no se actualiza automáticamente con estos cambios.</span><span class="sxs-lookup"><span data-stu-id="8a480-136">When **Manual** change tracking is in effect, the index is not automatically updated with these changes.</span></span> <span data-ttu-id="8a480-137">En su lugar, un administrador puede aplicar los cambios manualmente mediante el uso de una [instrucción ALTER fulltext index... INICIAR la instrucción UPDATE POPULATION](/sql/t-sql/statements/alter-fulltext-index-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="8a480-137">Instead, an administrator can apply the changes manually by using an [ALTER FULLTEXT INDEX ... START UPDATE POPULATION](/sql/t-sql/statements/alter-fulltext-index-transact-sql) statement.</span></span>|  
|<span data-ttu-id="8a480-138">**No realizar seguimiento de cambios**</span><span class="sxs-lookup"><span data-stu-id="8a480-138">**Do not track change**</span></span>|<span data-ttu-id="8a480-139">Con esta opción activa, no se registran los cambios realizados en los datos indizados del catálogo.</span><span class="sxs-lookup"><span data-stu-id="8a480-139">With this option in effect, changes to the indexed data in the catalog are not recorded.</span></span> <span data-ttu-id="8a480-140">Un administrador debe generar el índice utilizando FULLTEXT del ALTER INDICE con POBLACIÓN COMPLETA o la POBLACIÓN INCREMENTAL.</span><span class="sxs-lookup"><span data-stu-id="8a480-140">An administrator must build the index by using ALTER FULLTEXT INDEX with either FULL POPULATION or INCREMENTAL POPULATION.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a480-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a480-141">See Also</span></span>  
 <span data-ttu-id="8a480-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a480-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span></span>  
 <span data-ttu-id="8a480-143">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a480-143">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="8a480-144">Rellenar índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="8a480-144">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
