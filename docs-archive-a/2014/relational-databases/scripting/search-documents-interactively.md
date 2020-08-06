---
title: Buscar documentos de forma interactiva
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- interactive searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], interactive
- Query Editor [SQL Server Management Studio], interactive search
ms.assetid: dae65ac5-67af-45c6-a6e0-952fea26d680
author: rothja
ms.author: jroth
ms.openlocfilehash: 5603db77ea4f58d4bb036635a23ec3cfa400a818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677004"
---
# <a name="search-documents-interactively"></a><span data-ttu-id="0023f-102">Buscar documentos de forma interactiva</span><span class="sxs-lookup"><span data-stu-id="0023f-102">Search Documents Interactively</span></span>
  <span data-ttu-id="0023f-103">Mediante el cuadro de diálogo **Buscar y reemplazar** , puede buscar en uno o más archivos o ventanas abiertos y desplazarse por las coincidencias una a una.</span><span class="sxs-lookup"><span data-stu-id="0023f-103">Using the **Find and Replace** dialog box, you can search one or more open files or windows and move through the search matches one by one.</span></span> <span data-ttu-id="0023f-104">Esta técnica permite revisar cada coincidencia individual en el contexto en que se encuentra.</span><span class="sxs-lookup"><span data-stu-id="0023f-104">This technique allows you to review each individual search match in the context of the text around the match.</span></span> <span data-ttu-id="0023f-105">El cuadro de diálogo **Buscar y reemplazar** también ofrece la opción de realizar operaciones de búsqueda masiva y revisión de coincidencias en formato de informe.</span><span class="sxs-lookup"><span data-stu-id="0023f-105">You also have the option of performing bulk find operations and reviewing search matches in report format using the **Find and Replace** dialog box.</span></span>  
  
### <a name="to-search-all-open-documents"></a><span data-ttu-id="0023f-106">Para buscar en todos los documentos abiertos</span><span class="sxs-lookup"><span data-stu-id="0023f-106">To search all open documents</span></span>  
  
1.  <span data-ttu-id="0023f-107">Abra los elementos en los que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="0023f-107">Open the items you wish to search.</span></span>  
  
2.  <span data-ttu-id="0023f-108">En el menú **Editar** , elija **Buscar y reemplazar** y, después, haga clic en **Búsqueda rápida**.</span><span class="sxs-lookup"><span data-stu-id="0023f-108">On the **Edit** menu, point to **Find and Replace,** and then click **QuickFind**.</span></span>  
  
3.  <span data-ttu-id="0023f-109">En el cuadro de texto **Buscar y reemplazar** , escriba el texto que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="0023f-109">In the **Find and Replace** text box, enter the text to search for.</span></span>  
  
4.  <span data-ttu-id="0023f-110">En la lista **Buscar en** , seleccione **Todos los documentos abiertos**.</span><span class="sxs-lookup"><span data-stu-id="0023f-110">In the **Look in** list, select **All Open Documents**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0023f-111">Cuando se selecciona **Todos los documentos abiertos** , puede que no se busque en algunos archivos abiertos.</span><span class="sxs-lookup"><span data-stu-id="0023f-111">Certain open files might not be searched when **All Open Documents** is selected.</span></span> <span data-ttu-id="0023f-112">Solo se incluyen en las búsquedas aquellos archivos abiertos actualmente en una vista de texto, como la vista Código.</span><span class="sxs-lookup"><span data-stu-id="0023f-112">Only files currently open in a textual view, such as Code view, are included in searches.</span></span> <span data-ttu-id="0023f-113">Los archivos abiertos en la vista del diseñador no se incluyen en las búsquedas.</span><span class="sxs-lookup"><span data-stu-id="0023f-113">Files in Designer view are not included in searches.</span></span>  
  
5.  <span data-ttu-id="0023f-114">Seleccione opciones de búsqueda adicionales para aumentar la precisión de la misma.</span><span class="sxs-lookup"><span data-stu-id="0023f-114">Select additional search options to increase the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="0023f-115">Haga clic en **Buscar siguiente** para iniciar la búsqueda y siga haciendo clic en **Buscar siguiente** hasta que haya buscado en el último archivo.</span><span class="sxs-lookup"><span data-stu-id="0023f-115">Click **Find Next** to start the search, and continue clicking **Find Next** until the last file has been searched.</span></span>  
  
 <span data-ttu-id="0023f-116">Cuando la búsqueda pasa el comienzo o el final del documento, aparece un mensaje en la barra de estado.</span><span class="sxs-lookup"><span data-stu-id="0023f-116">When the search passes the beginning or end of the document, a message is displayed in the status bar.</span></span> <span data-ttu-id="0023f-117">Cuando la búsqueda alcanza el punto de inicio, aparece un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="0023f-117">A message box appears when the search reaches the starting point of the search.</span></span>  
  
#### <a name="to-replace-in-all-active-files-interactively"></a><span data-ttu-id="0023f-118">Para reemplazar en todos los archivos activos de forma interactiva</span><span class="sxs-lookup"><span data-stu-id="0023f-118">To replace in all active files interactively</span></span>  
  
1.  <span data-ttu-id="0023f-119">En el menú **Editar** , elija **Buscar y reemplazar**y, después, haga clic en **Reemplazo rápido**.</span><span class="sxs-lookup"><span data-stu-id="0023f-119">On the **Edit** menu, point to **Find and Replace**, and then click **QuickReplace**.</span></span>  
  
2.  <span data-ttu-id="0023f-120">En el cuadro **Buscar** , escriba el texto que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="0023f-120">In the **Find what** box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="0023f-121">En el cuadro **Reemplazar con** , escriba el texto que reemplazará al texto de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0023f-121">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="0023f-122">En la lista **Buscar en** , seleccione **Todos los documentos abiertos**.</span><span class="sxs-lookup"><span data-stu-id="0023f-122">In the **Look in** list, select **All Open Documents**.</span></span>  
  
5.  <span data-ttu-id="0023f-123">Haga clic en **Reemplazar**y siga haciendo clic en **Reemplazar** hasta que haya reemplazado la última coincidencia del última archivo.</span><span class="sxs-lookup"><span data-stu-id="0023f-123">Click **Replace**, and continue clicking **Replace** until the last match in the last file has been replaced.</span></span> <span data-ttu-id="0023f-124">Haga clic en **Buscar siguiente** para omitir una coincidencia que no desea reemplazar.</span><span class="sxs-lookup"><span data-stu-id="0023f-124">Click **Find Next** to skip a match you do not want to replace.</span></span>  
  
     <span data-ttu-id="0023f-125">O bien</span><span class="sxs-lookup"><span data-stu-id="0023f-125">-or-</span></span>  
  
     <span data-ttu-id="0023f-126">Elija **Reemplazar todo** para reemplazar todas las coincidencias.</span><span class="sxs-lookup"><span data-stu-id="0023f-126">Choose **Replace All** to replace all matches.</span></span> <span data-ttu-id="0023f-127">Aparecerá un cuadro de mensaje indicando el número total de reemplazos.</span><span class="sxs-lookup"><span data-stu-id="0023f-127">A message box appears, listing the total number of replacements.</span></span>  
  
 <span data-ttu-id="0023f-128">El comando **Reemplazar todo** reemplaza todas las coincidencias de la búsqueda, incluidas aquellas que se han omitido mediante el botón **Buscar siguiente** .</span><span class="sxs-lookup"><span data-stu-id="0023f-128">The **Replace All** command replaces all search matches, including those you have skipped with the **Find Next** button.</span></span> <span data-ttu-id="0023f-129">Para cancelar **Reemplazar todo**, haga clic en **Deshacer** en el menú **Editar** antes de cerrar cualquiera de los archivos.</span><span class="sxs-lookup"><span data-stu-id="0023f-129">To cancel **Replace All**, click **Undo** from the **Edit** menu before closing any of the files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0023f-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0023f-130">See Also</span></span>  
 <span data-ttu-id="0023f-131">[Buscar en un documento activo de forma incremental](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="0023f-131">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="0023f-132">[Buscar y reemplazar](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="0023f-132">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="0023f-133">[Buscar en documentos mediante las listas de resultados](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="0023f-133">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="0023f-134">[Buscar texto con caracteres comodín](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="0023f-134">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="0023f-135">Buscar texto mediante expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="0023f-135">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
