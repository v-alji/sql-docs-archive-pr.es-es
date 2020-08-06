---
title: Generar XML a partir de conjuntos de filas con FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, generating XML from rowsets
ms.assetid: d061c0f1-3de9-4ad1-bbca-ce45d064b6c8
author: rothja
ms.author: jroth
ms.openlocfilehash: dcf9feb4dab9ad1149ab433c9d9b4999c96c1cdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751957"
---
# <a name="generate-xml-from-rowsets-with-for-xml"></a><span data-ttu-id="a135c-102">Generar XML a partir de conjuntos de filas con FOR XML</span><span class="sxs-lookup"><span data-stu-id="a135c-102">Generate XML from Rowsets with FOR XML</span></span>
  <span data-ttu-id="a135c-103">Puede generar una `xml` instancia de tipo de datos a partir de un conjunto de filas mediante for XML con la nueva directiva **Type** .</span><span class="sxs-lookup"><span data-stu-id="a135c-103">You can generate an `xml` data type instance from a rowset by using FOR XML with the new **TYPE** directive.</span></span>  
  
 <span data-ttu-id="a135c-104">El resultado se puede asignar a una `xml` columna, variable o parámetro de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="a135c-104">The result can be assigned to an `xml` data type column, variable, or parameter.</span></span> <span data-ttu-id="a135c-105">Además, FOR XML se puede anidar para generar una estructura jerárquica.</span><span class="sxs-lookup"><span data-stu-id="a135c-105">Also, FOR XML can be nested to generate any hierarchical structure.</span></span> <span data-ttu-id="a135c-106">Por ello, FOR XML anidado resulta mucho más cómodo de escribir que FOR XML EXPLICIT, aunque tal vez no funcione tan bien para jerarquías con muchos niveles.</span><span class="sxs-lookup"><span data-stu-id="a135c-106">This makes nested FOR XML much more convenient to write than FOR XML EXPLICIT, but it may not perform as well for deep hierarchies.</span></span> <span data-ttu-id="a135c-107">FOR XML también incorpora un nuevo modo PATH.</span><span class="sxs-lookup"><span data-stu-id="a135c-107">FOR XML also introduces a new PATH mode.</span></span> <span data-ttu-id="a135c-108">Este nuevo modo especifica la ruta de acceso en el árbol XML donde aparece un valor de columna.</span><span class="sxs-lookup"><span data-stu-id="a135c-108">This new mode specifies the path in the XML tree where a column's value appears.</span></span>  
  
 <span data-ttu-id="a135c-109">La nueva directiva **FOR XML TYPE** puede emplearse para definir vistas XML de solo lectura en datos relacionales con sintaxis SQL.</span><span class="sxs-lookup"><span data-stu-id="a135c-109">The new **FOR XML TYPE** directive can be used to define read-only XML views over relational data with SQL syntax.</span></span> <span data-ttu-id="a135c-110">Es posible realizar consultas en la vista con instrucciones SQL y XQuery incrustado, como se indica en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a135c-110">The view can be queried with SQL statements and embedded XQuery, as shown in the following example.</span></span> <span data-ttu-id="a135c-111">También se puede hacer referencia a estas vistas SQL en procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="a135c-111">You can also refer to these SQL views in stored procedures.</span></span>  
  
## <a name="example-sql-view-returning-generated-xml-data-type"></a><span data-ttu-id="a135c-112">Ejemplo: Vista SQL que devuelve el tipo de datos XML generado</span><span class="sxs-lookup"><span data-stu-id="a135c-112">Example: SQL View Returning Generated xml Data Type</span></span>  
 <span data-ttu-id="a135c-113">La siguiente definición de vista SQL crea una vista XML de una columna relacional, pk, y de los autores de libros recuperados de una columna XML:</span><span class="sxs-lookup"><span data-stu-id="a135c-113">The following SQL view definition creates an XML view over a relational column, pk, and book authors retrieved from an XML column:</span></span>  
  
```  
CREATE VIEW V (xmlVal) AS  
SELECT pk, xCol.query('/book/author')  
FROM   T  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="a135c-114">La vista V contiene una sola fila con una sola columna xmlval de tipo XML `.` que se puede consultar como una `xml` instancia de tipo de datos normal.</span><span class="sxs-lookup"><span data-stu-id="a135c-114">The V view contains a single row with a single columnxmlVal of XML type`.` It can be queried like a regular `xml` data type instance.</span></span> <span data-ttu-id="a135c-115">Por ejemplo, la siguiente consulta devuelve el autor cuyo nombre es "David":</span><span class="sxs-lookup"><span data-stu-id="a135c-115">For example, the following query returns the author whose first name is "David":</span></span>  
  
```  
SELECT xmlVal.query('//author[first-name = "David"]')  
FROM   V  
```  
  
 <span data-ttu-id="a135c-116">Las definiciones de vistas SQL son en cierto modo similares a las vistas XML que se crean mediante esquemas anotados.</span><span class="sxs-lookup"><span data-stu-id="a135c-116">SQL view definitions are somewhat similar to XML views that are created by using annotated schemas.</span></span> <span data-ttu-id="a135c-117">Sin embargo, hay tres diferencias importantes.</span><span class="sxs-lookup"><span data-stu-id="a135c-117">However, there are important differences.</span></span> <span data-ttu-id="a135c-118">La definición de vista SQL es de solo lectura y se debe manipular con XQuery incrustado.</span><span class="sxs-lookup"><span data-stu-id="a135c-118">The SQL view definition is read-only and must be manipulated with embedded XQuery.</span></span> <span data-ttu-id="a135c-119">Las vistas XML se crean mediante un esquema anotado.</span><span class="sxs-lookup"><span data-stu-id="a135c-119">The XML views are created by using annotated schema.</span></span> <span data-ttu-id="a135c-120">Además, la vista SQL materializa el resultado XML antes de aplicar la expresión XQuery, mientras que las consultas XPath en las vistas XML evalúan consultas SQL en las tablas subyacentes.</span><span class="sxs-lookup"><span data-stu-id="a135c-120">Additionally, the SQL view materializes the XML result before applying the XQuery expression, while the XPath queries on XML views evaluate SQL queries on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a135c-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a135c-121">See Also</span></span>  
 [<span data-ttu-id="a135c-122">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a135c-122">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
