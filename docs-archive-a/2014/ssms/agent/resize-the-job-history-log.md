---
title: Cambiar el tamaño del registro del historial de trabajos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- resizing job history log
- size [SQL Server], job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: ddee1ce8-9d1b-4017-9894-bf7256aed95d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c25cc43295d47b2bc19d48b5b257dbbe6bcfe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671320"
---
# <a name="resize-the-job-history-log"></a><span data-ttu-id="8f0df-102">Resize the Job History Log</span><span class="sxs-lookup"><span data-stu-id="8f0df-102">Resize the Job History Log</span></span>
  <span data-ttu-id="8f0df-103">En este tema se describe cómo establecer límites de tamaño para los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registros de historial de trabajos del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f0df-103">This topic describes how to set size limits for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history logs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="8f0df-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="8f0df-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8f0df-105">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8f0df-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8f0df-106">**Para establecer los límites de tamaño de los registros de historial de trabajos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="8f0df-106">**To set size limits for job history logs, using:**</span></span>  
  
     [<span data-ttu-id="8f0df-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f0df-107">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8f0df-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8f0df-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8f0df-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8f0df-109">Security</span></span>  
 <span data-ttu-id="8f0df-110">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="8f0df-110">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="8f0df-111">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f0df-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-raw-size"></a><span data-ttu-id="8f0df-112">Para cambiar el tamaño del registro de historial de trabajos según un tamaño sin procesar</span><span class="sxs-lookup"><span data-stu-id="8f0df-112">To resize the job history log based on raw size</span></span>  
  
1.  <span data-ttu-id="8f0df-113">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="8f0df-113">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8f0df-114">Haga clic con el botón derecho en **Agente SQL Server**y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8f0df-114">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8f0df-115">Seleccione la página **Historial** y asegúrese de que la opción **Limitar tamaño del registro de historial de trabajos**esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8f0df-115">Select the **History** page, and then confirm that **Limit size of job history log**is checked.</span></span>  
  
4.  <span data-ttu-id="8f0df-116">En la casilla **Tamaño máximo del registro de historial de trabajos (filas)** , escriba el número máximo de filas que debe permitir el registro de historial de trabajos.</span><span class="sxs-lookup"><span data-stu-id="8f0df-116">In the **Maximum job history log size** box, enter the maximum number of rows the job history log should allow.</span></span>  
  
5.  <span data-ttu-id="8f0df-117">En la casilla **Máximo de filas de historial de trabajos por trabajo** , escriba el número máximo de filas que se va a permitir para un trabajo en el historial de trabajos.</span><span class="sxs-lookup"><span data-stu-id="8f0df-117">In the **Maximum job history rows per job** box, enter the maximum number of job history rows to allow for a job.</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-time"></a><span data-ttu-id="8f0df-118">Para cambiar el tamaño del registro de historial de trabajos según el tiempo</span><span class="sxs-lookup"><span data-stu-id="8f0df-118">To resize the job history log based on time</span></span>  
  
1.  <span data-ttu-id="8f0df-119">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="8f0df-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8f0df-120">Haga clic con el botón derecho en **Agente SQL Server**y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8f0df-120">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8f0df-121">Seleccione la página **Historial** y, a continuación, haga clic en **Quitar automáticamente historial del agente**.</span><span class="sxs-lookup"><span data-stu-id="8f0df-121">Select the **History** page, and then click **Automatically remove agent history**.</span></span>  
  
4.  <span data-ttu-id="8f0df-122">Seleccione el número apropiado de **días**, **semanas**o **meses**.</span><span class="sxs-lookup"><span data-stu-id="8f0df-122">Select the appropriate number of **Days(s)**, **Week(s)**, or **Month(s)**.</span></span>  
  
  
