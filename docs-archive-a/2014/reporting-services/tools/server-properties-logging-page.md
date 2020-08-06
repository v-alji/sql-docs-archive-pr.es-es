---
title: Propiedades del servidor (página Registro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.logging.f1
ms.assetid: b338deab-4868-4951-9f22-0605add2fc95
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a04c27fd790a1ad5c4ba453b43af5983a6440e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674007"
---
# <a name="server-properties-logging-page"></a><span data-ttu-id="7f6ec-102">Propiedades del servidor (página Registro)</span><span class="sxs-lookup"><span data-stu-id="7f6ec-102">Server Properties (Logging Page)</span></span>
  <span data-ttu-id="7f6ec-103">Utilice esta página para establecer límites en los datos de ejecución de informes que recoge un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7f6ec-103">Use this page to set limits on the report execution data that is collected by a report server.</span></span> <span data-ttu-id="7f6ec-104">Los datos de ejecución se almacenan internamente en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7f6ec-104">Execution data is stored internally in the report server database.</span></span> <span data-ttu-id="7f6ec-105">Puede realizar el seguimiento de la actividad de informe para el servidor de informes que se ejecuta en modo nativo o en modo integrado con SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7f6ec-105">You can track report activity for report server that runs in native mode or SharePoint integrated mode.</span></span> <span data-ttu-id="7f6ec-106">Si el servidor de informes forma parte de una implementación escalada, el registro de ejecución de informes mantiene un registro de toda la actividad de informe para la implementación completa en un archivo de registro único.</span><span class="sxs-lookup"><span data-stu-id="7f6ec-106">If the report server is part of a scale-out deployment, the report execution log maintains a record of all report activity for the entire deployment in a single log file.</span></span>  
  
 <span data-ttu-id="7f6ec-107">Para abrir esta página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a un servidor de informes, haga clic con el botón secundario en el nombre del servidor de informes y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7f6ec-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="7f6ec-108">Haga clic en **Registro** para abrir esta página.</span><span class="sxs-lookup"><span data-stu-id="7f6ec-108">Click **Logging** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f6ec-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="7f6ec-109">Options</span></span>  
 <span data-ttu-id="7f6ec-110">**Habilitar el registro de la ejecución de informes**</span><span class="sxs-lookup"><span data-stu-id="7f6ec-110">**Enable report execution logging**</span></span>  
 <span data-ttu-id="7f6ec-111">Haga clic para crear y almacenar información sobre la actividad de informe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="7f6ec-111">Click to create and store information about report activity on the server.</span></span> <span data-ttu-id="7f6ec-112">Si esta opción está habilitada, el servidor de informes realizará un seguimiento sobre qué informes se usan, la frecuencia del procesamiento de informes, el tipo de operación de informe que se realizó, el formato de salida y quién ejecutó el informe.</span><span class="sxs-lookup"><span data-stu-id="7f6ec-112">If this option is enabled, the report server will track which reports are used, the frequency of report processing, the type of report operation that was performed, the output format, and who ran the report.</span></span> <span data-ttu-id="7f6ec-113">Para obtener más información sobre los puntos de datos adicionales que se capturan en el registro, vea [registro de ejecución del servidor de informes y la vista ExecutionLog3](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="7f6ec-113">For more information about additional data points that are captured in the log, see [Report Server Execution Log and the ExecutionLog3 View](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
 <span data-ttu-id="7f6ec-114">**Quitar entradas de registro anteriores a este número de días**</span><span class="sxs-lookup"><span data-stu-id="7f6ec-114">**Remove log entries older than this number of days**</span></span>  
 <span data-ttu-id="7f6ec-115">Permite especificar el número de días después del cual se eliminarán las entradas de registro del registro de la ejecución de informes.</span><span class="sxs-lookup"><span data-stu-id="7f6ec-115">Specify the number of days after which log entries will be trimmed from the report execution log.</span></span> <span data-ttu-id="7f6ec-116">El valor predeterminado es 60 días.</span><span class="sxs-lookup"><span data-stu-id="7f6ec-116">The default value is 60 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f6ec-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f6ec-117">See Also</span></span>  
 <span data-ttu-id="7f6ec-118">[Establecer las propiedades del servidor de informes &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7f6ec-118">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="7f6ec-119">[Conectarse a un servidor de informes en Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7f6ec-119">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="7f6ec-120">[Archivos de registro y orígenes de Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="7f6ec-120">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="7f6ec-121">[Servidor de informes en Management Studio ayuda de F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="7f6ec-121">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="7f6ec-122">Registro de ejecución del servidor de informes y la vista ExecutionLog3</span><span class="sxs-lookup"><span data-stu-id="7f6ec-122">Report Server Execution Log and the ExecutionLog3 View</span></span>](../report-server/report-server-executionlog-and-the-executionlog3-view.md)  
  
  
