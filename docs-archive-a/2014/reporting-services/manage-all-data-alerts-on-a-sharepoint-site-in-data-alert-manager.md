---
title: Administrar todas las alertas de datos de un sitio de SharePoint en el Administrador de alertas de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: 9c70b0f4-2db8-4c2e-acbf-96e2a55ddc48
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b41fdbd18a0b1b4a7a69a3ca202de1c555c070de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748019"
---
# <a name="manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager"></a><span data-ttu-id="17682-102">Administrar todas las alertas de datos de un sitio de SharePoint en el Administrador de alertas de datos</span><span class="sxs-lookup"><span data-stu-id="17682-102">Manage All Data Alerts on a SharePoint Site in Data Alert Manager</span></span>
  <span data-ttu-id="17682-103">Los administradores de alertas de SharePoint pueden ver una lista de las alertas de datos creadas por los usuarios del sitio e información acerca de las alertas.</span><span class="sxs-lookup"><span data-stu-id="17682-103">SharePoint alerting administrators can view a list of the data alerts that were created by any site user and information about the alerts.</span></span> <span data-ttu-id="17682-104">Los administradores de alertas también pueden eliminar alertas.</span><span class="sxs-lookup"><span data-stu-id="17682-104">Alerting administrators can also delete alerts.</span></span> <span data-ttu-id="17682-105">En la imagen siguiente se muestran las características disponibles para los administradores de alertas en el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="17682-105">The following picture shows the features available to alerting administrators in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="17682-106">![Administrador de alertas para administradores de sitios de SharePoint](media/rs-alertmanagersite.gif "Administrador de alertas para administradores de sitios de SharePoint")</span><span class="sxs-lookup"><span data-stu-id="17682-106">![Alert Manager for SharePoin tsite administrators](media/rs-alertmanagersite.gif "Alert Manager for SharePoin tsite administrators")</span></span>  
  
### <a name="to-view-a-list-of-alerts-created-by-a-site-user"></a><span data-ttu-id="17682-107">Para ver una lista de las alertas creadas por un usuario del sitio</span><span class="sxs-lookup"><span data-stu-id="17682-107">To view a list of alerts created by a site user</span></span>  
  
1.  <span data-ttu-id="17682-108">Vaya al sitio de SharePoint donde se guardan las definiciones de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="17682-108">Go to the SharePoint site where data alerts definitions are saved.</span></span>  
  
2.  <span data-ttu-id="17682-109">En la página Inicio, haga clic en **Acciones del sitio**.</span><span class="sxs-lookup"><span data-stu-id="17682-109">On the Home page, click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="17682-110">Desplácese a la parte inferior de la lista y haga clic en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="17682-110">Scroll to the bottom of the list and click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="17682-111">En **Reporting Services**, haga clic en **Administrar alertas de datos**.</span><span class="sxs-lookup"><span data-stu-id="17682-111">Under **Reporting Services**, click **Manage Data Alerts**.</span></span>  
  
5.  <span data-ttu-id="17682-112">Haga clic en la flecha hacia abajo situada junta a la lista **Ver las alertas del usuario** y seleccione el usuario cuyas alertas desea ver.</span><span class="sxs-lookup"><span data-stu-id="17682-112">Click the down arrow by the **View alerts for user** list and select the user whose alerts you want to view.</span></span>  
  
6.  <span data-ttu-id="17682-113">Haga clic en la flecha hacia abajo que aparece junto a la lista **Ver las alertas del informe** y seleccione la alerta específica que desea ver, o haga clic en **Mostrar todas** para ver todas las alertas creadas por el usuario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="17682-113">Click the down arrow next to the **View alerts for report** list and select a specific alert to view, or click **Show All** to list all alerts created by the selected user.</span></span>  
  
     <span data-ttu-id="17682-114">En una tabla se muestra el nombre de la alerta, el nombre del informe, el nombre de la persona que creó la alerta de datos, el número de veces que se envió la alerta de datos, la última vez que se modificó la definición de la alerta de datos y el estado de la alerta de datos.</span><span class="sxs-lookup"><span data-stu-id="17682-114">A table lists the name, report name, name of the person who created the data alert, the number times the data alert was sent, the last time the data alert definition was modified, and the status of the data alert.</span></span> <span data-ttu-id="17682-115">Si la alerta de datos no se puede generar o enviar, la columna de estado contiene información sobre el error que le ayudará a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="17682-115">If the data alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="17682-116">Para eliminar una definición de alerta</span><span class="sxs-lookup"><span data-stu-id="17682-116">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="17682-117">Haga clic con el botón derecho en la alerta de datos que quiere eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="17682-117">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="17682-118">Después de eliminar la alerta, no se envían más mensajes de alerta.</span><span class="sxs-lookup"><span data-stu-id="17682-118">After you delete the alert, no further alert messages are sent.</span></span> <span data-ttu-id="17682-119">Sin embargo, si consulta la base de datos de alertas puede que todavía exista la definición de la alerta.</span><span class="sxs-lookup"><span data-stu-id="17682-119">However, if you query the alerting database you might find that the alert definition still exists.</span></span> <span data-ttu-id="17682-120">El servicio de alertas realiza limpiezas según una programación, y la definición de la alerta se eliminará definitivamente durante la limpieza siguiente.</span><span class="sxs-lookup"><span data-stu-id="17682-120">The alerting service performs clean up on a schedule and the alert definition is deleted permanently in the next cleanup.</span></span> <span data-ttu-id="17682-121">El intervalo de limpieza predeterminado es de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="17682-121">The default cleanup interval is 20 minutes.</span></span> <span data-ttu-id="17682-122">Este y otros intervalos de limpieza son configurables.</span><span class="sxs-lookup"><span data-stu-id="17682-122">This and other cleanup intervals are configurable.</span></span> <span data-ttu-id="17682-123">Para obtener más información, vea [Alertas de datos de Reporting Services](../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="17682-123">For more information, see [Reporting Services Data Alerts](../ssms/agent/alerts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17682-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17682-124">See Also</span></span>  
 <span data-ttu-id="17682-125">[Administrador de alertas de datos para administradores de alertas](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="17682-125">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="17682-126">Alertas de datos de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="17682-126">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
