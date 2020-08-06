---
title: Al realizar la actualización, la búsqueda de texto completo usará filtros y separadores de palabras de nivel de instancia, no globales, de forma predeterminada | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filters [Full-Text Search]
- word breakers [Full-Text Search]
ms.assetid: 93ee8fcb-d11c-49fa-8fac-51ed31a8f008
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b6cea7ab63351fad25f0205a614e364328171a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678035"
---
# <a name="upgrading-will-cause-full-text-search-to-use-instance-level-not-global-word-breakers-and-filters-by-default"></a><span data-ttu-id="6ddb4-102">La actualización provocará que, de forma predeterminada, la búsqueda de texto completo utilice separadores y filtros de palabras de nivel de instancia, no globales</span><span class="sxs-lookup"><span data-stu-id="6ddb4-102">Upgrading will cause Full-Text Search to use instance-level, not global, word breakers and filters by default</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6ddb4-103">proporciona una manera de registrar, a nivel de instancia, nuevos separadores y filtros de palabras.</span><span class="sxs-lookup"><span data-stu-id="6ddb4-103">provides a way to allow instance-level registration of new word breakers and filters.</span></span>  
  
## <a name="component"></a><span data-ttu-id="6ddb4-104">Componente</span><span class="sxs-lookup"><span data-stu-id="6ddb4-104">Component</span></span>  
 <span data-ttu-id="6ddb4-105">Búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="6ddb4-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="6ddb4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ddb4-106">Description</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6ddb4-107">permite el registro de nivel de instancia de nuevos separadores y filtros de palabras.</span><span class="sxs-lookup"><span data-stu-id="6ddb4-107">allows the instance-level registration of new word breakers and filters.</span></span> <span data-ttu-id="6ddb4-108">Este registro de nivel de instancia proporciona un grado de aislamiento, tanto funcional como de seguridad, entre las instancias.</span><span class="sxs-lookup"><span data-stu-id="6ddb4-108">This instance-level registration provides functional and security isolation between instances.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="6ddb4-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="6ddb4-109">Corrective Action</span></span>  
 <span data-ttu-id="6ddb4-110">Tras realizar la actualización, utilice `sp_fulltext_service` para establecer la propiedad de servicio y `load_os_resources`, que permiten cargar los componentes.</span><span class="sxs-lookup"><span data-stu-id="6ddb4-110">After upgrading, use the `sp_fulltext_service` to set the service property and `load_os_resources`, which allows the components to be loaded.</span></span> <span data-ttu-id="6ddb4-111">Debe ejecutar las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="6ddb4-111">You must run the following:</span></span>  
  
 `sp_fulltext_service 'load_os_resources', 1`  
  
## <a name="see-also"></a><span data-ttu-id="6ddb4-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ddb4-112">See Also</span></span>  
 [<span data-ttu-id="6ddb4-113">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="6ddb4-113">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
