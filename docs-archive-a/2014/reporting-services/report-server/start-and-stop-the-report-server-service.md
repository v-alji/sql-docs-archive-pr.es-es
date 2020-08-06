---
title: Iniciar y detener el servicio del servidor de informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- stopping Report Server service
- Report Server Windows service, starting
- Report Server service, starting
- starting Report Server service
ms.assetid: 6ec69ac3-27b0-472d-91e1-733af9078ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b751fd1a31830ffdc96cb296fa39d08e396c8c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672623"
---
# <a name="start-and-stop-the-report-server-service"></a><span data-ttu-id="2e5af-102">Iniciar y detener el servicio del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="2e5af-102">Start and Stop the Report Server Service</span></span>
  <span data-ttu-id="2e5af-103">Un servidor de informes se implementa como un servicio de Windows que contiene el servicio web del servidor de informes, el Administrador de informes y una aplicación de procesamiento en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2e5af-103">A report server is implemented as a Windows service that contains the Report Server Web service, Report Manager, and a background processing application.</span></span> <span data-ttu-id="2e5af-104">El servicio se debe estar ejecutando si desea usar cualquier funcionalidad del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2e5af-104">The service must be running if you want to use any report server functionality.</span></span> <span data-ttu-id="2e5af-105">Al detener el servicio se detienen todas las operaciones del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2e5af-105">Stopping the service stops all report server operations.</span></span>  
  
 <span data-ttu-id="2e5af-106">Aunque se detiene el servicio, las solicitudes para el procesamiento de informes y suscripciones programado que deberían haberse producido si se hubiera estado ejecutando el servicio se agregan a la cola.</span><span class="sxs-lookup"><span data-stu-id="2e5af-106">While the service is stopped, requests for scheduled report and subscription processing that would have occurred had the service been running are added to the queue.</span></span> <span data-ttu-id="2e5af-107">Esto se debe a que los trabajos que se ejecutan con el Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crean los eventos.</span><span class="sxs-lookup"><span data-stu-id="2e5af-107">This is because jobs that are run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent create the events.</span></span> <span data-ttu-id="2e5af-108">Si desea evitar un trabajo acumulado de operaciones mientras el servicio está apagado, piense también en detener el Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e5af-108">If you want to avoid a backlog of operations while the service is off, consider stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent as well.</span></span>  
  
 <span data-ttu-id="2e5af-109">Puede usar diversas herramientas para iniciar o detener el servicio del servidor de informes, como son la herramienta Configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y la herramienta Servicios que se proporciona en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="2e5af-109">You can use a variety of tools to start or stop the Report Server service, including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, and the Services tool provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span></span>  
  
 <span data-ttu-id="2e5af-110">Si está realizando otras acciones además de iniciar y detener el servicio, como por ejemplo, el cambio de la cuenta de servicio, debe usar la herramienta de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e5af-110">If you are doing more than starting or stopping the service, such as changing the service account, you must use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="2e5af-111">Si usa otras herramientas para cambiar la cuenta de servicio puede interrumpir la instalación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e5af-111">Using other tools to change the service account can break your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="2e5af-112">Para obtener más información, vea [Configurar la cuenta de servicio del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2e5af-112">For more information, see [Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="2e5af-113">No puede pausar ni reanudar el servicio.</span><span class="sxs-lookup"><span data-stu-id="2e5af-113">You cannot pause and resume the service.</span></span> <span data-ttu-id="2e5af-114">No existen parámetros de inicio.</span><span class="sxs-lookup"><span data-stu-id="2e5af-114">There are no start parameters.</span></span> <span data-ttu-id="2e5af-115">Aunque no hay dependencias explícitas, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe ejecutarse si se admiten suscripciones u operaciones de informe programadas en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2e5af-115">Although there are no explicit dependencies, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running if you support any subscriptions or scheduled report operations on the report server.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-the-reporting-services-configuration-tool"></a><span data-ttu-id="2e5af-116">Iniciar o detener el servicio mediante la herramienta de configuración de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2e5af-116">To start or stop the service using the Reporting Services Configuration tool</span></span>  
  
1.  <span data-ttu-id="2e5af-117">Inicie la herramienta de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y conéctese al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2e5af-117">Start [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and connect to the report server.</span></span>  
  
2.  <span data-ttu-id="2e5af-118">En la página Estado del servidor de informes, haga clic en **Detener** o **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="2e5af-118">On the Report Server Status page, click **Stop** or **Start**.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-services-in-administrative-tools"></a><span data-ttu-id="2e5af-119">Iniciar o detener el servicio usando Servicios en Herramientas administrativas</span><span class="sxs-lookup"><span data-stu-id="2e5af-119">To start or stop the service using Services in Administrative Tools</span></span>  
  
-   <span data-ttu-id="2e5af-120">En Herramientas administrativas, abra Servicios, haga clic con el botón derecho en **SQL Server Reporting Services (MSSQLSERVER)** y haga clic en **Detener** o **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="2e5af-120">In Administrative Tools, open Services, right-click **SQL Server Reporting Services (MSSQLSERVER)**, and click **Stop** or **Restart**.</span></span>  
  
 <span data-ttu-id="2e5af-121">Si se están ejecutando varias instancias o si el servidor de informes se está ejecutando como una instancia con nombre, compruebe que el nombre de instancia que está entre paréntesis corresponde a la instancia del servidor de informes que desea detener o reiniciar.</span><span class="sxs-lookup"><span data-stu-id="2e5af-121">If you are running multiple instance or if the report server is running as a named instance, verify that the instance name in parentheses corresponds to the report server instance you want to stop or restart.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-sql-server-configuration-manager"></a><span data-ttu-id="2e5af-122">Iniciar o detener el servicio usando el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2e5af-122">To start or stop the service using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="2e5af-123">Inicie el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e5af-123">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
2.  <span data-ttu-id="2e5af-124">Seleccione Servicios de SQL Server, haga clic con el botón derecho en **SQL Server Reporting Services**y haga clic en **Detener** o en **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="2e5af-124">Select SQL Server Services, right-click **SQL Server Reporting Services**, and click **Stop** or **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e5af-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e5af-125">See Also</span></span>  
 [<span data-ttu-id="2e5af-126">Administrador de configuración de Reporting Services &#40;modo nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="2e5af-126">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
