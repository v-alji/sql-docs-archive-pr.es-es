---
title: Propiedades del índice de texto completo (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.columns.f1
ms.assetid: 75e52edb-0d07-4393-9345-8b5af4561e35
author: rothja
ms.author: jroth
ms.openlocfilehash: f947af04463948ef551c6df866d5a306c248c6b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677838"
---
# <a name="full-text-index-properties-columns-page"></a><span data-ttu-id="53e1f-102">Propiedades del índice de texto completo (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="53e1f-102">Full-Text Index Properties (Columns Page)</span></span>
  <span data-ttu-id="53e1f-103">**Para ver o cambiar las propiedades de un índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="53e1f-103">**To view or change the properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="53e1f-104">Administrar índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="53e1f-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="53e1f-105">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="53e1f-105">UI element list</span></span>  
 <span data-ttu-id="53e1f-106">**Índice único**</span><span class="sxs-lookup"><span data-stu-id="53e1f-106">**Unique index**</span></span>  
 <span data-ttu-id="53e1f-107">Seleccione un índice de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="53e1f-107">Select an index from the drop down list.</span></span> <span data-ttu-id="53e1f-108">El índice deberá ser un índice de columna de una sola clave, único y que no admita valores NULL.</span><span class="sxs-lookup"><span data-stu-id="53e1f-108">The index must be a single-key-column, unique, non-nullable index.</span></span>  
  
 <span data-ttu-id="53e1f-109">**Seleccione las columnas coincidentes que tendrán índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="53e1f-109">**Select the eligible columns that will be full-text indexed**</span></span>  
 <span data-ttu-id="53e1f-110">La cuadrícula muestra las columnas de la tabla que están disponibles para este índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="53e1f-110">The grid displays the table columns that are available for this full-text index.</span></span> <span data-ttu-id="53e1f-111">Se activan las columnas que tienen indización de texto completo en este momento.</span><span class="sxs-lookup"><span data-stu-id="53e1f-111">Columns that are currently full-text indexed are checked.</span></span> <span data-ttu-id="53e1f-112">Opcionalmente, puede activar más columnas que desee que se indicen con texto completo.</span><span class="sxs-lookup"><span data-stu-id="53e1f-112">Optionally, you can check additional columns that you want to be full-text indexed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="53e1f-113">Asegúrese de que al menos una columna está activada antes de hacer clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="53e1f-113">Ensure that at least one column is checked before you click OK.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53e1f-114">**Columnas disponibles**</span><span class="sxs-lookup"><span data-stu-id="53e1f-114">**Available Columns**</span></span>|<span data-ttu-id="53e1f-115">Nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="53e1f-115">The column name.</span></span>|  
|<span data-ttu-id="53e1f-116">**Idioma del separador de palabras**</span><span class="sxs-lookup"><span data-stu-id="53e1f-116">**Language for Word Breaker**</span></span>|<span data-ttu-id="53e1f-117">El idioma cuyos separadores de palabras y lematizadores realizan un análisis lingüístico de todos los datos indizados de texto completo.</span><span class="sxs-lookup"><span data-stu-id="53e1f-117">The language whose word breakers and stemmers perform linguistic analysis on all full-text indexed data.</span></span><br /><br /> <span data-ttu-id="53e1f-118">Para obtener más información, vea [configurar y administrar separadores de palabras y lematizadores para la búsqueda](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) y [elegir un idioma al crear un índice de texto completo](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span><span class="sxs-lookup"><span data-stu-id="53e1f-118">For more information, see [Configure and Manage Word Breakers and Stemmers for Search](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) and [Choose a Language When Creating a Full-Text Index](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span></span>|  
|<span data-ttu-id="53e1f-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="53e1f-119">**Type**</span></span>|<span data-ttu-id="53e1f-120">Nombre de la columna de la tabla que contiene el tipo de documento de la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="53e1f-120">The name of the table column that holds the document type of the selected column.</span></span> <span data-ttu-id="53e1f-121">Se trata de una propiedad de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="53e1f-121">This is a read-only property.</span></span>|  
|<span data-ttu-id="53e1f-122">**Semántica estadística**</span><span class="sxs-lookup"><span data-stu-id="53e1f-122">**Statistical Semantics**</span></span>|<span data-ttu-id="53e1f-123">Seleccione si desea habilitar la indización semántica para la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="53e1f-123">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="53e1f-124">Para obtener más información, vea [Búsqueda semántica &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="53e1f-124">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="53e1f-125">Si selecciona **Idioma** antes de seleccionar **Semántica estadística**y el idioma seleccionado no tiene un modelo semántico asociado, la casilla **Semántica estadística** está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="53e1f-125">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="53e1f-126">Si selecciona **Semántica estadística** antes de seleccionar **Idioma**, los idiomas disponibles en el cuadro combinado desplegable estarán limitados a aquellos para los que exista un modelo de idioma semántico.</span><span class="sxs-lookup"><span data-stu-id="53e1f-126">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53e1f-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53e1f-127">See Also</span></span>  
 [<span data-ttu-id="53e1f-128">Rellenar índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="53e1f-128">Populate Full-Text Indexes</span></span>](../relational-databases/search/populate-full-text-indexes.md)  
  
  
