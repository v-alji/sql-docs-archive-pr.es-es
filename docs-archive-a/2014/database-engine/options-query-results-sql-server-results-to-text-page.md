---
title: 'Opciones (resultados de la consulta-SQL Server: resultados a la página de texto) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToText
ms.assetid: 2ccbdf17-e14f-42f1-a836-ca999a3432c9
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ece458e4bab9a57cb6692d4ac6dfdf2e8f4bd22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747159"
---
# <a name="options-query-results-sql-server-results-to-text-page"></a><span data-ttu-id="acc25-102">Opciones (resultados de la consulta-SQL Server-resultados a página de texto)</span><span class="sxs-lookup"><span data-stu-id="acc25-102">Options (Query Results-SQL Server-Results to Text Page)</span></span>
  <span data-ttu-id="acc25-103">Utilice esta página para especificar las opciones para mostrar el conjunto de resultados de una consulta en formato de texto.</span><span class="sxs-lookup"><span data-stu-id="acc25-103">Use this page to specify the options for displaying a query result set in text format.</span></span> <span data-ttu-id="acc25-104">Los cambios que se realicen en estas opciones solo se aplicarán a las nuevas consultas de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acc25-104">Changes to these options are applied only to new [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="acc25-105">Para cambiar las opciones de las consultas actuales, haga clic en **Opciones de consulta** en el menú **consulta** o haga clic con el botón derecho en la [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ventana de consulta y seleccione **Opciones de consulta**.</span><span class="sxs-lookup"><span data-stu-id="acc25-105">To change the options for the current queries, click **Query Options** on the **Query** menu, or right-click in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window, and select **Query Options**.</span></span> <span data-ttu-id="acc25-106">En el cuadro de diálogo **Opciones de consulta** , en **Resultados**, haga clic en **Texto**.</span><span class="sxs-lookup"><span data-stu-id="acc25-106">In the **Query Options** dialog box, under **Results**, click **Text**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="acc25-107">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="acc25-107">UI element list</span></span>  
 <span data-ttu-id="acc25-108">**Formato de salida**</span><span class="sxs-lookup"><span data-stu-id="acc25-108">**Output format**</span></span>  
 <span data-ttu-id="acc25-109">De manera predeterminada, la salida se muestra en columnas que se han creado rellenando de espacios los resultados.</span><span class="sxs-lookup"><span data-stu-id="acc25-109">By default the output is displayed in columns created by padding the results with spaces.</span></span> <span data-ttu-id="acc25-110">Otras de las opciones son el uso de comas, tabulaciones o espacios para separar las columnas.</span><span class="sxs-lookup"><span data-stu-id="acc25-110">Other options are to use commas, tabs, or spaces to separate columns.</span></span> <span data-ttu-id="acc25-111">Seleccione **Delimitador personalizado** en esta lista desplegable para especificar un carácter delimitador distinto en el cuadro de texto **Delimitador personalizado**.</span><span class="sxs-lookup"><span data-stu-id="acc25-111">Select **Custom delimiter** from this drop-down list to specify a different delimiting character in the **Custom delimiter** text box.</span></span>  
  
 <span data-ttu-id="acc25-112">**Delimitador personalizado**</span><span class="sxs-lookup"><span data-stu-id="acc25-112">**Custom delimiter**</span></span>  
 <span data-ttu-id="acc25-113">Especifique el carácter que desee para separar las columnas.</span><span class="sxs-lookup"><span data-stu-id="acc25-113">Specify the character of your choice to separate columns.</span></span> <span data-ttu-id="acc25-114">Este cuadro de texto solo estará disponible si se ha hecho clic en Delimitador personalizado en el cuadro de lista desplegable **Formato de salida**.</span><span class="sxs-lookup"><span data-stu-id="acc25-114">This text box is available only if you clicked Custom delimiter in the **Output format** drop-down list box.</span></span>  
  
 <span data-ttu-id="acc25-115">**Incluir encabezados de columna en el conjunto de resultados**</span><span class="sxs-lookup"><span data-stu-id="acc25-115">**Include column headers in the result set**</span></span>  
 <span data-ttu-id="acc25-116">Desactive esta casilla si no desea que cada columna tenga una etiqueta con un título de columna.</span><span class="sxs-lookup"><span data-stu-id="acc25-116">Clear this check box if you do not want each column labeled with a column title.</span></span>  
  
 <span data-ttu-id="acc25-117">**Incluir la consulta en el conjunto de resultados**</span><span class="sxs-lookup"><span data-stu-id="acc25-117">**Include the query in the result set**</span></span>  
 <span data-ttu-id="acc25-118">Active esta casilla para incluir el texto de la consulta que se ejecuta en el panel de resultados antes de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="acc25-118">Select this check box to include the text of the query that is running in the results pane before the results of the query.</span></span>  
  
 <span data-ttu-id="acc25-119">**Desplazarse a medida que se reciben resultados**</span><span class="sxs-lookup"><span data-stu-id="acc25-119">**Scroll as results are received**</span></span>  
 <span data-ttu-id="acc25-120">Active esta casilla para mantener el foco de visualización en los registros devueltos más recientemente al final del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="acc25-120">Select this check box to keep the display focus on the most recently returned records at the end of the results set.</span></span> <span data-ttu-id="acc25-121">Desactive esta casilla para mantener el foco de visualización en las primeras filas recibidas.</span><span class="sxs-lookup"><span data-stu-id="acc25-121">Clear this check box to keep the display focus on the first rows received.</span></span>  
  
 <span data-ttu-id="acc25-122">**Alinear a la derecha los valores numéricos**</span><span class="sxs-lookup"><span data-stu-id="acc25-122">**Right align numeric values**</span></span>  
 <span data-ttu-id="acc25-123">Active esta casilla para alinear los valores numéricos a la derecha de la columna.</span><span class="sxs-lookup"><span data-stu-id="acc25-123">Select this check box to align numeric values to the right of the column.</span></span> <span data-ttu-id="acc25-124">Esto puede ser de ayuda a la hora de revisar números con un número fijo de posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="acc25-124">This can make it easier to review numbers with a fixed number of decimal places.</span></span>  
  
 <span data-ttu-id="acc25-125">**Descartar resultados tras la ejecución**</span><span class="sxs-lookup"><span data-stu-id="acc25-125">**Discard result after query executes**</span></span>  
 <span data-ttu-id="acc25-126">Active esta casilla para descartar los resultados de la consulta después de que se hayan mostrado en el panel de resultados de la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="acc25-126">Select this check box to discard the query results after they are displayed in the results pane of the query window.</span></span>  
  
 <span data-ttu-id="acc25-127">**Mostrar resultados en otra pestaña**</span><span class="sxs-lookup"><span data-stu-id="acc25-127">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="acc25-128">Active esta casilla para mostrar el conjunto de resultados en una nueva ventana de documento, en lugar de en la parte inferior de la ventana de documento de la consulta.</span><span class="sxs-lookup"><span data-stu-id="acc25-128">Select this check box to display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="acc25-129">**Cambiar a la pestaña de resultados tras ejecutar la consulta**</span><span class="sxs-lookup"><span data-stu-id="acc25-129">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="acc25-130">Active esta casilla para establecer automáticamente el foco de la pantalla en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="acc25-130">Select this check box to automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="acc25-131">**Número máximo de caracteres mostrados en cada columna**</span><span class="sxs-lookup"><span data-stu-id="acc25-131">**Maximum number of characters displayed in each column**</span></span>  
 <span data-ttu-id="acc25-132">El valor predeterminado es 256.</span><span class="sxs-lookup"><span data-stu-id="acc25-132">This value defaults to 256.</span></span> <span data-ttu-id="acc25-133">Aumente este valor para poder mostrar conjuntos de resultados mayores sin truncamientos.</span><span class="sxs-lookup"><span data-stu-id="acc25-133">Increase this value to display larger result sets without truncation.</span></span> <span data-ttu-id="acc25-134">El valor máximo es 8,192.</span><span class="sxs-lookup"><span data-stu-id="acc25-134">The maximum value is 8,192.</span></span>  
  
 <span data-ttu-id="acc25-135">**Valores predeterminados**</span><span class="sxs-lookup"><span data-stu-id="acc25-135">**Reset to Default**</span></span>  
 <span data-ttu-id="acc25-136">Restablece todos los valores de esta página a los valores predeterminados originales.</span><span class="sxs-lookup"><span data-stu-id="acc25-136">Resets all values on this page to the original default values.</span></span>  
  
  
