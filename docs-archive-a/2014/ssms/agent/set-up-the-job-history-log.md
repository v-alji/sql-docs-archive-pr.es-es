---
title: Configurar el registro de historial de trabajos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 018e5c49-d3a0-4504-851a-f70996a34bb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb42e1daaee8a3a9e5ae9cc3c09a8cc42dcbff56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743903"
---
# <a name="set-up-the-job-history-log"></a><span data-ttu-id="5c59e-102">Set Up the Job History Log</span><span class="sxs-lookup"><span data-stu-id="5c59e-102">Set Up the Job History Log</span></span>
  <span data-ttu-id="5c59e-103">En este tema se describe cómo configurar el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registro de historial de trabajos del agente.</span><span class="sxs-lookup"><span data-stu-id="5c59e-103">This topic describes how to set up the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>  
  
-   <span data-ttu-id="5c59e-104">**Antes de empezar:**  [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="5c59e-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="5c59e-105">**Configuración del registro de historial de trabajos usando lo siguiente:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="5c59e-105">**To setup the job history log, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5c59e-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5c59e-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5c59e-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5c59e-107">Security</span></span>  
 <span data-ttu-id="5c59e-108">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="5c59e-108">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="5c59e-109">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c59e-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5c59e-110">**Para configurar el registro de historial de trabajos**</span><span class="sxs-lookup"><span data-stu-id="5c59e-110">**To set up the job history log**</span></span>  
  
1.  <span data-ttu-id="5c59e-111">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="5c59e-111">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5c59e-112">Haga clic con el botón derecho en **Agente SQL Server**y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-112">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5c59e-113">En el cuadro de diálogo **Propiedades de Agente SQL Server** , seleccione la página **Historial** .</span><span class="sxs-lookup"><span data-stu-id="5c59e-113">In the **SQL Server Agent Properties** dialog box, select the **History** page.</span></span>  
  
4.  <span data-ttu-id="5c59e-114">Elija entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5c59e-114">Choose from the following options:</span></span>  
  
    1.  <span data-ttu-id="5c59e-115">Seleccione **Limitar tamaño del registro de historial de trabajos**y, a continuación, escriba el número máximo de filas del registro y el número máximo de filas por trabajo.</span><span class="sxs-lookup"><span data-stu-id="5c59e-115">Check **Limit size of job history log**, and then type the maximum number of rows for the job history log, and the maximum number of rows per job.</span></span>  
  
    2.  <span data-ttu-id="5c59e-116">Seleccione **Quitar automáticamente historial del agente**y especifique un período de tiempo para que se elimine del registro la información anterior al mismo.</span><span class="sxs-lookup"><span data-stu-id="5c59e-116">Check **Automatically remove agent history**, and specify a time period, such that history older than this period will be purged from the log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c59e-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c59e-117">See Also</span></span>  
 <span data-ttu-id="5c59e-118">[Implementar trabajos](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="5c59e-118">[Implement Jobs](implement-jobs.md) </span></span>  
 <span data-ttu-id="5c59e-119">[Actividad supervisar trabajo](monitor-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="5c59e-119">[Monitor Job Activity](monitor-job-activity.md) </span></span>  
 [<span data-ttu-id="5c59e-120">Crear trabajos</span><span class="sxs-lookup"><span data-stu-id="5c59e-120">Create Jobs</span></span>](create-jobs.md)  
  
  
