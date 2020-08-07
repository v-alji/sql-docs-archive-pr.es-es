---
title: Opciones (resultados de la consulta-SQL Server-resultados a la página de cuadrícula) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToGrid
ms.assetid: f88a0f5c-e800-473b-ae23-c3943de5ed63
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f9cec7e544c295420a9ae2a25e96ea9aa82030b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747161"
---
# <a name="options-query-results-sql-server-results-to-grid-page"></a><span data-ttu-id="6a353-102">Opciones (resultados de la consulta-SQL Server-resultados a la página de cuadrícula)</span><span class="sxs-lookup"><span data-stu-id="6a353-102">Options (Query Results-SQL Server-Results to Grid Page)</span></span>
  <span data-ttu-id="6a353-103">Utilice esta página para especificar las opciones de visualización de un conjunto de resultados de consulta en formato de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6a353-103">Use this page to specify the options for displaying a query result set in grid format.</span></span> <span data-ttu-id="6a353-104">Los cambios que se realicen en estas opciones solo se aplicarán a las nuevas consultas de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a353-104">Changes to these options are applied only to new [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="6a353-105">Para cambiar las opciones de las consultas actuales, haga clic en **Opciones de consulta** en el menú **consulta** o haga clic con el botón secundario en la [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ventana de consulta y seleccione **Opciones de consulta**.</span><span class="sxs-lookup"><span data-stu-id="6a353-105">To change the options for the current queries, click **Query Options** on the **Query** menu, or right-click in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window and select **Query Options**.</span></span> <span data-ttu-id="6a353-106">En la página izquierda del cuadro de diálogo **Opciones de consulta** , en **Resultados**, haga clic en **Cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="6a353-106">In the left pane of the **Query Options** dialog box, under **Results**, click **Grid**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="6a353-107">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="6a353-107">UI element list</span></span>  
 <span data-ttu-id="6a353-108">**Incluir la consulta en el conjunto de resultados**</span><span class="sxs-lookup"><span data-stu-id="6a353-108">**Include the query in the result set**</span></span>  
 <span data-ttu-id="6a353-109">Devuelve el texto de la consulta como parte de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="6a353-109">Returns the text of the query as part of the query output.</span></span>  
  
 <span data-ttu-id="6a353-110">**Incluir encabezados de columna al copiar o guardar los resultados**</span><span class="sxs-lookup"><span data-stu-id="6a353-110">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="6a353-111">Seleccione esta casilla para incluir encabezados de columna cuando los resultados se copian en el Portapapeles o se guardan en un archivo.</span><span class="sxs-lookup"><span data-stu-id="6a353-111">Select this check box to include column headers when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="6a353-112">Si desea que los resultados guardados o copiados incluyan solo los datos y no los encabezados de columna, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="6a353-112">Clear this check box if you want saved or copied result data to have only the data and not the column headings.</span></span>  
  
 <span data-ttu-id="6a353-113">**Descartar resultados tras la ejecución**</span><span class="sxs-lookup"><span data-stu-id="6a353-113">**Discard results after execution**</span></span>  
 <span data-ttu-id="6a353-114">Evita que los resultados de la consulta se muestren en el panel de revisiones.</span><span class="sxs-lookup"><span data-stu-id="6a353-114">Prevents query results from being displayed in the reviewing pane.</span></span> <span data-ttu-id="6a353-115">Dichos resultados se descartan inmediatamente tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="6a353-115">The results are discarded immediately after execution.</span></span> <span data-ttu-id="6a353-116">Especifique esta opción si desea reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="6a353-116">Specifying this option helps save memory.</span></span>  
  
 <span data-ttu-id="6a353-117">**Mostrar resultados en otra pestaña**</span><span class="sxs-lookup"><span data-stu-id="6a353-117">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="6a353-118">Seleccione esta casilla para mostrar el conjunto de resultados en una nueva pestaña y no en la parte inferior de la ventana del documento de consulta.</span><span class="sxs-lookup"><span data-stu-id="6a353-118">Select this check box to display the result set in a new tab, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="6a353-119">**Cambiar a la pestaña de resultados tras ejecutar la consulta**</span><span class="sxs-lookup"><span data-stu-id="6a353-119">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="6a353-120">Haga clic en esta opción para establecer automáticamente el enfoque de pantalla en el panel de resultados tras ejecutar una consulta.</span><span class="sxs-lookup"><span data-stu-id="6a353-120">Click to automatically set the screen focus to the results pane upon execution of a query.</span></span>  
  
 <span data-ttu-id="6a353-121">**Número máximo de caracteres recuperados**</span><span class="sxs-lookup"><span data-stu-id="6a353-121">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="6a353-122">**Datos no XML**:</span><span class="sxs-lookup"><span data-stu-id="6a353-122">**Non XML data**:</span></span>  
  
 <span data-ttu-id="6a353-123">Especifique un número entre 1 y 65535 para definir el número máximo de caracteres que aparecerán en cada celda.</span><span class="sxs-lookup"><span data-stu-id="6a353-123">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a353-124">La especificación de un número alto puede provocar que los datos del conjunto de resultados aparezcan truncados.</span><span class="sxs-lookup"><span data-stu-id="6a353-124">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="6a353-125">El número máximo de caracteres que se muestra en cada celda depende del tamaño de la fuente.</span><span class="sxs-lookup"><span data-stu-id="6a353-125">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="6a353-126">Cuando se devuelven conjuntos de resultados grandes, un valor elevado en esta casilla puede provocar que [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] no disponga de suficiente memoria y el rendimiento del sistema se vea afectado.</span><span class="sxs-lookup"><span data-stu-id="6a353-126">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="6a353-127">**Datos XML**:</span><span class="sxs-lookup"><span data-stu-id="6a353-127">**XML data**:</span></span>  
  
 <span data-ttu-id="6a353-128">Seleccione **1 MB**, **2 MB**o **5 MB**.</span><span class="sxs-lookup"><span data-stu-id="6a353-128">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="6a353-129">Seleccione **Ilimitados** para recuperar todos los caracteres.</span><span class="sxs-lookup"><span data-stu-id="6a353-129">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="6a353-130">**Valores predeterminados**</span><span class="sxs-lookup"><span data-stu-id="6a353-130">**Reset to Default**</span></span>  
 <span data-ttu-id="6a353-131">Restablece todos los valores de esta página a los valores predeterminados originales.</span><span class="sxs-lookup"><span data-stu-id="6a353-131">Resets all values on this page to the original default values.</span></span>  
  
  
