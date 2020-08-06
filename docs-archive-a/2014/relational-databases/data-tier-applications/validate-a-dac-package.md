---
title: Validar un paquete de DAC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data-tier application [SQL Server], validate
- data-tier application [SQL Server], compare
- validate DAC
- compare DACs
- data-tier application [SQL Server], view
- view DAC
ms.assetid: 726ffcc2-9221-424a-8477-99e3f85f03bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 078c7bfeef2ff8636243f4853c03de252c7b9289
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677160"
---
# <a name="validate-a-dac-package"></a><span data-ttu-id="4248d-102">Validar un paquete de DAC</span><span class="sxs-lookup"><span data-stu-id="4248d-102">Validate a DAC Package</span></span>
  <span data-ttu-id="4248d-103">Es aconsejable revisar el contenido de un paquete DAC antes de implementarlo en producción y validar las acciones de actualización antes de actualizar una DAC existente.</span><span class="sxs-lookup"><span data-stu-id="4248d-103">It is a good practice to review the contents of a DAC package before deploying it in production, and to validate the upgrade actions before upgrading an existing DAC.</span></span> <span data-ttu-id="4248d-104">Esto es especialmente aconsejable al implementar paquetes que no se desarrollaron en su organización.</span><span class="sxs-lookup"><span data-stu-id="4248d-104">This is especially true when deploying packages that were not developed in your organization.</span></span>  
  
1.  <span data-ttu-id="4248d-105">**Antes de empezar:**  [Requisitos previos](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="4248d-105">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
2.  <span data-ttu-id="4248d-106">**Para actualizar una DAC mediante:**  [Ver el contenido de una DAC](#ViewDACContents), [Ver los cambios de la base de datos](#ViewDBChanges), [Ver las acciones de actualización](#ViewUpgradeActions), [Comparar las DAC](#CompareDACs)</span><span class="sxs-lookup"><span data-stu-id="4248d-106">**To upgrade a DAC, using:**  [View the Contents of a DAC](#ViewDACContents), [View Database Changes](#ViewDBChanges), [View Upgrade Actions](#ViewUpgradeActions), [Compare DACs](#CompareDACs)</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4248d-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4248d-107">Prerequisites</span></span>  
 <span data-ttu-id="4248d-108">Se recomienda no implementar un paquete DAC desde orígenes desconocidos o que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="4248d-108">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="4248d-109">Es posible que estas DAC contengan código malintencionado que podría ejecutar código [!INCLUDE[tsql](../../includes/tsql-md.md)] no deseado o provocar errores al modificar el esquema.</span><span class="sxs-lookup"><span data-stu-id="4248d-109">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="4248d-110">Antes de usar una DAC de un origen desconocido o que no sea de confianza, impleméntela en una instancia de prueba aislada de [!INCLUDE[ssDE](../../includes/ssde-md.md)], ejecute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) en la base de datos y examine también el código en la base de datos, como los procedimientos almacenados u otro código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4248d-110">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], run [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database, and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
##  <a name="view-the-contents-of-a-dac"></a><a name="ViewDACContents"></a> <span data-ttu-id="4248d-111">Ver el contenido de una DAC</span><span class="sxs-lookup"><span data-stu-id="4248d-111">View the Contents of a DAC</span></span>  
 <span data-ttu-id="4248d-112">Hay dos mecanismos para ver el contenido de un paquete de aplicación de capa de datos (DAC).</span><span class="sxs-lookup"><span data-stu-id="4248d-112">There are two mechanisms for viewing the contents of a data-tier application (DAC) package.</span></span> <span data-ttu-id="4248d-113">Puede importar el paquete DAC a un proyecto DAC en SQL Server Developer Tools.</span><span class="sxs-lookup"><span data-stu-id="4248d-113">You can import the DAC package to a DAC project in SQL Server Developer Tools.</span></span> <span data-ttu-id="4248d-114">Puede desempaquetar el contenido del paquete en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="4248d-114">You can unpack the contents of the package to a folder.</span></span>  
  
 <span data-ttu-id="4248d-115">**Ver una DAC en SQL Server Developer Tools**</span><span class="sxs-lookup"><span data-stu-id="4248d-115">**View a DAC in SQL Server Developer Tools**</span></span>  
  
1.  <span data-ttu-id="4248d-116">Abra el menú **Archivo**, seleccione **Nuevo** y, después, **Proyecto...** .</span><span class="sxs-lookup"><span data-stu-id="4248d-116">Open the **File** menu, select **New**, and then select **Project...**.</span></span>  
  
2.  <span data-ttu-id="4248d-117">Seleccione la plantilla de proyecto de **SQL Server** y especifique los valores de **Nombre**, **Ubicación**y **Nombre de solución**.</span><span class="sxs-lookup"><span data-stu-id="4248d-117">Select the **SQL Server** project template, and specify a **Name**, **Location**, and **Solution name**.</span></span>  
  
3.  <span data-ttu-id="4248d-118">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo y seleccione **Propiedades...** .</span><span class="sxs-lookup"><span data-stu-id="4248d-118">In **Solution Explorer**, right click the project node and select **Properties...**.</span></span>  
  
4.  <span data-ttu-id="4248d-119">En la pestaña **Configuración de proyecto** , en la sección **Tipos de salida** , active la casilla **Aplicación de capa de datos (archivo .dacpac)** y, después, cierre el cuadro de diálogo de propiedades.</span><span class="sxs-lookup"><span data-stu-id="4248d-119">On the **Project Settings** tab, in the **Output Types** section, select the **Data-tier Application (.dacpac File)** check box, and then close the properties dialog.</span></span>  
  
5.  <span data-ttu-id="4248d-120">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo de proyecto y seleccione **Importar aplicación de capa de datos...** .</span><span class="sxs-lookup"><span data-stu-id="4248d-120">In **Solution Explorer**, right click the project node and select **Import Data-tier Application...**.</span></span>  
  
6.  <span data-ttu-id="4248d-121">Use el **Explorador de soluciones** para abrir todos los archivos de la DAC, como la directiva de selección de servidor y los scripts previos y posteriores a la implementación.</span><span class="sxs-lookup"><span data-stu-id="4248d-121">Use **Solution Explorer** to open all of the files in the DAC, such as the server selection policy and the pre- and post-deployment scripts.</span></span>  
  
7.  <span data-ttu-id="4248d-122">Use la **Vista de esquema** para revisar todos los objetos en el esquema, especialmente el código en objetos, como funciones o procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="4248d-122">Use the **Schema View** to review all of the objects in the schema, particularly reviewing the code in objects such as functions or stored procedures.</span></span>  
  
 <span data-ttu-id="4248d-123">**Ver una DAC en una carpeta**</span><span class="sxs-lookup"><span data-stu-id="4248d-123">**View a DAC in a Folder**</span></span>  
  
-   <span data-ttu-id="4248d-124">Desempaquete el paquete DAC en una carpeta según las instrucciones de [Unpack a DAC Package](unpack-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="4248d-124">Unpack the DAC package into a folder by following the instructions in [Unpack a DAC Package](unpack-a-dac-package.md).</span></span>  
  
-   <span data-ttu-id="4248d-125">Para ver el contenido de los scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , ábralos en el editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4248d-125">View the contents of the [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts by opening them in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
-   <span data-ttu-id="4248d-126">Vea el contenido de los archivos de texto en herramientas como Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="4248d-126">View the contents of the text files in tools such as notepad.</span></span>  
  
##  <a name="view-database-changes"></a><a name="ViewDBChanges"></a> <span data-ttu-id="4248d-127">Ver los cambios de la base de datos</span><span class="sxs-lookup"><span data-stu-id="4248d-127">View Database Changes</span></span>  
 <span data-ttu-id="4248d-128">Después de que la versión actual de una DAC se haya implementado en producción, los cambios que se pueden haber realizado directamente en la base de datos asociada pueden estar en conflicto con el esquema definido en una nueva versión de la DAC.</span><span class="sxs-lookup"><span data-stu-id="4248d-128">After the current version of a DAC was deployed to production, changes may have been made directly to the associated database that might conflict with the schema defined in a new version of the DAC.</span></span> <span data-ttu-id="4248d-129">Antes de actualizar a una nueva versión de la DAC, compruebe si estos cambios se han realizado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4248d-129">Before upgrading to a new version of the DAC, check to see if such changes have been made to the database.</span></span>  
  
 <span data-ttu-id="4248d-130">**Ver los cambios de la base de datos mediante un asistente**</span><span class="sxs-lookup"><span data-stu-id="4248d-130">**View Database Changes by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="4248d-131">Ejecute el asistente **Actualizar aplicación de capa de datos** , y especifique la DAC implementada actualmente y el paquete DAC que contiene la nueva versión de la DAC.</span><span class="sxs-lookup"><span data-stu-id="4248d-131">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="4248d-132">En la página **Detectar cambio** , revise el informe de los cambios que se han realizado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4248d-132">On the **Detect Change** page, review the report of the changes that have been made to the database.</span></span>  
  
3.  <span data-ttu-id="4248d-133">Seleccione **Cancelar** si no desea continuar con la actualización.</span><span class="sxs-lookup"><span data-stu-id="4248d-133">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="4248d-134">Para obtener más información sobre cómo usar el asistente, vea [Actualizar una aplicación de capa de datos](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="4248d-134">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
### <a name="view-database-changes-by-using-powershell"></a><span data-ttu-id="4248d-135">Ver los cambios de las bases de datos mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="4248d-135">View Database Changes by Using PowerShell</span></span>
  
1.  <span data-ttu-id="4248d-136">Cree un objeto SMO Server y establézcalo en la instancia que contiene la DAC que se va a ver.</span><span class="sxs-lookup"><span data-stu-id="4248d-136">Create a SMO Server object and set it to the instance that contains the DAC to be viewed.</span></span>  
  
2.  <span data-ttu-id="4248d-137">Abra un objeto `ServerConnection` y conéctese a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="4248d-137">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="4248d-138">Especifique el nombre de DAC en una variable.</span><span class="sxs-lookup"><span data-stu-id="4248d-138">Specify the DAC name in a variable.</span></span>  
  
4.  <span data-ttu-id="4248d-139">Use el método `GetDatabaseChanges()` para recuperar un objeto de `ChangeResults` y canalícelo a un archivo de texto para generar un informe simple de objetos nuevos, eliminados y cambiados.</span><span class="sxs-lookup"><span data-stu-id="4248d-139">Use the `GetDatabaseChanges()` method to retrieve a `ChangeResults` object, and pipe the object to a text file to generate a simple report of new, deleted, and changed objects.</span></span>  
  
### <a name="view-database-changes-example-powershell"></a><span data-ttu-id="4248d-140">Ver el ejemplo de cambios de base de datos (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4248d-140">View Database Changes Example (PowerShell)</span></span>
  
 <span data-ttu-id="4248d-141">El ejemplo siguiente informa de los cambios de base de datos que se hayan realizado en una DAC implementada con el nombre MyApplication.</span><span class="sxs-lookup"><span data-stu-id="4248d-141">The following example reports any database changes that have been made in a deployed DAC named MyApplicaiton.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the change list and save to file.  
$dacChanges = $dacstore.GetDatabaseChanges($dacName) | Out-File -Filepath C:\DACScripts\MyApplicationChanges.txt  
```  
  
##  <a name="view-upgrade-actions"></a><a name="ViewUpgradeActions"></a> <span data-ttu-id="4248d-142">Ver las acciones de actualización</span><span class="sxs-lookup"><span data-stu-id="4248d-142">View Upgrade Actions</span></span>  
 <span data-ttu-id="4248d-143">Antes de usar una versión nueva de un paquete DAC para actualizar una DAC que se implementó a partir de un paquete DAC anterior, puede generar un informe que contenga las instrucciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] que se ejecutarán durante la actualización y, después, revisar las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="4248d-143">Before using a new version of a DAC package to upgrade a DAC that was deployed from an earlier DAC package, you can generate a report that contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that will be run during the upgrade, and then review the statements.</span></span>  
  
 <span data-ttu-id="4248d-144">**Acciones de actualización de informe mediante un asistente**</span><span class="sxs-lookup"><span data-stu-id="4248d-144">**Report Upgrade Actions by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="4248d-145">Ejecute el asistente **Actualizar aplicación de capa de datos** , y especifique la DAC implementada actualmente y el paquete DAC que contiene la nueva versión de la DAC.</span><span class="sxs-lookup"><span data-stu-id="4248d-145">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="4248d-146">En la página **Resumen** , revise el informe de las acciones de actualización.</span><span class="sxs-lookup"><span data-stu-id="4248d-146">On the **Summary** page, review the report of the upgrade actions.</span></span>  
  
3.  <span data-ttu-id="4248d-147">Seleccione **Cancelar** si no desea continuar con la actualización.</span><span class="sxs-lookup"><span data-stu-id="4248d-147">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="4248d-148">Para obtener más información sobre cómo usar el asistente, vea [Actualizar una aplicación de capa de datos](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="4248d-148">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
 <span data-ttu-id="4248d-149">**Acciones de actualización de informe mediante PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4248d-149">**Report Upgrade Actions by Using PowerShell**</span></span>  
  
1.  <span data-ttu-id="4248d-150">Cree un objeto SMO Server y establézcalo en la instancia que contiene la DAC implementada.</span><span class="sxs-lookup"><span data-stu-id="4248d-150">Create a SMO Server object and set it to the instance that contains the deployed DAC.</span></span>  
  
2.  <span data-ttu-id="4248d-151">Abra un objeto `ServerConnection` y conéctese a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="4248d-151">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="4248d-152">Use `System.IO.File` para cargar el archivo de paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="4248d-152">Use `System.IO.File` to load the DAC package file.</span></span>  
  
4.  <span data-ttu-id="4248d-153">Especifique el nombre de DAC en una variable.</span><span class="sxs-lookup"><span data-stu-id="4248d-153">Specify the DAC name in a variable.</span></span>  
  
5.  <span data-ttu-id="4248d-154">Use el método `GetIncrementalUpgradeScript()` para obtener una lista de las instrucciones Transact-SQL que ejecutaría una actualización y canalice la lista a un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4248d-154">Use the `GetIncrementalUpgradeScript()` method to get a list of the Transact-SQL statements an upgrade would run, and pipe the list to a text file.</span></span>  
  
6.  <span data-ttu-id="4248d-155">Cierra la secuencia de archivos usada para leer el archivo de paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="4248d-155">Close the file stream used to read the DAC package file.</span></span>  
  
### <a name="view-upgrade-actions-example-powershell"></a><span data-ttu-id="4248d-156">Ver el ejemplo de acciones de actualización (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4248d-156">View Upgrade Actions Example (PowerShell)</span></span>
  
 <span data-ttu-id="4248d-157">En el siguiente ejemplo se proporcionan instrucciones Transact-SQL que se ejecutan para actualizar una DAC denominada MyApplication en el esquema definido en un archivo MyApplicationVNext.dacpac.</span><span class="sxs-lookup"><span data-stu-id="4248d-157">The following example reports the Transact-SQL statements that would be run to upgrading a DAC named MyApplicaiton to the schema defined in a MyApplicationVNext.dacpac file.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Load the DAC package file.  
$dacpacPath = "C:\MyDACs\MyApplicationVNext.dacpac"  
$fileStream = [System.IO.File]::Open($dacpacPath,[System.IO.FileMode]::OpenOrCreate)  
$dacType = [Microsoft.SqlServer.Management.Dac.DacType]::Load($fileStream)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the upgrade script and save to file.  
$dacstore.GetIncrementalUpgradeScript($dacName, $dacType) | Out-File -Filepath C:\DACScripts\MyApplicationUpgrade.sql  
  
## Close the filestream to the new DAC package.  
$fileStream.Close()  
```  
  
##  <a name="compare-dacs"></a><a name="CompareDACs"></a><span data-ttu-id="4248d-158">Comparar DAC</span><span class="sxs-lookup"><span data-stu-id="4248d-158">Compare DACs</span></span>  
 <span data-ttu-id="4248d-159">Antes de actualizar una DAC, es aconsejable revisar las diferencias en la base de datos y los objetos en el nivel de instancia entre la DAC actual y la nueva.</span><span class="sxs-lookup"><span data-stu-id="4248d-159">Before upgrading a DAC, it is a good practice to review the differences in the database and instance-level objects between the current and new DACs.</span></span> <span data-ttu-id="4248d-160">Si no tiene una copia del paquete de la DAC actual, puede extraer un paquete de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="4248d-160">If you do not have a copy of the package for the current DAC, you can extract a package from the current database.</span></span>  
  
 <span data-ttu-id="4248d-161">Si importa ambos paquetes DAC en proyectos DAC en SQL Server Developer Tools, puede usar la herramienta de comparación de esquemas para analizar las diferencias entre las dos DAC.</span><span class="sxs-lookup"><span data-stu-id="4248d-161">If you import both DAC packages into DAC projects in SQL Server Developer Tools, you can use the Schema Compare tool to analyze the differences between the two DACs.</span></span>  
  
 <span data-ttu-id="4248d-162">O bien, desempaquete las DAC en carpetas independientes.</span><span class="sxs-lookup"><span data-stu-id="4248d-162">Alternatively, unpack the DACs into separate folders.</span></span> <span data-ttu-id="4248d-163">A continuación, puede usar una herramienta de diferenciación, como la utilidad WinDiff, para analizar las diferencias.</span><span class="sxs-lookup"><span data-stu-id="4248d-163">You can then use a difference tool, such as the WinDiff utility, to analyze the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4248d-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4248d-164">See Also</span></span>  
 <span data-ttu-id="4248d-165">[Aplicaciones de capa de datos](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="4248d-165">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="4248d-166">[Implementar una aplicación de capa de datos](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="4248d-166">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="4248d-167">Actualizar una aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="4248d-167">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
