---
title: Almacenamiento en caché XSL (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- XSL caching [SQLXML]
ms.assetid: 91994142-32f0-4d8d-a8cf-eb0d8b1f1999
author: rothja
ms.author: jroth
ms.openlocfilehash: e41f247c34c1b40bedfdf6924a45afe5f63735b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746200"
---
# <a name="xsl-caching-sqlxml-40"></a><span data-ttu-id="63ff3-102">Almacenamiento en caché XSL (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="63ff3-102">XSL Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="63ff3-103">Cuando se almacenan en caché hojas de estilos XSL, se mejora rendimiento.</span><span class="sxs-lookup"><span data-stu-id="63ff3-103">Caching XSL style sheets improves performance.</span></span> <span data-ttu-id="63ff3-104">En su primera ejecución, una hoja de estilos XSL permanece en memoria si el almacenamiento en caché XSL está establecido en ON; esto mejora el rendimiento en el procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="63ff3-104">Upon its first execution, an XSL style sheet remains in memory if XSL caching is set to ON; this improves performance for subsequent processing.</span></span> <span data-ttu-id="63ff3-105">El valor predeterminado es ON.</span><span class="sxs-lookup"><span data-stu-id="63ff3-105">The default setting is ON.</span></span>  
  
 <span data-ttu-id="63ff3-106">Puede establecer el tamaño de la caché de XSL agregando la siguiente clave en el Registro:</span><span class="sxs-lookup"><span data-stu-id="63ff3-106">You can set the XSL cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\XSLCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="63ff3-107">El tamaño de la caché de XSL se debería establecer en base a la memoria disponible y el número de hojas de estilos XSL que está utilizando.</span><span class="sxs-lookup"><span data-stu-id="63ff3-107">The XSL cache size should be set on the basis of the available memory and the number of XSL style sheets you are using.</span></span> <span data-ttu-id="63ff3-108">El valor predeterminado de **XSLCacheSize** es 31.</span><span class="sxs-lookup"><span data-stu-id="63ff3-108">The default of **XSLCacheSize** size is 31.</span></span> <span data-ttu-id="63ff3-109">Puede aumentar el tamaño de la caché si el acceso a XSL parece lento o puede reducirlo si hay poca memoria.</span><span class="sxs-lookup"><span data-stu-id="63ff3-109">You can increase the cache size if XSL access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="63ff3-110">Para mejorar el rendimiento, es recomendable que establezca **XSLCacheSize** en un valor más alto que el número de hojas de estilos XSL que normalmente utiliza.</span><span class="sxs-lookup"><span data-stu-id="63ff3-110">For better performance, it is recommended that you set **XSLCacheSize** higher than the number of XSL style sheets you usually use.</span></span> <span data-ttu-id="63ff3-111">Si **XSLCacheSize** es menor que el número que tiene de hojas de estilos XSL, el rendimiento es peor a medida que el número de hojas de estilos de XSL aumenta.</span><span class="sxs-lookup"><span data-stu-id="63ff3-111">If **XSLCacheSize** is less than the number of XSL style sheets you have, the performance degrades as the number of XSL style sheets increases.</span></span> <span data-ttu-id="63ff3-112">**XSLCacheSize** puede estar establecido en un máximo de 128.</span><span class="sxs-lookup"><span data-stu-id="63ff3-112">The **XSLCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="63ff3-113">Cada vez que se usa la hoja de estilos XSL almacenada en caché, se comprueba el tiempo de modificación del archivo XSL para determinar si se debe actualizar.</span><span class="sxs-lookup"><span data-stu-id="63ff3-113">Every time the cached XSL style sheet is used, the modification time of the XSL file is checked to determine whether it needs to be refreshed.</span></span> <span data-ttu-id="63ff3-114">Esto se debe a que la copia en disco es más reciente que la copia en la caché.</span><span class="sxs-lookup"><span data-stu-id="63ff3-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ff3-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63ff3-115">See Also</span></span>  
 <span data-ttu-id="63ff3-116">[Almacenamiento en caché de plantillas &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="63ff3-116">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="63ff3-117">Almacenamiento en caché de esquemas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="63ff3-117">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
  
  
