---
title: Crear RSExecRole | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RSExecRole
ms.assetid: 7ac17341-df7e-4401-870e-652caa2859c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0037ef0c4d7a949b5a30bb45356613f6114db130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745658"
---
# <a name="create-the-rsexecrole"></a><span data-ttu-id="e687b-102">Crear el RSExecRole</span><span class="sxs-lookup"><span data-stu-id="e687b-102">Create the RSExecRole</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="e687b-103">utiliza un rol de base de datos predefinido denominado `RSExecRole` para conceder permisos de servidor de informes a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e687b-103">uses a predefined database role called `RSExecRole` to grant report server permissions to the report server database.</span></span> <span data-ttu-id="e687b-104">El `RSExecRole` rol se crea automáticamente con la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e687b-104">The `RSExecRole` role is created automatically with the report server database.</span></span> <span data-ttu-id="e687b-105">Por lo general, nunca se debe modificar el rol ni asignar otros usuarios al mismo.</span><span class="sxs-lookup"><span data-stu-id="e687b-105">As a rule, you should never modify it or assign other users to the role.</span></span> <span data-ttu-id="e687b-106">Sin embargo, cuando se mueve una base de datos del servidor de informes a un nuevo o a uno diferente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , se debe volver a crear el rol en las bases de datos de sistema maestra y msdb.</span><span class="sxs-lookup"><span data-stu-id="e687b-106">However, when you move a report server database to a new or different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)], must re-create the role in the Master and MSDB system databases.</span></span>

 <span data-ttu-id="e687b-107">Usando estas instrucciones realizará los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e687b-107">Using the following instructions, you will perform the following steps:</span></span>

-   <span data-ttu-id="e687b-108">Crear y proporcionar el rol `RSExecRole` en la base de datos del sistema maestra.</span><span class="sxs-lookup"><span data-stu-id="e687b-108">Create and provision the `RSExecRole` in the Master system database.</span></span>

-   <span data-ttu-id="e687b-109">Crear y proporcionar el rol `RSExecRole` en la base de datos del sistema MSDB.</span><span class="sxs-lookup"><span data-stu-id="e687b-109">Create and provision the `RSExecRole` in the MSDB system database.</span></span>

> [!NOTE]
>  <span data-ttu-id="e687b-110">Las instrucciones de este tema están destinadas a los usuarios que no desean ejecutar un script o escribir código WMI para proporcionar la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e687b-110">The instructions in this topic are intended for users who do not want to run a script or write WMI code to provision the report server database.</span></span> <span data-ttu-id="e687b-111">Si administra una implementación grande y va a mover las bases de datos habitualmente, debe escribir un script para automatizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e687b-111">If you manage a large deployment and will be moving databases routinely, you should write a script to automate these steps.</span></span> <span data-ttu-id="e687b-112">Para obtener más información, vea [Obtener acceso al proveedor WMI de Reporting Services](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="e687b-112">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="e687b-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e687b-113">Before you start</span></span>

-   <span data-ttu-id="e687b-114">Realice una copia de seguridad de las claves de cifrado para poder restaurarlas después de mover la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e687b-114">Back up the encryption keys so that you can restore them after the database is moved.</span></span> <span data-ttu-id="e687b-115">Este paso no afecta directamente a la capacidad personal para crear y proporcionar el rol `RSExecRole`, pero se debe disponer de una copia de seguridad de las claves para comprobar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="e687b-115">This is step does not directly affect your ability to create and provision the `RSExecRole`, but you must have a backup of the keys in order to verify your work.</span></span> <span data-ttu-id="e687b-116">Para obtener más información, vea [Hacer copia de seguridad y restaurar claves de cifrado de Reporting Services](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span><span class="sxs-lookup"><span data-stu-id="e687b-116">For more information, see [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span></span>

-   <span data-ttu-id="e687b-117">Compruebe que ha iniciado sesión con una cuenta de usuario que tenga permisos `sysadmin` en la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e687b-117">Verify you are logged on as a user account that has `sysadmin` permissions on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>

-   <span data-ttu-id="e687b-118">Compruebe que el servicio Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] está instalado y se está ejecutando en la instancia de [!INCLUDE[ssDE](../../../includes/ssde-md.md)] que piensa utilizar.</span><span class="sxs-lookup"><span data-stu-id="e687b-118">Verify [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service is installed and running on the instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that you plan to use.</span></span>

-   <span data-ttu-id="e687b-119">Adjunte las bases de datos reportservertempdb y reportserver.</span><span class="sxs-lookup"><span data-stu-id="e687b-119">Attach the reportservertempdb and reportserver databases.</span></span> <span data-ttu-id="e687b-120">No es necesario que adjunte las bases de datos para crear el rol real, pero deben estar adjuntas para poder probar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="e687b-120">You are not required to attach the databases to create the actual role, but they must be attached before you can test your work.</span></span>

 <span data-ttu-id="e687b-121">Las instrucciones para crear manualmente el rol `RSExecRole` están destinadas a utilizarse en el contexto de migración de una instalación del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e687b-121">The instructions for manually creating the `RSExecRole` are intended to be used within the context of migrating a report server installation.</span></span> <span data-ttu-id="e687b-122">Las tareas importantes como realizar una copia de seguridad y mover la base de datos del servidor de informes no se tratan en este tema, pero se incluyen en la documentación del motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e687b-122">Important tasks such as backing up and moving the report server database are not addressed in this topic, but are documented in the Database Engine documentation.</span></span>

## <a name="create-rsexecrole-in-master"></a><span data-ttu-id="e687b-123">Crear RSExecRole en la base de datos maestra</span><span class="sxs-lookup"><span data-stu-id="e687b-123">Create RSExecRole in Master</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="e687b-124">utiliza procedimientos almacenados extendidos para que el servicio Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] admita las operaciones programadas.</span><span class="sxs-lookup"><span data-stu-id="e687b-124">uses extended stored procedures for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service to support scheduled operations.</span></span> <span data-ttu-id="e687b-125">En los pasos siguientes se explica cómo conceder permisos de ejecución para los procedimientos al rol `RSExecRole`.</span><span class="sxs-lookup"><span data-stu-id="e687b-125">The following steps explain how to grant Execute permissions for the procedures to the `RSExecRole` role.</span></span>

#### <a name="to-create-rsexecrole-in-the-master-system-database-using-management-studio"></a><span data-ttu-id="e687b-126">Para crear el rol RSExecRole en la base de datos del sistema maestra mediante Management Studio</span><span class="sxs-lookup"><span data-stu-id="e687b-126">To create RSExecRole in the Master system database using Management Studio</span></span>

1.  <span data-ttu-id="e687b-127">Inicie [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y conéctese a una instancia de [!INCLUDE[ssDE](../../../includes/ssde-md.md)] que hospede la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e687b-127">Start [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that hosts the report server database.</span></span>

2.  <span data-ttu-id="e687b-128">Abra **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="e687b-128">Open **Databases**.</span></span>

3.  <span data-ttu-id="e687b-129">Abra **Bases de datos del sistema**.</span><span class="sxs-lookup"><span data-stu-id="e687b-129">Open **System Databases**.</span></span>

4.  <span data-ttu-id="e687b-130">Abra `Master`.</span><span class="sxs-lookup"><span data-stu-id="e687b-130">Open `Master`.</span></span>

5.  <span data-ttu-id="e687b-131">Abra **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e687b-131">Open **Security**.</span></span>

6.  <span data-ttu-id="e687b-132">Abra **Roles**.</span><span class="sxs-lookup"><span data-stu-id="e687b-132">Open **Roles**.</span></span>

7.  <span data-ttu-id="e687b-133">Haga clic con el botón derecho en **Roles de base de datos**y seleccione **Nuevo rol de la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="e687b-133">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="e687b-134">Aparece la página General.</span><span class="sxs-lookup"><span data-stu-id="e687b-134">The General page appears.</span></span>

8.  <span data-ttu-id="e687b-135">En **nombre de rol**, escriba `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="e687b-135">In **Role name**, type `RSExecRole`.</span></span>

9. <span data-ttu-id="e687b-136">En **Propietario**, escriba **DBO**.</span><span class="sxs-lookup"><span data-stu-id="e687b-136">In **Owner**, type **DBO**.</span></span>

10. <span data-ttu-id="e687b-137">Haga clic en **Elementos protegibles**.</span><span class="sxs-lookup"><span data-stu-id="e687b-137">Click **Securables**.</span></span>

11. <span data-ttu-id="e687b-138">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e687b-138">Click **Search**.</span></span> <span data-ttu-id="e687b-139">Aparece el cuadro de diálogo **Agregar objetos** .</span><span class="sxs-lookup"><span data-stu-id="e687b-139">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="e687b-140">La opción **Especificar objetos** está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e687b-140">The **Specific Objects** option is selected by default.</span></span>

12. <span data-ttu-id="e687b-141">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e687b-141">Click **OK**.</span></span> <span data-ttu-id="e687b-142">Aparece el cuadro de diálogo **Seleccionar objetos** .</span><span class="sxs-lookup"><span data-stu-id="e687b-142">The **Select Objects** dialog box appears.</span></span>

13. <span data-ttu-id="e687b-143">Haga clic en **Tipos de objeto**.</span><span class="sxs-lookup"><span data-stu-id="e687b-143">Click **Object Types**.</span></span>

14. <span data-ttu-id="e687b-144">Haga clic en **Procedimientos almacenados extendidos**.</span><span class="sxs-lookup"><span data-stu-id="e687b-144">Click **Extended Stored Procedures**.</span></span>

15. <span data-ttu-id="e687b-145">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e687b-145">Click **OK**.</span></span>

16. <span data-ttu-id="e687b-146">Haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="e687b-146">Click **Browse**.</span></span>

17. <span data-ttu-id="e687b-147">Desplácese hacia abajo en la lista de procedimientos almacenados extendidos y seleccione los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e687b-147">Scroll down the list of extended stored procedures and select the following:</span></span>

    1.  <span data-ttu-id="e687b-148">xp_sqlagent_enum_jobs</span><span class="sxs-lookup"><span data-stu-id="e687b-148">xp_sqlagent_enum_jobs</span></span>

    2.  <span data-ttu-id="e687b-149">xp_sqlagent_is_starting</span><span class="sxs-lookup"><span data-stu-id="e687b-149">xp_sqlagent_is_starting</span></span>

    3.  <span data-ttu-id="e687b-150">xp_sqlagent_notify</span><span class="sxs-lookup"><span data-stu-id="e687b-150">xp_sqlagent_notify</span></span>

18. <span data-ttu-id="e687b-151">Haga clic en **Aceptar**y, a continuación, vuelva a hacer clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="e687b-151">Click **OK**, and the click **OK** again.</span></span>

19. <span data-ttu-id="e687b-152">En la fila **Ejecutar** , en la columna **Conceder** , haga clic en la casilla y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e687b-152">In the **Execute** row, in the **Grant** column, click the check box, and then click **OK**.</span></span>

20. <span data-ttu-id="e687b-153">Repita este paso con cada uno de los procedimientos almacenados restantes.</span><span class="sxs-lookup"><span data-stu-id="e687b-153">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="e687b-154">`RSExecRole` debe tener concedidos permisos de ejecución para los tres procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="e687b-154">`RSExecRole` must be granted Execute permissions for all three stored procedures.</span></span>

 <span data-ttu-id="e687b-155">![Página Propiedades del rol de la base de datos](../media/rsexecroledbproperties.gif "Página Propiedades del rol de la base de datos")</span><span class="sxs-lookup"><span data-stu-id="e687b-155">![Database Role Properties page](../media/rsexecroledbproperties.gif "Database Role Properties page")</span></span>

## <a name="create-rsexecrole-in-msdb"></a><span data-ttu-id="e687b-156">Crear el rol RSExecRole en la base de datos MSDB</span><span class="sxs-lookup"><span data-stu-id="e687b-156">Create RSExecRole in MSDB</span></span>
 <span data-ttu-id="e687b-157">Reporting Services utiliza procedimientos almacenados para el servicio Agente SQL Server y recupera información de los trabajos en las tablas del sistema para admitir las operaciones programadas.</span><span class="sxs-lookup"><span data-stu-id="e687b-157">Reporting Services uses stored procedures for SQL Server Agent service and retrieves job information from system tables to support scheduled operations.</span></span> <span data-ttu-id="e687b-158">En los pasos siguientes se explica cómo conceder al rol RSExecRole permisos de ejecución para los procedimientos y permisos de selección en las tablas.</span><span class="sxs-lookup"><span data-stu-id="e687b-158">The following steps explain how to grant Execute permissions for the procedures and Select permissions on the tables to the RSExecRole.</span></span>

#### <a name="to-create-rsexecrole-in-the-msdb-system-database"></a><span data-ttu-id="e687b-159">Para crear el rol RSExecRole en la base de datos del sistema MSDB</span><span class="sxs-lookup"><span data-stu-id="e687b-159">To create RSExecRole in the MSDB system database</span></span>

1.  <span data-ttu-id="e687b-160">Repita los pasos similares para conceder permisos a procedimientos almacenados y tablas en MSDB.</span><span class="sxs-lookup"><span data-stu-id="e687b-160">Repeat similar steps for granting permissions to stored procedures and tables in MSDB.</span></span> <span data-ttu-id="e687b-161">Para simplificar los pasos, proporcionará los procedimientos almacenados y las tablas de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="e687b-161">To simplify the steps, you will provision the stored procedures and tables separately.</span></span>

2.  <span data-ttu-id="e687b-162">Abra `MSDB`.</span><span class="sxs-lookup"><span data-stu-id="e687b-162">Open `MSDB`.</span></span>

3.  <span data-ttu-id="e687b-163">Abra **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e687b-163">Open **Security**.</span></span>

4.  <span data-ttu-id="e687b-164">Abra **Roles**.</span><span class="sxs-lookup"><span data-stu-id="e687b-164">Open **Roles**.</span></span>

5.  <span data-ttu-id="e687b-165">Haga clic con el botón derecho en **Roles de base de datos**y seleccione **Nuevo rol de la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="e687b-165">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="e687b-166">Aparece la página General.</span><span class="sxs-lookup"><span data-stu-id="e687b-166">The General page appears.</span></span>

6.  <span data-ttu-id="e687b-167">En nombre de rol, escriba `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="e687b-167">In Role name, type `RSExecRole`.</span></span>

7.  <span data-ttu-id="e687b-168">En propietario, escriba **DBO**.</span><span class="sxs-lookup"><span data-stu-id="e687b-168">In Owner, type **DBO**.</span></span>

8.  <span data-ttu-id="e687b-169">Haga clic en **Elementos protegibles**.</span><span class="sxs-lookup"><span data-stu-id="e687b-169">Click **Securables**.</span></span>

9. <span data-ttu-id="e687b-170">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e687b-170">Click **Add**.</span></span> <span data-ttu-id="e687b-171">Aparece el cuadro de diálogo **Agregar objetos** .</span><span class="sxs-lookup"><span data-stu-id="e687b-171">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="e687b-172">La opción **Especificar objetos** está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e687b-172">The **Specify Objects** option is selected by default.</span></span>

10. <span data-ttu-id="e687b-173">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e687b-173">Click **OK**.</span></span>

11. <span data-ttu-id="e687b-174">Haga clic en **Tipos de objeto**.</span><span class="sxs-lookup"><span data-stu-id="e687b-174">Click **Object Types**.</span></span>

12. <span data-ttu-id="e687b-175">Haga clic en **Procedimientos almacenados**.</span><span class="sxs-lookup"><span data-stu-id="e687b-175">Click **Stored Procedures.**</span></span>

13. <span data-ttu-id="e687b-176">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e687b-176">Click **OK**.</span></span>

14. <span data-ttu-id="e687b-177">Haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="e687b-177">Click **Browse**.</span></span>

15. <span data-ttu-id="e687b-178">Desplácese hacia abajo en la lista de elementos y seleccione los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e687b-178">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="e687b-179">sp_add_category</span><span class="sxs-lookup"><span data-stu-id="e687b-179">sp_add_category</span></span>

    2.  <span data-ttu-id="e687b-180">sp_add_job</span><span class="sxs-lookup"><span data-stu-id="e687b-180">sp_add_job</span></span>

    3.  <span data-ttu-id="e687b-181">sp_add_jobschedule</span><span class="sxs-lookup"><span data-stu-id="e687b-181">sp_add_jobschedule</span></span>

    4.  <span data-ttu-id="e687b-182">sp_add_jobserver</span><span class="sxs-lookup"><span data-stu-id="e687b-182">sp_add_jobserver</span></span>

    5.  <span data-ttu-id="e687b-183">sp_add_jobstep</span><span class="sxs-lookup"><span data-stu-id="e687b-183">sp_add_jobstep</span></span>

    6.  <span data-ttu-id="e687b-184">sp_delete_job</span><span class="sxs-lookup"><span data-stu-id="e687b-184">sp_delete_job</span></span>

    7.  <span data-ttu-id="e687b-185">sp_help_category</span><span class="sxs-lookup"><span data-stu-id="e687b-185">sp_help_category</span></span>

    8.  <span data-ttu-id="e687b-186">sp_help_job</span><span class="sxs-lookup"><span data-stu-id="e687b-186">sp_help_job</span></span>

    9. <span data-ttu-id="e687b-187">sp_help_jobschedule</span><span class="sxs-lookup"><span data-stu-id="e687b-187">sp_help_jobschedule</span></span>

    10. <span data-ttu-id="e687b-188">sp_verify_job_identifiers</span><span class="sxs-lookup"><span data-stu-id="e687b-188">sp_verify_job_identifiers</span></span>

16. <span data-ttu-id="e687b-189">Haga clic en **Aceptar**y, a continuación, vuelva a hacer clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="e687b-189">Click **OK**, and the click **OK** again.</span></span>

17. <span data-ttu-id="e687b-190">Seleccione el primer procedimiento almacenado: sp_add_category.</span><span class="sxs-lookup"><span data-stu-id="e687b-190">Select the first stored procedure: sp_add_category.</span></span>

18. <span data-ttu-id="e687b-191">En la fila **Ejecutar** , en la columna **Conceder** , haga clic en la casilla y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e687b-191">In the **Execute** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

19. <span data-ttu-id="e687b-192">Repita este paso con cada uno de los procedimientos almacenados restantes.</span><span class="sxs-lookup"><span data-stu-id="e687b-192">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="e687b-193">Se deben conceder al rol RSExecRole permisos de ejecución para los diez procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="e687b-193">RSExecRole must be granted Execute permissions for all ten stored procedures.</span></span>

20. <span data-ttu-id="e687b-194">En la pestaña Elementos protegibles, haga clic en **Agregar** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e687b-194">On the Securables tab, and click **Add** again.</span></span> <span data-ttu-id="e687b-195">Aparece el cuadro de diálogo **Agregar objetos** .</span><span class="sxs-lookup"><span data-stu-id="e687b-195">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="e687b-196">La opción **Especificar objetos** está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e687b-196">The **Specify Objects** option is selected by default.</span></span>

21. <span data-ttu-id="e687b-197">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e687b-197">Click **OK**.</span></span>

22. <span data-ttu-id="e687b-198">Haga clic en **Tipos de objeto**.</span><span class="sxs-lookup"><span data-stu-id="e687b-198">Click **Object Types**.</span></span>

23. <span data-ttu-id="e687b-199">Haga clic en **Tablas**.</span><span class="sxs-lookup"><span data-stu-id="e687b-199">Click **Tables.**</span></span>

24. <span data-ttu-id="e687b-200">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e687b-200">Click **OK**.</span></span>

25. <span data-ttu-id="e687b-201">Haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="e687b-201">Click **Browse**.</span></span>

26. <span data-ttu-id="e687b-202">Desplácese hacia abajo en la lista de elementos y seleccione los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e687b-202">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="e687b-203">syscategories</span><span class="sxs-lookup"><span data-stu-id="e687b-203">syscategories</span></span>

    2.  <span data-ttu-id="e687b-204">sysjobs</span><span class="sxs-lookup"><span data-stu-id="e687b-204">sysjobs</span></span>

27. <span data-ttu-id="e687b-205">Haga clic en **Aceptar**y, a continuación, vuelva a hacer clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="e687b-205">Click **OK**, and the click **OK** again.</span></span>

28. <span data-ttu-id="e687b-206">Seleccione la primera tabla: syscategories.</span><span class="sxs-lookup"><span data-stu-id="e687b-206">Select the first table: syscategories.</span></span>

29. <span data-ttu-id="e687b-207">En la fila **Seleccionar** , en la columna **Conceder** , haga clic en la casilla y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e687b-207">In the **Select** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

30. <span data-ttu-id="e687b-208">Repita este procedimiento con la tabla sysjobs.</span><span class="sxs-lookup"><span data-stu-id="e687b-208">Repeat for the sysjobs table.</span></span> <span data-ttu-id="e687b-209">Se deben conceder al rol RSExecRole permisos de selección para ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="e687b-209">RSExecRole must be granted Select permissions for both tables.</span></span>

## <a name="move-the-report-server-database"></a><span data-ttu-id="e687b-210">Mover la base de datos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="e687b-210">Move the Report Server Database</span></span>
 <span data-ttu-id="e687b-211">Después de crear los roles, puede mover la base de datos del servidor de informes a una instancia nueva de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e687b-211">After you create the roles, you can move the report server database to new SQL Server instance.</span></span> <span data-ttu-id="e687b-212">Para más información, vea [Mover las bases de datos del servidor de informes a otro equipo &#40;Modo nativo de SSRS&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e687b-212">For more information, see [Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span></span>

 <span data-ttu-id="e687b-213">Si va a actualizar [!INCLUDE[ssDE](../../../includes/ssde-md.md)] a [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], puede hacerlo antes o después de mover la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e687b-213">If you are upgrading the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can upgrade it before or after moving the database.</span></span>

 <span data-ttu-id="e687b-214">La base de datos del servidor de informes se actualizará a [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] automáticamente cuando el servidor de informes se conecte a ella.</span><span class="sxs-lookup"><span data-stu-id="e687b-214">The report server database will be upgraded to the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] automatically when the report server connects to it.</span></span> <span data-ttu-id="e687b-215">No hay ningún paso concreto requerido para actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e687b-215">There are no specific steps required for upgrading the database.</span></span>

## <a name="restore-encryption-keys-and-verify-your-work"></a><span data-ttu-id="e687b-216">Restaurar las claves de cifrado y comprobar el trabajo</span><span class="sxs-lookup"><span data-stu-id="e687b-216">Restore Encryption Keys and Verify Your Work</span></span>
 <span data-ttu-id="e687b-217">Si ha adjuntado las bases de datos del servidor de informes, ahora debe poder completar los pasos siguientes para comprobar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="e687b-217">If you have attached the report server databases, you should now be able to complete the following steps to verify your work.</span></span>

#### <a name="to-verify-report-server-operability-after-a-database-move"></a><span data-ttu-id="e687b-218">Para comprobar la capacidad de operación del servidor de informes después de mover una base de datos</span><span class="sxs-lookup"><span data-stu-id="e687b-218">To verify report server operability after a database move</span></span>

1.  <span data-ttu-id="e687b-219">Inicie la herramienta Configuración de Reporting Services y conéctese al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e687b-219">Start the Reporting Services Configuration tool and connect to the report server.</span></span>

2.  <span data-ttu-id="e687b-220">Haga clic en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="e687b-220">Click **Database**.</span></span>

3.  <span data-ttu-id="e687b-221">Haga clic en **Cambiar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="e687b-221">Click **Change Database**.</span></span>

4.  <span data-ttu-id="e687b-222">Haga clic en **Elija una base de datos del servidor de informes existente**.</span><span class="sxs-lookup"><span data-stu-id="e687b-222">Click **Choose an existing report server database**.</span></span>

5.  <span data-ttu-id="e687b-223">Escriba el nombre del servidor del motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e687b-223">Enter the server name of the Database Engine.</span></span> <span data-ttu-id="e687b-224">Si ha adjuntado las bases de datos del servidor de informes a una instancia con nombre, debe escribir el nombre de la instancia con este formato: \<servername> \\<InstanceName \> .</span><span class="sxs-lookup"><span data-stu-id="e687b-224">If you attached the report server databases to a named instance, you must type the instance name in this format: \<servername>\\<instancename\>.</span></span>

6.  <span data-ttu-id="e687b-225">Haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="e687b-225">Click **Test Connection**.</span></span>

7.  <span data-ttu-id="e687b-226">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="e687b-226">Click **Next**.</span></span>

8.  <span data-ttu-id="e687b-227">En Base de datos, seleccione la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e687b-227">On the Database, select the report server database.</span></span>

9. <span data-ttu-id="e687b-228">Haga clic en **Siguiente** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="e687b-228">Click **Next** and complete the wizard.</span></span>

10. <span data-ttu-id="e687b-229">Haga clic en **Claves de cifrado**.</span><span class="sxs-lookup"><span data-stu-id="e687b-229">Click **Encryption Keys**.</span></span>

11. <span data-ttu-id="e687b-230">Haga clic en **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="e687b-230">Click **Restore**.</span></span>

12. <span data-ttu-id="e687b-231">Seleccione el archivo seguro (.snk) que tiene la copia de seguridad de la clave simétrica utilizada para descifrar las credenciales almacenadas y la información de conexión en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e687b-231">Select the strong file (.snk) that has the backup copy of the symmetric key used to decrypt stored credentials and connection information in the report server database.</span></span>

13. <span data-ttu-id="e687b-232">Escriba la contraseña y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e687b-232">Enter the password and click **OK**.</span></span>

14. <span data-ttu-id="e687b-233">Haga clic en **Dirección URL del Administrador de informes**.</span><span class="sxs-lookup"><span data-stu-id="e687b-233">Click **Report Manager URL**.</span></span>

15. <span data-ttu-id="e687b-234">Haga clic en el vínculo para abrir el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="e687b-234">Click the link to open Report Manager.</span></span> <span data-ttu-id="e687b-235">Debe ver los elementos del servidor de informes de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e687b-235">You should see the report server items from the report server database.</span></span>

## <a name="see-also"></a><span data-ttu-id="e687b-236">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e687b-236">See Also</span></span>
 <span data-ttu-id="e687b-237">[Mover las bases de datos del servidor de informes a otro equipo &#40;el modo nativo de SSRS&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Administrador de configuración de Reporting Services &#40;modo nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [crear una base de datos del servidor de informes en modo nativo &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [realizar copias de seguridad y restaurar Reporting Services claves de cifrado](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span><span class="sxs-lookup"><span data-stu-id="e687b-237">[Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span></span>


