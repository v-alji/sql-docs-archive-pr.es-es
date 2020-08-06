---
title: Comprobar la ejecución de un informe | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- auditing [Reporting Services]
- verifying report execution
- logs [Reporting Services], verifying report run
- report execution data [Reporting Services]
- status information [Reporting Services]
- report processing [Reporting Services], verifying execution
- checking report execution
ms.assetid: 18a98f2f-6b40-454e-9b37-568ed1a96458
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c11c57f7c5f67b2557f5637ad10658abc9f80606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672609"
---
# <a name="verifying-a-report-run"></a><span data-ttu-id="2c1a3-102">Comprobar la ejecución de un informe</span><span class="sxs-lookup"><span data-stu-id="2c1a3-102">Verifying a Report Run</span></span>
  <span data-ttu-id="2c1a3-103">Para ver información acerca del estado del procesamiento de un informe, puede utilizar los archivos de registro o bien consultar la información de estado que se muestra junto con el informe en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-103">To view information about the status of report processing, you can use log files or refer to status information that is displayed with the report in Report Manager.</span></span>  
  
## <a name="sources-of-report-execution-data"></a><span data-ttu-id="2c1a3-104">Orígenes de datos de ejecución de informes</span><span class="sxs-lookup"><span data-stu-id="2c1a3-104">Sources of Report Execution Data</span></span>  
 <span data-ttu-id="2c1a3-105">Los registros de ejecución de los informes ofrecen información exhaustiva sobre la ejecución del informe, incluido el nombre del informe, el nombre del usuario que llevó a cabo la ejecución, la hora de ejecución y la extensión de entrega utilizada para distribuir el informe.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-105">The report execution logs provide comprehensive information about report execution, including the name of the report, the name of the user who ran the report, report execution time, and the delivery extension used to distribute the report.</span></span> <span data-ttu-id="2c1a3-106">Para ver y analizar estos datos, puede copiar el registro de ejecución del informe en tablas de base de datos, donde resulta muy sencillo consultar y estudiar los datos.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-106">To view and analyze this data, you can copy the report execution log into database tables that are easy to query and report on.</span></span>  
  
 <span data-ttu-id="2c1a3-107">Los archivos de registro contienen muchas entradas sobre la ejecución del informe y otras actividades del servidor.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-107">Log files contain many entries about report execution and other server activity.</span></span> <span data-ttu-id="2c1a3-108">Debido a la gran cantidad de datos que incluyen, quizás desee utilizar el Administrador de informes si solamente desea comprobar la última vez que se ejecutó el informe.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-108">Because log files contain so much data, you may want to use Report Manager if you only want to verify when the report last ran.</span></span> <span data-ttu-id="2c1a3-109">Si desea consultar información adicional, deberá utilizar los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-109">If you require additional information, you must view the log files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c1a3-110">El Administrador de informes no muestra las horas de procesamiento de los informes ejecutados a petición.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-110">Report Manager does not show the processing times of reports that run on demand.</span></span>  
  
 <span data-ttu-id="2c1a3-111">En la siguiente tabla se describe cómo ver la fecha y la hora de procesamiento de distintos tipos de informes.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-111">The following table describes how to view the processing date and time for various types of reports.</span></span>  
  
|<span data-ttu-id="2c1a3-112">Para este tipo de informe</span><span class="sxs-lookup"><span data-stu-id="2c1a3-112">For this type of report</span></span>|<span data-ttu-id="2c1a3-113">La información de fecha y hora se halla en</span><span class="sxs-lookup"><span data-stu-id="2c1a3-113">Date and time information is located here</span></span>|<span data-ttu-id="2c1a3-114">Para ver la información, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="2c1a3-114">To view the information, do the following</span></span>|  
|-----------------------------|-----------------------------------------------|-----------------------------------------------|  
|<span data-ttu-id="2c1a3-115">Un informe que se ejecuta como una instantánea de informe.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-115">A report that runs as a report snapshot.</span></span>|<span data-ttu-id="2c1a3-116">En la página Contenido.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-116">On the Contents page.</span></span> <span data-ttu-id="2c1a3-117">Para más información, vea [Contenido &#40;página del Administrador de informes&#41;](../contents-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2c1a3-117">For more information, see [Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md).</span></span>|<span data-ttu-id="2c1a3-118">1) Vaya a la carpeta que contiene el informe.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-118">1) Locate the folder that contains the report.</span></span><br /><span data-ttu-id="2c1a3-119">2) Establezca la carpeta en la vista Detalles.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-119">2) Set the folder in Details view.</span></span><br /><span data-ttu-id="2c1a3-120">3) 3) Anote la fecha y la hora de la columna **When Run** .</span><span class="sxs-lookup"><span data-stu-id="2c1a3-120">3) 3) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="2c1a3-121">Una instantánea del historial del informe.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-121">A snapshot in report history.</span></span>|<span data-ttu-id="2c1a3-122">En la página de propiedades Historial.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-122">On the History Properties page.</span></span> <span data-ttu-id="2c1a3-123">Para más información, vea [Página de propiedades de opciones de instantánea &#40;Administrador de informes&#41;](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2c1a3-123">For more information, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>|<span data-ttu-id="2c1a3-124">1) Abra el informe.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-124">1) Open the report.</span></span><br /><span data-ttu-id="2c1a3-125">2) Haga clic en la página **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="2c1a3-125">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="2c1a3-126">3) Haga clic en la pestaña **Historial** .</span><span class="sxs-lookup"><span data-stu-id="2c1a3-126">3) Click the **History** tab.</span></span><br /><span data-ttu-id="2c1a3-127">4) Anote la fecha y hora indicadas en la columna **When Run** (Cuándo se ejecuta).</span><span class="sxs-lookup"><span data-stu-id="2c1a3-127">4) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="2c1a3-128">Un informe en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-128">A cached report.</span></span>|<span data-ttu-id="2c1a3-129">En la programación utilizada para crear y actualizar el informe en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-129">In the schedule used to create and refresh the cached report.</span></span>|<span data-ttu-id="2c1a3-130">1) Abra el informe.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-130">1) Open the report.</span></span><br /><span data-ttu-id="2c1a3-131">2) Haga clic en la página **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="2c1a3-131">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="2c1a3-132">3) Haga clic en la pestaña **Ejecución** .</span><span class="sxs-lookup"><span data-stu-id="2c1a3-132">3) Click the **Execution** tab.</span></span><br /><span data-ttu-id="2c1a3-133">4) Abra la programación.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-133">4) Open the schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c1a3-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c1a3-134">See Also</span></span>  
 <span data-ttu-id="2c1a3-135">[Archivos de registro y orígenes de Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="2c1a3-135">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="2c1a3-136">[Establecer las propiedades del procesamiento de informes](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2c1a3-136">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="2c1a3-137">Administrador de informes &#40;Modo nativo de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2c1a3-137">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
