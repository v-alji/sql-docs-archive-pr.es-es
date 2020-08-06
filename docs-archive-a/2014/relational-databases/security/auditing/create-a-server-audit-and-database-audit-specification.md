---
title: Creación de una especificación de auditoría de servidor y de auditoría de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlaudit.dbaudit.general.f1
helpviewer_keywords:
- audits [SQL Server], creating database specification
- database audit [SQL Server]
ms.assetid: 26ee85de-6e97-4318-b526-900924d96e62
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0cad01eae45d534f0f74911ce8f57827858cc920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746217"
---
# <a name="create-a-server-audit-and-database-audit-specification"></a><span data-ttu-id="17439-102">Crear una especificación de auditoría de servidor y de auditoría de base de datos</span><span class="sxs-lookup"><span data-stu-id="17439-102">Create a Server Audit and Database Audit Specification</span></span>
  <span data-ttu-id="17439-103">En este tema se describe cómo crear una especificación de auditoría de servidor y de auditoría de base de datos en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17439-103">This topic describes how to create a server audit and database audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="17439-104">La*auditoría* de una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o de una base de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implica el seguimiento y registro de los eventos que se producen en el sistema.</span><span class="sxs-lookup"><span data-stu-id="17439-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="17439-105">El objeto *SQL Server Audit* recopila una única instancia de acciones y grupos de acciones de nivel de servidor o de base de datos para su supervisión.</span><span class="sxs-lookup"><span data-stu-id="17439-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="17439-106">La auditoría se realiza en el nivel de instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="17439-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="17439-107">Es posible tener varias auditorías por cada instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="17439-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="17439-108">El objeto *Especificación de auditoría de base de datos* pertenece a una auditoría.</span><span class="sxs-lookup"><span data-stu-id="17439-108">The *Database-Level Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="17439-109">Puede crear una única especificación de auditoría de base de datos para cada base de datos de SQL Server y cada auditoría.</span><span class="sxs-lookup"><span data-stu-id="17439-109">You can create one database audit specification per SQL Server database per audit.</span></span> <span data-ttu-id="17439-110">Para obtener más información, vea [SQL Server Audit &#40;motor de base de datos&#41;](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="17439-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="17439-111">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="17439-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="17439-112">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="17439-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="17439-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="17439-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="17439-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="17439-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="17439-115">**Para crear una especificación de auditoría de servidor y de auditoría de base de datos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="17439-115">**To create a server audit and database audit specification, using:**</span></span>  
  
     [<span data-ttu-id="17439-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17439-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="17439-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17439-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="17439-118">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="17439-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="17439-119">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="17439-119">Limitations and Restrictions</span></span>  
 <span data-ttu-id="17439-120">Las especificaciones de auditoría de base de datos son objetos no protegibles que residen en una base de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="17439-120">Database audit specifications are non-securable objects that reside in a given database.</span></span> <span data-ttu-id="17439-121">Cuando se crea una especificación de auditoría de servidor de base de datos, está en un estado deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="17439-121">When a database audit specification is created, it is in a disabled state.</span></span>  
  
 <span data-ttu-id="17439-122">Cuando cree o modifique una especificación de auditoría de base de datos en una base de datos de usuario, no incluya acciones de auditoría en objetos del ámbito de servidor, como las vistas del sistema.</span><span class="sxs-lookup"><span data-stu-id="17439-122">When you are creating or modifying a database audit specification in a user database, do not include audit actions on server-scope objects, such as the system views.</span></span> <span data-ttu-id="17439-123">Si los objetos del ámbito de servidor están incluidos, se creará la auditoría.</span><span class="sxs-lookup"><span data-stu-id="17439-123">If server-scoped objects are included, the audit will be created.</span></span> <span data-ttu-id="17439-124">Sin embargo, los objetos del ámbito de servidor no están incluidos y no se devolverá ningún error.</span><span class="sxs-lookup"><span data-stu-id="17439-124">However, the server-scoped objects will not be included, and no error will be returned.</span></span> <span data-ttu-id="17439-125">Para auditar objetos del ámbito de servidor, utilice una especificación de auditoría de base de datos en la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="17439-125">To audit server-scope objects, use a database audit specification in the master database.</span></span>  
  
 <span data-ttu-id="17439-126">Las especificaciones de auditoría de base de datos residen en la base de datos en la que se crearon, con la excepción de la base de datos del sistema `tempdb`.</span><span class="sxs-lookup"><span data-stu-id="17439-126">Database audit specifications reside in the database where they are created, with the exception of the `tempdb` system database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="17439-127">Seguridad</span><span class="sxs-lookup"><span data-stu-id="17439-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="17439-128">Permisos</span><span class="sxs-lookup"><span data-stu-id="17439-128">Permissions</span></span>  
  
-   <span data-ttu-id="17439-129">Los usuarios con el permiso ALTER ANY DATABASE AUDITpueden crear las especificaciones de auditoría de base de datos y enlazarlas a cualquier auditoría.</span><span class="sxs-lookup"><span data-stu-id="17439-129">Users with the ALTER ANY DATABASE AUDIT permission can create database audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="17439-130">Después de crearse una especificación de auditoría de base de datos, podrá ser vista por las entidades de seguridad que cuenten con los permisos CONTROL SERVER o ALTER ANY DATABASE AUDIT, o por la cuenta sysadmin.</span><span class="sxs-lookup"><span data-stu-id="17439-130">After a database audit specification is created, it can be viewed by principals with the CONTROL SERVER,  ALTER ANY DATABASE AUDIT permissions, or the sysadmin account.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="17439-131">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17439-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="17439-132">Para crear una auditoría de servidor</span><span class="sxs-lookup"><span data-stu-id="17439-132">To create a server audit</span></span>  
  
1.  <span data-ttu-id="17439-133">En el Explorador de objetos, expanda la carpeta **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="17439-133">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="17439-134">Haga clic con el botón secundario en la carpeta **auditorías** y seleccione **nueva auditoría.**... Para obtener más información, vea [crear una auditoría de servidor y una especificación de auditoría de servidor](create-a-server-audit-and-server-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="17439-134">Right-click the **Audits** folder and select **New Audit...**. For more information, see [Create a Server Audit and Server Audit Specification](create-a-server-audit-and-server-audit-specification.md).</span></span>  
  
3.  <span data-ttu-id="17439-135">Cuando termine de seleccionar opciones, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="17439-135">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="17439-136">Para crear una especificación de auditoría de nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="17439-136">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="17439-137">En el Explorador de objetos, expanda la base de datos donde desea crear una especificación de auditoría.</span><span class="sxs-lookup"><span data-stu-id="17439-137">In Object Explorer, expand the database where you want to create an audit specification.</span></span>  
  
2.  <span data-ttu-id="17439-138">Expanda la carpeta **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="17439-138">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="17439-139">Haga clic con el botón secundario en la carpeta **Especificaciones de auditoría de base de datos** y seleccione **nueva especificación de auditoría de base de datos.**</span><span class="sxs-lookup"><span data-stu-id="17439-139">Right-click the **Database Audit Specifications** folder and select **New Database Audit Specification...**.</span></span>  
  
     <span data-ttu-id="17439-140">Las siguientes opciones están disponibles en el cuadro de diálogo **Crear especificación de auditoría de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="17439-140">The following options are available on the **Create Database Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="17439-141">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="17439-141">**Name**</span></span>  
     <span data-ttu-id="17439-142">El nombre de la especificación de auditoría de base de datos.</span><span class="sxs-lookup"><span data-stu-id="17439-142">The name of the database audit specification.</span></span> <span data-ttu-id="17439-143">Se genera automáticamente al crear una nueva especificación de auditoría de servidor, pero se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="17439-143">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="17439-144">**Auditoría**</span><span class="sxs-lookup"><span data-stu-id="17439-144">**Audit**</span></span>  
     <span data-ttu-id="17439-145">El nombre de una auditoría de base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="17439-145">The name of an existing database audit.</span></span> <span data-ttu-id="17439-146">Escriba el nombre de la auditoría o selecciónelo en la lista.</span><span class="sxs-lookup"><span data-stu-id="17439-146">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="17439-147">**Tipo de acción de auditoría**</span><span class="sxs-lookup"><span data-stu-id="17439-147">**Audit Action Type**</span></span>  
     <span data-ttu-id="17439-148">Especifica los grupos de acciones de auditoría y las acciones de auditoría en el nivel de base de datos que se desean capturar.</span><span class="sxs-lookup"><span data-stu-id="17439-148">Specifies the database-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="17439-149">Para obtener la lista de grupos de acciones de auditoría y de acciones de auditoría de nivel de base de datos, así como una descripción de los eventos que contienen, vea [Grupos de acciones y acciones de SQL Server Audit](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="17439-149">For the list of database-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="17439-150">**Esquema de objeto**</span><span class="sxs-lookup"><span data-stu-id="17439-150">**Object Schema**</span></span>  
     <span data-ttu-id="17439-151">Muestra el esquema para el **Nombre de objeto**especificado.</span><span class="sxs-lookup"><span data-stu-id="17439-151">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="17439-152">**Nombre de objeto**</span><span class="sxs-lookup"><span data-stu-id="17439-152">**Object Name**</span></span>  
     <span data-ttu-id="17439-153">Nombre del objeto que se va a auditar.</span><span class="sxs-lookup"><span data-stu-id="17439-153">The name of the object to audit.</span></span> <span data-ttu-id="17439-154">Este valor solo está disponible para las acciones de auditoría, no se aplica a los grupos de auditoría.</span><span class="sxs-lookup"><span data-stu-id="17439-154">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="17439-155">**Puntos suspensivos (...)**</span><span class="sxs-lookup"><span data-stu-id="17439-155">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="17439-156">Abre el cuadro de diálogo **Seleccionar objetos** para buscar y seleccionar un objeto disponible, basándose en el **Tipo de acción de auditoría**especificado.</span><span class="sxs-lookup"><span data-stu-id="17439-156">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="17439-157">**Nombre de la entidad**</span><span class="sxs-lookup"><span data-stu-id="17439-157">**Principal Name**</span></span>  
     <span data-ttu-id="17439-158">La cuenta por la que se va filtrar la auditoría para el objeto que se va a auditar.</span><span class="sxs-lookup"><span data-stu-id="17439-158">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="17439-159">**Puntos suspensivos (...)**</span><span class="sxs-lookup"><span data-stu-id="17439-159">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="17439-160">Abre el cuadro de diálogo **Seleccionar objetos** para buscar y seleccionar un objeto disponible, basándose en el **Nombre de objeto**especificado.</span><span class="sxs-lookup"><span data-stu-id="17439-160">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
4.  <span data-ttu-id="17439-161">Cuando termine de seleccionar opciones, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="17439-161">When you are finished selecting option, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="17439-162">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17439-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="17439-163">Para crear una auditoría de servidor</span><span class="sxs-lookup"><span data-stu-id="17439-163">To create a server audit</span></span>  
  
1.  <span data-ttu-id="17439-164">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17439-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="17439-165">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="17439-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="17439-166">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="17439-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE master ;  
    GO  
    -- Create the server audit.   
    CREATE SERVER AUDIT Payrole_Security_Audit  
        TO FILE ( FILEPATH =   
    'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA' ) ;   
    GO  
    -- Enable the server audit.   
    ALTER SERVER AUDIT Payrole_Security_Audit   
    WITH (STATE = ON) ;  
    ```  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="17439-167">Para crear una especificación de auditoría de nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="17439-167">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="17439-168">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17439-168">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="17439-169">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="17439-169">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="17439-170">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="17439-170">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="17439-171">En el ejemplo se crea una especificación de auditoría de base de datos denominada `Audit_Pay_Tables` que audita las instrucciones SELECT e INSERT por el usuario `dbo` , para la tabla `HumanResources.EmployeePayHistory` basándose en la auditoría de servidor definida anteriormente.</span><span class="sxs-lookup"><span data-stu-id="17439-171">The example creates a database audit specification called `Audit_Pay_Tables` that audits SELECT and INSERT statements by the `dbo` user, for the `HumanResources.EmployeePayHistory` table based on the server audit defined above.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    -- Create the database audit specification.   
    CREATE DATABASE AUDIT SPECIFICATION Audit_Pay_Tables  
    FOR SERVER AUDIT Payrole_Security_Audit  
    ADD (SELECT , INSERT  
         ON HumanResources.EmployeePayHistory BY dbo )   
    WITH (STATE = ON) ;   
    GO  
  
    ```  
  
 <span data-ttu-id="17439-172">Para obtener más información, vea [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) y [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="17439-172">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span></span>  
  
  
