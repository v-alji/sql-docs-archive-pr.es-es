---
title: Propiedades de la programación (página Informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.reports.f1
ms.assetid: 7db728bd-4b08-43ef-a49a-e8dcdd37cf89
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: da0b5255e73522572fa22da8668329a28f108104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671357"
---
# <a name="schedule-properties-reports-page"></a><span data-ttu-id="1c050-102">Propiedades de la programación (página Informes)</span><span class="sxs-lookup"><span data-stu-id="1c050-102">Schedule Properties (Reports Page)</span></span>
  <span data-ttu-id="1c050-103">Utilice esta página para ver una lista de todos los informes que utilizan esta programación compartida.</span><span class="sxs-lookup"><span data-stu-id="1c050-103">Use this page to view a list of all reports that use this shared schedule.</span></span> <span data-ttu-id="1c050-104">Las programaciones pueden utilizarse para actualizar instantáneas de informe, generar un historial de informes, desencadenar una suscripción o hacer expirar una copia del informe almacenada en caché.</span><span class="sxs-lookup"><span data-stu-id="1c050-104">Schedules can be used to refresh report snapshots, generate report history, trigger a subscription, or expire a cached copy of the report.</span></span> <span data-ttu-id="1c050-105">Para averiguar cómo se usa la programación, vea la información de propiedad y suscripciones del informe.</span><span class="sxs-lookup"><span data-stu-id="1c050-105">To find out how the schedule is used, view the property and subscription information of the report.</span></span>  
  
 <span data-ttu-id="1c050-106">Aunque esta página muestra cada informe que usa la programación compartida, no indica cuántas veces se usa la programación compartida dentro de ese informe único.</span><span class="sxs-lookup"><span data-stu-id="1c050-106">Although this page shows each report that uses the shared schedule, it does not indicate how many times the shared schedule is used within that single report.</span></span> <span data-ttu-id="1c050-107">Por ejemplo, supongamos que 20 diferentes suscriptores al informe Company Sales usan la misma programación compartida para desencadenar el procesamiento de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="1c050-107">For example, suppose 20 different subscribers to the Company Sales report all use the same shared schedule to trigger subscription processing.</span></span> <span data-ttu-id="1c050-108">En este caso, el informe Company Sales solamente aparecerá una vez en esta lista, aunque el informe tenga 20 referencias a la programación compartida.</span><span class="sxs-lookup"><span data-stu-id="1c050-108">In this case, the Company Sales report will only appear once in this list, even though the report has 20 references to the shared schedule.</span></span>  
  
 <span data-ttu-id="1c050-109">Para abrir esta página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a un servidor de informes, abra la carpeta **Programaciones compartidas** , haga clic con el botón secundario en una programación compartida, seleccione **Propiedades**y, a continuación, haga clic en **Informes**.</span><span class="sxs-lookup"><span data-stu-id="1c050-109">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, select **Properties**, and then click **Reports**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c050-110">Esta característica no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c050-110">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1c050-111">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea [características compatibles con las ediciones de SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="1c050-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1c050-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="1c050-112">Options</span></span>  
 <span data-ttu-id="1c050-113">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="1c050-113">**Folder**</span></span>  
 <span data-ttu-id="1c050-114">Especifica la ruta de acceso del informe.</span><span class="sxs-lookup"><span data-stu-id="1c050-114">Specifies the path of the report.</span></span>  
  
 <span data-ttu-id="1c050-115">**Report**</span><span class="sxs-lookup"><span data-stu-id="1c050-115">**Report**</span></span>  
 <span data-ttu-id="1c050-116">Especifica el nombre del informe que utiliza la programación.</span><span class="sxs-lookup"><span data-stu-id="1c050-116">Specifies the name of the report that uses the schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c050-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c050-117">See Also</span></span>  
 <span data-ttu-id="1c050-118">[Crear, modificar y eliminar programaciones](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="1c050-118">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="1c050-119">[Programaciones](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="1c050-119">[Schedules](../subscriptions/schedules.md) </span></span>  
 <span data-ttu-id="1c050-120">[Servidor de informes en Management Studio ayuda de F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="1c050-120">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="1c050-121">[Conectarse a un servidor de informes en Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1c050-121">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="1c050-122">Configurar las propiedades generales de un informe &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="1c050-122">Configure General Properties for a Report &#40;Report Manager&#41;</span></span>](../configure-general-properties-for-a-report-report-manager.md)  
  
  
