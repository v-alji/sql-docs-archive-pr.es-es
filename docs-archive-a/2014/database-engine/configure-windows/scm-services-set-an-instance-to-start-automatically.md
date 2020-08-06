---
title: Establecer una instancia de SQL Server para que se inicie automáticamente (Administrador de configuración de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/07/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, automatic startup
- starting SQL Server, automatically
ms.assetid: aa2b6bde-e76d-4fea-a560-54a63745d9b1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2fc21bd881c1588da47710c6d8437e31d3df2ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748914"
---
# <a name="set-an-instance-of-sql-server-to-start-automatically-sql-server-configuration-manager"></a><span data-ttu-id="f12e9-102">Configurar una instancia de SQL Server para que se inicie automáticamente (Administrador de configuración de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f12e9-102">Set an Instance of SQL Server to Start Automatically (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="f12e9-103">En este tema se describe cómo establecer una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que se inicie automáticamente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f12e9-103">This topic describes how to set an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to start automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="f12e9-104">Durante la instalación, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se configura normalmente para iniciarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f12e9-104">During setup, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is normally configured to start automatically.</span></span> <span data-ttu-id="f12e9-105">Si esto no se ha hecho, puede modificar la configuración en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="f12e9-105">If this was not done, you can change that setting at any time.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f12e9-106">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f12e9-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-set-an-instance-of-sql-server-to-start-automatically"></a><span data-ttu-id="f12e9-107">Para configurar que una instancia de SQL Server se inicie automáticamente</span><span class="sxs-lookup"><span data-stu-id="f12e9-107">To set an instance of SQL Server to start automatically</span></span>  
  
1.  <span data-ttu-id="f12e9-108">En el menú **Inicio** , elija **Todos los programas**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Herramientas de configuración**y, por último, **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f12e9-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f12e9-109">Como el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es un complemento del programa [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console y no un programa independiente, el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no aparece como aplicación en las versiones más recientes de Windows.</span><span class="sxs-lookup"><span data-stu-id="f12e9-109">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager does not appear as an application in newer versions of Windows.</span></span>  
    >   
    >  -   <span data-ttu-id="f12e9-110">**Windows 10**:</span><span class="sxs-lookup"><span data-stu-id="f12e9-110">**Windows 10**:</span></span>  
    >          <span data-ttu-id="f12e9-111">Para abrir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, en la **Página de inicio**, escriba SQLServerManager12. msc (para [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="f12e9-111">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, on the **Start Page**, type SQLServerManager12.msc (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="f12e9-112">Para versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , reemplace el 12 por un número inferior.</span><span class="sxs-lookup"><span data-stu-id="f12e9-112">For previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replace 12 with a smaller number.</span></span> <span data-ttu-id="f12e9-113">Al hacer clic en SQLServerManager12.msc, se abre el Administrador de configuración.</span><span class="sxs-lookup"><span data-stu-id="f12e9-113">Clicking SQLServerManager12.msc opens the Configuration Manager.</span></span> <span data-ttu-id="f12e9-114">Para anclar el Configuration Manager a la página de inicio o a la barra de tareas, haga clic con el botón secundario en SQLServerManager12. msc y, a continuación, haga clic en **abrir ubicación de archivo**.</span><span class="sxs-lookup"><span data-stu-id="f12e9-114">To pin the Configuration Manager to the Start Page or Task Bar, right-click SQLServerManager12.msc, and then click **Open file location**.</span></span> <span data-ttu-id="f12e9-115">En el explorador de archivos de Windows, haga clic con el botón secundario en SQLServerManager12. msc y, a continuación, haga clic en **anclar a Inicio** o **anclar a la barra de tareas**.</span><span class="sxs-lookup"><span data-stu-id="f12e9-115">In the Windows File Explorer, right-click SQLServerManager12.msc, and then click **Pin to Start** or **Pin to taskbar**.</span></span>  
    > -   <span data-ttu-id="f12e9-116">**Windows 8**:</span><span class="sxs-lookup"><span data-stu-id="f12e9-116">**Windows 8**:</span></span>  
    >          <span data-ttu-id="f12e9-117">Para abrir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, en el acceso a **Buscar** , en **aplicaciones**, escriba **SQLServerManager \<version> . msc** como y, `SQLServerManager12.msc` a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="f12e9-117">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager\<version>.msc** such as `SQLServerManager12.msc`, and then press **Enter**.</span></span>  
  
2.  <span data-ttu-id="f12e9-118">En el **Administrador de configuración de SQL Server**, expanda **Servicios**y, a continuación, haga clic en **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f12e9-118">In **SQL Server Configuration Manager**, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="f12e9-119">En el panel de detalles, haga clic con el botón derecho en el nombre de la instancia que quiera iniciar automáticamente y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f12e9-119">In the details pane, right-click the name of the instance you want to start automatically, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f12e9-120">En el cuadro de diálogo **Propiedades de \<***instancename***> de SQL Server**, establezca **Modo de inicio** en **Automático**.</span><span class="sxs-lookup"><span data-stu-id="f12e9-120">In the **SQL Server \<***instancename***> Properties** dialog box, set **Start Mode** to **Automatic**.</span></span>  
  
5.  <span data-ttu-id="f12e9-121">Haga clic en **Aceptar**y, a continuación, cierre el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f12e9-121">Click **OK**, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f12e9-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f12e9-122">See Also</span></span>  
 <span data-ttu-id="f12e9-123">[Evitar el inicio automático de una instancia de SQL Server &#40;Administrador de configuración de SQL Server&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span><span class="sxs-lookup"><span data-stu-id="f12e9-123">[Prevent Automatic Startup of an Instance of SQL Server &#40;SQL Server Configuration Manager&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span></span>  
 <span data-ttu-id="f12e9-124">[Conectarse a otro equipo &#40;Administrador de configuración de SQL Server&#41;](scm-services-connect-to-another-computer.md) </span><span class="sxs-lookup"><span data-stu-id="f12e9-124">[Connect to Another Computer &#40;SQL Server Configuration Manager&#41;](scm-services-connect-to-another-computer.md) </span></span>  
 [<span data-ttu-id="f12e9-125">Configurar WMI para mostrar el estado del servidor en Herramientas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f12e9-125">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
