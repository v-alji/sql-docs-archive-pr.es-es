---
title: Página historial de informes (Administrador de informes) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services-native
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 4070be8c1d6b0633131e96c665d4551c1b676a9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672639"
---
# <a name="report-history-page-report-manager"></a><span data-ttu-id="2ba09-102">Historial del informe (página del Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="2ba09-102">Report History Page (Report Manager)</span></span>

<span data-ttu-id="2ba09-103">Use la página Historial de informes para ver las instantáneas de informe que se generan y almacenan a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="2ba09-103">Use the Report History page to view report snapshots that are generated and stored over time.</span></span> <span data-ttu-id="2ba09-104">Dependiendo de las opciones que se configuren en el servidor de informes, es posible que el historial de informe solamente contenga las instantáneas más recientes.</span><span class="sxs-lookup"><span data-stu-id="2ba09-104">Depending on options that are set on the report server, report history may contain only the more recent snapshots.</span></span>  
  

<span data-ttu-id="2ba09-105">El historial del informe siempre se ve en el contexto del informe desde el que se origina.</span><span class="sxs-lookup"><span data-stu-id="2ba09-105">Report history is always viewed within the context of the report from which it originates.</span></span> <span data-ttu-id="2ba09-106">No se puede ver el historial de todos los informes de un servidor de informes en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="2ba09-106">You cannot view the history of all reports on a report server in one place.</span></span>  
  
<span data-ttu-id="2ba09-107">Para generar el historial de un informe, el informe debe poder ejecutarse en modo desatendido, es decir, debe utilizar credenciales almacenadas; los informes parametrizados deben contener valores predeterminados para todos los parámetros.</span><span class="sxs-lookup"><span data-stu-id="2ba09-107">To generate report history, the report must be able to run unattended (that is, it must use stored credentials; parameterized reports must contain default parameter values for all parameters).</span></span> <span data-ttu-id="2ba09-108">Un historial de informe se puede generar manualmente o como una operación programada.</span><span class="sxs-lookup"><span data-stu-id="2ba09-108">Report history can be generated manually or as a scheduled operation.</span></span> <span data-ttu-id="2ba09-109">Las propiedades del historial en el informe determinan las formas en que se puede crear el historial.</span><span class="sxs-lookup"><span data-stu-id="2ba09-109">History properties on the report determine the ways in which report history can be created.</span></span>  
  
<span data-ttu-id="2ba09-110">Puede hacer clic en una instantánea del historial de un informe para verla.</span><span class="sxs-lookup"><span data-stu-id="2ba09-110">You can click a report history snapshot to view it.</span></span> <span data-ttu-id="2ba09-111">Las instantáneas que aparecen en un historial de informe solamente se distinguen por la fecha y la hora en que fueron creadas.</span><span class="sxs-lookup"><span data-stu-id="2ba09-111">Snapshots that appear in report history are distinguished only by the date and time at which they were created.</span></span> <span data-ttu-id="2ba09-112">No hay manera de distinguir visualmente si una instantánea se generó como respuesta a una operación programada o manual.</span><span class="sxs-lookup"><span data-stu-id="2ba09-112">There is no visual indication to distinguish whether a snapshot was generated in response to a schedule or a manual operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ba09-113">Esta característica no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ba09-113">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2ba09-114">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="2ba09-114">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="2ba09-115">Navegación</span><span class="sxs-lookup"><span data-stu-id="2ba09-115">Navigation</span></span>  
 <span data-ttu-id="2ba09-116">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="2ba09-116">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-report-history-page"></a><span data-ttu-id="2ba09-117">Para abrir la página Historial del informe</span><span class="sxs-lookup"><span data-stu-id="2ba09-117">To open the Report History page</span></span>  
  
1.  <span data-ttu-id="2ba09-118">Abra el Administrador de informes y busque el informe para el que desea ver las instantáneas de informe.</span><span class="sxs-lookup"><span data-stu-id="2ba09-118">Open Report Manager, and locate the report for which you want to view report snapshots.</span></span>  
  
2.  <span data-ttu-id="2ba09-119">Mantenga el mouse sobre el informe y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2ba09-119">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="2ba09-120">En el menú desplegable, haga clic en **Ver historial de informes**.</span><span class="sxs-lookup"><span data-stu-id="2ba09-120">In the drop-down menu, click **View Report History**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2ba09-121">Opciones</span><span class="sxs-lookup"><span data-stu-id="2ba09-121">Options</span></span>  
 <span data-ttu-id="2ba09-122">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="2ba09-122">**Delete**</span></span>  
 <span data-ttu-id="2ba09-123">Haga clic para eliminar una o varias instantáneas.</span><span class="sxs-lookup"><span data-stu-id="2ba09-123">Click to delete one or more snapshots.</span></span> <span data-ttu-id="2ba09-124">Antes de hacer clic en **Eliminar**, active la casilla situada junto a la instantánea que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="2ba09-124">Before clicking **Delete**, select the check box next to the snapshot that you want to delete.</span></span>  
  
 <span data-ttu-id="2ba09-125">**Nueva instantánea**</span><span class="sxs-lookup"><span data-stu-id="2ba09-125">**New Snapshot**</span></span>  
 <span data-ttu-id="2ba09-126">Haga clic para agregar una instantánea al historial de informes</span><span class="sxs-lookup"><span data-stu-id="2ba09-126">Click to add a snapshot to report history.</span></span> <span data-ttu-id="2ba09-127">Este botón está disponible cuando se elige la opción **Permitir que el historial se cree manualmente** en la página de propiedades Historial del informe.</span><span class="sxs-lookup"><span data-stu-id="2ba09-127">This button is available when you choose the option **Allow history to be created manually** on the History properties page of the report.</span></span>  
  
 <span data-ttu-id="2ba09-128">**Última ejecución**</span><span class="sxs-lookup"><span data-stu-id="2ba09-128">**Last Run**</span></span>  
 <span data-ttu-id="2ba09-129">Muestra la fecha y la hora en que se creó la instantánea.</span><span class="sxs-lookup"><span data-stu-id="2ba09-129">Displays the date and time at which the snapshot was created.</span></span> <span data-ttu-id="2ba09-130">Haga clic en una descripción para ver una instantánea determinada.</span><span class="sxs-lookup"><span data-stu-id="2ba09-130">Click a description to view a particular snapshot.</span></span>  
  
 <span data-ttu-id="2ba09-131">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="2ba09-131">**Size**</span></span>  
 <span data-ttu-id="2ba09-132">Muestra el tamaño de la definición del informe y los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="2ba09-132">Displays the size of the report definition plus the data in the report.</span></span> <span data-ttu-id="2ba09-133">Este valor indica el espacio que ocupan la definición y los datos del informe en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2ba09-133">This value indicates how much space in the report server database is used by the report definition and data.</span></span> <span data-ttu-id="2ba09-134">En realidad, el informe representado, que incluye el formato, tiene un tamaño mayor.</span><span class="sxs-lookup"><span data-stu-id="2ba09-134">The size of the rendered report, which includes formatting, is actually larger.</span></span> <span data-ttu-id="2ba09-135">El tamaño total, indicado entre paréntesis, suma los tamaños de todas las instantáneas del historial del informe actual.</span><span class="sxs-lookup"><span data-stu-id="2ba09-135">The total size, indicated in parentheses, sums the sizes of all snapshots in the report history for the current report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba09-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ba09-136">See Also</span></span>  
 <span data-ttu-id="2ba09-137">[Ver o eliminar el historial de informes &#40;Administrador de informes&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2ba09-137">[View or Delete Report History &#40;Report Manager&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="2ba09-138">[Agregar una instantánea al historial de informes &#40;Administrador de informes&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2ba09-138">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="2ba09-139">[Página de propiedades generales, informes &#40;Administrador de informes&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2ba09-139">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="2ba09-140">[Administrador de informes la ayuda F1](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="2ba09-140">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="2ba09-141">Página de propiedades opciones de instantánea &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="2ba09-141">Snapshot Options Properties Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/snapshot-options-properties-page-report-manager.md)