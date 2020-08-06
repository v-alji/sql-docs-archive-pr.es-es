---
title: 'Ejemplo: Especificación de la directiva XMLTEXT | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XMLTEXT directive
ms.assetid: e78008ec-51e8-4fd1-b86f-1058a781de17
author: rothja
ms.author: jroth
ms.openlocfilehash: d14299ad3e989c6600434b857a650fbbddd7a590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676381"
---
# <a name="example-specifying-the-xmltext-directive"></a><span data-ttu-id="1152f-102">Ejemplo: Especificación de la directiva XMLTEXT</span><span class="sxs-lookup"><span data-stu-id="1152f-102">Example: Specifying the XMLTEXT Directive</span></span>
  <span data-ttu-id="1152f-103">En este ejemplo se muestra cómo se tratan los datos de la columna de desbordamiento mediante la directiva `XMLTEXT` en una instrucción `SELECT` con el modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="1152f-103">This example illustrates how data in the overflow column is addressed by using the `XMLTEXT` directive in a `SELECT` statement using EXPLICIT mode.</span></span>  
  
 <span data-ttu-id="1152f-104">Considere la tabla `Person` .</span><span class="sxs-lookup"><span data-stu-id="1152f-104">Consider the `Person` table.</span></span> <span data-ttu-id="1152f-105">Esta tabla dispone de una columna `Overflow` que almacena la parte no utilizada del documento XML.</span><span class="sxs-lookup"><span data-stu-id="1152f-105">This table has an `Overflow` column that stores the unconsumed part of the XML document.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE TABLE Person(PersonID varchar(5), PersonName varchar(20), Overflow nvarchar(200));  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
   ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P">content</SomeTag>');  
```  
  
 <span data-ttu-id="1152f-106">Esta consulta recupera columnas de la tabla `Person` .</span><span class="sxs-lookup"><span data-stu-id="1152f-106">This query retrieves columns from the `Person` table.</span></span> <span data-ttu-id="1152f-107">En la columna `Overflow` no se especifica *AttributeName* , sino que *directive* se establece en `XMLTEXT` como parte del proceso destinado a proporcionar un nombre de columna de la tabla universal.</span><span class="sxs-lookup"><span data-stu-id="1152f-107">For the `Overflow` column, *AttributeName* is not specified, but *directive* is set to `XMLTEXT` as part of providing a universal table column name.</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEST] -- No AttributeName; XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="1152f-108">En el documento XML resultante:</span><span class="sxs-lookup"><span data-stu-id="1152f-108">In the resulting XML document:</span></span>  
  
-   <span data-ttu-id="1152f-109">Puesto que no se especifica *AttributeName* para la columna `Overflow` y se especifica la directiva `xmltext`, los atributos del elemento <`overflow`> se anexan a la lista de atributos del elemento <`Parent`> que los incluye.</span><span class="sxs-lookup"><span data-stu-id="1152f-109">Because *AttributeName* is not specified for the `Overflow` column and the `xmltext` directive is specified, the attributes in the <`overflow`> element are appended to the attribute list of the enclosing <`Parent`> element.</span></span>  
  
-   <span data-ttu-id="1152f-110">Dado que el atributo `PersonID` del elemento <`xmltext`> está en conflicto con el atributo `PersonID` recuperado en el mismo nivel de elementos, se omite el atributo del elemento <`xmltext`>, incluso aunque `PersonID` sea NULL.</span><span class="sxs-lookup"><span data-stu-id="1152f-110">Because the `PersonID`attribute in the <`xmltext`> element conflicts with the `PersonID` attribute retrieved on the same element level, the attribute in the <`xmltext`> element is ignored, even if `PersonID` is NULL.</span></span> <span data-ttu-id="1152f-111">En general, un atributo invalida un atributo del mismo nombre en el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="1152f-111">Generally, an attribute overrides an attribute of the same name in the overflow.</span></span>  
  
 <span data-ttu-id="1152f-112">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1152f-112">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">content</Parent>`  
  
 <span data-ttu-id="1152f-113">Si los datos de desbordamiento contienen subelementos y se especifica la misma consulta, se agregan los subelementos en la columna `Overflow` como subelementos del elemento <`Parent`> que los incluye.</span><span class="sxs-lookup"><span data-stu-id="1152f-113">If the overflow data has subelements and the same query is specified, the subelements in the `Overflow` column are added as the subelements of the enclosing <`Parent`> element.</span></span>  
  
 <span data-ttu-id="1152f-114">Por ejemplo, puede cambiar los datos de la tabla `Person` para que la columna `Overflow` disponga ahora de subelementos.</span><span class="sxs-lookup"><span data-stu-id="1152f-114">For example, change the data in the `Person` table so that the `Overflow` column now has subelements.</span></span>  
  
```  
USE tempdb;  
GO  
TRUNCATE TABLE Person;  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
    ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P"><name>PersonName</name></SomeTag>');  
```  
  
 <span data-ttu-id="1152f-115">Si se ejecuta la misma consulta, se agregan los subelementos del elemento <`xmltext`> como subelementos del elemento <`Parent`> que los incluye.</span><span class="sxs-lookup"><span data-stu-id="1152f-115">If the same query is executed, the subelements in the <`xmltext`> element are added as subelements of the enclosing <`Parent`> element:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEXT] -- no AttributeName, XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="1152f-116">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1152f-116">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `</Parent>`  
  
 <span data-ttu-id="1152f-117">Si se especifica *AttributeName* con la directiva `xmltext`, se agregan los atributos del elemento <`overflow`> como atributos de los subelementos del elemento <`Parent`> que los incluye.</span><span class="sxs-lookup"><span data-stu-id="1152f-117">If *AttributeName* is specified with the `xmltext` directive, the attributes of the <`overflow`> element are added as attributes of the subelements of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="1152f-118">El nombre especificado para *attributeName* se convierte en el nombre del subelemento.</span><span class="sxs-lookup"><span data-stu-id="1152f-118">The name specified for *AttributeName* becomes the name of the subelement.</span></span>  
  
 <span data-ttu-id="1152f-119">En esta consulta, se especifica *attributeName*, <`overflow`>, junto con la `xmltext` Directiva:</span><span class="sxs-lookup"><span data-stu-id="1152f-119">In this query, *AttributeName*, <`overflow`>, is specified together with the `xmltext` directive:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!overflow!XMLTEXT] -- Overflow is AttributeName  
                      -- XMLTEXT is a directive  
FROM Person  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="1152f-120">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1152f-120">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe">`  
  
 `<overflow attr1="data">content</overflow>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe">`  
  
 `<overflow attr2="data" />`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe">`  
  
 `<overflow attr3="data" PersonID="P">`  
  
 `<name>PersonName</name>`  
  
 `</overflow>`  
  
 `</Parent>`  
  
 <span data-ttu-id="1152f-121">En este elemento de consulta, se especifica *directive* para el atributo `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="1152f-121">In this query element, *directive* is specified for `PersonName` attribute.</span></span> <span data-ttu-id="1152f-122">De este modo, `PersonName` se agrega como subelemento del elemento <`Parent`> que lo incluye.</span><span class="sxs-lookup"><span data-stu-id="1152f-122">This results in `PersonName` being added as a subelement of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="1152f-123">Los atributos de <`xmltext`> se siguen agregando al elemento <`Parent`> que lo incluye.</span><span class="sxs-lookup"><span data-stu-id="1152f-123">The attributes of the <`xmltext`> are still appended to the enclosing <`Parent`> element.</span></span> <span data-ttu-id="1152f-124">El contenido del elemento <`overflow`> (los subelementos) se antepone a otros subelementos de los elementos <`Parent`> que lo incluyen.</span><span class="sxs-lookup"><span data-stu-id="1152f-124">The contents of the <`overflow`> element, subelements, are prepended to the other subelements of the enclosing <`Parent`> elements.</span></span>  
  
```  
SELECT 1      AS Tag, NULL as parent,  
       PersonID   AS [Parent!1!PersonID],  
       PersonName AS [Parent!1!PersonName!element], -- element directive  
       Overflow   AS [Parent!1!!XMLTEXT]  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="1152f-125">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1152f-125">This is the result:</span></span>  
  
 `<Parent PersonID="P1" attr1="data">content<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" attr2="data">`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 <span data-ttu-id="1152f-126">Si la columna de datos `XMLTEXT` contiene atributos en el elemento raíz, estos atributos no se muestran en el esquema de datos XML y el analizador de MSXML no valida el fragmento del documento XML resultante.</span><span class="sxs-lookup"><span data-stu-id="1152f-126">If the `XMLTEXT` column data contains attributes on the root element, these attributes are not shown in the XML data schema and the MSXML parser does not validate the resulting XML document fragment.</span></span> <span data-ttu-id="1152f-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1152f-127">For example:</span></span>  
  
```  
SELECT 1 AS Tag,  
       0 ASParent,  
       N'<overflow a="1"/>' AS 'overflow!1!!xmltext'  
FOR XML EXPLICIT, xmldata;  
```  
  
 <span data-ttu-id="1152f-128">Éste es el resultado.</span><span class="sxs-lookup"><span data-stu-id="1152f-128">This is the result.</span></span> <span data-ttu-id="1152f-129">Observe que el atributo de desbordamiento `a` no aparece en el esquema devuelto:</span><span class="sxs-lookup"><span data-stu-id="1152f-129">Note that in the returned schema, the overflow attribute `a` is missing from the schema:</span></span>  
  
 `<Schema name="Schema2"`  
  
 `xmlns="urn:schemas-microsoft-com:xml-data"`  
  
 `xmlns:dt="urn:schemas-microsoft-com:datatypes">`  
  
 `<ElementType name="overflow" content="mixed" model="open">`  
  
 `</ElementType>`  
  
 `</Schema>`  
  
 `<overflow xmlns="x-schema:#Schema2" a="1">`  
  
 `</overflow>`  
  
## <a name="see-also"></a><span data-ttu-id="1152f-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1152f-130">See Also</span></span>  
 [<span data-ttu-id="1152f-131">Usar el modo EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="1152f-131">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
