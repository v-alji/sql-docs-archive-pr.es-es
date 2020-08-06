---
title: Usar el modo RAW con FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML RAW mode
- XMLSCHEMA option
- FOR XML clause, RAW mode
- RAW FOR XML mode
- ELEMENTS directive
- RAW mode
- XMLDATA option
ms.assetid: 02c1bc0b-760c-4589-9ab1-6927c6d9c734
author: rothja
ms.author: jroth
ms.openlocfilehash: b2908a98336ec8a6e12029ad471f22a33d7a4dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748685"
---
# <a name="use-raw-mode-with-for-xml"></a><span data-ttu-id="a82ad-102">Usar el modo RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="a82ad-102">Use RAW Mode with FOR XML</span></span>
  <span data-ttu-id="a82ad-103">El modo RAW transforma cada fila del conjunto de resultados de la consulta en un elemento XML que tiene el identificador genérico \<row> o el nombre del elemento, que se proporciona de manera opcional.</span><span class="sxs-lookup"><span data-stu-id="a82ad-103">RAW mode transforms each row in the query result set into an XML element that has the generic identifier \<row>, or the optionally provided element name.</span></span> <span data-ttu-id="a82ad-104">De forma predeterminada, cada valor de columna del conjunto de filas que no es NULL se asigna a un atributo del elemento \<row>.</span><span class="sxs-lookup"><span data-stu-id="a82ad-104">By default, each column value in the rowset that is not NULL is mapped to an attribute of the \<row> element.</span></span> <span data-ttu-id="a82ad-105">Si se agrega la directiva ELEMENTS a la cláusula FOR XML, cada valor de columna se asigna a un subelemento del elemento \<row>.</span><span class="sxs-lookup"><span data-stu-id="a82ad-105">If the ELEMENTS directive is added to the FOR XML clause, each column value is mapped to a subelement of the \<row> element.</span></span> <span data-ttu-id="a82ad-106">Opcionalmente, junto con la directiva ELEMENTS se puede especificar la opción XSINIL para asignar los valores de columna NULL del conjunto de resultados a un elemento que tenga el atributo, xsi:nil=`"`true`"`.</span><span class="sxs-lookup"><span data-stu-id="a82ad-106">Together with the ELEMENTS directive, you can optionally specify the XSINIL option to map NULL column values in the result set to an element that has the attribute, xsi:nil=`"`true`"`.</span></span>  
  
 <span data-ttu-id="a82ad-107">Se puede solicitar un esquema para el XML resultante.</span><span class="sxs-lookup"><span data-stu-id="a82ad-107">You can request a schema for the resulting XML.</span></span> <span data-ttu-id="a82ad-108">Si se especifica la opción XMLDATA se devuelve un esquema XDR en línea.</span><span class="sxs-lookup"><span data-stu-id="a82ad-108">Specifying the XMLDATA option returns an in-line XDR schema.</span></span> <span data-ttu-id="a82ad-109">Si se especifica la opción XMLSCHEMA se devuelve un esquema XSD en línea.</span><span class="sxs-lookup"><span data-stu-id="a82ad-109">Specifying the XMLSCHEMA option returns an in-line XSD schema.</span></span> <span data-ttu-id="a82ad-110">El esquema aparece al principio de los datos.</span><span class="sxs-lookup"><span data-stu-id="a82ad-110">The schema appears at the start of the data.</span></span> <span data-ttu-id="a82ad-111">En el resultado, la referencia al espacio de nombres del esquema se repite en todos los elementos de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="a82ad-111">In the result, the schema namespace reference is repeated for every top-level element.</span></span>  
  
 <span data-ttu-id="a82ad-112">La opción BINARY BASE64 se debe especificar en la cláusula FOR XML para devolver los datos binarios en formato codificado en base 64.</span><span class="sxs-lookup"><span data-stu-id="a82ad-112">The BINARY BASE64 option must be specified in the FOR XML clause to return the binary data in base64-encoded format.</span></span> <span data-ttu-id="a82ad-113">En el modo RAW, si se recuperan los datos binarios sin especificar la opción BINARY BASE64, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="a82ad-113">In RAW mode, retrieving binary data without specifying the BINARY BASE64 option will result in an error.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a82ad-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a82ad-114">In This Section</span></span>  
 <span data-ttu-id="a82ad-115">En esta sección se incluyen los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a82ad-115">This section contains the following examples:</span></span>  
  
-   [<span data-ttu-id="a82ad-116">Ejemplo: Recuperación de información de modelos de productos como XML</span><span class="sxs-lookup"><span data-stu-id="a82ad-116">Example: Retrieving Product Model Information as XML</span></span>](example-retrieving-product-model-information-as-xml.md)  
  
-   [<span data-ttu-id="a82ad-117">Ejemplo: Especificación de XSINIL con la directiva ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="a82ad-117">Example: Specifying XSINIL with the ELEMENTS Directive</span></span>](example-specifying-xsinil-with-the-elements-directive.md)  
  
-   [<span data-ttu-id="a82ad-118">Ejemplo: Solicitud de esquemas como resultados con las opciones XMLDATA y XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="a82ad-118">Example: Requesting Schemas as Results with the XMLDATA and XMLSCHEMA Options</span></span>](example-requesting-schemas-as-results-with-the-xmldata-and-xmlschema-options.md)  
  
-   [<span data-ttu-id="a82ad-119">Ejemplo: Recuperación de datos binarios</span><span class="sxs-lookup"><span data-stu-id="a82ad-119">Example: Retrieving Binary Data</span></span>](example-retrieving-binary-data.md)  
  
-   [<span data-ttu-id="a82ad-120">Ejemplo: Cambio del nombre del elemento &#60;row&#62;</span><span class="sxs-lookup"><span data-stu-id="a82ad-120">Example: Renaming the &#60;row&#62; Element</span></span>](example-renaming-the-row-element.md)  
  
-   [<span data-ttu-id="a82ad-121">Ejemplo: Especificación de un elemento raíz para el XML generado por FOR XML</span><span class="sxs-lookup"><span data-stu-id="a82ad-121">Example: Specifying a Root Element for the XML Generated by FOR XML</span></span>](example-specifying-a-root-element-for-the-xml-generated-by-for-xml.md)  
  
-   [<span data-ttu-id="a82ad-122">Ejemplo: Consulta de columnas de tipo XML</span><span class="sxs-lookup"><span data-stu-id="a82ad-122">Example: Querying XMLType Columns</span></span>](example-querying-xmltype-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="a82ad-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a82ad-123">See Also</span></span>  
 <span data-ttu-id="a82ad-124">[Agregar espacios de nombres a consultas con WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="a82ad-124">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="a82ad-125">[Usar el modo AUTO con FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a82ad-125">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="a82ad-126">[Usar el modo EXPLICIT con FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a82ad-126">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="a82ad-127">[Usar el modo PATH con FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a82ad-127">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="a82ad-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a82ad-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="a82ad-129">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a82ad-129">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
