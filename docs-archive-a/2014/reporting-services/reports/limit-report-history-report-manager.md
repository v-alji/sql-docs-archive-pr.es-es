---
title: Limitar el historial de informe (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- viewing report history
- report history [Reporting Services], viewing history
- report history [Reporting Services], configuring history
- historical data [Reporting Services]
- displaying report history
ms.assetid: 8e255792-d9ef-496f-a26c-9e969c1209a0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01318b1e1ccf0b0bf4512ab57de90cbf5ebc7365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745009"
---
# <a name="limit-report-history-report-manager"></a><span data-ttu-id="d7c66-102">Limitar el historial de informe (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="d7c66-102">Limit Report History (Report Manager)</span></span>
  <span data-ttu-id="d7c66-103">El historial de informes es un conjunto de instantáneas de informe que se crean a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="d7c66-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="d7c66-104">Puede crear el historial de informes a petición o programar la frecuencia con que una instantánea se crea y se agrega al historial de informes.</span><span class="sxs-lookup"><span data-stu-id="d7c66-104">You can create report history on demand, or schedule how often a snapshot is created and added to report history.</span></span>  
  
 <span data-ttu-id="d7c66-105">El historial de informes está almacenado en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="d7c66-105">Report history is stored in the report server database.</span></span> <span data-ttu-id="d7c66-106">Si las instantáneas de informes contienen una gran cantidad de datos, considere la posibilidad de limitar el historial de informes para minimizar el efecto de la retención de instantáneas en el tamaño de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d7c66-106">If report snapshots contain a large amount of data, you might consider limiting report history to minimize the affect of snapshot retention on database size.</span></span>  
  
### <a name="to-configure-report-history-for-a-report-server"></a><span data-ttu-id="d7c66-107">Para configurar un historial del informe para un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="d7c66-107">To configure report history for a report server</span></span>  
  
1.  <span data-ttu-id="d7c66-108">En el Administrador de informes, haga clic en **Configuración del sitio** en la barra de herramientas global.</span><span class="sxs-lookup"><span data-stu-id="d7c66-108">In Report Manager, click **Site Settings** on the global toolbar.</span></span>  
  
2.  <span data-ttu-id="d7c66-109">Seleccione **Conservar un número ilimitado de instantáneas en el historial de informe** si desea guardar todo el historial del informe indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="d7c66-109">Select **Keep an unlimited number of snapshots in report history** if you want to keep all report history indefinitely.</span></span> <span data-ttu-id="d7c66-110">De lo contrario, seleccione **Limitar las copias del historial de informe** para especificar la cantidad máxima de instantáneas que se pueden guardar para un determinado informe.</span><span class="sxs-lookup"><span data-stu-id="d7c66-110">Otherwise, select **Limit the copies of report history** to specify the maximum number of snapshots that can be kept for any given report.</span></span>  
  
3.  <span data-ttu-id="d7c66-111">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="d7c66-111">Click **Apply**.</span></span>  
  
### <a name="to-configure-report-history-for-a-specific-report"></a><span data-ttu-id="d7c66-112">Para configurar un historial de un informe específico</span><span class="sxs-lookup"><span data-stu-id="d7c66-112">To configure report history for a specific report</span></span>  
  
1.  <span data-ttu-id="d7c66-113">En el Administrador de informes, navegue al informe para el cual desea configurar el historial y, a continuación, haga clic en el informe para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="d7c66-113">In Report Manager, navigate to the report for which you want to configure history, and then click the report to open it.</span></span>  
  
2.  <span data-ttu-id="d7c66-114">Haga clic en la pestaña **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d7c66-114">Click the **Properties** tab.</span></span>  
  
3.  <span data-ttu-id="d7c66-115">Haga clic en la pestaña **Historial**.</span><span class="sxs-lookup"><span data-stu-id="d7c66-115">Click the **History** tab.</span></span>  
  
4.  <span data-ttu-id="d7c66-116">Seleccione las opciones para el informe y haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="d7c66-116">Select the options for your report and click **Apply**.</span></span> <span data-ttu-id="d7c66-117">Para más información sobre cada opción, vea [Página de propiedades de opciones de instantánea &#40;Administrador de informes&#41;](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d7c66-117">For details about each option, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c66-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7c66-118">See Also</span></span>  
 <span data-ttu-id="d7c66-119">[Agregar una instantánea al historial de informes &#40;Administrador de informes&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d7c66-119">[Add a Snapshot to Report History &#40;Report Manager&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 [<span data-ttu-id="d7c66-120">Administrador de informes &#40;Modo nativo de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d7c66-120">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
