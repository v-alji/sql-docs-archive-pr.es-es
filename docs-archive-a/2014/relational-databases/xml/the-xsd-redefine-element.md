---
title: Elemento &lt;xsd:redefine&gt; | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xsd:redefine element
ms.assetid: 5f3e9b65-f10e-4db2-a62c-b270ac11d04e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce439e81cf87e97b4afe6e25a201e1ab0cb2a458
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747523"
---
# <a name="the-ltxsdredefinegt-element"></a><span data-ttu-id="7b969-102">Elemento &lt;xsd:redefine&gt;</span><span class="sxs-lookup"><span data-stu-id="7b969-102">The &lt;xsd:redefine&gt; Element</span></span>
  <span data-ttu-id="7b969-103">El elemento **redefine** de W3C XSD proporciona compatibilidad con la nueva definición de componentes de esquema.</span><span class="sxs-lookup"><span data-stu-id="7b969-103">The W3C XSD **redefine** element provides support for redefining schema components.</span></span> <span data-ttu-id="7b969-104">Sin embargo, la compatibilidad con esta directiva es potencialmente costosa para el rendimiento y también requiere que vuelva a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] validar todas las instancias del `xml` tipo de datos asociado al esquema redefinido.</span><span class="sxs-lookup"><span data-stu-id="7b969-104">However, support for this directive is potentially costly to performance and also requires that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revalidate all instances of the `xml` data type associated with the redefined schema.</span></span> <span data-ttu-id="7b969-105">Por consiguiente, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no admite este elemento.</span><span class="sxs-lookup"><span data-stu-id="7b969-105">Therefore, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support this element.</span></span> <span data-ttu-id="7b969-106">El servidor rechaza los esquemas XML que incluyen el elemento **\<xsd:redefine>** .</span><span class="sxs-lookup"><span data-stu-id="7b969-106">XML schemas that include the **\<xsd:redefine>** element are rejected by the server.</span></span>  
  
 <span data-ttu-id="7b969-107">Para actualizar un esquema o sus componentes, puede hacer, en su lugar, lo que se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="7b969-107">To update a schema or its components, you can do the following instead:</span></span>  
  
1.  <span data-ttu-id="7b969-108">Cree una nueva colección de esquemas XML con los componentes de esquema modificados.</span><span class="sxs-lookup"><span data-stu-id="7b969-108">Create a new XML Schema collection with the modified schema components.</span></span>  
  
2.  <span data-ttu-id="7b969-109">Vuelva a escribir todos los `xml` tipos de datos (XML DT) que usan la colección de esquemas XML que se van a redefinir para usar la nueva colección de esquemas XML en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7b969-109">Retype all `xml` data types (XML DT) that use the XML Schema collection to be redefined to use the new XML Schema collection instead.</span></span> <span data-ttu-id="7b969-110">Para ello, use la opción ALTER COLUMN del comando ALTER TABLE para volver a escribir columnas o bien, cambie las restricciones de la colección de esquemas XML en variables o parámetros.</span><span class="sxs-lookup"><span data-stu-id="7b969-110">To do this, use the ALTER COLUMN option of the ALTER TABLE command for retyping columns, or change the XML Schema collection constraints on variables or parameters.</span></span>  
  
3.  <span data-ttu-id="7b969-111">Quite la versión anterior de la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="7b969-111">Drop the old version of the XML Schema collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b969-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b969-112">See Also</span></span>  
 [<span data-ttu-id="7b969-113">Requisitos y limitaciones de las colecciones de esquemas XML en el servidor</span><span class="sxs-lookup"><span data-stu-id="7b969-113">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
