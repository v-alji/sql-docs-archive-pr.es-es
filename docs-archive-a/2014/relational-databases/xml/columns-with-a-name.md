---
title: Columnas con un nombre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: c994e089-4cfc-4e9b-b7fc-e74f6014b51a
author: rothja
ms.author: jroth
ms.openlocfilehash: 32cfe617b80ed216374249961b85eae401011a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744542"
---
# <a name="columns-with-a-name"></a><span data-ttu-id="f64b2-102">Columnas con nombre</span><span class="sxs-lookup"><span data-stu-id="f64b2-102">Columns with a Name</span></span>
  <span data-ttu-id="f64b2-103">A continuación se exponen las condiciones específicas en las que se asignan al XML resultante las columnas con nombre de los conjuntos de filas, con distinción entre mayúsculas de minúsculas:</span><span class="sxs-lookup"><span data-stu-id="f64b2-103">The following are the specific conditions in which rowset columns with a name are mapped, case-sensitive, to the resulting XML:</span></span>  
  
-   <span data-ttu-id="f64b2-104">El nombre de la columna empieza por \@.</span><span class="sxs-lookup"><span data-stu-id="f64b2-104">The column name starts with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="f64b2-105">El nombre de la columna no empieza por \@.</span><span class="sxs-lookup"><span data-stu-id="f64b2-105">The column name does not start with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="f64b2-106">El nombre de la columna no empieza por \@ y contiene una barra diagonal (/).</span><span class="sxs-lookup"><span data-stu-id="f64b2-106">The column name does not start with an at sign\@ and contains a slash mark (/).</span></span>  
  
-   <span data-ttu-id="f64b2-107">Varias columnas comparten el mismo prefijo.</span><span class="sxs-lookup"><span data-stu-id="f64b2-107">Several columns share the same prefix.</span></span>  
  
-   <span data-ttu-id="f64b2-108">Una columna tiene un nombre distinto.</span><span class="sxs-lookup"><span data-stu-id="f64b2-108">One column has a different name.</span></span>  
  
## <a name="column-name-starts-with-an-at-sign-"></a><span data-ttu-id="f64b2-109">El nombre de la columna empieza por \@</span><span class="sxs-lookup"><span data-stu-id="f64b2-109">Column Name Starts with an At Sign (\@)</span></span>  
 <span data-ttu-id="f64b2-110">Si el nombre de columna comienza con un signo de arroba ( \@ ) y no contiene una barra diagonal (/), se crea un atributo del <`row`> elemento que tiene el valor de columna correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f64b2-110">If the column name starts with an at sign (\@) and does not contain a slash mark (/), an attribute of the <`row`> element that has the corresponding column value is created.</span></span> <span data-ttu-id="f64b2-111">Por ejemplo, la consulta siguiente devuelve un conjunto de filas con dos columnas (\@PmId y Name).</span><span class="sxs-lookup"><span data-stu-id="f64b2-111">For example, the following query returns a two-column (\@PmId, Name) rowset.</span></span> <span data-ttu-id="f64b2-112">En el XML resultante, se agrega un atributo **PmId** al elemento <`row`> correspondiente y se le asigna un valor de ProductModelID.</span><span class="sxs-lookup"><span data-stu-id="f64b2-112">In the resulting XML, a **PmId** attribute is added to the corresponding <`row`> element and a value of ProductModelID is assigned to it.</span></span>  
  
```  
  
SELECT ProductModelID as "@PmId",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
  
```  
  
 <span data-ttu-id="f64b2-113">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f64b2-113">This is the result:</span></span>  
  
```  
<row PmId="7">  
  <Name>HL Touring Frame</Name>  
</row>  
```  
  
 <span data-ttu-id="f64b2-114">Tenga en cuenta que los atributos deben aparecer antes de cualquier otro tipo de nodo, como los de elemento y texto, del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="f64b2-114">Note that attributes must come before any other node types, such as element nodes and text nodes, in the same level.</span></span> <span data-ttu-id="f64b2-115">La consulta siguiente devolverá un error:</span><span class="sxs-lookup"><span data-stu-id="f64b2-115">The following query will return an error:</span></span>  
  
```  
SELECT Name,  
       ProductModelID as "@PmId"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign-"></a><span data-ttu-id="f64b2-116">El nombre de la columna no empieza por \@</span><span class="sxs-lookup"><span data-stu-id="f64b2-116">Column Name Does Not Start with an At Sign (\@)</span></span>  
 <span data-ttu-id="f64b2-117">Si el nombre de la columna no empieza con un signo de arroba ( \@ ), no es una de las pruebas de nodo XPath y no contiene una barra diagonal (/), se crea un elemento XML que es un subelemento del elemento row <`row`> de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f64b2-117">If the column name does not start with an at sign (\@), is not one of the XPath node tests, and does not contain a slash mark (/), an XML element that is a subelement of the row element, <`row`> by default, is created.</span></span>  
  
 <span data-ttu-id="f64b2-118">La consulta siguiente especifica el nombre de la columna, el resultado.</span><span class="sxs-lookup"><span data-stu-id="f64b2-118">The following query specifies the column name, the result.</span></span> <span data-ttu-id="f64b2-119">Por tanto, se agrega un elemento secundario <`result`> al elemento <`row`>.</span><span class="sxs-lookup"><span data-stu-id="f64b2-119">Therefore, a <`result`> element child is added to the <`row`> element.</span></span>  
  
```  
SELECT 2+2 as result  
for xml PATH  
```  
  
 <span data-ttu-id="f64b2-120">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f64b2-120">This is the result:</span></span>  
  
```  
<row>  
  <result>4</result>  
</row>  
```  
  
 <span data-ttu-id="f64b2-121">La consulta siguiente especifica el nombre de la columna, ManuWorkCenterInformation, para el XML devuelto por la expresión XQuery especificada con la columna Instructions de tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="f64b2-121">The following query specifies the column name, ManuWorkCenterInformation, for the XML returned by the XQuery specified against Instructions column of **xml** type.</span></span> <span data-ttu-id="f64b2-122">Por tanto, se agrega un elemento <`ManuWorkCenterInformation`> como elemento secundario del elemento <`row`>.</span><span class="sxs-lookup"><span data-stu-id="f64b2-122">Therefore, a <`ManuWorkCenterInformation`> element is added as a child of the <`row`> element.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') as ManuWorkCenterInformation  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
 <span data-ttu-id="f64b2-123">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f64b2-123">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>7</ProductModelID>  
  <Name>HL Touring Frame</Name>  
  <ManuWorkCenterInformation>  
    <MI:Location ...LocationID="10" ...></MI:Location>  
    <MI:Location ...LocationID="20" ...></MI:Location>  
     ...  
  </ManuWorkCenterInformation>  
</row>  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign--and-contains-a-slash-mark-"></a><span data-ttu-id="f64b2-124">El nombre de la columna no empieza por \@ y contiene una barra diagonal (/)</span><span class="sxs-lookup"><span data-stu-id="f64b2-124">Column Name Does Not Start with an At Sign (\@) and Contains a Slash Mark (/)</span></span>  
 <span data-ttu-id="f64b2-125">Si el nombre de la columna no empieza por \@ pero incluye una barra diagonal (/), el nombre de la columna indica una jerarquía XML.</span><span class="sxs-lookup"><span data-stu-id="f64b2-125">If the column name does not start with an at sign (\@), but contains a slash mark (/), the column name indicates an XML hierarchy.</span></span> <span data-ttu-id="f64b2-126">Por ejemplo, si el nombre de la columna es "Name1/Name2/Name3.../Name***n*** ", cada Name***i*** representa un nombre de elemento que está anidado en el elemento de fila actual (para i=1) o que se encuentra debajo del elemento con el nombre Name***i-1***.</span><span class="sxs-lookup"><span data-stu-id="f64b2-126">For example, if the column name is "Name1/Name2/Name3.../Name***n*** ", each Name***i*** represents an element name that is nested in the current row element (for i=1) or that is under the element that has the name Name***i-1***.</span></span> <span data-ttu-id="f64b2-127">Si Name***n*** empieza por "\@", se asignará a un atributo del elemento Name***n-1***.</span><span class="sxs-lookup"><span data-stu-id="f64b2-127">If Name***n*** starts with '\@', it is mapped to an attribute of Name***n-1*** element.</span></span>  
  
 <span data-ttu-id="f64b2-128">Por ejemplo, la consulta siguiente devuelve un Id. y un nombre de empleado que están representados como un elemento EmpName complejo que incluye nombre, inicial y apellidos.</span><span class="sxs-lookup"><span data-stu-id="f64b2-128">For example, the following query returns an employee ID and name that are represented as a complex element EmpName that contains a First, Middle, and Last name.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="f64b2-129">Los nombres de columna se utilizan como una ruta de acceso en la creación de XML en el modo PATH.</span><span class="sxs-lookup"><span data-stu-id="f64b2-129">The column names are used as a path in constructing XML in the PATH mode.</span></span> <span data-ttu-id="f64b2-130">El nombre de columna que contiene los valores de ID. de empleado comienza por ' \@ '. Por lo tanto, se agrega un atributo, **empid**, al `row` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="f64b2-130">The column name that contains employee ID values, starts with '\@'.Therefore, an attribute, **EmpID**, is added to the <`row`> element.</span></span> <span data-ttu-id="f64b2-131">Todas las demás columnas incluyen una barra diagonal ('/') en el nombre de columna que indica la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="f64b2-131">All other columns include a slash mark ('/') in the column name that indicates hierarchy.</span></span> <span data-ttu-id="f64b2-132">El XML resultante tendrá el elemento secundario <`EmpName`> debajo del elemento <`row`>, y el elemento secundario <`EmpName`> tendrá los elementos secundarios <`First`>, <`Middle`> y <`Last`>.</span><span class="sxs-lookup"><span data-stu-id="f64b2-132">The resulting XML will have the <`EmpName`> child under the <`row`> element, and the <`EmpName`> child will have <`First`>, <`Middle`> and <`Last`> element children.</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="f64b2-133">El valor de la inicial del empleado es Null y, de forma predeterminada, el valor Null se asigna a la ausencia del elemento o atributo.</span><span class="sxs-lookup"><span data-stu-id="f64b2-133">The employee middle name is null and, by default, the null value maps to the absence of the element or attribute.</span></span> <span data-ttu-id="f64b2-134">Si desea que se generen elementos para los valores NULL, puede especificar la directiva ELEMENTS con XSINIL tal y como se muestra en esta consulta.</span><span class="sxs-lookup"><span data-stu-id="f64b2-134">If you want elements generated for the NULL values, you can specify the ELEMENTS directive with XSINIL as shown in this query.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="f64b2-135">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f64b2-135">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
      EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="f64b2-136">De forma predeterminada, el modo PATH genera XML centrado en elementos.</span><span class="sxs-lookup"><span data-stu-id="f64b2-136">By default, the PATH mode generates element-centric XML.</span></span> <span data-ttu-id="f64b2-137">Por tanto, la especificación de la directiva ELEMENTS en una consulta de modo PATH no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="f64b2-137">Therefore, specifying the ELEMENTS directive in a PATH mode query has no effect.</span></span> <span data-ttu-id="f64b2-138">No obstante, tal y como se muestra en el ejemplo anterior, la directiva ELEMENTS resulta útil con XSINIL a fin de generar elementos para valores Null.</span><span class="sxs-lookup"><span data-stu-id="f64b2-138">However, as shown in the previous example, the ELEMENTS directive is useful with XSINIL to generate elements for null values.</span></span>  
  
 <span data-ttu-id="f64b2-139">Además del Id. y el nombre, la consulta siguiente recupera una dirección del empleado.</span><span class="sxs-lookup"><span data-stu-id="f64b2-139">Besides the ID and name, the following query retrieves an employee address.</span></span> <span data-ttu-id="f64b2-140">Según la ruta de acceso de los nombres de las columnas de direcciones, se agregará un elemento secundario <`Address`> al elemento <`row`> y los detalles de la dirección se agregarán como elemento secundario del elemento <`Address`>.</span><span class="sxs-lookup"><span data-stu-id="f64b2-140">As per the path in the column names for address columns, an <`Address`> element child is added to the <`row`> element and the address details are added as element children of the <`Address`> element.</span></span>  
  
```  
SELECT EmployeeID   "@EmpID",   
       FirstName    "EmpName/First",   
       MiddleName   "EmpName/Middle",   
       LastName     "EmpName/Last",  
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City         "Address/City"  
FROM   HumanResources.Employee E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="f64b2-141">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f64b2-141">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
</row>  
```  
  
## <a name="several-columns-share-the-same-path-prefix"></a><span data-ttu-id="f64b2-142">Varias columnas comparten el mismo prefijo de ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="f64b2-142">Several Columns Share the Same Path Prefix</span></span>  
 <span data-ttu-id="f64b2-143">Si varias columnas consecutivas comparten el mismo prefijo de ruta de acceso, se agruparán con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="f64b2-143">If several subsequent columns share the same path prefix, they are grouped together under the same name.</span></span> <span data-ttu-id="f64b2-144">Si se utilizan distintos prefijos de espacio de nombres aunque estén enlazados al mismo espacio de nombres, una ruta de acceso se considerará diferente.</span><span class="sxs-lookup"><span data-stu-id="f64b2-144">If different namespace prefixes are being used even if they are bound to the same namespace, a path is considered different.</span></span> <span data-ttu-id="f64b2-145">En la consulta anterior, las columnas FirstName, MiddleName y LastName comparten el mismo prefijo EmpName. Por tanto, se agregarán como elementos secundarios del elemento <`EmpName`>.</span><span class="sxs-lookup"><span data-stu-id="f64b2-145">In the previous query, the FirstName, MiddleName, and LastName columns share the same EmpName prefix.Therefore, they are added as children of the <`EmpName`> element.</span></span> <span data-ttu-id="f64b2-146">Lo mismo ocurrió al crear el elemento <`Address`> en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f64b2-146">This is also the case when you were creating the <`Address`> element in the previous example.</span></span>  
  
## <a name="one-column-has-a-different-name"></a><span data-ttu-id="f64b2-147">Una columna tiene un nombre distinto</span><span class="sxs-lookup"><span data-stu-id="f64b2-147">One Column Has a Different Name</span></span>  
 <span data-ttu-id="f64b2-148">Si aparece una columna con un nombre distinto, interrumpirá la agrupación, tal y como se muestra en la siguiente consulta modificada.</span><span class="sxs-lookup"><span data-stu-id="f64b2-148">If a column with a different name appears in between, it will break the grouping, as shown in the following modified query.</span></span> <span data-ttu-id="f64b2-149">La consulta interrumpe la agrupación de FirstName, MiddleName y LastName, tal y como se especificaba en la consulta anterior, al agregar columnas de dirección entre las columnas FirstName y MiddleName.</span><span class="sxs-lookup"><span data-stu-id="f64b2-149">The query breaks the grouping of FirstName, MiddleName, and LastName, as specified in the previous query, by adding address columns in between the FirstName and MiddleName columns.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName "EmpName/First",   
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City "Address/City",  
       MiddleName "EmpName/Middle",   
       LastName "EmpName/Last"  
FROM   HumanResources.EmployeeAddress E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="f64b2-150">Como resultado, la consulta crea dos elementos <`EmpName`>.</span><span class="sxs-lookup"><span data-stu-id="f64b2-150">As a result, the query creates two <`EmpName`> elements.</span></span> <span data-ttu-id="f64b2-151">El primer elemento <`EmpName`> tiene el elemento secundario <`FirstName`> y el segundo elemento <`EmpName`> tiene los elementos secundarios <`MiddleName`> y <`LastName`>.</span><span class="sxs-lookup"><span data-stu-id="f64b2-151">The first <`EmpName`> element has the <`FirstName`> element child and the second <`EmpName`> element has the <`MiddleName`> and <`LastName`> element children.</span></span>  
  
 <span data-ttu-id="f64b2-152">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f64b2-152">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
  <EmpName>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f64b2-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f64b2-153">See Also</span></span>  
 [<span data-ttu-id="f64b2-154">Usar el modo PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="f64b2-154">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
