---
title: Causa y resolución de errores de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- messages [Reporting Services]
- errors [Reporting Services]
- troubleshooting [Reporting Services], errors
ms.assetid: 3db0fef3-37f8-40d0-acc7-1928760dc0e9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa98b9f760485b80f4fa4ac74f3b8008dc3bbec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746112"
---
# <a name="cause-and-resolution-of-reporting-services-errors"></a><span data-ttu-id="c6640-102">Causa y resolución de errores de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c6640-102">Cause and Resolution of Reporting Services Errors</span></span>
  <span data-ttu-id="c6640-103">Este tema incluye información sobre la causa y la resolución de una serie de errores relacionados con [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6640-103">This topic contains cause and resolution information for a number of errors related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="c6640-104">Los temas sobre mensajes de error de esta sección proporcionan una explicación del mensaje de error, las posibles causas y las medidas que se pueden tomar para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="c6640-104">The error message topics in this section provide an explanation of the error message, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6640-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c6640-105">In This Section</span></span>  
  
|<span data-ttu-id="c6640-106">Error</span><span class="sxs-lookup"><span data-stu-id="c6640-106">Error</span></span>|<span data-ttu-id="c6640-107">Message</span><span class="sxs-lookup"><span data-stu-id="c6640-107">Message</span></span>|  
|-----------|-------------|  
|[<span data-ttu-id="c6640-108">rsAccessedDenied: error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c6640-108">rsAccessedDenied - Reporting Services Error</span></span>](rsaccesseddenied-reporting-services-error.md)|<span data-ttu-id="c6640-109">Los permisos otorgados al usuario 'miDominio\miCuenta' son insuficientes para realizar esta operación.</span><span class="sxs-lookup"><span data-stu-id="c6640-109">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="c6640-110">(rsAccessDenied) (ReportingServicesLibrary).</span><span class="sxs-lookup"><span data-stu-id="c6640-110">(rsAccessDenied) (ReportingServicesLibrary).</span></span>|  
|[<span data-ttu-id="c6640-111">rsInternalError: error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c6640-111">rsInternalError - Reporting Services Error</span></span>](rsinternalerror-reporting-services-error.md)|<span data-ttu-id="c6640-112">Error interno en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c6640-112">An internal error occurred on the report server.</span></span> <span data-ttu-id="c6640-113">Vea el registro de errores para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="c6640-113">See the error log for more details.</span></span>|  
|[<span data-ttu-id="c6640-114">rsModelGenerationError: error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c6640-114">rsModelGenerationError - Reporting Services Error</span></span>](rsmodelgenerationerror-reporting-services-error.md)|<span data-ttu-id="c6640-115">Error al generar el modelo.</span><span class="sxs-lookup"><span data-stu-id="c6640-115">An error occurred while generating model.</span></span> <span data-ttu-id="c6640-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span><span class="sxs-lookup"><span data-stu-id="c6640-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span></span>|  
|[<span data-ttu-id="c6640-117">rsProcessingError: error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c6640-117">rsProcessingError - Reporting Services Error</span></span>](rsprocessingerror-reporting-services-error.md)|<span data-ttu-id="c6640-118">Error al procesar el informe.</span><span class="sxs-lookup"><span data-stu-id="c6640-118">Errors have occurred in report processing.</span></span>|  
|[<span data-ttu-id="c6640-119">rsServerConfigurationError: error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c6640-119">rsServerConfigurationError - Reporting Services Error</span></span>](rsserverconfigurationerror-reporting-services-error.md)|<span data-ttu-id="c6640-120">El servidor de informes ha encontrado un error de configuración.</span><span class="sxs-lookup"><span data-stu-id="c6640-120">The report server has encountered a configuration error.</span></span>|  
|[<span data-ttu-id="c6640-121">rrRenderingError: error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c6640-121">rrRenderingError - Reporting Services Error</span></span>](rrrenderingerror-reporting-services-error.md)|<span data-ttu-id="c6640-122">Error durante la representación del informe.</span><span class="sxs-lookup"><span data-stu-id="c6640-122">An error occurred during rendering of the report.</span></span> <span data-ttu-id="c6640-123">(rrRenderingError) %1.</span><span class="sxs-lookup"><span data-stu-id="c6640-123">(rrRenderingError) %1.</span></span>|  
|[<span data-ttu-id="c6640-124">Servicio Servidor de informes de Windows &#40;MSSQLServer&#41; 107</span><span class="sxs-lookup"><span data-stu-id="c6640-124">Report Server Windows Service &#40;MSSQLServer&#41; 107</span></span>](../../relational-databases/errors-events/mssqlserver-107-database-engine-error.md)|<span data-ttu-id="c6640-125">El servicio Servidor de informes de Windows (MSSQLSERVER) no se puede conectar a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c6640-125">Report Server Windows service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6640-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6640-126">See Also</span></span>  
 <span data-ttu-id="c6640-127">[Archivos de registro y orígenes de Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="c6640-127">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="c6640-128">Referencia de errores y eventos &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c6640-128">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](errors-and-events-reference-reporting-services.md)  
  
  
