---
title: Creación de una auditoría de servidor y una especificación de auditoría de servidor, utilizando | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SQLAUDIT.FILTER.F1
- sql12.swb.sqlaudit.srvaudit.general.f1
- sql12.swb.sqlaudit.general.f1
helpviewer_keywords:
- server audit [SQL Server]
- audits [SQL Server], specification
ms.assetid: 6624b1ab-7ec8-44ce-8292-397edf644394
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a648a975ae9f2c4139a8ebd584f6998f4d0fa1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746215"
---
# <a name="create-a-server-audit-and-server-audit-specification"></a><span data-ttu-id="2d16d-102">Crear una auditoría de servidor y una especificación de auditoría de servidor</span><span class="sxs-lookup"><span data-stu-id="2d16d-102">Create a Server Audit and Server Audit Specification</span></span>
  <span data-ttu-id="2d16d-103">En este tema se describe cómo crear una auditoría de servidor y una especificación de auditoría de servidor en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d16d-103">This topic describes how to create a server audit and server audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2d16d-104">La*auditoría* de una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o de una base de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implica el seguimiento y registro de los eventos que se producen en el sistema.</span><span class="sxs-lookup"><span data-stu-id="2d16d-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="2d16d-105">El objeto *SQL Server Audit* recopila una única instancia de acciones y grupos de acciones de nivel de servidor o de base de datos para su supervisión.</span><span class="sxs-lookup"><span data-stu-id="2d16d-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="2d16d-106">La auditoría se realiza en el nivel de instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d16d-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="2d16d-107">Es posible tener varias auditorías por cada instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d16d-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="2d16d-108">El objeto *Especificación de auditoría de servidor* pertenece a una auditoría.</span><span class="sxs-lookup"><span data-stu-id="2d16d-108">The *Server Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="2d16d-109">Puede crear una especificación de auditoría de servidor por cada auditoría, ya que ambos se crean en el ámbito de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d16d-109">You can create one server audit specification per audit, because both are created at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance scope.</span></span> <span data-ttu-id="2d16d-110">Para obtener más información, vea [SQL Server Audit &#40;motor de base de datos&#41;](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="2d16d-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="2d16d-111">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="2d16d-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2d16d-112">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="2d16d-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2d16d-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2d16d-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2d16d-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2d16d-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2d16d-115">**Para crear una auditoría de servidor y una especificación de auditoría de servidor, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="2d16d-115">**To create a server audit and server audit specification, using:**</span></span>  
  
     [<span data-ttu-id="2d16d-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d16d-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2d16d-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d16d-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d16d-118">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2d16d-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2d16d-119">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2d16d-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2d16d-120">Para poder crear una especificación de auditoría de servidor, debe existir la auditoría.</span><span class="sxs-lookup"><span data-stu-id="2d16d-120">An audit must exist before creating a server audit specification for it.</span></span> <span data-ttu-id="2d16d-121">Cuando se crea una especificación de auditoría de servidor, está en estado deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2d16d-121">When a server audit specification is created, it is in a disabled state.</span></span>  
  
-   <span data-ttu-id="2d16d-122">La instrucción CREATE SERVER AUDIT está en el ámbito de una transacción.</span><span class="sxs-lookup"><span data-stu-id="2d16d-122">The CREATE SERVER AUDIT statement is in a transaction's scope.</span></span> <span data-ttu-id="2d16d-123">Si se revierte la transacción, también se revierte la instrucción.</span><span class="sxs-lookup"><span data-stu-id="2d16d-123">If the transaction is rolled back, the statement is also rolled back.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2d16d-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2d16d-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d16d-125">Permisos</span><span class="sxs-lookup"><span data-stu-id="2d16d-125">Permissions</span></span>  
  
-   <span data-ttu-id="2d16d-126">Para crear, modificar o quitar una auditoría de servidor, las entidades de seguridad deben tener el permiso ALTER ANY SERVER AUDIT o CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="2d16d-126">To create, alter, or drop a server audit, principals require the ALTER ANY SERVER AUDIT or the CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="2d16d-127">Los usuarios con el permiso ALTER ANY SERVER AUDIT pueden crear especificaciones de auditoría de servidor y enlazarlas a cualquier auditoría.</span><span class="sxs-lookup"><span data-stu-id="2d16d-127">Users with the ALTER ANY SERVER AUDIT permission can create server audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="2d16d-128">Una vez creada una especificación de auditoría de servidor, las entidades de seguridad que cuenten con los permisos CONTROL SERVER o ALTER ANY SERVER AUDIT, así como la cuenta sysadmin, o las entidades de seguridad que tengan acceso explícito a la auditoría podrán ver dicha especificación.</span><span class="sxs-lookup"><span data-stu-id="2d16d-128">After a server audit specification is created, it can be viewed by principals with the CONTROL SERVER or ALTER ANY SERVER AUDIT permissions, the sysadmin account, or principals having explicit access to the audit.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2d16d-129">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d16d-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="2d16d-130">Para crear una auditoría de servidor</span><span class="sxs-lookup"><span data-stu-id="2d16d-130">To create a server audit</span></span>  
  
1.  <span data-ttu-id="2d16d-131">En el Explorador de objetos, expanda la carpeta **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="2d16d-131">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="2d16d-132">Haga clic con el botón derecho en la carpeta **Auditorías** y, después, seleccione **Nueva auditoría...** .</span><span class="sxs-lookup"><span data-stu-id="2d16d-132">Right-click the **Audits** folder and select **New Audit...**.</span></span>  
  
     <span data-ttu-id="2d16d-133">Las siguientes opciones están disponibles en la página **General** del cuadro de diálogo **Crear auditoría** .</span><span class="sxs-lookup"><span data-stu-id="2d16d-133">The following options are available on the **General** page of the **Create Audit** dialog box.</span></span>  
  
     <span data-ttu-id="2d16d-134">**Nombre de auditoría**</span><span class="sxs-lookup"><span data-stu-id="2d16d-134">**Audit name**</span></span>  
     <span data-ttu-id="2d16d-135">Nombre de la auditoría.</span><span class="sxs-lookup"><span data-stu-id="2d16d-135">The name of the audit.</span></span> <span data-ttu-id="2d16d-136">Se genera automáticamente al crear una nueva auditoría, pero se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="2d16d-136">This is generated automatically when you create a new audit but is editable.</span></span>  
  
     <span data-ttu-id="2d16d-137">**Retardo de cola (en milisegundos)**</span><span class="sxs-lookup"><span data-stu-id="2d16d-137">**Queue delay (in milliseconds)**</span></span>  
     <span data-ttu-id="2d16d-138">Especifica la cantidad de tiempo, en milisegundos, que puede transcurrir antes de exigir que se procesen las acciones de auditoría.</span><span class="sxs-lookup"><span data-stu-id="2d16d-138">Specifies the amount of time in milliseconds that can elapse before audit actions are forced to be processed.</span></span>  <span data-ttu-id="2d16d-139">El valor 0 indica la entrega sincrónica.</span><span class="sxs-lookup"><span data-stu-id="2d16d-139">A value of 0 indicates synchronous delivery.</span></span> <span data-ttu-id="2d16d-140">El valor mínimo predeterminado es **1000** (1 segundo).</span><span class="sxs-lookup"><span data-stu-id="2d16d-140">The default minimum value is **1000** (1 second).</span></span> <span data-ttu-id="2d16d-141">El máximo es 2.147.483.647 (2.147.483,647 segundos, o 24 días, 20 horas, 31 minutos y 23,647 segundos).</span><span class="sxs-lookup"><span data-stu-id="2d16d-141">The maximum is 2,147,483,647 (2,147,483.647 seconds or 24 days, 20 hours, 31 minutes, 23.647 seconds).</span></span>  
  
     <span data-ttu-id="2d16d-142">**Si hay un error de registro de auditoría:**</span><span class="sxs-lookup"><span data-stu-id="2d16d-142">**On Audit Log Failure:**</span></span>  
     <span data-ttu-id="2d16d-143">**Continuar**</span><span class="sxs-lookup"><span data-stu-id="2d16d-143">**Continue**</span></span>  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="2d16d-144">Las operaciones de  continúan.</span><span class="sxs-lookup"><span data-stu-id="2d16d-144">operations continue.</span></span> <span data-ttu-id="2d16d-145">Los registros de auditoría no se conservan.</span><span class="sxs-lookup"><span data-stu-id="2d16d-145">Audit records are not retained.</span></span> <span data-ttu-id="2d16d-146">La auditoría continúa intentando el registro de eventos y se reanudará si se resuelve la condición de error.</span><span class="sxs-lookup"><span data-stu-id="2d16d-146">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="2d16d-147">La selección de la opción **Continuar** puede permitir que una actividad no se audite, con lo que se infringirían las directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2d16d-147">Selecting the **Continue** option can allow unaudited activity which could violate your security policies.</span></span> <span data-ttu-id="2d16d-148">Seleccione esta opción cuando la operación de continuación del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] sea más importante que el mantenimiento de una auditoría completa.</span><span class="sxs-lookup"><span data-stu-id="2d16d-148">Select this option when continuing operation of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] is more important than maintaining a complete audit.</span></span> <span data-ttu-id="2d16d-149">Esta es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2d16d-149">This is the default selection.</span></span>  
  
     <span data-ttu-id="2d16d-150">**Apagar el servidor**</span><span class="sxs-lookup"><span data-stu-id="2d16d-150">**Shut down server**</span></span>  
     <span data-ttu-id="2d16d-151">Fuerza el apagado del servidor cuando la instancia de servidor que escribe en el destino no puede escribir datos en el destino de la auditoría.</span><span class="sxs-lookup"><span data-stu-id="2d16d-151">Forces a server shut down when the server instance writing to the target cannot write data to the audit target.</span></span> <span data-ttu-id="2d16d-152">Para poder usarlo, es preciso utilizar un inicio de sesión con el permiso `SHUTDOWN`.</span><span class="sxs-lookup"><span data-stu-id="2d16d-152">The login issuing this must have the `SHUTDOWN` permission.</span></span> <span data-ttu-id="2d16d-153">Si el inicio de sesión no tiene dicho permiso, la función generará un error y se mostrará un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="2d16d-153">If the logon does not have this permission, this function will fail and an error message will be raised.</span></span> <span data-ttu-id="2d16d-154">No se producirán eventos auditados.</span><span class="sxs-lookup"><span data-stu-id="2d16d-154">No audited events occur.</span></span> <span data-ttu-id="2d16d-155">Seleccione esta opción si un error de auditoría puede poner en peligro la seguridad o la integridad del sistema.</span><span class="sxs-lookup"><span data-stu-id="2d16d-155">Select this option when an audit failure could compromise the security or integrity of the system.</span></span>  
  
     <span data-ttu-id="2d16d-156">**Error en la operación**</span><span class="sxs-lookup"><span data-stu-id="2d16d-156">**Fail operation**</span></span>  
     <span data-ttu-id="2d16d-157">En los casos en que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit no puede escribir en el registro de auditoría, esta opción haría que las acciones de base de datos produjesen un error si generasen eventos auditados.</span><span class="sxs-lookup"><span data-stu-id="2d16d-157">In cases where the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit cannot write to the audit log this option causes database actions to fail if they would otherwise cause audited events.</span></span> <span data-ttu-id="2d16d-158">No se producirán eventos auditados.</span><span class="sxs-lookup"><span data-stu-id="2d16d-158">No audited events occur.</span></span> <span data-ttu-id="2d16d-159">Las acciones que no producen eventos auditados pueden continuar.</span><span class="sxs-lookup"><span data-stu-id="2d16d-159">Actions which do not cause audited events can continue.</span></span> <span data-ttu-id="2d16d-160">La auditoría continúa intentando el registro de eventos y se reanudará si se resuelve la condición de error.</span><span class="sxs-lookup"><span data-stu-id="2d16d-160">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="2d16d-161">Seleccione esta opción si el mantenimiento de una auditoría completa es más importante que el acceso total al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d16d-161">Select this option when maintaining a complete audit is more important than full access to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="2d16d-162">Cuando la auditoría está en un estado de error, la conexión de administrador dedicada puede seguir realizando eventos auditados.</span><span class="sxs-lookup"><span data-stu-id="2d16d-162">When the audit is in a failed state, the Dedicated Administrator Connection can continue to perform audited events.</span></span>  
  
     <span data-ttu-id="2d16d-163">Lista**Destino de auditoría**</span><span class="sxs-lookup"><span data-stu-id="2d16d-163">**Audit destination** list</span></span>  
     <span data-ttu-id="2d16d-164">Especifica el destino de los datos de la auditoría.</span><span class="sxs-lookup"><span data-stu-id="2d16d-164">Specifies the target for auditing data.</span></span> <span data-ttu-id="2d16d-165">Las opciones disponibles son un archivo binario, el registro de aplicación Windows o el registro de seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="2d16d-165">The available options are a binary file, the Windows Application log, or the Windows Security log.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="2d16d-166">no puede escribir en el registro de seguridad de Windows sin configurar valores adicionales en Windows.</span><span class="sxs-lookup"><span data-stu-id="2d16d-166">cannot write to the Windows Security log without configuring additional settings in Windows.</span></span> <span data-ttu-id="2d16d-167">Para obtener más información, vea [Escribir eventos de auditoría de SQL Server en el registro de seguridad](write-sql-server-audit-events-to-the-security-log.md).</span><span class="sxs-lookup"><span data-stu-id="2d16d-167">For more information, see [Write SQL Server Audit Events to the Security Log](write-sql-server-audit-events-to-the-security-log.md).</span></span>  
  
     <span data-ttu-id="2d16d-168">**Ruta de acceso del archivo**</span><span class="sxs-lookup"><span data-stu-id="2d16d-168">**File path**</span></span>  
     <span data-ttu-id="2d16d-169">Especifica la ubicación de la carpeta donde se escriben los datos de la auditoría si se ha especificado un archivo **Destino de auditoría** .</span><span class="sxs-lookup"><span data-stu-id="2d16d-169">Specifies the location of the folder where audit data is written when the **Audit destination** is a file.</span></span>  
  
     <span data-ttu-id="2d16d-170">**Puntos suspensivos (...)**</span><span class="sxs-lookup"><span data-stu-id="2d16d-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="2d16d-171">Abre el cuadro de diálogo **Buscar carpeta-**_SERVER_NAME_ para especificar una ruta de acceso de archivo o crear una carpeta donde se escribe el archivo de auditoría.</span><span class="sxs-lookup"><span data-stu-id="2d16d-171">Opens the **Locate Folder -**_server_name_ dialog box to specify a file path or create a folder where the audit file is written.</span></span>  
  
     <span data-ttu-id="2d16d-172">**Límite máximo del archivo de auditoría:**</span><span class="sxs-lookup"><span data-stu-id="2d16d-172">**Audit File Maximum Limit:**</span></span>  
     <span data-ttu-id="2d16d-173">**Máximo de archivos de sustitución incremental**</span><span class="sxs-lookup"><span data-stu-id="2d16d-173">**Maximum rollover files**</span></span>  
     <span data-ttu-id="2d16d-174">Especifica que, si se alcanza el número máximo de archivos de auditoría, el contenido de los nuevos archivos reemplazará a los archivos de auditoría más antiguos.</span><span class="sxs-lookup"><span data-stu-id="2d16d-174">Specifies that, when the maximum number of audit files is reached, the oldest audit files are overwritten by new file content.</span></span>  
  
     <span data-ttu-id="2d16d-175">**Número máximo de archivos**</span><span class="sxs-lookup"><span data-stu-id="2d16d-175">**Maximum files**</span></span>  
     <span data-ttu-id="2d16d-176">Especifica que, si se alcanza el número máximo de archivos de auditoría, cualquier acción que ocasione la generación de eventos de auditoría adicionales producirá un error y se mostrará un mensaje.</span><span class="sxs-lookup"><span data-stu-id="2d16d-176">Specifies that, when the maximum number of audit files is reached, any action that causes additional audit events to be generated will fail with an error.</span></span>  
  
     <span data-ttu-id="2d16d-177">Casilla**Ilimitado**</span><span class="sxs-lookup"><span data-stu-id="2d16d-177">**Unlimited** check box</span></span>  
     <span data-ttu-id="2d16d-178">Cuando se activa la casilla **Ilimitado** en **Máximo de archivos de sustitución incremental** , no se impone ningún límite en cuanto al número de archivos de auditoría que se crearán.</span><span class="sxs-lookup"><span data-stu-id="2d16d-178">When the **Unlimited** check box under **Maximum rollover files** is selected, there is no limit imposed on the number of audit files that will be created.</span></span> <span data-ttu-id="2d16d-179">La casilla **Ilimitado** está activada de forma predeterminada y se aplica a las selecciones de **Máximo de archivos de sustitución incremental** y **Máximo de archivos** .</span><span class="sxs-lookup"><span data-stu-id="2d16d-179">The **Unlimited** check box is selected by default and applies to both the **Maximum rollover files** and **Maximum files** selections.</span></span>  
  
     <span data-ttu-id="2d16d-180">Casilla**Número de archivos**</span><span class="sxs-lookup"><span data-stu-id="2d16d-180">**Number of files** box</span></span>  
     <span data-ttu-id="2d16d-181">Especifica el número de archivos de auditoría que se crearán, hasta 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="2d16d-181">Specifies the number of audit files to be created, up to 2,147,483,647.</span></span> <span data-ttu-id="2d16d-182">Esta opción solo está disponible si se desactiva la casilla **Ilimitado** .</span><span class="sxs-lookup"><span data-stu-id="2d16d-182">This option is only available if **Unlimited** is unchecked.</span></span>  
  
     <span data-ttu-id="2d16d-183">**Tamaño máximo del archivo**</span><span class="sxs-lookup"><span data-stu-id="2d16d-183">**Maximum file size**</span></span>  
     <span data-ttu-id="2d16d-184">Especifica el tamaño máximo de un archivo de auditoría en megabytes (MB), gigabytes (GB) o terabytes (TB).</span><span class="sxs-lookup"><span data-stu-id="2d16d-184">Specifies the maximum size for an audit file in either megabytes (MB), gigabytes (GB), or terabytes (TB).</span></span> <span data-ttu-id="2d16d-185">Puede especificar entre 1024 MB y 2.147.483.647 TB.</span><span class="sxs-lookup"><span data-stu-id="2d16d-185">You can specify between 1024 MB and 2,147,483,647 TB.</span></span> <span data-ttu-id="2d16d-186">La activación de la casilla **Ilimitado** no pone un límite en el tamaño del archivo.</span><span class="sxs-lookup"><span data-stu-id="2d16d-186">Selecting the **Unlimited** check box does not place a limit on the size of the file.</span></span> <span data-ttu-id="2d16d-187">La especificación de un valor inferior a 1024 MB producirá y devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="2d16d-187">Specifying a value lower than 1024 MB will fail, returning an error.</span></span> <span data-ttu-id="2d16d-188">La casilla **Ilimitado** está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2d16d-188">The **Unlimited** check box is selected by default.</span></span>  
  
     <span data-ttu-id="2d16d-189">Casilla**Reservar espacio en disco**</span><span class="sxs-lookup"><span data-stu-id="2d16d-189">**Reserve disk space** check box</span></span>  
     <span data-ttu-id="2d16d-190">Especifica que se debe preasignar una cantidad de espacio en disco igual al tamaño máximo de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="2d16d-190">Specifies that space is pre-allocated on the disk equal to the specified maximum file size.</span></span> <span data-ttu-id="2d16d-191">Este valor solo se puede utilizar si la casilla **Ilimitado** en **Tamaño máximo del archivo** no está activada.</span><span class="sxs-lookup"><span data-stu-id="2d16d-191">This setting can only be used if the **Unlimited** check box under **Maximum file size** is not selected.</span></span> <span data-ttu-id="2d16d-192">Esta casilla no está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2d16d-192">This check box is not selected by default.</span></span>  
  
3.  <span data-ttu-id="2d16d-193">Opcionalmente, en la página **Filtrar** , escriba un predicado, o la cláusula `WHERE` , para la auditoría de servidor de modo que se especifiquen opciones adicionales no disponibles en la página **General** .</span><span class="sxs-lookup"><span data-stu-id="2d16d-193">Optionally, on the **Filter** page, enter a predicate, or `WHERE` clause, to the server audit to specify additional options not available from the **General** page.</span></span> <span data-ttu-id="2d16d-194">Encierre el predicado entre paréntesis; por ejemplo: `(object_name = 'EmployeesTable')`.</span><span class="sxs-lookup"><span data-stu-id="2d16d-194">Enclose the predicate in parentheses; for example: `(object_name = 'EmployeesTable')`.</span></span>  
  
4.  <span data-ttu-id="2d16d-195">Cuando termine de seleccionar opciones, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d16d-195">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="2d16d-196">Para crear una especificación de auditoría de servidor</span><span class="sxs-lookup"><span data-stu-id="2d16d-196">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="2d16d-197">En el Explorador de objetos, haga clic en el signo más para expandir la carpeta **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="2d16d-197">In Object Explorer, click the plus sign to expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="2d16d-198">Haga clic con el botón derecho en la carpeta **Especificaciones de auditoría de servidor** y seleccione **Nueva especificación de auditoría de base de servidor...** .</span><span class="sxs-lookup"><span data-stu-id="2d16d-198">Right-click the **Server Audit Specifications** folder and select **New Server Audit Specification...**.</span></span>  
  
     <span data-ttu-id="2d16d-199">Las siguientes opciones están disponibles en el cuadro de diálogo **Crear especificación de auditoría de servidor** .</span><span class="sxs-lookup"><span data-stu-id="2d16d-199">The following options are available on the **Create Server Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="2d16d-200">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2d16d-200">**Name**</span></span>  
     <span data-ttu-id="2d16d-201">El nombre de la especificación de auditoría de servidor.</span><span class="sxs-lookup"><span data-stu-id="2d16d-201">The name of the server audit specification.</span></span> <span data-ttu-id="2d16d-202">Se genera automáticamente al crear una nueva especificación de auditoría de servidor, pero se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="2d16d-202">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="2d16d-203">**Auditoría**</span><span class="sxs-lookup"><span data-stu-id="2d16d-203">**Audit**</span></span>  
     <span data-ttu-id="2d16d-204">Nombre de una auditoría de servidor existente.</span><span class="sxs-lookup"><span data-stu-id="2d16d-204">The name of an existing server audit.</span></span> <span data-ttu-id="2d16d-205">Escriba el nombre de la auditoría o selecciónelo en la lista.</span><span class="sxs-lookup"><span data-stu-id="2d16d-205">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="2d16d-206">**Tipo de acción de auditoría**</span><span class="sxs-lookup"><span data-stu-id="2d16d-206">**Audit Action Type**</span></span>  
     <span data-ttu-id="2d16d-207">Especifica los grupos de acciones de auditoría y las acciones de auditoría en el nivel de servidor que se desea capturar.</span><span class="sxs-lookup"><span data-stu-id="2d16d-207">Specifies the server-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="2d16d-208">Para obtener la lista de grupos de acciones de auditoría y de acciones de auditoría de nivel de servidor, así como una descripción de los eventos que contienen, vea [Grupos de acciones y acciones de SQL Server Audit](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="2d16d-208">For the list of server-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="2d16d-209">**Esquema de objeto**</span><span class="sxs-lookup"><span data-stu-id="2d16d-209">**Object Schema**</span></span>  
     <span data-ttu-id="2d16d-210">Muestra el esquema para el **Nombre de objeto**especificado.</span><span class="sxs-lookup"><span data-stu-id="2d16d-210">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="2d16d-211">**Nombre de objeto**</span><span class="sxs-lookup"><span data-stu-id="2d16d-211">**Object Name**</span></span>  
     <span data-ttu-id="2d16d-212">Nombre del objeto que se va a auditar.</span><span class="sxs-lookup"><span data-stu-id="2d16d-212">The name of the object to audit.</span></span> <span data-ttu-id="2d16d-213">Este valor solo está disponible para las acciones de auditoría, no se aplica a los grupos de auditoría.</span><span class="sxs-lookup"><span data-stu-id="2d16d-213">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="2d16d-214">**Puntos suspensivos (...)**</span><span class="sxs-lookup"><span data-stu-id="2d16d-214">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="2d16d-215">Abre el cuadro de diálogo **Seleccionar objetos** para buscar y seleccionar un objeto disponible, basándose en el **Tipo de acción de auditoría**especificado.</span><span class="sxs-lookup"><span data-stu-id="2d16d-215">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="2d16d-216">**Nombre de la entidad**</span><span class="sxs-lookup"><span data-stu-id="2d16d-216">**Principal Name**</span></span>  
     <span data-ttu-id="2d16d-217">La cuenta por la que se va filtrar la auditoría para el objeto que se va a auditar.</span><span class="sxs-lookup"><span data-stu-id="2d16d-217">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="2d16d-218">**Puntos suspensivos (...)**</span><span class="sxs-lookup"><span data-stu-id="2d16d-218">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="2d16d-219">Abre el cuadro de diálogo **Seleccionar objetos** para buscar y seleccionar un objeto disponible, basándose en el **Nombre de objeto**especificado.</span><span class="sxs-lookup"><span data-stu-id="2d16d-219">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
3.  <span data-ttu-id="2d16d-220">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d16d-220">When you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2d16d-221">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d16d-221">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="2d16d-222">Para crear una auditoría de servidor</span><span class="sxs-lookup"><span data-stu-id="2d16d-222">To create a server audit</span></span>  
  
1.  <span data-ttu-id="2d16d-223">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d16d-223">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2d16d-224">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2d16d-224">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2d16d-225">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2d16d-225">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a server audit called "HIPAA_Audit" with a binary file as the target and no options.  
    CREATE SERVER AUDIT HIPAA_Audit  
        TO FILE ( FILEPATH ='\\SQLPROD_1\Audit\' );  
    ```  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="2d16d-226">Para crear una especificación de auditoría de servidor</span><span class="sxs-lookup"><span data-stu-id="2d16d-226">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="2d16d-227">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d16d-227">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2d16d-228">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2d16d-228">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2d16d-229">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2d16d-229">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    /*Creates a server audit specification called "HIPAA_Audit_Specification" that audits failed logins for the SQL Server audit "HIPAA_Audit" created above.  
    */  
  
    CREATE SERVER AUDIT SPECIFICATION HIPAA_Audit_Specification  
    FOR SERVER AUDIT HIPAA_Audit  
        ADD (FAILED_LOGIN_GROUP);  
    GO  
    -- Enables the audit.   
  
    ALTER SERVER AUDIT HIPAA_Audit  
    WITH (STATE = ON);  
    GO  
    ```  
  
 <span data-ttu-id="2d16d-230">Para obtener más información, vea [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) y [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2d16d-230">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span></span>  
  
  
