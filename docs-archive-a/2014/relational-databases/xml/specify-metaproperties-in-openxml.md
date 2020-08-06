---
title: Especificar metapropiedades en OPENXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- overflow in XML document [SQL Server]
- metaproperties [XML in SQL Server]
- unconsumed data
- extracting information of XML nodes [SQL Server]
- OPENXML statement, metaproperties
ms.assetid: 29bfd1c6-3f9a-43c4-924a-53d438e442f4
author: rothja
ms.author: jroth
ms.openlocfilehash: c52d1162aa495deff8a0fde314fdcde0735d9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747529"
---
# <a name="specify-metaproperties-in-openxml"></a><span data-ttu-id="1ab94-102">Especificar metapropiedades en OPENXML</span><span class="sxs-lookup"><span data-stu-id="1ab94-102">Specify Metaproperties in OPENXML</span></span>
  <span data-ttu-id="1ab94-103">Los atributos de las metapropiedades de un documento XML son atributos que describen las propiedades de un elemento XML (como elemento, atributo o cualquier otro nodo DOM).</span><span class="sxs-lookup"><span data-stu-id="1ab94-103">Metaproperty attributes in an XML document are attributes that describe the properties of an XML item, such as element, attribute, or any other DOM node.</span></span> <span data-ttu-id="1ab94-104">Estos atributos no existen físicamente en el texto del documento XML.</span><span class="sxs-lookup"><span data-stu-id="1ab94-104">These attributes do not physically exist in the XML document text.</span></span> <span data-ttu-id="1ab94-105">Sin embargo, OPENXML proporciona estas metapropiedades para todos los elementos XML.</span><span class="sxs-lookup"><span data-stu-id="1ab94-105">However, OPENXML provides these metaproperties for all the XML items.</span></span> <span data-ttu-id="1ab94-106">Estas metapropiedades permiten extraer información, como la posición local e información de espacio de nombres, de los nodos XML.</span><span class="sxs-lookup"><span data-stu-id="1ab94-106">These metaproperties allow you to extract information, such as local positioning and namespace information, of XML nodes.</span></span> <span data-ttu-id="1ab94-107">Esta información ofrece más detalles de los que aparentemente hay en la representación textual.</span><span class="sxs-lookup"><span data-stu-id="1ab94-107">This information provides you with more details than are apparent in the textual representation.</span></span>  
  
 <span data-ttu-id="1ab94-108">Estas metapropiedades se pueden asignar a las columnas del conjunto de filas en una instrucción OPENXML mediante el parámetro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="1ab94-108">You can map these metaproperties to the rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span> <span data-ttu-id="1ab94-109">Las columnas contendrán los valores de las metapropiedades a las que se asignan.</span><span class="sxs-lookup"><span data-stu-id="1ab94-109">The columns will contain the values of the metaproperties to which they are mapped.</span></span> <span data-ttu-id="1ab94-110">Para obtener más información sobre la sintaxis de OPENXML, vea [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ab94-110">For more information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span>  
  
 <span data-ttu-id="1ab94-111">Para tener acceso a los atributos de las metapropiedades, se proporciona un espacio de nombres específico de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1ab94-111">To access the metaproperty attributes, a namespace that is specific to SQL Server is provided.</span></span> <span data-ttu-id="1ab94-112">Este espacio de nombres, **urn:schemas-microsoft-com:xml-metaprop** , permite al usuario tener acceso a los atributos de las metapropiedades.</span><span class="sxs-lookup"><span data-stu-id="1ab94-112">This namespace, **urn:schemas-microsoft-com:xml-metaprop** allows the user to access the metaproperty attributes.</span></span> <span data-ttu-id="1ab94-113">Si se devuelve el resultado de una consulta OPENXML en un formato de tabla irregular, dicha tabla contiene una columna para cada atributo de metapropiedad, excepto para la metapropiedad **xmltext** .</span><span class="sxs-lookup"><span data-stu-id="1ab94-113">If the result of an OPENXML query is returned in an edge table format, the edge table contains one column for each metaproperty attribute, except the **xmltext** metaproperty.</span></span>  
  
 <span data-ttu-id="1ab94-114">Algunos de los atributos de metapropiedades se utilizan para el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-114">Some of the metaproperty attributes are used for processing purposes.</span></span> <span data-ttu-id="1ab94-115">Por ejemplo, el atributo de metapropiedad **xmltext** se utiliza para controlar el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-115">For example, the **xmltext** metaproperty attribute is used for overflow handling.</span></span> <span data-ttu-id="1ab94-116">El control del desbordamiento se refiere a los datos no utilizados ni procesados del documento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-116">Overflow handling refers to the unconsumed, unprocessed data in the document.</span></span> <span data-ttu-id="1ab94-117">Una de las columnas del conjunto de filas que se genera mediante OPENXML se puede identificar como la columna de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-117">One of the columns in the rowset that is generated by OPENXML can be identified as the overflow column.</span></span> <span data-ttu-id="1ab94-118">Para ello, la columna se asigna a la metapropiedad **xmltext** mediante el parámetro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="1ab94-118">You do this by mapping it to the **xmltext** metaproperty by using the *ColPattern* parameter.</span></span> <span data-ttu-id="1ab94-119">En ese caso, la columna recibirá los datos de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-119">The column then receives the overflow data.</span></span> <span data-ttu-id="1ab94-120">El parámetro *flags* determina si la columna contiene todo o solo los datos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1ab94-120">The *flags* parameter determines whether the column contains everything or only the unconsumed data.</span></span>  
  
 <span data-ttu-id="1ab94-121">La siguiente tabla muestra una lista de los atributos de las metapropiedades que posee cada elemento XML analizado.</span><span class="sxs-lookup"><span data-stu-id="1ab94-121">The following table lists the metaproperty attributes that each parsed XML element possesses.</span></span> <span data-ttu-id="1ab94-122">Se puede obtener acceso a estos atributos de las metapropiedades mediante el espacio de nombres **urn:schemas-microsoft-com:xml-metaprop**.</span><span class="sxs-lookup"><span data-stu-id="1ab94-122">These metaproperty attributes can be accessed by using the namespace **urn:schemas-microsoft-com:xml-metaprop**.</span></span> <span data-ttu-id="1ab94-123">Se descarta cualquier valor que el usuario establezca directamente en el documento XML mediante estas metapropiedades.</span><span class="sxs-lookup"><span data-stu-id="1ab94-123">Any value that the user sets directly in the XML document by using these metaproperties is ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ab94-124">No se puede hacer referencia a estas metapropiedades en ninguna navegación XPath.</span><span class="sxs-lookup"><span data-stu-id="1ab94-124">You cannot reference these metaproperties in any XPath navigation.</span></span>  
  
|<span data-ttu-id="1ab94-125">Atributo de metapropiedad</span><span class="sxs-lookup"><span data-stu-id="1ab94-125">Metaproperty attribute</span></span>|<span data-ttu-id="1ab94-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ab94-126">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="1ab94-127">**\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="1ab94-127">**\@mp:id**</span></span>|<span data-ttu-id="1ab94-128">Proporciona un identificador del nodo DOM generado por el sistema para todo el documento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-128">Provides a system-generated, document-wide identifier of the DOM node.</span></span> <span data-ttu-id="1ab94-129">Este Id. hace referencia al mismo nodo XML siempre y cuando no se vuelva a analizar el documento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-129">As long as the document is not reparsed, this ID refers to the same XML node.</span></span><br /><br /> <span data-ttu-id="1ab94-130">Si el Id. XML es **0** , significa que se trata de un elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="1ab94-130">An XML ID of **0** indicates that the element is a root element.</span></span> <span data-ttu-id="1ab94-131">El Id. XML del elemento primario es NULL.</span><span class="sxs-lookup"><span data-stu-id="1ab94-131">Its parent XML ID is NULL.</span></span>|  
|<span data-ttu-id="1ab94-132">**\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="1ab94-132">**\@mp:localname**</span></span>|<span data-ttu-id="1ab94-133">Almacena la parte local del nombre del nodo.</span><span class="sxs-lookup"><span data-stu-id="1ab94-133">Stores the local part of the name of the node.</span></span> <span data-ttu-id="1ab94-134">Se utiliza con un prefijo y un URI del espacio de nombres para asignar nombres a los nodos de elemento o atributo.</span><span class="sxs-lookup"><span data-stu-id="1ab94-134">It is used with a prefix and a namespace URI to name element or attribute nodes.</span></span>|  
|<span data-ttu-id="1ab94-135">**\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="1ab94-135">**\@mp:namespaceuri**</span></span>|<span data-ttu-id="1ab94-136">Proporciona el URI del espacio de nombres del elemento actual.</span><span class="sxs-lookup"><span data-stu-id="1ab94-136">Provides the namespace URI of the current element.</span></span> <span data-ttu-id="1ab94-137">Si el valor de este atributo es NULL, no hay ningún espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1ab94-137">If the value of this attribute is NULL, no namespace is present</span></span>|  
|<span data-ttu-id="1ab94-138">**\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="1ab94-138">**\@mp:prefix**</span></span>|<span data-ttu-id="1ab94-139">Almacena el prefijo del espacio de nombres del nombre del elemento actual.</span><span class="sxs-lookup"><span data-stu-id="1ab94-139">Stores the namespace prefix of the current element name.</span></span><br /><br /> <span data-ttu-id="1ab94-140">Si no hay ningún prefijo (NULL) y se proporciona un URI, significa que el espacio de nombres especificado es el espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1ab94-140">If no prefix is present (NULL) and a URI is given, it indicates that the specified namespace is the default namespace.</span></span> <span data-ttu-id="1ab94-141">Si no se proporciona ningún URI, no se adjunta ningún espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1ab94-141">If no URI is given, no namespace is attached.</span></span>|  
|<span data-ttu-id="1ab94-142">**\@mp:prev**</span><span class="sxs-lookup"><span data-stu-id="1ab94-142">**\@mp:prev**</span></span>|<span data-ttu-id="1ab94-143">Almacena el nodo anterior relacionado con un nodo.</span><span class="sxs-lookup"><span data-stu-id="1ab94-143">Stores the previous sibling relative to a node.</span></span> <span data-ttu-id="1ab94-144">Proporciona información sobre el orden de los elementos del documento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-144">This provides information about the ordering of elements in the document.</span></span><br /><br /> <span data-ttu-id="1ab94-145">**\@mp:prev** contiene el identificador XML del nodo relacionado anterior que tiene el mismo elemento principal.</span><span class="sxs-lookup"><span data-stu-id="1ab94-145">**\@mp:prev** contains the XML ID of the previous sibling that has the same parent element.</span></span> <span data-ttu-id="1ab94-146">Si un elemento está al principio de la lista de nodos relacionados, **\@mp:prev** es NULL.</span><span class="sxs-lookup"><span data-stu-id="1ab94-146">If an element is at the front of the sibling list, **\@mp:prev** is NULL.</span></span>|  
|<span data-ttu-id="1ab94-147">**\@mp:xmltext**</span><span class="sxs-lookup"><span data-stu-id="1ab94-147">**\@mp:xmltext**</span></span>|<span data-ttu-id="1ab94-148">Se utiliza para el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-148">Used for processing purposes.</span></span> <span data-ttu-id="1ab94-149">Se trata de la serialización textual del elemento y sus atributos, y de los subelementos, tal como se utiliza en el control de desbordamiento de OPENXML.</span><span class="sxs-lookup"><span data-stu-id="1ab94-149">It is the textual serialization of the element and its attributes, and also the subelements, as used in the overflow handling of OPENXML.</span></span>|  
  
 <span data-ttu-id="1ab94-150">Esta tabla muestra las propiedades adicionales que se proporcionan para los elementos primarios, que permiten recuperar información acerca de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="1ab94-150">This table shows the additional parent properties that are provided and which allow you to retrieve information about the hierarchy.</span></span>  
  
|<span data-ttu-id="1ab94-151">Atributo de metapropiedad Parent</span><span class="sxs-lookup"><span data-stu-id="1ab94-151">Parent metaproperty attribute</span></span>|<span data-ttu-id="1ab94-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ab94-152">Description</span></span>|  
|-----------------------------------|-----------------|  
|<span data-ttu-id="1ab94-153">**\@mp:parentid**</span><span class="sxs-lookup"><span data-stu-id="1ab94-153">**\@mp:parentid**</span></span>|<span data-ttu-id="1ab94-154">Se corresponde con **../\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="1ab94-154">Corresponds to **../\@mp:id**</span></span>|  
|<span data-ttu-id="1ab94-155">**\@mp:parentlocalname**</span><span class="sxs-lookup"><span data-stu-id="1ab94-155">**\@mp:parentlocalname**</span></span>|<span data-ttu-id="1ab94-156">Se corresponde con **../\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="1ab94-156">Corresponds to **../\@mp:localname**</span></span>|  
|<span data-ttu-id="1ab94-157">**\@mp:parentnamespacerui**</span><span class="sxs-lookup"><span data-stu-id="1ab94-157">**\@mp:parentnamespacerui**</span></span>|<span data-ttu-id="1ab94-158">Se corresponde con **../\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="1ab94-158">Corresponds to **../\@mp:namespaceuri**</span></span>|  
|<span data-ttu-id="1ab94-159">**\@mp:parentprefix**</span><span class="sxs-lookup"><span data-stu-id="1ab94-159">**\@mp:parentprefix**</span></span>|<span data-ttu-id="1ab94-160">Se corresponde con **../\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="1ab94-160">Corresponds to **../\@mp:prefix**</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="1ab94-161">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1ab94-161">Examples</span></span>  
 <span data-ttu-id="1ab94-162">En los ejemplos siguientes se muestra cómo se utiliza OPENXML para crear distintas vistas de conjuntos de filas.</span><span class="sxs-lookup"><span data-stu-id="1ab94-162">The following examples illustrate how OPENXML is used to create different rowset views.</span></span>  
  
### <a name="a-mapping-the-openxml-rowset-columns-to-the-metaproperties"></a><span data-ttu-id="1ab94-163">A.</span><span class="sxs-lookup"><span data-stu-id="1ab94-163">A.</span></span> <span data-ttu-id="1ab94-164">Asignar las columnas de conjunto de filas OPENXML a las metapropiedades</span><span class="sxs-lookup"><span data-stu-id="1ab94-164">Mapping the OPENXML rowset columns to the metaproperties</span></span>  
 <span data-ttu-id="1ab94-165">Este ejemplo utiliza OPENXML para crear una vista de conjunto de filas del documento XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ab94-165">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="1ab94-166">Concretamente, muestra cómo se pueden asignar los distintos atributos de metapropiedades a columnas de conjunto de filas en una instrucción OPENXML mediante el parámetro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="1ab94-166">Specifically, it shows how the various metaproperty attributes can be mapped to rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="1ab94-167">La instrucción OPENXML muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ab94-167">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="1ab94-168">La columna **id** se asigna al atributo de metapropiedad **\@mp:id** e indica que la columna contiene el id. XML único del elemento, generado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="1ab94-168">The **id** column is mapped to the **\@mp:id** metaproperty attribute and indicates that the column contains the system-generated unique XML ID of the element.</span></span>  
  
-   <span data-ttu-id="1ab94-169">La columna **parent** se asigna a **\@mp:parentid** e indica que la columna contiene el Id. XML del elemento primario del elemento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-169">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent of the element.</span></span>  
  
-   <span data-ttu-id="1ab94-170">La columna **parentLocalName** se asigna a **\@mp:parentlocalname** e indica que la columna contiene el nombre local del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="1ab94-170">The **parentLocalName** column is mapped to **\@mp:parentlocalname** and indicates that the column contains the local name of the parent.</span></span>  
  
 <span data-ttu-id="1ab94-171">Y, a continuación, la instrucción SELECT devuelve el conjunto de filas proporcionado por OPENXML.</span><span class="sxs-lookup"><span data-stu-id="1ab94-171">The SELECT statement then returns the rowset that is provided by OPENXML:</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- Sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (id int '@mp:id',   
            oid char(5),   
            date datetime,   
            amount real,   
            parentIDNo int '@mp:parentid',   
            parentLocalName varchar(40) '@mp:parentlocalname')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="1ab94-172">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ab94-172">This is the result:</span></span>  
  
```  
id   oid         date                amount    parentIDNo  parentLocalName    
--- ------- ---------------------- ---------- ------------ ---------------  
6    O1    1996-01-20 00:00:00.000     3.5         2        Customer  
10   O2    1997-04-30 00:00:00.000     13.4        2        Customer  
19   O3    1999-07-14 00:00:00.000     100.0       15       Customer  
25   O4    1996-01-20 00:00:00.000     10000.0     15       Customer  
```  
  
### <a name="b-retrieving-the-whole-xml-document"></a><span data-ttu-id="1ab94-173">B.</span><span class="sxs-lookup"><span data-stu-id="1ab94-173">B.</span></span> <span data-ttu-id="1ab94-174">Recuperar todo el documento XML</span><span class="sxs-lookup"><span data-stu-id="1ab94-174">Retrieving the whole XML document</span></span>  
 <span data-ttu-id="1ab94-175">En este ejemplo, se usa OPENXML para crear una vista de conjunto de filas de una columna del documento XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ab94-175">In this example, OPENXML is used to create a one-column rowset view of the sample XML document.</span></span> <span data-ttu-id="1ab94-176">Esta columna ( **Col1**) se asigna a la metapropiedad **xmltext** y se convierte en una columna de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-176">This column, **Col1**, is mapped to the **xmltext** metaproperty and becomes an overflow column.</span></span> <span data-ttu-id="1ab94-177">Como consecuencia, la columna recibe los datos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1ab94-177">As a result, the column receives the unconsumed data.</span></span> <span data-ttu-id="1ab94-178">En este caso es todo el documento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-178">In this case, it is the whole document.</span></span>  
  
 <span data-ttu-id="1ab94-179">A continuación, la instrucción SELECT devuelve el conjunto de filas completo.</span><span class="sxs-lookup"><span data-stu-id="1ab94-179">The SELECT statement then returns the complete rowset.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
SET @doc = N'<?xml version="1.0"?>  
<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
     <MyTag>Testing to see if all the subelements are returned</MyTag>  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/')  
   WITH (Col1 ntext '@mp:xmltext')  
```  
  
 <span data-ttu-id="1ab94-180">Para recuperar todo el documento sin la declaración XML, se puede especificar la consulta como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="1ab94-180">To retrieve the whole document without the XML declaration, the query can be specified as shown in the following:</span></span>  
  
```  
SELECT *  
FROM OPENXML (@idoc, '/root')  
   WITH (Col1 ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="1ab94-181">La consulta devuelve el elemento raíz que tiene la raíz del nombre y los datos contenidos en el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="1ab94-181">The query returns the root element that has the name root and the data that is contained by the root element</span></span>  
  
### <a name="c-specifying-the-xmltext-metaproperty-to-retrieve-the-unconsumed-data-in-a-column"></a><span data-ttu-id="1ab94-182">C.</span><span class="sxs-lookup"><span data-stu-id="1ab94-182">C.</span></span> <span data-ttu-id="1ab94-183">Especificar la metapropiedad xmltext para recuperar los datos no usados en una columna</span><span class="sxs-lookup"><span data-stu-id="1ab94-183">Specifying the xmltext metaproperty to retrieve the unconsumed data in a column</span></span>  
 <span data-ttu-id="1ab94-184">Este ejemplo utiliza OPENXML para crear una vista de conjunto de filas del documento XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ab94-184">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="1ab94-185">Muestra cómo recuperar los datos XML no utilizados mediante la asignación del atributo de metapropiedad **xmltext** a una columna de conjunto de filas en OPENXML.</span><span class="sxs-lookup"><span data-stu-id="1ab94-185">The example shows how to retrieve unconsumed XML data by mapping the **xmltext** metaproperty attribute to a rowset column in OPENXML.</span></span>  
  
 <span data-ttu-id="1ab94-186">La columna **comment** se identifica como la columna de desbordamiento al asignarla a la metapropiedad **\@mp:xmltext**.</span><span class="sxs-lookup"><span data-stu-id="1ab94-186">The **comment** column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span> <span data-ttu-id="1ab94-187">El parámetro *flags* se establece en **9** (XML_ATTRIBUTE y XML_NOCOPY).</span><span class="sxs-lookup"><span data-stu-id="1ab94-187">The *flags* parameter is set to **9** (XML_ATTRIBUTE and XML_NOCOPY).</span></span> <span data-ttu-id="1ab94-188">Esto indica que es una asignación **centrada en atributos** y que solo deberían copiarse los datos no usados en la columna de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-188">This indicates **attribute-centric** mapping and indicates that only the unconsumed data should be copied to the overflow column.</span></span>  
  
 <span data-ttu-id="1ab94-189">A continuación, la instrucción SELECT devuelve el conjunto de filas proporcionado por OPENXML.</span><span class="sxs-lookup"><span data-stu-id="1ab94-189">The SELECT statement then returns the rowset provided by OPENXML.</span></span>  
  
 <span data-ttu-id="1ab94-190">En este ejemplo, se establece la metapropiedad **\@mp:parentlocalname** para una columna **ParentLocalName** del conjunto de filas generado por OPENXML.</span><span class="sxs-lookup"><span data-stu-id="1ab94-190">In this example, the **\@mp:parentlocalname** metaproperty is set for a column, **ParentLocalName**, in the rowset generated by OPENXML.</span></span> <span data-ttu-id="1ab94-191">Como resultado, esta columna contiene el nombre local del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="1ab94-191">As a result, this column contains the local name of the parent element.</span></span>  
  
 <span data-ttu-id="1ab94-192">Se especifican dos columnas adicionales en el conjunto de filas, **parent** y **comment**.</span><span class="sxs-lookup"><span data-stu-id="1ab94-192">Two additional columns are specified in the rowset, **parent** and **comment**.</span></span> <span data-ttu-id="1ab94-193">La columna **parent** se asigna a **\@mp:parentid** e indica que la columna contiene el Id. XML del elemento primario del elemento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-193">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent element of the element.</span></span> <span data-ttu-id="1ab94-194">La columna comment se identifica como la columna de desbordamiento al asignarla a la metapropiedad **\@mp:xmltext**.</span><span class="sxs-lookup"><span data-stu-id="1ab94-194">The comment column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>  
'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (oid char(5),   
            date datetime,  
            comment ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="1ab94-195">Éste es el resultado.</span><span class="sxs-lookup"><span data-stu-id="1ab94-195">This is the result.</span></span> <span data-ttu-id="1ab94-196">Como las columnas oid y date ya se han utilizado, no aparecen en la columna de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="1ab94-196">Because the oid columns and date columns are already consumed, they do not appear in the overflow column.</span></span>  
  
```  
oid   date                        comment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
----- --------------------------- ----------------------------------------  
O1    1996-01-20 00:00:00.000     <Order amount="3.5"/>  
O2    1997-04-30 00:00:00.000     <Order amount="13.4">Customer was very   
                                   satisfied</Order>  
O3    1999-07-14 00:00:00.000     <Order amount="100" note="Wrap it blue   
                                   white red"><Urgency>   
                                   Important</Urgency></Order>  
O4    1996-01-20 00:00:00.000     <Order amount="10000"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ab94-197">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ab94-197">See Also</span></span>  
 <span data-ttu-id="1ab94-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ab94-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="1ab94-199">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ab94-199">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
