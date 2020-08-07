---
title: Introducción a diagramas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- updategrams [SQLXML], mapping schema specifying
- namespaces [SQLXML]
- updategrams [SQLXML], about updategrams
- attribute-centric mapping
- invalid characters [SQLXML]
- element-centric mapping [SQLXML]
- mapping schema [SQLXML], updategrams
- namespaces [SQLXML], updategrams
- executing updategrams [SQLXML]
- implicit schema mapping
ms.assetid: cfe24e82-a645-4f93-ab16-39c21f90cce6
author: rothja
ms.author: jroth
ms.openlocfilehash: eb2f29d7f5d86d28254dacb9c55cceb9b4c72d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746181"
---
# <a name="introduction-to-updategrams-sqlxml-40"></a><span data-ttu-id="c618a-102">Introducción a los diagramas de actualización (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c618a-102">Introduction to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="c618a-103">Puede modificar (insertar, actualizar o eliminar) una base de datos de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] desde un documento XML existente mediante una diagrama o la función OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c618a-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="c618a-104">La función OPENXML modifica una base de datos dividiendo el documento XML existente y proporcionando un conjunto de filas que puede pasarse a una instrucción INSERT, UPDATE o DELETE.</span><span class="sxs-lookup"><span data-stu-id="c618a-104">The OPENXML function modifies a database by shredding the existing XML document and providing a rowset that can be passed to an INSERT, UPDATE, or DELETE statement.</span></span> <span data-ttu-id="c618a-105">Con OPENXML, las operaciones se realizan directamente en las tablas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c618a-105">With OPENXML, operations are performed directly against the database tables.</span></span> <span data-ttu-id="c618a-106">Por lo tanto, el uso de OPENXML resulta más adecuado siempre que los proveedores de conjuntos de filas, como una tabla, puedan aparecer como un origen.</span><span class="sxs-lookup"><span data-stu-id="c618a-106">Therefore, OPENXML is most appropriate wherever rowset providers, such as a table, can appear as a source.</span></span>  
  
 <span data-ttu-id="c618a-107">Al igual que OPENXML, un diagrama de actualización permite insertar, actualizar o eliminar datos en la base de datos; sin embargo, un diagrama de actualización funciona con las vistas XML proporcionadas por el esquema XSD (o XDR) anotado; por ejemplo, las actualizaciones se aplican a la vista XML proporcionada por el esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="c618a-107">Like OPENXML, an updategram allows you to insert, update, or delete data in the database; however, an updategram works against the XML views provided by the annotated XSD (or an XDR) schema; for example, the updates are applied to the XML view provided by the mapping schema.</span></span> <span data-ttu-id="c618a-108">El esquema de asignación, a su vez, incluye la información necesaria para asignar elementos y atributos XML a las columnas y tablas de base de datos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="c618a-108">The mapping schema, in turn, has the necessary information to map XML elements and attributes to the corresponding database tables and columns.</span></span> <span data-ttu-id="c618a-109">El diagrama de actualización usa esta información de asignación para actualizar las columnas y tablas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c618a-109">The updategram uses this mapping information to update the database tables and columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c618a-110">En esta documentación se asume que está familiarizado con la compatibilidad de las plantillas y el esquema de asignación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c618a-110">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c618a-111">Para obtener más información, vea [Introducción a los esquemas XSD anotados &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c618a-111">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="c618a-112">En el caso de las aplicaciones heredadas que usan XDR, consulte [esquemas XDR anotados &#40;en desuso en SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c618a-112">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="required-namespaces-in-the-updategram"></a><span data-ttu-id="c618a-113">Espacios de nombres necesarios en el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="c618a-113">Required Namespaces in the Updategram</span></span>  
 <span data-ttu-id="c618a-114">Las palabras clave de un diagrama, como **\<sync>** , **\<before>** y, **\<after>** existen en el `urn:schemas-microsoft-com:xml-updategram` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c618a-114">The keywords in an updategram, such as **\<sync>**, **\<before>**, and **\<after>**, exist in the `urn:schemas-microsoft-com:xml-updategram` namespace.</span></span> <span data-ttu-id="c618a-115">Se usa un prefijo de espacio de nombres arbitrario.</span><span class="sxs-lookup"><span data-stu-id="c618a-115">The namespace prefix that you use is arbitrary.</span></span> <span data-ttu-id="c618a-116">En esta documentación, el prefijo `updg` denota el espacio de nombres `updategram`.</span><span class="sxs-lookup"><span data-stu-id="c618a-116">In this documentation, the `updg` prefix denotes the `updategram` namespace.</span></span>  
  
## <a name="reviewing-syntax"></a><span data-ttu-id="c618a-117">Revisar la sintaxis</span><span class="sxs-lookup"><span data-stu-id="c618a-117">Reviewing Syntax</span></span>  
 <span data-ttu-id="c618a-118">Un diagrama es una plantilla con **\<sync>** **\<before>** bloques, y **\<after>** que forman la sintaxis de diagrama.</span><span class="sxs-lookup"><span data-stu-id="c618a-118">An updategram is a template with **\<sync>**, **\<before>**, and **\<after>** blocks that form the syntax of the updategram.</span></span> <span data-ttu-id="c618a-119">El código siguiente muestra esta sintaxis en su forma más simple:</span><span class="sxs-lookup"><span data-stu-id="c618a-119">The following code shows this syntax in its simplest form:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema= "AnnotatedSchemaFile.xml"] >  
    <updg:before>  
        ...  
    </updg:before>  
    <updg:after>  
        ...  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="c618a-120">Las definiciones siguientes describen el rol de cada uno de estos bloques:</span><span class="sxs-lookup"><span data-stu-id="c618a-120">The following definitions describe the role of each of these blocks:</span></span>  
  
 **\<before>**  
 <span data-ttu-id="c618a-121">Identifica el estado existente (que también recibe el nombre de "estado before") de la instancia de registro.</span><span class="sxs-lookup"><span data-stu-id="c618a-121">Identifies the existing state (also called "the before state") of the record instance.</span></span>  
  
 **\<after>**  
 <span data-ttu-id="c618a-122">Identifica el nuevo estado al que van a cambiarse los datos.</span><span class="sxs-lookup"><span data-stu-id="c618a-122">Identifies the new state to which data is to be changed.</span></span>  
  
 **\<sync>**  
 <span data-ttu-id="c618a-123">Contiene los **\<before>** **\<after>** bloques y.</span><span class="sxs-lookup"><span data-stu-id="c618a-123">Contains the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="c618a-124">Un **\<sync>** bloque puede contener más de un conjunto de **\<before>** **\<after>** bloques y.</span><span class="sxs-lookup"><span data-stu-id="c618a-124">A **\<sync>** block can contain more than one set of **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="c618a-125">Si hay más de un conjunto de **\<before>** bloques y **\<after>** , estos bloques (incluso si están vacíos) deben especificarse como pares.</span><span class="sxs-lookup"><span data-stu-id="c618a-125">If there is more than one set of **\<before>** and **\<after>** blocks, these blocks (even if they are empty) must be specified as pairs.</span></span> <span data-ttu-id="c618a-126">Además, un diagrama puede tener más de un **\<sync>** bloque.</span><span class="sxs-lookup"><span data-stu-id="c618a-126">Furthermore, an updategram can have more than one **\<sync>** block.</span></span> <span data-ttu-id="c618a-127">Cada **\<sync>** bloque es una unidad de transacción (lo que significa que se realiza todo el **\<sync>** bloque o no se hace nada).</span><span class="sxs-lookup"><span data-stu-id="c618a-127">Each **\<sync>** block is one unit of transaction (which means that either everything in the **\<sync>** block is done or nothing is done).</span></span> <span data-ttu-id="c618a-128">Si especifica varios **\<sync>** bloques en un diagrama, el error de un **\<sync>** bloque no afectará a los demás **\<sync>** bloques.</span><span class="sxs-lookup"><span data-stu-id="c618a-128">If you specify multiple **\<sync>** blocks in an updategram, the failure of one **\<sync>** block does not affect the other **\<sync>** blocks.</span></span>  
  
 <span data-ttu-id="c618a-129">El hecho de que un diagrama elimine, inserte o actualice una instancia de registro depende del contenido de **\<before>** los **\<after>** bloques y:</span><span class="sxs-lookup"><span data-stu-id="c618a-129">Whether an updategram deletes, inserts, or updates a record instance depends on the contents of the **\<before>** and **\<after>** blocks:</span></span>  
  
-   <span data-ttu-id="c618a-130">Si una instancia de registro aparece solo en el **\<before>** bloque sin ninguna instancia correspondiente en el **\<after>** bloque, el diagrama realiza una operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="c618a-130">If a record instance appears only in the **\<before>** block with no corresponding instance in the **\<after>** block, the updategram performs a delete operation.</span></span>  
  
-   <span data-ttu-id="c618a-131">Si una instancia de registro aparece solo en el **\<after>** bloque sin ninguna instancia correspondiente en el **\<before>** bloque, se trata de una operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="c618a-131">If a record instance appears only in the **\<after>** block with no corresponding instance in the **\<before>** block, it is an insert operation.</span></span>  
  
-   <span data-ttu-id="c618a-132">Si una instancia de registro aparece en el **\<before>** bloque y tiene una instancia correspondiente en el **\<after>** bloque, se trata de una operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="c618a-132">If a record instance appears in the **\<before>** block and has a corresponding instance in the **\<after>** block, it is an update operation.</span></span> <span data-ttu-id="c618a-133">En este caso, diagrama actualiza la instancia de registro a los valores que se especifican en el **\<after>** bloque.</span><span class="sxs-lookup"><span data-stu-id="c618a-133">In this case, the updategram updates the record instance to the values that are specified in the **\<after>** block.</span></span>  
  
## <a name="specifying-a-mapping-schema-in-the-updategram"></a><span data-ttu-id="c618a-134">Especificar un esquema de asignación en el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="c618a-134">Specifying a Mapping Schema in the Updategram</span></span>  
 <span data-ttu-id="c618a-135">En un diagrama de actualización, la abstracción XML que se proporciona con un esquema de asignación (se admiten tanto esquemas XSD como esquemas XDR) puede ser implícita o explícita (es decir, un diagrama de actualización puede funcionar con o sin un esquema de asignación especificado).</span><span class="sxs-lookup"><span data-stu-id="c618a-135">In an updategram, the XML abstraction that is provided by a mapping schema (both XSD and XDR schemas are supported) can be implicit or explicit (that is, an updategram can work with or without a specified mapping schema).</span></span> <span data-ttu-id="c618a-136">Si no se especifica un esquema de asignación, el diagrama asume una asignación implícita (la asignación predeterminada), donde cada elemento del **\<before>** bloque o **\<after>** bloque se asigna a una tabla y el atributo o elemento secundario de cada elemento se asigna a una columna de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c618a-136">If you do not specify a mapping schema, the updategram assumes an implicit mapping (the default mapping), where each element in the **\<before>** block or **\<after>** block maps to a table and each element's child element or attribute maps to a column in the database.</span></span> <span data-ttu-id="c618a-137">Si especifica explícitamente un esquema de asignación, los elementos y atributos del diagrama de actualización deben coincidir con los elementos y los atributos del esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="c618a-137">If you explicitly specify a mapping schema, the elements and attributes in the updategram must match the elements and attributes in the mapping schema.</span></span>  
  
### <a name="implicit-default-mapping"></a><span data-ttu-id="c618a-138">Asignación implícita (predeterminada)</span><span class="sxs-lookup"><span data-stu-id="c618a-138">Implicit (default) Mapping</span></span>  
 <span data-ttu-id="c618a-139">En la mayoría de los casos, es posible que un diagrama de actualización que realiza actualizaciones simples no requiera un esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="c618a-139">In most cases, an updategram that performs simple updates might not require a mapping schema.</span></span> <span data-ttu-id="c618a-140">En este caso, el diagrama de actualización se basa en el esquema de asignación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c618a-140">In this case, the updategram relies on the default mapping schema.</span></span>  
  
 <span data-ttu-id="c618a-141">En el diagrama de actualización siguiente se muestra una asignación implícita.</span><span class="sxs-lookup"><span data-stu-id="c618a-141">The following updategram demonstrates implicit mapping.</span></span> <span data-ttu-id="c618a-142">En este ejemplo, el diagrama de actualización inserta un nuevo cliente en la tabla Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="c618a-142">In this example, the updategram inserts a new customer in the Sales.Customer table.</span></span> <span data-ttu-id="c618a-143">Dado que este diagrama usa la asignación implícita, el \<Sales.Customer> elemento se asigna a la tabla sales. Customer y los atributos CustomerID y SalesPersonID se asignan a las columnas correspondientes de la tabla sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="c618a-143">Because this updategram uses implicit mapping, the \<Sales.Customer> element maps to the Sales.Customer table, and the CustomerID and SalesPersonID attributes map to the corresponding columns in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
</updg:before>  
<updg:after>  
    <Sales.Customer CustomerID="1" SalesPersonID="277" />  
    </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="explicit-mapping"></a><span data-ttu-id="c618a-144">Asignación explícita</span><span class="sxs-lookup"><span data-stu-id="c618a-144">Explicit Mapping</span></span>  
 <span data-ttu-id="c618a-145">Si especifica un esquema de asignación (ya sea XSD o XDR), el diagrama de actualización usa dicho esquema para determinar las columnas y las tablas de base de datos que van a actualizarse.</span><span class="sxs-lookup"><span data-stu-id="c618a-145">If you specify a mapping schema (either XSD or XDR), the updategram uses the schema to determine the database tables and columns that are to be updated.</span></span>  
  
 <span data-ttu-id="c618a-146">Si el diagrama de actualización realiza una actualización compleja (por ejemplo, insertando registros en varias tablas en base a la relación de elementos primarios y secundarios especificada en el esquema de asignación), deberá proporcionar el esquema de asignación de forma explícita mediante el atributo `mapping-schema` con el que se ejecuta el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="c618a-146">If the updategram performs a complex update (for example, inserting records in multiple tables on the basis of the parent-child relationship that is specified in the mapping schema), you must explicitly provide the mapping schema by using the `mapping-schema` attribute against which the updategram executes.</span></span>  
  
 <span data-ttu-id="c618a-147">Dado que un diagrama de actualización es una plantilla, la ruta de acceso especificada para el esquema de asignación en el diagrama de actualización es relativa a la ubicación del archivo de plantilla (con respecto al lugar donde se almacena el diagrama de actualización).</span><span class="sxs-lookup"><span data-stu-id="c618a-147">Because an updategram is a template, the path specified for the mapping schema in the updategram is relative to the location of the template file (relative to where the updategram is stored).</span></span> <span data-ttu-id="c618a-148">Para obtener más información, vea [especificar un esquema de asignación anotado en un diagrama &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c618a-148">For more information, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="element-centric-and-attribute-centric-mapping-in-updategrams"></a><span data-ttu-id="c618a-149">Asignación centrada en elementos y centrada en atributos en diagramas de actualización</span><span class="sxs-lookup"><span data-stu-id="c618a-149">Element-centric and Attribute-centric Mapping in Updategrams</span></span>  
 <span data-ttu-id="c618a-150">Con la asignación predeterminada (cuando el esquema de asignación no se especifica en el diagrama de actualización), los elementos del diagrama de actualización se asignan a tablas y los elementos secundarios (en el caso de la asignación centrada en elementos) y los atributos (en el caso de asignación centrada en atributos) se asignan a columnas.</span><span class="sxs-lookup"><span data-stu-id="c618a-150">With default mapping (when the mapping schema is not specified in the updategram), the updategram elements map to tables and the  child elements (in the case of element-centric mapping) and the attributes (in the case of attribute-centric mapping) map to columns.</span></span>  
  
### <a name="element-centric-mapping"></a><span data-ttu-id="c618a-151">Asignación centrada en elementos</span><span class="sxs-lookup"><span data-stu-id="c618a-151">Element-centric Mapping</span></span>  
 <span data-ttu-id="c618a-152">En un diagrama de actualización centrado en elementos, un elemento contiene elementos secundarios que denotan las propiedades del elemento.</span><span class="sxs-lookup"><span data-stu-id="c618a-152">In an element-centric updategram, an element contains child elements that denote the properties of the element.</span></span> <span data-ttu-id="c618a-153">Como ejemplo, consulte el diagrama de actualización siguiente.</span><span class="sxs-lookup"><span data-stu-id="c618a-153">As an example, refer to the following updategram.</span></span> <span data-ttu-id="c618a-154">El **\<Person.Contact>** elemento contiene los **\<FirstName>** **\<LastName>** elementos secundarios y.</span><span class="sxs-lookup"><span data-stu-id="c618a-154">The **\<Person.Contact>** element contains the **\<FirstName>** and **\<LastName>** child elements.</span></span> <span data-ttu-id="c618a-155">Estos elementos secundarios son propiedades del **\<Person.Contact>** elemento.</span><span class="sxs-lookup"><span data-stu-id="c618a-155">These child elements are properties of the **\<Person.Contact>** element.</span></span>  
  
 <span data-ttu-id="c618a-156">Dado que este diagrama no especifica un esquema de asignación, diagrama usa la asignación implícita, donde el **\<Person.Contact>** elemento se asigna a la tabla person. contact y sus elementos secundarios se asignan a las columnas FirstName y LastName.</span><span class="sxs-lookup"><span data-stu-id="c618a-156">Because this updategram does not specify a mapping schema, the updategram uses implicit mapping, where the **\<Person.Contact>** element maps to the Person.Contact table and its child elements map to the FirstName and LastName columns.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:after>  
    <Person.Contact>  
       <FirstName>Catherine</FirstName>  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="attribute-centric-mapping"></a><span data-ttu-id="c618a-157">asignación centrada en atributos</span><span class="sxs-lookup"><span data-stu-id="c618a-157">Attribute-centric Mapping</span></span>  
 <span data-ttu-id="c618a-158">En una asignación centrada en atributos, los elementos tienen atributos.</span><span class="sxs-lookup"><span data-stu-id="c618a-158">In an attribute-centric mapping, the elements have attributes.</span></span> <span data-ttu-id="c618a-159">El diagrama de actualización siguiente usa la asignación centrada en atributos.</span><span class="sxs-lookup"><span data-stu-id="c618a-159">The following updategram uses attribute-centric mapping.</span></span> <span data-ttu-id="c618a-160">En este ejemplo, el **\<Person.Contact>** elemento consta de los atributos **FirstName** y **LastName** .</span><span class="sxs-lookup"><span data-stu-id="c618a-160">In this example, the **\<Person.Contact>** element consists of the **FirstName** and **LastName** attributes.</span></span> <span data-ttu-id="c618a-161">Estos atributos son las propiedades del **\<Person.Contact>** elemento.</span><span class="sxs-lookup"><span data-stu-id="c618a-161">These attributes are the properties of the **\<Person.Contact>** element.</span></span> <span data-ttu-id="c618a-162">Como en el ejemplo anterior, este diagrama no especifica ningún esquema de asignación, por lo que se basa en la asignación implícita para asignar el **\<Person.Contact>** elemento a la tabla person. contact y los atributos del elemento a las columnas respectivas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c618a-162">As in the previous example, this updategram specifies no mapping schema, so it relies on implicit mapping to map the **\<Person.Contact>** element to the Person.Contact table and the element's attributes to the respective columns in the table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" LastName="Abel" />  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="using-both-element-centric-and-attribute-centric-mapping"></a><span data-ttu-id="c618a-163">Usar asignaciones centradas en elementos y centradas en atributos</span><span class="sxs-lookup"><span data-stu-id="c618a-163">Using Both Element-centric and Attribute-centric Mapping</span></span>  
 <span data-ttu-id="c618a-164">Puede especificar una combinación de asignaciones centradas en elementos y asignaciones centradas en atributos, tal y como se muestra en el diagrama de actualización siguiente.</span><span class="sxs-lookup"><span data-stu-id="c618a-164">You can specify a mix of element-centric and attribute-centric mapping, as shown in the following updategram.</span></span> <span data-ttu-id="c618a-165">Observe que el **\<Person.Contact>** elemento contiene un atributo y un elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="c618a-165">Notice that the **\<Person.Contact>** element contains both an attribute and a child element.</span></span> <span data-ttu-id="c618a-166">Asimismo, este diagrama de actualización se basa en la asignación implícita.</span><span class="sxs-lookup"><span data-stu-id="c618a-166">Also, this updategram relies on implicit mapping.</span></span> <span data-ttu-id="c618a-167">Por lo tanto, el atributo **FirstName** y el **\<LastName>** elemento secundario se asignan a las columnas correspondientes de la tabla person. contact.</span><span class="sxs-lookup"><span data-stu-id="c618a-167">Thus, the **FirstName** attribute and the **\<LastName>** child element map to corresponding columns in the Person.Contact table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" >  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="working-with-characters-valid-in-sql-server-but-not-valid-in-xml"></a><span data-ttu-id="c618a-168">Trabajar con caracteres que son válidos en SQL Server pero que no son válidos en XML</span><span class="sxs-lookup"><span data-stu-id="c618a-168">Working with Characters Valid in SQL Server but Not Valid in XML</span></span>  
 <span data-ttu-id="c618a-169">En [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], los nombres de tabla pueden incluir un espacio.</span><span class="sxs-lookup"><span data-stu-id="c618a-169">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space.</span></span> <span data-ttu-id="c618a-170">Sin embargo, este tipo de nombre de tabla no es válido en XML.</span><span class="sxs-lookup"><span data-stu-id="c618a-170">However, this type of table name is not valid in XML.</span></span>  
  
 <span data-ttu-id="c618a-171">Para codificar caracteres que son [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identificadores válidos pero que no son identificadores XML válidos, use ' __xHHHH \_ \_ ' como valor de codificación, donde HHHH representa el código UCS-2 hexadecimal de cuatro dígitos para el carácter en el orden más significativo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="c618a-171">To encode characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but are not valid XML identifiers, use '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="c618a-172">Con este esquema de codificación, un carácter de espacio se reemplaza por x0020 (el código hexadecimal de cuatro dígitos para un carácter de espacio); por lo tanto, el nombre de la tabla [Order Details] en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se _x005B_Order_x0020_Details_x005D \_ en XML.</span><span class="sxs-lookup"><span data-stu-id="c618a-172">Using this encoding scheme, a space character gets replaced with x0020 (the four-digit hexadecimal code for a space character); thus, the table name [Order Details] in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] becomes _x005B_Order_x0020_Details_x005D\_ in XML.</span></span>  
  
 <span data-ttu-id="c618a-173">Del mismo modo, es posible que necesite especificar nombres de elementos de tres partes, como \<[database].[owner].[table]> .</span><span class="sxs-lookup"><span data-stu-id="c618a-173">Similarly, you might need to specify three-part element names, such as \<[database].[owner].[table]>.</span></span> <span data-ttu-id="c618a-174">Dado que los caracteres de corchete ([y]) no son válidos en XML, debe especificarse como \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_> , donde _x005B \_ es la codificación del corchete de apertura ([) y _x005D \_ es la codificación del corchete de cierre (]).</span><span class="sxs-lookup"><span data-stu-id="c618a-174">Because the bracket characters ([ and ]) are not valid in XML, you must specify this as \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_>, where _x005B\_ is the encoding for the left bracket ([) and _x005D\_ is the encoding for the right bracket (]).</span></span>  
  
## <a name="executing-updategrams"></a><span data-ttu-id="c618a-175">Ejecutar diagramas de actualización</span><span class="sxs-lookup"><span data-stu-id="c618a-175">Executing Updategrams</span></span>  
 <span data-ttu-id="c618a-176">Dado que un diagrama de actualización es una plantilla, todos los mecanismos de procesamiento de una plantilla se aplican al diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="c618a-176">Because an updategram is a template, all the processing mechanisms of a template apply to the updategram.</span></span> <span data-ttu-id="c618a-177">Para SQLXML 4.0, puede ejecutar un diagrama de actualización de cualquiera de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="c618a-177">For SQLXML 4.0, you can execute an updategram in either of the following ways:</span></span>  
  
-   <span data-ttu-id="c618a-178">Enviándolo en un comando ADO.</span><span class="sxs-lookup"><span data-stu-id="c618a-178">By submitting it in an ADO command.</span></span>  
  
-   <span data-ttu-id="c618a-179">Enviándolo como un comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c618a-179">By submitting it as an OLE DB command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c618a-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c618a-180">See Also</span></span>  
 [<span data-ttu-id="c618a-181">Consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c618a-181">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
