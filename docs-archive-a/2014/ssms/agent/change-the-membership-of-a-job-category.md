---
title: Cambiar la pertenencia de una categoría de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- members [SQL Server], job categories
ms.assetid: 6a18f7f0-eb50-485f-a9c7-df31ae0f994e
author: stevestein
ms.author: sstein
ms.openlocfilehash: d9ed0db394f63594937ad923734b07fed8050955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677379"
---
# <a name="change-the-membership-of-a-job-category"></a><span data-ttu-id="d46d0-102">Change the Membership of a Job Category</span><span class="sxs-lookup"><span data-stu-id="d46d0-102">Change the Membership of a Job Category</span></span>
  <span data-ttu-id="d46d0-103">En este tema se describe cómo cambiar la pertenencia de la categoría de trabajo en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]u Objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d46d0-103">This topic describes how to change the membership of the job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="d46d0-104">Las categorías de trabajo le ayudan a organizar los trabajos para poder filtrarlos y agruparlos fácilmente.</span><span class="sxs-lookup"><span data-stu-id="d46d0-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="d46d0-105">Puede crear sus propias categorías de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d46d0-105">You can create your own job categories.</span></span> <span data-ttu-id="d46d0-106">También puede cambiar la pertenencia de los trabajos del Agente Microsoft SQL Server en categorías de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d46d0-106">You can also change Microsoft SQL Server Agent jobs membership in job categories.</span></span>  
  
 <span data-ttu-id="d46d0-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d46d0-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d46d0-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="d46d0-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d46d0-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d46d0-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d46d0-110">**Para cambiar la pertenencia a una categoría de trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="d46d0-110">**To change the membership of a job category, using:**</span></span>  
  
     [<span data-ttu-id="d46d0-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d46d0-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="d46d0-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d46d0-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="d46d0-113">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d46d0-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d46d0-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d46d0-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d46d0-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d46d0-115">Security</span></span>  
 <span data-ttu-id="d46d0-116">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="d46d0-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="d46d0-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d46d0-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="d46d0-118">Para cambiar la pertenencia a una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="d46d0-118">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="d46d0-119">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que desea editar una categoría de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d46d0-119">In **Object Explorer**, click the plus sign to expand the server where you want to edit a job category.</span></span>  
  
2.  <span data-ttu-id="d46d0-120">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d46d0-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="d46d0-121">Haga clic con el botón derecho en la carpeta **Trabajos** y seleccione **Administrar categorías de trabajos**.</span><span class="sxs-lookup"><span data-stu-id="d46d0-121">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="d46d0-122">En el cuadro de diálogo **Administrar categorías de trabajos**_nombre_servidor_ , seleccione la categoría de trabajo que desea editar y, luego, haga clic en **Ver trabajos**.</span><span class="sxs-lookup"><span data-stu-id="d46d0-122">In the **Manage Job Categories**_server_name_ dialog box, select the job category that you want to edit, and then click **View Jobs**.</span></span>  
  
5.  <span data-ttu-id="d46d0-123">Active la casilla **Mostrar todos los trabajos** .</span><span class="sxs-lookup"><span data-stu-id="d46d0-123">Select the **Show all jobs** check box.</span></span>  
  
6.  <span data-ttu-id="d46d0-124">Para agregar un trabajo a la categoría, en la cuadrícula principal, active la casilla de la columna **Seleccionar** correspondiente al trabajo.</span><span class="sxs-lookup"><span data-stu-id="d46d0-124">To add a job to the category, in the main grid, select the check box in the **Select** column corresponding to the job.</span></span> <span data-ttu-id="d46d0-125">Para quitar un trabajo de la categoría, desactive la casilla.</span><span class="sxs-lookup"><span data-stu-id="d46d0-125">To remove a job from the category, clear the box.</span></span> <span data-ttu-id="d46d0-126">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d46d0-126">When finished, click **OK**.</span></span>  
  
7.  <span data-ttu-id="d46d0-127">En el cuadro de diálogo **Administrar categorías de trabajos**_nombre_servidor_ .</span><span class="sxs-lookup"><span data-stu-id="d46d0-127">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="d46d0-128">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d46d0-128">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="d46d0-129">Para cambiar la pertenencia a una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="d46d0-129">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="d46d0-130">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d46d0-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d46d0-131">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d46d0-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d46d0-132">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d46d0-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="d46d0-133">Para obtener más información, vea [sp_update_job &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d46d0-133">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="d46d0-134">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d46d0-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="d46d0-135">**Para cambiar la pertenencia a una categoría de trabajo**</span><span class="sxs-lookup"><span data-stu-id="d46d0-135">**To change the membership of a job category**</span></span>  
  
 <span data-ttu-id="d46d0-136">Utilice la clase `JobCategory` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d46d0-136">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
