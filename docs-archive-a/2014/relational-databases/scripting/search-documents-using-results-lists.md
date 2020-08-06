---
title: Buscar en documentos mediante las listas de resultados
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], result lists
- result list searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], multiple files
- Query Editor [SQL Server Management Studio], search multiple files
ms.assetid: 275e1b6c-fbd0-4408-af77-35903f90657c
author: rothja
ms.author: jroth
ms.openlocfilehash: 58ff3754bc1667de75426e52b3ddd855e7d1a348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676999"
---
# <a name="search-documents-using-results-lists"></a><span data-ttu-id="ce754-102">Buscar en documentos mediante las listas de resultados</span><span class="sxs-lookup"><span data-stu-id="ce754-102">Search Documents Using Results Lists</span></span>
  <span data-ttu-id="ce754-103">Con el cuadro de diálogo **Buscar y reemplazar** es posible buscar y reemplazar texto en todos los archivos de un proyecto o una solución, o en una carpeta del sistema de archivos, aunque no estén abiertos en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce754-103">Using the **Find and Replace** dialog box, you can search and replace text in all files in a project or solution or in a file system folder, even when they are not open in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ce754-104">Las coincidencias de las búsquedas realizadas con el cuadro de diálogo **Buscar y reemplazar** aparecen en las ventanas Resultados de la búsqueda 1 y Resultados de la búsqueda 2, que permiten ver el texto exacto de la línea que contiene la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="ce754-104">Matches from searches that were performed with the **Find and Replace** dialog box appear in the Find Results 1 and Find Results 2 windows, which allows you to view the exact text from the line containing the match.</span></span>  
  
### <a name="to-search-in-multiple-files"></a><span data-ttu-id="ce754-105">Para buscar en varios archivos</span><span class="sxs-lookup"><span data-stu-id="ce754-105">To search in multiple files</span></span>  
  
1.  <span data-ttu-id="ce754-106">En el menú **Editar** , elija **Buscar y reemplazar** y, a continuación, haga clic en **Buscar en archivos**.</span><span class="sxs-lookup"><span data-stu-id="ce754-106">On the **Edit** menu, point to **Find and Replace,** and then click **Find in Files**.</span></span>  
  
2.  <span data-ttu-id="ce754-107">En el cuadro de texto **Buscar** , escriba el texto que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="ce754-107">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="ce754-108">En la lista **Buscar en** , haga clic en **Todos los documentos abiertos**, **Proyecto actual**, **Toda la solución**o especifique una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="ce754-108">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
4.  <span data-ttu-id="ce754-109">En la lista **Tipos de archivo** , seleccione uno de los conjuntos enumerados de extensiones de archivo o especifique las extensiones de los tipos de archivo que desea buscar, separadas por signos de punto y coma.</span><span class="sxs-lookup"><span data-stu-id="ce754-109">In the **File types** list, select one of the listed sets of file extensions or enter the extensions for the types of files to be searched, separated by semicolons.</span></span> <span data-ttu-id="ce754-110">Utilice \*.\* para buscar todos los archivos del directorio que aparece en la lista desplegable **Buscar en** .</span><span class="sxs-lookup"><span data-stu-id="ce754-110">Use \*.\* to search all files in the directory listed in the **Look in** drop-down list.</span></span>  
  
5.  <span data-ttu-id="ce754-111">Elija las opciones de búsqueda restantes para aumentar la precisión de la misma.</span><span class="sxs-lookup"><span data-stu-id="ce754-111">Select from the remaining search options to improve the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="ce754-112">Haga clic en **Buscar** para iniciar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ce754-112">Click **Find** to begin the search.</span></span>  
  
 <span data-ttu-id="ce754-113">Las coincidencias de la búsqueda aparecen, de forma predeterminada, en la ventana Resultados de la búsqueda 1.</span><span class="sxs-lookup"><span data-stu-id="ce754-113">The matches for the search appear in the Find Results 1 window by default.</span></span> <span data-ttu-id="ce754-114">Puede examinar las coincidencias de la búsqueda si hace doble clic en cada entrada de la ventana Resultados de la búsqueda 1.</span><span class="sxs-lookup"><span data-stu-id="ce754-114">You can browse the search matches by double-clicking each entry in the Find Results 1 window.</span></span> <span data-ttu-id="ce754-115">Para ver los resultados de la búsqueda en una ventana nueva, seleccione **Mostrar resultados en otra ventana**.</span><span class="sxs-lookup"><span data-stu-id="ce754-115">To view the search results in a new window, select **Display in Find 2**.</span></span>  
  
#### <a name="to-replace-across-multiple-files-or-folders"></a><span data-ttu-id="ce754-116">Para reemplazar en varios archivos o carpetas</span><span class="sxs-lookup"><span data-stu-id="ce754-116">To replace across multiple files or folders</span></span>  
  
1.  <span data-ttu-id="ce754-117">En el menú **Editar** , elija **Buscar y reemplazar** y, a continuación, haga clic en **Reemplazar en archivos**.</span><span class="sxs-lookup"><span data-stu-id="ce754-117">On the **Edit** menu, point to **Find and Replace,** and then click **Replace in Files**.</span></span>  
  
2.  <span data-ttu-id="ce754-118">En el cuadro de texto **Buscar** , escriba el texto que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="ce754-118">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="ce754-119">En el cuadro **Reemplazar con** , escriba el texto que reemplazará al texto de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ce754-119">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="ce754-120">En la lista **Buscar en** , haga clic en **Todos los documentos abiertos**, **Proyecto actual**, **Toda la solución**o especifique una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="ce754-120">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
5.  <span data-ttu-id="ce754-121">Haga clic en **Reemplazar** para reemplazar el texto de búsqueda con el texto del cuadro **Reemplazar con** .</span><span class="sxs-lookup"><span data-stu-id="ce754-121">Click **Replace** to replace the current search match with the text in the **Replace with** box.</span></span> <span data-ttu-id="ce754-122">Puede omitir una coincidencia específica si hace clic en **Buscar siguiente** o un archivo entero si hace clic en **Omitir archivo**.</span><span class="sxs-lookup"><span data-stu-id="ce754-122">You can skip a single match by clicking **Find Next** or skip an entire file clicking **Skip File**.</span></span>  
  
     <span data-ttu-id="ce754-123">\- O bien</span><span class="sxs-lookup"><span data-stu-id="ce754-123">\- or -</span></span>  
  
     <span data-ttu-id="ce754-124">Elija **Reemplazar todo** para reemplazar todas las coincidencias de búsqueda con el texto del cuadro **Reemplazar con** .</span><span class="sxs-lookup"><span data-stu-id="ce754-124">Choose **Replace all** to replace all search matches with the text in the **Replace with** box.</span></span> <span data-ttu-id="ce754-125">Si desea deshacer algunos de los reemplazos en otro momento, seleccione **Mantener los archivos modificados abiertos después de Reemplazar todo** .</span><span class="sxs-lookup"><span data-stu-id="ce754-125">Select **Keep modified files open after Replace All** if you want to undo some of the replacements at another time.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce754-126">**Reemplazar todo** reemplaza todas las coincidencias de la búsqueda, incluidas aquellas que se encuentran en archivos que se han omitido mediante **Omitir archivo** o **Buscar siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ce754-126">**Replace all** replaces all search matches, including those in files you have skipped with **Skip File** or **Find Next**.</span></span> <span data-ttu-id="ce754-127">Solo es posible utilizar **Deshacer** en los reemplazos realizados en archivos que permanecen abiertos tras la operación de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="ce754-127">You can only use **Undo** for replacements made in files that remain open after the replacement operation.</span></span>  
  
 <span data-ttu-id="ce754-128">La información de reemplazo aparece de forma predeterminada en la ventana Resultados de la búsqueda 1.</span><span class="sxs-lookup"><span data-stu-id="ce754-128">Replacement information appears in the Find Results 1 window by default.</span></span> <span data-ttu-id="ce754-129">Puede examinar los reemplazos si hace doble clic en cada entrada de la ventana Resultados de la búsqueda 1.</span><span class="sxs-lookup"><span data-stu-id="ce754-129">You can browse replacements by double-clicking each entry in the Find Results 1 window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce754-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce754-130">See Also</span></span>  
 <span data-ttu-id="ce754-131">[Buscar y reemplazar](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="ce754-131">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="ce754-132">[Buscar documentos de forma interactiva](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="ce754-132">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="ce754-133">[Buscar texto con caracteres comodín](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="ce754-133">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="ce754-134">Buscar texto mediante expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="ce754-134">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
