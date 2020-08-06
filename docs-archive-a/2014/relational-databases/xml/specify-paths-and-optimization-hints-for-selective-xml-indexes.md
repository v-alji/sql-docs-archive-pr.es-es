---
title: Especificar rutas de acceso y sugerencias de optimización para índices XML selectivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 486ee339-165b-4aeb-b760-d2ba023d7d0a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a9d683fe57d489fdb9922b53d2c5c6825835216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747525"
---
# <a name="specify-paths-and-optimization-hints-for-selective-xml-indexes"></a><span data-ttu-id="f1c87-102">Especificar rutas de acceso y sugerencias de optimización para índices XML selectivos</span><span class="sxs-lookup"><span data-stu-id="f1c87-102">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>
  <span data-ttu-id="f1c87-103">En este tema se describe cómo especificar rutas de acceso del nodo al índice y sugerencias de optimización para indizar cuando se crean o modifican índices XML selectivos.</span><span class="sxs-lookup"><span data-stu-id="f1c87-103">This topic describes how to specify node paths to index and optimization hints for indexing when you create or alter selective XML indexes.</span></span>  
  
 <span data-ttu-id="f1c87-104">Especifique las rutas de acceso del nodo y las sugerencias de optimización al mismo tiempo en una de las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1c87-104">You specify node paths and optimization hints at the same time in one of the following statements:</span></span>  
  
-   <span data-ttu-id="f1c87-105">En la cláusula **FOR** de una instrucción **CREATE** .</span><span class="sxs-lookup"><span data-stu-id="f1c87-105">In the **FOR** clause of a **CREATE** statement.</span></span> <span data-ttu-id="f1c87-106">Para obtener más información, vea [CREAR ÍNDICE XML SELECTIVO &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f1c87-106">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="f1c87-107">En la cláusula **ADD** de una instrucción **ALTER** .</span><span class="sxs-lookup"><span data-stu-id="f1c87-107">In the **ADD** clause of an **ALTER** statement.</span></span> <span data-ttu-id="f1c87-108">Para obtener más información, vea [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="f1c87-108">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="f1c87-109">Para obtener más información sobre los índices XML selectivos, vea [Índices XML selectivos &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="f1c87-109">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="understanding-xquery-and-sql-server-types-in-untyped-xml"></a><a name="untyped"></a> <span data-ttu-id="f1c87-110">Descripción de los tipos de XQuery y SQL Server en XML sin tipo</span><span class="sxs-lookup"><span data-stu-id="f1c87-110">Understanding XQuery and SQL Server Types in Untyped XML</span></span>  
 <span data-ttu-id="f1c87-111">Los índices XML selectivos admiten dos sistemas de tipos: tipos XQuery y tipos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1c87-111">Selective XML indexes support two type systems: XQuery types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="f1c87-112">La ruta de acceso indizada se puede usar para buscar coincidencias con una expresión XQuery o para buscar coincidencias con el tipo de valor devuelto del método value() del tipo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="f1c87-112">The indexed path can be used either to match an XQuery expression, or to match the return type of the value() method of the XML data type.</span></span>  
  
-   <span data-ttu-id="f1c87-113">Si una ruta de acceso al índice no está anotada, o si está anotada con la palabra clave XQUERY, la ruta de acceso coincide con una expresión XQuery.</span><span class="sxs-lookup"><span data-stu-id="f1c87-113">When a path to index is not annotated, or is annotated with the XQUERY keyword, the path matches an XQuery expression.</span></span> <span data-ttu-id="f1c87-114">Hay dos variaciones de rutas de acceso del nodo con XQUERY:</span><span class="sxs-lookup"><span data-stu-id="f1c87-114">There are two variations for XQUERY-annotated node paths:</span></span>  
  
    -   <span data-ttu-id="f1c87-115">Si no especifica la palabra clave XQUERY y el tipo de datos XQuery, se usan las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="f1c87-115">If you do not specify the XQUERY keyword and the XQuery data type, then default mappings are used.</span></span> <span data-ttu-id="f1c87-116">Normalmente el rendimiento y el almacenamiento no son óptimos.</span><span class="sxs-lookup"><span data-stu-id="f1c87-116">Typically performance and storage are not optimal.</span></span>  
  
    -   <span data-ttu-id="f1c87-117">Si se especifica la palabra clave XQUERY y el tipo de datos XQuery, y opcionalmente otras sugerencias de optimización, puede obtener el mejor rendimiento y el almacenamiento más eficiente posibles.</span><span class="sxs-lookup"><span data-stu-id="f1c87-117">If you specify the XQUERY keyword and the XQuery data type, and optionally other optimization hints, then you can achieve the best possible performance and the most efficient possible storage.</span></span> <span data-ttu-id="f1c87-118">Sin embargo, una conversión puede producir un error.</span><span class="sxs-lookup"><span data-stu-id="f1c87-118">However, a cast can fail.</span></span>  
  
-   <span data-ttu-id="f1c87-119">Si una ruta de acceso al índice está anotada con la palabra clave SQL, la ruta de acceso coincide con el tipo de valor devuelto del método value() del tipo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="f1c87-119">When a path to index is annotated with the SQL keyword, the path matches the return type of the value() method of the XML data type.</span></span> <span data-ttu-id="f1c87-120">Especifique el tipo de datos adecuado de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , que es el tipo de valor devuelto que espera del método value().</span><span class="sxs-lookup"><span data-stu-id="f1c87-120">Specify the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, which is the return type that you expect from the value() method.</span></span>  
  
 <span data-ttu-id="f1c87-121">Hay sutiles diferencias entre el sistema de tipos XML de las expresiones XQuery y el sistema de tipos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se aplica al método value() del tipo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="f1c87-121">There are subtle differences between the XQuery expressions XML type system and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type system applied to the value() method of the XML data type.</span></span> <span data-ttu-id="f1c87-122">Entre estas diferencias cabe citar las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1c87-122">These differences include the following:</span></span>  
  
-   <span data-ttu-id="f1c87-123">El sistema de tipos XQuery reconoce los espacios finales.</span><span class="sxs-lookup"><span data-stu-id="f1c87-123">The XQuery type system is aware of trailing spaces.</span></span> <span data-ttu-id="f1c87-124">Por ejemplo, según la semántica de tipos XQuery, las cadenas "abc" y "abc " no son iguales, mientras que en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estas cadenas son iguales.</span><span class="sxs-lookup"><span data-stu-id="f1c87-124">For example, according to XQuery type semantics, the strings "abc" and "abc " are not equal, while in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] these strings are equal.</span></span>  
  
-   <span data-ttu-id="f1c87-125">Los tipos de datos de punto flotante XQuery admiten valores especiales de +/- cero y +/- infinito.</span><span class="sxs-lookup"><span data-stu-id="f1c87-125">XQuery floating point data types support special values of +/- zero and +/- infinity.</span></span> <span data-ttu-id="f1c87-126">Estos valores especiales no se admiten en los tipos de datos de punto flotante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1c87-126">These special values are not supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] floating point data types.</span></span>  
  
### <a name="xquery-types-in-untyped-xml"></a><span data-ttu-id="f1c87-127">Tipos XQuery en XML sin tipo</span><span class="sxs-lookup"><span data-stu-id="f1c87-127">XQuery Types in Untyped XML</span></span>  
  
-   <span data-ttu-id="f1c87-128">Los tipos XQuery coinciden con expresiones XQuery en todos los métodos del tipo de datos XML incluido el método value().</span><span class="sxs-lookup"><span data-stu-id="f1c87-128">XQuery types match XQuery expressions in all methods of the XML data type including the value() method.</span></span>  
  
-   <span data-ttu-id="f1c87-129">Los tipos XQuery admiten estas sugerencias de optimización: node(), SINGLETON, DATA TYPE y MAXLENGTH.</span><span class="sxs-lookup"><span data-stu-id="f1c87-129">XQuery types support these optimization hints: node(), SINGLETON, DATA TYPE, and MAXLENGTH.</span></span>  
  
 <span data-ttu-id="f1c87-130">Para las expresiones XQuery sobre XML sin tipo, puede elegir entre dos modos de funcionamiento:</span><span class="sxs-lookup"><span data-stu-id="f1c87-130">For XQuery expressions over untyped XML, you can choose between two modes of operation:</span></span>  
  
-   <span data-ttu-id="f1c87-131">**Modo de asignación predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="f1c87-131">**Default mapping mode**.</span></span> <span data-ttu-id="f1c87-132">En este modo, solo especifica la ruta de acceso al crear un índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-132">In this mode, you specify only the path when creating a selective XML index.</span></span>  
  
-   <span data-ttu-id="f1c87-133">**Modo de asignación especificada por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="f1c87-133">**User-specified mapping mode**.</span></span> <span data-ttu-id="f1c87-134">En este modo, especifica la ruta de acceso y las sugerencias opcionales de optimización.</span><span class="sxs-lookup"><span data-stu-id="f1c87-134">In this mode, you specify both the path and optional optimization hints.</span></span>  
  
 <span data-ttu-id="f1c87-135">El modo de asignación predeterminada emplea una opción de almacenamiento conservadora que siempre es segura y general.</span><span class="sxs-lookup"><span data-stu-id="f1c87-135">The default mapping mode uses a conservative storage option which is always safe and general.</span></span> <span data-ttu-id="f1c87-136">Puede coincidir con cualquier tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="f1c87-136">It can match any expression type.</span></span> <span data-ttu-id="f1c87-137">Una limitación del modo de asignación predeterminada es que el rendimiento no es óptimo, ya que se necesita un mayor número de conversiones en tiempo de ejecución y no hay índices secundarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="f1c87-137">A limitation of the default mapping mode is less than optimal performance, because an increased number of runtime casts are required, and secondary indexes are not available.</span></span>  
  
 <span data-ttu-id="f1c87-138">A continuación se muestra un ejemplo de un índice XML selectivo creado con las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="f1c87-138">Here is an example of a selective XML index created with default mappings.</span></span> <span data-ttu-id="f1c87-139">Para las tres rutas de acceso, se usa el tipo de nodo predeterminado (**xs:untypedAtomic**) y cardinalidad.</span><span class="sxs-lookup"><span data-stu-id="f1c87-139">For all three paths, the default node type (**xs:untypedAtomic**) and cardinality are used.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_default  
ON Tbl(xmlcol)  
FOR  
(  
mypath01 =  '/a/b',  
mypath02 = '/a/b/c',  
mypath03 = '/a/b/d'  
)  
```  
  
 <span data-ttu-id="f1c87-140">El modo de asignación especificada por el usuario permite especificar un tipo y la cardinalidad del nodo para obtener un rendimiento mejor.</span><span class="sxs-lookup"><span data-stu-id="f1c87-140">The user-specified mapping mode lets you specify a type and cardinality for the node to obtain better performance.</span></span> <span data-ttu-id="f1c87-141">Pero este rendimiento mejorado se obtiene a costa de la seguridad (porque una conversión puede producir un error) y la generalidad (porque solo se compara el tipo especificado con el índice XML selectivo).</span><span class="sxs-lookup"><span data-stu-id="f1c87-141">However, this improved performance is achieved by giving up safety - because a cast can fail - and generality - because only the specified type is matched with the selective XML index.</span></span>  
  
 <span data-ttu-id="f1c87-142">Los tipos XQuery admitidos para XML sin tipo son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1c87-142">The XQuery types supported for untyped XML case are:</span></span>  
  
-   <span data-ttu-id="f1c87-143">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="f1c87-143">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="f1c87-144">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="f1c87-144">**xs:double**</span></span>  
  
-   <span data-ttu-id="f1c87-145">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="f1c87-145">**xs:string**</span></span>  
  
-   <span data-ttu-id="f1c87-146">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="f1c87-146">**xs:date**</span></span>  
  
-   <span data-ttu-id="f1c87-147">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="f1c87-147">**xs:time**</span></span>  
  
-   <span data-ttu-id="f1c87-148">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="f1c87-148">**xs:dateTime**</span></span>  
  
 <span data-ttu-id="f1c87-149">Si no se especifica el tipo, se supone que el nodo tiene el tipo de datos **xs:untypedAtomic** .</span><span class="sxs-lookup"><span data-stu-id="f1c87-149">If the type is not specified, the node is assumed to be of the **xs:untypedAtomic** data type.</span></span>  
  
 <span data-ttu-id="f1c87-150">Puede optimizar el índice XML selectivo que se muestra de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1c87-150">You can optimize the selective XML index shown in the following manner:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_optimized  
ON Tbl(xmlcol)  
FOR  
(  
mypath= '/a/b' as XQUERY 'node()',  
pathX = '/a/b/c' as XQUERY 'xs:double' SINGLETON,  
pathY = '/a/b/d' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
)  
-- mypath - Only the node value is needed; storage is saved.  
-- pathX - Performance is improved; secondary indexes are possible.  
-- pathY - Performance is improved; secondary indexes are possible; storage is saved.  
```  
  
### <a name="sql-server-types-in-untyped-xml"></a><span data-ttu-id="f1c87-151">Tipos de SQL Server en XML sin tipo</span><span class="sxs-lookup"><span data-stu-id="f1c87-151">SQL Server Types in Untyped XML</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f1c87-152">los tipos coinciden con el valor devuelto del método value().</span><span class="sxs-lookup"><span data-stu-id="f1c87-152">types match the return value of the value() method.</span></span>  
  
-   <span data-ttu-id="f1c87-153">Los tipos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admiten esta sugerencia de optimización: SINGLETON.</span><span class="sxs-lookup"><span data-stu-id="f1c87-153">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types support this optimization hint: SINGLETON.</span></span>  
  
 <span data-ttu-id="f1c87-154">Es obligatorio especificar un tipo para las rutas de acceso que devuelven tipos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1c87-154">Specifying a type is mandatory for paths that return [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="f1c87-155">Use el mismo tipo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usaría en el método value().</span><span class="sxs-lookup"><span data-stu-id="f1c87-155">Use the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type that you would use in the value() method.</span></span>  
  
 <span data-ttu-id="f1c87-156">Considere la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="f1c87-156">Consider the following query:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/d)[1]', 'NVARCHAR(200)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="f1c87-157">La consulta especificada devuelve un valor de la ruta de acceso `/a/b/d` empaquetado en un tipos de datos NVARCHAR(200), por lo que el tipo de datos para especificar el nodo es obvio.</span><span class="sxs-lookup"><span data-stu-id="f1c87-157">The specified query returns a value from the path `/a/b/d` packed into an NVARCHAR(200) data type, so the data type to specify for the node is obvious.</span></span> <span data-ttu-id="f1c87-158">Sin embargo, no hay ningún esquema para especificar la cardinalidad del nodo en XML sin tipo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-158">However there is no schema to specify the cardinality of the node in untyped XML.</span></span> <span data-ttu-id="f1c87-159">Para especificar que el nodo `d` aparece como máximo una vez en su nodo primario `b`, cree un índice XML selectivo que use la sugerencia de optimización SINGLETON de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1c87-159">To specify that node `d` appears at most once under its parent node `b`, create a selective XML index that uses the SINGLETON optimization hint as follows:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_US  
ON Tbl(xmlcol)  
FOR  
(  
node1223 = '/a/b/d' as SQL NVARCHAR(200) SINGLETON  
)  
```  
  

  
##  <a name="understanding-selective-xml-index-support-for-typed-xml"></a><a name="typed"></a> <span data-ttu-id="f1c87-160">Descripción de la compatibilidad con índices XML selectivos para XML con tipo</span><span class="sxs-lookup"><span data-stu-id="f1c87-160">Understanding Selective XML Index support for typed XML</span></span>  
 <span data-ttu-id="f1c87-161">XML con tipo en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es un esquema asociado a un documento XML determinado.</span><span class="sxs-lookup"><span data-stu-id="f1c87-161">Typed XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is a schema associated with a given XML document.</span></span> <span data-ttu-id="f1c87-162">El esquema define la estructura global del documento y los tipos de nodos.</span><span class="sxs-lookup"><span data-stu-id="f1c87-162">The schema defines overall document structure and types of nodes.</span></span> <span data-ttu-id="f1c87-163">Si existe un esquema, el índice XML selectivo aplica la estructura del esquema cuando el usuario promueve rutas de acceso, por lo que no es necesario especificar los tipos XQUERY para las rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="f1c87-163">If a schema exists, Selective XML Index applies the schema structure when the user promotes paths, so there is no need to specify the XQUERY types for paths.</span></span>  
  
 <span data-ttu-id="f1c87-164">El índice XML selectivo admite los tipos XSD siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1c87-164">Selective XML Index supports following XSD types:</span></span>  
  
-   <span data-ttu-id="f1c87-165">**xs:anyUri**</span><span class="sxs-lookup"><span data-stu-id="f1c87-165">**xs:anyUri**</span></span>  
  
-   <span data-ttu-id="f1c87-166">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="f1c87-166">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="f1c87-167">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="f1c87-167">**xs:date**</span></span>  
  
-   <span data-ttu-id="f1c87-168">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="f1c87-168">**xs:dateTime**</span></span>  
  
-   <span data-ttu-id="f1c87-169">**xs:day**</span><span class="sxs-lookup"><span data-stu-id="f1c87-169">**xs:day**</span></span>  
  
-   <span data-ttu-id="f1c87-170">**xs:decimal**</span><span class="sxs-lookup"><span data-stu-id="f1c87-170">**xs:decimal**</span></span>  
  
-   <span data-ttu-id="f1c87-171">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="f1c87-171">**xs:double**</span></span>  
  
-   <span data-ttu-id="f1c87-172">**xs:float**</span><span class="sxs-lookup"><span data-stu-id="f1c87-172">**xs:float**</span></span>  
  
-   <span data-ttu-id="f1c87-173">**xs:int**</span><span class="sxs-lookup"><span data-stu-id="f1c87-173">**xs:int**</span></span>  
  
-   <span data-ttu-id="f1c87-174">**xs:integer**</span><span class="sxs-lookup"><span data-stu-id="f1c87-174">**xs:integer**</span></span>  
  
-   <span data-ttu-id="f1c87-175">**xs:language**</span><span class="sxs-lookup"><span data-stu-id="f1c87-175">**xs:language**</span></span>  
  
-   <span data-ttu-id="f1c87-176">**xs:long**</span><span class="sxs-lookup"><span data-stu-id="f1c87-176">**xs:long**</span></span>  
  
-   <span data-ttu-id="f1c87-177">**xs:name**</span><span class="sxs-lookup"><span data-stu-id="f1c87-177">**xs:name**</span></span>  
  
-   <span data-ttu-id="f1c87-178">**xs:NCName**</span><span class="sxs-lookup"><span data-stu-id="f1c87-178">**xs:NCName**</span></span>  
  
-   <span data-ttu-id="f1c87-179">**xs:negativeInteger**</span><span class="sxs-lookup"><span data-stu-id="f1c87-179">**xs:negativeInteger**</span></span>  
  
-   <span data-ttu-id="f1c87-180">**xs:nmtoken**</span><span class="sxs-lookup"><span data-stu-id="f1c87-180">**xs:nmtoken**</span></span>  
  
-   <span data-ttu-id="f1c87-181">**xs:nonNegativeInteger**</span><span class="sxs-lookup"><span data-stu-id="f1c87-181">**xs:nonNegativeInteger**</span></span>  
  
-   <span data-ttu-id="f1c87-182">**xs:nonPositiveInteger**</span><span class="sxs-lookup"><span data-stu-id="f1c87-182">**xs:nonPositiveInteger**</span></span>  
  
-   <span data-ttu-id="f1c87-183">**xs:positiveInteger**</span><span class="sxs-lookup"><span data-stu-id="f1c87-183">**xs:positiveInteger**</span></span>  
  
-   <span data-ttu-id="f1c87-184">**xs:qname**</span><span class="sxs-lookup"><span data-stu-id="f1c87-184">**xs:qname**</span></span>  
  
-   <span data-ttu-id="f1c87-185">**xs:short**</span><span class="sxs-lookup"><span data-stu-id="f1c87-185">**xs:short**</span></span>  
  
-   <span data-ttu-id="f1c87-186">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="f1c87-186">**xs:string**</span></span>  
  
-   <span data-ttu-id="f1c87-187">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="f1c87-187">**xs:time**</span></span>  
  
-   <span data-ttu-id="f1c87-188">**xs:token**</span><span class="sxs-lookup"><span data-stu-id="f1c87-188">**xs:token**</span></span>  
  
-   <span data-ttu-id="f1c87-189">**xs:unsignedByte**</span><span class="sxs-lookup"><span data-stu-id="f1c87-189">**xs:unsignedByte**</span></span>  
  
-   <span data-ttu-id="f1c87-190">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="f1c87-190">**xs:unsignedInt**</span></span>  
  
-   <span data-ttu-id="f1c87-191">**xs:unsignedLong**</span><span class="sxs-lookup"><span data-stu-id="f1c87-191">**xs:unsignedLong**</span></span>  
  
-   <span data-ttu-id="f1c87-192">**xs:unsignedShort**</span><span class="sxs-lookup"><span data-stu-id="f1c87-192">**xs:unsignedShort**</span></span>  
  
 <span data-ttu-id="f1c87-193">Cuando el índice XML selectivo se crea en un documento que tiene un esquema asociado, si se especifica un tipo XQUERY al crear o modificar el índice se devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="f1c87-193">When Selective XML Index is created over a document that has schema associated with it, specifying a XQUERY type at index creation or altering returns an error.</span></span> <span data-ttu-id="f1c87-194">El usuario puede emplear anotaciones de tipo SQL en la parte de promoción de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f1c87-194">The user can use SQL type annotations in the path promotion part.</span></span> <span data-ttu-id="f1c87-195">El tipo SQL debe ser una conversión válida del tipo XSD definido en el esquema o, de lo contrario, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="f1c87-195">The SQL type must be a valid conversion from the XSD type defined in the schema, or an error is thrown.</span></span> <span data-ttu-id="f1c87-196">Se admiten todos los tipos SQL que tienen una representación suficiente en XSD, salvo los tipos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="f1c87-196">All SQL types that have adequate representation in XSD are supported, with an exception of date/time types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1c87-197">El índice selectivo se usa si el tipo especificado en la promoción de ruta de acceso del índice XML selectivo es igual que el valor devuelto del método value().</span><span class="sxs-lookup"><span data-stu-id="f1c87-197">The selective index is used if the type specified in the Selective XML Index path promotion is the same as the value() method return value.</span></span>  
  
 <span data-ttu-id="f1c87-198">Se pueden usar las siguientes sugerencias de optimización con los documentos XML con tipo:</span><span class="sxs-lookup"><span data-stu-id="f1c87-198">The following optimization hints can be used with typed XML documents:</span></span>  
  
-   <span data-ttu-id="f1c87-199">Sugerencia de optimización node().</span><span class="sxs-lookup"><span data-stu-id="f1c87-199">node() optimization hint.</span></span>  
  
-   <span data-ttu-id="f1c87-200">La sugerencia de optimización MAXLENGTH se puede usar con tipos xs:string para acortar el valor indizado.</span><span class="sxs-lookup"><span data-stu-id="f1c87-200">MAXLENGTH optimization hint can be used with xs:string types to shorten the indexed value.</span></span>  
  
 <span data-ttu-id="f1c87-201">Para obtener más información acerca de las sugerencias de optimización, vea [Especificar sugerencias de optimización](#hints).</span><span class="sxs-lookup"><span data-stu-id="f1c87-201">For more information about optimization hints, see [Specifying Optimization Hints](#hints).</span></span>  
  
##  <a name="specifying-paths"></a><a name="paths"></a> <span data-ttu-id="f1c87-202">Especificar rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="f1c87-202">Specifying Paths</span></span>  
 <span data-ttu-id="f1c87-203">Un índice XML selectivo permite indizar solo un subconjunto de nodos de los datos XML almacenados que son pertinentes para las consultas que espera ejecutar.</span><span class="sxs-lookup"><span data-stu-id="f1c87-203">A selective XML index lets you index only a subset of nodes from the stored XML data that are relevant for the queries that you expect to run.</span></span> <span data-ttu-id="f1c87-204">Cuando el subconjunto de nodos pertinentes es mucho menor que el número total de nodos del documento XML, el índice XML selectivo solo almacena los nodos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="f1c87-204">When the subset of relevant nodes is much smaller than the total number of nodes in the XML document, the selective XML index stores only the relevant nodes.</span></span> <span data-ttu-id="f1c87-205">Para beneficiarse de un índice XML selectivo, identifique el subconjunto correcto de nodos para indizar.</span><span class="sxs-lookup"><span data-stu-id="f1c87-205">To benefit from a selective XML index, identify the correct subset of nodes to index.</span></span>  
  
### <a name="choosing-the-nodes-to-index"></a><span data-ttu-id="f1c87-206">Elegir los nodos para indizar</span><span class="sxs-lookup"><span data-stu-id="f1c87-206">Choosing the nodes to index</span></span>  
 <span data-ttu-id="f1c87-207">Puede usar los dos principios simples siguientes para identificar el subconjunto correcto de nodos para agregar un índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-207">You can use the following two simple principles to identify the correct subset of nodes to add to a selective XML index.</span></span>  
  
1.  <span data-ttu-id="f1c87-208">**Principio 1**: para evaluar una expresión XQuery especificada, indice todos los nodos que necesite examinar.</span><span class="sxs-lookup"><span data-stu-id="f1c87-208">**Principle 1**: To evaluate a given XQuery expression, index all nodes that you need to examine.</span></span>  
  
    -   <span data-ttu-id="f1c87-209">Indice todos los nodos cuya existencia o valor se emplee en la expresión XQuery.</span><span class="sxs-lookup"><span data-stu-id="f1c87-209">Index all nodes whose existence or value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="f1c87-210">Indice todos los nodos de la expresión XQuery en la que se aplican los predicados XQuery.</span><span class="sxs-lookup"><span data-stu-id="f1c87-210">Index all nodes in the XQuery expression on which XQuery predicates are applied.</span></span>  
  
     <span data-ttu-id="f1c87-211">Examine la consulta simple siguiente sobre el [documento XML de ejemplo](#sample) de este tema:</span><span class="sxs-lookup"><span data-stu-id="f1c87-211">Consider the following simple query over the [sample XML document](#sample) in this topic:</span></span>  
  
    ```sql  
    SELECT T.record FROM myXMLTable T  
    WHERE T.xmldata.exist('/a/b[./c = "43"]') = 1  
    ```  
  
     <span data-ttu-id="f1c87-212">Para devolver las instancias XML que cumplen esta consulta, un índice XML selectivo necesita examinar dos nodos en cada instancia XML:</span><span class="sxs-lookup"><span data-stu-id="f1c87-212">In order to return the XML instances that satisfy this query, a selective XML index needs to examine two nodes in every XML instance:</span></span>  
  
    -   <span data-ttu-id="f1c87-213">Nodo `c`, porque su valor se emplea en la expresión XQuery.</span><span class="sxs-lookup"><span data-stu-id="f1c87-213">Node `c`, because its value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="f1c87-214">Nodo `b`, porque se aplica un predicado sobre el nodo`b` en la expresión XQuery.</span><span class="sxs-lookup"><span data-stu-id="f1c87-214">Node `b`, because a predicate is applied over node`b` in the XQuery expression.</span></span>  
  
2.  <span data-ttu-id="f1c87-215">**Principio 2:** para obtener el máximo rendimiento, indice todos los nodos que sean necesarios para evaluar una expresión XQuery dada.</span><span class="sxs-lookup"><span data-stu-id="f1c87-215">**Principle 2**: For best performance, index all nodes that are required to evaluate a given XQuery expression.</span></span> <span data-ttu-id="f1c87-216">Si solo indiza algunos de los nodos, el índice XML selectivo mejora la evaluación de las subexpresiones que incluyen solo nodos indizados.</span><span class="sxs-lookup"><span data-stu-id="f1c87-216">If you index only some of the nodes, then the selective XML index improves the evaluation of sub-expressions that include only indexed nodes.</span></span>  
  
 <span data-ttu-id="f1c87-217">Para mejorar el rendimiento de la instrucción SELECT mostrada anteriormente, puede crear el índice XML selectivo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1c87-217">To improve the performance of the SELECT statement shown above, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX simple_sxi  
ON Tbl(xmlcol)  
FOR  
(  
    path123 =  '/a/b',  
    path124 =  '/a/b/c'  
)  
```  
  
### <a name="indexing-identical-paths"></a><span data-ttu-id="f1c87-218">Indizar rutas de acceso idénticas</span><span class="sxs-lookup"><span data-stu-id="f1c87-218">Indexing identical paths</span></span>  
 <span data-ttu-id="f1c87-219">No puede promover rutas de acceso idénticas como el mismo tipo de datos con nombres de ruta de acceso diferentes.</span><span class="sxs-lookup"><span data-stu-id="f1c87-219">You cannot promote identical paths as the same data type under different path names.</span></span> <span data-ttu-id="f1c87-220">Por ejemplo, la consulta siguiente genera un error porque `pathOne` y `pathTwo` son idénticas:</span><span class="sxs-lookup"><span data-stu-id="f1c87-220">For example, the following query raises an error, because `pathOne` and `pathTwo` are identical:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:string',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
 <span data-ttu-id="f1c87-221">Sin embargo, puede promover rutas de acceso idénticas como tipos de datos diferentes con nombres distintos.</span><span class="sxs-lookup"><span data-stu-id="f1c87-221">However, you can promote identical paths as different data types with different names.</span></span> <span data-ttu-id="f1c87-222">Por ejemplo, la consulta siguiente ahora es aceptable porque los tipos de datos son diferentes:</span><span class="sxs-lookup"><span data-stu-id="f1c87-222">For example, the following query is now acceptable, because the data types are different:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:double',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
### <a name="examples"></a><span data-ttu-id="f1c87-223">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f1c87-223">Examples</span></span>  
 <span data-ttu-id="f1c87-224">A continuación se muestran algunos ejemplos adicionales de cómo seleccionar los nodos correctos para indizar para diferentes tipos XQuery.</span><span class="sxs-lookup"><span data-stu-id="f1c87-224">Here are some additional examples of selecting the correct nodes to index for different XQuery types.</span></span>  
  
 <span data-ttu-id="f1c87-225">**Ejemplo 1**</span><span class="sxs-lookup"><span data-stu-id="f1c87-225">**Example 1**</span></span>  
  
 <span data-ttu-id="f1c87-226">Esta es una expresión XQuery simple que usa el método exist():</span><span class="sxs-lookup"><span data-stu-id="f1c87-226">Here is a simple XQuery that uses the exist() method:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e/h') = 1  
```  
  
 <span data-ttu-id="f1c87-227">En la tabla siguiente se muestran los nodos que se deben indizar para permitir que esta consulta use el índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-227">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="f1c87-228">Nodo para incluir en el índice</span><span class="sxs-lookup"><span data-stu-id="f1c87-228">Node to include in the index</span></span>|<span data-ttu-id="f1c87-229">Motivo para indizar este nodo</span><span class="sxs-lookup"><span data-stu-id="f1c87-229">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="f1c87-230">**/a/b/c/d/e/h**</span><span class="sxs-lookup"><span data-stu-id="f1c87-230">**/a/b/c/d/e/h**</span></span>|<span data-ttu-id="f1c87-231">La existencia del nodo `h` se evalúa en el método exist().</span><span class="sxs-lookup"><span data-stu-id="f1c87-231">The existence of node `h` is evaluated in the exist() method.</span></span>|  
  
 <span data-ttu-id="f1c87-232">**Ejemplo 2**</span><span class="sxs-lookup"><span data-stu-id="f1c87-232">**Example 2**</span></span>  
  
 <span data-ttu-id="f1c87-233">Esta es una variación más compleja de la expresión XQuery anterior a la que se ha aplicado un predicado:</span><span class="sxs-lookup"><span data-stu-id="f1c87-233">Here is a more complex variation of the previous XQuery, with a predicate applied:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e[./f = "SQL"]') = 1  
```  
  
 <span data-ttu-id="f1c87-234">En la tabla siguiente se muestran los nodos que se deben indizar para permitir que esta consulta use el índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-234">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="f1c87-235">Nodo para incluir en el índice</span><span class="sxs-lookup"><span data-stu-id="f1c87-235">Node to include in the index</span></span>|<span data-ttu-id="f1c87-236">Motivo para indizar este nodo</span><span class="sxs-lookup"><span data-stu-id="f1c87-236">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="f1c87-237">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="f1c87-237">**/a/b/c/d/e**</span></span>|<span data-ttu-id="f1c87-238">Se aplica un predicado sobre el nodo `e`.</span><span class="sxs-lookup"><span data-stu-id="f1c87-238">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="f1c87-239">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="f1c87-239">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="f1c87-240">El valor del nodo `f` se evalúa dentro del predicado.</span><span class="sxs-lookup"><span data-stu-id="f1c87-240">The value of node `f` is evaluated inside the predicate.</span></span>|  
  
 <span data-ttu-id="f1c87-241">**Ejemplo 3**</span><span class="sxs-lookup"><span data-stu-id="f1c87-241">**Example 3**</span></span>  
  
 <span data-ttu-id="f1c87-242">Esta es una consulta más compleja con una cláusula value():</span><span class="sxs-lookup"><span data-stu-id="f1c87-242">Here is a more complex query with a value() clause:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/c/d/e[./f = "SQL"]/g)[1]', 'nvarchar(100)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="f1c87-243">En la tabla siguiente se muestran los nodos que se deben indizar para permitir que esta consulta use el índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-243">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="f1c87-244">Nodo para incluir en el índice</span><span class="sxs-lookup"><span data-stu-id="f1c87-244">Node to include in the index</span></span>|<span data-ttu-id="f1c87-245">Motivo para indizar este nodo</span><span class="sxs-lookup"><span data-stu-id="f1c87-245">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="f1c87-246">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="f1c87-246">**/a/b/c/d/e**</span></span>|<span data-ttu-id="f1c87-247">Se aplica un predicado sobre el nodo `e`.</span><span class="sxs-lookup"><span data-stu-id="f1c87-247">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="f1c87-248">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="f1c87-248">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="f1c87-249">El valor del nodo `f` se evalúa dentro del predicado.</span><span class="sxs-lookup"><span data-stu-id="f1c87-249">The value of node `f` is evaluated inside the predicate.</span></span>|  
|<span data-ttu-id="f1c87-250">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="f1c87-250">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="f1c87-251">El método value() devuelve el valor del nodo `g` .</span><span class="sxs-lookup"><span data-stu-id="f1c87-251">The value of node `g` is returned by the value() method.</span></span>|  
  
 <span data-ttu-id="f1c87-252">**Ejemplo 4**</span><span class="sxs-lookup"><span data-stu-id="f1c87-252">**Example 4**</span></span>  
  
 <span data-ttu-id="f1c87-253">Esta es una consulta que usa una cláusula FLWOR dentro de una cláusula exist().</span><span class="sxs-lookup"><span data-stu-id="f1c87-253">Here is a query that uses a FLWOR clause inside an exist() clause.</span></span> <span data-ttu-id="f1c87-254">(El nombre FLWOR proviene de las cinco cláusulas que pueden crear una expresión FLWOR de XQuery: for, let, where, order by y return).</span><span class="sxs-lookup"><span data-stu-id="f1c87-254">(The name FLWOR comes from the five clauses that can make up an XQuery FLWOR expression: for, let, where, order by, and return.)</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('  
  For $x in /a/b/c/d/e  
  Where $x/f = "SQL"  
  Return $x/g  
') = 1  
```  
  
 <span data-ttu-id="f1c87-255">En la tabla siguiente se muestran los nodos que se deben indizar para permitir que esta consulta use el índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-255">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="f1c87-256">Nodo para incluir en el índice</span><span class="sxs-lookup"><span data-stu-id="f1c87-256">Node to include in the index</span></span>|<span data-ttu-id="f1c87-257">Motivo para indizar este nodo</span><span class="sxs-lookup"><span data-stu-id="f1c87-257">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="f1c87-258">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="f1c87-258">**/a/b/c/d/e**</span></span>|<span data-ttu-id="f1c87-259">La existencia del nodo `e` se evalúa en la cláusula FLWOR.</span><span class="sxs-lookup"><span data-stu-id="f1c87-259">The existence of node `e` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="f1c87-260">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="f1c87-260">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="f1c87-261">El valor del nodo `f` se evalúa en la cláusula FLWOR.</span><span class="sxs-lookup"><span data-stu-id="f1c87-261">The value of node `f` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="f1c87-262">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="f1c87-262">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="f1c87-263">El método exist() evalúa la existencia del nodo `g` .</span><span class="sxs-lookup"><span data-stu-id="f1c87-263">The existence of node `g` is evaluated by the exist() method.</span></span>|  
  

  
##  <a name="specifying-optimization-hints"></a><a name="hints"></a> <span data-ttu-id="f1c87-264">Especificar sugerencias de optimización</span><span class="sxs-lookup"><span data-stu-id="f1c87-264">Specifying Optimization Hints</span></span>  
 <span data-ttu-id="f1c87-265">Puede usar sugerencias opcionales de optimización para especificar detalles de asignación adicionales para un nodo indizado mediante un índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-265">You can use optional optimization hints to specify additional mapping details for a node indexed by a selective XML index.</span></span> <span data-ttu-id="f1c87-266">Por ejemplo, puede especificar el tipo de datos y la cardinalidad del nodo, así como cierta información sobre la estructura de los datos.</span><span class="sxs-lookup"><span data-stu-id="f1c87-266">For example, you can specify the data type and cardinality of the node, and certain information about the structure of the data.</span></span> <span data-ttu-id="f1c87-267">Esta información adicional admite una mejor asignación.</span><span class="sxs-lookup"><span data-stu-id="f1c87-267">This additional information supports better mapping.</span></span> <span data-ttu-id="f1c87-268">También consigue mejoras en el rendimiento, ahorros de almacenamiento o ambos.</span><span class="sxs-lookup"><span data-stu-id="f1c87-268">It also results in improvements in performance or savings in storage, or both.</span></span>  
  
 <span data-ttu-id="f1c87-269">El uso de sugerencias de optimización es opcional.</span><span class="sxs-lookup"><span data-stu-id="f1c87-269">The use of optimization hints is optional.</span></span> <span data-ttu-id="f1c87-270">Siempre puede aceptar las asignaciones predeterminadas, que son confiables pero no puede proporcionar un rendimiento y un almacenamiento óptimos.</span><span class="sxs-lookup"><span data-stu-id="f1c87-270">You can always accept the default mappings, which are reliable but may not provide optimal performance and storage.</span></span>  
  
 <span data-ttu-id="f1c87-271">Algunas sugerencias de optimización (por ejemplo, la sugerencia SINGLETON) presentan restricciones sobre los datos.</span><span class="sxs-lookup"><span data-stu-id="f1c87-271">Some optimization hints - for example, the SINGLETON hint - introduce constraints over your data.</span></span> <span data-ttu-id="f1c87-272">En algunos casos, se pueden producir errores cuando esas restricciones no se cumplen.</span><span class="sxs-lookup"><span data-stu-id="f1c87-272">In some cases, errors may be raised when those constraints are not met.</span></span>  
  
### <a name="benefits-of-optimization-hints"></a><span data-ttu-id="f1c87-273">Ventajas de las sugerencias de optimización</span><span class="sxs-lookup"><span data-stu-id="f1c87-273">Benefits of Optimization Hints</span></span>  
 <span data-ttu-id="f1c87-274">En la tabla siguiente se identifican las sugerencias de optimización que admiten un almacenamiento o un rendimiento más eficiente.</span><span class="sxs-lookup"><span data-stu-id="f1c87-274">The following table identifies the optimization hints that support more efficient storage or improved performance.</span></span>  
  
|<span data-ttu-id="f1c87-275">Sugerencia de optimización</span><span class="sxs-lookup"><span data-stu-id="f1c87-275">Optimization hint</span></span>|<span data-ttu-id="f1c87-276">Almacenamiento más eficiente</span><span class="sxs-lookup"><span data-stu-id="f1c87-276">More efficient storage</span></span>|<span data-ttu-id="f1c87-277">rendimiento mejorado.</span><span class="sxs-lookup"><span data-stu-id="f1c87-277">Improved performance</span></span>|  
|-----------------------|----------------------------|--------------------------|  
|<span data-ttu-id="f1c87-278">**node()**</span><span class="sxs-lookup"><span data-stu-id="f1c87-278">**node()**</span></span>|<span data-ttu-id="f1c87-279">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-279">Yes</span></span>|<span data-ttu-id="f1c87-280">No</span><span class="sxs-lookup"><span data-stu-id="f1c87-280">No</span></span>|  
|<span data-ttu-id="f1c87-281">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="f1c87-281">**SINGLETON**</span></span>|<span data-ttu-id="f1c87-282">No</span><span class="sxs-lookup"><span data-stu-id="f1c87-282">No</span></span>|<span data-ttu-id="f1c87-283">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-283">Yes</span></span>|  
|<span data-ttu-id="f1c87-284">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="f1c87-284">**DATA TYPE**</span></span>|<span data-ttu-id="f1c87-285">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-285">Yes</span></span>|<span data-ttu-id="f1c87-286">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-286">Yes</span></span>|  
|<span data-ttu-id="f1c87-287">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="f1c87-287">**MAXLENGTH**</span></span>|<span data-ttu-id="f1c87-288">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-288">Yes</span></span>|<span data-ttu-id="f1c87-289">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-289">Yes</span></span>|  
  
### <a name="optimization-hints-and-data-types"></a><span data-ttu-id="f1c87-290">Sugerencias de optimización y tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f1c87-290">Optimization Hints and Data Types</span></span>  
 <span data-ttu-id="f1c87-291">Puede indizar nodos como tipos de datos XQuery o como tipos de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1c87-291">You can index nodes as XQuery data types or as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="f1c87-292">En la tabla siguiente se muestran las sugerencias de optimización que se admiten con cada tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f1c87-292">The following table shows which optimization hints are supported with each data type.</span></span>  
  
|<span data-ttu-id="f1c87-293">Sugerencia de optimización</span><span class="sxs-lookup"><span data-stu-id="f1c87-293">Optimization hint</span></span>|<span data-ttu-id="f1c87-294">Tipos de datos XQuery</span><span class="sxs-lookup"><span data-stu-id="f1c87-294">XQuery data types</span></span>|<span data-ttu-id="f1c87-295">Tipos de datos SQL</span><span class="sxs-lookup"><span data-stu-id="f1c87-295">SQL data types</span></span>|  
|-----------------------|-----------------------|--------------------|  
|<span data-ttu-id="f1c87-296">**node()**</span><span class="sxs-lookup"><span data-stu-id="f1c87-296">**node()**</span></span>|<span data-ttu-id="f1c87-297">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-297">Yes</span></span>|<span data-ttu-id="f1c87-298">No</span><span class="sxs-lookup"><span data-stu-id="f1c87-298">No</span></span>|  
|<span data-ttu-id="f1c87-299">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="f1c87-299">**SINGLETON**</span></span>|<span data-ttu-id="f1c87-300">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-300">Yes</span></span>|<span data-ttu-id="f1c87-301">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-301">Yes</span></span>|  
|<span data-ttu-id="f1c87-302">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="f1c87-302">**DATA TYPE**</span></span>|<span data-ttu-id="f1c87-303">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-303">Yes</span></span>|<span data-ttu-id="f1c87-304">No</span><span class="sxs-lookup"><span data-stu-id="f1c87-304">No</span></span>|  
|<span data-ttu-id="f1c87-305">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="f1c87-305">**MAXLENGTH**</span></span>|<span data-ttu-id="f1c87-306">Sí</span><span class="sxs-lookup"><span data-stu-id="f1c87-306">Yes</span></span>|<span data-ttu-id="f1c87-307">No</span><span class="sxs-lookup"><span data-stu-id="f1c87-307">No</span></span>|  
  
### <a name="node-optimization-hint"></a><span data-ttu-id="f1c87-308">Sugerencia de optimización node()</span><span class="sxs-lookup"><span data-stu-id="f1c87-308">node() optimization hint</span></span>  
 <span data-ttu-id="f1c87-309">Se aplica a: Tipos de datos XQuery</span><span class="sxs-lookup"><span data-stu-id="f1c87-309">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="f1c87-310">Puede usar la optimización node() para especificar un nodo cuyo valor no es necesario para evaluar la consulta típica.</span><span class="sxs-lookup"><span data-stu-id="f1c87-310">You can use the node() optimization to specify a node whose value is not required to evaluate the typical query.</span></span> <span data-ttu-id="f1c87-311">Esta sugerencia reduce los requisitos de almacenamiento cuando la consulta típica solo tiene que evaluar la existencia del nodo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-311">This hint reduces storage requirements when the typical query only has to evaluate the existence of the node.</span></span> <span data-ttu-id="f1c87-312">(De forma predeterminada, un índice XML selectivo almacena el valor para todos los nodos promovidos, excepto para los tipos de nodos complejos).</span><span class="sxs-lookup"><span data-stu-id="f1c87-312">(By default, a selective XML index stores the value for all promoted nodes, except complex node types.)</span></span>  
  
 <span data-ttu-id="f1c87-313">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1c87-313">Consider the following example:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b[./c=5]') = 1  
```  
  
 <span data-ttu-id="f1c87-314">Para usar un índice XML selectivo con el fin de evaluar esta consulta, promueva los nodos `b` y `c`.</span><span class="sxs-lookup"><span data-stu-id="f1c87-314">To use a selective XML index to evaluate this query, promote nodes `b` and `c`.</span></span> <span data-ttu-id="f1c87-315">Sin embargo, puesto que el valor del nodo `b` no es necesario, puede usar la sugerencia node() con la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f1c87-315">However, since the value of node `b` is not required, you can use the node() hint with the following syntax:</span></span>  
  
 `/a/b/ as node()`  
  
 <span data-ttu-id="f1c87-316">Si una consulta necesita el valor de un nodo que se ha indizado con la sugerencia node(), no se puede usar el índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-316">If a query requires the value of a node that has been indexed with the node() hint, then the selective XML index cannot be used.</span></span>  
  
### <a name="singleton-optimization-hint"></a><span data-ttu-id="f1c87-317">Sugerencia de optimización SINGLETON</span><span class="sxs-lookup"><span data-stu-id="f1c87-317">SINGLETON optimization hint</span></span>  
 <span data-ttu-id="f1c87-318">Se aplica a: tipos de datos XQuery o de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c87-318">Applies to: XQuery or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types</span></span>  
  
 <span data-ttu-id="f1c87-319">La sugerencia de optimización SINGLETON especifica la cardinalidad de un nodo.</span><span class="sxs-lookup"><span data-stu-id="f1c87-319">The SINGLETON optimization hint specifies the cardinality of a node.</span></span> <span data-ttu-id="f1c87-320">Esta sugerencia mejora el rendimiento de las consultas porque se sabe de antemano que un nodo aparece como máximo una vez dentro de su elemento primario o antecesor.</span><span class="sxs-lookup"><span data-stu-id="f1c87-320">This hint improves query performance since it is known in advance that a node appears at most one time within its parent or ancestor.</span></span>  
  
 <span data-ttu-id="f1c87-321">Examine el [documento XML de ejemplo](#sample) de este tema.</span><span class="sxs-lookup"><span data-stu-id="f1c87-321">Consider the [sample XML document](#sample) in this topic.</span></span>  
  
 <span data-ttu-id="f1c87-322">Para usar un índice XML selectivo con el fin de consultar este documento, puede especificar la sugerencia SINGLETON para el nodo `d` puesto que aparece como máximo una vez dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="f1c87-322">To use a selective XML index to query this document, you can specify the SINGLETON hint for node `d` since it appears at most one time within its parent.</span></span>  
  
 <span data-ttu-id="f1c87-323">Si se ha especificado la sugerencia SINGLETON, pero un nodo aparece más de una vez dentro de su elemento primario o antecesor, se generará un error cuando cree el índice (para datos existentes) o cuando ejecute una consulta (para datos nuevos).</span><span class="sxs-lookup"><span data-stu-id="f1c87-323">If the SINGLETON hint has been specified, but a node appears more than one time within its parent or ancestor, then an error is raised when you create the index (for existing data) or when you run a query (for new data).</span></span>  
  
### <a name="data-type-optimization-hint"></a><span data-ttu-id="f1c87-324">Sugerencia de optimización DATA TYPE</span><span class="sxs-lookup"><span data-stu-id="f1c87-324">DATA TYPE optimization hint</span></span>  
 <span data-ttu-id="f1c87-325">Se aplica a: Tipos de datos XQuery</span><span class="sxs-lookup"><span data-stu-id="f1c87-325">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="f1c87-326">La sugerencia de optimización DATA TYPE permite especificar un tipo de datos XQuery o de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para el nodo indizado.</span><span class="sxs-lookup"><span data-stu-id="f1c87-326">The DATA TYPE optimization hint lets you specify an XQuery or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for the indexed node.</span></span> <span data-ttu-id="f1c87-327">El tipo de datos se usa para la columna de la tabla de datos del índice XML selectivo correspondiente al nodo indizado.</span><span class="sxs-lookup"><span data-stu-id="f1c87-327">The data type is used for the column in the data table of the selective XML index that corresponds to the indexed node.</span></span>  
  
 <span data-ttu-id="f1c87-328">Al convertir un valor existente al tipo de datos especificado se produce un error y la operación de inserción (en el índice) funciona correctamente; sin embargo, se inserta un valor NULL en la tabla de datos del índice.</span><span class="sxs-lookup"><span data-stu-id="f1c87-328">When casting an existing value to the specified data type fails, the insert operation (into the index) does not fail; however, a null value is inserted into the data table of the index.</span></span>  
  
### <a name="maxlength-optimization-hint"></a><span data-ttu-id="f1c87-329">Sugerencia de optimización MAXLENGTH</span><span class="sxs-lookup"><span data-stu-id="f1c87-329">MAXLENGTH optimization hint</span></span>  
 <span data-ttu-id="f1c87-330">Se aplica a: Tipos de datos XQuery</span><span class="sxs-lookup"><span data-stu-id="f1c87-330">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="f1c87-331">La sugerencia de optimización MAXLENGTH permite limitar la longitud de datos xs:string.</span><span class="sxs-lookup"><span data-stu-id="f1c87-331">The MAXLENGTH optimization hint lets you limit the length of xs:string data.</span></span> <span data-ttu-id="f1c87-332">MAXLENGTH no es pertinente para los tipos de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ya que especifica la longitud al especificar los tipos de fecha VARCHAR o NVARCHAR.</span><span class="sxs-lookup"><span data-stu-id="f1c87-332">MAXLENGTH is not relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types since you specify the length when you specify the VARCHAR or NVARCHAR date types.</span></span>  
  
 <span data-ttu-id="f1c87-333">Cuando una cadena existente es más larga que el valor de MAXLENGTH especificado, se produce un error al insertar el valor en el índice.</span><span class="sxs-lookup"><span data-stu-id="f1c87-333">When an existing string is longer than the specified MAXLENGTH, then inserting that value into the index fails.</span></span>  
  

  
##  <a name="sample-xml-document-for-examples"></a><a name="sample"></a> <span data-ttu-id="f1c87-334">Documento XML de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1c87-334">Sample XML Document for Examples</span></span>  
 <span data-ttu-id="f1c87-335">En los ejemplos de este tema se hace referencia al documento XML de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1c87-335">The following sample XML document is referenced in the examples in this topic:</span></span>  
  
```xml  
<a>  
    <b>  
         <c atc="aa">10</c>  
         <c atc="bb">15</c>  
         <d atd1="dd" atd2="ddd">md </d>  
    </b>  
     <b>  
        <c></c>  
        <c atc="">117</c>  
     </b>  
</a>  
```  
  

  
## <a name="see-also"></a><span data-ttu-id="f1c87-336">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1c87-336">See Also</span></span>  
 <span data-ttu-id="f1c87-337">[Índices XML selectivos &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span><span class="sxs-lookup"><span data-stu-id="f1c87-337">[Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span></span>  
 [<span data-ttu-id="f1c87-338">Crear, modificar y quitar índices XML selectivos</span><span class="sxs-lookup"><span data-stu-id="f1c87-338">Create, Alter, and Drop Selective XML Indexes</span></span>](../xml/create-alter-and-drop-selective-xml-indexes.md)  
  
  
