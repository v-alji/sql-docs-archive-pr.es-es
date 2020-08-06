---
title: Conectarse a otro equipo (Administrador de configuración de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], other computers
ms.assetid: c4c1e94f-4f5f-431e-8b5b-d5ff97baf723
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3d478cebc1ca36ccb8f87b0355b7c8fe0a928cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677882"
---
# <a name="connect-to-another-computer-sql-server-configuration-manager"></a><span data-ttu-id="bfa2a-102">Conectarse a otro equipo (Administrador de configuración de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bfa2a-102">Connect to Another Computer (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="bfa2a-103">En este tema se describe cómo conectar con otro equipo en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfa2a-103">This topic describes how to connect to another computer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="bfa2a-104">Siga el primer procedimiento para abrir [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (mmc) de Administración de equipos de Windows, conéctese al equipo y expanda el árbol Servicios y Aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-104">Follow the first procedure to open the Windows Computer Management [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (mmc), connect to the computer, and expand the Services and Applications tree.</span></span> <span data-ttu-id="bfa2a-105">Siga el segundo procedimiento para crear un archivo con un vínculo al Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-105">Follow the second procedure to create a file with a link to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bfa2a-106">Algunas acciones no se pueden realizar mediante el Administrador de configuración cuando se conecta de forma remota.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-106">Some actions cannot be performed by Configuration Manager when connecting remotely.</span></span>  
  
 <span data-ttu-id="bfa2a-107">Para iniciar, detener, pausar o reanudar servicios en otro equipo, también puede conectarse al servidor con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], hacer clic con el botón secundario en el servidor o el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y, a continuación, hacer clic en la acción deseada.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-107">To start, stop, pause, or resume services on another computer, you can also connect to the server with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the server or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and then click the desired action.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-connect-to-another-computer-with-windows-computer-management"></a><span data-ttu-id="bfa2a-108">Para conectarse a otro equipo con la Administración de equipos de Windows</span><span class="sxs-lookup"><span data-stu-id="bfa2a-108">To connect to another computer with Windows Computer Management</span></span>  
  
1.  <span data-ttu-id="bfa2a-109">En el menú **Inicio** , haga clic con el botón secundario en **mi PC**y, a continuación, haga clic en **administrar.**</span><span class="sxs-lookup"><span data-stu-id="bfa2a-109">On the **Start** menu, right-click **My Computer**, and then click **Manage.**</span></span>  
  
2.  <span data-ttu-id="bfa2a-110">En **Administración de equipos**, haga clic con el botón secundario en **Administración del equipo (Local)** y, a continuación, haga clic en **Conectar con otro equipo**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-110">In **Computer Management**, right-click **Computer Management (Local)**, and then click **Connect to another computer**.</span></span>  
  
3.  <span data-ttu-id="bfa2a-111">En el cuadro de diálogo **Seleccionar equipo** , en el cuadro de texto **Otro equipo** , escriba el nombre del equipo que desea administrar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-111">In the **Select Computer** dialog box, in the **Another computer** text box, type the name of the computer you want to manage, and then click **OK**.</span></span>  
  
     <span data-ttu-id="bfa2a-112">Administración de equipos muestra los servicios que se ejecutan en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-112">Computer Management displays the services running on the remote computer.</span></span> <span data-ttu-id="bfa2a-113">El nodo de nivel superior cambia a **Administración de equipos** \<*remotecomputer*>.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-113">The top-level node changes to **Computer Management** \<*remotecomputer*>.</span></span>  
  
4.  <span data-ttu-id="bfa2a-114">En el árbol de consola, expanda **Servicios y aplicaciones**y, a continuación, expanda **Administrador de configuración de SQL Server** para administrar los servicios del equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-114">In the console tree, expand **Services and Applications**, and then expand **SQL Server Configuration Manager** to manage the remote computer's services.</span></span>  
  
#### <a name="to-save-a-link-to-sql-server-configuration-manager-for-another-computer"></a><span data-ttu-id="bfa2a-115">Para guardar un vínculo al Administrador de configuración de SQL Server para otro equipo</span><span class="sxs-lookup"><span data-stu-id="bfa2a-115">To save a link to SQL Server Configuration Manager for another computer</span></span>  
  
1.  <span data-ttu-id="bfa2a-116">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-116">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="bfa2a-117">En el cuadro **abrir** , escriba `mmc -a` para abrir la [!INCLUDE[msCoName](../../includes/msconame-md.md)] consola de administración de en modo de autor.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-117">In the **Open** box, type `mmc -a` to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console in author mode.</span></span>  
  
3.  <span data-ttu-id="bfa2a-118">En el menú **Archivo** , haga clic en **Agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-118">On the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
4.  <span data-ttu-id="bfa2a-119">En la ventana **Agregar o quitar complemento** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-119">In the **Add/Remove Snap-in** window, click **Add**.</span></span>  
  
5.  <span data-ttu-id="bfa2a-120">En la ventana **Agregar un complemento independiente** , haga clic en **Administración de equipos** y, después, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-120">In the **Add Standalone Snap-in** window, click **Computer Management** and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="bfa2a-121">En la ventana **Administración de equipos** , haga clic en **Otro equipo**, escriba el nombre del equipo remoto que desea administrar y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-121">In the **Computer Management** window, click **Another computer**, type the name of the remote computer you wish to manage, and then click **Finish**.</span></span>  
  
7.  <span data-ttu-id="bfa2a-122">En la ventana **Agregar un complemento independiente** , haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-122">In the **Add Standalone Snap-in** window, click **Close**.</span></span>  
  
8.  <span data-ttu-id="bfa2a-123">En la ventana **Agregar o quitar complemento** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-123">In the **Add/Remove Snap-in** window, click **OK**.</span></span>  
  
9. <span data-ttu-id="bfa2a-124">Expanda **Administración de equipos ( ***\<computer name>*** )** y **servicios y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-124">Expand **Computer Management (***\<computer name>***)**, and **Services and Applications**.</span></span>  
  
10. <span data-ttu-id="bfa2a-125">Haga clic con el botón derecho en **Administrador de configuración de SQL Server**y, después, haga clic en **Nueva ventana desde aquí**.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-125">Right-click **SQL Server Configuration Manager**, and then click **New Window from here**.</span></span>  
  
11. <span data-ttu-id="bfa2a-126">En el menú **Ventana**, haga clic en **Raíz de consola**para regresar a la primera ventana y eliminar la ventana.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-126">On the **Window** menu, click **Console Root**, to switch back to the first window, and delete the window.</span></span>  
  
12. <span data-ttu-id="bfa2a-127">En el menú **archivo** , haga clic en **Guardar como**y guarde el archivo en la carpeta que desee, con un nombre adecuado con la `.msc` extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-127">On the **File** menu, click **Save As**, and save the file in the desired folder, with an appropriate name with the `.msc` file extension.</span></span> <span data-ttu-id="bfa2a-128">Cierre [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-128">Close the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span>  
  
13. <span data-ttu-id="bfa2a-129">Para abrir el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el equipo de destino, haga doble clic en el archivo.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-129">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on the target computer, double-click the file.</span></span> <span data-ttu-id="bfa2a-130">Si lo desea, guarde un vínculo al archivo en el escritorio o en el menú **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="bfa2a-130">If desired, save a link to the file on the desktop or in the **Start** menu.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="bfa2a-131">Cuando utiliza el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en un equipo remoto, el nombre del equipo no es obvio y es posible que se detenga por error o que se configure el equipo equivocado.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-131">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer, the computer name is not obvious and it is possible to mistakenly stop or configure the wrong computer.</span></span> <span data-ttu-id="bfa2a-132">En la pestaña **Servicio** , marque la casilla **Nombre de host** para confirmar el nombre del equipo antes de modificar un servicio.</span><span class="sxs-lookup"><span data-stu-id="bfa2a-132">On the **Service** tab, check the **Host Name** box to confirm the computer name before modifying a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa2a-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bfa2a-133">See Also</span></span>  
 [<span data-ttu-id="bfa2a-134">Configurar WMI para mostrar el estado del servidor en Herramientas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfa2a-134">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
