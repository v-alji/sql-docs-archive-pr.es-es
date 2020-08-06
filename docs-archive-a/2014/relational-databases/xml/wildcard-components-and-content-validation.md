---
title: Componentes comodín y validación del contenido | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- wildcard components [XML]
- content validation [XML]
ms.assetid: ffa7d974-3645-446c-8425-f0b22b6b060a
author: rothja
ms.author: jroth
ms.openlocfilehash: 76ff2b48efb8cff0b98827fe8522405682c294e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669546"
---
# <a name="wildcard-components-and-content-validation"></a><span data-ttu-id="1a8cc-102">Componentes comodín y validación del contenido</span><span class="sxs-lookup"><span data-stu-id="1a8cc-102">Wildcard Components and Content Validation</span></span>
  <span data-ttu-id="1a8cc-103">Los componentes comodín se utilizan para aumentar la flexibilidad en cuanto a lo que se permite que aparezca en un modelo de contenido.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-103">Wildcard components are used to increase flexibility in what is allowed to appear in a content model.</span></span> <span data-ttu-id="1a8cc-104">El lenguaje XSD admite estos componentes de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1a8cc-104">These components are supported in the XSD language in the following ways:</span></span>  
  
-   <span data-ttu-id="1a8cc-105">Componentes de carácter comodín de elementos.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-105">Element wildcard components.</span></span> <span data-ttu-id="1a8cc-106">Se representan mediante el elemento **\<xsd:any>** .</span><span class="sxs-lookup"><span data-stu-id="1a8cc-106">These are represented by the **\<xsd:any>** element.</span></span>  
  
-   <span data-ttu-id="1a8cc-107">Componentes de carácter comodín de atributos.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-107">Attribute wildcard components.</span></span> <span data-ttu-id="1a8cc-108">Se representan mediante el elemento **\<xsd:anyAttribute>** .</span><span class="sxs-lookup"><span data-stu-id="1a8cc-108">These are represented by the **\<xsd:anyAttribute>** element.</span></span>  
  
 <span data-ttu-id="1a8cc-109">Los dos elementos de carácter comodín ( **\<xsd:any>** y **\<xsd:anyAttribute>** ) admiten el uso de un atributo **processContents**.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-109">Both wildcard character elements, **\<xsd:any>** and **\<xsd:anyAttribute>**, support the use of a **processContents** attribute.</span></span> <span data-ttu-id="1a8cc-110">Esto permite especificar un valor que indica el modo en que las aplicaciones XML controlan la validación del contenido de los documentos asociado a estos elementos de caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-110">This lets you specify a value that indicates how XML applications handle the validation of document content associated with these wildcard character elements.</span></span> <span data-ttu-id="1a8cc-111">A continuación se exponen los distintos valores y su efecto:</span><span class="sxs-lookup"><span data-stu-id="1a8cc-111">These are the different values and their effect:</span></span>  
  
-   <span data-ttu-id="1a8cc-112">El valor **strict** especifica que se valida totalmente el contenido.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-112">The **strict** value specifies that the contents are fully validated.</span></span>  
  
-   <span data-ttu-id="1a8cc-113">El valor **skip** especifica que no se valida totalmente el contenido</span><span class="sxs-lookup"><span data-stu-id="1a8cc-113">The **skip** value specifies that the contents are not validated.</span></span>  
  
-   <span data-ttu-id="1a8cc-114">El valor **lax** especifica que solo se validan los elementos y atributos para los que hay disponibles definiciones de esquema.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-114">The **lax** value specifies that only elements and attributes for which schema definitions are available are validated.</span></span>  
  
## <a name="lax-validation-and-xsanytype-elements"></a><span data-ttu-id="1a8cc-115">La validación lax y los elementos xs:anyType</span><span class="sxs-lookup"><span data-stu-id="1a8cc-115">Lax Validation and xs:anyType Elements</span></span>  
 <span data-ttu-id="1a8cc-116">La especificación de esquemas XML utiliza la validación **lax** para los elementos del tipo **anyType** .</span><span class="sxs-lookup"><span data-stu-id="1a8cc-116">The XML Schema specification uses **lax** validation for elements of the **anyType** type.</span></span> <span data-ttu-id="1a8cc-117">Puesto que [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] no admitía la validación lax, se aplicaba la validación estricta a los elementos **anyType**.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-117">Because [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] did not support lax validation, strict validation was applied for elements of the **anyType**.</span></span> <span data-ttu-id="1a8cc-118">A partir de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], se admite la validación lax.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-118">Beginning with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], lax validation is supported.</span></span> <span data-ttu-id="1a8cc-119">El contenido de los elementos de tipo **anyType** se validará utilizando la validación lax.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-119">Content of elements of type **anyType** will be validated using lax validation.</span></span>  
  
 <span data-ttu-id="1a8cc-120">En el ejemplo siguiente se ilustra la validación lax:</span><span class="sxs-lookup"><span data-stu-id="1a8cc-120">The following example illustrates the lax validation.</span></span> <span data-ttu-id="1a8cc-121">el elemento de esquema `e` es de tipo **anyType** .</span><span class="sxs-lookup"><span data-stu-id="1a8cc-121">The schema element `e` is of the **anyType** type.</span></span> <span data-ttu-id="1a8cc-122">El ejemplo crea variables **xml** con tipo e ilustra la validación lax del elemento de tipo **anyType** .</span><span class="sxs-lookup"><span data-stu-id="1a8cc-122">The example creates typed **xml** variables and illustrates the lax validation of the element of the **anyType** type.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="http://ns">  
   <element name="e" type="anyType"/>  
   <element name="a" type="byte"/>  
   <element name="b" type="string"/>  
 </schema>'  
GO  
```  
  
 <span data-ttu-id="1a8cc-123">El ejemplo siguiente funciona correctamente porque la validación de `<e>` es correcta:</span><span class="sxs-lookup"><span data-stu-id="1a8cc-123">The following example succeeds, because the validation of `<e>` is successful:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="1a8cc-124">El ejemplo siguiente funciona correctamente:</span><span class="sxs-lookup"><span data-stu-id="1a8cc-124">The following example succeeds.</span></span> <span data-ttu-id="1a8cc-125">se acepta la instancia, aunque no se haya definido ningún elemento `<c>` en el esquema:</span><span class="sxs-lookup"><span data-stu-id="1a8cc-125">The instance is accepted, even though no element `<c>` is defined in the schema:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><c>Wrong</c><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="1a8cc-126">La instancia XML del ejemplo siguiente se rechaza, porque la definición del elemento `<a>` no permite un valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="1a8cc-126">The XML instance in the following example is rejected, because the definition of the `<a>` element does not allow a string value.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>Wrong</a><b>data</b></e>'  
SELECT @var  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a8cc-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1a8cc-127">See Also</span></span>  
 [<span data-ttu-id="1a8cc-128">Requisitos y limitaciones de las colecciones de esquemas XML en el servidor</span><span class="sxs-lookup"><span data-stu-id="1a8cc-128">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
