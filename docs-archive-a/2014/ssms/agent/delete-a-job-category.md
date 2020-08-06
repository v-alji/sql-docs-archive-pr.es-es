---
title: Eliminar una categoría de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- deleting job category
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- removing job category
ms.assetid: 47a7640b-20b3-4639-ab37-b6fc73575e6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: e96dd0461f3dace138b7822cdbaaa2fa242e2cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744462"
---
# <a name="delete-a-job-category"></a><span data-ttu-id="025d0-102">Eliminar una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="025d0-102">Delete a Job Category</span></span>
  <span data-ttu-id="025d0-103">En este tema se describe cómo eliminar una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] categoría de trabajo del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="025d0-103">This topic describes how to delete a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="025d0-104">Las categorías de trabajo le ayudan a organizar los trabajos para poder filtrarlos y agruparlos fácilmente.</span><span class="sxs-lookup"><span data-stu-id="025d0-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="025d0-105">Por ejemplo, puede organizar todos los trabajos de copia de seguridad de las bases de datos en la categoría Mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="025d0-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span>  

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="025d0-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="025d0-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="025d0-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="025d0-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="025d0-108">Al eliminar una categoría de trabajo definida por el usuario, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] le solicita que vuelva a asignar los trabajos asignados a ella a otra categoría de trabajo.</span><span class="sxs-lookup"><span data-stu-id="025d0-108">When you delete a user-defined job category, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent prompts you to reassign the jobs that are assigned to it to another job category.</span></span> <span data-ttu-id="025d0-109">Solo puede eliminar categorías de trabajo definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="025d0-109">You can only delete user-defined job categories.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="025d0-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="025d0-110">Security</span></span>  
 <span data-ttu-id="025d0-111">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="025d0-111">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="025d0-112">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="025d0-112">Using SQL Server Management Studio</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="025d0-113">Para eliminar una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="025d0-113">To delete a job category</span></span>  
  
1.  <span data-ttu-id="025d0-114">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que desea eliminar una categoría de trabajo.</span><span class="sxs-lookup"><span data-stu-id="025d0-114">In **Object Explorer**, click the plus sign to expand the server where you want to delete a job category.</span></span>  
  
2.  <span data-ttu-id="025d0-115">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="025d0-115">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="025d0-116">Haga clic con el botón derecho en la carpeta **Trabajos** y seleccione **Administrar categorías de trabajos**.</span><span class="sxs-lookup"><span data-stu-id="025d0-116">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="025d0-117">En el cuadro de diálogo **Administrar categorías de trabajos**_nombre_servidor_ , seleccione la categoría de trabajo que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="025d0-117">In the **Manage Job Categories**_server_name_ dialog box, select the job category to delete.</span></span>  
  
5.  <span data-ttu-id="025d0-118">Haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="025d0-118">Click **Delete**.</span></span>  
  
6.  <span data-ttu-id="025d0-119">En el cuadro de diálogo **Categorías de trabajo** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="025d0-119">In the **Job Categories** dialog box, click **Yes**.</span></span>  
  
7.  <span data-ttu-id="025d0-120">En el cuadro de diálogo **Administrar categorías de trabajos**_nombre_servidor_ .</span><span class="sxs-lookup"><span data-stu-id="025d0-120">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="025d0-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="025d0-121">Using Transact-SQL</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="025d0-122">Para eliminar una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="025d0-122">To delete a job category</span></span>  
  
1.  <span data-ttu-id="025d0-123">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="025d0-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="025d0-124">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="025d0-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="025d0-125">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="025d0-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- deletes the job category named AdminJobs.  
    USE msdb ;  
    GO   
    EXEC dbo.sp_delete_category  
        @name = N'AdminJobs',  
        @class = N'JOB' ;  
    GO  
    ```  
  
 <span data-ttu-id="025d0-126">Para obtener más información, vea [sp_delete_category &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="025d0-126">For more information, see [sp_delete_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span></span>  

  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="025d0-127">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="025d0-127">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-a-job-category"></a><span data-ttu-id="025d0-128">Para eliminar una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="025d0-128">To delete a job category</span></span>
  
 <span data-ttu-id="025d0-129">Llame a la clase `JobCategory` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="025d0-129">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
