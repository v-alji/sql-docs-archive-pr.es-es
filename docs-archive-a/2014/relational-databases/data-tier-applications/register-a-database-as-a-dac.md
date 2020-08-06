---
title: Registro de una base de datos como una DAC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerdacwizard.registerdac.f1
- sql12.swb.registerdacwizard.summary.f1
- sql12.swb.registerdacwizard.introduction.f1
- sql12.swb.registerdacwizard.setproperties.f1
helpviewer_keywords:
- wizard [DAC], register
- How to [DAC], register
- register DAC
- data-tier application [SQL Server], register
ms.assetid: 08e52aa6-12f3-41dd-a793-14b99a083fd5
author: stevestein
ms.author: sstein
ms.openlocfilehash: c4e8061362d013dbfbd6cbaba47d0f2cb4d8e83b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677675"
---
# <a name="register-a-database-as-a-dac"></a><span data-ttu-id="86a68-102">Registrar una base de datos como una DAC</span><span class="sxs-lookup"><span data-stu-id="86a68-102">Register a Database As a DAC</span></span>
  <span data-ttu-id="86a68-103">Use el **Asistente para registrar aplicación de capa de datos** o un script de Windows PowerShell para compilar una definición de aplicación de capa de datos (DAC) que describa los objetos de una base de datos existente y registre la definición de la DAC en la base de datos `msdb` del sistema (**maestra** en [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="86a68-103">Use either the **Register Data-tier Application Wizard** or a Windows PowerShell script to build a data-tier application (DAC) definition that describes the objects in an existing database, and register the DAC definition in the `msdb` system database (**master** in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]).</span></span>  
  
-   <span data-ttu-id="86a68-104">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="86a68-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="86a68-105">**Para actualizar una DAC mediante:**  [el Asistente para registrar aplicación de capa de datos](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="86a68-105">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="86a68-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="86a68-106">Before You Begin</span></span>  
 <span data-ttu-id="86a68-107">El proceso de registro crea una definición de DAC que define los objetos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="86a68-107">The registration process creates a DAC definition that defines the objects in the database.</span></span> <span data-ttu-id="86a68-108">La combinación de la definición de DAC y la base de datos forma una instancia de DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-108">The combination of the DAC definition and the database form a DAC instance.</span></span> <span data-ttu-id="86a68-109">Si registra una base de datos como una DA CONTINUACIÓN en una instancia administrada del motor de base de datos, la DAC registrada se incorporará a la Utilidad de SQL Server la próxima vez que el conjunto de recopilación de utilidades se envíe desde la instancia al punto de control de la utilidad.</span><span class="sxs-lookup"><span data-stu-id="86a68-109">If you register a database as a DAC on a managed instance of the Database Engine, the registered DAC will be incorporated into the SQL Server Utility the next time the utility collection set is sent from the instance to the Utility Control Point.</span></span> <span data-ttu-id="86a68-110">Posteriormente, la DAC aparecerá en el nodo **Aplicaciones de capa de datos implementadas** del [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Explorador de la utilidad** y se notificará en la página de detalles **Aplicaciones de capa de datos implementadas**.</span><span class="sxs-lookup"><span data-stu-id="86a68-110">The DAC will then be present in the **Deployed Data-tier Applications** node of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Utility Explorer** and reported in the **Deployed Data-tier Applications** details page.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="86a68-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="86a68-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="86a68-112">El registro de la DAC solo se puede realizar en una base de datos en [!INCLUDE[ssSDS](../../includes/sssds-md.md)]o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) o posterior.</span><span class="sxs-lookup"><span data-stu-id="86a68-112">DAC registration can only be performed on a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span> <span data-ttu-id="86a68-113">El registro de la DAC no se puede llevar a cabo si una DAC ya está registrada en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="86a68-113">DAC registration cannot be performed if a DAC is already registered for the database.</span></span> <span data-ttu-id="86a68-114">Por ejemplo, si la base de datos se creó implementando una DAC, no puede ejecutar el **Asistente para registrar aplicación de capa de datos**.</span><span class="sxs-lookup"><span data-stu-id="86a68-114">For example, if the database was created by deploying a DAC, you cannot run the **Register Data-tier Application Wizard**.</span></span>  
  
 <span data-ttu-id="86a68-115">No puede registra ninguna DAC si la base de datos tiene objetos que no se admiten en una DAC o usuarios contenidos.</span><span class="sxs-lookup"><span data-stu-id="86a68-115">You cannot register a DAC if the database has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="86a68-116">Para obtener más información acerca de los objetos admitidos por una DAC, vea [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="86a68-116">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="86a68-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="86a68-117">Permissions</span></span>  
 <span data-ttu-id="86a68-118">El registro de una DAC en una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] requiere, por lo menos, permisos ALTER ANY LOGIN y DEFINITION VIEW en el ámbito de la base de datos, permisos SELECT en **sys.sql_expression_dependencies**y pertenencia al rol fijo de servidor **dbcreator** .</span><span class="sxs-lookup"><span data-stu-id="86a68-118">Registering a DAC in an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, SELECT permissions on **sys.sql_expression_dependencies**, and membership in the **dbcreator** fixed server role.</span></span> <span data-ttu-id="86a68-119">Los miembros del rol fijo de servidor **sysadmin** o la cuenta de administrador del sistema de SQL Server integrada denominada **sa** también pueden registrar una DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-119">Members of the **sysadmin** fixed server role or the built-in SQL Server system administrator account named **sa** can also register a DAC.</span></span> <span data-ttu-id="86a68-120">El registro de una DAC que no tiene inicios de sesión en [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requiere la pertenencia a los roles **dbmanager** o **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="86a68-120">Registering a DAC that does not contain logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **dbmanager** or **serveradmin** roles.</span></span> <span data-ttu-id="86a68-121">El registro de una DAC que tiene inicios de sesión en [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requiere la pertenencia a los roles **loginmanager** o **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="86a68-121">Registering a DAC that contains logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **loginmanager** or **serveradmin** roles.</span></span>  
  
##  <a name="using-the-register-data-tier-application-wizard"></a><a name="UsingRegisterDACWizard"></a> <span data-ttu-id="86a68-122">Usar el Asistente para registrar aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="86a68-122">Using the Register Data-tier Application Wizard</span></span>  
 <span data-ttu-id="86a68-123">**Para registrar una DAC mediante un asistente**</span><span class="sxs-lookup"><span data-stu-id="86a68-123">**To Register a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="86a68-124">En **Explorador de objetos**, expanda el nodo de la instancia que contiene la base de datos que se va a registrar como una DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-124">In **Object Explorer**, expand the node for the instance containing the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="86a68-125">Expanda el nodo **Bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="86a68-125">Expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="86a68-126">Haga clic con el botón derecho en la base de datos que se va a registrar, seleccione **Tareas** y después **Registrar como aplicación de capa de datos...**</span><span class="sxs-lookup"><span data-stu-id="86a68-126">Right-click the database to be registered, point to **Tasks**, and then select **Register As Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="86a68-127">Complete los cuadros de diálogo del asistente:</span><span class="sxs-lookup"><span data-stu-id="86a68-127">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="86a68-128">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="86a68-128">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="86a68-129">Página Definir propiedades</span><span class="sxs-lookup"><span data-stu-id="86a68-129">Set Properties Page</span></span>](#Set_properties)  
  
    3.  [<span data-ttu-id="86a68-130">Página Validación y resumen</span><span class="sxs-lookup"><span data-stu-id="86a68-130">Validation and Summary Page</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="86a68-131">Página Registrar DAC</span><span class="sxs-lookup"><span data-stu-id="86a68-131">Register DAC Page</span></span>](#Register)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="86a68-132">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="86a68-132">Introduction Page</span></span>  
 <span data-ttu-id="86a68-133">Esta página describe los pasos para registrar una aplicación de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="86a68-133">This page describes the steps for registering a data-tier application.</span></span>  
  
 <span data-ttu-id="86a68-134">**No volver a mostrar esta página.**</span><span class="sxs-lookup"><span data-stu-id="86a68-134">**Do not show this page again.**</span></span> <span data-ttu-id="86a68-135">- Haga clic en la casilla para evitar que la página se muestre en el futuro.</span><span class="sxs-lookup"><span data-stu-id="86a68-135">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="86a68-136">**Siguiente >** : avanza a la página **Definir propiedades**.</span><span class="sxs-lookup"><span data-stu-id="86a68-136">**Next >** - Proceeds to the **Set Properties** page.</span></span>  
  
 <span data-ttu-id="86a68-137">**Cancelar** : sale del asistente sin registrar una DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-137">**Cancel** - Terminates the wizard without registering a DAC.</span></span>  
  
##  <a name="set-properties-page"></a><a name="Set_properties"></a> <span data-ttu-id="86a68-138">Página Definir propiedades</span><span class="sxs-lookup"><span data-stu-id="86a68-138">Set Properties Page</span></span>  
 <span data-ttu-id="86a68-139">Use esta página para especificar propiedades en el nivel de DAC como el nombre y la versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="86a68-139">Use this page to specify DAC-level properties such as the application name and version.</span></span>  
  
 <span data-ttu-id="86a68-140">**Nombre de aplicación.**</span><span class="sxs-lookup"><span data-stu-id="86a68-140">**Application name.**</span></span> <span data-ttu-id="86a68-141">- Una cadena que especifica el nombre que se usa para identificar la definición de la DAC; el campo se rellena con el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="86a68-141">- A string that specifies the name used to identify the DAC definition, the field is been populated with the database name.</span></span>  
  
 <span data-ttu-id="86a68-142">**Versión**.</span><span class="sxs-lookup"><span data-stu-id="86a68-142">**Version.**</span></span> <span data-ttu-id="86a68-143">- Un valor numérico que identifica la versión de la DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-143">- A numeric value that identifies the version of the DAC.</span></span> <span data-ttu-id="86a68-144">La versión de DAC se usa en Visual Studio para identificar la versión de la DAC en la que están trabajando los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="86a68-144">The DAC version is used in Visual Studio to identify the version of the DAC that developers are working on.</span></span> <span data-ttu-id="86a68-145">Al implementar una DAC, la versión se almacena en la `msdb` base de datos y se puede ver después en el nodo **aplicaciones de capa de datos** en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86a68-145">When deploying a DAC, the version is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="86a68-146">**Descripción.**</span><span class="sxs-lookup"><span data-stu-id="86a68-146">**Description.**</span></span> <span data-ttu-id="86a68-147">- Opcional.</span><span class="sxs-lookup"><span data-stu-id="86a68-147">- Optional.</span></span> <span data-ttu-id="86a68-148">Texto que explica el propósito de la DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-148">Text that explains the purpose of the DAC.</span></span> <span data-ttu-id="86a68-149">Al implementar una DAC, la descripción se almacena en la `msdb` base de datos y se puede ver después en el nodo **aplicaciones de capa de datos** en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86a68-149">When deploying a DAC, the description is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="86a68-150">\*\* \< Anterior\*\* : vuelve a la página **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="86a68-150">**\< Previous** - Returns you to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="86a68-151">**Siguiente >** : comprueba que se puede crear una DAC a partir de los objetos de la base de datos y muestra los resultados en la página **Validación y resumen**.</span><span class="sxs-lookup"><span data-stu-id="86a68-151">**Next >** - Verifies that a DAC can be built from the objects in the database, and displays the results in the **Validation and Summary** page.</span></span>  
  
 <span data-ttu-id="86a68-152">**Cancelar** : sale del asistente sin registrar la DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-152">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="validation-and-summary-page"></a><a name="Summary"></a> <span data-ttu-id="86a68-153">Página Validación y resumen</span><span class="sxs-lookup"><span data-stu-id="86a68-153">Validation and Summary Page</span></span>  
 <span data-ttu-id="86a68-154">Use esta página para revisar las acciones que el asistente realizará al registrar la DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-154">Use this page to review the actions the wizard will take when registering the DAC.</span></span> <span data-ttu-id="86a68-155">La página pasa por tres estados cuando comprueba que una DAC se puede compilar a partir de los objetos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="86a68-155">The page transitions through three states as it verifies that a DAC can be built from the objects in the database.</span></span>  
  
### <a name="retrieving-objects"></a><span data-ttu-id="86a68-156">Recuperar objetos</span><span class="sxs-lookup"><span data-stu-id="86a68-156">Retrieving Objects</span></span>  
 <span data-ttu-id="86a68-157">**Recuperando la base de datos y los objetos de servidor.**</span><span class="sxs-lookup"><span data-stu-id="86a68-157">**Retrieving database and server objects.**</span></span> <span data-ttu-id="86a68-158">- Muestra una barra de progreso a medida que el asistente recupera todos los objetos necesarios de la base de datos y la instancia del motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="86a68-158">- Displays a progress bar as the wizard retrieves all of the required objects from the database and the instance of the Database Engine.</span></span>  
  
 <span data-ttu-id="86a68-159">\*\* \< Anterior\*\* : vuelve a la página **establecer propiedades** para cambiar las entradas.</span><span class="sxs-lookup"><span data-stu-id="86a68-159">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="86a68-160">**Siguiente >** : registra la DAC y muestra los resultados en la página **Registrar DAC**.</span><span class="sxs-lookup"><span data-stu-id="86a68-160">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="86a68-161">**Cancelar** : sale del asistente sin registrar la DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-161">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="validating-objects"></a><span data-ttu-id="86a68-162">Validar objetos</span><span class="sxs-lookup"><span data-stu-id="86a68-162">Validating Objects</span></span>  
 <span data-ttu-id="86a68-163">**Checking**  _SchemaName_ **.**</span><span class="sxs-lookup"><span data-stu-id="86a68-163">**Checking**  _SchemaName_ **.**</span></span> <span data-ttu-id="86a68-164">_ObjectName_ **.**</span><span class="sxs-lookup"><span data-stu-id="86a68-164">_ObjectName_ **.**</span></span> <span data-ttu-id="86a68-165">- Muestra una barra de progreso cuando el asistente comprueba las dependencias de los objetos recuperados y comprueba que son todos objetos válidos para una DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-165">- Displays a progress bar as the wizard verifies the dependencies of the retrieved objects, and verifies that they are all valid objects for a DAC.</span></span> <span data-ttu-id="86a68-166">_SchemaName_ **.** _ObjectName_ identifican el objeto que se está comprobando.</span><span class="sxs-lookup"><span data-stu-id="86a68-166">_SchemaName_**.**_ObjectName_ identify which object is currently being verified.</span></span>  
  
 <span data-ttu-id="86a68-167">\*\* \< Anterior\*\* : vuelve a la página **establecer propiedades** para cambiar las entradas.</span><span class="sxs-lookup"><span data-stu-id="86a68-167">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="86a68-168">**Siguiente >** : registra la DAC y muestra los resultados en la página **Registrar DAC**.</span><span class="sxs-lookup"><span data-stu-id="86a68-168">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="86a68-169">**Cancelar** : sale del asistente sin registrar la DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-169">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="summary"></a><span data-ttu-id="86a68-170">Resumen</span><span class="sxs-lookup"><span data-stu-id="86a68-170">Summary</span></span>  
 <span data-ttu-id="86a68-171">**El siguiente valor se usará para registrar la DAC.**</span><span class="sxs-lookup"><span data-stu-id="86a68-171">**The following setting will be used to register your DAC.**</span></span> <span data-ttu-id="86a68-172">- Muestra un informe de las propiedades y objetos que se incluirán en la DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-172">- Displays a report of the properties and objects that will be included in the DAC.</span></span>  
  
 <span data-ttu-id="86a68-173">**Guardar informe** : seleccione este botón para guardar una copia del informe de validación en un archivo HTML.</span><span class="sxs-lookup"><span data-stu-id="86a68-173">**Save Report** - Select this button to save a copy of the validation report to an HTML file.</span></span> <span data-ttu-id="86a68-174">La carpeta predeterminada es una carpeta **SQL Server Management Studio\DAC Packages** de la carpeta Documentos de su cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="86a68-174">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span>  
  
 <span data-ttu-id="86a68-175">\*\* \< Anterior\*\* : vuelve a la página **establecer propiedades** para cambiar las entradas.</span><span class="sxs-lookup"><span data-stu-id="86a68-175">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="86a68-176">**Siguiente >** : registra la DAC y muestra los resultados en la página **Registrar DAC**.</span><span class="sxs-lookup"><span data-stu-id="86a68-176">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="86a68-177">**Cancelar** : sale del asistente sin registrar la DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-177">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="register-dac-page"></a><a name="Register"></a> <span data-ttu-id="86a68-178">Página Registrar DAC</span><span class="sxs-lookup"><span data-stu-id="86a68-178">Register DAC Page</span></span>  
 <span data-ttu-id="86a68-179">Esta página notifica si la operación de registro se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="86a68-179">This page reports the success or failure of the registration.</span></span>  
  
 <span data-ttu-id="86a68-180">**Registrando la DAC** : notifica si cada acción realizada para registrar la DAC se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="86a68-180">**Registering the DAC** - Reports the success or failure of each action taken to register the DAC.</span></span> <span data-ttu-id="86a68-181">Revise la información para determinar si cada acción se realizó o no correctamente.</span><span class="sxs-lookup"><span data-stu-id="86a68-181">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="86a68-182">Cualquier acción que encontrara un error tendrá un vínculo en la columna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="86a68-182">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="86a68-183">Seleccione el vínculo para ver un informe del error para esa acción.</span><span class="sxs-lookup"><span data-stu-id="86a68-183">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="86a68-184">**Guardar informe** : seleccione este botón para guardar el informe de registro en un archivo HTML.</span><span class="sxs-lookup"><span data-stu-id="86a68-184">**Save Report** - Select this button to save the registration report to an HTML file.</span></span> <span data-ttu-id="86a68-185">El archivo notifica el estado de cada acción, incluidos todos los errores generados por cualquiera de las acciones.</span><span class="sxs-lookup"><span data-stu-id="86a68-185">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="86a68-186">La carpeta predeterminada es una carpeta **SQL Server Management Studio\DAC Packages** de la carpeta Documentos de su cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="86a68-186">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span> <span data-ttu-id="86a68-187">El nombre de archivo tiene el formato \<DACPackageName>_RegisterDACReport_yyyymmdd.html, donde \<*DACPackageName*> es el nombre del paquete que se implementa; *yyyy*, el año actual; *mm*, el mes actual y *dd* el día actual.</span><span class="sxs-lookup"><span data-stu-id="86a68-187">The file name is in the format \<DACPackageName>_RegisterDACReport_yyyymmdd.html, where \<*DACPackageName*> is the name of the package being deployed, *yyyy* = the current year, *mm* = the current month, and *dd* = the current day.</span></span>  
  
 <span data-ttu-id="86a68-188">**Finalizar** : termina el asistente.</span><span class="sxs-lookup"><span data-stu-id="86a68-188">**Finish** - Terminates the wizard.</span></span>  
  
##  <a name="register-a-dac-using-powershell"></a><a name="RegisterDACPowerShell"></a> <span data-ttu-id="86a68-189">Registrar una DAC con PowerShell</span><span class="sxs-lookup"><span data-stu-id="86a68-189">Register a DAC Using PowerShell</span></span>  
 <span data-ttu-id="86a68-190">**Para registrar una base de datos como una DAC mediante el método Register() en un script de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="86a68-190">**To register a database as a DAC using the Register() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="86a68-191">Cree un objeto SMO Server y establézcalo en la instancia que contiene la base de datos que se va a registrar una DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-191">Create a SMO Server object and set it to the instance that contains the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="86a68-192">Agregue una variable que especifique el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="86a68-192">Add a variable that specifies the name of the database.</span></span>  
  
3.  <span data-ttu-id="86a68-193">Especifique los metadatos de la DAC, como su nombre, versión y descripción.</span><span class="sxs-lookup"><span data-stu-id="86a68-193">Specify the metadata for the DAC, such as the DAC name, version, and description.</span></span>  
  
4.  <span data-ttu-id="86a68-194">Ejecute el método Register con la información especificada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="86a68-194">Run the Register method with the information specified above.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="86a68-195">Ejemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="86a68-195">Example (PowerShell)</span></span>  
 <span data-ttu-id="86a68-196">El ejemplo siguiente registra una base de datos denominada MyDB como DAC.</span><span class="sxs-lookup"><span data-stu-id="86a68-196">The following example registers a database named MyDB as a DAC.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Specify the database to register as a DAC.  
$dbname = "MyDB"  
  
## Specify the DAC metadata.  
$applicationname = "MyApplication"  
$version = "1.0.0.0"  
$description = "This DAC defines the database used by my application."  
  
## Register the DAC.  
$registerunit = New-Object Microsoft.SqlServer.Management.Dac.DacExtractionUnit($srv, $dbname, $applicationname, $version)  
$registerunit.Description = $description  
$registerunit.Register()  
```  
  
## <a name="see-also"></a><span data-ttu-id="86a68-197">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86a68-197">See Also</span></span>  
 [<span data-ttu-id="86a68-198">Aplicaciones de capa de datos</span><span class="sxs-lookup"><span data-stu-id="86a68-198">Data-tier Applications</span></span>](data-tier-applications.md)  
