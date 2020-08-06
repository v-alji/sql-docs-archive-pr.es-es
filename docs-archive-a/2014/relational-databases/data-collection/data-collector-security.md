---
title: Seguridad del recopilador de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
- security [data collector]
- data collector [SQL Server], security
ms.assetid: e75d6975-641e-440a-a642-cb39a583359a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c89f1658f6ae1b5bd79de96f20222b0b19529df2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669703"
---
# <a name="data-collector-security"></a><span data-ttu-id="15c36-102">Seguridad del recopilador de datos</span><span class="sxs-lookup"><span data-stu-id="15c36-102">Data Collector Security</span></span>
  <span data-ttu-id="15c36-103">El recopilador de datos utiliza el modelo de seguridad basada en roles implementado por el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c36-103">The data collector uses the role-based security model implemented by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="15c36-104">Este modelo permite al administrador de bases de datos ejecutar las distintas tareas de recopilador de datos en un contexto de seguridad que solo tiene los permisos necesarios realizar dicha tarea.</span><span class="sxs-lookup"><span data-stu-id="15c36-104">This model lets the database administrator run the various data collector tasks in a security context that has only the permissions required to perform that task.</span></span> <span data-ttu-id="15c36-105">Este enfoque también se utiliza para operaciones que implican tablas internas, a las que solamente se puede tener acceso utilizando un procedimiento almacenado o vista.</span><span class="sxs-lookup"><span data-stu-id="15c36-105">This approach is also used for operations involving internal tables, which can only be accessed by using a stored procedure or view.</span></span> <span data-ttu-id="15c36-106">No se concede ningún permiso a las tablas internas.</span><span class="sxs-lookup"><span data-stu-id="15c36-106">No permissions are granted to internal tables.</span></span> <span data-ttu-id="15c36-107">En lugar de ello, los permisos se comprueban en el usuario del procedimiento almacenado o vista que se utiliza para tener acceso a una tabla.</span><span class="sxs-lookup"><span data-stu-id="15c36-107">Instead, permissions are checked on the user of the stored procedure or view that is used to access a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15c36-108">Otro aspecto clave de este modelo de seguridad son los permisos concéntricos.</span><span class="sxs-lookup"><span data-stu-id="15c36-108">Another key aspect of this security model is concentric permissions.</span></span> <span data-ttu-id="15c36-109">Con los permisos concéntricos, los roles con más privilegios heredan los permisos de los roles con menos privilegios sobre los objetos (incluidos alertas, operadores, trabajos, programaciones y servidores proxy).</span><span class="sxs-lookup"><span data-stu-id="15c36-109">Under concentric permissions, more privileged roles inherit the permissions of less privileged roles on objects (including alerts, operators, jobs, schedules, and proxies).</span></span> <span data-ttu-id="15c36-110">Para más información, consulte [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="15c36-110">For more information, see [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="15c36-111">En las secciones siguientes se describe la seguridad de la recopilación de datos en general, así como los roles que debe conceder a los usuarios para que puedan configurar y utilizar el recopilador de datos y llevar a cabo tareas asociadas al almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-111">The following sections describe data collection security in general, as well as the roles you must grant to users so they can configure and use the data collector, and carry out tasks associated with the management data warehouse.</span></span>  
  
## <a name="general-security"></a><span data-ttu-id="15c36-112">Seguridad general</span><span class="sxs-lookup"><span data-stu-id="15c36-112">General Security</span></span>  
 <span data-ttu-id="15c36-113">El recopilador de datos se instala según los estándares especificados para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15c36-113">The data collector is installed according to the documented standards specified for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
### <a name="network-security"></a><span data-ttu-id="15c36-114">Seguridad de redes</span><span class="sxs-lookup"><span data-stu-id="15c36-114">Network Security</span></span>  
 <span data-ttu-id="15c36-115">Se puede pasar información confidencial entre las instancias de destino, la instancia relacional asociada al servidor de configuración, los conjuntos de recopilación que se están ejecutando y el servidor que hospeda el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-115">Sensitive information can be passed between target instances, the relational instance associated with the configuration server, the collection sets that are running, and the server that hosts the management data warehouse.</span></span>  
  
 <span data-ttu-id="15c36-116">Para proteger los datos que se transfieren a través de una red, se implementan mecanismos de seguridad estándar, como el cifrado de protocolos para [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15c36-116">To protect any data that is transferred over a network, the standard security mechanisms are implemented, such as protocol encryption for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-data-collector"></a><span data-ttu-id="15c36-117">Permisos para configurar y utilizar el recopilador de datos</span><span class="sxs-lookup"><span data-stu-id="15c36-117">Permissions for Configuring and Using the Data Collector</span></span>  
 <span data-ttu-id="15c36-118">En función de la tarea, los usuarios deben ser miembros de uno o varios de los roles fijos de base de datos que se proporcionan para el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-118">Depending on the task, users must be members of one or more of the fixed database roles provided for the data collector.</span></span> <span data-ttu-id="15c36-119">En orden de acceso con más privilegios a acceso con menos privilegios, los roles son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="15c36-119">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   `dc_admin`  
  
-   <span data-ttu-id="15c36-120">**dc_operator**</span><span class="sxs-lookup"><span data-stu-id="15c36-120">**dc_operator**</span></span>  
  
-   <span data-ttu-id="15c36-121">**dc_proxy**</span><span class="sxs-lookup"><span data-stu-id="15c36-121">**dc_proxy**</span></span>  
  
 <span data-ttu-id="15c36-122">Estos roles se almacenan en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="15c36-122">These roles are stored in the msdb database.</span></span> <span data-ttu-id="15c36-123">De manera predeterminada, ningún usuario es miembro de estos roles de base de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-123">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="15c36-124">La pertenencia de los usuarios a estos roles se debe conceder explícitamente.</span><span class="sxs-lookup"><span data-stu-id="15c36-124">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="15c36-125">Los usuarios que son miembros del `sysadmin` rol fijo de servidor tienen acceso total a los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objetos del agente y a las vistas del recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-125">Users who are members of the `sysadmin` fixed server role have full access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent objects and data collector views.</span></span> <span data-ttu-id="15c36-126">No obstante, deben agregarse explícitamente a los roles del recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-126">However, they need to be explicitly added to data collector roles.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15c36-127">Los miembros del rol db_ssisadmin y del rol dc_admin quizá puedan elevar sus privilegios a sysadmin.</span><span class="sxs-lookup"><span data-stu-id="15c36-127">Members of the db_ssisadmin role and the dc_admin role may be able to elevate their privileges to sysadmin.</span></span> <span data-ttu-id="15c36-128">Esta elevación de privilegio se puede producir porque estos roles pueden modificar los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] y los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] los puede ejecutar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando el contexto de seguridad de sysadmin del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c36-128">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the sysadmin security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="15c36-129">Para protegerse contra esta elevación de privilegio al ejecutar planes de mantenimiento, conjuntos de recopilación de datos y otros paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , configure los trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que ejecutan paquetes para utilizar una cuenta de proxy con privilegios limitados o agregar solo los miembros de sysadmin a los roles dc_admin y db_ssisadmin.</span><span class="sxs-lookup"><span data-stu-id="15c36-129">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add sysadmin members to the db_ssisadmin and dc_admin roles.</span></span>  
  
### <a name="dc_admin-role"></a><span data-ttu-id="15c36-130">Rol dc_admin</span><span class="sxs-lookup"><span data-stu-id="15c36-130">dc_admin Role</span></span>  
 <span data-ttu-id="15c36-131">Los usuarios asignados al `dc_admin` rol tienen acceso de administrador completo (crear, leer, actualizar y eliminar) a la configuración del recopilador de datos en una instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="15c36-131">Users assigned to the `dc_admin` role have full administrator access (Create, Read, Update, and Delete) to the data collector configuration on a server instance.</span></span> <span data-ttu-id="15c36-132">Los miembros de este rol pueden realizar las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="15c36-132">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="15c36-133">Establecer propiedades de nivel del recopilador.</span><span class="sxs-lookup"><span data-stu-id="15c36-133">Set collector-level properties.</span></span>  
  
-   <span data-ttu-id="15c36-134">Agregar nuevos conjuntos de recopilación.</span><span class="sxs-lookup"><span data-stu-id="15c36-134">Add new collection sets.</span></span>  
  
-   <span data-ttu-id="15c36-135">Instalar nuevos tipos de recopilación.</span><span class="sxs-lookup"><span data-stu-id="15c36-135">Install new collection types.</span></span>  
  
-   <span data-ttu-id="15c36-136">Realizar todas las operaciones permitidas al rol **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="15c36-136">Perform all the operations permitted to the **dc_operator** role.</span></span>  
  
 <span data-ttu-id="15c36-137">El `dc_admin` rol es un miembro de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="15c36-137">The `dc_admin` role is a member of the following roles:</span></span>  
  
-   <span data-ttu-id="15c36-138">**SQLAgentUserRole**.</span><span class="sxs-lookup"><span data-stu-id="15c36-138">**SQLAgentUserRole**.</span></span> <span data-ttu-id="15c36-139">Este rol es necesario para crear programaciones y ejecutar trabajos.</span><span class="sxs-lookup"><span data-stu-id="15c36-139">This role is required to create schedules and run jobs.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15c36-140">Los servidores proxy creados para el recopilador de datos deben conceder acceso a `dc_admin` para crearlos y usarlos en los pasos de trabajo que requieran un proxy.</span><span class="sxs-lookup"><span data-stu-id="15c36-140">Proxies created for the data collector must grant access to `dc_admin` to create them and use them in any job steps that require a proxy.</span></span>  
  
-   <span data-ttu-id="15c36-141">**dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="15c36-141">**dc_operator**.</span></span> <span data-ttu-id="15c36-142">Los miembros de `dc_admin` heredan los permisos concedidos a **dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="15c36-142">Members of `dc_admin` inherit the permissions given to **dc_operator**.</span></span>  
  
### <a name="dc_operator-role"></a><span data-ttu-id="15c36-143">Rol dc_operator</span><span class="sxs-lookup"><span data-stu-id="15c36-143">dc_operator Role</span></span>  
 <span data-ttu-id="15c36-144">Los miembros del rol **dc_operator** tienen acceso de lectura y actualización.</span><span class="sxs-lookup"><span data-stu-id="15c36-144">Members of the **dc_operator** role have Read and Update access.</span></span> <span data-ttu-id="15c36-145">Este rol admite tareas de operaciones relacionadas con la ejecución y configuración de conjuntos de recopilación.</span><span class="sxs-lookup"><span data-stu-id="15c36-145">This role supports operations tasks related to running and configuring collection sets.</span></span> <span data-ttu-id="15c36-146">Los miembros de este rol pueden realizar las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="15c36-146">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="15c36-147">Iniciar o detener un conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="15c36-147">Start or stop a collection set.</span></span>  
  
-   <span data-ttu-id="15c36-148">Enumerar conjuntos de recopilación existentes.</span><span class="sxs-lookup"><span data-stu-id="15c36-148">Enumerate existing collection sets.</span></span>  
  
-   <span data-ttu-id="15c36-149">Ver la información detallada (por ejemplo, elementos de recopilación y frecuencia de recopilación) asociada a un conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="15c36-149">View the detailed information (for example, collection items, and collection frequency) associated with a collection set.</span></span>  
  
-   <span data-ttu-id="15c36-150">Cambiar la frecuencia de la carga para los conjuntos de recopilación existentes.</span><span class="sxs-lookup"><span data-stu-id="15c36-150">Change the upload frequency for existing collection sets.</span></span>  
  
-   <span data-ttu-id="15c36-151">Cambiar la frecuencia de recopilación de los elementos de recopilación que forman parte de un conjunto de recopilación existente.</span><span class="sxs-lookup"><span data-stu-id="15c36-151">Change the collection frequency for collection items that are part of an existing collection set.</span></span>  
  
 <span data-ttu-id="15c36-152">El rol **dc_operator** es miembro de los roles siguientes que son necesarios para enumerar y ver paquetes del recopilador de datos:</span><span class="sxs-lookup"><span data-stu-id="15c36-152">The **dc_operator** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="15c36-153">**db_ssisltduser**</span><span class="sxs-lookup"><span data-stu-id="15c36-153">**db_ssisltduser**</span></span>  
  
-   <span data-ttu-id="15c36-154">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="15c36-154">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="15c36-155">Para obtener más información, vea [Roles de Integration Services &#40;servicio SSIS&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="15c36-155">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
### <a name="dc_proxy-role"></a><span data-ttu-id="15c36-156">Rol dc_proxy</span><span class="sxs-lookup"><span data-stu-id="15c36-156">dc_proxy Role</span></span>  
 <span data-ttu-id="15c36-157">Los miembros del rol **dc_proxy** tienen acceso de lectura a los conjuntos de recopilación y a las propiedades de nivel de recopilador.</span><span class="sxs-lookup"><span data-stu-id="15c36-157">Members of the **dc_proxy** role have Read access to data collector collection sets and collector-level properties.</span></span> <span data-ttu-id="15c36-158">Los miembros de este rol también pueden ejecutar los trabajos que les pertenecen, así como crear pasos de trabajos que se ejecuten como una cuenta de proxy existente.</span><span class="sxs-lookup"><span data-stu-id="15c36-158">Members of this role can also execute jobs that they own and create job steps that run as an existing proxy account.</span></span>  
  
 <span data-ttu-id="15c36-159">Los miembros de este rol pueden realizar las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="15c36-159">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="15c36-160">Ver la información de configuración de conjuntos de recopilación (por ejemplo, parámetros de entrada para los elementos de recopilación, y la frecuencia de recopilación de estos elementos).</span><span class="sxs-lookup"><span data-stu-id="15c36-160">View collection set configuration information (for example, input parameters for collection items, and the collection frequency for these items).</span></span>  
  
-   <span data-ttu-id="15c36-161">Obtener información cifrada interna a la que solo se puede tener acceso por un procedimiento almacenado firmado (por ejemplo, información de conexión de almacenamiento de datos utilizada para las cargas de datos).</span><span class="sxs-lookup"><span data-stu-id="15c36-161">Obtain internal encrypted information that can only be accessed by a signed stored procedure (for example, data warehouse connection information used for data uploads).</span></span>  
  
-   <span data-ttu-id="15c36-162">Registrar eventos en tiempo de ejecución de los conjuntos de recopilación.</span><span class="sxs-lookup"><span data-stu-id="15c36-162">Log collection-set run-time events.</span></span>  
  
 <span data-ttu-id="15c36-163">El rol **dc_proxy** es miembro de los roles siguientes que son necesarios para enumerar y ver paquetes del recopilador de datos:</span><span class="sxs-lookup"><span data-stu-id="15c36-163">The **dc_proxy** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="15c36-164">**db_ssisltduser**.</span><span class="sxs-lookup"><span data-stu-id="15c36-164">**db_ssisltduser**.</span></span>  
  
-   <span data-ttu-id="15c36-165">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="15c36-165">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="15c36-166">Para obtener más información, vea [Roles de Integration Services &#40;servicio SSIS&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="15c36-166">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-management-data-warehouse"></a><span data-ttu-id="15c36-167">Permisos para configurar y utilizar el almacén de administración de datos</span><span class="sxs-lookup"><span data-stu-id="15c36-167">Permissions for Configuring and Using the Management Data Warehouse</span></span>  
 <span data-ttu-id="15c36-168">En función de la tarea, los usuarios deben ser miembros de uno o varios de los roles fijos de base de datos que se proporcionan para tener acceso al almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-168">Depending on the task, users must be members of one or more of the fixed database roles provided for accessing the management data warehouse.</span></span> <span data-ttu-id="15c36-169">En orden de acceso con más privilegios a acceso con menos privilegios, los roles son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="15c36-169">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   <span data-ttu-id="15c36-170">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="15c36-170">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="15c36-171">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="15c36-171">**mdw_writer**</span></span>  
  
-   <span data-ttu-id="15c36-172">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="15c36-172">**mdw_reader**</span></span>  
  
 <span data-ttu-id="15c36-173">Estos roles se almacenan en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="15c36-173">These roles are stored in the msdb database.</span></span> <span data-ttu-id="15c36-174">De manera predeterminada, ningún usuario es miembro de estos roles de base de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-174">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="15c36-175">La pertenencia de los usuarios a estos roles se debe conceder explícitamente.</span><span class="sxs-lookup"><span data-stu-id="15c36-175">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="15c36-176">Los usuarios que son miembros del `sysadmin` rol fijo de servidor tienen acceso total a las vistas del recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-176">Users who are members of the `sysadmin` fixed server role have full access to data collector views.</span></span> <span data-ttu-id="15c36-177">No obstante, deben agregarse explícitamente a los roles de la base de datos para realizar otras operaciones.</span><span class="sxs-lookup"><span data-stu-id="15c36-177">However, they need to be explicitly added to database roles to perform other operations.</span></span>  
  
### <a name="mdw_admin-role"></a><span data-ttu-id="15c36-178">Rol mdw_admin</span><span class="sxs-lookup"><span data-stu-id="15c36-178">mdw_admin Role</span></span>  
 <span data-ttu-id="15c36-179">Los miembros del rol **mdw_admin** tienen acceso de lectura, escritura, actualización y eliminación al almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-179">Members of the **mdw_admin** role have Read, Write, Update, and Delete access to the management data warehouse.</span></span>  
  
 <span data-ttu-id="15c36-180">Los miembros de este rol pueden realizar las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="15c36-180">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="15c36-181">Cambiar el esquema del almacén de administración de datos cuando se requiere (por ejemplo, agregando una nueva tabla cuando se instala un nuevo tipo de recopilador).</span><span class="sxs-lookup"><span data-stu-id="15c36-181">Change the management data warehouse schema when required (for example, adding a new table when a new collection type is installed).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15c36-182">Cuando hay un cambio de esquema, el usuario también debe ser miembro del `dc_admin` rol para instalar un nuevo tipo de recopilador, puesto que esta acción requiere permiso para actualizar la configuración del recopilador de datos en msdb.</span><span class="sxs-lookup"><span data-stu-id="15c36-182">Where there is a schema change, the user must also be a member of the `dc_admin` role to install a new collector type, since this action requires permission to update the data collector configuration in msdb.</span></span>  
  
-   <span data-ttu-id="15c36-183">Ejecutar trabajos de mantenimiento en el almacén de administración de datos, por ejemplo archivado o limpieza.</span><span class="sxs-lookup"><span data-stu-id="15c36-183">Run maintenance jobs on the management data warehouse, such as archive or cleanup.</span></span>  
  
### <a name="mdw_writer-role"></a><span data-ttu-id="15c36-184">Rol mdw_writer</span><span class="sxs-lookup"><span data-stu-id="15c36-184">mdw_writer Role</span></span>  
 <span data-ttu-id="15c36-185">Los miembros del rol **mdw_writer** pueden cargar y escribir datos en el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-185">Members of the **mdw_writer** role can upload and write data to the management data warehouse.</span></span> <span data-ttu-id="15c36-186">Cualquier recopilador de datos que almacene datos en el almacén de administración de datos tiene que ser miembro de este rol.</span><span class="sxs-lookup"><span data-stu-id="15c36-186">Any data collector that stores data in the management data warehouse has to be a member of this role.</span></span>  
  
### <a name="mdw_reader-role"></a><span data-ttu-id="15c36-187">Rol mdw_reader</span><span class="sxs-lookup"><span data-stu-id="15c36-187">mdw_reader Role</span></span>  
 <span data-ttu-id="15c36-188">Los miembros del rol **mdw_reader** tienen acceso de lectura al almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-188">Members of the **mdw_reader** role have Read access to the management data warehouse.</span></span> <span data-ttu-id="15c36-189">Dado que la finalidad de este rol es permitir solucionar problemas proporcionando acceso a datos históricos, los miembros de este rol no pueden ver otros elementos del esquema de almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="15c36-189">Because the purpose of this role is to support troubleshooting by providing access to historical data, members of this role cannot view other elements of the management data warehouse schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c36-190">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15c36-190">See Also</span></span>  
 [<span data-ttu-id="15c36-191">Implementar la seguridad del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="15c36-191">Implement SQL Server Agent Security</span></span>](../../ssms/agent/implement-sql-server-agent-security.md)  
  
  
