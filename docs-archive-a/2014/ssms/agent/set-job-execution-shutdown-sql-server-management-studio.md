---
title: Configurar el cierre de la ejecución de trabajos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
- SQL Server Agent jobs, execution shutdowns
ms.assetid: ac23e88f-53fc-41de-bb16-0c27c002d5a5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0e60807676c3c54faf1d44de318ff0a31c2e20b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676310"
---
# <a name="set-job-execution-shutdown-sql-server-management-studio"></a><span data-ttu-id="17318-102">Configurar el cierre de la ejecución de trabajos (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="17318-102">Set Job Execution Shutdown (SQL Server Management Studio)</span></span>
  <span data-ttu-id="17318-103">En este tema se describe cómo establecer el tiempo que el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente esperará a que finalice la ejecución de los trabajos antes de que el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] propio agente finalice en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="17318-103">This topic describes how to set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="17318-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="17318-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="17318-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="17318-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="17318-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="17318-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="17318-107">**Para establecer un tiempo de cierre para un trabajo del Agente SQL Server, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="17318-107">**To set a shutdown time for a SQL Server Agent job, using:**</span></span>  
  
     [<span data-ttu-id="17318-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17318-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="17318-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="17318-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="17318-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="17318-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="17318-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="17318-111">Permissions</span></span>  
 <span data-ttu-id="17318-112">De forma predeterminada, los miembros del rol fijo de servidor **sysadmin** pueden establecer el tiempo que el Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esperará a que finalice la ejecución de los trabajos antes de que el propio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finalice.</span><span class="sxs-lookup"><span data-stu-id="17318-112">By default, members of the **sysadmin** fixed server role can set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span> <span data-ttu-id="17318-113">Al resto de usuarios se les debe conceder uno de los siguientes roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la base de datos **msdb** :</span><span class="sxs-lookup"><span data-stu-id="17318-113">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="17318-114">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="17318-114">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="17318-115">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="17318-115">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="17318-116">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="17318-116">**SQLAgentOperatorRole**</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="17318-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17318-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-execution-shutdown"></a><span data-ttu-id="17318-118">Para configurar el cierre de la ejecución de trabajos</span><span class="sxs-lookup"><span data-stu-id="17318-118">To set job execution shutdown</span></span>  
  
1.  <span data-ttu-id="17318-119">En **El Explorador de objetos** , haga clic en el signo más para expandir el servidor en el que desea establecer un intervalo de cierre de la ejecución de trabajos.</span><span class="sxs-lookup"><span data-stu-id="17318-119">In **Object Explorer,** , click the plus sign to expand the server where you want to set a job execution shutdown interval.</span></span>  
  
2.  <span data-ttu-id="17318-120">Haga clic con el botón derecho en **Agente SQL Server** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="17318-120">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="17318-121">En **Seleccionar una página**, seleccione **Sistema de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="17318-121">Under **Select a page**, select **Job System**.</span></span>  
  
4.  <span data-ttu-id="17318-122">Configure **Intervalo de tiempo de espera de cierre** en segundos para aumentar o reducir dicho intervalo.</span><span class="sxs-lookup"><span data-stu-id="17318-122">Set the **Shutdown time-out interval** in seconds to increase or decrease the shutdown time-out interval.</span></span> <span data-ttu-id="17318-123">Así se determina el tiempo que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] va a esperar a que finalice la ejecución de los trabajos antes de que se cierre el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="17318-123">This determines how long [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span>  
  
  
