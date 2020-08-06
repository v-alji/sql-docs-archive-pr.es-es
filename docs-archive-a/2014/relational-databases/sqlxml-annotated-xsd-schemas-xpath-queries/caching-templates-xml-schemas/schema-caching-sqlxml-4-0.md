---
title: Almacenamiento en caché de esquemas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- schemas [SQLXML]
ms.assetid: 7e5fda21-b435-41fd-b637-8b616560a93f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e36711955fa28bafd3b0996b1a02f6cd71f3c4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676414"
---
# <a name="schema-caching-sqlxml-40"></a><span data-ttu-id="03692-102">Almacenamiento de esquemas en caché (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="03692-102">Schema Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="03692-103">Con una instalación simultánea de XML para Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0 y SQLXML 3.0, puede controlar de forma explícita el almacenamiento en caché de esquemas en todas las versiones utilizando las siguientes claves del Registro:</span><span class="sxs-lookup"><span data-stu-id="03692-103">With a side-by-side installation of XML for Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0, and SQLXML 3.0, you can explicitly control the schema caching in all versions by using the following registry keys:</span></span>  
  
 <span data-ttu-id="03692-104">Web Release 1:</span><span class="sxs-lookup"><span data-stu-id="03692-104">Web Release 1:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXMLX\SchemaCacheSize  
```  
  
 <span data-ttu-id="03692-105">SQLXML 2,0:</span><span class="sxs-lookup"><span data-stu-id="03692-105">SQLXML 2.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML2\SchemaCacheSize  
```  
  
 <span data-ttu-id="03692-106">SQLXML 3.0:</span><span class="sxs-lookup"><span data-stu-id="03692-106">SQLXML 3.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML3\SchemaCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="03692-107">Para obtener más información acerca de la instalación en paralelo, vea [novedades de SQLXML 4,0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span><span class="sxs-lookup"><span data-stu-id="03692-107">For more information about side-by-side installation, see [What's New in SQLXML 4.0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span></span>  
  
 <span data-ttu-id="03692-108">El almacenamiento de esquemas en la memoria caché mejora significativamente el rendimiento de una consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="03692-108">Schema caching significantly improves the performance of an XPath query.</span></span> <span data-ttu-id="03692-109">Cuando se ejecuta una consulta XPath para un esquema de asignación, el esquema se almacena en memoria y las estructuras de datos necesarias se generan en memoria.</span><span class="sxs-lookup"><span data-stu-id="03692-109">When an XPath query is executed against a mapping schema, the schema is stored in memory, and the necessary data structures are built in memory.</span></span> <span data-ttu-id="03692-110">Si se establece el almacenamiento en caché del esquema, el esquema permanece en memoria, con lo que se mejora el rendimiento de las consultas XPath subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="03692-110">If schema caching is set, the schema remains in memory, thereby improving performance for subsequent XPath queries.</span></span>  
  
 <span data-ttu-id="03692-111">Puede establecer el tamaño de caché para el esquema agregando la clave anterior en el Registro</span><span class="sxs-lookup"><span data-stu-id="03692-111">You can set the schema cache size by adding the above key in the registry</span></span>  
  
 <span data-ttu-id="03692-112">El tamaño del esquema se establece en función de la memoria disponible y el número de esquemas que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="03692-112">The schema size is set based on the available memory and the number of schemas you are using.</span></span> <span data-ttu-id="03692-113">El tamaño predeterminado de **SchemaCacheSize** es 31.</span><span class="sxs-lookup"><span data-stu-id="03692-113">The default **SchemaCacheSize** size is 31.</span></span> <span data-ttu-id="03692-114">Si establece **SchemaCacheSize** superior, se usa más memoria.</span><span class="sxs-lookup"><span data-stu-id="03692-114">If you set **SchemaCacheSize** higher, more memory is used.</span></span> <span data-ttu-id="03692-115">Por consiguiente, puede aumentar el tamaño de caché si el acceso al esquema parece lento o puede reducirlo si hay poca memoria.</span><span class="sxs-lookup"><span data-stu-id="03692-115">Therefore, you can increase the cache size if schema access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="03692-116">Por motivos de rendimiento, se recomienda establecer **SchemaCacheSize** en un valor mayor que el número de esquemas de asignación que se suelen usar.</span><span class="sxs-lookup"><span data-stu-id="03692-116">For performance reasons, it is recommended that you set **SchemaCacheSize** higher than the number of mapping schemas you usually use.</span></span> <span data-ttu-id="03692-117">A medida que aumenta el número de esquemas, si **SchemaCacheSize** es menor que el número de esquemas que tiene, el rendimiento se degrada.</span><span class="sxs-lookup"><span data-stu-id="03692-117">As the number of schemas increase, if **SchemaCacheSize** is less than the number of schemas you have, the performance degrades.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03692-118">Durante el desarrollo, se recomienda que no almacene los esquemas en la memoria caché, ya que los cambios hechos en los esquemas no se reflejan en la caché durante aproximadamente dos minutos.</span><span class="sxs-lookup"><span data-stu-id="03692-118">During development, it is recommended that you do not cache the schemas, because the changes to the schemas are not reflected in the cache for about two minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03692-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03692-119">See Also</span></span>  
 <span data-ttu-id="03692-120">[Almacenamiento en caché de plantillas &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="03692-120">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="03692-121">Almacenamiento en caché XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="03692-121">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
