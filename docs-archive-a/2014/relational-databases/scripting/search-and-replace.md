---
title: Buscar y reemplazar
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- match case [SQL Server]
- undo operations
- searches [SQL Server Management Studio]
- replacing text
- quick search and replaces [SQL Server Management Studio]
- Query Editor [SQL Server Management Studio], undo
- Query Editor [SQL Server Management Studio], searching
- regular expressions [SQL Server Management Studio]
- finding text [SQL Server Management Studio]
- text [SQL Server], search and replace operations
- finding [SQL Server Management Studio]
- locating text
- Query Editor [SQL Server Management Studio], replacing text
- Find and Replace dialog box
- wildcard options [SQL Server Management Studio]
- match whole word [SQL Server]
- searches [SQL Server Management Studio], replacing
ms.assetid: 3641c7b3-3e3e-4ddd-af82-c15b50004f94
author: rothja
ms.author: jroth
ms.openlocfilehash: 55422fa7201213477426c7bc25c45ff05acf8945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669586"
---
# <a name="search-and-replace"></a><span data-ttu-id="b523b-102">Buscar y reemplazar</span><span class="sxs-lookup"><span data-stu-id="b523b-102">Search and Replace</span></span>
  <span data-ttu-id="b523b-103">Existen varias maneras de buscar y reemplazar texto.</span><span class="sxs-lookup"><span data-stu-id="b523b-103">There are several different ways to find and replace text.</span></span> <span data-ttu-id="b523b-104">En el menú **Editar** , **Buscar y reemplazar** ofrece cuatro opciones: **Búsqueda rápida**, **Reemplazo rápido**, **Buscar en archivos**o **Reemplazar en archivos**.</span><span class="sxs-lookup"><span data-stu-id="b523b-104">On the **Edit** menu, **Find and Replace** offers four choices: **Quick Find**, **Quick Replace**, **Find in Files**, or **Replace in Files**.</span></span> <span data-ttu-id="b523b-105">Cada una abre versiones del cuadro de diálogo **Buscar y reemplazar** .</span><span class="sxs-lookup"><span data-stu-id="b523b-105">Each of these opens versions of the **Find and Replace** dialog box.</span></span> <span data-ttu-id="b523b-106">También es posible buscar sin un cuadro de diálogo mediante los métodos abreviados de teclado para búsqueda incremental.</span><span class="sxs-lookup"><span data-stu-id="b523b-106">You can also search without a dialog box by using incremental search keyboard shortcut keys.</span></span> <span data-ttu-id="b523b-107">Estas técnicas permiten controlar el ámbito de búsqueda y reemplazo y elegir el método de revisión de las coincidencias de búsqueda y los reemplazos.</span><span class="sxs-lookup"><span data-stu-id="b523b-107">These techniques allow you to control the scope of find and replace, and choose the method of reviewing search matches and replacements.</span></span>  
  
 <span data-ttu-id="b523b-108">A la hora de buscar y reemplazar texto, es necesario tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b523b-108">You should consider the following when you search and replace text:</span></span>  
  
-   <span data-ttu-id="b523b-109">Las opciones establecidas en el cuadro de diálogo **Buscar y reemplazar** afectan a todas las búsquedas.</span><span class="sxs-lookup"><span data-stu-id="b523b-109">Options set in the **Find and Replace** dialog box affect all the searches.</span></span> <span data-ttu-id="b523b-110">Estas opciones incluyen **Coincidir mayúsculas y minúsculas**, **Solo palabras completas**, **Buscar hacia atrás**, **Buscar en texto oculto**, **Usar Caracteres comodín**, **Usar Expresiones regulares**, **Buscar en Todos los documentos abiertos**y **Buscar en Proyecto actual**.</span><span class="sxs-lookup"><span data-stu-id="b523b-110">These options include **Match case**, **Match whole word**, **Search up**, **Search hidden text**, **Wildcards**, **Regular Expressions**, **Look in All Open Documents**, and **Look in Current Project**.</span></span> <span data-ttu-id="b523b-111">Todas las opciones no están disponibles en todas las versiones del cuadro de diálogo **Buscar y reemplazar** .</span><span class="sxs-lookup"><span data-stu-id="b523b-111">All options are not available in all versions of the **Find and Replace** dialog box.</span></span>  
  
-   <span data-ttu-id="b523b-112">**Deshacer** solo está disponible para aquellos documentos que se dejan abiertos tras una operación de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="b523b-112">**Undo** is available only for documents left open after a replace operation.</span></span>  
  
-   <span data-ttu-id="b523b-113">**Deshacer** para una operación **Reemplazar todo** que abarca más de un archivo se considera una acción única masiva en todos los archivos afectados.</span><span class="sxs-lookup"><span data-stu-id="b523b-113">**Undo** for a **Replace All** operation that spans more than one file is considered a single, bulk action across all the affected files.</span></span> <span data-ttu-id="b523b-114">Es decir, no es posible deshacer el cambio en algunos archivos y no en otros.</span><span class="sxs-lookup"><span data-stu-id="b523b-114">That is, you cannot undo the change in some files while retaining the change in other files.</span></span>  
  
 <span data-ttu-id="b523b-115">Normalmente no es posible buscar elementos mediante vistas gráficas.</span><span class="sxs-lookup"><span data-stu-id="b523b-115">Generally, you cannot search items with graphical views.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b523b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b523b-116">See Also</span></span>  
 <span data-ttu-id="b523b-117">[Buscar en un documento activo de forma incremental](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="b523b-117">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="b523b-118">[Buscar documentos de forma interactiva](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="b523b-118">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="b523b-119">[Buscar en documentos mediante las listas de resultados](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="b523b-119">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="b523b-120">[Buscar texto con caracteres comodín](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="b523b-120">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="b523b-121">Buscar texto mediante expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="b523b-121">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
