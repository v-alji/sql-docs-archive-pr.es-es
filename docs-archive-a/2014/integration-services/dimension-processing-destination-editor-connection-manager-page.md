---
title: Editor de destino de procesamiento de dimensiones (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.connection.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 44aab631-d62d-4895-8fc7-7f1f3b1b68ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 50ba42292c1f48c9b1cdf2ba00c709dacd2f9675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677225"
---
# <a name="dimension-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="a0bcb-102">Editor de destino de procesamiento de dimensiones (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="a0bcb-102">Dimension Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="a0bcb-103">Utilice la página **Administrador de conexiones** del cuadro de diálogo **Editor de destino de procesamiento de dimensiones** para especificar una conexión a un proyecto de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o a una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0bcb-103">Use the **Connection Manager** page of the **Dimension Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a0bcb-104">Para obtener más información acerca del destino de procesamiento de dimensiones, vea [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a0bcb-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a0bcb-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="a0bcb-105">Options</span></span>  
 <span data-ttu-id="a0bcb-106">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="a0bcb-106">**Connection manager**</span></span>  
 <span data-ttu-id="a0bcb-107">Seleccione un administrador de conexiones existente de la lista, o haga clic en **Nuevo** para crear un nuevo administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="a0bcb-107">Select an existing connection manager from the list, or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="a0bcb-108">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="a0bcb-108">**New**</span></span>  
 <span data-ttu-id="a0bcb-109">Permite crear una conexión con el cuadro de diálogo **Agregar administrador de conexiones de Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="a0bcb-109">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="a0bcb-110">**Lista de dimensiones disponibles**</span><span class="sxs-lookup"><span data-stu-id="a0bcb-110">**List of available dimensions**</span></span>  
 <span data-ttu-id="a0bcb-111">Seleccione la dimensión para procesar.</span><span class="sxs-lookup"><span data-stu-id="a0bcb-111">Select the dimension to process.</span></span>  
  
 <span data-ttu-id="a0bcb-112">**Método de procesamiento**</span><span class="sxs-lookup"><span data-stu-id="a0bcb-112">**Processing method**</span></span>  
 <span data-ttu-id="a0bcb-113">En la lista, seleccione el método de procesamiento a aplicar a la dimensión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a0bcb-113">Select the processing method to apply to the dimension selected in the list.</span></span> <span data-ttu-id="a0bcb-114">El valor predeterminado de esta opción es **Completa**.</span><span class="sxs-lookup"><span data-stu-id="a0bcb-114">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="a0bcb-115">Value</span><span class="sxs-lookup"><span data-stu-id="a0bcb-115">Value</span></span>|<span data-ttu-id="a0bcb-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0bcb-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0bcb-117">**Agregar (incremental)**</span><span class="sxs-lookup"><span data-stu-id="a0bcb-117">**Add (incremental)**</span></span>|<span data-ttu-id="a0bcb-118">Realiza un procesamiento incremental de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="a0bcb-118">Perform an incremental processing of the dimension.</span></span>|  
|<span data-ttu-id="a0bcb-119">**Completa**</span><span class="sxs-lookup"><span data-stu-id="a0bcb-119">**Full**</span></span>|<span data-ttu-id="a0bcb-120">Realiza un procesamiento completo de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="a0bcb-120">Perform full processing of the dimension.</span></span>|  
|<span data-ttu-id="a0bcb-121">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="a0bcb-121">**Update**</span></span>|<span data-ttu-id="a0bcb-122">Realiza un procesamiento actualizado de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="a0bcb-122">Perform an update processing of the dimension.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0bcb-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0bcb-123">See Also</span></span>  
 <span data-ttu-id="a0bcb-124">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a0bcb-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a0bcb-125">[Editor de destino de procesamiento de dimensiones &#40;página asignaciones&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="a0bcb-125">[Dimension Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="a0bcb-126">Editor de destino de procesamiento de dimensiones &#40;página Avanzadas&#41;</span><span class="sxs-lookup"><span data-stu-id="a0bcb-126">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-advanced-page.md)  
  
  
