---
title: Actualizar una aplicación de capa de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.upgradedacwizard.reviewpolicy.f1
- sql12.swb.upgradedacwizard.selectoptions.f1
- sql12.swb.upgradedacwizard.selectpackage.f1
- sql12.swb.upgradedacwizard.reviewplan.f1
- sql12.swb.upgradedacwizard.checkdrift.f1
- sql12.swb.upgradedacwizard.summary.f1
- sql12.swb.upgradedacwizard.upgradedac.f1
- sql12.swb.upgradedacwizard.introduction.f1
helpviewer_keywords:
- upgrade DAC
- data-tier application [SQL Server], upgrade
- wizard [DAC], upgrade
- How to [DAC], upgrade
ms.assetid: c117df94-f02b-403f-9383-ec5b3ac3763c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0e597d02af28a16539b50ff76503059278ef7a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677161"
---
# <a name="upgrade-a-data-tier-application"></a><span data-ttu-id="6c809-102">Upgrade a Data-tier Application</span><span class="sxs-lookup"><span data-stu-id="6c809-102">Upgrade a Data-tier Application</span></span>
  <span data-ttu-id="6c809-103">Use el Asistente Actualizar aplicación de capa de datos o un script de Windows PowerShell para cambiar el esquema y las propiedades de una aplicación de capa de datos (DAC) implementada actualmente para coincidir con el esquema y las propiedades definidas en una versión nueva de la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-103">Use either the Upgrade Data-tier Application Wizard or a Windows PowerShell script to change the schema and properties of a currently deployed data-tier application (DAC) to match the schema and properties defined in a new version of the DAC.</span></span>  
  
-   <span data-ttu-id="6c809-104">**Antes de empezar:**  [Elegir opciones de actualización de DAC](#ChoseDACUpgOptions), [Limitaciones y restricciones](#LimitationsRestrictions), [Requisitos previos](#Prerequisites), [Seguridad](#Security), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="6c809-104">**Before you begin:**  [Choosing DAC Upgrade Options](#ChoseDACUpgOptions), [Limitations and Restrictions](#LimitationsRestrictions), [Prerequisites](#Prerequisites), [Security](#Security), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="6c809-105">**Para actualizar una DAC mediante:**  [el Asistente Actualizar aplicación de capa de datos](#UsingDACUpgradeWizard), [PowerShell](#UpgradeDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="6c809-105">**To upgrade a DAC, using:**  [The Upgrade Data-tier Application Wizard](#UsingDACUpgradeWizard), [PowerShell](#UpgradeDACPowerShell)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6c809-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6c809-106">Before You Begin</span></span>  
 <span data-ttu-id="6c809-107">Una actualización de DAC es un proceso en contexto que modifica el esquema de la base de datos existente para coincidir con el esquema definido en una nueva versión de la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-107">A DAC upgrade is an in-place process that alters the schema of the existing database to match the schema defined in a new version of the DAC.</span></span> <span data-ttu-id="6c809-108">La nueva versión de la DAC se proporciona en un archivo de paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-108">The new version of the DAC is supplied in a DAC package file.</span></span> <span data-ttu-id="6c809-109">Para obtener más información sobre cómo crear un paquete DAC, vea [Aplicaciones de capa de datos](data-tier-applications.md).</span><span class="sxs-lookup"><span data-stu-id="6c809-109">For more information about creating a DAC package, see [Data-tier Applications](data-tier-applications.md).</span></span>  
  
###  <a name="choosing-dac-upgrade-options"></a><a name="ChoseDACUpgOptions"></a> <span data-ttu-id="6c809-110">Elegir opciones de actualización de DAC</span><span class="sxs-lookup"><span data-stu-id="6c809-110">Choosing DAC Upgrade Options</span></span>  
 <span data-ttu-id="6c809-111">Hay cuatro opciones de actualización para una actualización en contexto:</span><span class="sxs-lookup"><span data-stu-id="6c809-111">There are four upgrade options for an in-place upgrade:</span></span>  
  
-   <span data-ttu-id="6c809-112">**Omitir pérdida de datos** : si es `True` , la actualización continuará incluso si algunas de las operaciones provocan la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-112">**Ignore Data Loss** - If `True`, the upgrade will proceed even if some of the operations result in the loss of data.</span></span> <span data-ttu-id="6c809-113">Si es `False`, estas operaciones terminarán la actualización.</span><span class="sxs-lookup"><span data-stu-id="6c809-113">If `False`, these operations will terminate the upgrade.</span></span> <span data-ttu-id="6c809-114">Por ejemplo, si no hay una tabla de la base de datos actual en el esquema de la nueva DAC, la tabla se quitará si se especifica `True`.</span><span class="sxs-lookup"><span data-stu-id="6c809-114">For example, if a table in the current database is not present in the schema of the new DAC, the table will be dropped if `True` is specified.</span></span> <span data-ttu-id="6c809-115">El valor predeterminado es `True`.</span><span class="sxs-lookup"><span data-stu-id="6c809-115">The default setting is `True`.</span></span>  
  
-   <span data-ttu-id="6c809-116">**Bloquear en cambios** : si es `True` , la actualización se termina si el esquema de la base de datos es diferente del definido en la DAC anterior.</span><span class="sxs-lookup"><span data-stu-id="6c809-116">**Block on Changes** - If `True`, the upgrade is terminated if the database schema is different than that defined in the previous DAC.</span></span> <span data-ttu-id="6c809-117">Si es `False`, la actualización continúa incluso si se detectan cambios.</span><span class="sxs-lookup"><span data-stu-id="6c809-117">If `False`, the upgrade continues even if changes are detected.</span></span> <span data-ttu-id="6c809-118">El valor predeterminado es `False`.</span><span class="sxs-lookup"><span data-stu-id="6c809-118">The default setting is `False`.</span></span>  
  
-   <span data-ttu-id="6c809-119">**Reversión en** caso de error: Si `True` es, la actualización se incluye en una transacción y, si se detectan errores, se intentará revertir.</span><span class="sxs-lookup"><span data-stu-id="6c809-119">**Rollback on Failure** - If `True`, the upgrade is enclosed in a transaction, and if errors are encountered a rollback will be attempted.</span></span> <span data-ttu-id="6c809-120">Si es `False`, se confirman todos los cambios a medida que se efectúan y, si se producen errores, puede que tenga que restaurar una copia de seguridad anterior de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-120">If `False`, all changes are committed as they are made and if errors occur you may have to restore a previous backup of the database.</span></span> <span data-ttu-id="6c809-121">El valor predeterminado es `False`.</span><span class="sxs-lookup"><span data-stu-id="6c809-121">The default setting is `False`.</span></span>  
  
-   <span data-ttu-id="6c809-122">**Omitir validación de directiva** : Si `True` es, la Directiva de selección de servidor DAC no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="6c809-122">**Skip Policy Validation** - If `True`, the DAC server selection policy is not evaluated.</span></span> <span data-ttu-id="6c809-123">Si es `False`, se evalúa la directiva y la actualización se termina si se produce un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="6c809-123">If `False`, the policy is evaluated and the upgrade terminates if there is a validation error.</span></span> <span data-ttu-id="6c809-124">El valor predeterminado es `False`.</span><span class="sxs-lookup"><span data-stu-id="6c809-124">The default setting is `False`.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="6c809-125">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6c809-125">Limitations and Restrictions</span></span>  
 <span data-ttu-id="6c809-126">Las actualizaciones de DAC solo se pueden realizar en [!INCLUDE[ssSDS](../../includes/sssds-md.md)]o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) o posterior.</span><span class="sxs-lookup"><span data-stu-id="6c809-126">DAC uprades can only be performed in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6c809-127">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6c809-127">Prerequisites</span></span>  
 <span data-ttu-id="6c809-128">Es conveniente hacer una copia de seguridad completa de la base de datos antes de comenzar la actualización.</span><span class="sxs-lookup"><span data-stu-id="6c809-128">It is prudent to take a full database backup before starting the upgrade.</span></span> <span data-ttu-id="6c809-129">Si una actualización encuentra un error y no puede revertir todos sus cambios, puede que tenga que restaurar la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6c809-129">If an upgrade encounters an error and cannot roll back all of its changes, you may need to restore the backup.</span></span>  
  
 <span data-ttu-id="6c809-130">Antes de iniciar la actualización, hay varias acciones que debe realizar para validar el paquete DAC y las acciones de actualización.</span><span class="sxs-lookup"><span data-stu-id="6c809-130">Before starting the upgrade, there are several actions that you should take to validate the DAC package and the upgrade actions.</span></span> <span data-ttu-id="6c809-131">Para obtener más información acerca de cómo realizar estas comprobaciones, vea [Validate a DAC Package](validate-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="6c809-131">For more information about how to perform these checks, see [Validate a DAC Package](validate-a-dac-package.md).</span></span>  
  
-   <span data-ttu-id="6c809-132">Recomendamos no realizar la actualización con un paquete DAC de fuentes desconocidas o que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="6c809-132">We recommend that you do not upgrade by using a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="6c809-133">Es posible que estos paquetes contengan código malintencionado que podría ejecutar código Transact-SQL no deseado o provocar errores al modificar el esquema o la estructura de la base de datos física.</span><span class="sxs-lookup"><span data-stu-id="6c809-133">Such packages could contain malicious code that might execute unintended Transact-SQL code or cause errors by modifying the schema.</span></span> <span data-ttu-id="6c809-134">Antes de usar un paquete desde un origen desconocido o que no sea de confianza, desempaquete la DAC y examine el código, como por ejemplo procedimientos almacenados u otro código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6c809-134">Before you use a package from an unknown or untrusted source, unpack the DAC and examine the code, such as stored procedures or other user-defined code.</span></span>  
  
-   <span data-ttu-id="6c809-135">Si se han realizado cambios en la base de datos actual tras la implementación de la última versión de la DAC, algunos de los cambios pueden impedir que la actualización se complete correctamente o puede que la actualización los quite.</span><span class="sxs-lookup"><span data-stu-id="6c809-135">If changes have been made to the current database after the last version of the DAC was deployed, some of the changes may prevent the successful completion of the upgrade, or be removed by the upgrade.</span></span> <span data-ttu-id="6c809-136">Primero debe generar y revisar un informe de los cambios efectuados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-136">You should first generate and review a report of any such changes made in the database.</span></span>  
  
-   <span data-ttu-id="6c809-137">Es conveniente generar una lista de los cambios en el esquema que va a realizar la actualización y revisar la lista para comprobar si existe algún problema.</span><span class="sxs-lookup"><span data-stu-id="6c809-137">It is prudent to generate a list of the schema changes the upgrade will perform, and review the list for any problems.</span></span>  
  
 <span data-ttu-id="6c809-138">El nombre de la aplicación en el paquete DAC debe coincidir con el nombre de la aplicación de la DAC implementada actualmente.</span><span class="sxs-lookup"><span data-stu-id="6c809-138">The application name in the DAC package must match the application name of the currently deployed DAC.</span></span> <span data-ttu-id="6c809-139">Por ejemplo, si la DAC actual tiene un nombre de aplicación **GeneralLedger**, solo se puede actualizar mediante un paquete DAC que tenga también un nombre de aplicación **GeneralLedger**.</span><span class="sxs-lookup"><span data-stu-id="6c809-139">For example, if the current DAC has an application name of **GeneralLedger**, you can only upgrade by using a DAC package that also has an application name of **GeneralLedger**.</span></span>  
  
 <span data-ttu-id="6c809-140">Asegúrese de que hay suficiente espacio del registro de transacciones disponible para registrar todas las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="6c809-140">Ensure there is enough transaction log space available to log all of the modifications.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6c809-141">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6c809-141">Security</span></span>  
 <span data-ttu-id="6c809-142">Para mejorar la seguridad, los inicios de sesión de la autenticación de SQL Server están almacenados en un paquete DAC sin ninguna contraseña.</span><span class="sxs-lookup"><span data-stu-id="6c809-142">To improve security, SQL Server Authentication logins are stored in a DAC package without a password.</span></span> <span data-ttu-id="6c809-143">Cuando el paquete se implementa o actualiza, el inicio de sesión se crea como un inicio de sesión deshabilitado con una contraseña generada.</span><span class="sxs-lookup"><span data-stu-id="6c809-143">When the package is deployed or upgraded, the login is created as a disabled login with a generated password.</span></span> <span data-ttu-id="6c809-144">Para habilitar los inicios de sesión, use un inicio de sesión que disponga del permiso ALTER ANY LOGIN y emplee ALTER LOGIN para habilitar el inicio de sesión y asignar una nueva contraseña que pueda comunicar al usuario.</span><span class="sxs-lookup"><span data-stu-id="6c809-144">To enable the logins, log in using a login that has ALTER ANY LOGIN permission and use ALTER LOGIN to enable the login and assign a new password that can be communicated to the user.</span></span> <span data-ttu-id="6c809-145">Esto no se necesita para los inicios de sesión de Autenticación de Windows, porque SQL Server no administra sus contraseñas.</span><span class="sxs-lookup"><span data-stu-id="6c809-145">This is not needed for Windows Authentication logins because their passwords are not managed by SQL Server.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6c809-146">Permisos</span><span class="sxs-lookup"><span data-stu-id="6c809-146">Permissions</span></span>  
 <span data-ttu-id="6c809-147">Una DAC solo la pueden actualizar miembros de los roles fijos de servidor **sysadmin** o **serveradmin** , o los inicios de sesión que pertenezcan al rol fijo de servidor **dbcreator** y dispongan de permisos ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="6c809-147">A DAC can only be upgraded by members of the **sysadmin** or **serveradmin** fixed server roles, or by logins that are in the **dbcreator** fixed server role and have ALTER ANY LOGIN permissions.</span></span> <span data-ttu-id="6c809-148">El inicio de sesión debe ser el propietario de la base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="6c809-148">The login must be the owner of the existing database.</span></span> <span data-ttu-id="6c809-149">La cuenta de administrador del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integrada denominada **sa** también puede actualizar una DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-149">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also upgrade a DAC.</span></span>  
  
##  <a name="using-the-upgrade-data-tier-application-wizard"></a><a name="UsingDACUpgradeWizard"></a> <span data-ttu-id="6c809-150">Usar el Asistente Actualizar aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="6c809-150">Using the Upgrade Data-tier Application Wizard</span></span>  
 <span data-ttu-id="6c809-151">**Para actualizar una DAC mediante un asistente**</span><span class="sxs-lookup"><span data-stu-id="6c809-151">**To Upgrade a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="6c809-152">En **Explorador de objetos**, expanda el nodo de la instancia que contiene la DAC que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="6c809-152">In **Object Explorer**, expand the node for the instance containing the DAC to be upgraded.</span></span>  
  
2.  <span data-ttu-id="6c809-153">Expanda el nodo **Administración** y, después, expanda el nodo **Aplicaciones de capa de datos** .</span><span class="sxs-lookup"><span data-stu-id="6c809-153">Expand the **Management** node, and then expand the **Data-tier Applications** node.</span></span>  
  
3.  <span data-ttu-id="6c809-154">Haga clic con el botón derecho en el nodo de la DAC que se va a actualizar y, luego, seleccione **Actualizar aplicación de capa de datos...**</span><span class="sxs-lookup"><span data-stu-id="6c809-154">Right-click the node for the DAC to be upgraded, and then select **Upgrade Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="6c809-155">Complete los cuadros de diálogo del asistente:</span><span class="sxs-lookup"><span data-stu-id="6c809-155">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="6c809-156">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="6c809-156">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="6c809-157">Página Seleccionar paquete</span><span class="sxs-lookup"><span data-stu-id="6c809-157">Select Package Page</span></span>](#Select_dac_package)  
  
    3.  [<span data-ttu-id="6c809-158">Página Revisar directiva</span><span class="sxs-lookup"><span data-stu-id="6c809-158">Review Policy Page</span></span>](#Review_policy)  
  
    4.  [<span data-ttu-id="6c809-159">Página Detectar cambio</span><span class="sxs-lookup"><span data-stu-id="6c809-159">Detect Change Page</span></span>](#Detect_change)  
  
    5.  [<span data-ttu-id="6c809-160">Revisar el plan de actualización</span><span class="sxs-lookup"><span data-stu-id="6c809-160">Review the Upgrade Plan</span></span>](#ReviewUpgPlan)  
  
    6.  [<span data-ttu-id="6c809-161">Página Resumen</span><span class="sxs-lookup"><span data-stu-id="6c809-161">Summary Page</span></span>](#Summary)  
  
    7.  [<span data-ttu-id="6c809-162">Página Actualizar DAC</span><span class="sxs-lookup"><span data-stu-id="6c809-162">Upgrade DAC Page</span></span>](#Upgrade)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="6c809-163">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="6c809-163">Introduction Page</span></span>  
 <span data-ttu-id="6c809-164">Esta página describe los pasos para actualizar una aplicación de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-164">This page describes the steps for upgrading a data-tier application.</span></span>  
  
 <span data-ttu-id="6c809-165">**No volver a mostrar esta página.**</span><span class="sxs-lookup"><span data-stu-id="6c809-165">**Do not show this page again.**</span></span> <span data-ttu-id="6c809-166">- Haga clic en la casilla para evitar que la página se muestre en el futuro.</span><span class="sxs-lookup"><span data-stu-id="6c809-166">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="6c809-167">**Siguiente >:** avanza a la página **Seleccionar paquete**.</span><span class="sxs-lookup"><span data-stu-id="6c809-167">**Next >** - Proceeds to the **Select Package** page.</span></span>  
  
 <span data-ttu-id="6c809-168">**Cancelar:** termina el asistente sin actualizar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-168">**Cancel** - Terminates the wizard without upgrading the DAC.</span></span>  
  
##  <a name="select-package-page"></a><a name="Select_dac_package"></a> <span data-ttu-id="6c809-169">Página Seleccionar paquete</span><span class="sxs-lookup"><span data-stu-id="6c809-169">Select Package Page</span></span>  
 <span data-ttu-id="6c809-170">Use esta página para especificar el paquete DAC que contiene la nueva versión de la aplicación de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-170">Use this page to specify the DAC package that contains the new version of the data-tier application.</span></span> <span data-ttu-id="6c809-171">Las página pasa por dos estados.</span><span class="sxs-lookup"><span data-stu-id="6c809-171">The page transitions through two states.</span></span>  
  
### <a name="select-the-dac-package"></a><span data-ttu-id="6c809-172">Seleccionar el paquete DAC</span><span class="sxs-lookup"><span data-stu-id="6c809-172">Select the DAC Package</span></span>  
 <span data-ttu-id="6c809-173">Use el estado inicial de la página para elegir el paquete DAC que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="6c809-173">Use the initial state of the page to choose the DAC package to deploy.</span></span> <span data-ttu-id="6c809-174">El paquete DAC debe ser un archivo de paquete DAC válido y tener una extensión .dacpac.</span><span class="sxs-lookup"><span data-stu-id="6c809-174">The DAC package must be a valid DAC package file and must have a .dacpac extension.</span></span> <span data-ttu-id="6c809-175">El nombre de la aplicación DAC en el paquete DAC debe ser el mismo que el de la aplicación de la DAC actual.</span><span class="sxs-lookup"><span data-stu-id="6c809-175">The DAC application name in the DAC package must be the same as the application name of the current DAC.</span></span>  
  
 <span data-ttu-id="6c809-176">**Paquete DAC:** especifique la ruta de acceso y el nombre del archivo del paquete DAC que contiene la nueva versión de la aplicación de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-176">**DAC Package** - Specify the path and file name of the DAC package that contains the new version of the data-tier application.</span></span> <span data-ttu-id="6c809-177">Puede seleccionar el botón **Examinar** a la derecha del cuadro para ir a la ubicación del paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-177">You can select the **Browse** button at the right of the box to browse to the location of the DAC package.</span></span>  
  
 <span data-ttu-id="6c809-178">**Nombre de aplicación:** cuadro de solo lectura que muestra el nombre de la aplicación DAC que se asignó cuando la DAC se creó o extrajo de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-178">**Application Name** - A read-only box that displays the DAC application name assigned when the DAC was authored or extracted from a database.</span></span>  
  
 <span data-ttu-id="6c809-179">**Versión:** cuadro de solo lectura que muestra la versión que se asignó cuando la DAC se creó o extrajo de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-179">**Version** - A read-only box that displays the version assigned when the DAC was authored or extracted from a database.</span></span>  
  
 <span data-ttu-id="6c809-180">**Descripción:** cuadro de solo lectura que muestra la descripción que se escribió cuando la DAC se creó o extrajo de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-180">**Description** - A read-only box that displays the description written when the DAC was authored or extracted from a database.</span></span>  
  
 <span data-ttu-id="6c809-181">\*\* \< Anterior\*\* : vuelve a la página **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="6c809-181">**\< Previous** - Returns to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="6c809-182">**Siguiente>:** muestra una barra de progreso cuando el asistente confirma que el archivo seleccionado es un paquete DAC válido.</span><span class="sxs-lookup"><span data-stu-id="6c809-182">**Next >** - Displays a progress bar as the wizard confirms that the selected file is a valid DAC package.</span></span>  
  
 <span data-ttu-id="6c809-183">**Cancelar:** termina el asistente sin actualizar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-183">**Cancel** - Terminates the wizard without upgrading the DAC.</span></span>  
  
### <a name="validating-the-dac-package"></a><span data-ttu-id="6c809-184">Validar el paquete DAC</span><span class="sxs-lookup"><span data-stu-id="6c809-184">Validating the DAC Package</span></span>  
 <span data-ttu-id="6c809-185">Muestra una barra de progreso cuando el asistente confirma que el archivo seleccionado es un paquete DAC válido.</span><span class="sxs-lookup"><span data-stu-id="6c809-185">Displays a progress bar as the wizard confirms that the selected file is a valid DAC package.</span></span> <span data-ttu-id="6c809-186">Si se valida el paquete DAC, el asistente va a la página **Revisar directiva** .</span><span class="sxs-lookup"><span data-stu-id="6c809-186">If the DAC package is validated, the wizard proceeds to the **Review Policy** page.</span></span> <span data-ttu-id="6c809-187">Si el archivo no es un paquete DAC válido, el asistente se queda en la página **Seleccionar paquete DAC** .</span><span class="sxs-lookup"><span data-stu-id="6c809-187">If the file is not a valid DAC package, the wizard remains on the **Select DAC Package** page.</span></span> <span data-ttu-id="6c809-188">Seleccione otro paquete DAC válido o cancele el asistente y genere un nuevo paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-188">Either select another valid DAC package or cancel the wizard and generate a new DAC package.</span></span>  
  
 <span data-ttu-id="6c809-189">**Validando el contenido de DAC:** barra de progreso que notifica el estado actual del proceso de validación.</span><span class="sxs-lookup"><span data-stu-id="6c809-189">**Validating the contents of the DAC** - The progress bar that reports the current status of the validation process.</span></span>  
  
 <span data-ttu-id="6c809-190">\*\* \< Anterior\*\* : vuelve al estado inicial de la página **seleccionar paquete** .</span><span class="sxs-lookup"><span data-stu-id="6c809-190">**\< Previous** - Returns to the initial state of the **Select Package** page.</span></span>  
  
 <span data-ttu-id="6c809-191">**Siguiente>:** avanza a la versión final de la página **Seleccionar paquete**.</span><span class="sxs-lookup"><span data-stu-id="6c809-191">**Next >** - Proceeds to the final version of the **Select Package** page.</span></span>  
  
 <span data-ttu-id="6c809-192">**Cancelar:** termina el asistente sin implementar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-192">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="review-policy-page"></a><a name="Review_policy"></a> <span data-ttu-id="6c809-193">Página Revisar directiva</span><span class="sxs-lookup"><span data-stu-id="6c809-193">Review Policy Page</span></span>  
 <span data-ttu-id="6c809-194">Use esta página para revisar los resultados de la evaluación de la directiva de selección de servidores de DAC, en caso de que la DAC tenga una directiva.</span><span class="sxs-lookup"><span data-stu-id="6c809-194">Use this page to review the results of evaluating the DAC server selection policy, if the DAC has a policy.</span></span> <span data-ttu-id="6c809-195">La directiva de selección de servidores de DAC es opcional y está asignada a una DAC que se creó en Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6c809-195">The DAC server selection policy is optional, and is assigned to a DAC authored in Microsoft Visual Studio.</span></span> <span data-ttu-id="6c809-196">La directiva se sirve de las facetas de la directiva de selección de servidores para especificar las condiciones que debe cumplir una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] para hospedar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-196">The policy uses the server selection policy facets to specify conditions an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] should meet to host the DAC.</span></span>  
  
 <span data-ttu-id="6c809-197">**Resultados de evaluación de condiciones de directivas:** un informe de solo lectura que muestra si se ha cumplido correctamente la evaluación de las condiciones de la directiva de implementación de DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-197">**Evaluation results of policy conditions** - A read-only report showing whether the evaluations of the conditions in the DAC server selection policy succeeded.</span></span> <span data-ttu-id="6c809-198">Los resultados de la evaluación de cada condición se notifican en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="6c809-198">The results of evaluating each condition are reported on a separate line.</span></span>  
  
 <span data-ttu-id="6c809-199">**Pasar por alto infracciones de directivas:** use esta casilla para comenzar con la actualización si se produce un error en una o más de las condiciones de la directiva.</span><span class="sxs-lookup"><span data-stu-id="6c809-199">**Ignore policy violations** - Use this check box to proceed with the upgrade if one or more of the policy conditions failed.</span></span> <span data-ttu-id="6c809-200">Seleccione esta opción solamente si está seguro de que todas las condiciones que produjeron errores no evitarán la correcta operación de la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-200">Only select this option if you are sure that all of the conditions which failed will not prevent the successful operation of the DAC.</span></span>  
  
 <span data-ttu-id="6c809-201">\*\* \< Anterior\*\* : vuelve a la página **seleccionar paquete** .</span><span class="sxs-lookup"><span data-stu-id="6c809-201">**\< Previous** - Returns to the **Select Package** page.</span></span>  
  
 <span data-ttu-id="6c809-202">**Siguiente >:** avanza a la página **Detectar cambio**.</span><span class="sxs-lookup"><span data-stu-id="6c809-202">**Next >** - Proceeds to the **Detect Change** page.</span></span>  
  
 <span data-ttu-id="6c809-203">**Cancelar:** termina el asistente sin actualizar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-203">**Cancel** - Terminates the wizard without upgrading the DAC.</span></span>  
  
##  <a name="detect-change-page"></a><a name="Detect_change"></a> <span data-ttu-id="6c809-204">Página Detectar cambio</span><span class="sxs-lookup"><span data-stu-id="6c809-204">Detect Change Page</span></span>  
 <span data-ttu-id="6c809-205">Use esta página para notificar los resultados de la comprobación de los asistentes con respecto a los cambios realizados en la base de datos que hacen que su esquema sea distinto de la definición de esquema almacenada en los metadatos de la DAC en **msdb**.</span><span class="sxs-lookup"><span data-stu-id="6c809-205">Use this page reports the results of the wizards check for changes made to the database that make it's schema different than the schema definition stored in the DAC metadata in **msdb**.</span></span> <span data-ttu-id="6c809-206">Por ejemplo, si se han usado las instrucciones CREATE, ALTER o DROP para agregar, cambiar o quitar objetos en la base de datos tras la implementación inicial de la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-206">For example, if CREATE, ALTER, or DROP statements have been used to add, change, or remove objects from the database after the DAC was originally deployed.</span></span> <span data-ttu-id="6c809-207">En primer lugar, la página muestra una barra de progreso y, a continuación, notifica los resultados del análisis.</span><span class="sxs-lookup"><span data-stu-id="6c809-207">The page first displays a progress bar, and then reports the results of the analysis.</span></span>  
  
 <span data-ttu-id="6c809-208">**Detectando cambio. Esta operación puede tardar algunos minutos:** muestra una barra de progreso mientras el asistente comprueba las diferencias entre el esquema actual de la base de datos y los objetos en la definición de la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-208">**Detecting change, this may take a few minutes** - Displays a progress bar as the wizard checks for differences between the current schema of the database and the objects in the DAC definition.</span></span>  
  
 <span data-ttu-id="6c809-209">**Resultado de la detección de cambios:** indica que el análisis se ha completado y los resultados se notifican más abajo.</span><span class="sxs-lookup"><span data-stu-id="6c809-209">**Change detection results:** - Indicates that the analysis has completed and the results are reported below.</span></span>  
  
 <span data-ttu-id="6c809-210">**La base de datos DatabaseName no ha cambiado:** el asistente no detectó diferencia alguna en los objetos definidos en la base de datos ni en sus homólogos en la definición de la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-210">**The database DatabaseName has not changed** - The wizard detected no differences in the objects defined in the database and their counterparts in the DAC definition.</span></span>  
  
 <span data-ttu-id="6c809-211">**La base de datos DatabaseName ha cambiado:** el asistente detectó cambios entre los objetos en la base de datos y sus homólogos en la definición de la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-211">**The database DatabaseName has changed** - The wizard detected changes between the objects in the database and their counterparts in the DAC definition.</span></span>  
  
 <span data-ttu-id="6c809-212">**Continuar a pesar de la posible pérdida de los cambios:** indica que entiende que algunos de los objetos o datos en la base de datos actual no estarán presentes en la base de datos nueva y que quiere continuar con la actualización.</span><span class="sxs-lookup"><span data-stu-id="6c809-212">**Proceed despite possible loss of changes** - Specifies that you understand some of the objects or data in the current database will not be present in the new database, and that you are willing to proceed with the upgrade.</span></span> <span data-ttu-id="6c809-213">Seleccione este botón solamente si ha analizado el informe de cambios y entiende los pasos que debe seguir para transferir manualmente cualquier objeto o datos que sean necesarios en la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-213">You should select this button only if you have analyzed the change report and understand the steps you must perform to manually transfer any objects or data required in the new database.</span></span> <span data-ttu-id="6c809-214">Si no está seguro, haga clic en el botón **Guardar informe** para guardar el informe de cambios y, a continuación, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="6c809-214">If you are not sure, click the **Save Report** button to save the change report, then click **Cancel**.</span></span> <span data-ttu-id="6c809-215">Analice el informe, programe cómo transferir los objetos y datos necesarios una vez se haya completado la actualización y, a continuación, reinicie el asistente.</span><span class="sxs-lookup"><span data-stu-id="6c809-215">Analyze the report, plan how to transfer any required objects and data after the upgrade completes, then restart the wizard.</span></span>  
  
 <span data-ttu-id="6c809-216">**Guardar informe:** haga clic en el botón para guardar un informe de los cambios que el asistente detectó entre los objetos de la base de datos y sus homólogos en la definición de la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-216">**Save Report** - Click the button to save a report of the changes the wizard detected between the objects in the database and their counterparts in the DAC definition.</span></span> <span data-ttu-id="6c809-217">A continuación, puede revisar el informe para determinar si necesita tomar medidas cuando se complete la actualización para incorporar algunos o todos los objetos enumerados en el informe dentro de la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-217">You can then review the report to determine if you need to take actions after the upgrade completes to incorporate some or all of the objects listed in the report into the new database.</span></span>  
  
 <span data-ttu-id="6c809-218">\*\* \< Anterior\*\* : vuelve a la página **seleccionar paquete DAC** .</span><span class="sxs-lookup"><span data-stu-id="6c809-218">**\< Previous** - Returns to the **Select DAC Package** page.</span></span>  
  
 <span data-ttu-id="6c809-219">**Siguiente >** : avanza a la página **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="6c809-219">**Next >** - Proceeds to the **Options** page.</span></span>  
  
 <span data-ttu-id="6c809-220">**Cancelar:** termina el asistente sin implementar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-220">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
## <a name="options-page"></a><span data-ttu-id="6c809-221">Página Opciones</span><span class="sxs-lookup"><span data-stu-id="6c809-221">Options Page</span></span>  
 <span data-ttu-id="6c809-222">Use esta página para seleccionar la reversión en la opción de error para la actualización.</span><span class="sxs-lookup"><span data-stu-id="6c809-222">Use this page to select the rollback on failure option for the upgrade.</span></span>  
  
 <span data-ttu-id="6c809-223">**Reversión en caso de error**: seleccione esta opción para agregar la actualización en una transacción que el asistente puede intentar revertir si se producen errores.</span><span class="sxs-lookup"><span data-stu-id="6c809-223">**Rollback on failure** - Select this option to enclose the upgrade in a transaction which the wizard can attempt to roll back if errors occur.</span></span> <span data-ttu-id="6c809-224">Para obtener más información acerca de la opción, vea [Elegir opciones de actualización de DAC](#ChoseDACUpgOptions).</span><span class="sxs-lookup"><span data-stu-id="6c809-224">For more information about the option, see [Choosing DAC Upgrade Options](#ChoseDACUpgOptions).</span></span>  
  
 <span data-ttu-id="6c809-225">**Restaurar valores predeterminados:** devuelve la opción a su valor predeterminado de false.</span><span class="sxs-lookup"><span data-stu-id="6c809-225">**Restore Defaults** - Returns the option to its default setting of false.</span></span>  
  
 <span data-ttu-id="6c809-226">\*\* \< Anterior\*\* : vuelve a la página **detectar cambio** .</span><span class="sxs-lookup"><span data-stu-id="6c809-226">**\< Previous** - Returns to the **Detect Change** page.</span></span>  
  
 <span data-ttu-id="6c809-227">**Siguiente >:** avanza a la página **Revisar el plan de actualización**.</span><span class="sxs-lookup"><span data-stu-id="6c809-227">**Next >** - Proceeds to the **Review the Upgrade Plan** page.</span></span>  
  
 <span data-ttu-id="6c809-228">**Cancelar:** termina el asistente sin implementar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-228">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="review-the-upgrade-plan-page"></a><a name="ReviewUpgPlan"></a> <span data-ttu-id="6c809-229">Página Revisar el plan de actualización</span><span class="sxs-lookup"><span data-stu-id="6c809-229">Review the Upgrade Plan Page</span></span>  
 <span data-ttu-id="6c809-230">Use esta página para comprobar las acciones que realizará el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="6c809-230">Use this page to do review the actions that will be taken by the upgrade process.</span></span> <span data-ttu-id="6c809-231">Continúe solo si está seguro de que la actualización no causará problemas.</span><span class="sxs-lookup"><span data-stu-id="6c809-231">Only proceed when you are confident the upgrade will not create problems.</span></span>  
  
 <span data-ttu-id="6c809-232">**Se usarán las acciones siguientes para actualizar la DAC.**</span><span class="sxs-lookup"><span data-stu-id="6c809-232">**The following actions will be used to upgrade the DAC.**</span></span> <span data-ttu-id="6c809-233">- Compruebe la información que se muestra para asegurarse de que las acciones emprenda serán las correctas.</span><span class="sxs-lookup"><span data-stu-id="6c809-233">- Review the information displayed to ensure the actions taken will be correct.</span></span> <span data-ttu-id="6c809-234">La columna **Acción** muestra las acciones, como instrucciones Transact-SQL, que se ejecutarán para realizar la actualización.</span><span class="sxs-lookup"><span data-stu-id="6c809-234">The **Action** column displays the actions, such as Transact-SQL statements, that will be run to perform the upgrade.</span></span> <span data-ttu-id="6c809-235">La columna **Pérdida de datos** contendrá una advertencia si la acción asociada puede eliminar datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-235">The **Data Loss** column will contain a warning if the associated action could delete data.</span></span>  
  
 <span data-ttu-id="6c809-236">**Actualizar**: actualiza la lista de acciones.</span><span class="sxs-lookup"><span data-stu-id="6c809-236">**Refresh** - refreshes the action list.</span></span>  
  
 <span data-ttu-id="6c809-237">**Guardar informe de acciones**: guarda el contenido de la ventana de acción en un archivo HTML.</span><span class="sxs-lookup"><span data-stu-id="6c809-237">**Save Action Report** - saves the contents of the action window to an HTML file.</span></span>  
  
 <span data-ttu-id="6c809-238">**Continuar a pesar de la posible pérdida de los cambios:** indica que entiende que algunos de los objetos o datos en la base de datos actual no estarán presentes en la base de datos nueva y que quiere continuar con la actualización.</span><span class="sxs-lookup"><span data-stu-id="6c809-238">**Proceed despite possible loss of changes** - Specifies that you understand some of the objects or data in the current database will not be present in the new database, and that you are willing to proceed with the upgrade.</span></span> <span data-ttu-id="6c809-239">Seleccione este botón solamente si ha analizado el informe de cambios y entiende los pasos que debe seguir para transferir manualmente cualquier objeto o datos que sean necesarios en la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c809-239">You should select this button only if you have analyzed the change report and understand the steps you must perform to manually transfer any objects or data required in the new database.</span></span> <span data-ttu-id="6c809-240">Si no está seguro, haga clic en el botón **Guardar informe de acciones** para guardar el informe de cambios y en el botón **Guardar scripts** para guardar el script Transact-SQL; luego, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="6c809-240">If you are not sure, click the **Save Action Report** button to save the change report and the **Save Scripts** button to save the Transact-SQL script, then click **Cancel**.</span></span> <span data-ttu-id="6c809-241">Analice el informe y el script, planee cómo transferir los objetos y datos necesarios una vez que se haya completado la actualización y, a continuación, reinicie el asistente.</span><span class="sxs-lookup"><span data-stu-id="6c809-241">Analyze the report and script, and then plan how to transfer any required objects and data after the upgrade completes, then restart the wizard.</span></span>  
  
 <span data-ttu-id="6c809-242">**Guardar scripts**: guarda en un archivo de texto las instrucciones Transact-SQL que se van a usar para realizar la actualización.</span><span class="sxs-lookup"><span data-stu-id="6c809-242">**Save Scripts** - saves the Transact-SQL statements that will be used to perform the upgrade to a text file.</span></span>  
  
 <span data-ttu-id="6c809-243">**Restaurar valores predeterminados:** devuelve la opción a su valor predeterminado de false.</span><span class="sxs-lookup"><span data-stu-id="6c809-243">**Restore Defaults** - Returns the option to its default setting of false.</span></span>  
  
 <span data-ttu-id="6c809-244">\*\* \< Anterior\*\* : vuelve a la página **detectar cambio** .</span><span class="sxs-lookup"><span data-stu-id="6c809-244">**\< Previous** - Returns to the **Detect Change** page.</span></span>  
  
 <span data-ttu-id="6c809-245">**Siguiente >** : avanza a la página **Resumen**.</span><span class="sxs-lookup"><span data-stu-id="6c809-245">**Next >** - Proceeds to the **Summary** page.</span></span>  
  
 <span data-ttu-id="6c809-246">**Cancelar:** termina el asistente sin implementar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-246">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="6c809-247">Página Resumen</span><span class="sxs-lookup"><span data-stu-id="6c809-247">Summary Page</span></span>  
 <span data-ttu-id="6c809-248">Use esta página para realizar una revisión final de las acciones que el asistente realizará al actualizar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-248">Use this page to do a final review of the actions the wizard will take when upgrading the DAC.</span></span>  
  
 <span data-ttu-id="6c809-249">**Se usará la siguiente configuración en la actualización de su DAC.**</span><span class="sxs-lookup"><span data-stu-id="6c809-249">**The following settings will be used to upgrade your DAC.**</span></span> <span data-ttu-id="6c809-250">- Compruebe la información que se muestra para asegurarse de que las acciones emprenda serán las correctas.</span><span class="sxs-lookup"><span data-stu-id="6c809-250">- Review the information displayed to ensure the actions taken will be correct.</span></span> <span data-ttu-id="6c809-251">La ventana muestra la DAC que seleccionó para su actualización y el paquete DAC que contiene la nueva versión de la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-251">The window displays the DAC you selected to be upgraded, and the DAC package containing the new version of the DAC.</span></span> <span data-ttu-id="6c809-252">La ventana también muestra si la versión actual de la base de datos es igual que la definición de la DAC actual, o bien si la base de datos ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="6c809-252">The window also displays whether the current version of the database is the same as the current DAC definition, or if the database has changed.</span></span>  
  
 <span data-ttu-id="6c809-253">\*\* \< Anterior\*\* : vuelve a la página **revisar el plan de actualización** .</span><span class="sxs-lookup"><span data-stu-id="6c809-253">**\< Previous** - Returns you to the **Review the Upgrade Plan** page.</span></span>  
  
 <span data-ttu-id="6c809-254">**Siguiente >** : implementa la DAC y muestra los resultados en la página **Actualizar DAC**.</span><span class="sxs-lookup"><span data-stu-id="6c809-254">**Next >** - Deploys the DAC and displays the results in the **Upgrade DAC** page.</span></span>  
  
 <span data-ttu-id="6c809-255">**Cancelar:** termina el asistente sin implementar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-255">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="upgrade-dac-page"></a><a name="Upgrade"></a> <span data-ttu-id="6c809-256">Página Actualizar DAC</span><span class="sxs-lookup"><span data-stu-id="6c809-256">Upgrade DAC Page</span></span>  
 <span data-ttu-id="6c809-257">Esta página notifica si la operación de actualización se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="6c809-257">This page reports the success or failure of the upgrade operation.</span></span>  
  
 <span data-ttu-id="6c809-258">**Actualizando la DAC:** indica si cada acción realizada para actualizar la DAC se realizó o no correctamente.</span><span class="sxs-lookup"><span data-stu-id="6c809-258">**Upgrading the DAC** - Reports the success or failure of each action taken to upgrade the DAC.</span></span> <span data-ttu-id="6c809-259">Revise la información para determinar si cada acción se realizó o no correctamente.</span><span class="sxs-lookup"><span data-stu-id="6c809-259">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="6c809-260">Cualquier acción que encontrara un error tendrá un vínculo en la columna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="6c809-260">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="6c809-261">Seleccione el vínculo para ver un informe del error para esa acción.</span><span class="sxs-lookup"><span data-stu-id="6c809-261">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="6c809-262">**Guardar informe:** seleccione este botón para guardar el informe de actualización en un archivo HTML.</span><span class="sxs-lookup"><span data-stu-id="6c809-262">**Save Report** - Select this button to save the upgrade report to an HTML file.</span></span> <span data-ttu-id="6c809-263">El archivo notifica el estado de cada acción, incluidos todos los errores generados por cualquiera de las acciones.</span><span class="sxs-lookup"><span data-stu-id="6c809-263">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="6c809-264">La carpeta predeterminada es una carpeta SQL Server Management Studio\DAC Packages de la carpeta Documentos de su cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="6c809-264">The default folder is a SQL Server Management Studio\DAC Packages folder in the Documents folder of your Windows account.</span></span>  
  
 <span data-ttu-id="6c809-265">**Finalizar** : termina el asistente.</span><span class="sxs-lookup"><span data-stu-id="6c809-265">**Finish** - Terminates the wizard.</span></span>  
  
##  <a name="using-powershell"></a><a name="UpgradeDACPowerShell"></a> <span data-ttu-id="6c809-266">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c809-266">Using PowerShell</span></span>  
 <span data-ttu-id="6c809-267">**Para actualizar la DAC con el método IncrementalUpgrade() en un script de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6c809-267">**To upgrade a DAC using the IncrementalUpgrade() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="6c809-268">Cree un objeto SMO Server y establézcalo en la instancia que contiene la DAC que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="6c809-268">Create a SMO Server object and set it to the instance that contains the DAC to be upgraded.</span></span>  
  
2.  <span data-ttu-id="6c809-269">Abra un objeto `ServerConnection` y conéctese a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="6c809-269">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="6c809-270">Use `System.IO.File` para cargar el archivo de paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-270">Use `System.IO.File` to load the DAC package file.</span></span>  
  
4.  <span data-ttu-id="6c809-271">Use `add_DacActionStarted` y `add_DacActionFinished` para suscribirse a los eventos de actualización de DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-271">Use `add_DacActionStarted` and `add_DacActionFinished` to subscribe to the DAC upgrade events.</span></span>  
  
5.  <span data-ttu-id="6c809-272">Establezca `DacUpgradeOptions`.</span><span class="sxs-lookup"><span data-stu-id="6c809-272">Set the `DacUpgradeOptions`.</span></span>  
  
6.  <span data-ttu-id="6c809-273">Use el método `IncrementalUpgrade` para actualizar la DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-273">Use the `IncrementalUpgrade` method to upgrade the DAC.</span></span>  
  
7.  <span data-ttu-id="6c809-274">Cierra la secuencia de archivos usada para leer el archivo de paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="6c809-274">Close the file stream used to read the DAC package file.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="6c809-275">Ejemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="6c809-275">Example (PowerShell)</span></span>  
 <span data-ttu-id="6c809-276">En el ejemplo siguiente se actualiza la DAC denominada MyApplication en una instancia predeterminada de [!INCLUDE[ssDE](../../includes/ssde-md.md)], mediante una nueva versión de la DAC en un paquete MyApplicationVNext.dacpac.</span><span class="sxs-lookup"><span data-stu-id="6c809-276">The following example upgrades a DAC named MyApplication on a default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], using a new DAC version in a MyApplicationVNext.dacpac package.</span></span>  
  
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
  
## Subscribe to the DAC upgrade events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Upgrade the DAC and close the package.  
$dacName  = "MyApplication"  
  
## Set the upgrade options.  
$upgradeProperties = New-Object Microsoft.SqlServer.Management.Dac.DacUpgradeOptions  
$upgradeProperties.blockonchanges = $true  
$upgradeProperties.ignoredataloss = $false  
$upgradeProperties.rollbackonfailure = $true  
$ upgradeProperties.skippolicyvalidation = $false  
  
## Upgrade the DAC  
$dacstore.IncrementalUpgrade($dacName, $dacType, $upgradeProperties)  
## Close the package file.  
$fileStream.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c809-277">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c809-277">See Also</span></span>  
 <span data-ttu-id="6c809-278">[Aplicaciones de capa de datos](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="6c809-278">[Data-tier Applications](data-tier-applications.md) </span></span>  
 [<span data-ttu-id="6c809-279">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c809-279">SQL Server PowerShell</span></span>](../../powershell/sql-server-powershell.md)  
