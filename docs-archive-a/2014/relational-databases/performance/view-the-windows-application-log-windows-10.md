---
title: Ver el registro de aplicación Windows (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- application logs [SQL Server]
- logs [SQL Server], application
- monitoring Windows NT application log [SQL Server]
- Windows NT application logs [SQL Server]
- displaying logs
- monitoring [SQL Server], events
- logs [SQL Server], viewing
ms.assetid: 168a6c6e-12df-46a9-9904-55d63ca8fe14
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1255e95833d9fc56abd1700f5acb0d2f49ebf77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745732"
---
# <a name="view-the-windows-application-log-windows"></a><span data-ttu-id="bc353-102">Ver el registro de aplicación Windows (Windows)</span><span class="sxs-lookup"><span data-stu-id="bc353-102">View the Windows Application Log (Windows)</span></span>
  <span data-ttu-id="bc353-103">Si se configura [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para utilizar el registro de aplicación de Windows, todas las sesiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escribirán los nuevos eventos en el registro.</span><span class="sxs-lookup"><span data-stu-id="bc353-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="bc353-104">A diferencia del registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no se crea un nuevo registro de aplicación cada vez que se inicia una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc353-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-the-windows-application-log"></a><span data-ttu-id="bc353-105">Para ver el registro de aplicación Windows</span><span class="sxs-lookup"><span data-stu-id="bc353-105">To view the Windows application log</span></span>  
  
1.  <span data-ttu-id="bc353-106">En el menú **Inicio** , seleccione **Todos los programas**, **Herramientas administrativas**y, a continuación, haga clic en **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="bc353-106">On the **Start** menu, point to **All Programs**, point to **Administrative Tools**, and then click **Event Viewer**.</span></span>  
  
2.  <span data-ttu-id="bc353-107">En el Visor de eventos, haga clic en **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="bc353-107">In Event Viewer, click **Application**.</span></span>  
  
3.  <span data-ttu-id="bc353-108">Los eventos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se identifican con la entrada **MSSQLSERVER**(las instancias con nombre se identifican con **MSSQL$** _<nombre_de_instancia>_ ) en la columna **Origen**.</span><span class="sxs-lookup"><span data-stu-id="bc353-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events are identified by the entry **MSSQLSERVER** (named instances are identified with **MSSQL$**_<instance_name>_) in the **Source** column.</span></span> <span data-ttu-id="bc353-109">Los eventos del Agente SQL Server se identifican con la entrada SQLSERVERAGENT (para las instancias con nombre de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], los eventos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se identifican con **SQLAgent$** \<*instance_name*>).</span><span class="sxs-lookup"><span data-stu-id="bc353-109">SQL Server Agent events are identified by the entry SQLSERVERAGENT (for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events are identified with **SQLAgent$**\<*instance_name*>).</span></span> <span data-ttu-id="bc353-110">Los eventos del servicio Microsoft Search se identifican con la entrada **Microsoft Search**.</span><span class="sxs-lookup"><span data-stu-id="bc353-110">Microsoft Search service events are identified by the entry **Microsoft Search**.</span></span>  
  
4.  <span data-ttu-id="bc353-111">Para ver el registro de otro equipo, haga clic con el botón secundario en **visor de eventos**, haga clic en **conectar con otro equipo** y complete el cuadro de diálogo **seleccionar equipo**.</span><span class="sxs-lookup"><span data-stu-id="bc353-111">To view the log of a different computer, right-click **Event Viewer**, click **Connect to another computer,** and complete the **Select Computer**dialog box.</span></span>  
  
5.  <span data-ttu-id="bc353-112">Opcionalmente, para que solo se muestren los eventos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , en el menú **Ver** , haga clic en **Filtro**y, en la lista **Origen del evento** , seleccione **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="bc353-112">Optionally, to display only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, on the **View** menu click **Filter**, and in the **Event source** list, select **MSSQLSERVER**.</span></span> <span data-ttu-id="bc353-113">Para ver solo los eventos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , seleccione **SQLSERVERAGENT** en la lista **Origen del evento** .</span><span class="sxs-lookup"><span data-stu-id="bc353-113">To view only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events, instead select **SQLSERVERAGENT** in the **Event source** list.</span></span>  
  
6.  <span data-ttu-id="bc353-114">Para ver más información acerca de un evento, haga doble clic en el suceso.</span><span class="sxs-lookup"><span data-stu-id="bc353-114">To view more information about an event, double-click the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc353-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc353-115">See Also</span></span>  
 [<span data-ttu-id="bc353-116">Ver el registro de errores de SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="bc353-116">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
