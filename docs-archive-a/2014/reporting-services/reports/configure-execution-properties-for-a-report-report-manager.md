---
title: Configurar las propiedades de ejecución de un informe (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- reports [Reporting Services], properties
- reports [Reporting Services], execution options
ms.assetid: 73cc8dcc-ef80-40d7-9739-d33bba0eb28a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51cd7b5db225b39f5a061ed750b2ef5cdd265b9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678049"
---
# <a name="configure-execution-properties-for-a-report--report-manager"></a><span data-ttu-id="94923-102">Configurar las propiedades de ejecución de un informe (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="94923-102">Configure Execution Properties for a Report  (Report Manager)</span></span>
  <span data-ttu-id="94923-103">Puede establecer las opciones de procesamiento de informes para especificar cuándo se recuperan los datos para un informe.</span><span class="sxs-lookup"><span data-stu-id="94923-103">You can set report processing options to specify when data is retrieved for a report.</span></span> <span data-ttu-id="94923-104">Resulta útil programar el procesamiento de datos para un informe si el origen de datos externo se actualiza en momentos concretos (por ejemplo, un almacenamiento de datos que se actualiza diariamente o semanalmente) y desea evitar la sobrecarga de recuperar los mismos datos cada vez que se solicita un informe.</span><span class="sxs-lookup"><span data-stu-id="94923-104">It is useful to schedule data processing for a report if the external data source is refreshed at specific times (for example, a data warehouse that is refreshed daily or weekly) and you want to avoid the overhead of retrieving the same data each time a report is requested.</span></span> <span data-ttu-id="94923-105">La programación del procesamiento de datos también resulta útil si desea controlar la carga del procesamiento en el servidor de bases de datos externo o si desea proporcionar resultados coherentes para varios usuarios que deben trabajar con conjuntos idénticos de datos.</span><span class="sxs-lookup"><span data-stu-id="94923-105">Scheduling data processing is also useful if you want to control the processing load on the external database server or when you want to provide consistent results for multiple users who must work with identical sets of data.</span></span> <span data-ttu-id="94923-106">Si los datos no son estables, un informe a petición puede producir resultados diferentes en pocos minutos.</span><span class="sxs-lookup"><span data-stu-id="94923-106">With volatile data, an on-demand report can produce different results from one minute to the next.</span></span> <span data-ttu-id="94923-107">Por el contrario, una instantánea de informe permite hacer comparaciones válidas con otros informes o herramientas de análisis que tengan los datos existentes en el mismo instante.</span><span class="sxs-lookup"><span data-stu-id="94923-107">A report snapshot, by contrast, allows you to make valid comparisons against other reports or analytical tools that contain data from the same point in time.</span></span>  
  
 <span data-ttu-id="94923-108">Una instantánea de informe es un informe que contiene instrucciones de diseño y resultados de consultas que se recuperaron en un momento concreto.</span><span class="sxs-lookup"><span data-stu-id="94923-108">A report snapshot is a report that contains layout instructions and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="94923-109">A diferencia de los informes a petición, que obtienen resultados de consulta actualizados cuando se seleccionan, las instantáneas de informe se procesan según una programación y luego se guardan en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="94923-109">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="94923-110">Al seleccionar una instantánea de informe para su visualización, el servidor de informes recupera el informe almacenado en la base de datos del servidor de informes y muestra los datos y el diseño actualizados para el informe en el momento en que se creó la instantánea.</span><span class="sxs-lookup"><span data-stu-id="94923-110">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
 <span data-ttu-id="94923-111">Las instantáneas de informe no se guardan con un formato de representación concreto.</span><span class="sxs-lookup"><span data-stu-id="94923-111">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="94923-112">En su lugar, las instantáneas de informe se representan en un formato de visualización final (como HTML) solo cuando un usuario o una aplicación lo solicita.</span><span class="sxs-lookup"><span data-stu-id="94923-112">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="94923-113">La representación aplazada hace que las instantáneas sean portátiles.</span><span class="sxs-lookup"><span data-stu-id="94923-113">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="94923-114">El informe se puede representar con el formato correcto para el dispositivo o explorador web que lo solicita.</span><span class="sxs-lookup"><span data-stu-id="94923-114">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
### <a name="to-configure-report-processing-options"></a><span data-ttu-id="94923-115">Para configurar las opciones de procesamiento de informe</span><span class="sxs-lookup"><span data-stu-id="94923-115">To configure report processing options</span></span>  
  
1.  <span data-ttu-id="94923-116">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="94923-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="94923-117">Navegue hasta el informe para el que desea establecer las opciones de procesamiento y ábralo.</span><span class="sxs-lookup"><span data-stu-id="94923-117">Navigate to and open the report for which you want to set processing options.</span></span>  
  
 <span data-ttu-id="94923-118">Mantenga el mouse sobre el informe y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="94923-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
1.  <span data-ttu-id="94923-119">En el menú desplegable, haga clic en **Administrar** y, después, seleccione la pestaña **Opciones de procesamiento** .</span><span class="sxs-lookup"><span data-stu-id="94923-119">In the drop-down menu, click **Manage** and then select the **Processing Options** tab.</span></span>  
  
2.  <span data-ttu-id="94923-120">Haga clic en **Representar este informe a partir de una instantánea de ejecución y seleccione una de las opciones siguientes:**</span><span class="sxs-lookup"><span data-stu-id="94923-120">Click **Render this report from an execution snapshot, and then select one of the following options:**</span></span>  
  
    -   <span data-ttu-id="94923-121">Si quiere crear una instantánea, seleccione **Utilizar la siguiente programación para crear instantáneas de ejecución de informes**y, después, defina una programación específica del informe o seleccione una de la lista **Programación compartida** .</span><span class="sxs-lookup"><span data-stu-id="94923-121">If you want to create a snapshot, select **Use the following schedule to create report execution snapshots**, and then either define a report-specific schedule or select from the **Shared schedule** list.</span></span>  
  
    -   <span data-ttu-id="94923-122">Si desea crear una instantánea inmediatamente, seleccione **Crea una instantánea de informe cuando hace clic en el botón Aplicar de esta página**.</span><span class="sxs-lookup"><span data-stu-id="94923-122">If you want to create a snapshot immediately, select **Create a report snapshot when you click the Apply button on this page**.</span></span>  
  
3.  <span data-ttu-id="94923-123">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="94923-123">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94923-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94923-124">See Also</span></span>  
 <span data-ttu-id="94923-125">[Establecer propiedades de procesamiento de informes](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="94923-125">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="94923-126">[Abrir y cerrar un informe &#40;Administrador de informes&#41;](../reports/open-and-close-a-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="94923-126">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) </span></span>  
 <span data-ttu-id="94923-127">[Contenido &#40;página del Administrador de informes&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="94923-127">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="94923-128">[Administración de contenido del servidor de informes &#40;Modo nativo de SSRS&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="94923-128">[Report Server Content Management &#40;SSRS Native Mode&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="94923-129">Página de propiedades Opciones de procesamiento &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="94923-129">Processing Options Properties Page &#40;Report Manager&#41;</span></span>](../processing-options-properties-page-report-manager.md)  
  
  
