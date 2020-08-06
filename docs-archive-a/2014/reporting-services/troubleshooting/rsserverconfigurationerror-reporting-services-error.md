---
title: 'rsServerConfigurationError: error de Reporting Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsServerConfigurationError
ms.assetid: 0913afc2-34b4-4713-b570-cfd5718975ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02f8a18c42715d1f118920614eb425820130dacb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748616"
---
# <a name="rsserverconfigurationerror---reporting-services-error"></a><span data-ttu-id="f2028-102">rsServerConfigurationError - Error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f2028-102">rsServerConfigurationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="f2028-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f2028-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2028-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="f2028-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="f2028-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f2028-105">Event ID</span></span>|<span data-ttu-id="f2028-106">rsServerConfiguration</span><span class="sxs-lookup"><span data-stu-id="f2028-106">rsServerConfiguration</span></span>|  
|<span data-ttu-id="f2028-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="f2028-107">Event Source</span></span>|<span data-ttu-id="f2028-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="f2028-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="f2028-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f2028-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="f2028-110">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f2028-110">Message Text</span></span>|<span data-ttu-id="f2028-111">El servidor de informes ha encontrado un error de configuración.</span><span class="sxs-lookup"><span data-stu-id="f2028-111">The report server has encountered a configuration error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f2028-112">Explicación</span><span class="sxs-lookup"><span data-stu-id="f2028-112">Explanation</span></span>  
 <span data-ttu-id="f2028-113">Este es un error de uso general que se produce cuando el servidor de informes o una herramienta de creación de informes tienen valores de configuración no válidos.</span><span class="sxs-lookup"><span data-stu-id="f2028-113">This is a general purpose error that occurs when either the report server or a report authoring tool has invalid configuration settings.</span></span> <span data-ttu-id="f2028-114">El error suele ir acompañado de un segundo mensaje que indica la causa real del error.</span><span class="sxs-lookup"><span data-stu-id="f2028-114">The error is usually accompanied by a second message that states the actual cause of the error.</span></span>  
  
 <span data-ttu-id="f2028-115">La lista siguiente resume las posibles causas:</span><span class="sxs-lookup"><span data-stu-id="f2028-115">The following list summarizes possible causes:</span></span>  
  
-   <span data-ttu-id="f2028-116">El archivo RSReportServer.config o RSReportDesigner.config no se puede encontrar o leer.</span><span class="sxs-lookup"><span data-stu-id="f2028-116">The RSReportServer.config or RSReportDesigner.config file cannot be found or read.</span></span>  
  
-   <span data-ttu-id="f2028-117">Los elementos XML de cualquier archivo de configuración faltan o no son válidos.</span><span class="sxs-lookup"><span data-stu-id="f2028-117">XML elements in either configuration file are missing or invalid.</span></span>  
  
-   <span data-ttu-id="f2028-118">Los valores de uno o más elementos XML faltan o no son válidos.</span><span class="sxs-lookup"><span data-stu-id="f2028-118">Values for one or more XML elements are missing or invalid.</span></span>  
  
-   <span data-ttu-id="f2028-119">Los parámetros del Registro no son válidos.</span><span class="sxs-lookup"><span data-stu-id="f2028-119">Registry settings are invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f2028-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f2028-120">User Action</span></span>  
 <span data-ttu-id="f2028-121">Si este error empezara a producirse después de editar manualmente un archivo de configuración, quite los cambios efectuados y especifique el valor anterior, o restaure una versión anterior si tiene una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f2028-121">If this error began to occur after you manually edited a configuration file, remove your changes and enter the previous value, or restore a previous version if you have a backup.</span></span>  
  
 <span data-ttu-id="f2028-122">Para revisar la información adicional del mensaje de error que acompaña al `rsServerConfiguration` error, revise los archivos de registro de seguimiento del servidor de informes, que se encuentran en \MICROSOFT SQL Server\MSRS12. \<instancename > \Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="f2028-122">To review additional error message information that accompanies the `rsServerConfiguration` error, review the report server trace log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="f2028-123">Para más información, vea [Archivos de registro y orígenes de Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="f2028-123">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="f2028-124">Solo para uso interno</span><span class="sxs-lookup"><span data-stu-id="f2028-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2028-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2028-125">See Also</span></span>  
 <span data-ttu-id="f2028-126">[Archivos de configuración de Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="f2028-126">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="f2028-127">Modificar un archivo de configuración de Reporting Services &#40;RSreportserver.config&#41;</span><span class="sxs-lookup"><span data-stu-id="f2028-127">Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;</span></span>](../report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md)  
  
  
