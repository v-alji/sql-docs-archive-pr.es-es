---
title: Propiedades del servidor (página Historial) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.history.f1
ms.assetid: be9d8018-a46f-4625-9ae1-138ebe6b38ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: df5ff9dc7a94431f8feec112d460938aa1631ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674005"
---
# <a name="server-properties-history-page"></a><span data-ttu-id="67525-102">Propiedades del servidor (página Historial)</span><span class="sxs-lookup"><span data-stu-id="67525-102">Server Properties (History Page)</span></span>
  <span data-ttu-id="67525-103">Utilice esta página para establecer un valor predeterminado para el número de copias del historial del informe que deben guardarse.</span><span class="sxs-lookup"><span data-stu-id="67525-103">Use this page to set a default value for the number of copies of report history to retain.</span></span> <span data-ttu-id="67525-104">El valor predeterminado proporciona un valor inicial que establece los límites del historial de informes para todos los informes.</span><span class="sxs-lookup"><span data-stu-id="67525-104">The default value provides an initial setting that establishes report history limits for all reports.</span></span> <span data-ttu-id="67525-105">Existe la posibilidad de modificar esta configuración para informes individuales.</span><span class="sxs-lookup"><span data-stu-id="67525-105">You can vary these settings for individual reports.</span></span>  
  
 <span data-ttu-id="67525-106">El historial de informes es una colección de instantáneas de informe que incluye datos de informe y diseño actual para el informe en el momento en que se crea la instantánea.</span><span class="sxs-lookup"><span data-stu-id="67525-106">Report history is a collection of report snapshots that include report data and layout that is current for the report at the time the snapshot is created.</span></span> <span data-ttu-id="67525-107">Puede usar el historial de informes para mantener una copia de un informe como se encontraba en una fecha u hora específicas.</span><span class="sxs-lookup"><span data-stu-id="67525-107">You can use report history to keep a copy of a report as it was on a specific date or time.</span></span> <span data-ttu-id="67525-108">Puede crear y administrar el historial de informes para informes individuales que se ejecutan en un servidor de informes en modo nativo o un servidor de informes que se configura para modo integrado con SharePoint.</span><span class="sxs-lookup"><span data-stu-id="67525-108">You can create and manage report history for individual reports that run on a native mode report server or a report server that is configured for SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="67525-109">Las instantáneas del historial de informes están almacenadas en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="67525-109">Report history snapshots are stored in the report server database.</span></span> <span data-ttu-id="67525-110">Si mantiene un número ilimitado de instantáneas, asegúrese de comprobar periódicamente el tamaño de la base de datos para asegurarse de que no crece demasiado rápido ni consume demasiado espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="67525-110">If you keep an unlimited number of snapshots, be sure to periodically check the database size to ensure it is not growing too fast or consuming too much disk space.</span></span>  
  
 <span data-ttu-id="67525-111">Para abrir esta página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a una instancia del servidor de informes, haga clic con el botón derecho en el nombre del servidor de informes y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="67525-111">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="67525-112">Haga clic en **Historial** para abrir esta página.</span><span class="sxs-lookup"><span data-stu-id="67525-112">Click **History** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="67525-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="67525-113">Options</span></span>  
 <span data-ttu-id="67525-114">**Conservar un número ilimitado de instantáneas en el historial de informe**</span><span class="sxs-lookup"><span data-stu-id="67525-114">**Keep an unlimited number of snapshots in report history**</span></span>  
 <span data-ttu-id="67525-115">Conserve todas las instantáneas del historial de informes.</span><span class="sxs-lookup"><span data-stu-id="67525-115">Retain all report history snapshots.</span></span> <span data-ttu-id="67525-116">Para reducir el tamaño del historial de informe, debe eliminar las instantáneas manualmente.</span><span class="sxs-lookup"><span data-stu-id="67525-116">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
 <span data-ttu-id="67525-117">**Limitar las copias del historial de informe**</span><span class="sxs-lookup"><span data-stu-id="67525-117">**Limit the copies of report history**</span></span>  
 <span data-ttu-id="67525-118">Conserve un número fijo de instantáneas del historial de informes.</span><span class="sxs-lookup"><span data-stu-id="67525-118">Retain a set number of report history snapshots.</span></span> <span data-ttu-id="67525-119">Cuando se alcanza el límite, las copias más antiguas se eliminan del historial de informe para dejar sitio para las nuevas.</span><span class="sxs-lookup"><span data-stu-id="67525-119">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="67525-120">Si posteriormente limita el historial del informe, cuando el historial del informe existente exceda el límite especificado, el servidor de informes lo reducirá según el nuevo límite.</span><span class="sxs-lookup"><span data-stu-id="67525-120">If you limit report history later, when the existing report history exceeds the limit you specify, the report server reduces the existing report history to the new limit.</span></span> <span data-ttu-id="67525-121">Las instantáneas de informe más antiguas son las que se eliminan primero.</span><span class="sxs-lookup"><span data-stu-id="67525-121">The oldest report snapshots are deleted first.</span></span> <span data-ttu-id="67525-122">Si el historial del informe está vacío o por debajo del límite, se agregan nuevas instantáneas de informe.</span><span class="sxs-lookup"><span data-stu-id="67525-122">If report history is empty or below the limit, new report snapshots are added.</span></span> <span data-ttu-id="67525-123">Cuando se alcanza el límite, se elimina la instantánea del informe más antigua cuando se agrega una nueva.</span><span class="sxs-lookup"><span data-stu-id="67525-123">When the limit is reached, the oldest snapshot is deleted when a new report snapshot is added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67525-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67525-124">See Also</span></span>  
 <span data-ttu-id="67525-125">[Establecer las propiedades del servidor de informes &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="67525-125">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="67525-126">[Conectarse a un servidor de informes en Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="67525-126">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="67525-127">Servidor de informes en Management Studio ayuda F1</span><span class="sxs-lookup"><span data-stu-id="67525-127">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
