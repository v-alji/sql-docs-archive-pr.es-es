---
title: Plantillas de almacenamiento en caché, XSL y esquemas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, caching
- cache [SQLXML]
- memory [SQLXML]
ms.assetid: 80b4fa79-243f-442c-9f22-74ad66186501
author: rothja
ms.author: jroth
ms.openlocfilehash: 4df25909cf156957908abf0691964fd66a76343a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674032"
---
# <a name="caching-templates-xsl-and-schemas-sqlxml-40"></a><span data-ttu-id="bbacc-102">Almacenar en memoria caché plantillas, XSL y esquemas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="bbacc-102">Caching Templates, XSL, and Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="bbacc-103">Para mejorar el rendimiento, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 permite almacenar en la memoria caché plantillas, archivos XSL y esquemas.</span><span class="sxs-lookup"><span data-stu-id="bbacc-103">To improve performance, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 supports caching templates, XSL, and schemas.</span></span>  
  
 <span data-ttu-id="bbacc-104">Todos los esquemas, plantillas y archivos XSL (excepto los archivos de una ubicación http:// o ftp://) están almacenados en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="bbacc-104">All schemas, templates, and XSL files (except the files from an http:// or ftp:// location) are cached.</span></span> <span data-ttu-id="bbacc-105">Los archivos almacenados en la memoria caché permanecen en memoria mientras el proceso se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="bbacc-105">The cached files remain in memory while the process is running.</span></span> <span data-ttu-id="bbacc-106">Cuando finaliza el proceso, se pierde toda la caché.</span><span class="sxs-lookup"><span data-stu-id="bbacc-106">As the process exits, all the cache is lost.</span></span> <span data-ttu-id="bbacc-107">Por consiguiente, si ejecuta un proceso por consulta, es posible que no se aprecien las ventajas del almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="bbacc-107">Therefore, if you run one process per query, the caching benefit may not be noticeable.</span></span>  
  
 <span data-ttu-id="bbacc-108">Los temas de esta sección proporcionan más información sobre cómo almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="bbacc-108">The topics in this section provide more information about caching.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bbacc-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bbacc-109">In This Section</span></span>  
 [<span data-ttu-id="bbacc-110">Almacenamiento en caché de plantillas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="bbacc-110">Template Caching &#40;SQLXML 4.0&#41;</span></span>](template-caching-sqlxml-4-0.md)  
 <span data-ttu-id="bbacc-111">Se describe y proporciona una clave del Registro para el almacenamiento en caché de las plantillas.</span><span class="sxs-lookup"><span data-stu-id="bbacc-111">Describes and provides a registry key for template caching.</span></span>  
  
 [<span data-ttu-id="bbacc-112">Almacenamiento en caché XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="bbacc-112">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
 <span data-ttu-id="bbacc-113">Se describe y proporciona una clave del Registro para el almacenamiento en caché de archivos XSL.</span><span class="sxs-lookup"><span data-stu-id="bbacc-113">Describes and provides a registry key for XSL caching.</span></span>  
  
 [<span data-ttu-id="bbacc-114">Almacenamiento en caché de esquemas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="bbacc-114">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
 <span data-ttu-id="bbacc-115">Se explican cuestiones de instalación simultánea de SQLXML relacionadas con el almacenamiento en la memoria caché de esquemas y proporciona las claves del Registro para el almacenamiento en caché de esquemas.</span><span class="sxs-lookup"><span data-stu-id="bbacc-115">Discusses SQLXML side-by-side installation issues related to schema caching, and provides registry keys for schema caching.</span></span>  
  
  
