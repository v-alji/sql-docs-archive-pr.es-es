---
title: Establecer el flujo correcto o con errores de los pasos de un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, action flow logic
- successful jobs [SQL Server]
- failed jobs [SQL Server]
- jobs [SQL Server Agent], action flow logic
ms.assetid: 23041ccf-8a07-41d3-85b9-c449a54b7e1e
author: stevestein
ms.author: sstein
ms.openlocfilehash: fddc5820676cb231b6f0cd5f7151e24d8eceaefa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751633"
---
# <a name="set-job-step-success-or-failure-flow"></a><span data-ttu-id="e1a5a-102">Set Job Step Success or Failure Flow</span><span class="sxs-lookup"><span data-stu-id="e1a5a-102">Set Job Step Success or Failure Flow</span></span>
  <span data-ttu-id="e1a5a-103">Al crear [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajos del agente, puede especificar qué acción [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe realizar si se produce un error durante la ejecución del trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-103">When creating [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you can specify what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take if a failure occurs during job execution.</span></span> <span data-ttu-id="e1a5a-104">Tras la resolución correcta o errónea de cada paso del trabajo, determine la acción que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debería realizar.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-104">Determine the action that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take upon the success or failure of each job step.</span></span> <span data-ttu-id="e1a5a-105">A continuación, utilice el siguiente procedimiento para configurar la lógica del flujo de las acciones de los pasos de trabajo mediante el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1a5a-105">Then use the following procedure to configure the job step action flow logic by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
-   <span data-ttu-id="e1a5a-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="e1a5a-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e1a5a-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e1a5a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e1a5a-108">**Para establecer el flujo correcto o con errores de los pasos de un trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="e1a5a-108">**To set job step success or failure flow, using:**</span></span>  
  
     [<span data-ttu-id="e1a5a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1a5a-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e1a5a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1a5a-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="e1a5a-111">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1a5a-111">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="e1a5a-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="e1a5a-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e1a5a-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e1a5a-113">Security</span></span>  
 <span data-ttu-id="e1a5a-114">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e1a5a-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e1a5a-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1a5a-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="e1a5a-116">Para establecer el flujo con éxito o con errores de los pasos de un trabajo</span><span class="sxs-lookup"><span data-stu-id="e1a5a-116">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="e1a5a-117">En el **Explorador de objetos**, expanda **Agente SQL Server**y, a continuación, expanda **Trabajos**.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-117">In **Object Explorer**, expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
2.  <span data-ttu-id="e1a5a-118">Haga clic con el botón derecho en el trabajo que desea modificar y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-118">Right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e1a5a-119">Seleccione la página **Pasos** , haga clic en un paso y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-119">Select the **Steps** page, click a step, and then click **Edit**.</span></span>  
  
4.  <span data-ttu-id="e1a5a-120">En el cuadro de diálogo **Propiedades de paso de trabajo** , seleccione la página **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="e1a5a-120">In the **Job Step Properties** dialog box, select the **Advanced** page.</span></span>  
  
5.  <span data-ttu-id="e1a5a-121">En el cuadro de diálogo **Acción en caso de éxito**, haga clic en la acción que se realizará si el paso del trabajo se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-121">In the **On success action**list, click the action to perform if the job step completes successfully.</span></span>  
  
6.  <span data-ttu-id="e1a5a-122">En el cuadro **Número de reintentos** , escriba el número de veces (entre 0 y 9.999) que se debe repetir el paso del trabajo antes de considerar que ha sido erróneo.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-122">In the **Retry attempts** box, enter the number of times from 0 through 9999 that the job step should be repeated before it is considered to have failed.</span></span> <span data-ttu-id="e1a5a-123">Si escribió un valor superior a 0 en el cuadro **Número de reintentos** , escriba en el cuadro **Intervalo entre intentos (min.)** el número de minutos (entre 1 y 9999) que deben transcurrir antes de volver a realizar el paso del trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-123">If you entered a value greater than 0 in the **Retry attempts** box, enter in the **Retry interval (minutes)** box the number of minutes from 1 through 9999 that must pass before the job step is retried.</span></span>  
  
7.  <span data-ttu-id="e1a5a-124">En la lista **Acción en caso de error** , haga clic en la acción que se realizará si el paso del trabajo no se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-124">In the **On failure action** list, click the action to perform if the job step fails.</span></span>  
  
8.  <span data-ttu-id="e1a5a-125">Si el trabajo es un script de [!INCLUDE[tsql](../../includes/tsql-md.md)] , puede elegir una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e1a5a-125">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="e1a5a-126">En el cuadro **Archivo de salida** , escriba el nombre de un archivo de salida en el que se escribirá la salida del script.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-126">In the **Output file** box, enter the name of an output file to which the script output will be written.</span></span> <span data-ttu-id="e1a5a-127">De forma predeterminada, el archivo se sobrescribe cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-127">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="e1a5a-128">Si no desea que se sobrescriba el archivo de salida, active la casilla **Anexar salida al archivo existente**.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-128">If you do not want the output file overwritten, check **Append output to existing file**.</span></span>  
  
    -   <span data-ttu-id="e1a5a-129">Active la casilla **Registro en tabla** si desea registrar el paso de trabajo en una tabla de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-129">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="e1a5a-130">De forma predeterminada, el contenido de la tabla se sobrescribe cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-130">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="e1a5a-131">Si no desea que se sobrescriba el contenido, active la casilla **Anexar salida a la entrada existente de la tabla**.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-131">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="e1a5a-132">Una vez ejecutado el paso de trabajo ya puede verse el contenido de la tabla haciendo clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-132">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="e1a5a-133">Active la casilla **Incluir salida de paso en historial** si desea que la salida se incluya en el historial de pasos.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-133">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="e1a5a-134">La salida solo se mostrará si no hubo errores.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-134">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="e1a5a-135">Asimismo, la salida puede aparecer truncada.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-135">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="e1a5a-136">Si la lista **Ejecutar como usuario** está disponible, seleccione la cuenta de proxy con las credenciales que utilizará el trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-136">If the **Run as user** list is available, select the proxy account with the credentials that the job will use.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e1a5a-137">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1a5a-137">Using Transact-SQL</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="e1a5a-138">Para establecer el flujo con éxito o con errores de los pasos de un trabajo</span><span class="sxs-lookup"><span data-stu-id="e1a5a-138">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="e1a5a-139">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1a5a-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e1a5a-140">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e1a5a-141">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @on_success_action = 1;  
    GO  
    ```  
  
 <span data-ttu-id="e1a5a-142">Para obtener más información, vea [sp_add_jobstep &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e1a5a-142">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e1a5a-143">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1a5a-143">Using SQL Server Management Objects</span></span>  

### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="e1a5a-144">Para establecer el flujo con éxito o con errores de los pasos de un trabajo</span><span class="sxs-lookup"><span data-stu-id="e1a5a-144">To set job step success or failure flow</span></span>
  
 <span data-ttu-id="e1a5a-145">Utilice la clase `JobStep` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1a5a-145">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="e1a5a-146">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="e1a5a-146">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
