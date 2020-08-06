---
title: Usar el modo PATH con FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode
- characters [SQL Server], XML
- aliases [SQL Server], XML
- FOR XML clause, PATH mode
- FOR XML PATH mode
- column names [SQL Server]
- XPath queries [SQL Server]
ms.assetid: a685a9ad-3d28-4596-aa72-119202df3976
author: rothja
ms.author: jroth
ms.openlocfilehash: ce0cf811f1e610d14a94993b54c51ea079f613e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673553"
---
# <a name="use-path-mode-with-for-xml"></a><span data-ttu-id="15523-102">Usar el modo PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="15523-102">Use PATH Mode with FOR XML</span></span>
  <span data-ttu-id="15523-103">Tal como se describe en [Generar XML mediante FOR XML](for-xml-sql-server.md), el modo PATH facilita la combinación de elementos y atributos.</span><span class="sxs-lookup"><span data-stu-id="15523-103">As described in [Constructing XML Using FOR XML](for-xml-sql-server.md), the PATH mode provides a simpler way to mix elements and attributes.</span></span> <span data-ttu-id="15523-104">También facilita la especificación de anidación adicional para representar propiedades complejas.</span><span class="sxs-lookup"><span data-stu-id="15523-104">PATH mode is also a simpler way to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="15523-105">Puede utilizar consultas de modo FOR XML EXPLICIT para generar XML a partir de un conjunto de filas, pero el modo PATH supone una alternativa más sencilla a las consultas de modo EXPLICIT potencialmente complicadas.</span><span class="sxs-lookup"><span data-stu-id="15523-105">You can use FOR XML EXPLICIT mode queries to construct such XML from a rowset, but the PATH mode provides a simpler alternative to the potentially cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="15523-106">El modo PATH, junto con la posibilidad de escribir consultas FOR XML anidadas y la directiva TYPE para devolver instancias de tipo **xml** , permite escribir consultas de forma más fácil.</span><span class="sxs-lookup"><span data-stu-id="15523-106">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span>  
  
 <span data-ttu-id="15523-107">En el modo PATH, los nombres o alias de columna se tratan como expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="15523-107">In PATH mode, column names or column aliases are treated as XPath expressions.</span></span> <span data-ttu-id="15523-108">Estas expresiones indican el modo en el que se asignan los valores a XML.</span><span class="sxs-lookup"><span data-stu-id="15523-108">These expressions indicate how the values are being mapped to XML.</span></span> <span data-ttu-id="15523-109">Cada expresión XPath es una expresión relativa que proporciona el tipo de elemento, como el atributo, el elemento y el valor escalar, así como el nombre y la jerarquía del nodo que se generará en relación con el elemento de fila.</span><span class="sxs-lookup"><span data-stu-id="15523-109">Each XPath expression is a relative XPath that provides the item type., such as the attribute, element, and scalar value, and the name and hierarchy of the node that will be generated relative to the row element.</span></span>  
  
 <span data-ttu-id="15523-110">Esta sección describe las columnas de asignación en un conjunto de filas bajo varias condiciones y proporciona los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="15523-110">This section describes mapping columns in a rowset under various conditions, and provides examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15523-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="15523-111">In This Section</span></span>  
  
-   [<span data-ttu-id="15523-112">Columnas sin nombre</span><span class="sxs-lookup"><span data-stu-id="15523-112">Columns without a Name</span></span>](columns-without-a-name.md)  
  
-   [<span data-ttu-id="15523-113">Columnas con nombre</span><span class="sxs-lookup"><span data-stu-id="15523-113">Columns with a Name</span></span>](columns-with-a-name.md)  
  
-   [<span data-ttu-id="15523-114">Columnas con un nombre especificado como carácter comodín</span><span class="sxs-lookup"><span data-stu-id="15523-114">Columns with a Name Specified as a Wildcard Character</span></span>](columns-with-a-name-specified-as-a-wildcard-character.md)  
  
-   [<span data-ttu-id="15523-115">Columnas con el nombre de una prueba de nodo XPath</span><span class="sxs-lookup"><span data-stu-id="15523-115">Columns with the Name of an XPath Node Test</span></span>](columns-with-the-name-of-an-xpath-node-test.md)  
  
-   [<span data-ttu-id="15523-116">Nombres de columna con la ruta de acceso especificada como data&#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="15523-116">Column Names with the Path Specified as data&#40;&#41;</span></span>](column-names-with-the-path-specified-as-data.md)  
  
-   [<span data-ttu-id="15523-117">Columnas que incluyen un valor NULL de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="15523-117">Columns that Contain a Null Value By Default</span></span>](columns-that-contain-a-null-value-by-default.md)  
  
-   [<span data-ttu-id="15523-118">Compatibilidad con elementos de espacio de nombres en el modo PATH</span><span class="sxs-lookup"><span data-stu-id="15523-118">Namespace Support in PATH Mode</span></span>](namespace-support-in-path-mode.md)  
  
-   [<span data-ttu-id="15523-119">Ejemplos: Uso del modo PATH</span><span class="sxs-lookup"><span data-stu-id="15523-119">Examples: Using PATH Mode</span></span>](examples-using-path-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="15523-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15523-120">See Also</span></span>  
 <span data-ttu-id="15523-121">[Agregar espacios de nombres a consultas con WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="15523-121">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="15523-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15523-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="15523-123">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="15523-123">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
