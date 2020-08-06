---
title: Especificar predicados de selección en la ruta de acceso de ubicación (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- predicates [SQLXML]
- position-based filtering [SQLXML]
- XPath queries [SQLXML], location paths
- filtering [SQLXML]
- location path for XPath query
ms.assetid: dbef4cf4-a89b-4d7e-b72b-4062f7b29a80
author: rothja
ms.author: jroth
ms.openlocfilehash: d323558556fb05d350e48ea9218a8e9b8dc9b5c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673576"
---
# <a name="specifying-selection-predicates-in-the-location-path-sqlxml-40"></a><span data-ttu-id="23bfd-102">Especificar predicados de selección en la ruta de acceso de ubicación (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="23bfd-102">Specifying Selection Predicates in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="23bfd-103">Un predicado filtra un conjunto de nodos con respecto a un eje (similar a una cláusula WHERE en una instrucción SELECT).</span><span class="sxs-lookup"><span data-stu-id="23bfd-103">A predicate filters a node-set with respect to an axis (similar to a WHERE clause in a SELECT statement).</span></span> <span data-ttu-id="23bfd-104">El predicado se especifica entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="23bfd-104">The predicate is specified between brackets.</span></span> <span data-ttu-id="23bfd-105">Para cada nodo del conjunto de nodos que se va a filtrar, la expresión de predicado se evalúa con ese nodo como el nodo de contexto, con el número de nodos del conjunto de nodos como tamaño de contexto.</span><span class="sxs-lookup"><span data-stu-id="23bfd-105">For each node in the node-set to be filtered, the predicate expression is evaluated with that node as the context node, with the number of nodes in the node-set as context size.</span></span> <span data-ttu-id="23bfd-106">Si la expresión de predicado se evalúa como TRUE para ese nodo, el nodo se incluye en el conjunto de nodos resultante.</span><span class="sxs-lookup"><span data-stu-id="23bfd-106">If the predicate expression evaluates to TRUE for that node, the node is included in the resulting node-set.</span></span>  
  
 <span data-ttu-id="23bfd-107">XPath también permite el filtrado basado en posición.</span><span class="sxs-lookup"><span data-stu-id="23bfd-107">XPath also allows position-based filtering.</span></span> <span data-ttu-id="23bfd-108">Una expresión de predicado que se evalúa como un número selecciona ese nodo ordinal.</span><span class="sxs-lookup"><span data-stu-id="23bfd-108">A predicate expression evaluating to a number selects that ordinal node.</span></span> <span data-ttu-id="23bfd-109">Por ejemplo, la ruta de acceso de la ubicación `Customer[3]` devuelve el tercer cliente.</span><span class="sxs-lookup"><span data-stu-id="23bfd-109">For example, the location path `Customer[3]` returns the third customer.</span></span> <span data-ttu-id="23bfd-110">No se admiten tales predicados numéricos.</span><span class="sxs-lookup"><span data-stu-id="23bfd-110">Such numeric predicates are not supported.</span></span> <span data-ttu-id="23bfd-111">Solo se admiten expresiones de predicado que devuelven un resultado Booleano.</span><span class="sxs-lookup"><span data-stu-id="23bfd-111">Only predicate expressions that return a Boolean result are supported.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23bfd-112">Para obtener información acerca de las limitaciones de esta implementación XPath de XPath y las diferencias entre ella y la especificación W3C, vea [Introducción al uso de consultas xpath &#40;SQLXML 4,0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="23bfd-112">For information about the limitations of this XPath implementation of XPath and the differences between it and the W3C specification, see [Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span></span>  
  
## <a name="selection-predicate-example-1"></a><span data-ttu-id="23bfd-113">Predicado de selección: ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="23bfd-113">Selection Predicate: Example 1</span></span>  
 <span data-ttu-id="23bfd-114">La expresión XPath siguiente (ruta de acceso de ubicación) selecciona del nodo de contexto actual todos los **\<Customer>** elementos secundarios que tienen el atributo **CustomerID** con el valor ALFKI:</span><span class="sxs-lookup"><span data-stu-id="23bfd-114">The following XPath expression (location path) selects from the current context node all the **\<Customer>** element children that have the **CustomerID** attribute with value of ALFKI:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="ALFKI"]  
```  
  
 <span data-ttu-id="23bfd-115">En esta consulta XPath, `child` y `attribute` son nombres de eje.</span><span class="sxs-lookup"><span data-stu-id="23bfd-115">In this XPath query, `child` and `attribute` are axis names.</span></span> <span data-ttu-id="23bfd-116">`Customer`es la prueba de nodo (TRUE si `Customer` es **\<element node>** , porque **\<element>** es el tipo de nodo principal del `child` eje).</span><span class="sxs-lookup"><span data-stu-id="23bfd-116">`Customer` is the node test (TRUE if `Customer` is an **\<element node>**, because **\<element>** is the principal node type for the `child` axis).</span></span> <span data-ttu-id="23bfd-117">`attribute::CustomerID="ALFKI"` es el predicado.</span><span class="sxs-lookup"><span data-stu-id="23bfd-117">`attribute::CustomerID="ALFKI"` is the predicate.</span></span> <span data-ttu-id="23bfd-118">En el predicado, `attribute` es el eje y `CustomerID` es la prueba de nodo (true si **CustomerID** es un atributo del nodo de contexto, porque **\<attribute>** es el tipo de nodo principal del `attribute` eje).</span><span class="sxs-lookup"><span data-stu-id="23bfd-118">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an attribute of the context node, because **\<attribute>** is the principal node type of `attribute` axis).</span></span>  
  
 <span data-ttu-id="23bfd-119">Con la sintaxis abreviada, la consulta XPath también se puede especificar como:</span><span class="sxs-lookup"><span data-stu-id="23bfd-119">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer[@CustomerID="ALFKI"]  
```  
  
## <a name="selection-predicate-example-2"></a><span data-ttu-id="23bfd-120">Predicado de selección: ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="23bfd-120">Selection Predicate: Example 2</span></span>  
 <span data-ttu-id="23bfd-121">La expresión XPath siguiente (ruta de acceso de ubicación) selecciona del nodo de contexto actual todos los **\<Order>** descendientes que tienen el atributo **SalesOrderID** con el valor 1:</span><span class="sxs-lookup"><span data-stu-id="23bfd-121">The following XPath expression (location path) selects from the current context node all the **\<Order>** grandchildren that have the **SalesOrderID** attribute with the value 1:</span></span>  
  
```  
/child::Customer/child::Order[attribute::SalesOrderID="1"]  
```  
  
 <span data-ttu-id="23bfd-122">En esta expresión XPath, `child` y `attribute` son los nombres del eje.</span><span class="sxs-lookup"><span data-stu-id="23bfd-122">In this XPath expression, `child` and `attribute` are the axis names.</span></span> <span data-ttu-id="23bfd-123">`Customer`, `Order` y `SalesOrderID` son las pruebas de nodo.</span><span class="sxs-lookup"><span data-stu-id="23bfd-123">`Customer`, `Order`, and `SalesOrderID` are the node tests.</span></span> <span data-ttu-id="23bfd-124">`attribute::OrderID="1"` es el predicado.</span><span class="sxs-lookup"><span data-stu-id="23bfd-124">`attribute::OrderID="1"` is the predicate.</span></span>  
  
 <span data-ttu-id="23bfd-125">Con la sintaxis abreviada, la consulta XPath también se puede especificar como:</span><span class="sxs-lookup"><span data-stu-id="23bfd-125">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer/Order[@SalesOrderID="1"]  
```  
  
## <a name="selection-predicate-example-3"></a><span data-ttu-id="23bfd-126">Predicado de selección: ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="23bfd-126">Selection Predicate: Example 3</span></span>  
 <span data-ttu-id="23bfd-127">La expresión XPath siguiente (ruta de acceso de ubicación) selecciona del nodo de contexto actual todos los **\<Customer>** elementos secundarios que tienen uno o más **\<ContactName>** elementos secundarios:</span><span class="sxs-lookup"><span data-stu-id="23bfd-127">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children that have one or more **\<ContactName>** children:</span></span>  
  
```  
child::Customer[child::ContactName]  
```  
  
 <span data-ttu-id="23bfd-128">En este ejemplo se da por supuesto que **\<ContactName>** es un elemento secundario del **\<Customer>** elemento en el documento XML, al que se hace referencia como *asignación centrada en elementos* en un esquema XSD anotado.</span><span class="sxs-lookup"><span data-stu-id="23bfd-128">This example assumes that the **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, which is referred to as *element-centric mapping* in an annotated XSD schema.</span></span>  
  
 <span data-ttu-id="23bfd-129">En esta expresión XPath, `child` es el nombre de eje.</span><span class="sxs-lookup"><span data-stu-id="23bfd-129">In this XPath expression, `child` is the axis name.</span></span> <span data-ttu-id="23bfd-130">`Customer`es la prueba de nodo (TRUE si `Customer` es un **\<element>** nodo, porque **\<element>** es el tipo de nodo principal del `child` eje).</span><span class="sxs-lookup"><span data-stu-id="23bfd-130">`Customer` is the node test (TRUE if `Customer` is an **\<element>** node, because **\<element>** is the principal node type for `child` axis).</span></span> <span data-ttu-id="23bfd-131">`child::ContactName` es el predicado.</span><span class="sxs-lookup"><span data-stu-id="23bfd-131">`child::ContactName` is the predicate.</span></span> <span data-ttu-id="23bfd-132">En el predicado, `child` es el eje y `ContactName` es la prueba de nodo (true si `ContactName` es un **\<element>** nodo).</span><span class="sxs-lookup"><span data-stu-id="23bfd-132">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an **\<element>** node).</span></span>  
  
 <span data-ttu-id="23bfd-133">Esta expresión solo devuelve los elementos **\<Customer>** secundarios del nodo de contexto que tienen elementos **\<ContactName>** secundarios.</span><span class="sxs-lookup"><span data-stu-id="23bfd-133">This expression returns only the **\<Customer>** element children of the context node that have **\<ContactName>** element children.</span></span>  
  
 <span data-ttu-id="23bfd-134">Con la sintaxis abreviada, la consulta XPath también se puede especificar como:</span><span class="sxs-lookup"><span data-stu-id="23bfd-134">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[ContactName]  
```  
  
## <a name="selection-predicate-example-4"></a><span data-ttu-id="23bfd-135">Predicado de selección: ejemplo 4</span><span class="sxs-lookup"><span data-stu-id="23bfd-135">Selection Predicate: Example 4</span></span>  
 <span data-ttu-id="23bfd-136">La expresión XPath siguiente selecciona elementos **\<Customer>** secundarios del nodo de contexto que no tienen **\<ContactName>** elementos secundarios:</span><span class="sxs-lookup"><span data-stu-id="23bfd-136">The following XPath expression selects **\<Customer>** element children of the context node that do not have **\<ContactName>** element children:</span></span>  
  
```  
child::Customer[not(child::ContactName)]  
```  
  
 <span data-ttu-id="23bfd-137">En este ejemplo se da por supuesto que **\<ContactName>** es un elemento secundario del **\<Customer>** elemento en el documento XML y el campo ContactName no es necesario en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="23bfd-137">This example assumes that **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, and the ContactName field is not required in the database.</span></span>  
  
 <span data-ttu-id="23bfd-138">En este ejemplo, `child` es el eje.</span><span class="sxs-lookup"><span data-stu-id="23bfd-138">In this example, `child` is the axis.</span></span> <span data-ttu-id="23bfd-139">`Customer`es la prueba de nodo (TRUE si `Customer` es un \<element> nodo).</span><span class="sxs-lookup"><span data-stu-id="23bfd-139">`Customer` is the node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="23bfd-140">`not(child::ContactName)` es el predicado.</span><span class="sxs-lookup"><span data-stu-id="23bfd-140">`not(child::ContactName)` is the predicate.</span></span> <span data-ttu-id="23bfd-141">En el predicado, `child` es el eje y `ContactName` es la prueba de nodo (true si `ContactName` es un \<element> nodo).</span><span class="sxs-lookup"><span data-stu-id="23bfd-141">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an \<element> node).</span></span>  
  
 <span data-ttu-id="23bfd-142">Con la sintaxis abreviada, la consulta XPath también se puede especificar como:</span><span class="sxs-lookup"><span data-stu-id="23bfd-142">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[not(ContactName)]  
```  
  
## <a name="selection-predicate-example-5"></a><span data-ttu-id="23bfd-143">Predicado de selección: ejemplo 5</span><span class="sxs-lookup"><span data-stu-id="23bfd-143">Selection Predicate: Example 5</span></span>  
 <span data-ttu-id="23bfd-144">La expresión XPath siguiente selecciona del nodo de contexto actual todos los **\<Customer>** elementos secundarios que tienen el atributo **CustomerID** :</span><span class="sxs-lookup"><span data-stu-id="23bfd-144">The following XPath expression selects from the current context node all the **\<Customer>** children that have the **CustomerID** attribute:</span></span>  
  
```  
child::Customer[attribute::CustomerID]  
```  
  
 <span data-ttu-id="23bfd-145">En este ejemplo, `child` es el eje y `Customer` es la prueba de nodo (true si `Customer` es un \<element> nodo).</span><span class="sxs-lookup"><span data-stu-id="23bfd-145">In this example, `child` is the axis and `Customer` is node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="23bfd-146">`attribute::CustomerID` es el predicado.</span><span class="sxs-lookup"><span data-stu-id="23bfd-146">`attribute::CustomerID` is the predicate.</span></span> <span data-ttu-id="23bfd-147">En el predicado, `attribute` es el eje y `CustomerID` es el predicado (true si `CustomerID` es un **\<attribute>** nodo).</span><span class="sxs-lookup"><span data-stu-id="23bfd-147">In the predicate, `attribute` is the axis and `CustomerID` is the predicate (TRUE if `CustomerID` is an **\<attribute>** node).</span></span>  
  
 <span data-ttu-id="23bfd-148">Con la sintaxis abreviada, la consulta XPath también se puede especificar como:</span><span class="sxs-lookup"><span data-stu-id="23bfd-148">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[@CustomerID]  
```  
  
## <a name="selection-predicate-example-6"></a><span data-ttu-id="23bfd-149">Predicado de selección: Ejemplo 6</span><span class="sxs-lookup"><span data-stu-id="23bfd-149">Selection Predicate: Example 6</span></span>  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="23bfd-150">SQLXML 4.0 incluye compatibilidad para las consultas XPath que contienen un producto cruzado en el predicado, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23bfd-150">SQLXML 4.0 includes support for XPath queries that contain a cross-product in the predicate, as shown in the following example:</span></span>  
  
```  
Customer[Order/@OrderDate=Order/@ShipDate]  
```  
  
 <span data-ttu-id="23bfd-151">Esta consulta selecciona todos los clientes con algún elemento `Order` para el que `OrderDate` sea igual a `ShipDate` de cualquier `Order`.</span><span class="sxs-lookup"><span data-stu-id="23bfd-151">This query selects all customers with any `Order` for which the `OrderDate` equals the `ShipDate` of any `Order`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23bfd-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23bfd-152">See Also</span></span>  
 <span data-ttu-id="23bfd-153">[Introducción a los esquemas XSD anotados &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="23bfd-153">[Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="23bfd-154">Formato XML del lado cliente &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="23bfd-154">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
