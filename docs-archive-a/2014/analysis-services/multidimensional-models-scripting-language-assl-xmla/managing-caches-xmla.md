---
title: Administrar cachés (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- XMLA, cache
- XML for Analysis, cache
- clearing cache
- cache [Analysis Services]
ms.assetid: afad5c39-d4c3-4307-b3b9-a06617da0028
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdc5bcd2e0500749edfa298a871b6fec7243ddfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671768"
---
# <a name="managing-caches-xmla"></a><span data-ttu-id="5ae5f-102">Administrar cachés (XMLA)</span><span class="sxs-lookup"><span data-stu-id="5ae5f-102">Managing Caches (XMLA)</span></span>
  <span data-ttu-id="5ae5f-103">Puede usar el comando [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) en XML for Analysis (XMLA) para borrar la memoria caché de una dimensión o partición especificada.</span><span class="sxs-lookup"><span data-stu-id="5ae5f-103">You can use the [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) command in XML for Analysis (XMLA) to clear the cache of a specified dimension or partition.</span></span> <span data-ttu-id="5ae5f-104">Al borrar las fuerzas de caché, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se vuelve a generar la memoria caché para ese objeto.</span><span class="sxs-lookup"><span data-stu-id="5ae5f-104">Clearing the cache forces [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to rebuild the cache for that object.</span></span>  
  
## <a name="specifying-objects"></a><span data-ttu-id="5ae5f-105">Especificar objetos</span><span class="sxs-lookup"><span data-stu-id="5ae5f-105">Specifying Objects</span></span>  
 <span data-ttu-id="5ae5f-106">La propiedad [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) del `ClearCache` comando solo puede contener una referencia de objeto para uno de los siguientes objetos.</span><span class="sxs-lookup"><span data-stu-id="5ae5f-106">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `ClearCache` command can contain an object reference only for one of the following objects.</span></span> <span data-ttu-id="5ae5f-107">Si se utiliza una referencia de objeto para un objeto distinto de los siguientes, se produce un error:</span><span class="sxs-lookup"><span data-stu-id="5ae5f-107">An error occurs if an object reference is for an object other than one of following objects:</span></span>  
  
 <span data-ttu-id="5ae5f-108">Base de datos</span><span class="sxs-lookup"><span data-stu-id="5ae5f-108">Database</span></span>  
 <span data-ttu-id="5ae5f-109">Borra la memoria caché para todas las dimensiones y particiones contenidas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5ae5f-109">Clears the cache for all dimensions and partitions contained in the database.</span></span>  
  
 <span data-ttu-id="5ae5f-110">Dimensión</span><span class="sxs-lookup"><span data-stu-id="5ae5f-110">Dimension</span></span>  
 <span data-ttu-id="5ae5f-111">Borra la memoria caché para la dimensión especificada.</span><span class="sxs-lookup"><span data-stu-id="5ae5f-111">Clears the cache for the specified dimension.</span></span>  
  
 <span data-ttu-id="5ae5f-112">Cubo</span><span class="sxs-lookup"><span data-stu-id="5ae5f-112">Cube</span></span>  
 <span data-ttu-id="5ae5f-113">Borra la memoria caché para todas las particiones contenidas en los grupos de medida para el cubo.</span><span class="sxs-lookup"><span data-stu-id="5ae5f-113">Clears the cache for all partitions contained in the measure groups for the cube.</span></span>  
  
 <span data-ttu-id="5ae5f-114">Grupo de medida</span><span class="sxs-lookup"><span data-stu-id="5ae5f-114">Measure group</span></span>  
 <span data-ttu-id="5ae5f-115">Borra la memoria caché para todas las particiones contenidas en el grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="5ae5f-115">Clears the cache for all partitions contained in the measure group.</span></span>  
  
 <span data-ttu-id="5ae5f-116">Partition</span><span class="sxs-lookup"><span data-stu-id="5ae5f-116">Partition</span></span>  
 <span data-ttu-id="5ae5f-117">Borra la memoria caché para la partición especificada.</span><span class="sxs-lookup"><span data-stu-id="5ae5f-117">Clears the cache for the specified partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae5f-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ae5f-118">See Also</span></span>  
 [<span data-ttu-id="5ae5f-119">Desarrollar con XMLA en Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5ae5f-119">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
