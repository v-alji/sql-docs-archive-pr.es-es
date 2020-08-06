---
title: Índices XML selectivos (SXI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 598ecdcd-084b-4032-81b2-eed6ae9f5d44
author: rothja
ms.author: jroth
ms.openlocfilehash: 37dd72c5de2892672dc9f63066075ab5e770d758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677448"
---
# <a name="selective-xml-indexes-sxi"></a><span data-ttu-id="60d3e-102">Índices XML selectivos (SXI)</span><span class="sxs-lookup"><span data-stu-id="60d3e-102">Selective XML Indexes (SXI)</span></span>
  <span data-ttu-id="60d3e-103">Los índices XML selectivos son otro tipo de índice XML disponible además de los índices XML normales.</span><span class="sxs-lookup"><span data-stu-id="60d3e-103">Selective XML indexes are another type of XML index that is available to you in addition to ordinary XML indexes.</span></span> <span data-ttu-id="60d3e-104">Los objetivos de la característica de índice XML selectivo son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="60d3e-104">The goals of the selective XML index feature are the following:</span></span>  
  
-   <span data-ttu-id="60d3e-105">Mejorar el rendimiento de las consultas sobre datos XML almacenados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60d3e-105">To improve the performance of queries over XML data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="60d3e-106">Admitir una indización más rápida de cargas de trabajo grandes de datos XML.</span><span class="sxs-lookup"><span data-stu-id="60d3e-106">To support faster indexing of large XML data workloads.</span></span>  
  
-   <span data-ttu-id="60d3e-107">Mejorar la escalabilidad reduciendo los costos de almacenamiento de los índices XML.</span><span class="sxs-lookup"><span data-stu-id="60d3e-107">To improve scalability by reducing the storage costs of XML indexes.</span></span>  
  
 <span data-ttu-id="60d3e-108">La limitación principal de los índices XML normales es que indizan el documento XML completo.</span><span class="sxs-lookup"><span data-stu-id="60d3e-108">The main limitation with ordinary XML indexes is that they index the entire XML document.</span></span> <span data-ttu-id="60d3e-109">Este conduce a varias desventajas importantes, como el menor rendimiento de las consultas y el mayor costo de mantenimiento de los índices, que están relacionadas principalmente con los costos de almacenamiento del índice.</span><span class="sxs-lookup"><span data-stu-id="60d3e-109">This leads to several significant drawbacks, such as decreased query performance and increased index maintenance cost, mostly related to the storage costs of the index.</span></span>  
  
 <span data-ttu-id="60d3e-110">La característica de índice XML selectivo le permite promover solo ciertas rutas de acceso de los documentos XML al índice.</span><span class="sxs-lookup"><span data-stu-id="60d3e-110">The selective XML index feature lets you promote only certain paths from the XML documents to index.</span></span> <span data-ttu-id="60d3e-111">En el momento de la creación del índice se evalúan estas rutas de acceso, y los nodos a los que señalan se dividen y se almacenan en una tabla relacional en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60d3e-111">At index creation time, these paths are evaluated, and the nodes that they point to are shredded and stored inside a relational table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="60d3e-112">Esta característica emplea un algoritmo de asignación eficiente desarrollado por [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research en colaboración con el equipo del producto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60d3e-112">This feature uses an efficient mapping algorithm developed by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research in collaboration with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product team.</span></span> <span data-ttu-id="60d3e-113">Este algoritmo asigna los nodos XML a una única tabla relacional, y consigue un rendimiento excepcional y solo necesita una cantidad modesta de espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="60d3e-113">This algorithm maps the XML nodes to a single relational table, and achieves exceptional performance while requiring only modest storage space.</span></span>  
  
 <span data-ttu-id="60d3e-114">La característica de índice XML selectivo también admite índices XML selectivos secundarios sobre nodos que se han indizado mediante un índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="60d3e-114">The selective XML index feature also supports secondary selective XML indexes over nodes that have been indexed by a selective XML index.</span></span> <span data-ttu-id="60d3e-115">Estos índices selectivos secundarios son eficaces y mejoran aún más el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="60d3e-115">These secondary selective indexes are efficient and further improve the performance of queries.</span></span>  
  
##  <a name="benefits-of-selective-xml-indexes"></a><a name="benefits"></a> <span data-ttu-id="60d3e-116">Ventajas de los índices XML selectivos</span><span class="sxs-lookup"><span data-stu-id="60d3e-116">Benefits of Selective XML Indexes</span></span>  
 <span data-ttu-id="60d3e-117">Los índices XML selectivos proporcionan las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="60d3e-117">Selective XML indexes provide the following benefits:</span></span>  
  
1.  <span data-ttu-id="60d3e-118">Rendimiento de consultas mejorado considerablemente sobre el tipo de datos XML para cargas típicos de consulta.</span><span class="sxs-lookup"><span data-stu-id="60d3e-118">Greatly improved query performance over the XML data type for typical query loads.</span></span>  
  
2.  <span data-ttu-id="60d3e-119">Menores requisitos de almacenamiento en comparación con los índices XML normales.</span><span class="sxs-lookup"><span data-stu-id="60d3e-119">Reduced storage requirements compared to ordinary XML indexes.</span></span>  
  
3.  <span data-ttu-id="60d3e-120">Menores costos de mantenimiento de índices en comparación con los índices XML normales.</span><span class="sxs-lookup"><span data-stu-id="60d3e-120">Reduced index maintenance costs compared to ordinary XML indexes.</span></span>  
  
4.  <span data-ttu-id="60d3e-121">No es necesario actualizar las aplicaciones para beneficiarse de los índices XML selectivos.</span><span class="sxs-lookup"><span data-stu-id="60d3e-121">No need to update applications to benefit from selective XML indexes.</span></span>  
  

  
##  <a name="selective-xml-indexes-and-primary-xml-indexes"></a><a name="compare"></a> <span data-ttu-id="60d3e-122">Índices XML selectivos e índices XML principales</span><span class="sxs-lookup"><span data-stu-id="60d3e-122">Selective XML Indexes and Primary XML Indexes</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="60d3e-123">Cree un índice XML selectivo en lugar de un índice XML normal en la mayoría de los casos para mejorar el rendimiento y lograr un almacenamiento más eficiente.</span><span class="sxs-lookup"><span data-stu-id="60d3e-123">Create a selective XML index instead of an ordinary XML index in most cases for better performance and more efficient storage.</span></span>  
  
 <span data-ttu-id="60d3e-124">Sin embargo, no se recomienda usar un índice XML selectivo cuando alguna de las condiciones siguientes sea verdadera:</span><span class="sxs-lookup"><span data-stu-id="60d3e-124">However, a selective XML index is not recommended when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="60d3e-125">Asigne un gran número de rutas de acceso del nodo.</span><span class="sxs-lookup"><span data-stu-id="60d3e-125">You map a large number of node paths.</span></span>  
  
-   <span data-ttu-id="60d3e-126">Admita consultas para elementos desconocidos o elementos de una ubicación desconocida en la estructura del documento.</span><span class="sxs-lookup"><span data-stu-id="60d3e-126">You support queries for unknown elements or elements in an unknown location in the document structure.</span></span>  
  

  
##  <a name="simple-example-of-a-selective-xml-index"></a><a name="example"></a> <span data-ttu-id="60d3e-127">Ejemplo simple de un índice XML selectivo</span><span class="sxs-lookup"><span data-stu-id="60d3e-127">Simple Example of a Selective XML Index</span></span>  
 <span data-ttu-id="60d3e-128">Considere el siguiente fragmento XML como un documento XML de una tabla de aproximadamente 500.000 filas:</span><span class="sxs-lookup"><span data-stu-id="60d3e-128">Consider the following XML fragment as an XML document in a table of approximately 500,000 rows:</span></span>  
  
```xml  
<book>  
    <created>2004-03-01</created>   
    <authors>Various</authors>  
    <subjects>  
        <subject>English wit and humor -- Periodicals</subject>  
        <subject>AP</subject>   
    </subjects>  
    <title>Punch, or the London Charivari, Volume 156, April 2, 1919</title>  
    <id>etext11617</id>  
</book>  
```  
  
 <span data-ttu-id="60d3e-129">Crear un índice XML principal sobre tantas filas de este esquema simple lleva mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="60d3e-129">Creating a primary XML index over so many rows of this simple schema takes a long time.</span></span> <span data-ttu-id="60d3e-130">La consulta de estos datos también se resiente del hecho de que un índice XML principal no admite la indización selectiva.</span><span class="sxs-lookup"><span data-stu-id="60d3e-130">Querying this data also suffers from the fact that a primary XML index does not support selective indexing.</span></span>  
  
 <span data-ttu-id="60d3e-131">Si solo necesita consultar estos datos sobre la ruta de acceso `/book/title` y la ruta de acceso `/book/subjects` , puede crear el índice XML selectivo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60d3e-131">If you only need to query this data over the `/book/title` path and the `/book/subjects` path, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX SXI_index  
ON Tbl(xmlcol)  
FOR   
(  
    pathTitle = '/book/title/text()' AS XQUERY 'xs:string',   
    pathAuthors = '/book/authors' AS XQUERY 'node()',  
    pathId = '/book/id' AS SQL NVARCHAR(100)  
)  
```  
  
 <span data-ttu-id="60d3e-132">La instrucción anterior es un buen ejemplo de sintaxis de CREATE que se usa cuando se crea un índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="60d3e-132">The preceding statement is a good example of the CREATE syntax that you use when you create a selective XML index.</span></span> <span data-ttu-id="60d3e-133">En la instrucción CREATE, primero debe proporcionar un nombre para el índice e identificar la tabla y la columna XML para indizar.</span><span class="sxs-lookup"><span data-stu-id="60d3e-133">In the CREATE statement, first you provide a name for the index and identify the table and the XML column to index.</span></span> <span data-ttu-id="60d3e-134">A continuación se proporcionan las rutas de acceso al índice.</span><span class="sxs-lookup"><span data-stu-id="60d3e-134">Then you provide the paths to index.</span></span> <span data-ttu-id="60d3e-135">Una ruta de acceso consta de tres partes:</span><span class="sxs-lookup"><span data-stu-id="60d3e-135">A path has three parts:</span></span>  
  
1.  <span data-ttu-id="60d3e-136">Un nombre que identifica de forma única la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="60d3e-136">A name that uniquely identifies the path.</span></span>  
  
2.  <span data-ttu-id="60d3e-137">Una expresión XQuery que describe la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="60d3e-137">An XQuery expression that describes the path.</span></span>  
  
3.  <span data-ttu-id="60d3e-138">Sugerencias opcionales de optimización.</span><span class="sxs-lookup"><span data-stu-id="60d3e-138">Optional optimization hints.</span></span>  
  
 <span data-ttu-id="60d3e-139">Para obtener más información acerca de estos elementos, vea [Tareas relacionadas](#reltasks).</span><span class="sxs-lookup"><span data-stu-id="60d3e-139">For more information about these elements, see [Related Tasks](#reltasks).</span></span>  
  

  
## <a name="supported-features-prerequisites-and-limitations"></a><span data-ttu-id="60d3e-140">Características admitidas, requisitos previos y limitaciones</span><span class="sxs-lookup"><span data-stu-id="60d3e-140">Supported Features, Prerequisites, and Limitations</span></span>  
  
###  <a name="supported-xml-features"></a><a name="features"></a> <span data-ttu-id="60d3e-141">Características XML admitidas</span><span class="sxs-lookup"><span data-stu-id="60d3e-141">Supported XML Features</span></span>  
 <span data-ttu-id="60d3e-142">Los índices XML selectivos admiten XQuery admitido por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dentro de los métodos exist(), value() y nodes().</span><span class="sxs-lookup"><span data-stu-id="60d3e-142">Selective XML indexes support the XQuery supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inside the exist(), value() and nodes() methods.</span></span>  
  
-   <span data-ttu-id="60d3e-143">Para los métodos exist(), value() y nodes(), los índices XML selectivos contienen información suficiente para transformar toda la expresión.</span><span class="sxs-lookup"><span data-stu-id="60d3e-143">For the exist(), value() and nodes() methods, selective XML indexes contain enough information to transform the entire expression.</span></span>  
  
-   <span data-ttu-id="60d3e-144">En el caso de los métodos query() y modify(), los índices XML selectivos solo se pueden usar para el filtrado de nodos.</span><span class="sxs-lookup"><span data-stu-id="60d3e-144">For the query() and modify() methods, selective XML indexes may be used for node filtering only.</span></span>  
  
-   <span data-ttu-id="60d3e-145">Para el método query(), no se usan índices XML selectivos para recuperar resultados.</span><span class="sxs-lookup"><span data-stu-id="60d3e-145">For the query() method, selective XML indexes are not used to retrieve results.</span></span>  
  
-   <span data-ttu-id="60d3e-146">Para el método modify(), no se usan índices XML selectivos para actualizar documentos XML.</span><span class="sxs-lookup"><span data-stu-id="60d3e-146">For the modify() method, selective XML indexes are not used to update XML documents.</span></span>  
  

  
###  <a name="unsupported-xml-features"></a><a name="unsupported"></a> <span data-ttu-id="60d3e-147">Características XML no admitidas</span><span class="sxs-lookup"><span data-stu-id="60d3e-147">Unsupported XML Features</span></span>  
 <span data-ttu-id="60d3e-148">Los índices XML selectivos no admiten las siguientes características compatibles con la implementación de XML de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="60d3e-148">Selective XML indexes do not support the following features that are supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implementation of XML:</span></span>  
  
-   <span data-ttu-id="60d3e-149">Indizar nodos con tipos XS complejos: tipos de unión, tipos de secuencia y tipos de lista.</span><span class="sxs-lookup"><span data-stu-id="60d3e-149">Indexing of nodes with complex XS types: union types, sequence types, and list types.</span></span>  
  
-   <span data-ttu-id="60d3e-150">Indizar nodos con tipos XS binarios: por ejemplo, base64Binary y hexBinary.</span><span class="sxs-lookup"><span data-stu-id="60d3e-150">Indexing of nodes with binary XS types: for example, base64Binary and hexBinary.</span></span>  
  
-   <span data-ttu-id="60d3e-151">Especificar los nodos para indizar con expresiones XPath que contienen el carácter comodín `*` al final, por ejemplo, `/a/b/c/*`, `/a//b/*`o `/a/b/*:c`.</span><span class="sxs-lookup"><span data-stu-id="60d3e-151">Specifying the nodes to index with XPath expressions that contain the wildcard character `*` at the end: For example,  `/a/b/c/*`, `/a//b/*`, or `/a/b/*:c`.</span></span>  
  
-   <span data-ttu-id="60d3e-152">Indizar cualquier eje distinto de secundario, atributo o descendiente.</span><span class="sxs-lookup"><span data-stu-id="60d3e-152">Indexing any axis other than child, attribute, or descendant.</span></span> <span data-ttu-id="60d3e-153">El caso `//<step>` se permite como un caso especial.</span><span class="sxs-lookup"><span data-stu-id="60d3e-153">The `//<step>` case is allowed as a special case.</span></span>  
  
-   <span data-ttu-id="60d3e-154">Indizar instrucciones de procesamiento y comentarios XML.</span><span class="sxs-lookup"><span data-stu-id="60d3e-154">Indexing of XML processing instructions and comments.</span></span>  
  
-   <span data-ttu-id="60d3e-155">Especificar y recuperar el identificador de un nodo mediante la función id().</span><span class="sxs-lookup"><span data-stu-id="60d3e-155">Specifying and retrieving the identifier for a node by using the id() function.</span></span>  
  

  
###  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="60d3e-156">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="60d3e-156">Prerequisites</span></span>  
 <span data-ttu-id="60d3e-157">Los siguientes requisitos previos deben existir antes de poder crear un índice XML selectivo en una columna XML en una tabla de usuario:</span><span class="sxs-lookup"><span data-stu-id="60d3e-157">The following prerequisites must exist before you can create a selective XML index over an XML column in a user table:</span></span>  
  
-   <span data-ttu-id="60d3e-158">Debe existir un índice clúster en la clave principal de la tabla de usuario.</span><span class="sxs-lookup"><span data-stu-id="60d3e-158">A clustered index must exist on the primary key of the user table.</span></span>  
  
-   <span data-ttu-id="60d3e-159">La clave principal de la tabla de usuario está limitada a un tamaño de 128 bytes cuando se usa con índices XML selectivos.</span><span class="sxs-lookup"><span data-stu-id="60d3e-159">The primary key of the user table is limited to a size of 128 bytes when used with selective XML indexes.</span></span>  
  
-   <span data-ttu-id="60d3e-160">La clave de agrupación de la tabla de usuario está limitada a 15 columnas cuando se usa con índices XML selectivos.</span><span class="sxs-lookup"><span data-stu-id="60d3e-160">The clustering key of the user table is limited to 15 columns when used with selective XML indexes.</span></span>  
  

  
###  <a name="limitations"></a><a name="limits"></a> <span data-ttu-id="60d3e-161">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="60d3e-161">Limitations</span></span>  
 <span data-ttu-id="60d3e-162">**Requisitos generales y limitaciones**</span><span class="sxs-lookup"><span data-stu-id="60d3e-162">**General requirements and limitations**</span></span>  
  
-   <span data-ttu-id="60d3e-163">Cada índice XML selectivo solamente puede crearse en una única columna XML.</span><span class="sxs-lookup"><span data-stu-id="60d3e-163">Each selective XML index can only be created on a single XML column.</span></span>  
  
-   <span data-ttu-id="60d3e-164">No puede crear un índice XML selectivo en una columna que no sea XML.</span><span class="sxs-lookup"><span data-stu-id="60d3e-164">You cannot create a selective XML index on a non-XML column.</span></span>  
  
-   <span data-ttu-id="60d3e-165">Cada columna XML de una tabla solo puede tener un índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="60d3e-165">Each XML column in a table can have only one selective XML index.</span></span>  
  
-   <span data-ttu-id="60d3e-166">Cada tabla puede tener hasta 249 índices XML selectivos.</span><span class="sxs-lookup"><span data-stu-id="60d3e-166">Each table can have up to 249 selective XML indexes.</span></span>  
  
 <span data-ttu-id="60d3e-167">**Limitaciones sobre objetos admitidos**</span><span class="sxs-lookup"><span data-stu-id="60d3e-167">**Limitations on supported objects**</span></span>  
  
 <span data-ttu-id="60d3e-168">No puede crear índices XML selectivos en los objetos siguientes:</span><span class="sxs-lookup"><span data-stu-id="60d3e-168">You cannot create selective XML indexes on the following objects:</span></span>  
  
1.  <span data-ttu-id="60d3e-169">Columnas XML de una vista.</span><span class="sxs-lookup"><span data-stu-id="60d3e-169">XML columns in a view.</span></span>  
  
2.  <span data-ttu-id="60d3e-170">Variable con valores de tabla con columnas XML.</span><span class="sxs-lookup"><span data-stu-id="60d3e-170">Table-valued variable with XML columns.</span></span>  
  
3.  <span data-ttu-id="60d3e-171">Variables de tipo XML.</span><span class="sxs-lookup"><span data-stu-id="60d3e-171">XML type variables.</span></span>  
  
4.  <span data-ttu-id="60d3e-172">Columnas XML calculadas.</span><span class="sxs-lookup"><span data-stu-id="60d3e-172">Computed XML columns.</span></span>  
  
5.  <span data-ttu-id="60d3e-173">Columnas XML con una profundidad de más de 128 nodos anidados.</span><span class="sxs-lookup"><span data-stu-id="60d3e-173">XML columns with a depth of more than 128 nested nodes.</span></span>  
  
 <span data-ttu-id="60d3e-174">**Limitaciones relativas al almacenamiento**</span><span class="sxs-lookup"><span data-stu-id="60d3e-174">**Limitations related to storage**</span></span>  
  
 <span data-ttu-id="60d3e-175">Hay un límite finito en cuanto al número de nodos del documento XML que se pueden agregar al índice.</span><span class="sxs-lookup"><span data-stu-id="60d3e-175">There is a finite limit on the number of nodes from the XML document that can be added to the index.</span></span> <span data-ttu-id="60d3e-176">Un índice XML selectivo asigna documentos XML a una única tabla relacional.</span><span class="sxs-lookup"><span data-stu-id="60d3e-176">A selective XML index maps XML documents to a single relational table.</span></span> <span data-ttu-id="60d3e-177">Por tanto, no puede tener más de 1024 columnas no NULL en ninguna fila especificada de la tabla.</span><span class="sxs-lookup"><span data-stu-id="60d3e-177">Therefore it cannot have more than 1024 non-null columns in any given row of the table.</span></span> <span data-ttu-id="60d3e-178">Además, muchas de las limitaciones de las columnas dispersas también se aplican a los índices XML selectivos, ya que los índices usan columnas dispersas para el almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="60d3e-178">Furthermore, many of the limitations of sparse columns also apply to selective XML indexes, because the indexes use sparse columns for storage.</span></span>  
  
 <span data-ttu-id="60d3e-179">El número máximo de columnas no NULL no admitidas en una fila determinada depende del tamaño de los datos de las columnas:</span><span class="sxs-lookup"><span data-stu-id="60d3e-179">The maximum number of non-null columns supported in any given row depends on the size of the data in the columns:</span></span>  
  
-   <span data-ttu-id="60d3e-180">En el mejor de los casos, se admiten 1024 columnas no NULL cuando todas las columnas son de tipo **bit**.</span><span class="sxs-lookup"><span data-stu-id="60d3e-180">In the best case, 1024 non-null columns are supported when all columns are of type **bit**.</span></span>  
  
-   <span data-ttu-id="60d3e-181">En el peor de los casos, solo se admiten 236 columnas no NULL cuando todas las columnas son objetos grandes de tipo **varchar**.</span><span class="sxs-lookup"><span data-stu-id="60d3e-181">In the worst case, only 236 non-null columns are supported when all columns are large objects of type **varchar**.</span></span>  
  
 <span data-ttu-id="60d3e-182">Los índices XML selectivos usan de uno a cuatro columnas internamente para cada ruta de acceso del nodo que se indiza.</span><span class="sxs-lookup"><span data-stu-id="60d3e-182">Selective XML indexes use from one to four columns internally for every node path that is indexed.</span></span> <span data-ttu-id="60d3e-183">El número total de nodos que se pueden indizar oscila desde 60 hasta varios cientos de nodos, según el tamaño real de los datos de las rutas de acceso indizadas.</span><span class="sxs-lookup"><span data-stu-id="60d3e-183">The total number of nodes that can be indexed ranges from 60 to several hundred nodes, depending on the actual size of the data in the indexed paths.</span></span>  
  
-   <span data-ttu-id="60d3e-184">En el peor de los casos, cuando se asignan algunos o todos los nodos usando `//` en la definición de ruta de acceso del nodo, el número máximo de nodos indizados es 60.</span><span class="sxs-lookup"><span data-stu-id="60d3e-184">In the worst case, when some or all nodes are mapped using `//` in the node path definition, the maximum number of indexed nodes is 60.</span></span>  
  
-   <span data-ttu-id="60d3e-185">En el mejor de los casos, cuando se asignan nodos sin usar `//` en la definición de ruta de acceso del nodo, el número máximo de nodos indizados es 200.</span><span class="sxs-lookup"><span data-stu-id="60d3e-185">In the best case, when nodes are mapped without using `//` in the node path definition, the maximum number of indexed nodes is 200.</span></span>  
  
 <span data-ttu-id="60d3e-186">**Los índices XML selectivos se vuelven a generar al crear (con CREATE) o modificar (con ALTER) el índice.**</span><span class="sxs-lookup"><span data-stu-id="60d3e-186">**Selective XML indexes are rebuilt when you CREATE or ALTER the index.**</span></span>  
  
 <span data-ttu-id="60d3e-187">Cuando usa CREATE o ALTER en un índice XML selectivo, se vuelve a generar en modo uniproceso sin conexión.</span><span class="sxs-lookup"><span data-stu-id="60d3e-187">When you CREATE or ALTER a selective XML index, it is rebuilt in a single-threaded, offline mode.</span></span> <span data-ttu-id="60d3e-188">Con frecuencia las instrucciones ALTER afectan negativamente al rendimiento de las consultas sobre los documentos XML indizados.</span><span class="sxs-lookup"><span data-stu-id="60d3e-188">Frequently ALTER statements negatively affect the performance of queries over the indexed XML documents.</span></span>  
  
 <span data-ttu-id="60d3e-189">**Otras limitaciones**</span><span class="sxs-lookup"><span data-stu-id="60d3e-189">**Other limitations**</span></span>  
  
-   <span data-ttu-id="60d3e-190">Los índices XML selectivos no se admiten en sugerencias de consulta.</span><span class="sxs-lookup"><span data-stu-id="60d3e-190">Selective XML indexes are not supported in query hints.</span></span>  
  
-   <span data-ttu-id="60d3e-191">Los índices XML selectivos y los índices XML selectivos secundarios no se admiten en el Asistente para la optimización de base de datos.</span><span class="sxs-lookup"><span data-stu-id="60d3e-191">Selective XML indexes and secondary selective XML indexes are not supported in Database Tuning Advisor.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="60d3e-192">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="60d3e-192">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60d3e-193">**Task**</span><span class="sxs-lookup"><span data-stu-id="60d3e-193">**Task**</span></span>|<span data-ttu-id="60d3e-194">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="60d3e-194">**Topic**</span></span>|  
|<span data-ttu-id="60d3e-195">Especificar las rutas de acceso del nodo que desea indizar y las sugerencias opcionales de optimización cuando cree o modifique un índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="60d3e-195">Specify the node paths that you want to index and optional optimization hints when you create or alter a selective XML index.</span></span>|[<span data-ttu-id="60d3e-196">Especificar rutas de acceso y sugerencias de optimización para índices XML selectivos</span><span class="sxs-lookup"><span data-stu-id="60d3e-196">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>](specify-paths-and-optimization-hints-for-selective-xml-indexes.md)|  
|<span data-ttu-id="60d3e-197">Crear, modificar o quitar un índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="60d3e-197">Create, alter, or drop a selective XML index.</span></span>|[<span data-ttu-id="60d3e-198">Crear, modificar y quitar índices XML selectivos</span><span class="sxs-lookup"><span data-stu-id="60d3e-198">Create, Alter, and Drop Selective XML Indexes</span></span>](create-alter-and-drop-selective-xml-indexes.md)|  
|<span data-ttu-id="60d3e-199">Crear, modificar o quitar un índice XML selectivo secundario.</span><span class="sxs-lookup"><span data-stu-id="60d3e-199">Create, alter, or drop a secondary selective XML index.</span></span>|[<span data-ttu-id="60d3e-200">Crear, modificar y quitar índices XML selectivos secundarios</span><span class="sxs-lookup"><span data-stu-id="60d3e-200">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>](create-alter-and-drop-secondary-selective-xml-indexes.md)|  
  

  
  
