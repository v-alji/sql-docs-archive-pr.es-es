---
title: Buscar en un documento activo de forma incremental
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], incremental
- Query Editor [SQL Server Management Studio], incremental search
- incremental searches [SQL Server Management Studio]
ms.assetid: 490bb36c-dd43-4219-9e2a-ff27046b9395
author: rothja
ms.author: jroth
ms.openlocfilehash: aefc2f0b7abff5992a8f4f7817e564ef1b72009d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669589"
---
# <a name="search-an-active-document-incrementally"></a><span data-ttu-id="4e805-102">Buscar en un documento activo de forma incremental</span><span class="sxs-lookup"><span data-stu-id="4e805-102">Search an Active Document Incrementally</span></span>
  <span data-ttu-id="4e805-103">Es posible buscar en un único documento o ventana de forma incremental mediante la especificación de texto.</span><span class="sxs-lookup"><span data-stu-id="4e805-103">You can search a single document or window incrementally by entering text.</span></span> <span data-ttu-id="4e805-104">La operación de búsqueda destaca el primer juego de caracteres que coincide con los especificados durante la búsqueda incremental en el documento o ventana.</span><span class="sxs-lookup"><span data-stu-id="4e805-104">The search operation highlights the first set of characters that matches the characters entered during the incremental search in the document or window.</span></span> <span data-ttu-id="4e805-105">La búsqueda incremental busca automáticamente en todo el texto de un documento o ventana, excepto el texto oculto.</span><span class="sxs-lookup"><span data-stu-id="4e805-105">Incremental search automatically searches all of the text within a document or window except for text that has been hidden.</span></span>  
  
 <span data-ttu-id="4e805-106">Con la opción **Coincidir mayúsculas y minúsculas** , la búsqueda incremental utiliza los criterios de la búsqueda anterior.</span><span class="sxs-lookup"><span data-stu-id="4e805-106">For the **Match case** option, incremental search uses the criteria from your previous search.</span></span> <span data-ttu-id="4e805-107">Por ejemplo, si se ha buscado en varios archivos mediante el cuadro de diálogo **Buscar en archivos** y se ha activado **Coincidir mayúsculas y minúsculas**, si la siguiente vez se busca de forma incremental, la búsqueda distinguirá entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4e805-107">For example, if you searched across multiple files using the **Find in Files** dialog box and select **Match Case**, and you next search incrementally, the search will be case-sensitive.</span></span>  
  
### <a name="to-search-incrementally"></a><span data-ttu-id="4e805-108">Para buscar de forma incremental</span><span class="sxs-lookup"><span data-stu-id="4e805-108">To search incrementally</span></span>  
  
1.  <span data-ttu-id="4e805-109">Abra el archivo o ventana en que desea realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e805-109">Open the file or window to you want to search.</span></span>  
  
2.  <span data-ttu-id="4e805-110">En el menú **Editar** , elija **Avanzado**y, a continuación, haga clic en **Búsqueda incremental**.</span><span class="sxs-lookup"><span data-stu-id="4e805-110">On the **Edit** menu, point to **Advanced**, and then click **Incremental Search**.</span></span>  
  
     <span data-ttu-id="4e805-111">El cursor cambia a unos prismáticos con una flecha, que indica la dirección de la búsqueda, y la barra de estado muestra "Búsqueda incremental".</span><span class="sxs-lookup"><span data-stu-id="4e805-111">The cursor icon changes to a binocular with an arrow, indicating the search direction, and the status bar displays "Incremental Search."</span></span>  
  
3.  <span data-ttu-id="4e805-112">Comience a escribir la cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="4e805-112">Begin typing the text string.</span></span>  
  
     <span data-ttu-id="4e805-113">La barra de estado muestra el texto que se está escribiendo, mientras el editor resalta la primera repetición del texto.</span><span class="sxs-lookup"><span data-stu-id="4e805-113">The status bar displays the text you are entering while the editor highlights the first occurrence that matches the text.</span></span> <span data-ttu-id="4e805-114">A medida que se continúa escribiendo, el editor pasa a la siguiente coincidencia y la resalta.</span><span class="sxs-lookup"><span data-stu-id="4e805-114">As you continue typing, the editor moves to the next match and highlights it.</span></span> <span data-ttu-id="4e805-115">Si no hay coincidencias, la barra de estado muestra lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4e805-115">If no matches are available, the status bar displays the following.</span></span>  
  
    ```  
    Incremental Search: <text> (not found)  
    ```  
  
 <span data-ttu-id="4e805-116">Las búsquedas incrementales se llevan a cabo desde la ubicación actual en el documento hacia abajo y de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="4e805-116">Incremental searches are performed from the current location in the document downwards from left to right.</span></span> <span data-ttu-id="4e805-117">Se pueden realizar mediante métodos abreviados de teclado.</span><span class="sxs-lookup"><span data-stu-id="4e805-117">Incremental searches can be done using keyboard shortcut keys.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e805-118">Para obtener una lista completa de las teclas de método abreviado, vea [Métodos abreviados de teclado de SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="4e805-118">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e805-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e805-119">See Also</span></span>  
 <span data-ttu-id="4e805-120">[Buscar y reemplazar](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="4e805-120">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="4e805-121">[Buscar documentos de forma interactiva](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="4e805-121">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="4e805-122">[Buscar en documentos mediante las listas de resultados](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="4e805-122">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="4e805-123">[Buscar texto con caracteres comodín](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="4e805-123">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="4e805-124">Buscar texto mediante expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="4e805-124">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
