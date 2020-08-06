---
title: Ver paquetes de Integration Services en SQL Server Management Studio (servicio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- viewing packages
- connections [Integration Services], packages
ms.assetid: 783e653c-0f1f-45ed-b3ef-5ba07b019f27
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4ba86320f1b1a685eab6e80399f3e8c21bd110eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744179"
---
# <a name="view-integration-services-packages-in-sql-server-management-studio-ssis-service"></a><span data-ttu-id="834f8-102">Ver paquetes de Integration Services en SQL Server Management Studio (servicio SSIS)</span><span class="sxs-lookup"><span data-stu-id="834f8-102">View Integration Services Packages in SQL Server Management Studio (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="834f8-103">En este tema se describe el servicio de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un servicio Windows para administrar paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="834f8-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="834f8-104">admite el servicio para mantener la compatibilidad con versiones anteriores de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="834f8-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="834f8-105">A partir de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], puede administrar objetos como paquetes en el servidor de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="834f8-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="834f8-106">En este procedimiento se explica cómo conectarse a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] y ver una lista de los paquetes que administra el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="834f8-106">This procedure describes how to connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and view a list of the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
### <a name="to-connect-to-integration-services"></a><span data-ttu-id="834f8-107">Para conectarse a Integration Services</span><span class="sxs-lookup"><span data-stu-id="834f8-107">To connect to Integration Services</span></span>  
  
1.  <span data-ttu-id="834f8-108">Haga clic en **Inicio**, elija **Todos los programas**, **Microsoft SQL Server**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="834f8-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="834f8-109">En el cuadro de diálogo **Conectar al servidor** , seleccione **Integration Services** en la lista **Tipo de servidor** , proporcione un nombre de servidor en el cuadro **Nombre de servidor** y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="834f8-109">In the **Connect to Server** dialog box, select **Integration Services** in the **Server type** list, provide a server name in the **Server name** box, and then click **Connect**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="834f8-110">Si no puede conectarse a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], es probable que no se esté ejecutando el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="834f8-110">If you cannot connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is likely not running.</span></span> <span data-ttu-id="834f8-111">Para conocer el estado del servicio, haga clic en **Inicio**, elija sucesivamente **Todos los programas**, **Microsoft SQL Server**, **Herramientas de configuración**, y haga clic en **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="834f8-111">To learn the status of the service, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="834f8-112">En el panel izquierdo, haga clic en **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="834f8-112">In the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="834f8-113">En el panel derecho, busque el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="834f8-113">In the right pane, find the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="834f8-114">Inicie el servicio, si no se está ejecutando todavía.</span><span class="sxs-lookup"><span data-stu-id="834f8-114">Start the service if it is not already running.</span></span>  
  
     [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="834f8-115">.</span><span class="sxs-lookup"><span data-stu-id="834f8-115">opens.</span></span> <span data-ttu-id="834f8-116">De forma predeterminada, la ventana del Explorador de objetos está abierta y colocada en la esquina inferior izquierda del estudio.</span><span class="sxs-lookup"><span data-stu-id="834f8-116">By default the Object Explorer window is open and positioned in the lower-left corner of the studio.</span></span> <span data-ttu-id="834f8-117">Si el Explorador de objetos no está abierto, haga clic en **Explorador de objetos** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="834f8-117">If Object Explorer is not open, click **Object Explorer** on the **View** menu.</span></span>  
  
### <a name="to-view-the-packages-that-integration-services-service-manages"></a><span data-ttu-id="834f8-118">Para ver los paquetes que administra el servicio Integration Services</span><span class="sxs-lookup"><span data-stu-id="834f8-118">To view the packages that Integration Services service manages</span></span>  
  
1.  <span data-ttu-id="834f8-119">En el Explorador de objetos, expanda la carpeta Paquetes almacenados.</span><span class="sxs-lookup"><span data-stu-id="834f8-119">In Object Explorer, expand the Stored Packages folder.</span></span>  
  
2.  <span data-ttu-id="834f8-120">Expanda las subcarpetas de Paquetes almacenados para mostrar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="834f8-120">Expand the Stored Packages subfolders to show packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="834f8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="834f8-121">See Also</span></span>  
 <span data-ttu-id="834f8-122">[Administración de paquetes &#40;servicio SSIS&#41;](service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="834f8-122">[Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="834f8-123">Usar SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="834f8-123">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
