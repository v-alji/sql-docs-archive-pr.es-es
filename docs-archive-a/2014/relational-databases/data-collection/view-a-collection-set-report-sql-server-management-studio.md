---
title: Ver un informe de conjunto de recopilación (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.reporthistory.calendar.f1
helpviewer_keywords:
- collection sets [SQL Server], viewing reports
- reports [SQL Server], viewing collection set
ms.assetid: c3b1e791-9aa1-4bba-9622-4954568e1820
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb8755c67e6c03bb318fdb86d703f6d647d5a3eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676006"
---
# <a name="view-a-collection-set-report-sql-server-management-studio"></a><span data-ttu-id="2c4ee-102">Ver un informe de conjunto de recopilación (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2c4ee-102">View a Collection Set Report (SQL Server Management Studio)</span></span>
  <span data-ttu-id="2c4ee-103">Después de haber configurado el almacén de administración de datos, puede ver un informe de conjunto de recopilación en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c4ee-103">After you have configured the management data warehouse, you can view a collection set report in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2c4ee-104">Se proporcionan informes para los conjuntos de recopilación de datos del sistema que se instalan durante el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-104">Reports are provided for the System Data collection sets that are installed during Setup.</span></span> <span data-ttu-id="2c4ee-105">Entre otros, se incluyen los siguientes informes:</span><span class="sxs-lookup"><span data-stu-id="2c4ee-105">The reports include the following:</span></span>  
  
-   <span data-ttu-id="2c4ee-106">Resumen de uso de disco</span><span class="sxs-lookup"><span data-stu-id="2c4ee-106">Disk Usage Summary</span></span>  
  
-   <span data-ttu-id="2c4ee-107">Historial de estadísticas de consultas</span><span class="sxs-lookup"><span data-stu-id="2c4ee-107">Query Statistics History</span></span>  
  
-   <span data-ttu-id="2c4ee-108">Historial de actividad del servidor</span><span class="sxs-lookup"><span data-stu-id="2c4ee-108">Server Activity History</span></span>  
  
 <span data-ttu-id="2c4ee-109">En este procedimiento se muestra el informe para el conjunto de recopilación **Uso de disco** .</span><span class="sxs-lookup"><span data-stu-id="2c4ee-109">This procedure displays the report for the **Disk Usage** collection set.</span></span> <span data-ttu-id="2c4ee-110">Puede seguir el mismo procedimiento general para ver los informes de los demás conjuntos de recopilación de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-110">You can follow the same general procedure to view the reports for the other System Data collection sets.</span></span>  
  
### <a name="to-view-a-collection-set-report"></a><span data-ttu-id="2c4ee-111">Para ver un informe de conjunto de recopilación</span><span class="sxs-lookup"><span data-stu-id="2c4ee-111">To view a collection set report</span></span>  
  
1.  <span data-ttu-id="2c4ee-112">Las tablas para un informe se crean la primera vez que se cargan los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-112">The tables for a report are created the first time that the collected data is uploaded.</span></span> <span data-ttu-id="2c4ee-113">Si intenta ver un informe antes de esta primera carga, se produce un error y no se muestra ningún informe.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-113">If you try to view a report before this first upload, an error occurs and no report is displayed.</span></span> <span data-ttu-id="2c4ee-114">Para cargar los datos para el conjunto de recopilación Uso de disco, en Explorador de objetos, expanda la carpeta **Administración** , expanda **Recopilación de datos**y **Conjuntos de recopilación de datos del sistema**, haga clic con el botón derecho en el conjunto de recopilación **Uso de disco** y, después, haga clic en **Recopilar y cargar ahora**.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-114">To upload data for the Disk Usage collection set, in Object Explorer, expand the **Management** folder, expand **Data Collection**, expand **System Data Collection Sets**, right-click the **Disk Usage** collection set, and then click **Collect and Upload Now**.</span></span>  
  
2.  <span data-ttu-id="2c4ee-115">Para ver el informe, en el Explorador de objetos, expanda la carpeta **Administración** , haga clic con el botón derecho en **Recopilación de datos**, seleccione **Informes**, **Almacén de administración de datos**y, después, haga clic en **Resumen de uso de disco**.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-115">To view the report, in Object Explorer, expand the **Management** folder, right-click **Data Collection**, point to **Reports**, point to **Management Data Warehouse**, and then click **Disk Usage Summary**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2c4ee-116">Algunos informes pueden mostrar un botón de calendario en la escala de tiempo de la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-116">Some reports might display a calendar button under the data collection timeline.</span></span> <span data-ttu-id="2c4ee-117">Haga clic en este botón para acceder a **Calendario de informe de recopilación de datos**.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-117">Click this button to access the **Data Collection Report Calendar**.</span></span>  
  
#### <a name="data-collection-report-calendar"></a><span data-ttu-id="2c4ee-118">Calendario de informe de recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="2c4ee-118">Data Collection Report Calendar</span></span>  
 <span data-ttu-id="2c4ee-119">Utilice este cuadro de diálogo para especificar la fecha de inicio, hora de inicio y duración de los datos que desea notificar.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-119">Use this dialog box to specify the start date, start time, and duration of the data that you want to report on.</span></span> <span data-ttu-id="2c4ee-120">Por ejemplo, puede desear notificar la actividad de uso del disco de un servidor durante un período de 12 horas concreto del último miércoles.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-120">For example, you may want to report on the disk usage activity of a server for a specific 12-hour period last Wednesday.</span></span>  
  
 <span data-ttu-id="2c4ee-121">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="2c4ee-121">**Start date**</span></span>  
 <span data-ttu-id="2c4ee-122">Escriba una fecha de inicio para los datos del informe o seleccione una en el calendario.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-122">Enter a beginning date for the report data, or select one from the calendar.</span></span>  
  
 <span data-ttu-id="2c4ee-123">**Hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="2c4ee-123">**Start time**</span></span>  
 <span data-ttu-id="2c4ee-124">Escriba una hora inicial para los datos del informe o especifique una haciendo clic en las flechas.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-124">Enter a beginning time for the report data or specify one by clicking the arrows.</span></span>  
  
 <span data-ttu-id="2c4ee-125">**Duration**</span><span class="sxs-lookup"><span data-stu-id="2c4ee-125">**Duration**</span></span>  
 <span data-ttu-id="2c4ee-126">Especifique el intervalo de tiempo que incluir en el informe.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-126">Specify the time range to include in the report.</span></span> <span data-ttu-id="2c4ee-127">El valor predeterminado es de 240 minutos.</span><span class="sxs-lookup"><span data-stu-id="2c4ee-127">The default value is 240 minutes.</span></span> <span data-ttu-id="2c4ee-128">Los valores posibles entre los que seleccionar son 15 minutos, 60 minutos, 240 minutos (4 horas), 720 minutos (12 horas) y 1440 minutos (24 horas).</span><span class="sxs-lookup"><span data-stu-id="2c4ee-128">The possible values to select from are 15 minutes, 60 minutes, 240 minutes (4 hours), 720 minutes (12 hours), and 1440 minutes (24 hours).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c4ee-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c4ee-129">See Also</span></span>  
 <span data-ttu-id="2c4ee-130">[Recopilación de datos](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="2c4ee-130">[Data Collection](data-collection.md) </span></span>  
 <span data-ttu-id="2c4ee-131">[Informes personalizados en Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="2c4ee-131">[Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span></span>  
 [<span data-ttu-id="2c4ee-132">Configurar el almacén de administración de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2c4ee-132">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
