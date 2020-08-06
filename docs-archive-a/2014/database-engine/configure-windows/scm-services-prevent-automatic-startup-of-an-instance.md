---
title: Impedir el inicio automático de una instancia de SQL Server (Administrador de configuración de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, stopping
- SQL Server, automatic startup
- canceling automatic startup
- stopping SQL Server
- preventing automatic startups [SQL Server]
ms.assetid: 782663cf-f3d7-4cc6-b621-21e4550f0322
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8f93f5abc749f589ab4208b3a4c9434ca63b8769
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673894"
---
# <a name="prevent-automatic-startup-of-an-instance-of-sql-server-sql-server-configuration-manager"></a><span data-ttu-id="0954c-102">Evitar el inicio automático de una instancia de SQL Server (Administrador de configuración de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0954c-102">Prevent Automatic Startup of an Instance of SQL Server (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="0954c-103">En este tema se describe cómo evitar que una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se inicie automáticamente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0954c-103">This topic describes how prevent an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from starting automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0954c-104">se suele configurar para iniciarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0954c-104">is normally configured to start automatically.</span></span> <span data-ttu-id="0954c-105">Puede cambiar esta configuración estableciendo en manual el modo de inicio de la instancia.</span><span class="sxs-lookup"><span data-stu-id="0954c-105">You can change that by setting the start mode for the instance to manual.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0954c-106">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0954c-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-prevent-automatic-startup-of-an-instance-of-sql-server"></a><span data-ttu-id="0954c-107">Para evitar el inicio automático de una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0954c-107">To prevent automatic startup of an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="0954c-108">En el menú **Inicio** , elija **Todos los programas**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Herramientas de configuración**y, por último, **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0954c-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="0954c-109">En el Administrador de configuración de SQL Server, expanda **Servicios**y haga clic en **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0954c-109">In SQL Server Configuration Manager, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="0954c-110">En el panel de detalles, haga clic con el botón derecho en **MSSQLServer**y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0954c-110">In the details pane, right-click **MSSQLServer**, and then click **Properties.**</span></span>  
  
4.  <span data-ttu-id="0954c-111">En el cuadro de diálogo \*\* \<**_instancename_**> propiedades de SQL Server\*\* , en el cuadro **propiedades** , establezca el valor de **modo de inicio** en **manual**.</span><span class="sxs-lookup"><span data-stu-id="0954c-111">In the **SQL Server \<**_instancename_**> Properties** dialog box, in the **Properties** box, set the value of **Start Mode** to **Manual**.</span></span>  
  
5.  <span data-ttu-id="0954c-112">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Propiedades de \<**_instancename_**> de SQL Server** y, luego, cierre Configuration Manager de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0954c-112">Click **OK** to close the **SQL Server \<**_instancename_**> Properties** dialog box, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0954c-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0954c-113">See Also</span></span>  
 [<span data-ttu-id="0954c-114">Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="0954c-114">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
