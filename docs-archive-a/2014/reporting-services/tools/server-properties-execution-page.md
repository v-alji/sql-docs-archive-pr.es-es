---
title: Propiedades del servidor (página Ejecución) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.execution.f1
ms.assetid: 53b77db1-b013-4dac-82dd-30c0de276639
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ec8725a0cec9e15cb6d8402f8d654320c38471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674008"
---
# <a name="server-properties-execution-page"></a><span data-ttu-id="b5622-102">Propiedades del servidor (página Ejecución)</span><span class="sxs-lookup"><span data-stu-id="b5622-102">Server Properties (Execution Page)</span></span>
  <span data-ttu-id="b5622-103">Utilice esta página para establecer un valor de tiempo de espera para la ejecución de informes.</span><span class="sxs-lookup"><span data-stu-id="b5622-103">Use this page to set a timeout value for report execution.</span></span> <span data-ttu-id="b5622-104">Este valor se aplica a todos los informes que se procesan mediante la instancia del servidor de informes actual.</span><span class="sxs-lookup"><span data-stu-id="b5622-104">This value applies to all reports that are processed by the current report server instance.</span></span> <span data-ttu-id="b5622-105">Puede sobrescribir este valor para informes individuales.</span><span class="sxs-lookup"><span data-stu-id="b5622-105">You can override this value for individual reports.</span></span> <span data-ttu-id="b5622-106">El valor que especifica debe alojar todo el procesamiento de informes que se produce en el servidor de informes, más el procesamiento de consultas realizado en el servidor de bases de datos cuando el servidor de informes recupera datos que se usan en el informe.</span><span class="sxs-lookup"><span data-stu-id="b5622-106">The value you specify must accommodate all report processing that occurs on the report server, plus query processing performed on the database server when the report server retrieves data that is used in the report.</span></span>  
  
 <span data-ttu-id="b5622-107">Para abrir esta página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a una instancia del servidor de informes, haga clic con el botón derecho en el nombre del servidor de informes y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b5622-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="b5622-108">Haga clic en **Ejecución** para abrir esta página.</span><span class="sxs-lookup"><span data-stu-id="b5622-108">Click **Execution** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b5622-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="b5622-109">Options</span></span>  
 <span data-ttu-id="b5622-110">**No establecer tiempo de espera para la ejecución de informes**</span><span class="sxs-lookup"><span data-stu-id="b5622-110">**Do not timeout report execution**</span></span>  
 <span data-ttu-id="b5622-111">Permite a un servidor de informes tiempo ilimitado para completar el procesamiento de informes.</span><span class="sxs-lookup"><span data-stu-id="b5622-111">Allow a report server unlimited time to complete report processing.</span></span>  
  
 <span data-ttu-id="b5622-112">**Limitar la ejecución de informes al siguiente número de segundos**</span><span class="sxs-lookup"><span data-stu-id="b5622-112">**Limit report execution to the following number of seconds**</span></span>  
 <span data-ttu-id="b5622-113">Establezca una restricción horaria en la ejecución de informes.</span><span class="sxs-lookup"><span data-stu-id="b5622-113">Set a time constraint on report execution.</span></span> <span data-ttu-id="b5622-114">El período de tiempo empieza cuando se solicita el informe.</span><span class="sxs-lookup"><span data-stu-id="b5622-114">The time period starts when the report is requested.</span></span> <span data-ttu-id="b5622-115">Si el período finaliza antes de que el informe se haya procesado completamente, el servidor de informes cancela el proceso y todas las consultas en proceso para orígenes de datos externos.</span><span class="sxs-lookup"><span data-stu-id="b5622-115">If the time period ends before the report is fully processed, the report server cancels the process and any in-process queries to external data sources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5622-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5622-116">See Also</span></span>  
 <span data-ttu-id="b5622-117">[Establecer las propiedades del servidor de informes &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b5622-117">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="b5622-118">[Conectar con un servidor de informes en Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b5622-118">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="b5622-119">[Establecer las propiedades del procesamiento de informes](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b5622-119">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="b5622-120">[Establecer valores de tiempo de espera para el procesamiento de informes y conjuntos de datos compartidos &#40;SSRS&#41;](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b5622-120">[Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span></span>  
 [<span data-ttu-id="b5622-121">Servidor de informes en Management Studio (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="b5622-121">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
