---
title: Modelos de contenido no determinista | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- non-deterministic content models
- content models [XML in SQL Server]
ms.assetid: 9d4513e7-dd19-4491-b7c7-28bc7c2f8589
author: rothja
ms.author: jroth
ms.openlocfilehash: 6182ff4a5ee0c9c109f6880c7d3337fb6dd20749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744533"
---
# <a name="non-deterministic-content-models"></a><span data-ttu-id="f2f1e-102">modelos de contenido no determinista</span><span class="sxs-lookup"><span data-stu-id="f2f1e-102">Non-Deterministic Content Models</span></span>
  <span data-ttu-id="f2f1e-103">Antes de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rechazaba los esquemas XML que tenían modelos de contenido no deterministas.</span><span class="sxs-lookup"><span data-stu-id="f2f1e-103">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejected XML schemas that had non-deterministic content models.</span></span>  
  
 <span data-ttu-id="f2f1e-104">Pero a partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1, se aceptan modelos de contenido no deterministas si las restricciones de repetición son 0, 1 o sin delimitar.</span><span class="sxs-lookup"><span data-stu-id="f2f1e-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1, however, non-deterministic content models are accepted if the occurrence constraints are 0,1, or unbounded.</span></span>  
  
## <a name="example-non-deterministic-content-model-rejected"></a><span data-ttu-id="f2f1e-105">Ejemplo: modelo de contenido no determinista rechazado</span><span class="sxs-lookup"><span data-stu-id="f2f1e-105">Example: Non-deterministic content model rejected</span></span>  
 <span data-ttu-id="f2f1e-106">En el siguiente ejemplo se intenta crear un esquema XML con un modelo de contenido no determinista.</span><span class="sxs-lookup"><span data-stu-id="f2f1e-106">The following example attempts to create an XML schema with a non-deterministic content model.</span></span> <span data-ttu-id="f2f1e-107">El código genera un error porque no está claro si el elemento `<root>` debería tener una secuencia de dos elementos `<a>` o si el elemento `<root>` debería tener dos secuencias, cada una de ellas con un elemento `<a>` .</span><span class="sxs-lookup"><span data-stu-id="f2f1e-107">The code fails because it is not clear whether the `<root>` element should have a sequence of two `<a>` elements or if the `<root>` element should have two sequences, each with an `<a>` element.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="1" maxOccurs="2">  
                <element name="a" type="string" minOccurs="1" maxOccurs="2"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
 <span data-ttu-id="f2f1e-108">El esquema se puede corregir moviendo la restricción de repetición a una ubicación única.</span><span class="sxs-lookup"><span data-stu-id="f2f1e-108">The schema can be fixed by moving the occurrence constraint to a unique location.</span></span> <span data-ttu-id="f2f1e-109">Por ejemplo, la restricción se puede mover a la partícula de secuencia contenedora:</span><span class="sxs-lookup"><span data-stu-id="f2f1e-109">For example, the constraint can be moved to the containing sequence particle:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="4">  
    <element name="a" type="string" minOccurs="1" maxOccurs="1"/>  
</sequence>  
```  
  
 <span data-ttu-id="f2f1e-110">O bien, la restricción se puede mover al elemento contenido:</span><span class="sxs-lookup"><span data-stu-id="f2f1e-110">Or the constraint can be moved to the contained element:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="1">  
     <element name="a" type="string" minOccurs="1" maxOccurs="4"/>  
</sequence>  
```  
  
## <a name="example-non-deterministic-content-model-accepted"></a><span data-ttu-id="f2f1e-111">Ejemplo: modelo de contenido no determinista aceptado</span><span class="sxs-lookup"><span data-stu-id="f2f1e-111">Example: Non-deterministic content model accepted</span></span>  
 <span data-ttu-id="f2f1e-112">El esquema siguiente se rechazaría en versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="f2f1e-112">The following schema would be rejected in versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="0" maxOccurs="unbounded">  
                <element name="a" type="string" minOccurs="0" maxOccurs="1"/>  
                <element name="b" type="string" minOccurs="1" maxOccurs="unbounded"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2f1e-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2f1e-113">See Also</span></span>  
 [<span data-ttu-id="f2f1e-114">Requisitos y limitaciones de las colecciones de esquemas XML en el servidor</span><span class="sxs-lookup"><span data-stu-id="f2f1e-114">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
