---
title: 'rsInternalError: error de Reporting Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsInternalError
ms.assetid: 52613d52-fc78-4870-93f0-7d393ab9c335
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 85b88519df810f60c580ad2d6eb355dde236d081
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673454"
---
# <a name="rsinternalerror---reporting-services-error"></a><span data-ttu-id="fee99-102">rsInternalError - Error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fee99-102">rsInternalError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="fee99-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fee99-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fee99-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="fee99-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="fee99-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="fee99-105">Event ID</span></span>|<span data-ttu-id="fee99-106">rsInternalError</span><span class="sxs-lookup"><span data-stu-id="fee99-106">rsInternalError</span></span>|  
|<span data-ttu-id="fee99-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="fee99-107">Event Source</span></span>|<span data-ttu-id="fee99-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="fee99-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="fee99-109">Componente</span><span class="sxs-lookup"><span data-stu-id="fee99-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="fee99-110">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fee99-110">Message Text</span></span>|<span data-ttu-id="fee99-111">Error interno en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fee99-111">An internal error occurred on the report server.</span></span> <span data-ttu-id="fee99-112">Vea el registro de errores para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="fee99-112">See the error log for more details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fee99-113">Explicación</span><span class="sxs-lookup"><span data-stu-id="fee99-113">Explanation</span></span>  
 <span data-ttu-id="fee99-114">Se trata de un mensaje de error genérico que suele ir seguido de un error más descriptivo que proporciona más información.</span><span class="sxs-lookup"><span data-stu-id="fee99-114">This is a generic error message that is often followed by a more descriptive error that provides more detail.</span></span>  
  
 <span data-ttu-id="fee99-115">Los errores internos no son comunes.</span><span class="sxs-lookup"><span data-stu-id="fee99-115">Internal errors are uncommon.</span></span> <span data-ttu-id="fee99-116">Si obtiene este error, puede conseguir más información en los registros de seguimiento del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fee99-116">If you get this error, more information is available in report server trace logs.</span></span> <span data-ttu-id="fee99-117">Además, si está ejecutando como administrador local en el mismo equipo en el que se produjo el error, puede ver la pila de llamadas para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fee99-117">In addition, if you are running as local administrator on the same computer on which the error occurs, you can view the call stack for more information.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fee99-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fee99-118">User Action</span></span>  
 <span data-ttu-id="fee99-119">Para determinar la causa específica de este mensaje, revise los archivos de registro del servidor de informes, que se encuentran en \Microsoft SQL Server\MSRS12. \<instancename > \Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="fee99-119">To determine the specific cause for this message, review the report server log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="fee99-120">Para más información, vea [Archivos de registro y orígenes de Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="fee99-120">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
 <span data-ttu-id="fee99-121">Para ver la pila de llamadas, haga clic con el botón derecho en la página donde se ha producido el error y seleccione **Ver código fuente**.</span><span class="sxs-lookup"><span data-stu-id="fee99-121">To view the call stack, right-click the page on which the error occurs and point to **View Source**.</span></span> <span data-ttu-id="fee99-122">Esta acción requiere tener permisos de administrador para el mismo equipo en que se produce el error.</span><span class="sxs-lookup"><span data-stu-id="fee99-122">Viewing the call stack requires administrator permissions on the same computer on which the error occurs.</span></span>  
  
 <span data-ttu-id="fee99-123">Si no hay información adicional disponible, puede intentar de nuevo la solicitud.</span><span class="sxs-lookup"><span data-stu-id="fee99-123">If there is no additional information available, you can try your request again.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="fee99-124">Solo para uso interno</span><span class="sxs-lookup"><span data-stu-id="fee99-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee99-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fee99-125">See Also</span></span>  
 [<span data-ttu-id="fee99-126">Inicio y detención del servicio del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="fee99-126">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
