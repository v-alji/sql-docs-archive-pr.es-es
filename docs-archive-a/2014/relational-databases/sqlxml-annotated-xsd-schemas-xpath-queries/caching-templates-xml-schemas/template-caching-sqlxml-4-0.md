---
title: Almacenamiento en caché de plantillas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- templates [SQLXML], caching
ms.assetid: 73e151c6-b24e-4422-a116-51e0846bc6f5
author: rothja
ms.author: jroth
ms.openlocfilehash: b2ea8a539086ada1b15abbb9cff4f838af45818c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672874"
---
# <a name="template-caching-sqlxml-40"></a><span data-ttu-id="d59e8-102">Almacenamiento en caché de plantillas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d59e8-102">Template Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="d59e8-103">Al almacenar las plantillas en la memoria caché mejora considerablemente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d59e8-103">Template caching significantly improves performance.</span></span> <span data-ttu-id="d59e8-104">Si se establece el almacenamiento en caché de la plantilla, ésta permanece en memoria en su primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="d59e8-104">If template caching is set, the template remains in memory upon its first execution.</span></span> <span data-ttu-id="d59e8-105">Esto mejora el rendimiento de la próxima ejecución de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="d59e8-105">This improves the performance for the subsequent execution of the template.</span></span>  
  
 <span data-ttu-id="d59e8-106">Puede establecer el tamaño de caché de la plantilla agregando la siguiente clave en el Registro:</span><span class="sxs-lookup"><span data-stu-id="d59e8-106">You can set the template cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\TemplateCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="d59e8-107">El tamaño de la plantilla se debería establecer en función de la memoria disponible y del número de plantillas que se esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="d59e8-107">The template size should be set on the basis of the available memory and the number of templates you are using.</span></span> <span data-ttu-id="d59e8-108">El valor predeterminado de **TemplateCacheSize** size es 31.</span><span class="sxs-lookup"><span data-stu-id="d59e8-108">The default of **TemplateCacheSize** size is 31.</span></span> <span data-ttu-id="d59e8-109">Puede aumentar el tamaño de caché si el acceso a la plantilla parece lento o puede reducirlo si hay poca memoria.</span><span class="sxs-lookup"><span data-stu-id="d59e8-109">You can increase the cache size if template access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="d59e8-110">Para mejorar el rendimiento, se recomienda establecer **TemplateCacheSize** en un valor mayor que el número de plantillas que se suelen usar.</span><span class="sxs-lookup"><span data-stu-id="d59e8-110">For better performance, it is recommended that you set **TemplateCacheSize** higher than the number of templates you usually use.</span></span> <span data-ttu-id="d59e8-111">Si **templatecachesize** es menor que el número de plantillas que tiene, el rendimiento se degrada a medida que aumenta el número de plantillas.</span><span class="sxs-lookup"><span data-stu-id="d59e8-111">If **TemlateCacheSize** is less than the number of templates you have, performance degrades as the number of templates increase.</span></span> <span data-ttu-id="d59e8-112">El valor de **TemplateCacheSize** se puede establecer en un máximo de 128.</span><span class="sxs-lookup"><span data-stu-id="d59e8-112">The **TemplateCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="d59e8-113">Cada vez que se utiliza una plantilla almacenada en la memoria caché, se comprueba el tiempo de modificación del archivo de plantilla para ver si es necesario actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="d59e8-113">Every time a cached template is used, the modification time of the template file is checked to see whether it needs to be refreshed.</span></span> <span data-ttu-id="d59e8-114">Esto se debe a que la copia en disco es más reciente que la copia en la caché.</span><span class="sxs-lookup"><span data-stu-id="d59e8-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d59e8-115">Los parámetros de plantilla y las propiedades de comandos no se almacenan en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d59e8-115">Template parameters and command properties are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d59e8-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d59e8-116">See Also</span></span>  
 <span data-ttu-id="d59e8-117">[Almacenamiento en caché de esquemas &#40;SQLXML 4,0&#41;](schema-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="d59e8-117">[Schema Caching &#40;SQLXML 4.0&#41;](schema-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="d59e8-118">Almacenamiento en caché XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d59e8-118">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
