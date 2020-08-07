---
title: 'Los servicios de Excel no admiten las siguientes características y es posible que no se muestren o se muestren solo parcialmente: comentarios, formas u otros objetos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ade92e15-dfbf-496b-9378-a00bd83ba750
author: minewiskan
ms.author: owend
ms.openlocfilehash: 67c2989ab89f242fdce2ca64f3c2f361e17d49ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746000"
---
# <a name="the-following-features-are-not-supported-by-excel-services-and-may-not-display-or-may-display-only-partially-comments-shapes-or-other-objects"></a><span data-ttu-id="23419-102">Las siguientes características no se admiten en Servicios de Excel y puede que no se muestren o que se muestren solo parcialmente: comentarios, formas u otros objetos</span><span class="sxs-lookup"><span data-stu-id="23419-102">The following features are not supported by Excel Services and may not display or may display only partially: Comments, Shapes, or other objects</span></span>
  <span data-ttu-id="23419-103">Este error se produce al agregar segmentaciones a un libro PowerPivot desde una lista de campos de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="23419-103">This error occurs when you add Slicers to a PowerPivot workbook from a PowerPivot Field List.</span></span>  
  
## <a name="details"></a><span data-ttu-id="23419-104">Detalles</span><span class="sxs-lookup"><span data-stu-id="23419-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23419-105">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="23419-105">Applies to</span></span>|<span data-ttu-id="23419-106">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="23419-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="23419-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="23419-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="23419-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23419-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="23419-109">Causa</span><span class="sxs-lookup"><span data-stu-id="23419-109">Cause</span></span>|<span data-ttu-id="23419-110">Excel Web Access no puede representar el objeto Forma que se usa para controlar la posición y el formato de las segmentaciones agregadas a un libro de la lista de campos de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="23419-110">Excel Web Access cannot render the Shape object used to control positioning and formatting of Slicers added to a workbook from the PowerPivot Field List.</span></span>|  
|<span data-ttu-id="23419-111">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="23419-111">Message Text</span></span>|<span data-ttu-id="23419-112">Servicios de Excel no admite las siguientes características y puede que no se muestren o se muestren solo parcialmente:</span><span class="sxs-lookup"><span data-stu-id="23419-112">The following features are not supported by Excel Services and may not display or may display only partially:</span></span><br /><br /> <span data-ttu-id="23419-113">Comentarios, formas o otros objetos</span><span class="sxs-lookup"><span data-stu-id="23419-113">Comments, Shapes, or other objects</span></span><br /><br /> <span data-ttu-id="23419-114">Algunas características, como las consultas de datos externos, muestran datos en caché que solo pueden actualizarse en Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="23419-114">Some features, such as external data queries, display cached data which can only be refreshed in Microsoft Excel.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="23419-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="23419-115">Explanation</span></span>  
 <span data-ttu-id="23419-116">Excel Web Access muestra este error al abrir un libro PowerPivot en un explorador y hacer clic en el botón **detalles** del mensaje, **es posible que no se muestren las características no admitidas de este libro como se pretende**.</span><span class="sxs-lookup"><span data-stu-id="23419-116">Excel Web Access shows this error when you open a PowerPivot workbook in a browser and you click the **Details** button for the message, **Unsupported Features This workbook may not display as intended**.</span></span>  
  
 <span data-ttu-id="23419-117">Este error se produce porque el libro PowerPivot contiene segmentaciones cuyo diseño es controlado por un objeto Forma oculto en Excel.</span><span class="sxs-lookup"><span data-stu-id="23419-117">This error occurs because the PowerPivot workbook contains Slicers whose layout is controlled by a hidden Shape object in Excel.</span></span> <span data-ttu-id="23419-118">El objeto Forma controla el formato y la posición de las segmentaciones en la posición horizontal y vertical.</span><span class="sxs-lookup"><span data-stu-id="23419-118">The Shape object controls the formatting and positioning of the Slicers in horizontal and vertical placements.</span></span>  
  
 <span data-ttu-id="23419-119">Servicios de Excel no puede representar un objeto Forma, pero dado que el objeto está oculto, este hecho no constituye un problema.</span><span class="sxs-lookup"><span data-stu-id="23419-119">Excel Services cannot render a Shape object, but because the object is hidden, the fact that it does not render is not an issue.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="23419-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="23419-120">User Action</span></span>  
 <span data-ttu-id="23419-121">Se puede omitir este error.</span><span class="sxs-lookup"><span data-stu-id="23419-121">This error can be ignored.</span></span> <span data-ttu-id="23419-122">Haga clic en **Aceptar** para cerrar el mensaje de error y continuar utilizar el libro y las segmentaciones sin problema.</span><span class="sxs-lookup"><span data-stu-id="23419-122">Click **OK** to close the error message and proceed to use the workbook and Slicers with no problem.</span></span>  
  
  
