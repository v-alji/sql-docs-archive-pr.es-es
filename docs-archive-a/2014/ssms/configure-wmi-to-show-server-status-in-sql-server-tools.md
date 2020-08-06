---
title: Configurar WMI para mostrar el estado del servidor en Herramientas de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI Provider for Server Events, setting permissions
- WMI permissions [SQL Server]
ms.assetid: 7e97197b-ed4d-40d1-9a52-9ab1d92401d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 138abbe2b7b819d6afd6da62135f7cd7ce86496f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748470"
---
# <a name="configure-wmi-to-show-server-status-in-sql-server-tools"></a><span data-ttu-id="8eb34-102">Configurar WMI para mostrar el estado del servidor en Herramientas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8eb34-102">Configure WMI to Show Server Status in SQL Server Tools</span></span>
  <span data-ttu-id="8eb34-103">En este tema se describe cómo configurar WMI para mostrar el estado del servidor en herramientas de SQL Server en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8eb34-103">This topic describes how to configure WMI to show the server status in SQL Server tools in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="8eb34-104">Al conectarse a los servidores, los componentes Servidores registrados y Explorador de objetos de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], así como el Administrador de configuración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , usan Instrumental de administración de Windows (WMI) para obtener el estado de los servicios de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) y el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="8eb34-104">When connecting to servers, both the Registered Servers and Object Explorer components of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], as well as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager, use Windows Management Instrumentation (WMI) to obtain the status of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent (MSSQLSERVER) services.</span></span> <span data-ttu-id="8eb34-105">Para mostrar el estado del servicio, el usuario debe tener derechos de acceso remoto al objeto WMI.</span><span class="sxs-lookup"><span data-stu-id="8eb34-105">To display the status of the service, the user must have rights to remotely access the WMI object.</span></span> <span data-ttu-id="8eb34-106">El servidor debe tener WMI instalado para configurar este permiso.</span><span class="sxs-lookup"><span data-stu-id="8eb34-106">The server must have WMI installed to configure this permission.</span></span>  
  
##  <a name="to-configure-wmi-permission"></a><a name="SSMSProcedure"></a><span data-ttu-id="8eb34-107">Para configurar el permiso WMI</span><span class="sxs-lookup"><span data-stu-id="8eb34-107">To configure WMI permission</span></span>  
  
1.  <span data-ttu-id="8eb34-108">En el menú **Inicio** del servidor remoto, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8eb34-108">On the **Start** menu on the remote server, click **Run**.</span></span>  
  
2.  <span data-ttu-id="8eb34-109">En el cuadro **abrir** `wmimgmt.msc` , escriba y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8eb34-109">In the **Open** box type `wmimgmt.msc`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="8eb34-110">En el programa **Windows Management Infrastructure** , haga clic con el botón derecho en **Control WMI (Local)** y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8eb34-110">In the **Windows Management Infrastructure** program, right-click **WMI Control (Local)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8eb34-111">En el cuadro de diálogo **Propiedades de Control WMI (Local)** , en la pestaña **Seguridad** , expanda **Raíz**y, luego, haga clic en **CIMV2**.</span><span class="sxs-lookup"><span data-stu-id="8eb34-111">In the **WMI Control (Local) Properties** dialog box, on the **Security** tab, expand **Root**, and then click **CIMV2**.</span></span>  
  
5.  <span data-ttu-id="8eb34-112">Haga clic en **Seguridad** para abrir el cuadro de diálogo **Seguridad para ROOT\CIMV2** .</span><span class="sxs-lookup"><span data-stu-id="8eb34-112">Click **Security** to open the **Security for ROOT\CIMV2** dialog box.</span></span>  
  
6.  <span data-ttu-id="8eb34-113">Agregue un grupo o un usuario al cuadro **Nombres de grupos o usuarios** y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="8eb34-113">Add a group or user to the **Group or user names** box and select it.</span></span>  
  
7.  <span data-ttu-id="8eb34-114">En el cuadro **Permisos para** _\<group or user>_ , seleccione la columna **Permitir** , para el permiso **Llamada remota habilitada** , para los usuarios que desee que detecten remotamente el estado del servicio.</span><span class="sxs-lookup"><span data-stu-id="8eb34-114">In the **Permissions for**_\<group or user>_ box, select the **Allow** column, for the **Remote Enable** permission, for users whom you wish to remotely detect the service status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb34-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8eb34-115">See Also</span></span>  
 [<span data-ttu-id="8eb34-116">Iniciar, detener o pausar el servicio del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="8eb34-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
