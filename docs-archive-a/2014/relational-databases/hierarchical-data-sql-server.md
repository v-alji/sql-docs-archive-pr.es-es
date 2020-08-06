---
title: Datos jerárquicos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [SQL Server], tables to support
- hierarchyid [Database Engine], concepts
- hierarchical tables [Database Engine]
- SqlHierarchyId
- hierarchyid [Database Engine]
- hierarchical queries [SQL Server], using hierarchyid data type
ms.assetid: 19aefa9a-fbc2-4b22-92cf-67b8bb01671c
author: rothja
ms.author: jroth
ms.openlocfilehash: 351a5a4aa6bc1655b8da5fced3e51385dd498bdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671994"
---
# <a name="hierarchical-data-sql-server"></a><span data-ttu-id="fd383-102">Datos jerárquicos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fd383-102">Hierarchical Data (SQL Server)</span></span>
  <span data-ttu-id="fd383-103">El `hierarchyid` tipo de datos integrado facilita el almacenamiento y la consulta de datos jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="fd383-103">The built-in `hierarchyid` data type makes it easier to store and query hierarchical data.</span></span> <span data-ttu-id="fd383-104">`hierarchyid`está optimizado para representar árboles, que son el tipo más común de datos jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="fd383-104">`hierarchyid` is optimized for representing trees, which are the most common type of hierarchical data.</span></span>  
  
 <span data-ttu-id="fd383-105">Los datos jerárquicos se definen como un conjunto de elementos de datos que se relacionan entre sí mediante relaciones jerárquicas.</span><span class="sxs-lookup"><span data-stu-id="fd383-105">Hierarchical data is defined as a set of data items that are related to each other by hierarchical relationships.</span></span> <span data-ttu-id="fd383-106">Las relaciones jerárquicas existen allí donde un elemento de los datos es el elemento primario de otro elemento.</span><span class="sxs-lookup"><span data-stu-id="fd383-106">Hierarchical relationships exist where one item of data is the parent of another item.</span></span> <span data-ttu-id="fd383-107">Entre los ejemplos de datos jerárquicos que se almacenan normalmente en las bases de datos se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd383-107">Examples of the hierarchical data that is commonly stored in databases include the following:</span></span>  
  
-   <span data-ttu-id="fd383-108">Una estructura organizativa</span><span class="sxs-lookup"><span data-stu-id="fd383-108">An organizational structure</span></span>  
  
-   <span data-ttu-id="fd383-109">Un sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="fd383-109">A file system</span></span>  
  
-   <span data-ttu-id="fd383-110">Un conjunto de tareas de un proyecto</span><span class="sxs-lookup"><span data-stu-id="fd383-110">A set of tasks in a project</span></span>  
  
-   <span data-ttu-id="fd383-111">Una taxonomía de términos de idioma</span><span class="sxs-lookup"><span data-stu-id="fd383-111">A taxonomy of language terms</span></span>  
  
-   <span data-ttu-id="fd383-112">Un gráfico de vínculos entre páginas web</span><span class="sxs-lookup"><span data-stu-id="fd383-112">A graph of links between Web pages</span></span>  
  
 <span data-ttu-id="fd383-113">Use [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) como tipo de datos para crear tablas con una estructura jerárquica o para describir la estructura jerárquica de datos almacenados en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="fd383-113">Use [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) as a data type to create tables with a hierarchical structure, or to describe the hierarchical structure of data that is stored in another location.</span></span> <span data-ttu-id="fd383-114">Use las [funciones hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) de [!INCLUDE[tsql](../includes/tsql-md.md)] para consultar y administrar los datos jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="fd383-114">Use the [hierarchyid functions](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) in [!INCLUDE[tsql](../includes/tsql-md.md)] to query and manage hierarchical data.</span></span>  
  
##  <a name="key-properties-of-hierarchyid"></a><a name="keyprops"></a> <span data-ttu-id="fd383-115">Propiedades principales de hierarchyid</span><span class="sxs-lookup"><span data-stu-id="fd383-115">Key Properties of hierarchyid</span></span>  
 <span data-ttu-id="fd383-116">Un valor del tipo de datos `hierarchyid` representa una posición en una jerarquía de árbol.</span><span class="sxs-lookup"><span data-stu-id="fd383-116">A value of the `hierarchyid` data type represents a position in a tree hierarchy.</span></span> <span data-ttu-id="fd383-117">Los valores de `hierarchyid` tienen las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="fd383-117">Values for `hierarchyid` have the following properties:</span></span>  
  
-   <span data-ttu-id="fd383-118">Muy compactos</span><span class="sxs-lookup"><span data-stu-id="fd383-118">Extremely compact</span></span>  
  
     <span data-ttu-id="fd383-119">El número medio de bits necesarios para representar un nodo en un árbol con *n* nodos depende del promedio de distribución ramificada secundarios (el promedio de elementos secundarios de un nodo).</span><span class="sxs-lookup"><span data-stu-id="fd383-119">The average number of bits that are required to represent a node in a tree with *n* nodes depends on the average fanout (the average number of children of a node).</span></span> <span data-ttu-id="fd383-120">Para distribuciones ramificadas pequeñas (0-7), el tamaño es aproximadamente 6\*logA*n* bits, donde A es el promedio de distribución ramificada.</span><span class="sxs-lookup"><span data-stu-id="fd383-120">For small fanouts, (0-7) the size is about 6\*logA*n* bits, where A is the average fanout.</span></span> <span data-ttu-id="fd383-121">Un nodo en una jerarquía organizativa de 100.000 personas con un promedio de nodos secundarios de 6 niveles supone aproximadamente 38 bits.</span><span class="sxs-lookup"><span data-stu-id="fd383-121">A node in an organizational hierarchy of 100,000 people with an average fanout of 6 levels takes about 38 bits.</span></span> <span data-ttu-id="fd383-122">Esto se redondea a 40 bits (o 5 bytes) para el almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="fd383-122">This is rounded up to 40 bits, or 5 bytes, for storage.</span></span>  
  
-   <span data-ttu-id="fd383-123">La comparación se realiza con prioridad a la profundidad</span><span class="sxs-lookup"><span data-stu-id="fd383-123">Comparison is in depth-first order</span></span>  
  
     <span data-ttu-id="fd383-124">Dados dos `hierarchyid` valores **a** y **b**, **una<b** significa que un viene antes de b en un recorrido transversal con prioridad a la profundidad del árbol.</span><span class="sxs-lookup"><span data-stu-id="fd383-124">Given two `hierarchyid` values **a** and **b**, **a<b** means a comes before b in a depth-first traversal of the tree.</span></span> <span data-ttu-id="fd383-125">Los índices de los tipos de datos `hierarchyid` están en orden con prioridad a la profundidad y los nodos cercanos entre sí en un corte transversal de prioridad a la profundidad se almacenan casi uno junto a otro.</span><span class="sxs-lookup"><span data-stu-id="fd383-125">Indexes on `hierarchyid` data types are in depth-first order, and nodes close to each other in a depth-first traversal are stored near each other.</span></span> <span data-ttu-id="fd383-126">Por ejemplo, los elementos secundarios de un registro se almacenan adyacentes a ese registro.</span><span class="sxs-lookup"><span data-stu-id="fd383-126">For example, the children of a record are stored adjacent to that record.</span></span>  
  
-   <span data-ttu-id="fd383-127">Compatibilidad con inserciones y eliminaciones arbitrarias</span><span class="sxs-lookup"><span data-stu-id="fd383-127">Support for arbitrary insertions and deletions</span></span>  
  
     <span data-ttu-id="fd383-128">Con el método [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) siempre es posible generar un miembro del mismo nivel a la derecha de cualquier nodo determinado, a la izquierda de cualquier nodo determinado, o entre dos miembros cualesquiera del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="fd383-128">By using the [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) method, it is always possible to generate a sibling to the right of any given node, to the left of any given node, or between any two siblings.</span></span> <span data-ttu-id="fd383-129">Se mantiene la propiedad comparison cuando se inserta o elimina un número arbitrario de nodos de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="fd383-129">The comparison property is maintained when an arbitrary number of nodes is inserted or deleted from the hierarchy.</span></span> <span data-ttu-id="fd383-130">La mayoría de las inserciones y eliminaciones conservan la propiedad compactness.</span><span class="sxs-lookup"><span data-stu-id="fd383-130">Most insertions and deletions preserve the compactness property.</span></span> <span data-ttu-id="fd383-131">Sin embargo, las inserciones entre dos nodos generarán valores hierarchyid con una representación ligeramente menos compacta.</span><span class="sxs-lookup"><span data-stu-id="fd383-131">However, insertions between two nodes will produce hierarchyid values with a slightly less compact representation.</span></span>  
  
  
##  <a name="limitations-of-hierarchyid"></a><a name="limits"></a> <span data-ttu-id="fd383-132">Limitaciones de hierarchyid</span><span class="sxs-lookup"><span data-stu-id="fd383-132">Limitations of hierarchyid</span></span>  
 <span data-ttu-id="fd383-133">El `hierarchyid` tipo de datos tiene las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="fd383-133">The `hierarchyid` data type has the following limitations:</span></span>  
  
-   <span data-ttu-id="fd383-134">Una columna de tipo `hierarchyid` no representa automáticamente un árbol.</span><span class="sxs-lookup"><span data-stu-id="fd383-134">A column of type `hierarchyid` does not automatically represent a tree.</span></span> <span data-ttu-id="fd383-135">Dependerá de la aplicación generar y asignar los valores `hierarchyid` de tal forma que la relación deseada entre las filas se refleje en los valores.</span><span class="sxs-lookup"><span data-stu-id="fd383-135">It is up to the application to generate and assign `hierarchyid` values in such a way that the desired relationship between rows is reflected in the values.</span></span> <span data-ttu-id="fd383-136">Algunas aplicaciones pueden tener una columna de tipo `hierarchyid` que indica la ubicación en una jerarquía definida en otra tabla.</span><span class="sxs-lookup"><span data-stu-id="fd383-136">Some applications might have a column of type `hierarchyid` that indicates the location in a hierarchy defined in another table.</span></span>  
  
-   <span data-ttu-id="fd383-137">Depende de la aplicación el administrar la simultaneidad en la generación y asignación de valores `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="fd383-137">It is up to the application to manage concurrency in generating and assigning `hierarchyid` values.</span></span> <span data-ttu-id="fd383-138">No hay ninguna garantía de que los valores `hierarchyid` de una columna sean únicos, a menos que la aplicación use una restricción de clave única o se aplique singularidad a través de su lógica.</span><span class="sxs-lookup"><span data-stu-id="fd383-138">There is no guarantee that `hierarchyid` values in a column are unique unless the application uses a unique key constraint or enforces uniqueness itself through its own logic.</span></span>  
  
-   <span data-ttu-id="fd383-139">Las relaciones jerárquicas representadas por valores `hierarchyid` no se aplican como una relación de clave externa.</span><span class="sxs-lookup"><span data-stu-id="fd383-139">Hierarchical relationships represented by `hierarchyid` values are not enforced like a foreign key relationship.</span></span> <span data-ttu-id="fd383-140">Es posible, y a veces adecuado, establecer una relación jerárquica donde A tiene un elemento secundario B, de forma que A se elimina dejando a B con una relación con un registro no existente.</span><span class="sxs-lookup"><span data-stu-id="fd383-140">It is possible and sometimes appropriate to have a hierarchical relationship where A has a child B, and then A is deleted leaving B with a relationship to a nonexistent record.</span></span> <span data-ttu-id="fd383-141">Si este comportamiento no es aceptable, la aplicación debe consultar a los descendientes antes de eliminar los miembros primarios.</span><span class="sxs-lookup"><span data-stu-id="fd383-141">If this behavior is unacceptable, the application must query for descendants before deleting parents.</span></span>  
  
  
##  <a name="when-to-use-alternatives-to-hierarchyid"></a><a name="alternatives"></a> <span data-ttu-id="fd383-142">Cuándo utilizar alternativas a hierarchyid</span><span class="sxs-lookup"><span data-stu-id="fd383-142">When to Use Alternatives to hierarchyid</span></span>  
 <span data-ttu-id="fd383-143">Dos alternativas a `hierarchyid` para representar los datos jerárquicos son:</span><span class="sxs-lookup"><span data-stu-id="fd383-143">Two alternatives to `hierarchyid` for representing hierarchical data are:</span></span>  
  
-   <span data-ttu-id="fd383-144">Elemento primario/secundario</span><span class="sxs-lookup"><span data-stu-id="fd383-144">Parent/Child</span></span>  
  
-   <span data-ttu-id="fd383-145">XML</span><span class="sxs-lookup"><span data-stu-id="fd383-145">XML</span></span>  
  
 <span data-ttu-id="fd383-146">Normalmente, `hierarchyid` es mejor opción en comparación con estas alternativas.</span><span class="sxs-lookup"><span data-stu-id="fd383-146">`hierarchyid` is generally superior to these alternatives.</span></span> <span data-ttu-id="fd383-147">Sin embargo, hay situaciones concretas, que se detallan a continuación, donde es probable que las alternativas sean una mejor opción.</span><span class="sxs-lookup"><span data-stu-id="fd383-147">However, there are specific situations detailed below where the alternatives are likely superior.</span></span>  
  
### <a name="parentchild"></a><span data-ttu-id="fd383-148">Elemento primario/secundario</span><span class="sxs-lookup"><span data-stu-id="fd383-148">Parent/Child</span></span>  
 <span data-ttu-id="fd383-149">Cuando se usa el planteamiento de elemento primario/secundario, cada fila contiene una referencia al elemento primario.</span><span class="sxs-lookup"><span data-stu-id="fd383-149">When using the Parent/Child approach, each row contains a reference to the parent.</span></span> <span data-ttu-id="fd383-150">La tabla siguiente define una tabla típica que se usa para contener las filas del elemento primario y el secundario en una relación entre elemento primario y secundario:</span><span class="sxs-lookup"><span data-stu-id="fd383-150">The following table defines a typical table used to contain the parent and the child rows in a Parent/Child relationship:</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE TABLE ParentChildOrg  
   (  
    BusinessEntityID int PRIMARY KEY,  
    ManagerId int REFERENCES ParentChildOrg(BusinessEntityID),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
```  
  
 <span data-ttu-id="fd383-151">Comparar el planteamiento de elemento primario/secundario y `hierarchyid` en operaciones comunes</span><span class="sxs-lookup"><span data-stu-id="fd383-151">Comparing Parent/Child and `hierarchyid` for Common Operations</span></span>  
  
-   <span data-ttu-id="fd383-152">Las consultas de subárboles son significativamente más rápidas con `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="fd383-152">Subtree queries are significantly faster with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="fd383-153">Las consultas directas de descendientes son ligeramente más lentas con `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="fd383-153">Direct descendant queries are slightly slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="fd383-154">Mover los nodos no hoja es más lento con `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="fd383-154">Moving non-leaf nodes is slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="fd383-155">Insertar nodos no hoja e insertar o mover nodos hoja es igual de complejo con `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="fd383-155">Inserting non-leaf nodes and inserting or moving leaf nodes has the same complexity with `hierarchyid`.</span></span>  
  
 <span data-ttu-id="fd383-156">La estructura de elemento primario/secundario puede ser mejor opción cuando se dan las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd383-156">Parent/Child might be superior when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="fd383-157">El tamaño de la clave es crítico.</span><span class="sxs-lookup"><span data-stu-id="fd383-157">The size of the key is critical.</span></span> <span data-ttu-id="fd383-158">Para el mismo número de nodos, un valor `hierarchyid` es igual o mayor que un valor de la familia de enteros (`smallint`, `int`, `bigint`).</span><span class="sxs-lookup"><span data-stu-id="fd383-158">For the same number of nodes, a `hierarchyid` value is equal to or larger than an integer-family (`smallint`, `int`, `bigint`) value.</span></span> <span data-ttu-id="fd383-159">Ésta es solo una de las razones para utilizar la estructura de elemento primario/secundario en casos poco comunes porque `hierarchyid` tiene una proximidad significativamente mejor de E/S y de complejidad de la CPU que las expresiones de tabla comunes necesarias cuando se utiliza una estructura de elemento primario/secundario.</span><span class="sxs-lookup"><span data-stu-id="fd383-159">This is only a reason to use Parent/Child in rare cases, because `hierarchyid` has significantly better locality of I/O and CPU complexity than the common table expressions required when you are using a Parent/Child structure.</span></span>  
  
-   <span data-ttu-id="fd383-160">Las consultas raramente recorren todas las secciones de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="fd383-160">Queries rarely query across sections of the hierarchy.</span></span> <span data-ttu-id="fd383-161">Dicho de otro modo, las consultas normalmente se dirigen a un solo punto de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="fd383-161">In other words, queries usually address only a single point in the hierarchy.</span></span> <span data-ttu-id="fd383-162">En estos casos la ubicación conjunta no es importante.</span><span class="sxs-lookup"><span data-stu-id="fd383-162">In these cases co-location is not important.</span></span> <span data-ttu-id="fd383-163">Por ejemplo, la estructura de elemento primario y secundario es la mejor opción cuando la tabla de organización solo se usa para procesar la nómina de empleados individuales.</span><span class="sxs-lookup"><span data-stu-id="fd383-163">For example, Parent/Child is superior when the organization table is only used to process payroll for individual employees.</span></span>  
  
-   <span data-ttu-id="fd383-164">Los subárboles no hoja se mueven con frecuencia y el rendimiento es muy importante.</span><span class="sxs-lookup"><span data-stu-id="fd383-164">Non-leaf subtrees move frequently and performance is very important.</span></span> <span data-ttu-id="fd383-165">En una representación de elemento primario/secundario, el cambio de ubicación de una fila en una jerarquía afecta a una única fila.</span><span class="sxs-lookup"><span data-stu-id="fd383-165">In a parent/child representation changing the location of a row in a hierarchy affects a single row.</span></span> <span data-ttu-id="fd383-166">Cambiar la ubicación de una fila en un `hierarchyid` uso afecta a *n* filas, donde *n* es el número de nodos del subárbol que se están moviendo.</span><span class="sxs-lookup"><span data-stu-id="fd383-166">Changing the location of a row in a `hierarchyid` usage affects *n* rows, where *n* is number of nodes in the sub-tree being moved.</span></span>  
  
     <span data-ttu-id="fd383-167">Si los subárboles no hoja se mueven con frecuencia y el rendimiento es importante, pero la mayoría de los movimientos se encuentran en un nivel bien definido de la jerarquía, tenga en cuenta la posibilidad de dividir los niveles más altos y más bajos en dos jerarquías.</span><span class="sxs-lookup"><span data-stu-id="fd383-167">If the non-leaf subtrees move frequently and performance is important, but most of the moves are at a well-defined level of the hierarchy, consider splitting the higher and lower levels into two hierarchies.</span></span> <span data-ttu-id="fd383-168">Esto convierte todos los movimientos en niveles de hoja de la jerarquía más alta.</span><span class="sxs-lookup"><span data-stu-id="fd383-168">This makes all moves into leaf-levels of the higher hierarchy.</span></span> <span data-ttu-id="fd383-169">Por ejemplo, considere la posibilidad de tener una jerarquía de sitios web hospedada por un servicio.</span><span class="sxs-lookup"><span data-stu-id="fd383-169">For instance, consider a hierarchy of Web sites hosted by a service.</span></span> <span data-ttu-id="fd383-170">Los sitios contienen muchas páginas organizadas de forma jerárquica.</span><span class="sxs-lookup"><span data-stu-id="fd383-170">Sites contain many pages arranged in a hierarchical manner.</span></span> <span data-ttu-id="fd383-171">Los sitios hospedados se pueden mover a otras ubicaciones en la jerarquía del sitio, pero las páginas subordinadas rara vez se reorganizan.</span><span class="sxs-lookup"><span data-stu-id="fd383-171">Hosted sites might be moved to other locations in the site hierarchy, but the subordinate pages are rarely re-arranged.</span></span> <span data-ttu-id="fd383-172">Esto se podría representar mediante:</span><span class="sxs-lookup"><span data-stu-id="fd383-172">This could be represented via:</span></span>  
  
    ```  
    CREATE TABLE HostedSites   
       (  
        SiteId hierarchyid, PageId hierarchyid  
       ) ;  
    GO  
    ```  
  
  
### <a name="xml"></a><span data-ttu-id="fd383-173">XML</span><span class="sxs-lookup"><span data-stu-id="fd383-173">XML</span></span>  
 <span data-ttu-id="fd383-174">Un documento XML es un árbol y, por lo tanto, una única instancia de tipo de datos XML puede representar una jerarquía completa.</span><span class="sxs-lookup"><span data-stu-id="fd383-174">An XML document is a tree, and therefore a single XML data type instance can represent a complete hierarchy.</span></span> <span data-ttu-id="fd383-175">En [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , cuando se crea un índice XML, `hierarchyid` los valores se usan internamente para representar la posición en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="fd383-175">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when an XML index is created, `hierarchyid` values are used internally to represent the position in the hierarchy.</span></span>  
  
 <span data-ttu-id="fd383-176">Utilizar el tipo de datos XML puede ser mejor opción cuando se cumplen todas las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd383-176">Using XML data type can be superior when all the following are true:</span></span>  
  
-   <span data-ttu-id="fd383-177">Siempre se almacena y se recupera la jerarquía completa.</span><span class="sxs-lookup"><span data-stu-id="fd383-177">The complete hierarchy is always stored and retrieved.</span></span>  
  
-   <span data-ttu-id="fd383-178">La aplicación consume los datos en formato XML.</span><span class="sxs-lookup"><span data-stu-id="fd383-178">The data is consumed in XML format by the application.</span></span>  
  
-   <span data-ttu-id="fd383-179">Las búsquedas del predicado están muy limitadas y no son vitales para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fd383-179">Predicate searches are extremely limited and not performance critical.</span></span>  
  
 <span data-ttu-id="fd383-180">Por ejemplo, cuando una aplicación realiza el seguimiento de varias organizaciones, siempre almacena y recupera la jerarquía de la organización completa y no consulta en una sola organización, entonces podría tener sentido utilizar una tabla con la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd383-180">For example, if an application tracks multiple organizations, always stores and retrieves the complete organizational hierarchy, and does not query into a single organization, a table of the following form might make sense:</span></span>  
  
```  
CREATE TABLE XMLOrg   
    (  
    Orgid int,  
    Orgdata xml  
    ) ;  
GO  
```  
  
  
##  <a name="indexing-strategies-for-hierarchical-data"></a><a name="indexing"></a> <span data-ttu-id="fd383-181">Estrategias de indización para los datos jerárquicos</span><span class="sxs-lookup"><span data-stu-id="fd383-181">Indexing Strategies for Hierarchical Data</span></span>  
 <span data-ttu-id="fd383-182">Hay dos estrategias para indizar datos jerárquicos:</span><span class="sxs-lookup"><span data-stu-id="fd383-182">There are two strategies for indexing hierarchical data:</span></span>  
  
-   <span data-ttu-id="fd383-183">**Con prioridad a la profundidad**</span><span class="sxs-lookup"><span data-stu-id="fd383-183">**Depth-first**</span></span>  
  
     <span data-ttu-id="fd383-184">En un índice con prioridad de profundidad, las filas de un subárbol se almacenan unas junto a otras.</span><span class="sxs-lookup"><span data-stu-id="fd383-184">A depth-first index stores the rows in a subtree near each other.</span></span> <span data-ttu-id="fd383-185">Por ejemplo, todos los empleados al mando de un gerente se almacenan junto al registro de este último.</span><span class="sxs-lookup"><span data-stu-id="fd383-185">For example, all employees that report through a manager are stored near their managers' record.</span></span>  
  
     <span data-ttu-id="fd383-186">En un índice con prioridad de profundidad, todos los nodos del subárbol de un nodo se ubican conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="fd383-186">In a depth-first index, all nodes in the subtree of a node are co-located.</span></span> <span data-ttu-id="fd383-187">Por lo tanto, los índices con prioridad a la profundidad son eficaces para responder a las consultas sobre subárboles, como "Buscar todos los archivos en esta carpeta y en sus subcarpetas".</span><span class="sxs-lookup"><span data-stu-id="fd383-187">Depth-first indexes are therefore efficient for answering queries about subtrees, such as "Find all files in this folder and its subfolders".</span></span>  
  
-   <span data-ttu-id="fd383-188">**Con prioridad a la amplitud**</span><span class="sxs-lookup"><span data-stu-id="fd383-188">**Breadth-first**</span></span>  
  
     <span data-ttu-id="fd383-189">Un índice con prioridad a la amplitud almacena juntas las filas de cada nivel de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="fd383-189">A breadth-first stores the rows each level of the hierarchy together.</span></span> <span data-ttu-id="fd383-190">Por ejemplo, se almacenan unos junto a otros los registros de empleados que notifican directamente al mismo gerente.</span><span class="sxs-lookup"><span data-stu-id="fd383-190">For example, the records of employees who directly report to the same manager are stored near each other.</span></span>  
  
     <span data-ttu-id="fd383-191">En un índice con prioridad a la amplitud, todos los elementos secundarios directos de un nodo se ubican conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="fd383-191">In a breadth-first index all direct children of a node are co-located.</span></span> <span data-ttu-id="fd383-192">Por lo tanto, los índices con prioridad a la amplitud son eficaces para responder a las consultas sobre elementos secundarios inmediatos, como "Buscar todos los empleados que informan directamente a este gerente".</span><span class="sxs-lookup"><span data-stu-id="fd383-192">Breadth-first indexes are therefore efficient for answering queries about immediate children, such as "Find all employees who report directly to this manager".</span></span>  
  
 <span data-ttu-id="fd383-193">Saber si es mejor tener un índice con prioridad de profundidad, con prioridad de amplitud, o ambos, y cuál de estos se debe establecer como clave de agrupación en clústeres (cuando proceda), depende de la importancia relativa de los tipos de consultas anteriores y de la importancia relativa de las operaciones SELECT frente a las de DML.</span><span class="sxs-lookup"><span data-stu-id="fd383-193">Whether to have depth-first, breadth-first, or both, and which to make the clustering key (if any), depends on the relative importance of the above types of queries, and the relative importance of SELECT vs. DML operations.</span></span> <span data-ttu-id="fd383-194">Para obtener un ejemplo detallado de las estrategias de indización, consulte [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="fd383-194">For a detailed example of indexing strategies, see [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
### <a name="creating-indexes"></a><span data-ttu-id="fd383-195">Crear índices</span><span class="sxs-lookup"><span data-stu-id="fd383-195">Creating Indexes</span></span>  
 <span data-ttu-id="fd383-196">El método GetLevel() se puede usar para crear una ordenación con prioridad a la amplitud.</span><span class="sxs-lookup"><span data-stu-id="fd383-196">The GetLevel() method can be used to create a breadth first ordering.</span></span> <span data-ttu-id="fd383-197">En el ejemplo siguiente se han creado los índices con prioridad a la amplitud y con prioridad a la profundidad:</span><span class="sxs-lookup"><span data-stu-id="fd383-197">In the following example, both breadth-first and depth-first indexes are created:</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;   
GO  
  
CREATE TABLE Organization  
   (  
    BusinessEntityID hierarchyid,  
    OrgLevel as BusinessEntityID.GetLevel(),   
    EmployeeName nvarchar(50) NOT NULL  
   ) ;  
GO  
  
CREATE CLUSTERED INDEX Org_Breadth_First   
ON Organization(OrgLevel,BusinessEntityID) ;  
GO  
  
CREATE UNIQUE INDEX Org_Depth_First   
ON Organization(BusinessEntityID) ;  
GO  
```  
  
  
## <a name="examples"></a><span data-ttu-id="fd383-198">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fd383-198">Examples</span></span>  
  
### <a name="simple-example"></a><span data-ttu-id="fd383-199">Ejemplo sencillo</span><span class="sxs-lookup"><span data-stu-id="fd383-199">Simple Example</span></span>  
 <span data-ttu-id="fd383-200">El ejemplo siguiente es deliberadamente simplista para ayudarle a empezar.</span><span class="sxs-lookup"><span data-stu-id="fd383-200">The following example is intentionally simplistic to help you get started.</span></span> <span data-ttu-id="fd383-201">Cree primero una tabla que contenga algunos datos de geografía.</span><span class="sxs-lookup"><span data-stu-id="fd383-201">First create a table to hold some geography data.</span></span>  
  
```  
CREATE TABLE SimpleDemo  
(Level hierarchyid NOT NULL,  
Location nvarchar(30) NOT NULL,  
LocationType nvarchar(9) NULL);  
```  
  
 <span data-ttu-id="fd383-202">Ahora inserte datos para algunos continentes, países, estados y ciudades.</span><span class="sxs-lookup"><span data-stu-id="fd383-202">Now insert data for some continents, countries, states, and cities.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES   
('/1/', 'Europe', 'Continent'),  
('/2/', 'South America', 'Continent'),  
('/1/1/', 'France', 'Country'),  
('/1/1/1/', 'Paris', 'City'),  
('/1/2/1/', 'Madrid', 'City'),  
('/1/2/', 'Spain', 'Country'),  
('/3/', 'Antarctica', 'Continent'),  
('/2/1/', 'Brazil', 'Country'),  
('/2/1/1/', 'Brasilia', 'City'),  
('/2/1/2/', 'Bahia', 'State'),  
('/2/1/2/1/', 'Salvador', 'City'),  
('/3/1/', 'McMurdo Station', 'City');  
```  
  
 <span data-ttu-id="fd383-203">Seleccione los datos, agregando una columna que convierta los datos de nivel a un valor de texto que sea fácil de entender.</span><span class="sxs-lookup"><span data-stu-id="fd383-203">Select the data, adding a column that converts the Level data into a text value that is easy to understand.</span></span> <span data-ttu-id="fd383-204">Esta consulta también ordena el resultado por el tipo de datos `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="fd383-204">This query also orders the result by the `hierarchyid` data type.</span></span>  
  
```  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], *   
FROM SimpleDemo ORDER BY Level;  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
Converted Level  Level     Location         LocationType  
/1/              0x58      Europe           Continent  
/1/1/            0x5AC0    France           Country  
/1/1/1/          0x5AD6    Paris            City  
/1/2/            0x5B40    Spain            Country  
/1/2/1/          0x5B56    Madrid           City  
/2/              0x68      South America    Continent  
/2/1/            0x6AC0    Brazil           Country  
/2/1/1/          0x6AD6    Brasilia         City  
/2/1/2/          0x6ADA    Bahia            State  
/2/1/2/1/        0x6ADAB0  Salvador         City  
/3/              0x78      Antarctica       Continent  
/3/1/            0x7AC0    McMurdo Station  City  
```  
  
 <span data-ttu-id="fd383-205">Observe que la jerarquía is tiene una estructura válida, aunque no sea coherente internamente.</span><span class="sxs-lookup"><span data-stu-id="fd383-205">Notice that the hierarchy is has a valid structure, even though it is not internally consistent.</span></span> <span data-ttu-id="fd383-206">Bahia es el único estado.</span><span class="sxs-lookup"><span data-stu-id="fd383-206">Bahia is the only state.</span></span> <span data-ttu-id="fd383-207">Aparece en la jerarquía como un homólogo de la ciudad Brasilia.</span><span class="sxs-lookup"><span data-stu-id="fd383-207">It appears in the hierarchy as a peer of the city Brasilia.</span></span> <span data-ttu-id="fd383-208">Del mismo modo, McMurdo Station no tiene un país primario.</span><span class="sxs-lookup"><span data-stu-id="fd383-208">Similarly, McMurdo Station does not have a parent country.</span></span> <span data-ttu-id="fd383-209">Los usuarios deben decidir si este tipo de jerarquía es adecuado para su uso.</span><span class="sxs-lookup"><span data-stu-id="fd383-209">Users must decide if this type of hierarchy is appropriate for their use.</span></span>  
  
 <span data-ttu-id="fd383-210">Agregue otra fila y seleccione los resultados.</span><span class="sxs-lookup"><span data-stu-id="fd383-210">Add another row and select the results.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/1/3/1/', 'Kyoto', 'City'), ('/1/3/1/', 'London', 'City');  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], * FROM SimpleDemo ORDER BY Level;  
```  
  
 <span data-ttu-id="fd383-211">Esto muestra más problemas posibles.</span><span class="sxs-lookup"><span data-stu-id="fd383-211">This demonstrates more possible problems.</span></span> <span data-ttu-id="fd383-212">Kyoto se puede insertar como el nivel `/1/3/1/` aunque no hay ningún nivel primario `/1/3/`.</span><span class="sxs-lookup"><span data-stu-id="fd383-212">Kyoto can be inserted as level `/1/3/1/` even though there is no parent level `/1/3/`.</span></span> <span data-ttu-id="fd383-213">Y tanto London como Kyoto tienen el mismo valor de `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="fd383-213">And both London and Kyoto have the same value for the `hierarchyid`.</span></span> <span data-ttu-id="fd383-214">Una vez más, los usuarios deben decidir si este tipo de jerarquía es adecuado para su uso y bloquear los valores que no se puedan usar.</span><span class="sxs-lookup"><span data-stu-id="fd383-214">Again, users must decide if this type of hierarchy is appropriate for their use, and block values that are invalid for their usage.</span></span>  
  
 <span data-ttu-id="fd383-215">Además, en esta tabla no se usó la parte superior de la jerarquía `'/'`.</span><span class="sxs-lookup"><span data-stu-id="fd383-215">Also, this table did not use the top of the hierarchy `'/'`.</span></span> <span data-ttu-id="fd383-216">Se omitió porque no hay ningún elemento primario común de todos los continentes.</span><span class="sxs-lookup"><span data-stu-id="fd383-216">It was omitted because there is no common parent of all the continents.</span></span> <span data-ttu-id="fd383-217">Puede agregar uno si agrega todo el planeta.</span><span class="sxs-lookup"><span data-stu-id="fd383-217">You can add one by adding the whole planet.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/', 'Earth', 'Planet');  
```  
  
##  <a name="related-tasks"></a><a name="tasks"></a> <span data-ttu-id="fd383-218">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="fd383-218">Related Tasks</span></span>  
  
###  <a name="migrating-from-parentchild-to-hierarchyid"></a><a name="migrating"></a> <span data-ttu-id="fd383-219">Migrar de elemento primario/secundario a hierarchyid</span><span class="sxs-lookup"><span data-stu-id="fd383-219">Migrating from Parent/Child to hierarchyid</span></span>  
 <span data-ttu-id="fd383-220">La mayoría de los árboles se representan mediante elementos primario y secundario.</span><span class="sxs-lookup"><span data-stu-id="fd383-220">Most trees are represented using Parent/Child.</span></span> <span data-ttu-id="fd383-221">La manera más fácil de migrar de una estructura de elemento primario y secundario a una tabla que use `hierarchyid` consiste en utilizar una columna temporal o una tabla temporal para realizar el seguimiento del número de nodos en cada nivel de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="fd383-221">The easiest way to migrate from a Parent/Child structure to a table using `hierarchyid` is to use a temporary column or a temporary table to keep track of the number of nodes at each level of the hierarchy.</span></span> <span data-ttu-id="fd383-222">Para ver un ejemplo sobre la migración de una tabla de elemento primario/secundario, consulte la lección 1 de [Tutorial: Usar el tipo de datos hierarchyid](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="fd383-222">For an example of migrating a Parent/Child table, see lesson 1 of [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
###  <a name="managing-a-tree-using-hierarchyid"></a><a name="BKMK_ManagingTrees"></a> <span data-ttu-id="fd383-223">Administrar un árbol mediante hierarchyid</span><span class="sxs-lookup"><span data-stu-id="fd383-223">Managing a Tree Using hierarchyid</span></span>  
 <span data-ttu-id="fd383-224">Aunque una columna de `hierarchyid` no representa necesariamente un árbol, una aplicación puede exigir fácilmente que sí lo haga.</span><span class="sxs-lookup"><span data-stu-id="fd383-224">Although a `hierarchyid` column does not necessarily represent a tree, an application can easily ensure that it does.</span></span>  
  
-   <span data-ttu-id="fd383-225">Cuando genere nuevos valores, realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="fd383-225">When generating new values, do one of the following:</span></span>  
  
    -   <span data-ttu-id="fd383-226">Realice el seguimiento del último número secundario en la fila primaria.</span><span class="sxs-lookup"><span data-stu-id="fd383-226">Keep track of the last child number in the parent row.</span></span>  
  
    -   <span data-ttu-id="fd383-227">Calcule el último elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="fd383-227">Compute the last child.</span></span> <span data-ttu-id="fd383-228">Si desea realizar eficazmente este proceso, deberá ejecutar un índice con prioridad a la amplitud.</span><span class="sxs-lookup"><span data-stu-id="fd383-228">Doing this efficiently requires a breadth-first index.</span></span>  
  
-   <span data-ttu-id="fd383-229">Exija la singularidad creando un índice único en la columna, tal vez como parte de una clave de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="fd383-229">Enforce uniqueness by creating a unique index on the column, perhaps as part of a clustering key.</span></span> <span data-ttu-id="fd383-230">Para asegurarse de que se insertan valores únicos, realice una de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="fd383-230">To ensure that unique values are inserted, do one of the following:</span></span>  
  
    -   <span data-ttu-id="fd383-231">Detecte errores y reintentos de infracción de clave única.</span><span class="sxs-lookup"><span data-stu-id="fd383-231">Detect unique key violation failures and retry.</span></span>  
  
    -   <span data-ttu-id="fd383-232">Determine la singularidad de cada nuevo nodo secundario e insértelo como parte de una transacción serializable.</span><span class="sxs-lookup"><span data-stu-id="fd383-232">Determine the uniqueness of each new child node, and insert it as part of a serializable transaction.</span></span>  
  
  
#### <a name="example-using-error-detection"></a><span data-ttu-id="fd383-233">Ejemplo usando la detección de errores</span><span class="sxs-lookup"><span data-stu-id="fd383-233">Example Using Error Detection</span></span>  
 <span data-ttu-id="fd383-234">En el ejemplo siguiente, el código de ejemplo calcula el nuevo valor secundario de **EmployeeId** y, después, detecta cualquier infracción de clave y la devuelve al marcador **INS_EMP** para volver a calcular el valor de **EmployeeId** para la nueva fila:</span><span class="sxs-lookup"><span data-stu-id="fd383-234">In the following example, the sample code computes the new child **EmployeeId** value, and then detects any key violation and returns to **INS_EMP** marker to recompute the **EmployeeId** value for the new row:</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
CREATE TABLE Org_T1  
   (  
    EmployeeId hierarchyid PRIMARY KEY,  
    OrgLevel AS EmployeeId.GetLevel(),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
  
CREATE INDEX Org_BreadthFirst ON Org_T1(OrgLevel, EmployeeId)  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50) )   
AS  
BEGIN  
    DECLARE @last_child hierarchyid  
INS_EMP:   
    SELECT @last_child = MAX(EmployeeId) FROM Org_T1   
    WHERE EmployeeId.GetAncestor(1) = @mgrid  
INSERT Org_T1 (EmployeeId, EmployeeName)  
SELECT @mgrid.GetDescendant(@last_child, NULL), @EmpName   
-- On error, return to INS_EMP to recompute @last_child  
IF @@error <> 0 GOTO INS_EMP   
END ;  
GO  
```  
  
  
#### <a name="example-using-a-serializable-transaction"></a><span data-ttu-id="fd383-235">Ejemplo usando una transacción serializable</span><span class="sxs-lookup"><span data-stu-id="fd383-235">Example Using a Serializable Transaction</span></span>  
 <span data-ttu-id="fd383-236">El tipo de datos **Org_BreadthFirst** garantiza que se use una búsqueda de rango al determinar **@last_child** .</span><span class="sxs-lookup"><span data-stu-id="fd383-236">The **Org_BreadthFirst** index ensures that determining **@last_child** uses a range seek.</span></span> <span data-ttu-id="fd383-237">Además de otros casos de error, es posible que una aplicación quiera comprobar una infracción de clave duplicada después de que la inserción indique un intento de agregar varios empleados con el mismo identificador y, por consiguiente, **@last_child** debe volver a calcularse.</span><span class="sxs-lookup"><span data-stu-id="fd383-237">In addition to other error cases an application might want to check, a duplicate key violation after the insert indicates an attempt to add multiple employees with the same id, and therefore **@last_child** must be recomputed.</span></span> <span data-ttu-id="fd383-238">El código siguiente usa una transacción serializable y un índice con prioridad a la amplitud para calcular el nuevo valor de nodo:</span><span class="sxs-lookup"><span data-stu-id="fd383-238">The following code uses a serializable transaction and a breadth-first index to compute the new node value:</span></span>  
  
```  
CREATE TABLE Org_T2  
    (  
    EmployeeId hierarchyid PRIMARY KEY,  
    LastChild hierarchyid,   
    EmployeeName nvarchar(50)   
    ) ;  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50))   
AS  
BEGIN  
DECLARE @last_child hierarchyid  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION   
  
UPDATE Org_T2   
SET @last_child = LastChild = EmployeeId.GetDescendant(LastChild,NULL)  
WHERE EmployeeId = @mgrid  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(@last_child, @EmpName)  
COMMIT  
END ;  
```  
  
 <span data-ttu-id="fd383-239">El código siguiente rellena la tabla con tres filas y devuelve los resultados:</span><span class="sxs-lookup"><span data-stu-id="fd383-239">The following code populates the table with three rows and returns the results:</span></span>  
  
```  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(hierarchyid::GetRoot(), 'David') ;  
GO  
AddEmp 0x , 'Sariya'  
GO  
AddEmp 0x58 , 'Mary'  
GO  
SELECT * FROM Org_T2  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
EmployeeId LastChild EmployeeName  
---------- --------- ------------  
0x        0x58       David  
0x58      0x5AC0     Sariya  
0x5AC0    NULL       Mary  
```  
  
  
###  <a name="enforcing-a-tree"></a><a name="BKMK_EnforcingTrees"></a> <span data-ttu-id="fd383-240">Exigir un árbol</span><span class="sxs-lookup"><span data-stu-id="fd383-240">Enforcing a tree</span></span>  
 <span data-ttu-id="fd383-241">Los ejemplos anteriores muestran cómo una aplicación puede asegurarse de que se mantenga un árbol.</span><span class="sxs-lookup"><span data-stu-id="fd383-241">The above examples illustrate how an application can ensure that a tree is maintained.</span></span> <span data-ttu-id="fd383-242">Para exigir un árbol mediante restricciones, se puede crear una columna calculada que defina el elemento primario de cada nodo con una restricción de clave externa respecto al identificador de clave principal.</span><span class="sxs-lookup"><span data-stu-id="fd383-242">To enforce a tree by using constraints, a computed column that defines the parent of each node can be created with a foreign key constraint back to the primary key id.</span></span>  
  
```  
CREATE TABLE Org_T3  
(  
   EmployeeId hierarchyid PRIMARY KEY,  
   ParentId AS EmployeeId.GetAncestor(1) PERSISTED    
      REFERENCES Org_T3(EmployeeId),  
   LastChild hierarchyid,   
   EmployeeName nvarchar(50)  
)  
GO  
```  
  
 <span data-ttu-id="fd383-243">Se prefiere este método que exige una relación cuando el código que no es de confianza para mantener el árbol jerárquico tiene acceso DML directo a la tabla.</span><span class="sxs-lookup"><span data-stu-id="fd383-243">This method of enforcing a relationship is preferred when code that is not trusted to maintain the hierarchical tree has direct DML access to the table.</span></span> <span data-ttu-id="fd383-244">No obstante, este método puede reducir el rendimiento porque es necesario comprobar la restricción para cada operación DML.</span><span class="sxs-lookup"><span data-stu-id="fd383-244">However this method might reduce performance because the constraint must be checked on every DML operation.</span></span>  
  
  
###  <a name="finding-ancestors-by-using-the-clr"></a><a name="findclr"></a> <span data-ttu-id="fd383-245">Buscar antecesores mediante CLR</span><span class="sxs-lookup"><span data-stu-id="fd383-245">Finding Ancestors by Using the CLR</span></span>  
 <span data-ttu-id="fd383-246">Una operación común, en la que se implican dos nodos en una jerarquía, es buscar el antecesor común más bajo.</span><span class="sxs-lookup"><span data-stu-id="fd383-246">A common operation involving two nodes in a hierarchy is to find the lowest common ancestor.</span></span> <span data-ttu-id="fd383-247">Esto puede escribirse en [!INCLUDE[tsql](../includes/tsql-md.md)] o en CLR, ya que el `hierarchyid` tipo está disponible en ambos.</span><span class="sxs-lookup"><span data-stu-id="fd383-247">This can be written in either [!INCLUDE[tsql](../includes/tsql-md.md)] or CLR, because the `hierarchyid` type is available in both.</span></span> <span data-ttu-id="fd383-248">Se recomienda CLR porque la ejecución es más rápida.</span><span class="sxs-lookup"><span data-stu-id="fd383-248">CLR is recommended because performance will be faster.</span></span>  
  
 <span data-ttu-id="fd383-249">Use el siguiente código de CLR para hacer una lista de los antecesores y buscar el antecesor común más bajo:</span><span class="sxs-lookup"><span data-stu-id="fd383-249">Use the following CLR code to list ancestors and to find the lowest common ancestor:</span></span>  
  
```  
using System;  
using System.Collections;  
using System.Text;  
using Microsoft.SqlServer.Server;  
using Microsoft.SqlServer.Types;  
  
public partial class HierarchyId_Operations  
{  
    [SqlFunction(FillRowMethodName = "FillRow_ListAncestors")]  
    public static IEnumerable ListAncestors(SqlHierarchyId h)  
    {  
        while (!h.IsNull)  
        {  
            yield return (h);  
            h = h.GetAncestor(1);  
        }  
    }  
    public static void FillRow_ListAncestors(Object obj, out SqlHierarchyId ancestor)  
    {  
        ancestor = (SqlHierarchyId)obj;  
    }  
  
    public static HierarchyId CommonAncestor(SqlHierarchyId h1, HierarchyId h2)  
    {  
        while (!h1.IsDescendant(h2))  
            h1 = h1.GetAncestor(1);  
  
        return h1;  
    }  
}  
```  
  
 <span data-ttu-id="fd383-250">Para usar los métodos **ListAncestor** y **CommonAncestor** en los siguientes ejemplos de [!INCLUDE[tsql](../includes/tsql-md.md)] , genere la DLL y cree el ensamblado de **HierarchyId_Operations** en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ejecutando un código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd383-250">To use the **ListAncestor** and **CommonAncestor** methods in the following [!INCLUDE[tsql](../includes/tsql-md.md)] examples, build the DLL and create the **HierarchyId_Operations** assembly in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by executing code similar to the following:</span></span>  
  
```  
CREATE ASSEMBLY HierarchyId_Operations   
FROM '<path to DLL>\ListAncestors.dll'  
GO  
```  
  
  
###  <a name="listing-ancestors"></a><a name="ancestors"></a> <span data-ttu-id="fd383-251">Enumerar antecesores</span><span class="sxs-lookup"><span data-stu-id="fd383-251">Listing Ancestors</span></span>  
 <span data-ttu-id="fd383-252">La creación de una lista de antecesores de un nodo es una operación común que sirve, por ejemplo, para mostrar la posición en una organización.</span><span class="sxs-lookup"><span data-stu-id="fd383-252">Creating a list of ancestors of a node is a common operation, for instance to show position in an organization.</span></span> <span data-ttu-id="fd383-253">Esto se puede realizar, por ejemplo, mediante una función con valores de tabla que use la clase **HierarchyId_Operations** definida anteriormente:</span><span class="sxs-lookup"><span data-stu-id="fd383-253">One way of doing this is by using a table-valued-function using the **HierarchyId_Operations** class defined above:</span></span>  
  
 <span data-ttu-id="fd383-254">Usar [!INCLUDE[tsql](../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fd383-254">Using [!INCLUDE[tsql](../includes/tsql-md.md)]:</span></span>  
  
```  
CREATE FUNCTION ListAncestors (@node hierarchyid)  
RETURNS TABLE (node hierarchyid)  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.ListAncestors  
GO  
```  
  
 <span data-ttu-id="fd383-255">Ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="fd383-255">Example of usage:</span></span>  
  
```  
DECLARE @h hierarchyid  
SELECT @h = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- /1/1/5/2/  
  
SELECT LoginID, OrgNode.ToString() AS LogicalNode  
FROM HumanResources.EmployeeDemo AS ED  
JOIN ListAncestors(@h) AS A   
   ON ED.OrgNode = A.Node  
GO  
```  
  
  
###  <a name="finding-the-lowest-common-ancestor"></a><a name="lowestcommon"></a> <span data-ttu-id="fd383-256">Buscar el antecesor común más bajo</span><span class="sxs-lookup"><span data-stu-id="fd383-256">Finding the Lowest Common Ancestor</span></span>  
 <span data-ttu-id="fd383-257">Use la clase **HierarchyId_Operations** definida anteriormente para crear la siguiente función de [!INCLUDE[tsql](../includes/tsql-md.md)] a fin de buscar el antecesor común más bajo que implica dos nodos en una jerarquía:</span><span class="sxs-lookup"><span data-stu-id="fd383-257">Using the **HierarchyId_Operations** class defined above, create the following [!INCLUDE[tsql](../includes/tsql-md.md)] function to find the lowest common ancestor involving two nodes in a hierarchy:</span></span>  
  
```  
CREATE FUNCTION CommonAncestor (@node1 hierarchyid, @node2 hierarchyid)  
RETURNS hierarchyid  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.CommonAncestor  
GO  
```  
  
 <span data-ttu-id="fd383-258">Ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="fd383-258">Example of usage:</span></span>  
  
```  
DECLARE @h1 hierarchyid, @h2 hierarchyid  
  
SELECT @h1 = OrgNode   
FROM  HumanResources.EmployeeDemo   
WHERE LoginID = 'adventure-works\jossef0' -- Node is /1/1/3/  
  
SELECT @h2 = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- Node is /1/1/5/2/  
  
SELECT OrgNode.ToString() AS LogicalNode, LoginID   
FROM HumanResources.EmployeeDemo    
WHERE OrgNode = dbo.CommonAncestor(@h1, @h2) ;  
```  
  
 <span data-ttu-id="fd383-259">El nodo resultante es /1/1/</span><span class="sxs-lookup"><span data-stu-id="fd383-259">The resultant node is /1/1/</span></span>  
  
  
###  <a name="moving-subtrees"></a><a name="BKMK_MovingSubtrees"></a> <span data-ttu-id="fd383-260">Mover los subárboles</span><span class="sxs-lookup"><span data-stu-id="fd383-260">Moving Subtrees</span></span>  
 <span data-ttu-id="fd383-261">Otra operación común es mover subárboles.</span><span class="sxs-lookup"><span data-stu-id="fd383-261">Another common operation is moving subtrees.</span></span> <span data-ttu-id="fd383-262">El procedimiento siguiente toma el subárbol de **@oldMgr** y lo convierte (incluido **@oldMgr** ) en un subárbol de **@newMgr** .</span><span class="sxs-lookup"><span data-stu-id="fd383-262">The procedure below takes the subtree of **@oldMgr** and makes it (including **@oldMgr**) a subtree of **@newMgr**.</span></span>  
  
```  
CREATE PROCEDURE MoveOrg(@oldMgr nvarchar(256), @newMgr nvarchar(256) )  
AS  
BEGIN  
DECLARE @nold hierarchyid, @nnew hierarchyid  
SELECT @nold = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @oldMgr ;  
  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION  
SELECT @nnew = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @newMgr ;  
  
SELECT @nnew = @nnew.GetDescendant(max(OrgNode), NULL)   
FROM HumanResources.EmployeeDemo WHERE OrgNode.GetAncestor(1)=@nnew ;  
  
UPDATE HumanResources.EmployeeDemo    
SET OrgNode = OrgNode.GetReparentedValue(@nold, @nnew)  
WHERE OrgNode.IsDescendantOf(@nold) = 1 ;  
  
COMMIT TRANSACTION  
END ;  
GO  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="fd383-263">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd383-263">See Also</span></span>  
 <span data-ttu-id="fd383-264">[Referencia de los métodos del tipo de datos hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="fd383-264">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="fd383-265">[Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="fd383-265">[Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span></span>  
 [<span data-ttu-id="fd383-266">hierarchyid &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd383-266">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
