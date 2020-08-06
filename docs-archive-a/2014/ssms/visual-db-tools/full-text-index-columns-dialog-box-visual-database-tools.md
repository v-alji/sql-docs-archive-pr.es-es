---
title: Columnas de índice de texto completo (cuadro de diálogo, Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextcolumn
ms.assetid: a6f41c5c-d950-4d64-9e42-d062925917b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f1cd2c94739a13e1820d8c05b338abd91d8a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750429"
---
# <a name="full-text-index-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="17207-102">Columnas de índice de texto completo (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="17207-102">Full-Text Index Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="17207-103">En este cuadro de diálogo se enumeran las columnas que participan en el índice de texto completo de la tabla abierta en el Diseñador tablas.</span><span class="sxs-lookup"><span data-stu-id="17207-103">This dialog box lists the columns participating in the full-text index for the table open in Table Designer.</span></span> <span data-ttu-id="17207-104">Para acceder a este cuadro de diálogo, haga clic con el botón derecho en la tabla en el Diseñador de tablas, seleccione **Índice de texto completo** y, en el cuadro de diálogo **Índice de texto completo**, haga clic en el índice con columnas que quiera ver o editar, haga clic en el campo **Columnas** de la cuadrícula situada a la derecha y haga clic en los puntos suspensivos ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="17207-104">To access this dialog box, right-click the table in Table Designer, choose **Full-Text Index**, and in the **Full-Text Index** dialog box, click the index with columns you want to view or edit, click the **Columns** field in the grid to the right, and click the ellipses (**...**).</span></span>  
  
## <a name="options"></a><span data-ttu-id="17207-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="17207-105">Options</span></span>  
 <span data-ttu-id="17207-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="17207-106">**Column**</span></span>  
 <span data-ttu-id="17207-107">Muestra los nombres de las columnas que participan en el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="17207-107">Shows the names of columns participating in the full-text index.</span></span> <span data-ttu-id="17207-108">Para agregar una columna, haga clic en la primera celda vacía y elija una columna en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="17207-108">To add a column, click in the first empty cell and choose a column from the drop-down list.</span></span> <span data-ttu-id="17207-109">Solo serán accesibles las columnas con tipos de datos de imagen o basados en texto.</span><span class="sxs-lookup"><span data-stu-id="17207-109">Only columns with either text-based or image data types will be accessible.</span></span>  
  
 <span data-ttu-id="17207-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="17207-110">**Data Type**</span></span>  
 <span data-ttu-id="17207-111">Muestra el tipo de datos de cada columna.</span><span class="sxs-lookup"><span data-stu-id="17207-111">Shows the data type for each column.</span></span> <span data-ttu-id="17207-112">Se trata de una propiedad de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="17207-112">This is a read-only property.</span></span> <span data-ttu-id="17207-113">Para cambiar un tipo de datos, abra la tabla en el Diseñador de tablas, haga clic en la columna y edite el tipo de datos en la pestaña **Propiedades de columna** .</span><span class="sxs-lookup"><span data-stu-id="17207-113">To change a data type, open the table in Table Designer, click the column, and edit the data type in the **Column Properties** tab.</span></span>  
  
 <span data-ttu-id="17207-114">**Escrito por columna**</span><span class="sxs-lookup"><span data-stu-id="17207-114">**Typed by Column**</span></span>  
 <span data-ttu-id="17207-115">Solo se aplica a columnas con el tipo de datos `image`.</span><span class="sxs-lookup"><span data-stu-id="17207-115">Applies only to columns with the data type `image`.</span></span> <span data-ttu-id="17207-116">Proporciona una lista desplegable en la que se puede elegir qué otras columnas representan el tipo de datos de esta columna.</span><span class="sxs-lookup"><span data-stu-id="17207-116">Provides a drop-down list from which you can choose which of the other columns represent the data type of this column.</span></span> <span data-ttu-id="17207-117">Si esta columna no es del tipo de datos `image`, el valor será Ninguno.</span><span class="sxs-lookup"><span data-stu-id="17207-117">If this column is not of the `image` data type the value will be None.</span></span>  
  
 <span data-ttu-id="17207-118">Las columnas con el tipo de datos `image` pueden contener archivos de Microsoft Office (.doc, .xls y .ppt), de texto (.txt) y HTML (.htm), y al establecer el tipo de datos de dicha columna en image, se permite la búsqueda de texto completo en el contenido de los archivos.</span><span class="sxs-lookup"><span data-stu-id="17207-118">Columns with the data type `image` can contain Microsoft Office files (.doc, .xls, and .ppt files), text files (.txt files), and HTML files (.htm files), and setting the data type of that column to image allows the full-text search to search the contents of the files.</span></span>  
  
 <span data-ttu-id="17207-119">**Lenguaje**</span><span class="sxs-lookup"><span data-stu-id="17207-119">**Language**</span></span>  
 <span data-ttu-id="17207-120">Muestra los idiomas disponibles.</span><span class="sxs-lookup"><span data-stu-id="17207-120">Lists available languages.</span></span> <span data-ttu-id="17207-121">En la lista desplegable, elija el idioma en el que están los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="17207-121">Choose the language from the drop-down list appropriate for your column data.</span></span> <span data-ttu-id="17207-122">Por ejemplo, si utiliza un sistema operativo en inglés, pero desea indizar una columna que contiene texto en alemán, elija el alemán en la lista desplegable para mejorar el rendimiento del índice.</span><span class="sxs-lookup"><span data-stu-id="17207-122">For example, if you are using an English operating system, but you want to index a column that contains German text, choose German from the drop-down list to improve the index's performance.</span></span>  
  
 <span data-ttu-id="17207-123">**Semántica estadística**</span><span class="sxs-lookup"><span data-stu-id="17207-123">**Statistical Semantics**</span></span>  
 <span data-ttu-id="17207-124">Seleccione si desea habilitar la indización semántica para la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="17207-124">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="17207-125">Para obtener más información, vea [Búsqueda semántica &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="17207-125">For more information, see [Semantic Search &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span></span>  
  
 <span data-ttu-id="17207-126">Si selecciona **Idioma** antes de seleccionar **Semántica estadística**y el idioma seleccionado no tiene un modelo semántico asociado, la casilla **Semántica estadística** está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="17207-126">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="17207-127">Si selecciona **Semántica estadística** antes de seleccionar **Idioma**, los idiomas disponibles en el cuadro combinado desplegable estarán limitados a aquellos para los que exista un modelo de idioma semántico.</span><span class="sxs-lookup"><span data-stu-id="17207-127">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17207-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17207-128">See Also</span></span>  
 [<span data-ttu-id="17207-129">Cuadro de diálogo Índice de texto completo &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="17207-129">Full-Text Index Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
