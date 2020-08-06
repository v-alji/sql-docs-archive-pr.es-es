---
title: Resultados de opciones de consulta (página cuadrícula) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.grid.f1
ms.assetid: 764bf435-3aab-4c62-b4e0-64fe020a5a95
author: rothja
ms.author: jroth
ms.openlocfilehash: bf300dd5071128b0259230ae788a27595bd8d29e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676158"
---
# <a name="query-options-results-grid-page"></a><span data-ttu-id="28d6a-102">Resultados de Opciones de consulta (página Cuadrícula)</span><span class="sxs-lookup"><span data-stu-id="28d6a-102">Query Options Results (Grid Page)</span></span>
  <span data-ttu-id="28d6a-103">Utilice esta página para especificar las opciones de visualización de un conjunto de resultados de consulta en formato de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="28d6a-103">Use this page to specify the options for displaying a query result set in grid format.</span></span>  
  
## <a name="options"></a><span data-ttu-id="28d6a-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="28d6a-104">Options</span></span>  
 <span data-ttu-id="28d6a-105">**Incluir la consulta en el conjunto de resultados**</span><span class="sxs-lookup"><span data-stu-id="28d6a-105">**Include the query in the result set**</span></span>  
 <span data-ttu-id="28d6a-106">Devuelve el texto de la consulta como parte del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="28d6a-106">Returns the text of the query as part of the result set.</span></span>  
  
 <span data-ttu-id="28d6a-107">**Incluir encabezados de columna al copiar o guardar los resultados**</span><span class="sxs-lookup"><span data-stu-id="28d6a-107">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="28d6a-108">Incluye los encabezados de columna (títulos) cuando los resultados se copian en el portapapeles o se guardan en un archivo.</span><span class="sxs-lookup"><span data-stu-id="28d6a-108">Include column headers (titles) when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="28d6a-109">Si desea que los resultados guardados o copiados incluyan solo los datos y no los encabezados de columna, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="28d6a-109">Clear this check box if you do not want saved or copied result data to have only the data, and not the column headings.</span></span>  
  
 <span data-ttu-id="28d6a-110">**Descartar resultados tras la ejecución**</span><span class="sxs-lookup"><span data-stu-id="28d6a-110">**Discard results after execution**</span></span>  
 <span data-ttu-id="28d6a-111">Si descarta los resultados de la consulta después de que la pantalla los reciba, liberará memoria.</span><span class="sxs-lookup"><span data-stu-id="28d6a-111">Free memory by discarding the query results after the screen display has received them.</span></span>  
  
 <span data-ttu-id="28d6a-112">**Mostrar resultados en otra pestaña**</span><span class="sxs-lookup"><span data-stu-id="28d6a-112">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="28d6a-113">Muestra el conjunto de resultados en una nueva ventana de documento, en lugar de mostrarlos en la parte inferior de la ventana del documento de consulta.</span><span class="sxs-lookup"><span data-stu-id="28d6a-113">Display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="28d6a-114">**Cambiar a la pestaña de resultados tras ejecutar la consulta**</span><span class="sxs-lookup"><span data-stu-id="28d6a-114">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="28d6a-115">Establece el foco de la pantalla automáticamente en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="28d6a-115">Automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="28d6a-116">**Número máximo de caracteres recuperados**</span><span class="sxs-lookup"><span data-stu-id="28d6a-116">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="28d6a-117">**Datos no XML**:</span><span class="sxs-lookup"><span data-stu-id="28d6a-117">**Non XML data**:</span></span>  
  
 <span data-ttu-id="28d6a-118">Especifique un número entre 1 y 65535 para definir el número máximo de caracteres que aparecerán en cada celda.</span><span class="sxs-lookup"><span data-stu-id="28d6a-118">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28d6a-119">La especificación de un número alto puede provocar que los datos del conjunto de resultados aparezcan truncados.</span><span class="sxs-lookup"><span data-stu-id="28d6a-119">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="28d6a-120">El número máximo de caracteres que se muestra en cada celda depende del tamaño de la fuente.</span><span class="sxs-lookup"><span data-stu-id="28d6a-120">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="28d6a-121">Cuando se devuelven conjuntos de resultados grandes, un valor elevado en esta casilla puede provocar que [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] no disponga de suficiente memoria y el rendimiento del sistema se vea afectado.</span><span class="sxs-lookup"><span data-stu-id="28d6a-121">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="28d6a-122">**Datos XML**:</span><span class="sxs-lookup"><span data-stu-id="28d6a-122">**XML data**:</span></span>  
  
 <span data-ttu-id="28d6a-123">Seleccione **1 MB**, **2 MB**o **5 MB**.</span><span class="sxs-lookup"><span data-stu-id="28d6a-123">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="28d6a-124">Seleccione **Ilimitados** para recuperar todos los caracteres.</span><span class="sxs-lookup"><span data-stu-id="28d6a-124">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="28d6a-125">**Valores predeterminados**</span><span class="sxs-lookup"><span data-stu-id="28d6a-125">**Reset to Default**</span></span>  
 <span data-ttu-id="28d6a-126">Restablece todos los valores de esta página a los valores predeterminados originales.</span><span class="sxs-lookup"><span data-stu-id="28d6a-126">Resets all values on this page to the original default values.</span></span>  
  
  
