---
title: Definir las opciones de pasos de trabajo de Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: b2a47057-f6fb-432b-a7b6-5d61f33a5d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc1d6412e52e74ce0c6d987d6189c0c72ffd7df7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744463"
---
# <a name="define-transact-sql-job-step-options"></a><span data-ttu-id="a81c0-102">Define Transact-SQL Job Step Options</span><span class="sxs-lookup"><span data-stu-id="a81c0-102">Define Transact-SQL Job Step Options</span></span>
  <span data-ttu-id="a81c0-103">En este tema se describe cómo definir opciones para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] los pasos de trabajo del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a81c0-103">This topic describes how to define options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent [!INCLUDE[tsql](../../includes/tsql-md.md)] job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="a81c0-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a81c0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a81c0-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a81c0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a81c0-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a81c0-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a81c0-107">**Para definir las opciones de pasos de trabajo de Transact-SQL con:** ,</span><span class="sxs-lookup"><span data-stu-id="a81c0-107">**To define Transact-SQL job step options, using:** ,</span></span>  
  
     [<span data-ttu-id="a81c0-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a81c0-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="a81c0-109">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a81c0-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a81c0-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a81c0-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a81c0-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a81c0-111">Security</span></span>  
 <span data-ttu-id="a81c0-112">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="a81c0-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="a81c0-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a81c0-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-transact-sql-job-step-options"></a><span data-ttu-id="a81c0-114">Para definir opciones de pasos de trabajo de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a81c0-114">To define Transact-SQL job step options</span></span>  
  
1.  <span data-ttu-id="a81c0-115">En el **Explorador de objetos**, expanda **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que desee editar y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a81c0-115">In **Object Explorer**, expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a81c0-116">Haga clic en la página **Pasos** , seleccione un paso de trabajo y, a continuación, haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="a81c0-116">Click the **Steps** page, click a job step, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="a81c0-117">En el cuadro de diálogo **Propiedades de paso de trabajo** , confirme que el tipo de trabajo es **Script de Transact-SQL (TSQL)** y seleccione la página **Opciones avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="a81c0-117">On the **Job Step Properties** dialog, confirm that the job type is **Transact-SQL script (TSQL)**, and then select the **Advanced** page.</span></span>  
  
4.  <span data-ttu-id="a81c0-118">Especifique la acción para llevar a cabo en caso de que el trabajo sea correcto. Para ello, selecciónela de la lista **Acción en caso de éxito** .</span><span class="sxs-lookup"><span data-stu-id="a81c0-118">Specify an action to take if the job is successful by selecting from the **On success action** list.</span></span>  
  
5.  <span data-ttu-id="a81c0-119">Especifique el número de reintentos escribiendo un número comprendido entre 0 y 9999 en el cuadro **Número de reintentos** .</span><span class="sxs-lookup"><span data-stu-id="a81c0-119">Specify a number of retry attempts by entering a number from 0 to 9999 into the **Retry attempts** box.</span></span>  
  
6.  <span data-ttu-id="a81c0-120">Especifique el intervalo de reintento escribiendo un número de minutos comprendido entre 0 y 9999 en el cuadro **Intervalo de reintento** .</span><span class="sxs-lookup"><span data-stu-id="a81c0-120">Specify a retry interval by entering a number of minutes from 0 to 9999 into the **Retry interval** box.</span></span>  
  
7.  <span data-ttu-id="a81c0-121">En la lista **Acción en caso de error** , elija la acción que se llevará a cabo en caso de que el trabajo genere un error.</span><span class="sxs-lookup"><span data-stu-id="a81c0-121">Specify an action to take if the job fails by choosing from the **On failure action** list.</span></span>  
  
8.  <span data-ttu-id="a81c0-122">Si el trabajo es un script de [!INCLUDE[tsql](../../includes/tsql-md.md)] , puede elegir una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a81c0-122">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="a81c0-123">Escriba el nombre de un **archivo de salida**.</span><span class="sxs-lookup"><span data-stu-id="a81c0-123">Enter the name of an **Output file**.</span></span> <span data-ttu-id="a81c0-124">De forma predeterminada, el archivo se sobrescribe cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a81c0-124">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="a81c0-125">Si no desea que se sobrescriba el archivo de salida, active la casilla **Anexar salida al archivo existente**.</span><span class="sxs-lookup"><span data-stu-id="a81c0-125">If you do not want the output file overwritten, check **Append output to existing file**.</span></span> <span data-ttu-id="a81c0-126">Esta opción solo está disponible para los miembros del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="a81c0-126">This option is only available to members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="a81c0-127">Tenga en cuenta que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] no permite a los usuarios ver archivos arbitrarios del sistema de archivos, por lo que no se puede utilizar [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para ver los registros de los pasos de trabajo que se escriben en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="a81c0-127">Note that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] does not allow users to view arbitrary files on the file system, so you cannot use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to view job step logs that are written to the file system.</span></span>  
  
    -   <span data-ttu-id="a81c0-128">Active la casilla **Registro en tabla** si desea registrar el paso de trabajo en una tabla de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a81c0-128">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="a81c0-129">De forma predeterminada, el contenido de la tabla se sobrescribe cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a81c0-129">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="a81c0-130">Si no desea que se sobrescriba el contenido, active la casilla **Anexar salida a la entrada existente de la tabla**.</span><span class="sxs-lookup"><span data-stu-id="a81c0-130">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="a81c0-131">Una vez ejecutado el paso de trabajo ya puede verse el contenido de la tabla haciendo clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="a81c0-131">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="a81c0-132">Active la casilla **Incluir salida de paso en historial** si desea que la salida se incluya en el historial de pasos.</span><span class="sxs-lookup"><span data-stu-id="a81c0-132">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="a81c0-133">La salida solo se mostrará si no hubo errores.</span><span class="sxs-lookup"><span data-stu-id="a81c0-133">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="a81c0-134">Asimismo, la salida puede aparecer truncada.</span><span class="sxs-lookup"><span data-stu-id="a81c0-134">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="a81c0-135">Si es miembro del rol fijo de servidor **sysadmin** y desea ejecutar este paso de trabajo con otro inicio de sesión de SQL, seleccione el inicio de sesión de SQL en la lista **Ejecutar como usuario** .</span><span class="sxs-lookup"><span data-stu-id="a81c0-135">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="a81c0-136">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a81c0-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="a81c0-137">**Para definir opciones de pasos de trabajo de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="a81c0-137">**To define Transact-SQL job step options**</span></span>  
  
 <span data-ttu-id="a81c0-138">Utilice la clase `JobStep` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a81c0-138">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
