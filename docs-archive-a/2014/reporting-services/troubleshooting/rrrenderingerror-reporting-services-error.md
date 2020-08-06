---
title: rrRenderingError - Error de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rrRenderingError
ms.assetid: 0751efc3-b81b-44ee-8aac-8560f86ca322
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b44b042c5f3c0cfdb9ffb99d3f45ed073beb972a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746108"
---
# <a name="rrrenderingerror---reporting-services-error"></a><span data-ttu-id="56c06-102">rrRenderingError - Error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="56c06-102">rrRenderingError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="56c06-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="56c06-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56c06-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="56c06-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="56c06-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="56c06-105">Event ID</span></span>|<span data-ttu-id="56c06-106">rrRenderingError</span><span class="sxs-lookup"><span data-stu-id="56c06-106">rrRenderingError</span></span>|  
|<span data-ttu-id="56c06-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="56c06-107">Event Source</span></span>|<span data-ttu-id="56c06-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span><span class="sxs-lookup"><span data-stu-id="56c06-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span></span>|  
|<span data-ttu-id="56c06-109">Componente</span><span class="sxs-lookup"><span data-stu-id="56c06-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="56c06-110">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="56c06-110">Message Text</span></span>|<span data-ttu-id="56c06-111">Error durante la representación del informe.</span><span class="sxs-lookup"><span data-stu-id="56c06-111">An error occurred during rendering of the report.</span></span> <span data-ttu-id="56c06-112">(rrRenderingError) %1</span><span class="sxs-lookup"><span data-stu-id="56c06-112">(rrRenderingError) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="56c06-113">Explicación</span><span class="sxs-lookup"><span data-stu-id="56c06-113">Explanation</span></span>  
 <span data-ttu-id="56c06-114">Se devuelve este mensaje cuando [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no puede representar ni exportar el informe.</span><span class="sxs-lookup"><span data-stu-id="56c06-114">This message is returned when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] cannot render or export the report.</span></span>  
  
 <span data-ttu-id="56c06-115">Un mensaje que indique que no se admite el tamaño se suele producir cuando el tamaño de página RDL especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="56c06-115">A message that indicates that the size is not supported is typically caused when the specified RDL page size is not valid.</span></span> <span data-ttu-id="56c06-116">Especifique un tamaño de página RDL válido y, a continuación, vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="56c06-116">Specify a valid RDL page size and then try again.</span></span>  
  
 <span data-ttu-id="56c06-117">Un mensaje que indique que no se admite la medida de tamaño RDL se suele producir cuando se especifica un tipo de unidad no admitido.</span><span class="sxs-lookup"><span data-stu-id="56c06-117">A message that indicates that an RDL size measurement is not supported is typically caused when an unsupported unit type is specified.</span></span> <span data-ttu-id="56c06-118">Los tipos de unidad válidos son cm, pda, mm, pc y pt.</span><span class="sxs-lookup"><span data-stu-id="56c06-118">Valid unit types are cm, in, mm, pc, and pt.</span></span> <span data-ttu-id="56c06-119">Especifique un tipo de unidad válido y vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="56c06-119">Specify a valid unit type and then try again.</span></span>  
  
 <span data-ttu-id="56c06-120">Un mensaje que indique que no se admite un tamaño negativo se suele producir cuando se especifica una medida negativa para el tamaño de página, por ejemplo -5 cm.</span><span class="sxs-lookup"><span data-stu-id="56c06-120">A message that indicates that a negative size is not supported is typically caused when a negative measurement for the page size, for example -5 cm, is specified.</span></span> <span data-ttu-id="56c06-121">Especifique un número positivo para el tamaño de página y, a continuación, vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="56c06-121">Specify a positive number for the page size and then try again.</span></span>  
  
 <span data-ttu-id="56c06-122">Un mensaje que indique que se ha especificado un tamaño RDL fuera del intervalo se suele producir cuando una medida para el tamaño de página está fuera del tamaño de margen de página válido.</span><span class="sxs-lookup"><span data-stu-id="56c06-122">A message that indicates that an RDL size is specified out of range is typically caused when a measurement for the page size is outside of the valid page margin size.</span></span> <span data-ttu-id="56c06-123">Especifique una medida para el tamaño de página que esté dentro de los tamaños de margen de página válidos.</span><span class="sxs-lookup"><span data-stu-id="56c06-123">Specify a measurement for the page size that is within the valid page margin sizes.</span></span>  
  
 <span data-ttu-id="56c06-124">Un mensaje que indica que no se admite un color especificado se suele producir cuando el color especificado en el RDL no es válido.</span><span class="sxs-lookup"><span data-stu-id="56c06-124">A message that indicates that a color specified is not supported is typically caused when a color specified in the RDL is not valid.</span></span> <span data-ttu-id="56c06-125">Elija un color admitido por RDL y, a continuación, vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="56c06-125">Choose a color supported by RDL and then try again.</span></span>  
  
 <span data-ttu-id="56c06-126">Un mensaje que indique que la etiqueta de acción solo es opcional cuando se use una acción única y que si se agregan varias acciones se necesitan etiquetas para cada acción se suele producir cuando se especifica una etiqueta de acción y no es válida.</span><span class="sxs-lookup"><span data-stu-id="56c06-126">A message that indicates that the action label is only optional when using a single action and that adding multiple actions requires labels for each action is typically caused when an action label is specified and it is not valid.</span></span> <span data-ttu-id="56c06-127">Especifique una etiqueta de acción válida para cada acción.</span><span class="sxs-lookup"><span data-stu-id="56c06-127">Specify a valid action label for each action.</span></span>  
  
 <span data-ttu-id="56c06-128">Un mensaje que indique que el argumento de estilo debe ser de un tipo específico se suele producir cuando el valor de estilo es incorrecto para el tipo de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="56c06-128">A message that indicates the style argument has to be of a specific type is typically caused when an incorrect style value for the data type is specified.</span></span> <span data-ttu-id="56c06-129">La especificación RDL identifica los tipos válidos que puede utilizar en los valores de estilo de los distintos elementos RDL.</span><span class="sxs-lookup"><span data-stu-id="56c06-129">The RDL specification identifies the valid types that you can use in the style values of different RDL elements.</span></span> <span data-ttu-id="56c06-130">Por ejemplo, un valor de estilo incorrecto para el color de fondo es "2pt" y un valor incorrecto para el alto es "true".</span><span class="sxs-lookup"><span data-stu-id="56c06-130">For example, an incorrect style value for background color is "2pt" and incorrect value for height is "true".</span></span> <span data-ttu-id="56c06-131">Especifique un valor correcto y, a continuación, vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="56c06-131">Specify a correct value and then try again.</span></span>  
  
 <span data-ttu-id="56c06-132">Un mensaje que indique que no se admite el estilo de borde se suele producir cuando el estilo de borde especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="56c06-132">A message that indicates that the border style is not supported is typically caused when the border style specified is not valid.</span></span> <span data-ttu-id="56c06-133">Especifique un estilo de borde admitido y, a continuación, vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="56c06-133">Specify a supported border style and then try again.</span></span>  
  
 <span data-ttu-id="56c06-134">Un mensaje que indique que no se admite el tipo MIME de imagen se suele producir cuando el tipo MIME especificado para un elemento de informe de imagen no es válido.</span><span class="sxs-lookup"><span data-stu-id="56c06-134">A message that indicates that the image mimetype is not supported is typically caused when the specified mimetype for an image report item is not valid.</span></span> <span data-ttu-id="56c06-135">Especifique un tipo MIME admitido para el elemento de informe y, a continuación, vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="56c06-135">Specify a supported mimetype for the report item and then try again.</span></span>  
  
 <span data-ttu-id="56c06-136">Un mensaje que indique que el número de filas supera el número máximo posible de filas por hoja se suele producir cuando se supera el número de filas de una hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="56c06-136">A message that indicates that the number of rows exceeds the maximum possible rows per sheet is typically caused when the number of rows in an Excel worksheet is exceeded.</span></span> <span data-ttu-id="56c06-137">Excel admite un máximo de 65.000 filas.</span><span class="sxs-lookup"><span data-stu-id="56c06-137">Excel supports up to 65,000 rows.</span></span>  
  
 <span data-ttu-id="56c06-138">Un mensaje que indique que el número de columnas supera el número máximo posible de columnas por hoja se suele producir cuando se supera el número de columnas de una hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="56c06-138">A message that indicates that the number of columns exceeds the maximum possible columns per sheet is typically caused when the number of columns in an Excel worksheet is exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="56c06-139">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="56c06-139">User Action</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="56c06-140">Solo para uso interno</span><span class="sxs-lookup"><span data-stu-id="56c06-140">Internal-Only</span></span>  
  
