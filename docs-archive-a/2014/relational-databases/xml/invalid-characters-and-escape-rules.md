---
title: Reglas de escape y caracteres no válidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, invalid characters
- FOR XML clause, escape rules
ms.assetid: f2e9b997-f400-4963-b225-59d46c6b93e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 8624a31dea4e97e05da6d86c3c0c518b9c4d0aba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750558"
---
# <a name="invalid-characters-and-escape-rules"></a><span data-ttu-id="87b87-102">Reglas de escape y caracteres no válidos</span><span class="sxs-lookup"><span data-stu-id="87b87-102">Invalid Characters and Escape Rules</span></span>
  <span data-ttu-id="87b87-103">En este tema se describe cómo la cláusula FOR XML controla los caracteres XML no válidos y se enumeran las reglas de escape para los caracteres que no son válidos en los nombres XML.</span><span class="sxs-lookup"><span data-stu-id="87b87-103">This topic describes how invalid XML characters are handled by the FOR XML clause, and lists the escape rules for characters that are invalid in XML names.</span></span>  
  
## <a name="for-xml-and-invalid-characters"></a><span data-ttu-id="87b87-104">FOR XML y los caracteres no válidos</span><span class="sxs-lookup"><span data-stu-id="87b87-104">For XML and Invalid Characters</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="87b87-105">crea entidades de caracteres XML no válidos cuando estos caracteres se devuelven dentro de consultas FOR XML que no usan la directiva TYPE.</span><span class="sxs-lookup"><span data-stu-id="87b87-105">entitizes invalid XML characters when they are returned within FOR XML queries that do not use the TYPE directive.</span></span>  
  
 <span data-ttu-id="87b87-106">Aunque los analizadores compatibles con XML 1.0 generan errores de análisis, independientemente de que se hayan creado o no entidades con estos caracteres, el uso de estos caracteres con entidades se ajusta mejor a XML 1.1.</span><span class="sxs-lookup"><span data-stu-id="87b87-106">Although XML 1.0 conformant parsers raise parse errors regardless of whether these characters are entitized or not, the entitized form is better aligned with XML 1.1.</span></span> <span data-ttu-id="87b87-107">El uso de estos caracteres con entidades también se ajusta mejor a las futuras versiones del estándar XML.</span><span class="sxs-lookup"><span data-stu-id="87b87-107">The entitized form is also potentially better aligned with future versions of the XML standard.</span></span> <span data-ttu-id="87b87-108">Además, simplifica la depuración, porque el punto de código del carácter no válido pasa a ser visible.</span><span class="sxs-lookup"><span data-stu-id="87b87-108">Additionally, it makes debugging simpler, because the code point of the invalid character becomes visible.</span></span>  
  
 <span data-ttu-id="87b87-109">Los usuarios de herramientas XML no necesitan ninguna solución porque el analizador XML generará errores de todos modos en el punto del flujo de datos donde haya caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="87b87-109">For users of XML tools, no workaround is required, because the XML parser will fail either way at the point where the invalid characters occur in the data stream.</span></span> <span data-ttu-id="87b87-110">Si se utilizan herramientas no XML, este cambio puede exigir la actualización de la lógica de programación para poder buscar estos caracteres como valores con entidades.</span><span class="sxs-lookup"><span data-stu-id="87b87-110">If you use non-XML tools, this change can require you to update your programming logic to search for these characters as entitized values.</span></span>  
  
 <span data-ttu-id="87b87-111">En los siguientes caracteres de espacio en blanco, ha cambiado la forma de crear entidades en consultas FOR XML con objeto de conservar su presencia a lo largo de los recorridos de ida y vuelta:</span><span class="sxs-lookup"><span data-stu-id="87b87-111">The following white space characters are entitized differently in FOR XML queries to preserve their presence through round-tripping:</span></span>  
  
-   <span data-ttu-id="87b87-112">En contenido de elemento y atributos: **hex(0D)** (retorno de carro)</span><span class="sxs-lookup"><span data-stu-id="87b87-112">In element content and attributes: **hex(0D)** (carriage return)</span></span>  
  
-   <span data-ttu-id="87b87-113">En contenido de atributo: **hex(09)** (tabulador), **hex(0A)** (avance de línea)</span><span class="sxs-lookup"><span data-stu-id="87b87-113">In attribute content: **hex(09)** (tab), **hex(0A)** (line feed)</span></span>  
  
 <span data-ttu-id="87b87-114">Estos caracteres se conservan en la salida y no se normalizarán con ningún analizador.</span><span class="sxs-lookup"><span data-stu-id="87b87-114">These characters are preserved in output, and a parser will not normalize them.</span></span>  
  
## <a name="escape-rules"></a><span data-ttu-id="87b87-115">Reglas de escape</span><span class="sxs-lookup"><span data-stu-id="87b87-115">Escape Rules</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="87b87-116">que contienen caracteres que no son válidos en los nombres XML, como los espacios, se traducen a nombres XML, de forma que los caracteres no válidos se convierten en codificaciones de entidad numérica de escape.</span><span class="sxs-lookup"><span data-stu-id="87b87-116">names that contain characters that are invalid in XML names, such as spaces, are translated into XML names in a way in which the invalid characters are translated into escaped numeric entity encoding.</span></span>  
  
 <span data-ttu-id="87b87-117">Solo hay dos caracteres no alfabéticos que pueden incluirse en un nombre XML: los dos puntos (:) y el carácter de subrayado (_).</span><span class="sxs-lookup"><span data-stu-id="87b87-117">There are only two non-alphabetic characters that can occur within an XML name: the colon (:) and the underscore (_).</span></span> <span data-ttu-id="87b87-118">Dado que el carácter de dos puntos está reservado para los espacios de nombres, se elige el subrayado como carácter de escape.</span><span class="sxs-lookup"><span data-stu-id="87b87-118">Because the colon is already reserved for namespaces, the underscore is chosen as the escape character.</span></span> <span data-ttu-id="87b87-119">A continuación se muestran las reglas de escape que se utilizan en la codificación:</span><span class="sxs-lookup"><span data-stu-id="87b87-119">Following are the escape rules that are used for encoding:</span></span>  
  
-   <span data-ttu-id="87b87-120">Cualquier carácter UCS-2 que no sea válido como carácter de nombre XML, conforme a la especificación XML 1.0, se convierte en un carácter de escape con formato _xHHHH\_.</span><span class="sxs-lookup"><span data-stu-id="87b87-120">Any UCS-2 character that is not a valid XML name character, according to the XML 1.0 specification, is escaped as _xHHHH\_.</span></span> <span data-ttu-id="87b87-121">HHHH hace referencia al código UCS-2 hexadecimal de cuatro dígitos correspondiente al carácter que ocupa el primer lugar en función del bit más significativo.</span><span class="sxs-lookup"><span data-stu-id="87b87-121">The HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="87b87-122">Por ejemplo, el nombre de tabla **Order Details** se codifica como Order_x0020_Details.</span><span class="sxs-lookup"><span data-stu-id="87b87-122">For example, the table name **Order Details** is encoded as Order_x0020_Details.</span></span>  
  
-   <span data-ttu-id="87b87-123">Los caracteres que no se ajustan al dominio UCS-2 (como las adiciones UCS-4 del rango de U+00010000 a U+0010FFFF) se codifican como _xHHHHHHHH\_.</span><span class="sxs-lookup"><span data-stu-id="87b87-123">Characters that do not fit into the UCS-2 realm (the UCS-4 additions of the range U+00010000 to U+0010FFFF) are encoded as _xHHHHHHHH\_.</span></span> <span data-ttu-id="87b87-124">HHHHHHHH hace referencia al código UCS-4 hexadecimal de ocho dígitos correspondiente al carácter, para el modo de compatibilidad con versiones anteriores de SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="87b87-124">The HHHHHHHH stands for the eight-digit hexadecimal UCS-4 encoding of the character, if under SQL Server 2000 backward compatibility mode.</span></span> <span data-ttu-id="87b87-125">De lo contrario, los caracteres se codifican como _xHHHHHH\_, para ajustarse a la norma ISO.</span><span class="sxs-lookup"><span data-stu-id="87b87-125">Otherwise, the characters are encoded as_xHHHHHH\_, in order to align with the ISO standard.</span></span>  
  
-   <span data-ttu-id="87b87-126">No es necesario convertir en carácter de escape el carácter de subrayado, a menos que vaya seguido del carácter x.</span><span class="sxs-lookup"><span data-stu-id="87b87-126">The underscore character does not have to be escaped unless it is followed by the character x.</span></span> <span data-ttu-id="87b87-127">Por ejemplo, no es necesario codificar el nombre de tabla **Order_Details** .</span><span class="sxs-lookup"><span data-stu-id="87b87-127">For example, the table name **Order_Details** is not encoded.</span></span>  
  
-   <span data-ttu-id="87b87-128">Los dos puntos de los identificadores no se convierten en un carácter de escape, por lo que la consulta FOR XML puede generar nombres de elementos y atributos de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="87b87-128">The colon in identifiers is not escaped As a result, the namespace element and attribute names can be generated by the FOR XML query.</span></span> <span data-ttu-id="87b87-129">Por ejemplo, la siguiente consulta genera un atributo de espacio de nombres con un carácter de dos puntos en el nombre:</span><span class="sxs-lookup"><span data-stu-id="87b87-129">For example, the following query generates a namespace attribute that has a colon in the name:</span></span>  
  
    ```  
    SELECT 'namespace-urn' as 'xmlns:namespace',   
     1 as 'namespace:a'   
    FOR XML RAW  
    ```  
  
     <span data-ttu-id="87b87-130">La consulta genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="87b87-130">The query produces this result:</span></span>  
  
    ```  
    <row xmlns:namespace="namespace-urn" namespace:a="1"/>  
    ```  
  
     <span data-ttu-id="87b87-131">Tenga en cuenta que el uso de WITH XMLNAMESPACES es la forma recomendada de agregar espacios de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="87b87-131">Note that WITH XMLNAMESPACES is the recommended way to add XML namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b87-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87b87-132">See Also</span></span>  
 [<span data-ttu-id="87b87-133">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="87b87-133">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
