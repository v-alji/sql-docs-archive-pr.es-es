---
title: Tipo mixto y contenido simple | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- mixed types [SQL Server]
ms.assetid: 6ea1f11d-e64b-4ebb-ab68-4eb6e4027665
author: rothja
ms.author: jroth
ms.openlocfilehash: eb46769ee4c4d635af36a3c50fda34e8e1801b34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744536"
---
# <a name="mixed-type-and-simple-content"></a><span data-ttu-id="422b8-102">Contenido simple y de tipo mixto</span><span class="sxs-lookup"><span data-stu-id="422b8-102">Mixed Type and Simple Content</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="422b8-103">no admite la restricción de un tipo mixto a un contenido simple.</span><span class="sxs-lookup"><span data-stu-id="422b8-103">does not support restricting a mixed type to a simple content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="422b8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="422b8-104">Example</span></span>  
 <span data-ttu-id="422b8-105">En la colección de esquemas XML siguiente, `myComplexTypeA` es un tipo complejo que se puede vaciar.</span><span class="sxs-lookup"><span data-stu-id="422b8-105">In the following XML schema collection, `myComplexTypeA` is a complex type that can be emptied.</span></span> <span data-ttu-id="422b8-106">Es decir, ambos elementos tienen `minOccurs` establecido en 0.</span><span class="sxs-lookup"><span data-stu-id="422b8-106">That is, both its elements have `minOccurs` set to 0.</span></span> <span data-ttu-id="422b8-107">No se admite el intento de restringir esto a un contenido simple, como en la declaración `myComplexTypeB` .</span><span class="sxs-lookup"><span data-stu-id="422b8-107">The attempt to restrict this to a simple content, as in the `myComplexTypeB` declaration, is not supported.</span></span> <span data-ttu-id="422b8-108">Por tanto, se produce un error en la creación de la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="422b8-108">Therefore, the following XML schema collection creation fails:</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns" xmlns:ns="http://ns"  
xmlns:ns1="http://ns1">  
  
    <complexType name="myComplexTypeA" mixed="true">  
        <sequence>  
            <element name="a" type="string" minOccurs="0"/>  
            <element name="b" type="string" minOccurs="0" maxOccurs="23"/>  
        </sequence>  
    </complexType>  
  
    <complexType name="myComplexTypeB">  
        <simpleContent>  
            <restriction base="ns:myComplexTypeA">  
                <simpleType>  
                    <restriction base="int">  
                        <minExclusive value="25"/>  
                    </restriction>  
                </simpleType>  
            </restriction>  
        </simpleContent>  
    </complexType>  
</schema>  
'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="422b8-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="422b8-109">See Also</span></span>  
 [<span data-ttu-id="422b8-110">Requisitos y limitaciones de las colecciones de esquemas XML en el servidor</span><span class="sxs-lookup"><span data-stu-id="422b8-110">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
