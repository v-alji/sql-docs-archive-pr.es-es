---
title: Comparación de la consulta FOR XML con la consulta FOR XML anidada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], comparing query types
ms.assetid: 19225b4a-ee3f-47cf-8bcc-52699eeda32c
author: rothja
ms.author: jroth
ms.openlocfilehash: ca10060702d0c7e50f2be79310c55e177dca358d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751998"
---
# <a name="for-xml-query-compared-to-nested-for-xml-query"></a><span data-ttu-id="34a14-102">Comparación de la consulta FOR XML con la consulta FOR XML anidada</span><span class="sxs-lookup"><span data-stu-id="34a14-102">FOR XML Query Compared to Nested FOR XML Query</span></span>
  <span data-ttu-id="34a14-103">En este tema se compara una consulta FOR XML de nivel único con una consulta FOR XML anidada.</span><span class="sxs-lookup"><span data-stu-id="34a14-103">This topic compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="34a14-104">Una de las ventajas de usar consultas FOR XML anidadas es que puede especificar una combinación de XML centrado en atributos y un XML centrado en elementos para los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="34a14-104">One of the benefits of using nested FOR XML queries is that you can specify a combination of attribute-centric and element-centric XML for query results.</span></span> <span data-ttu-id="34a14-105">En este ejemplo se demuestra.</span><span class="sxs-lookup"><span data-stu-id="34a14-105">The example demonstrates this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34a14-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34a14-106">Example</span></span>  
 <span data-ttu-id="34a14-107">La siguiente consulta `SELECT` recupera información de categoría y subcategoría de productos de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34a14-107">The following `SELECT` query retrieves product category and subcategory information in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="34a14-108">No hay FOR XML anidado en la consulta.</span><span class="sxs-lookup"><span data-stu-id="34a14-108">There is no nested FOR XML in the query.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   ProductCategory.ProductCategoryID,   
         ProductCategory.Name as CategoryName,  
         ProductSubCategory.ProductSubCategoryID,   
         ProductSubCategory.Name  
FROM     Production.ProductCategory, Production.ProductSubCategory  
WHERE    ProductCategory.ProductCategoryID = ProductSubCategory.ProductCategoryID  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
GO  
```  
  
 <span data-ttu-id="34a14-109">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="34a14-109">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory ProductSubCategoryID="1" Name="Mountain Bike"/>  
  <ProductSubCategory ProductSubCategoryID="2" Name="Road Bike"/>  
  <ProductSubCategory ProductSubCategoryID="3" Name="Touring Bike"/>  
</ProductCategory>  
...  
```  
  
 <span data-ttu-id="34a14-110">Si especifica la directiva `ELEMENTS` en la consulta, recibirá un resultado centrado en elementos, como se muestra en el siguiente fragmento de resultados:</span><span class="sxs-lookup"><span data-stu-id="34a14-110">If you specify the `ELEMENTS` directive in the query, you receive an element-centric result, as shown in the following result fragment:</span></span>  
  
```  
<ProductCategory>  
  <ProductCategoryID>1</ProductCategoryID>  
  <CategoryName>Bike</CategoryName>  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <Name>Mountain Bike</Name>  
  </ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  </ProductSubCategory>  
</ProductCategory>  
```  
  
 <span data-ttu-id="34a14-111">A continuación, imagine que desea generar una jerarquía XML que sea una combinación de XML centrado en atributos y centrado en elementos, como se muestra en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="34a14-111">Next, assume that you want to generate an XML hierarchy that is a combination of attribute-centric and element-centric XML, as shown in the following fragment:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="34a14-112">En el fragmento anterior, la información de categoría de productos, como el Id. y el nombre de categoría, son atributos.</span><span class="sxs-lookup"><span data-stu-id="34a14-112">In the previous fragment, product category information such as category ID and category name are attributes.</span></span> <span data-ttu-id="34a14-113">Sin embargo, la información de subcategoría está centrada en elementos.</span><span class="sxs-lookup"><span data-stu-id="34a14-113">However, the subcategory information is element-centric.</span></span> <span data-ttu-id="34a14-114">Para construir el elemento <`ProductCategory`>, puede escribir una consulta `FOR XML` como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="34a14-114">To construct the <`ProductCategory`> element, you can write a `FOR XML` query as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName  
FROM Production.ProductCategory ProdCat  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="34a14-115">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="34a14-115">This is the result:</span></span>  
  
```  
< ProdCat ProductCategoryID="1" CategoryName="Bikes" />  
< ProdCat ProductCategoryID="2" CategoryName="Components" />  
< ProdCat ProductCategoryID="3" CategoryName="Clothing" />  
< ProdCat ProductCategoryID="4" CategoryName="Accessories" />  
```  
  
 <span data-ttu-id="34a14-116">Para construir los elementos <`ProductSubCategory`> anidados en el XML que desee, debe agregar una consulta `FOR XML` anidada, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="34a14-116">To construct the nested <`ProductSubCategory`> elements in the XML you want, you then add a nested `FOR XML` query, as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName  
        FROM   Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="34a14-117">Observe lo siguiente en la consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="34a14-117">Note the following in the previous query:</span></span>  
  
-   <span data-ttu-id="34a14-118">La consulta `FOR XML` interna recupera información de subcategoría de productos.</span><span class="sxs-lookup"><span data-stu-id="34a14-118">The inner `FOR XML` query retrieves product subcategory information.</span></span> <span data-ttu-id="34a14-119">La directiva `ELEMENTS` se agrega a la consulta `FOR XML` interna para generar el XML centrado en elementos que se agrega al XML generado por la consulta externa.</span><span class="sxs-lookup"><span data-stu-id="34a14-119">The `ELEMENTS` directive is added in the inner `FOR XML` to generate element-centric XML that is added to the XML generated by the outer query.</span></span> <span data-ttu-id="34a14-120">De manera predeterminada, la consulta externa genera XML centrado en atributos.</span><span class="sxs-lookup"><span data-stu-id="34a14-120">By default, the outer query generates attribute-centric XML.</span></span>  
  
-   <span data-ttu-id="34a14-121">En la consulta interna, se especifica la directiva `TYPE` para que el resultado sea de tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="34a14-121">In the inner query, the `TYPE` directive is specified so the result is of **xml** type.</span></span> <span data-ttu-id="34a14-122">Si no se especifica `TYPE`, el resultado se devuelve como tipo `nvarchar(max)` y los datos XML se devuelven como entidades.</span><span class="sxs-lookup"><span data-stu-id="34a14-122">If `TYPE` is not specified, the result is returned as `nvarchar(max)` type and the XML data is returned as entities.</span></span>  
  
-   <span data-ttu-id="34a14-123">La consulta externa especifica también la directiva `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="34a14-123">The outer query also specifies the `TYPE` directive.</span></span> <span data-ttu-id="34a14-124">Por tanto, el resultado de esta consulta se devuelve al cliente como tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="34a14-124">Therefore, the result of this query is returned to the client as **xml** type.</span></span>  
  
 <span data-ttu-id="34a14-125">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="34a14-125">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="34a14-126">La consulta siguiente es solo una extensión de la anterior.</span><span class="sxs-lookup"><span data-stu-id="34a14-126">The following query is just an extension of the previous query.</span></span> <span data-ttu-id="34a14-127">Muestra la jerarquía de productos completa de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34a14-127">It shows the full product hierarchy in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="34a14-128">Incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="34a14-128">This includes the following:</span></span>  
  
-   <span data-ttu-id="34a14-129">Categorías de productos</span><span class="sxs-lookup"><span data-stu-id="34a14-129">Product categories</span></span>  
  
-   <span data-ttu-id="34a14-130">Subcategorías de productos de cada categoría</span><span class="sxs-lookup"><span data-stu-id="34a14-130">Product subcategories in each category</span></span>  
  
-   <span data-ttu-id="34a14-131">Modelos de productos en cada subcategoría</span><span class="sxs-lookup"><span data-stu-id="34a14-131">Product models in each subcategory</span></span>  
  
-   <span data-ttu-id="34a14-132">Productos en cada modelo</span><span class="sxs-lookup"><span data-stu-id="34a14-132">Products in each model</span></span>  
  
 <span data-ttu-id="34a14-133">Quizá encuentre útil la siguiente consulta para comprender la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="34a14-133">You might find the following query useful in understanding the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName,  
               (SELECT ProductModel.ProductModelID,   
                       ProductModel.Name as ModelName,  
                       (SELECT ProductID, Name as ProductName, Color  
                        FROM   Production.Product  
                        WHERE  Product.ProductModelID =   
                               ProductModel.ProductModelID  
                        FOR XML AUTO, TYPE)  
                FROM   (SELECT distinct ProductModel.ProductModelID,   
                               ProductModel.Name  
                        FROM   Production.ProductModel,   
                               Production.Product  
                        WHERE  ProductModel.ProductModelID =   
                               Product.ProductModelID  
                        AND    Product.ProductSubCategoryID =   
                               ProductSubCategory.ProductSubCategoryID)   
                                  ProductModel  
                FOR XML AUTO, type  
               )  
        FROM Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="34a14-134">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="34a14-134">This is the partial result:</span></span>  
  
```  
<Production.ProductCategory ProductCategoryID="1" CategoryName="Bikes">  
  <Production.ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bikes</SubCategoryName>  
    <ProductModel ProductModelID="19" ModelName="Mountain-100">  
      <Production.Product ProductID="771"   
                ProductName="Mountain-100 Silver, 38" Color="Silver" />  
      <Production.Product ProductID="772"   
                ProductName="Mountain-100 Silver, 42" Color="Silver" />  
      <Production.Product ProductID="773"   
                ProductName="Mountain-100 Silver, 44" Color="Silver" />  
        ...  
    </ProductModel>  
     ...  
```  
  
 <span data-ttu-id="34a14-135">Si quita la directiva `ELEMENTS` de la consulta `FOR XML` anidada que genera subcategorías de productos, todo el resultado está centrado en atributos.</span><span class="sxs-lookup"><span data-stu-id="34a14-135">If you remove the `ELEMENTS` directive from the nested `FOR XML` query that generates product subcategories, the whole result is attribute-centric.</span></span> <span data-ttu-id="34a14-136">Después puede escribir esta consulta sin anidar.</span><span class="sxs-lookup"><span data-stu-id="34a14-136">You can then write this query without nesting.</span></span> <span data-ttu-id="34a14-137">La adición de `ELEMENTS` da lugar a un XML parcialmente centrado en atributos y parcialmente centrado en elementos.</span><span class="sxs-lookup"><span data-stu-id="34a14-137">The addition of `ELEMENTS` results in an XML that is partly attribute-centric and partly element-centric.</span></span> <span data-ttu-id="34a14-138">Este resultado no se puede generar en un solo nivel, consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="34a14-138">This result cannot be generated by a single-level, FOR XML query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a14-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34a14-139">See Also</span></span>  
 [<span data-ttu-id="34a14-140">Usar consultas FOR XML anidadas</span><span class="sxs-lookup"><span data-stu-id="34a14-140">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
