---
title: Propiedades personalizadas del destino DataReader | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f151c3e8-3811-457d-a3d3-6158ca65a646
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62b6f628614d533e1bebcce071ce4761e73e08f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673814"
---
# <a name="datareader-destination-custom-properties"></a><span data-ttu-id="c3e99-102">Propiedades personalizadas del destino DataReader</span><span class="sxs-lookup"><span data-stu-id="c3e99-102">DataReader Destination Custom Properties</span></span>
  <span data-ttu-id="c3e99-103">El destino DataReader tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="c3e99-103">The DataReader destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="c3e99-104">En la tabla siguiente se describen las propiedades personalizadas del destino DataReader.</span><span class="sxs-lookup"><span data-stu-id="c3e99-104">The following table describes the custom properties of the DataReader destination.</span></span> <span data-ttu-id="c3e99-105">Todas las propiedades excepto `DataReader` son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="c3e99-105">All properties except for `DataReader` are read/write.</span></span>  
  
|<span data-ttu-id="c3e99-106">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="c3e99-106">Property name</span></span>|<span data-ttu-id="c3e99-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c3e99-107">Data Type</span></span>|<span data-ttu-id="c3e99-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3e99-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="c3e99-109">DataReader</span><span class="sxs-lookup"><span data-stu-id="c3e99-109">DataReader</span></span>|<span data-ttu-id="c3e99-110">String</span><span class="sxs-lookup"><span data-stu-id="c3e99-110">String</span></span>|<span data-ttu-id="c3e99-111">Nombre de clase del destino DataReader.</span><span class="sxs-lookup"><span data-stu-id="c3e99-111">The class name of the DataReader destination.</span></span>|  
|<span data-ttu-id="c3e99-112">FailOnTimeout</span><span class="sxs-lookup"><span data-stu-id="c3e99-112">FailOnTimeout</span></span>|<span data-ttu-id="c3e99-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3e99-113">Boolean</span></span>|<span data-ttu-id="c3e99-114">Indica si generar un error cuando se produce un `ReadTimeout`.</span><span class="sxs-lookup"><span data-stu-id="c3e99-114">Indicates whether to fail when a `ReadTimeout` occurs.</span></span> <span data-ttu-id="c3e99-115">El valor predeterminado de esta propiedad es **False**.</span><span class="sxs-lookup"><span data-stu-id="c3e99-115">The default value of this property is **False**.</span></span>|  
|<span data-ttu-id="c3e99-116">ReadTimeout</span><span class="sxs-lookup"><span data-stu-id="c3e99-116">ReadTimeout</span></span>|<span data-ttu-id="c3e99-117">Entero</span><span class="sxs-lookup"><span data-stu-id="c3e99-117">Integer</span></span>|<span data-ttu-id="c3e99-118">Número de milisegundos que transcurren antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c3e99-118">The number of milliseconds before a time-out occurs.</span></span> <span data-ttu-id="c3e99-119">El valor predeterminado de esta propiedad es 30000 (30 segundos).</span><span class="sxs-lookup"><span data-stu-id="c3e99-119">The default value of this property is 30000 (30 seconds).</span></span>|  
  
 <span data-ttu-id="c3e99-120">La entrada y las columnas de entrada del destino DataReader no tienen ninguna propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="c3e99-120">The input and the input columns of the DataReader destination have no custom properties.</span></span>  
  
 <span data-ttu-id="c3e99-121">Para más información, consulte [DataReader Destination](datareader-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c3e99-121">For more information, see [DataReader Destination](datareader-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e99-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3e99-122">See Also</span></span>  
 [<span data-ttu-id="c3e99-123">Common Properties</span><span class="sxs-lookup"><span data-stu-id="c3e99-123">Common Properties</span></span>](../common-properties.md)  
  
  
