---
title: Editor de la tarea transferir objetos de SQL Server (página objetos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfersqlserverobjects.objects.f1
helpviewer_keywords:
- Transfer SQL Server Objects Task Editor
ms.assetid: 8cc09118-70ac-4013-8308-d87f8411ca0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7038939b02d17b2449a374be51f7f9fa42eae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747096"
---
# <a name="transfer-sql-server-objects-task-editor-objects-page"></a><span data-ttu-id="47f4a-102">Editor de la tarea Transferir objetos de SQL Server (página Objetos)</span><span class="sxs-lookup"><span data-stu-id="47f4a-102">Transfer SQL Server Objects Task Editor (Objects Page)</span></span>
  <span data-ttu-id="47f4a-103">Utilice la página **Objetos** del cuadro de diálogo **Editor de la tarea Transferir objetos de SQL Server** para especificar propiedades para copiar uno o más objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] desde una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a otra.</span><span class="sxs-lookup"><span data-stu-id="47f4a-103">Use the **Objects** page of the **Transfer SQL Server Objects Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="47f4a-104">Las tablas, las vistas, los procedimientos almacenados y las funciones definidas por el usuario son algunos ejemplos de objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que puede copiar.</span><span class="sxs-lookup"><span data-stu-id="47f4a-104">Tables, views, stored procedures, and user-defined functions are a few examples of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects that you can copy.</span></span> <span data-ttu-id="47f4a-105">Para obtener más información acerca de esta tarea, vea [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span><span class="sxs-lookup"><span data-stu-id="47f4a-105">For more information about this task, see [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47f4a-106">El usuario que crea la tarea Transferir objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] debe tener suficientes permisos en los objetos del servidor de origen para seleccionarlos para la copia, además de permiso para tener acceso a la base de datos del servidor de destino donde se transferirán los objetos.</span><span class="sxs-lookup"><span data-stu-id="47f4a-106">The user who creates the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task must have sufficient permissions on the source server objects to select them for copying, and permission to access the destination server database where the objects will be transferred.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="47f4a-107">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="47f4a-107">Static Options</span></span>  
 <span data-ttu-id="47f4a-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="47f4a-108">**SourceConnection**</span></span>  
 <span data-ttu-id="47f4a-109">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una conexión al servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="47f4a-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="47f4a-110">**SourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="47f4a-110">**SourceDatabase**</span></span>  
 <span data-ttu-id="47f4a-111">Seleccione una base de datos en el servidor de origen desde donde se copiarán los objetos.</span><span class="sxs-lookup"><span data-stu-id="47f4a-111">Select a database on the source server from which objects will be copied.</span></span>  
  
 <span data-ttu-id="47f4a-112">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="47f4a-112">**DestinationConnection**</span></span>  
 <span data-ttu-id="47f4a-113">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una conexión al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="47f4a-113">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="47f4a-114">**DestinationDatabase**</span><span class="sxs-lookup"><span data-stu-id="47f4a-114">**DestinationDatabase**</span></span>  
 <span data-ttu-id="47f4a-115">Seleccione una base de datos en el servidor de destino al que se copiarán los objetos.</span><span class="sxs-lookup"><span data-stu-id="47f4a-115">Select a database on the destination server to which objects will be copied.</span></span>  
  
 <span data-ttu-id="47f4a-116">**DropObjectsFirst**</span><span class="sxs-lookup"><span data-stu-id="47f4a-116">**DropObjectsFirst**</span></span>  
 <span data-ttu-id="47f4a-117">Seleccione si los objetos seleccionados se quitarán primero del servidor de destino antes de la copia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-117">Select whether the selected objects will be dropped first on the destination server before copying.</span></span>  
  
 <span data-ttu-id="47f4a-118">**IncludeExtendedProperties**</span><span class="sxs-lookup"><span data-stu-id="47f4a-118">**IncludeExtendedProperties**</span></span>  
 <span data-ttu-id="47f4a-119">Seleccione si las propiedades extendidas se incluirán cuando se copien objetos desde el servidor de origen al de destino.</span><span class="sxs-lookup"><span data-stu-id="47f4a-119">Select whether extended properties will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="47f4a-120">**CopyData**</span><span class="sxs-lookup"><span data-stu-id="47f4a-120">**CopyData**</span></span>  
 <span data-ttu-id="47f4a-121">Seleccione si los datos se incluirán cuando se copien objetos desde el servidor de origen al de destino.</span><span class="sxs-lookup"><span data-stu-id="47f4a-121">Select whether data will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="47f4a-122">**ExistingData**</span><span class="sxs-lookup"><span data-stu-id="47f4a-122">**ExistingData**</span></span>  
 <span data-ttu-id="47f4a-123">Especifique cómo se copiarán los datos al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="47f4a-123">Specify how data will be copied to the destination server.</span></span> <span data-ttu-id="47f4a-124">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="47f4a-124">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="47f4a-125">Value</span><span class="sxs-lookup"><span data-stu-id="47f4a-125">Value</span></span>|<span data-ttu-id="47f4a-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="47f4a-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="47f4a-127">**Sustituya**</span><span class="sxs-lookup"><span data-stu-id="47f4a-127">**Replace**</span></span>|<span data-ttu-id="47f4a-128">Se sobrescribirán los datos del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="47f4a-128">Data on the destination server will be overwritten.</span></span>|  
|<span data-ttu-id="47f4a-129">**Append**</span><span class="sxs-lookup"><span data-stu-id="47f4a-129">**Append**</span></span>|<span data-ttu-id="47f4a-130">Los datos copiados desde el servidor de origen se anexarán a los datos existentes en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="47f4a-130">Data copied from the source server will be appended to existing data on the destination server.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="47f4a-131">La opción **ExistingData** solo está disponible cuando **CopyData** se establece en **True**.</span><span class="sxs-lookup"><span data-stu-id="47f4a-131">The **ExistingData** option is only available when **CopyData** is set to **True**.</span></span>  
  
 <span data-ttu-id="47f4a-132">**CopySchema**</span><span class="sxs-lookup"><span data-stu-id="47f4a-132">**CopySchema**</span></span>  
 <span data-ttu-id="47f4a-133">Seleccione esta opción si el esquema se copia durante la tarea Transferir objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47f4a-133">Select whether the schema is copied during the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47f4a-134">**CopySchema** solo está disponible para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47f4a-134">**CopySchema** is only available for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="47f4a-135">**UseCollation**</span><span class="sxs-lookup"><span data-stu-id="47f4a-135">**UseCollation**</span></span>  
 <span data-ttu-id="47f4a-136">Seleccione esta opción si la transferencia de objetos debe incluir la intercalación especificada en el servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="47f4a-136">Select whether the transfer of objects should include the collation specified on the source server.</span></span>  
  
 <span data-ttu-id="47f4a-137">**IncludeDependentObjects**</span><span class="sxs-lookup"><span data-stu-id="47f4a-137">**IncludeDependentObjects**</span></span>  
 <span data-ttu-id="47f4a-138">Seleccione si la copia de los objetos seleccionados se realizará en cascada para incluir otros objetos que dependen de los objetos seleccionados para la copia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-138">Select whether copying the selected objects will cascade to include other objects that depend on the objects selected for copying.</span></span>  
  
 <span data-ttu-id="47f4a-139">**CopyAllObjects**</span><span class="sxs-lookup"><span data-stu-id="47f4a-139">**CopyAllObjects**</span></span>  
 <span data-ttu-id="47f4a-140">Seleccione si la tarea copiará todos los objetos de la base de datos de origen especificada o solo los objetos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="47f4a-140">Select whether the task will copy all objects in the specified source database or only selected objects.</span></span>  <span data-ttu-id="47f4a-141">Si esta opción se establece en False, puede seleccionar los objetos que se van a transferir y se muestran las opciones dinámicas de la sección **CopyAllObjects**.</span><span class="sxs-lookup"><span data-stu-id="47f4a-141">Setting this option to False gives you the option to select the objects to transfer, and displays the dynamic options in the section, **CopyAllObjects**.</span></span>  
  
 <span data-ttu-id="47f4a-142">**ObjectsToCopy**</span><span class="sxs-lookup"><span data-stu-id="47f4a-142">**ObjectsToCopy**</span></span>  
 <span data-ttu-id="47f4a-143">Expanda **ObjectsToCopy** para especificar los objetos que se deben copiar desde la base de datos de origen a la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="47f4a-143">Expand **ObjectsToCopy** to specify which objects should be copied from the source database to the destination database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47f4a-144">**ObjectsToCopy** solo está disponible cuando **CopyAllObjects** se establece en **False**.</span><span class="sxs-lookup"><span data-stu-id="47f4a-144">**ObjectsToCopy** is only available when **CopyAllObjects** is set to **False**.</span></span>  
  
 <span data-ttu-id="47f4a-145">Las opciones para copiar los siguientes tipos de objetos solo son compatibles con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="47f4a-145">The options to copy the following types of objects are supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="47f4a-146">Ensamblados</span><span class="sxs-lookup"><span data-stu-id="47f4a-146">Assemblies</span></span>  
  
 <span data-ttu-id="47f4a-147">Funciones de partición</span><span class="sxs-lookup"><span data-stu-id="47f4a-147">Partition functions</span></span>  
  
 <span data-ttu-id="47f4a-148">Esquemas de partición</span><span class="sxs-lookup"><span data-stu-id="47f4a-148">Partition schemes</span></span>  
  
 <span data-ttu-id="47f4a-149">Esquemas</span><span class="sxs-lookup"><span data-stu-id="47f4a-149">Schemas</span></span>  
  
 <span data-ttu-id="47f4a-150">Agregados definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="47f4a-150">User-defined aggregates</span></span>  
  
 <span data-ttu-id="47f4a-151">Tipos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="47f4a-151">User-defined types</span></span>  
  
 <span data-ttu-id="47f4a-152">Colecciones de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="47f4a-152">XML schema collections</span></span>  
  
 <span data-ttu-id="47f4a-153">**CopyDatabaseUsers**</span><span class="sxs-lookup"><span data-stu-id="47f4a-153">**CopyDatabaseUsers**</span></span>  
 <span data-ttu-id="47f4a-154">Especifique si los usuarios de la base de datos deben incluirse en la transferencia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-154">Specify whether database users should be included in the transfer.</span></span>  
  
 <span data-ttu-id="47f4a-155">**CopyDatabaseRoles**</span><span class="sxs-lookup"><span data-stu-id="47f4a-155">**CopyDatabaseRoles**</span></span>  
 <span data-ttu-id="47f4a-156">Especifique si los roles de la base de datos deben incluirse en la transferencia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-156">Specify whether database roles should be included in the transfer.</span></span>  
  
 <span data-ttu-id="47f4a-157">**CopySqlServerLogins**</span><span class="sxs-lookup"><span data-stu-id="47f4a-157">**CopySqlServerLogins**</span></span>  
 <span data-ttu-id="47f4a-158">Especifique si los inicios de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] deben incluirse en la transferencia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-158">Specify whether [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins should be included in the transfer.</span></span>  
  
 <span data-ttu-id="47f4a-159">**CopyObjectLevelPermissions**</span><span class="sxs-lookup"><span data-stu-id="47f4a-159">**CopyObjectLevelPermissions**</span></span>  
 <span data-ttu-id="47f4a-160">Especifique si los permisos de objetos deben incluirse en la transferencia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-160">Specify whether object-level permissions should be included in the transfer.</span></span>  
  
 <span data-ttu-id="47f4a-161">**CopyIndexes**</span><span class="sxs-lookup"><span data-stu-id="47f4a-161">**CopyIndexes**</span></span>  
 <span data-ttu-id="47f4a-162">Especifique si los índices deben incluirse en la transferencia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-162">Specify whether indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="47f4a-163">**CopyTriggers**</span><span class="sxs-lookup"><span data-stu-id="47f4a-163">**CopyTriggers**</span></span>  
 <span data-ttu-id="47f4a-164">Especifique si los desencadenadores deben incluirse en la transferencia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-164">Specify whether triggers should be included in the transfer.</span></span>  
  
 <span data-ttu-id="47f4a-165">**CopyFullTextIndexes**</span><span class="sxs-lookup"><span data-stu-id="47f4a-165">**CopyFullTextIndexes**</span></span>  
 <span data-ttu-id="47f4a-166">Especifique si los índices de texto completo deben incluirse en la transferencia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-166">Specify whether full-text indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="47f4a-167">**CopyPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="47f4a-167">**CopyPrimaryKeys**</span></span>  
 <span data-ttu-id="47f4a-168">Especifique si las claves principales deben incluirse en la transferencia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-168">Specify whether primary keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="47f4a-169">**CopyForeignKeys**</span><span class="sxs-lookup"><span data-stu-id="47f4a-169">**CopyForeignKeys**</span></span>  
 <span data-ttu-id="47f4a-170">Especifique si las claves externas deben incluirse en la transferencia.</span><span class="sxs-lookup"><span data-stu-id="47f4a-170">Specify whether foreign keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="47f4a-171">**GenerateScriptsInUnicode**</span><span class="sxs-lookup"><span data-stu-id="47f4a-171">**GenerateScriptsInUnicode**</span></span>  
 <span data-ttu-id="47f4a-172">Especifique si los scripts de transferencia generados están en formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="47f4a-172">Specify whether the generated transfer scripts are in Unicode format.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="47f4a-173">Opciones dinámicas</span><span class="sxs-lookup"><span data-stu-id="47f4a-173">Dynamic Options</span></span>  
  
### <a name="copyallobjects--false"></a><span data-ttu-id="47f4a-174">CopyAllObjects = False</span><span class="sxs-lookup"><span data-stu-id="47f4a-174">CopyAllObjects = False</span></span>  
 <span data-ttu-id="47f4a-175">**CopyAllTables**</span><span class="sxs-lookup"><span data-stu-id="47f4a-175">**CopyAllTables**</span></span>  
 <span data-ttu-id="47f4a-176">Seleccione si la tarea copiará todas las tablas de la base de datos de origen especificada o solo las tablas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="47f4a-176">Select whether the task will copy all tables in the specified source database or only the selected tables.</span></span>  
  
 <span data-ttu-id="47f4a-177">**TablesList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-177">**TablesList**</span></span>  
 <span data-ttu-id="47f4a-178">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar tablas** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-178">Click to open the **Select Tables** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-179">**CopyAllViews**</span><span class="sxs-lookup"><span data-stu-id="47f4a-179">**CopyAllViews**</span></span>  
 <span data-ttu-id="47f4a-180">Seleccione si la tarea copiará todas las vistas de la base de datos de origen especificada o solo las vistas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="47f4a-180">Select whether the task will copy all views in the specified source database or only the selected views.</span></span>  
  
 <span data-ttu-id="47f4a-181">**ViewsList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-181">**ViewsList**</span></span>  
 <span data-ttu-id="47f4a-182">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar vistas** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-182">Click to open the **Select Views** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-183">**CopyAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="47f4a-183">**CopyAllStoredProcedures**</span></span>  
 <span data-ttu-id="47f4a-184">Seleccione si la tarea copiará todos los procedimientos almacenados definidos por el usuario en la base de datos de origen especificada o solo los procedimientos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="47f4a-184">Select whether the task will copy all user-defined stored procedures in the specified source database or only the selected procedures.</span></span>  
  
 <span data-ttu-id="47f4a-185">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-185">**StoredProceduresList**</span></span>  
 <span data-ttu-id="47f4a-186">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar procedimientos almacenados** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-186">Click to open the **Select Stored Procedures** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-187">**CopyAllUserDefinedFunctions**</span><span class="sxs-lookup"><span data-stu-id="47f4a-187">**CopyAllUserDefinedFunctions**</span></span>  
 <span data-ttu-id="47f4a-188">Seleccione si la tarea copiará todas las funciones definidas por el usuario en la base de datos de origen especificada o solo las UDF seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="47f4a-188">Select whether the task will copy all user-defined functions in the specified source database or only the selected UDFs.</span></span>  
  
 <span data-ttu-id="47f4a-189">**UserDefinedFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-189">**UserDefinedFunctionsList**</span></span>  
 <span data-ttu-id="47f4a-190">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar funciones definidas por el usuario** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-190">Click to open the **Select User Defined Functions** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-191">**CopyAllDefaults**</span><span class="sxs-lookup"><span data-stu-id="47f4a-191">**CopyAllDefaults**</span></span>  
 <span data-ttu-id="47f4a-192">Seleccione si la tarea copiará todos los valores predeterminados de la base de datos de origen especificada o solo los valores predeterminados seleccionados.</span><span class="sxs-lookup"><span data-stu-id="47f4a-192">Select whether the task will copy all defaults in the specified source database or only the selected defaults.</span></span>  
  
 <span data-ttu-id="47f4a-193">**DefaultsList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-193">**DefaultsList**</span></span>  
 <span data-ttu-id="47f4a-194">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar valores predeterminados** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-194">Click to open the **Select Defaults** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-195">**CopyAllUserDefinedDataTypes**</span><span class="sxs-lookup"><span data-stu-id="47f4a-195">**CopyAllUserDefinedDataTypes**</span></span>  
 <span data-ttu-id="47f4a-196">Seleccione si la tarea copiará todos los tipos de datos definidos por el usuario en la base de datos de origen especificada o solo los tipos de datos definidos por el usuario seleccionados.</span><span class="sxs-lookup"><span data-stu-id="47f4a-196">Select whether the task will copy all user-defined data types in the specified source database or only the selected user-defined data types.</span></span>  
  
 <span data-ttu-id="47f4a-197">**UserDefinedDataTypesList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-197">**UserDefinedDataTypesList**</span></span>  
 <span data-ttu-id="47f4a-198">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar tipos de datos definidos por el usuario** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-198">Click to open the **Select User-Defined Data Types** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-199">**CopyAllPartitionFunctions**</span><span class="sxs-lookup"><span data-stu-id="47f4a-199">**CopyAllPartitionFunctions**</span></span>  
 <span data-ttu-id="47f4a-200">Seleccione si la tarea copiará todas las funciones de partición definidas por el usuario en la base de datos de origen especificada o solo las seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="47f4a-200">Select whether the task will copy all user-defined partition functions in the specified source database or only the selected partition functions.</span></span> <span data-ttu-id="47f4a-201">Esta opción solo es compatible con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47f4a-201">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="47f4a-202">**PartitionFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-202">**PartitionFunctionsList**</span></span>  
 <span data-ttu-id="47f4a-203">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar funciones de partición** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-203">Click to open the **Select Partition Functions** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-204">**CopyAllPartitionSchemes**</span><span class="sxs-lookup"><span data-stu-id="47f4a-204">**CopyAllPartitionSchemes**</span></span>  
 <span data-ttu-id="47f4a-205">Seleccione si la tarea copiará todos los esquemas de partición de la base de datos de origen especificada o solo los seleccionados.</span><span class="sxs-lookup"><span data-stu-id="47f4a-205">Select whether the task will copy all partition schemes in the specified source database or only the selected partition schemes.</span></span> <span data-ttu-id="47f4a-206">Esta opción solo es compatible con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47f4a-206">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="47f4a-207">**PartitionSchemesList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-207">**PartitionSchemesList**</span></span>  
 <span data-ttu-id="47f4a-208">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar esquemas de partición** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-208">Click to open the **Select Partition Schemes** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-209">**CopyAllSchemas**</span><span class="sxs-lookup"><span data-stu-id="47f4a-209">**CopyAllSchemas**</span></span>  
 <span data-ttu-id="47f4a-210">Seleccione si la tarea copiará todos los esquemas de la base de datos de origen especificada o solo los seleccionados.</span><span class="sxs-lookup"><span data-stu-id="47f4a-210">Select whether the task will copy all schemas in the specified source database or only the selected schemas.</span></span> <span data-ttu-id="47f4a-211">Esta opción solo es compatible con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47f4a-211">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="47f4a-212">**SchemasList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-212">**SchemasList**</span></span>  
 <span data-ttu-id="47f4a-213">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar esquemas** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-213">Click to open the **Select Schemas** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-214">**CopyAllSqlAssemblies**</span><span class="sxs-lookup"><span data-stu-id="47f4a-214">**CopyAllSqlAssemblies**</span></span>  
 <span data-ttu-id="47f4a-215">Seleccione si la tarea copiará todos los ensamblados de SQL de la base de datos de origen especificada o solo los seleccionados.</span><span class="sxs-lookup"><span data-stu-id="47f4a-215">Select whether the task will copy all SQL assemblies in the specified source database or only the selected SQL assemblies.</span></span> <span data-ttu-id="47f4a-216">Esta opción solo es compatible con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47f4a-216">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="47f4a-217">**SqlAssembliesList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-217">**SqlAssembliesList**</span></span>  
 <span data-ttu-id="47f4a-218">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar ensamblados de SQL** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-218">Click to open the **Select SQL Assemblies** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-219">**CopyAllUserDefinedAggregates**</span><span class="sxs-lookup"><span data-stu-id="47f4a-219">**CopyAllUserDefinedAggregates**</span></span>  
 <span data-ttu-id="47f4a-220">Seleccione si la tarea copiará todas las funciones de agregado definidas por el usuario en la base de datos de origen especificada o solo las seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="47f4a-220">Select whether the task will copy all user-defined aggregates in the specified source database or only the selected user-defined aggregates.</span></span> <span data-ttu-id="47f4a-221">Esta opción solo es compatible con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47f4a-221">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="47f4a-222">**UserDefinedAggregatesList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-222">**UserDefinedAggregatesList**</span></span>  
 <span data-ttu-id="47f4a-223">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar agregados definidos por el usuario** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-223">Click to open the **Select User-Defined Aggregates** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-224">**CopyAllUserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="47f4a-224">**CopyAllUserDefinedTypes**</span></span>  
 <span data-ttu-id="47f4a-225">Seleccione si la tarea copiará todos los tipos definidos por el usuario en la base de datos de origen especificada o solo los seleccionados.</span><span class="sxs-lookup"><span data-stu-id="47f4a-225">Select whether the task will copy all user-defined types in the specified source database or only the selected UDTs.</span></span> <span data-ttu-id="47f4a-226">Esta opción solo es compatible con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47f4a-226">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="47f4a-227">**UserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="47f4a-227">**UserDefinedTypes**</span></span>  
 <span data-ttu-id="47f4a-228">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar tipos definidos por el usuario** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-228">Click to open the **Select User-Defined Types** dialog box.</span></span>  
  
 <span data-ttu-id="47f4a-229">**CopyAllXmlSchemaCollections**</span><span class="sxs-lookup"><span data-stu-id="47f4a-229">**CopyAllXmlSchemaCollections**</span></span>  
 <span data-ttu-id="47f4a-230">Seleccione si la tarea copiará todas las colecciones de esquemas XML de la base de datos de origen especificada o solo las seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="47f4a-230">Select whether the task will copy all XML Schema collections in the specified source database or only the selected XML schema collections.</span></span> <span data-ttu-id="47f4a-231">Esta opción solo es compatible con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47f4a-231">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="47f4a-232">**XmlSchemaCollectionsList**</span><span class="sxs-lookup"><span data-stu-id="47f4a-232">**XmlSchemaCollectionsList**</span></span>  
 <span data-ttu-id="47f4a-233">Haga clic en esta opción para abrir el cuadro de diálogo **Seleccionar colecciones de esquemas XML** .</span><span class="sxs-lookup"><span data-stu-id="47f4a-233">Click to open the **Select XML Schema Collections** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f4a-234">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47f4a-234">See Also</span></span>  
 <span data-ttu-id="47f4a-235">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="47f4a-235">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="47f4a-236">[Tareas de Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="47f4a-236">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="47f4a-237">[Editor de la tarea Transferir objetos de SQL Server &#40;página General&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="47f4a-237">[Transfer SQL Server Objects Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="47f4a-238">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="47f4a-238">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="47f4a-239">[Formatos de datos para importación en bloque o exportación masiva &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="47f4a-239">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 [<span data-ttu-id="47f4a-240">Consideraciones de seguridad para una instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="47f4a-240">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
