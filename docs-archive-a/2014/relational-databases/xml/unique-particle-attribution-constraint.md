---
title: Restricción de atribución de partículas exclusivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
f1_keywords:
- unique particle attribution
helpviewer_keywords:
- schema collections [SQL Server], unique particle attribution
- XML schema collections [SQL Server], unique particle attribution
- UPA constraint rule
- unique particle attribution constraint rule
ms.assetid: 6bb879e9-a5ee-402e-94e4-fe8cec5966b0
author: rothja
ms.author: jroth
ms.openlocfilehash: 7416aa4ea14539f3bf633207768783aa439ec818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744007"
---
# <a name="unique-particle-attribution-constraint"></a><span data-ttu-id="6d624-102">Restricción de atribución de partículas exclusivas</span><span class="sxs-lookup"><span data-stu-id="6d624-102">Unique Particle Attribution Constraint</span></span>
  <span data-ttu-id="6d624-103">En XSD, los modelos de contenido complejos están restringidos por la regla de restricción de atribución de partículas exclusivas (UPA).</span><span class="sxs-lookup"><span data-stu-id="6d624-103">In XSD, complex content models are constrained by the unique particle attribution (UPA) constraint rule.</span></span> <span data-ttu-id="6d624-104">Esta regla requiere que cada elemento de un documento de una instancia se corresponda sin ambigüedades exactamente con una partícula `<xsd:element>` o `<xsd:any>` en el modelo de contenido de su elemento principal.</span><span class="sxs-lookup"><span data-stu-id="6d624-104">This rule requires that each element in an instance document correspond unambiguously to exactly one `<xsd:element>` or `<xsd:any>` particle in its parent's content model.</span></span> <span data-ttu-id="6d624-105">Cualquier esquema que contenga un tipo con un modelo de contenido potencialmente ambiguo se rechaza.</span><span class="sxs-lookup"><span data-stu-id="6d624-105">Any schema that contains a type with a potentially ambiguous content model is rejected.</span></span>  
  
 <span data-ttu-id="6d624-106">Las causas más comunes de ambigüedad son los caracteres comodín `<xsd:any>` y las partículas con intervalos de repetición variables, como minOccurs < maxOccurs.</span><span class="sxs-lookup"><span data-stu-id="6d624-106">The most common causes of ambiguity are `<xsd:any>` wildcard characters and particles that have variable occurrence ranges, such as minOccurs < maxOccurs.</span></span> <span data-ttu-id="6d624-107">Por ejemplo, el siguiente modelo de contenido es ambiguo, porque un elemento <`e1`> puede corresponderse con el elemento `<xsd:element>` o el elemento `<xsd:any>`.</span><span class="sxs-lookup"><span data-stu-id="6d624-107">For example, the following content model is ambiguous, because an <`e1`> element could match either the `<xsd:element>` or the `<xsd:any>` element.</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:choice>  
            <xsd:element name="e1"/>  
            <xsd:any namespace="##any"/>  
        </xsd:choice>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="6d624-108">El siguiente modelo de contenido también es ambiguo:</span><span class="sxs-lookup"><span data-stu-id="6d624-108">The following content model is also ambiguous:</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:sequence>  
            <xsd:element name="e1" maxOccurs="2"/>  
            <xsd:element name="e2" minOccurs="0"/>  
            <xsd:element name="e1"/>  
        </xsd:sequence>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="6d624-109">Aunque un documento como `<root><e1/><e2/><e1/></root>` se puede validar sin ambigüedades, este no es el caso de otro documento como `<root><e1/><e1/></root>` , ya que no está claro a qué `<xsd:element>` corresponde el segundo `<e1/>` .</span><span class="sxs-lookup"><span data-stu-id="6d624-109">Although a document such as `<root><e1/><e2/><e1/></root>` can be validated unambiguously, a document such as `<root><e1/><e1/></root>` cannot, because it is not clear to which `<xsd:element>` the second `<e1/>` corresponds.</span></span> <span data-ttu-id="6d624-110">Aunque algunos documentos se pueden validar sin ambigüedades, el esquema se rechazará debido a la posible ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="6d624-110">Even though some documents can be validated unambiguously, the schema will be rejected, because of the potential for ambiguity.</span></span>  
  
 <span data-ttu-id="6d624-111">Tenga en cuenta que, para que un modelo de contenido sea válido, debe ser posible validar cualquier instancia sin ambigüedades sin mirar hacia delante.</span><span class="sxs-lookup"><span data-stu-id="6d624-111">Note that for a content model to be valid, it must be possible to validate any instance unambiguously without looking ahead.</span></span> <span data-ttu-id="6d624-112">Considere, por ejemplo, el siguiente modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="6d624-112">For example, consider the following content model:</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:choice>  
           <xsd:sequence>  
               <xsd:element name="e1"/>  
               <xsd:element name="e2"/>  
           </xsd:sequence>  
           <xsd:sequence>  
               <xsd:element name="e1"/>  
               <xsd:element name="e3"/>  
           </xsd:sequence>  
       </xsd:choice>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="6d624-113">Para un documento como `<root><e1/><e3/></root>`, la secuencia `<e1/><e3/>` se corresponde sin ambigüedades con el segundo `<xsd:sequence>`.</span><span class="sxs-lookup"><span data-stu-id="6d624-113">For a document such as `<root><e1/><e3/></root>`, the sequence `<e1/><e3/>` unambiguously matches the second `<xsd:sequence>`.</span></span> <span data-ttu-id="6d624-114">Sin embargo, dado que el `<xsd:element>` al que corresponde `<e1/>` no se puede determinar sin mirar hacia delante a `<e3/>`, el modelo de contenido infringe la regla de restricción UPA.</span><span class="sxs-lookup"><span data-stu-id="6d624-114">However, because the `<xsd:element>` to which `<e1/>` corresponds cannot be determined without looking ahead to `<e3/>`, the content model violates the UPA constraint rule.</span></span>  
  
## <a name="finding-more-information"></a><span data-ttu-id="6d624-115">Buscar más información</span><span class="sxs-lookup"><span data-stu-id="6d624-115">Finding More Information</span></span>  
 <span data-ttu-id="6d624-116">El World Wide Web Consortium (W3C) publica el siguiente documento, que contiene la descripción técnica de la restricción de atribución de partículas exclusivas:</span><span class="sxs-lookup"><span data-stu-id="6d624-116">The following document is published by the World Wide Web Consortium (W3C) and contains the technical description of the unique particle attribution constraint:</span></span>  
  
 <span data-ttu-id="6d624-117">"XML Schema Part 1: Segunda edición de estructuras, recomendación editada propuesta por la W3C":</span><span class="sxs-lookup"><span data-stu-id="6d624-117">"XML Schema Part 1: Structures Second Edition, W3C Proposed Edited Recommendation":</span></span>  
  
-   <span data-ttu-id="6d624-118">Sección 3.8.6: Restricciones en los componentes del esquema de grupo de modelos</span><span class="sxs-lookup"><span data-stu-id="6d624-118">Section 3.8.6: Constraints on Model Group Schema Components</span></span>  
  
-   <span data-ttu-id="6d624-119">Apéndice H: Análisis de la restricción de la atribución de partículas únicas (no normativa)</span><span class="sxs-lookup"><span data-stu-id="6d624-119">Appendix H: Analysis of the Unique Particle Attribution Constraint (non-normative)</span></span>  
  
 <span data-ttu-id="6d624-120">Para ver el documento, visite [http://www.w3.org/TR/xmlschema-1](https://go.microsoft.com/fwlink/?linkid=48881).</span><span class="sxs-lookup"><span data-stu-id="6d624-120">To see the document, visit [http://www.w3.org/TR/xmlschema-1](https://go.microsoft.com/fwlink/?linkid=48881).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d624-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d624-121">See Also</span></span>  
 [<span data-ttu-id="6d624-122">Colecciones de esquemas XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d624-122">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
