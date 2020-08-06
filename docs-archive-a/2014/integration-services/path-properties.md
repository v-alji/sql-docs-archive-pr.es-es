---
title: Propiedades de ruta de acceso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- paths [Integration Services], properties
ms.assetid: 89b1e347-9579-4f6b-af74-c6519ea08eea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ca263b866fb6d5d7ceb6352f708f387d79cad4f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663560"
---
# <a name="path-properties"></a><span data-ttu-id="f8d4b-102">Propiedades de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="f8d4b-102">Path Properties</span></span>
  <span data-ttu-id="f8d4b-103">Los objetos de flujo de datos del [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] modelo de objetos de tienen propiedades comunes y propiedades personalizadas en el nivel del componente, entradas y salidas, y columnas de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-103">The data flow objects in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model have common properties and custom properties at the level of the component, inputs and outputs, and input columns and output columns.</span></span> <span data-ttu-id="f8d4b-104">Muchas propiedades tienen valores de solo lectura que son asignados en tiempo de ejecución por el motor de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-104">Many properties have read-only values that are assigned at run time by the data flow engine.</span></span>  
  
 <span data-ttu-id="f8d4b-105">En este tema se enumeran y describen las propiedades personalizadas de las rutas de acceso que conectan los objetos del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-105">This topic lists and describes the custom properties of the paths that connect data flow objects.</span></span>  
  
## <a name="path-properties"></a><span data-ttu-id="f8d4b-106">Propiedades de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="f8d4b-106">Path Properties</span></span>  
 <span data-ttu-id="f8d4b-107">En el modelo de objetos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], una ruta de acceso que conecta componentes en el flujo de datos implementa la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-107">In the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model, a path that connects components in the data flow implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> interface.</span></span>  
  
 <span data-ttu-id="f8d4b-108">La tabla siguiente describe las propiedades configurables de las rutas de acceso en un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-108">The following table describes the configurable properties of the paths in a data flow.</span></span> <span data-ttu-id="f8d4b-109">El motor de flujo de datos también asigna valores a propiedades de solo lectura adicionales no enumeradas aquí.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-109">The data flow engine also assigns values to additional read-only properties that are not listed here.</span></span>  
  
|<span data-ttu-id="f8d4b-110">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="f8d4b-110">Property name</span></span>|<span data-ttu-id="f8d4b-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f8d4b-111">Data Type</span></span>|<span data-ttu-id="f8d4b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8d4b-112">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="f8d4b-113">PathAnnotation</span><span class="sxs-lookup"><span data-stu-id="f8d4b-113">PathAnnotation</span></span>|<span data-ttu-id="f8d4b-114">Integer (enumeración)</span><span class="sxs-lookup"><span data-stu-id="f8d4b-114">Integer (enumeration)</span></span>|<span data-ttu-id="f8d4b-115">Un valor que indica si una anotación se debería mostrar con la ruta de acceso en el área del diseñador.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-115">A value that indicates whether an annotation should be displayed with the path on the designer surface.</span></span> <span data-ttu-id="f8d4b-116">Los valores posibles son `AsNeeded`, `SourceName`, `PathName` y `Never`.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-116">The possible values are `AsNeeded`, `SourceName`, `PathName`, and `Never`.</span></span> <span data-ttu-id="f8d4b-117">El valor predeterminado es `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-117">The default value is `AsNeeded`.</span></span>|  
|<span data-ttu-id="f8d4b-118">DestinationName</span><span class="sxs-lookup"><span data-stu-id="f8d4b-118">DestinationName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100>|<span data-ttu-id="f8d4b-119">La entrada asociada a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-119">The input associated with the path.</span></span>|  
|<span data-ttu-id="f8d4b-120">SourceName</span><span class="sxs-lookup"><span data-stu-id="f8d4b-120">SourceName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>|<span data-ttu-id="f8d4b-121">La salida asociada a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-121">The output associated with the path.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8d4b-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8d4b-122">See Also</span></span>  
 <span data-ttu-id="f8d4b-123">[Rutas de Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="f8d4b-123">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="f8d4b-124">[Propiedades comunes](../../2014/integration-services/common-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f8d4b-124">[Common Properties](../../2014/integration-services/common-properties.md) </span></span>  
 <span data-ttu-id="f8d4b-125">[Propiedades personalizadas de la transformación](data-flow/transformations/transformation-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f8d4b-125">[Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md) </span></span>  
 [<span data-ttu-id="f8d4b-126">Propiedades de flujo de datos que se pueden establecer utilizando expresiones</span><span class="sxs-lookup"><span data-stu-id="f8d4b-126">Data Flow Properties that Can Be Set by Using Expressions</span></span>](../../2014/integration-services/data-flow-properties-that-can-be-set-by-using-expressions.md)  
  
  
