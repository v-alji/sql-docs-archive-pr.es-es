---
title: Crear una categoría de trabajo | Microsoft Docs
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
ms.assetid: e24a6d38-d231-4f64-ab89-2d1ef6f5792c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f6daeeca6253861e8a9dcbb72faa2bd55eb2761
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747880"
---
# <a name="create-a-job-category"></a><span data-ttu-id="2b840-102">Crear una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="2b840-102">Create a Job Category</span></span>
  <span data-ttu-id="2b840-103">En este tema se describe cómo crear una categoría de trabajo en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] u Objetos de administración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b840-103">This topic describes how to create a job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2b840-104">El Agente proporciona categorías de trabajo integradas a las que puede asignar trabajos, o bien puede crear una categoría de trabajo y asignarle trabajos.</span><span class="sxs-lookup"><span data-stu-id="2b840-104">Agent provides built-in job categories that you can assign jobs to, or you can create a job category and assign jobs to it.</span></span> <span data-ttu-id="2b840-105">Las categorías de trabajo le ayudan a organizar los trabajos para poder filtrarlos y agruparlos fácilmente.</span><span class="sxs-lookup"><span data-stu-id="2b840-105">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="2b840-106">Por ejemplo, puede organizar todos los trabajos de copia de seguridad de las bases de datos en la categoría Mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2b840-106">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="2b840-107">También puede crear sus propias categorías.</span><span class="sxs-lookup"><span data-stu-id="2b840-107">You can also create your own job categories.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2b840-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2b840-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2b840-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2b840-109">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2b840-110">Las categorías multiservidor existen solo en los servidores maestros.</span><span class="sxs-lookup"><span data-stu-id="2b840-110">Multiserver categories exist only on a master server.</span></span> <span data-ttu-id="2b840-111">Solo hay una categoría de trabajo predeterminada disponible en un servidor maestro: [**Sin categoría (Multiservidor)**].</span><span class="sxs-lookup"><span data-stu-id="2b840-111">There is only one default job category available on a master server: [**Uncategorized (Multi-Server)**].</span></span> <span data-ttu-id="2b840-112">Cuando se descarga un trabajo multiservidor, su categoría se cambia a **Trabajos del servidor principal** en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="2b840-112">When a multiserver job is downloaded, its category is changed to **Jobs From MSX** at the target server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2b840-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2b840-113">Security</span></span>  
 <span data-ttu-id="2b840-114">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="2b840-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="2b840-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2b840-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="2b840-116">Para crear una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="2b840-116">To create a job category</span></span>  
  
1.  <span data-ttu-id="2b840-117">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que desea crear una categoría de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2b840-117">In **Object Explorer**, click the plus sign to expand the server where you want to create a job category.</span></span>  
  
2.  <span data-ttu-id="2b840-118">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2b840-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="2b840-119">Haga clic con el botón derecho en la carpeta **Trabajos** y seleccione **Administrar categorías de trabajos**.</span><span class="sxs-lookup"><span data-stu-id="2b840-119">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="2b840-120">En el cuadro de diálogo **Administrar categorías de trabajo**_nombre_servidor_ , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2b840-120">In the **Manage Job Categories**_server_name_ dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="2b840-121">En el nuevo cuadro de diálogo, en el cuadro **Nombre** , especifique un nombre para la nueva categoría de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2b840-121">In the new dialog box, in the **Name** box, enter a name for the new job category.</span></span>  
  
6.  <span data-ttu-id="2b840-122">Active la casilla **Mostrar todos los trabajos** .</span><span class="sxs-lookup"><span data-stu-id="2b840-122">Select the **Show all jobs** check box.</span></span> <span data-ttu-id="2b840-123">Seleccione uno o varios trabajos para la nueva categoría activando las casillas correspondientes a los trabajos.</span><span class="sxs-lookup"><span data-stu-id="2b840-123">Select one or more jobs for the new category by checking the boxes corresponding to the jobs.</span></span>  
  
7.  <span data-ttu-id="2b840-124">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b840-124">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="2b840-125">En el cuadro de diálogo **Administrar categorías de trabajo**_server_name_ , haga clic en **Actualizar** para asegurarse de que la nueva categoría de trabajo esté activa.</span><span class="sxs-lookup"><span data-stu-id="2b840-125">In the **Manage Job Categories**_server_name_ dialog box, click **Refresh** to ensure that the new job category is active.</span></span> <span data-ttu-id="2b840-126">Si todo se busca conforme a lo esperado, cierre este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2b840-126">If everything looks as expected, close this dialog box.</span></span>  
  
 <span data-ttu-id="2b840-127">Para obtener más información sobre estos cuadros de diálogo, vea categorías de trabajos [: administrar categorías de trabajo](job-categories-manage-job-categories.md) y [propiedades de categorías de trabajos y nueva categoría de trabajo](job-categories-properties-new-job-category.md).</span><span class="sxs-lookup"><span data-stu-id="2b840-127">For more information on these dialog boxes, see [Job Categories: Manage Job Categories](job-categories-manage-job-categories.md) and [Job Categories Properties and New Job Category](job-categories-properties-new-job-category.md).</span></span>  

##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="2b840-128">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b840-128">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="2b840-129">Para crear una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="2b840-129">To create a job category</span></span>  
  
1.  <span data-ttu-id="2b840-130">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b840-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2b840-131">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2b840-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2b840-132">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2b840-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a local job category named AdminJobs   
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_category  
        @class=N'JOB',  
        @type=N'LOCAL',  
        @name=N'AdminJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="2b840-133">Para obtener más información, vea [sp_add_category &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2b840-133">For more information, see [sp_add_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="2b840-134">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2b840-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="2b840-135">**Para crear una categoría de trabajo**</span><span class="sxs-lookup"><span data-stu-id="2b840-135">**To create a job category**</span></span>  
  
 <span data-ttu-id="2b840-136">Llame a la clase `JobCategory` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b840-136">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="2b840-137">Para el código de ejemplo, consulte [Programar tareas administrativas automáticas en el Agente SQL Server](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="2b840-137">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
