---
title: 'Ejemplo: Recuperación de información de los empleados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- EXPLICIT mode
ms.assetid: 63cd6569-2600-485b-92b4-1f6ba09db219
author: rothja
ms.author: jroth
ms.openlocfilehash: ae4578aedb7dbcc63388d5ef797e3a0bf5d8c306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673561"
---
# <a name="example-retrieving-employee-information"></a><span data-ttu-id="18b9e-102">Ejemplo: Recuperación de información de los empleados</span><span class="sxs-lookup"><span data-stu-id="18b9e-102">Example: Retrieving Employee Information</span></span>
  <span data-ttu-id="18b9e-103">En este ejemplo, se recupera el identificador y el nombre de cada empleado.</span><span class="sxs-lookup"><span data-stu-id="18b9e-103">This example retrieves an employee ID and employee name for each employee.</span></span> <span data-ttu-id="18b9e-104">En la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , el identificador de empleado se puede obtener de la columna BusinessEntityID de la tabla Employee.</span><span class="sxs-lookup"><span data-stu-id="18b9e-104">In the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, the employeeID can be obtained from the BusinessEntityID column in the Employee table.</span></span> <span data-ttu-id="18b9e-105">Los nombres de los empleados se pueden obtener de la tabla Person.</span><span class="sxs-lookup"><span data-stu-id="18b9e-105">Employee names can be obtained from the Person table.</span></span> <span data-ttu-id="18b9e-106">Para combinar las tablas, se puede usar la columna BusinessEntityID.</span><span class="sxs-lookup"><span data-stu-id="18b9e-106">The BusinessEntityID column can be used to join the tables.</span></span>  
  
 <span data-ttu-id="18b9e-107">Supongamos que desea una transformación FOR XML EXPLICIT para generar XML como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="18b9e-107">Assume that you want FOR XML EXPLICIT transformation to generate XML as shown in the following:</span></span>  
  
```  
<Employee EmpID="1" >  
  <Name FName="Ken" LName="S??nchez" />  
</Employee>  
...  
```  
  
 <span data-ttu-id="18b9e-108">Dado que hay dos niveles en la jerarquía, habría que escribir dos consultas `SELECT` y aplicar UNION ALL.</span><span class="sxs-lookup"><span data-stu-id="18b9e-108">Because there are two levels in the hierarchy, you would write two `SELECT` queries and apply UNION ALL.</span></span> <span data-ttu-id="18b9e-109">Esta es la primera consulta, que recupera los valores correspondientes al elemento <`Employee`> y sus atributos.</span><span class="sxs-lookup"><span data-stu-id="18b9e-109">This is the first query that retrieves values for the <`Employee`> element and its attributes.</span></span> <span data-ttu-id="18b9e-110">La consulta asigna `1` como valor `Tag` para el elemento <`Employee`> y NULL como `Parent`, puesto que se trata del elemento de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="18b9e-110">The query assigns `1` as `Tag` value for the <`Employee`> element and NULL as `Parent`, because it is the top-level element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID AS [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="18b9e-111">Esta es la segunda consulta.</span><span class="sxs-lookup"><span data-stu-id="18b9e-111">This is the second query.</span></span> <span data-ttu-id="18b9e-112">Recupera los valores correspondientes al elemento <`Name`>.</span><span class="sxs-lookup"><span data-stu-id="18b9e-112">It retrieves values for the <`Name`> element.</span></span> <span data-ttu-id="18b9e-113">Asigna `2` como valor de `Tag` para el elemento <`Name`> y 1 como valor de etiqueta en `1` como valor de etiqueta `Parent` que identifica <`Employee`> como elemento primario.</span><span class="sxs-lookup"><span data-stu-id="18b9e-113">It assigns `2` as `Tag` value for the <`Name`> element and `1` as `Parent` tag value identifying <`Employee`> as the parent.</span></span>  
  
```  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="18b9e-114">Combina estas consultas con `UNION AL`L, aplica `FOR XML EXPLICIT`y especifica la cláusula `ORDER BY` querida.</span><span class="sxs-lookup"><span data-stu-id="18b9e-114">You combine these queries with `UNION AL`L, apply `FOR XML EXPLICIT`, and specify the required `ORDER BY` clause.</span></span> <span data-ttu-id="18b9e-115">El conjunto de filas se debe ordenar primero según el valor de `BusinessEntityID` y, a continuación, por nombre, de modo que los valores NULL en el nombre aparezcan al principio.</span><span class="sxs-lookup"><span data-stu-id="18b9e-115">You must sort the rowset first by `BusinessEntityID` and then by name so that the NULL values in the name appear first.</span></span> <span data-ttu-id="18b9e-116">Si ejecuta la siguiente consulta sin la cláusula FOR XML, podrá ver la tabla universal generada.</span><span class="sxs-lookup"><span data-stu-id="18b9e-116">By executing the following query without the FOR XML clause, you can see the universal table generated.</span></span>  
  
 <span data-ttu-id="18b9e-117">Esta es la consulta final:</span><span class="sxs-lookup"><span data-stu-id="18b9e-117">This is the final query:</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
ORDER BY [Employee!1!EmpID],[Name!2!FName]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="18b9e-118">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="18b9e-118">This is the partial result:</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name FName="Ken" LName="S??nchez" />`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name FName="Terri" LName="Duffy" />`  
  
 `</Employee>`  
  
 `...`  
  
 <span data-ttu-id="18b9e-119">El primer `SELECT` especifica los nombres para las columnas del conjunto de filas resultante.</span><span class="sxs-lookup"><span data-stu-id="18b9e-119">The first `SELECT` specifies names for columns in the resulting rowset.</span></span> <span data-ttu-id="18b9e-120">Estos nombres forman dos grupos de columnas.</span><span class="sxs-lookup"><span data-stu-id="18b9e-120">These names form two column groups.</span></span> <span data-ttu-id="18b9e-121">El grupo con el valor `Tag` de `1` en el nombre de columna identifica `Employee` como elemento y `EmpID` como atributo.</span><span class="sxs-lookup"><span data-stu-id="18b9e-121">The group that has `Tag` value `1` in the column name identifies `Employee` as an element and `EmpID` as the attribute.</span></span> <span data-ttu-id="18b9e-122">El otro grupo de columnas tiene el valor `Tag` de `2` en la columna e identifica <`Name`> como elemento, y `FName` y `LName` como atributos.</span><span class="sxs-lookup"><span data-stu-id="18b9e-122">The other column group has `Tag` value `2` in the column and identifies <`Name`> as the element and `FName` and `LName` as the attributes.</span></span>  
  
 <span data-ttu-id="18b9e-123">La siguiente tabla muestra el conjunto de filas parcial generado por la consulta:</span><span class="sxs-lookup"><span data-stu-id="18b9e-123">The following table shows the partial rowset generated by the query:</span></span>  
  
 `Tag Parent  Employee!1!EmpID Name!2!FName Name!2!LName`  
  
 `--- ------  ---------------- ------------ ------------`  
  
 `1   NULL    1                NULL         NULL`  
  
 `2   1       1                Ken          S??nchez`  
  
 `1   NULL    2                NULL         NULL`  
  
 `2   1       2                Terri        Duffy`  
  
 `1   NULL    3                NULL         NULL`  
  
 `2   1       3                Roberto      Tamburello`  
  
 `...`  
  
 <span data-ttu-id="18b9e-124">Así es como se procesan las filas de la tabla universal para crear el árbol XML resultante:</span><span class="sxs-lookup"><span data-stu-id="18b9e-124">This is how the rows in the universal table are processed to produce the resulting XML tree:</span></span>  
  
 <span data-ttu-id="18b9e-125">La primera fila identifica el valor `Tag` en `1`.</span><span class="sxs-lookup"><span data-stu-id="18b9e-125">The first row identifies `Tag` value `1`.</span></span> <span data-ttu-id="18b9e-126">Por consiguiente, se identifica el grupo de columnas que tiene el valor `Tag` en `1` , `Employee!1!EmpID`.</span><span class="sxs-lookup"><span data-stu-id="18b9e-126">Therefore, the column group that has the `Tag` value `1` is identified, `Employee!1!EmpID`.</span></span> <span data-ttu-id="18b9e-127">Esta columna identifica `Employee` como nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="18b9e-127">This column identifies `Employee` as the element name.</span></span> <span data-ttu-id="18b9e-128">A continuación, se crea un elemento <`Employee`> que tenga atributos `EmpID`.</span><span class="sxs-lookup"><span data-stu-id="18b9e-128">An <`Employee`> element is then created that has `EmpID` attributes.</span></span> <span data-ttu-id="18b9e-129">Los valores de columna correspondientes se asignan a estos atributos.</span><span class="sxs-lookup"><span data-stu-id="18b9e-129">Corresponding column values are assigned to these attributes.</span></span>  
  
 <span data-ttu-id="18b9e-130">La segunda fila tiene en `Tag` en valor `2`.</span><span class="sxs-lookup"><span data-stu-id="18b9e-130">The second row has the `Tag` value `2`.</span></span> <span data-ttu-id="18b9e-131">Por consiguiente, el grupo de columnas que tiene el valor `Tag` en `2` en el nombre de columna, `Name!2!FName`, se identifica: `Name!2!LName`.</span><span class="sxs-lookup"><span data-stu-id="18b9e-131">Therefore, the column group that has the `Tag` value `2` in the column name, `Name!2!FName`, `Name!2!LName`, is identified.</span></span> <span data-ttu-id="18b9e-132">Estos nombres de columna identifican `Name` como nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="18b9e-132">These column names identify `Name` as element name.</span></span> <span data-ttu-id="18b9e-133">Se crea un elemento <`Name`> con atributos `FName` y `LName`.</span><span class="sxs-lookup"><span data-stu-id="18b9e-133">A <`Name`> element is created that has `FName` and `LName` attributes.</span></span> <span data-ttu-id="18b9e-134">A continuación, se asignan los valores de columna correspondientes a estos atributos.</span><span class="sxs-lookup"><span data-stu-id="18b9e-134">Corresponding column values are then assigned to these attributes.</span></span> <span data-ttu-id="18b9e-135">Esta fila identifica `1` como `Parent`.</span><span class="sxs-lookup"><span data-stu-id="18b9e-135">This row identifies `1` as `Parent`.</span></span> <span data-ttu-id="18b9e-136">Este elemento secundario se agrega al elemento <`Employee`> anterior.</span><span class="sxs-lookup"><span data-stu-id="18b9e-136">This element child is added to the previous <`Employee`> element.</span></span>  
  
 <span data-ttu-id="18b9e-137">Este proceso se repite con el resto de filas del conjunto.</span><span class="sxs-lookup"><span data-stu-id="18b9e-137">This process is repeated for rest of the rows in the rowset.</span></span> <span data-ttu-id="18b9e-138">Observe la importancia de ordenar las filas de la tabla universal para que FOR XML EXPLICIT pueda procesar el conjunto de filas por orden y generar el XML deseado.</span><span class="sxs-lookup"><span data-stu-id="18b9e-138">Note the importance of ordering the rows in the universal table so that FOR XML EXPLICIT can process the rowset in order and generate the XML you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b9e-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18b9e-139">See Also</span></span>  
 [<span data-ttu-id="18b9e-140">Usar el modo EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="18b9e-140">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
