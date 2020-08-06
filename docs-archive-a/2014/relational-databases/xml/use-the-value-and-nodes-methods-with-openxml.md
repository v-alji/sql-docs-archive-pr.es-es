---
title: Usar los métodos value() y nodes() con OPENXML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- OpenXML method [XML in SQL Server]
- value method [XML in SQL Server]
- nodes method [XML in SQL Server]
ms.assetid: c73dbe55-d685-42eb-b0ee-9f3c5b9d97f3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5dccf5a7ef626d1f1a42d011d22ba77807b34eba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748673"
---
# <a name="use-the-value-and-nodes-methods-with-openxml"></a><span data-ttu-id="e3ba5-102">Utilizar los métodos de valor() y nodos() con OPENXML</span><span class="sxs-lookup"><span data-stu-id="e3ba5-102">Use the value() and nodes() Methods with OPENXML</span></span>
  <span data-ttu-id="e3ba5-103">Puede usar varios métodos **Value ()** en `xml` el tipo de datos de una cláusula **Select** para generar un conjunto de filas de valores extraídos.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-103">You can use multiple **value()** methods on `xml` data type in a **SELECT** clause to generate a rowset of extracted values.</span></span> <span data-ttu-id="e3ba5-104">El método **nodes()** da como resultado una referencia interna para cada nodo seleccionado, que se puede usar para hacer más consultas.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-104">The **nodes()** method yields an internal reference for each selected node that can be used for additional query.</span></span> <span data-ttu-id="e3ba5-105">La combinación de los métodos **nodes()** y **value()** puede ser más eficaz para generar el conjunto de filas cuando tiene varias columnas y, tal vez, cuando las expresiones de ruta de acceso empleadas en su generación son complejas.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-105">The combination of the **nodes()** and **value()** methods can be more efficient in generating the rowset when it has several columns and, perhaps, when the path expressions used in its generation are complex.</span></span>  
  
 <span data-ttu-id="e3ba5-106">El método **Nodes ()** produce instancias de un `xml` tipo de datos Especial, cada una de las cuales tiene su contexto establecido en un nodo seleccionado diferente.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-106">The **nodes()** method yields instances of a special `xml` data type, each of which has its context set to a different selected node.</span></span> <span data-ttu-id="e3ba5-107">Este tipo de instancia XML admite los métodos **query()** , **value()** , **nodes()** y **exist()** y se puede usar en agregaciones **count(\*)** .</span><span class="sxs-lookup"><span data-stu-id="e3ba5-107">This kind of XML instance supports **query()**, **value()**, **nodes()**, and **exist()** methods and can be used in **count(\*)** aggregations.</span></span> <span data-ttu-id="e3ba5-108">Otros usos generarían un error.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-108">All other uses cause an error.</span></span>  
  
## <a name="example-using-nodes"></a><span data-ttu-id="e3ba5-109">Ejemplo: Uso de nodes()</span><span class="sxs-lookup"><span data-stu-id="e3ba5-109">Example: Using nodes()</span></span>  
 <span data-ttu-id="e3ba5-110">Suponga que desea extraer el nombre y los apellidos de los autores cuyo nombre no sea "David".</span><span class="sxs-lookup"><span data-stu-id="e3ba5-110">Assume that you want to extract the first and last names of authors, and the first name is not "David".</span></span> <span data-ttu-id="e3ba5-111">Además, desea extraer esta información como un conjunto de filas que contiene dos columnas: FirstName y LastName.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-111">Additionally, you want to extract this information as a rowset that contains two columns, FirstName and LastName.</span></span> <span data-ttu-id="e3ba5-112">Con los métodos **nodes()** y **value()** puede lograrlo, como se indica aquí:</span><span class="sxs-lookup"><span data-stu-id="e3ba5-112">By using **nodes()** and **value()** methods, you can accomplish this as shown in the following:</span></span>  
  
```  
SELECT nref.value('(first-name/text())[1]', 'nvarchar(50)') FirstName,  
       nref.value('(last-name/text())[1]', 'nvarchar(50)') LastName  
FROM   T CROSS APPLY xCol.nodes('//author') AS R(nref)  
WHERE  nref.exist('first-name[. != "David"]') = 1  
```  
  
 <span data-ttu-id="e3ba5-113">En este ejemplo, `nodes('//author')` da como resultado un conjunto de filas de referencias a elementos `<author>` para cada instancia XML.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-113">In this example, `nodes('//author')` yields a rowset of references to `<author>` elements for each XML instance.</span></span> <span data-ttu-id="e3ba5-114">Los nombres y apellidos de los autores se obtienen evaluando los métodos **value()** relativos a esas referencias.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-114">The first and last names of authors are obtained by evaluating **value()** methods relative to those references.</span></span>  
  
 <span data-ttu-id="e3ba5-115">SQL Server 2000 permite generar un conjunto de filas a partir de una instancia XML con **OpenXml()** .</span><span class="sxs-lookup"><span data-stu-id="e3ba5-115">SQL Server 2000 provides the capability for generating a rowset from an XML instance by using **OpenXml()**.</span></span> <span data-ttu-id="e3ba5-116">Puede especificar el esquema relacional para el conjunto de filas y la manera en que se asignan los valores dentro de la instancia XML a columnas del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-116">You can specify the relational schema for the rowset and how values inside the XML instance map to columns in the rowset.</span></span>  
  
## <a name="example-using-openxml-on-the-xml-data-type"></a><span data-ttu-id="e3ba5-117">Ejemplo: Uso de OpenXml() en el tipo de datos XML</span><span class="sxs-lookup"><span data-stu-id="e3ba5-117">Example: Using OpenXml() on the xml Data Type</span></span>  
 <span data-ttu-id="e3ba5-118">La consulta se puede volver a escribir a partir del ejemplo anterior usando **OpenXml()** como se indica aquí.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-118">The query can be rewritten from the previous example by using **OpenXml()** as shown in the following.</span></span> <span data-ttu-id="e3ba5-119">Para ello, se crea un cursor que lee cada instancia XML en una variable XML y luego le aplica OpenXML:</span><span class="sxs-lookup"><span data-stu-id="e3ba5-119">This is done by creating a cursor that reads each XML instance into an XML variable and then applies OpenXML to it:</span></span>  
  
```  
DECLARE name_cursor CURSOR  
FOR  
   SELECT xCol   
   FROM   T  
OPEN name_cursor  
DECLARE @xmlVal XML  
DECLARE @idoc int  
FETCH NEXT FROM name_cursor INTO @xmlVal  
  
WHILE (@@FETCH_STATUS = 0)  
BEGIN  
   EXEC sp_xml_preparedocument @idoc OUTPUT, @xmlVal  
   SELECT   *  
   FROM   OPENXML (@idoc, '//author')  
          WITH (FirstName  varchar(50) 'first-name',  
                LastName   varchar(50) 'last-name') R  
   WHERE  R.FirstName != 'David'  
  
   EXEC sp_xml_removedocument @idoc  
   FETCH NEXT FROM name_cursor INTO @xmlVal  
END  
CLOSE name_cursor  
DEALLOCATE name_cursor   
```  
  
 <span data-ttu-id="e3ba5-120">**OpenXml()** crea una representación en la memoria y usa tablas de trabajo en lugar del procesador de consultas.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-120">**OpenXml()** creates an in-memory representation and uses work tables instead of the query processor.</span></span> <span data-ttu-id="e3ba5-121">Se basa en el procesador de XPath versión 1.0 de MSXML versión 3.0 en lugar del motor de XQuery.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-121">It relies on the XPath version 1.0 processor of MSXML version 3.0 instead of the XQuery engine.</span></span> <span data-ttu-id="e3ba5-122">Las tablas de trabajo no se comparten entre varias llamadas a **OpenXml()** , ni siquiera en la misma instancia XML.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-122">The work tables are not shared among multiple calls to **OpenXml()**, even on the same XML instance.</span></span> <span data-ttu-id="e3ba5-123">Esto limita su escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-123">This limits its scalability.</span></span> <span data-ttu-id="e3ba5-124">**OpenXml()** permite el acceso a un formato de tabla irregular para los datos XML cuando no se especifica la cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-124">**OpenXml()** allows you to access an edge table format for the XML data when the WITH clause is not specified.</span></span> <span data-ttu-id="e3ba5-125">Además, permite utilizar el valor XML restante en una columna de "desbordamiento" independiente.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-125">Also, it allows you to use the remaining XML value in a separate, "overflow" column.</span></span>  
  
 <span data-ttu-id="e3ba5-126">En la combinación de las funciones **nodes()** y **value()** se usan índices XML con eficacia.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-126">The combination of **nodes()** and **value()** functions uses XML indexes effectively.</span></span> <span data-ttu-id="e3ba5-127">Como resultado, esta combinación puede ofrecer una mayor escalabilidad que **OpenXml**.</span><span class="sxs-lookup"><span data-stu-id="e3ba5-127">As a result, this combination can exhibit more scalability than **OpenXml**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ba5-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3ba5-128">See Also</span></span>  
 [<span data-ttu-id="e3ba5-129">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e3ba5-129">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
