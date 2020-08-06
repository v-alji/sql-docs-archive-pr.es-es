---
title: Ver información de pasos de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- displaying job step information
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- viewing job step information
ms.assetid: e3f06492-dc86-4e06-b186-ea58aff6d591
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d9fc6a006884bc564b5db2bfa8b168c8ae59149
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661799"
---
# <a name="view-job-step-information"></a><span data-ttu-id="979b6-102">View Job Step Information</span><span class="sxs-lookup"><span data-stu-id="979b6-102">View Job Step Information</span></span>
  <span data-ttu-id="979b6-103">Este tema explica cómo ver detalles de pasos de trabajo en el cuadro de diálogo Propiedades de paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="979b6-103">This topic describes how to view job step details in the Job Step Properties dialog.</span></span> <span data-ttu-id="979b6-104">También incluye información sobre cómo ver la salida de pasos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="979b6-104">It also includes information about viewing job step output.</span></span>  
  
-   <span data-ttu-id="979b6-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="979b6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="979b6-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="979b6-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="979b6-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="979b6-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="979b6-108">**Para ver información de pasos de trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="979b6-108">**To view job step information, using:**</span></span>  
  
     [<span data-ttu-id="979b6-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="979b6-109">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="979b6-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="979b6-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="979b6-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="979b6-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="979b6-112">Si el paso de trabajo está configurado para escribir la salida en una tabla o un archivo y se ha ejecutado el trabajo al menos una vez, puede ver la salida en la página **Avanzadas** del cuadro de diálogo **Propiedades de paso de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="979b6-112">If the job step has been configured to write its output to a table or file and the job has run at least once, you can view its output on the **Advanced** page of the **Job Step Properties** dialog.</span></span> <span data-ttu-id="979b6-113">Cuando se elimina un trabajo o un paso de trabajo, el registro de salida se elimina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="979b6-113">When a job or job step is deleted, the output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="979b6-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="979b6-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="979b6-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="979b6-115">Permissions</span></span>  
 <span data-ttu-id="979b6-116">Puede ver únicamente los pasos de trabajo de su propiedad, a menos que sea miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="979b6-116">You can view only those jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="979b6-117">Los miembros de este rol pueden ver todos los trabajos y detalles de pasos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="979b6-117">Members of this role can view all jobs and job step details.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="979b6-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="979b6-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-step-information"></a><span data-ttu-id="979b6-119">Para ver información de pasos de trabajo</span><span class="sxs-lookup"><span data-stu-id="979b6-119">To view job step information</span></span>  
  
1.  <span data-ttu-id="979b6-120">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="979b6-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="979b6-121">Expanda **Agente SQL Server**, **Trabajos**, haga clic con el botón derecho en el trabajo que contiene el paso de trabajo que desea ver y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="979b6-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that contains the job step to be viewed, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="979b6-122">En el cuadro de diálogo **Propiedades del trabajo** , haga clic en la página **Pasos** .</span><span class="sxs-lookup"><span data-stu-id="979b6-122">In the **Job Properties** dialog, click the **Steps** page.</span></span>  
  
4.  <span data-ttu-id="979b6-123">Haga clic en el paso de trabajo que desea ver y después en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="979b6-123">Click the job step to be viewed, and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="979b6-124">En la página **General** del cuadro de diálogo **Propiedades de paso de trabajo** , puede ver el tipo de paso de trabajo y lo que hace.</span><span class="sxs-lookup"><span data-stu-id="979b6-124">On the **General** page of the **Job Step Properties** dialog, you can view the type of job step and what it does.</span></span>  
  
6.  <span data-ttu-id="979b6-125">Haga clic en la página **Avanzadas** para ver las acciones que realiza el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si el paso de trabajo progresa o no progresa, cuántas veces se debe intentar el paso de trabajo, dónde se escribe la salida del paso de trabajo y el usuario con el que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="979b6-125">Click the **Advanced** page to view the actions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent takes if the job step succeeds or fails, how many times the job step should be attempted, where the job step output is written, and the user the job step runs as.</span></span>  
  
#### <a name="to-view-job-step-output"></a><span data-ttu-id="979b6-126">Para ver la salida de un paso de trabajo</span><span class="sxs-lookup"><span data-stu-id="979b6-126">To view job step output</span></span>  
  
1.  <span data-ttu-id="979b6-127">En el cuadro de diálogo **Propiedades de paso de trabajo** , haga clic en la página **Avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="979b6-127">In the **Job Step Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="979b6-128">Dependiendo de la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a la que esté conectado, puede ver el archivo o la tabla de salida del paso de trabajo como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="979b6-128">Depending on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connected to, you can view either the job step output file or table as follows:</span></span>  
  
    -   <span data-ttu-id="979b6-129">Si está conectado a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o posterior, haga clic en **Ver** solo si está seleccionada la opción **Registro en tabla** .</span><span class="sxs-lookup"><span data-stu-id="979b6-129">When you are connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later, you can click **View** only when **Log to table** is checked.</span></span> <span data-ttu-id="979b6-130">En este caso, la salida del paso de trabajo se escribe en la tabla **sysjobstepslogs** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="979b6-130">In this case, the job step output is written to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
    -   <span data-ttu-id="979b6-131">El botón **Ver** se deshabilita cuando la salida del paso de trabajo se escribe en un archivo.</span><span class="sxs-lookup"><span data-stu-id="979b6-131">The **View** button is disabled when job step output is written to a file.</span></span> <span data-ttu-id="979b6-132">Para ver el archivo de salida de un paso de trabajo, use el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="979b6-132">To view a job step output file, use Notepad.</span></span>  
  
  
