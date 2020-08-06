---
title: Eliminar automáticamente un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- dropping jobs
- SQL Server Agent jobs, removing
- automatic job removal
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 92dbb6da-5919-4bde-9354-d454e9ea3da0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07a10ec4a31d553a548bfecdcba426e3b46a1782
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674542"
---
# <a name="automatically-delete-a-job"></a><span data-ttu-id="8e020-102">Automatically Delete a Job</span><span class="sxs-lookup"><span data-stu-id="8e020-102">Automatically Delete a Job</span></span>
  <span data-ttu-id="8e020-103">En este tema se describe cómo configurar el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para que elimine los trabajos automáticamente cuando se realizan correctamente, con error o se completan mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8e020-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to automatically delete jobs when they succeed, fail, or complete by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="8e020-104">Estas respuestas permiten a los administradores de las bases de datos saber cuándo se completan los trabajos y con qué frecuencia se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="8e020-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="8e020-105">Algunas respuestas de trabajos típicas son:</span><span class="sxs-lookup"><span data-stu-id="8e020-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="8e020-106">Notificar al operador mediante correo electrónico, localizador electrónico o un mensaje de **net send** .</span><span class="sxs-lookup"><span data-stu-id="8e020-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="8e020-107">Use una de estas respuestas de trabajo si el operador debe realizar una acción de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8e020-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="8e020-108">Por ejemplo, si un trabajo de copia de seguridad se realiza correctamente, se debe notificar de ello al operador para que quite la cinta de copia de seguridad y la guarde en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="8e020-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="8e020-109">Escribir un mensaje de evento en el registro de aplicación Windows.</span><span class="sxs-lookup"><span data-stu-id="8e020-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="8e020-110">Puede utilizar esta respuesta solo para trabajos con errores.</span><span class="sxs-lookup"><span data-stu-id="8e020-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="8e020-111">Eliminar automáticamente el trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e020-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="8e020-112">Utilice esta respuesta de trabajo si está seguro de que no necesita volver a ejecutar este trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e020-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="8e020-113">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="8e020-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8e020-114">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="8e020-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8e020-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8e020-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8e020-116">**Para especificar respuestas de trabajos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="8e020-116">**To specify job responses, using:**</span></span>  
  
     [<span data-ttu-id="8e020-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e020-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="8e020-118">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e020-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8e020-119">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8e020-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8e020-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8e020-120">Security</span></span>  
 <span data-ttu-id="8e020-121">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="8e020-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="8e020-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e020-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-automatically-delete-a-job"></a><span data-ttu-id="8e020-123">Para eliminar automáticamente un trabajo</span><span class="sxs-lookup"><span data-stu-id="8e020-123">To automatically delete a job</span></span>  
  
1.  <span data-ttu-id="8e020-124">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="8e020-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8e020-125">Expanda **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que desee editar y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8e020-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8e020-126">Seleccione la página **Notificaciones** .</span><span class="sxs-lookup"><span data-stu-id="8e020-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="8e020-127">Active **Eliminar el trabajo automáticamente**y elija una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8e020-127">Check **Automatically delete job**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="8e020-128">Haga clic en **Cuando el trabajo se realiza correctamente** para eliminar el estado del trabajo cuando se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="8e020-128">Click **When the job succeeds** to delete the job status when it has completed successfully.</span></span>  
  
    -   <span data-ttu-id="8e020-129">Haga clic en **Cuando se produce un error en el trabajo** para eliminar el trabajo cuando no se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="8e020-129">Click **When the job fails** to delete the job when it has completed unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="8e020-130">Haga clic en **Si el trabajo termina** para eliminar el trabajo independientemente del estado de finalización.</span><span class="sxs-lookup"><span data-stu-id="8e020-130">Click **When the job completes** to delete the job regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="8e020-131">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e020-131">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="8e020-132">**Para eliminar automáticamente un trabajo**</span><span class="sxs-lookup"><span data-stu-id="8e020-132">**To automatically delete a job**</span></span>  
  
 <span data-ttu-id="8e020-133">Use la propiedad `DeleteLevel` de la clase `Job` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e020-133">Use the `DeleteLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="8e020-134">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="8e020-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
