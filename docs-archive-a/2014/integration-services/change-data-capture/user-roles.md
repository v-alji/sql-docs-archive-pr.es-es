---
title: Roles de usuario para Change Data Capture Service para Oracle de Attunity | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: be0ec384-e03b-4483-96ca-02b289804d6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e694da0cfd8645fe594b049b6dc2394b55d1bb55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747710"
---
# <a name="user-roles-for-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="49010-102">Roles de usuario para el Servicio de captura de datos modificados para Oracle de Attunity</span><span class="sxs-lookup"><span data-stu-id="49010-102">User Roles for Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="49010-103">En esta sección se describen los roles de usuario para el Servicio de captura de datos modificados para Oracle de Attunity.</span><span class="sxs-lookup"><span data-stu-id="49010-103">This section describes the user roles for the Change Data Capture Service for Oracle by Attunity.</span></span> <span data-ttu-id="49010-104">Los roles descritos son roles de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , roles de Windows o roles de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-104">The roles described are [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database roles, Windows roles, or Oracle database roles.</span></span>  
  
## <a name="windows-user-roles"></a><span data-ttu-id="49010-105">Roles de usuario de Windows</span><span class="sxs-lookup"><span data-stu-id="49010-105">Windows User Roles</span></span>  
 <span data-ttu-id="49010-106">A continuación se describen los roles de usuario de Windows que el servicio CDC de Oracle emplea.</span><span class="sxs-lookup"><span data-stu-id="49010-106">The following describes the Windows user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="computer-administrator-oracle-cdc-service"></a><span data-ttu-id="49010-107">Administrador del equipo: Servicio CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="49010-107">Computer Administrator: Oracle CDC Service</span></span>  
 <span data-ttu-id="49010-108">El administrador del equipo es un usuario de Windows responsable de crear y mantener el servicio CDC en el equipo.</span><span class="sxs-lookup"><span data-stu-id="49010-108">The computer administrator is a Windows user responsible for creating and maintaining the CDC Service on the computer.</span></span> <span data-ttu-id="49010-109">Este usuario debe pertenecer al grupo Administradores del equipo local.</span><span class="sxs-lookup"><span data-stu-id="49010-109">This user must belong to the group of local machine administrators.</span></span>  
  
 <span data-ttu-id="49010-110">Entre las tareas realizadas por el administrador del equipo del servicio CDC de Oracle se incluyen:</span><span class="sxs-lookup"><span data-stu-id="49010-110">The tasks performed by the Oracle CDC Service Computer Administrator include:</span></span>  
  
-   <span data-ttu-id="49010-111">Instalar el software del servicio CDC para Oracle</span><span class="sxs-lookup"><span data-stu-id="49010-111">Installing the CDC Service for Oracle software</span></span>  
  
-   <span data-ttu-id="49010-112">Crear un servicio de Windows CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="49010-112">Creating an Oracle CDC Windows service</span></span>  
  
-   <span data-ttu-id="49010-113">Configurar la conexión del servicio CDC con la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino (cadena de conexión y credenciales)</span><span class="sxs-lookup"><span data-stu-id="49010-113">Setting up the CDC Service connection to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (connection string and credentials)</span></span>  
  
-   <span data-ttu-id="49010-114">Asegurarse de que la contraseña maestra del servicio CDC con las credenciales de minería de registros de Oracle está protegida</span><span class="sxs-lookup"><span data-stu-id="49010-114">Ensuring that the CDC Service Master Password with which Oracle log mining credentials are protected</span></span>  
  
-   <span data-ttu-id="49010-115">Eliminar un servicio de Windows de servicio CDC</span><span class="sxs-lookup"><span data-stu-id="49010-115">Deleting a CDC Service Windows service</span></span>  
  
-   <span data-ttu-id="49010-116">Desinstalar el software del servicio CDC para Oracle</span><span class="sxs-lookup"><span data-stu-id="49010-116">Uninstalling the CDC Service for Oracle software</span></span>  
  
-   <span data-ttu-id="49010-117">Mantener el software del servicio CDC para Oracle (por ejemplo, instalando actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="49010-117">Maintaining the CDC Service for Oracle software (for example, installing updates)</span></span>  
  
-   <span data-ttu-id="49010-118">Iniciar y detener un servicio de Windows de servicio CDC</span><span class="sxs-lookup"><span data-stu-id="49010-118">Starting and stopping a CDC Service Windows service</span></span>  
  
 <span data-ttu-id="49010-119">Al trabajar con configuraciones de alta disponibilidad, como clústeres de conmutación por error de Microsoft, el administrador del equipo debe tener responsabilidades y permisos adicionales como:</span><span class="sxs-lookup"><span data-stu-id="49010-119">When working with high-availability configurations, such as Microsoft failover clusters, the computer administrator must have additional responsibilities and permissions such as:</span></span>  
  
-   <span data-ttu-id="49010-120">Instalar y mantener el software del servicio CDC para Oracle en todos los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="49010-120">Installation and maintenance of the CDC Service for Oracle software on all cluster nodes.</span></span>  
  
-   <span data-ttu-id="49010-121">Definir los recursos genéricos del servicio de clúster para el servicio de Windows de servicio CDC en los distintos nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="49010-121">Defining generic cluster service resources for the CDC Service' Windows service on the various cluster nodes.</span></span>  
  
-   <span data-ttu-id="49010-122">Actuar como administrador del equipo autorizado como administrador en el equipo donde está instalado el servicio CDC para Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-122">Acting as the computer administrator authorized as an administrator on the computer where the CDC Service for Oracle is installed.</span></span> <span data-ttu-id="49010-123">Esta persona instala el servicio CDC para Oracle y emplea la Consola de configuración del servicio CDC para configurar un servicio CDC para Oracle en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="49010-123">This person installs the CDC Service for Oracle and uses the CDC Service Configuration Console to configure a CDC Service for Oracle on a local computer.</span></span>  
  
### <a name="service-account-oracle-cdc-service"></a><span data-ttu-id="49010-124">Cuenta de servicio: Servicio CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="49010-124">Service Account: Oracle CDC Service</span></span>  
 <span data-ttu-id="49010-125">Esta cuenta de servicio de Windows de servicio CDC de Oracle es una cuenta de Windows que se usa para ejecutar el servicio CDC de Oracle (la cuenta de servicio).</span><span class="sxs-lookup"><span data-stu-id="49010-125">This is Oracle CDC Service Windows Service Account is a Windows account used for running the Oracle CDC Service (the Service Account).</span></span>  
  
 <span data-ttu-id="49010-126">El único privilegio necesario para la cuenta de servicio es poder usar el cliente de Oracle y el proveedor ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="49010-126">The only required privilege necessary for the service account is to be able to use the Oracle client and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client ODBC provider.</span></span> <span data-ttu-id="49010-127">Esta cuenta no necesita tener acceso a archivos, a menos que lo necesiten determinados proveedores (por ejemplo, si la cadena de conexión de cliente de Oracle hace referencia a instancias de base de datos de Oracle en un archivo **tnsnames.ora** , la cuenta de servicio necesita tener acceso de lectura a ese archivo).</span><span class="sxs-lookup"><span data-stu-id="49010-127">This account does not need to access files unless required by specific providers (for example, if the Oracle client connection string references Oracle database instances in a **tnsnames.ora** file, then that file must be read-accessible to the service account).</span></span>  
  
 <span data-ttu-id="49010-128">Al crear un servicio CDC de Oracle en Windows Vista o Windows Server 2008, la cuenta de servicio predeterminada es SERVICIO DE RED.</span><span class="sxs-lookup"><span data-stu-id="49010-128">When creating an Oracle CDC Service on Windows Vista or Windows Server 2008, the default service account is the NETWORK SERVICE account.</span></span>  
  
 <span data-ttu-id="49010-129">En Windows 7, Windows Server 2008 R2 y versiones posteriores, la cuenta de servicio predeterminada es Servicio NT\\<nombre-servicio>.</span><span class="sxs-lookup"><span data-stu-id="49010-129">On Windows 7, Windows Server 2008 R2 and later, the default service account is NT Service\\<service-name>.</span></span>  
  
 <span data-ttu-id="49010-130">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecuta en otro equipo o es una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en clúster y el servicio necesita conectar con el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino usando la autenticación de Windows, la cuenta de servicio debe ser una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="49010-130">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on another machine or is a clustered [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and there the service needs to connect to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows authentication, then the service account should be a domain account.</span></span>  
  
## <a name="sql-server-user-roles"></a><span data-ttu-id="49010-131">Roles de usuario de SQL Server</span><span class="sxs-lookup"><span data-stu-id="49010-131">SQL Server User Roles</span></span>  
 <span data-ttu-id="49010-132">A continuación se describen los roles de usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que el servicio CDC de Oracle emplea.</span><span class="sxs-lookup"><span data-stu-id="49010-132">The following describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="oracle-cdc-service-administrator"></a><span data-ttu-id="49010-133">Administrador del servicio CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="49010-133">Oracle CDC Service Administrator</span></span>  
 <span data-ttu-id="49010-134">El administrador del servicio CDC es un usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con control total sobre los artefactos del servicio CDC de Oracle en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="49010-134">The CDC Service Administrator is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user with full control over the Oracle CDC Service artifacts in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="49010-135">El administrador del servicio CDC usa la Consola del diseñador CDC de Oracle para diseñar instancias CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-135">The CDC Service Administrator uses the Oracle CDC Designer Console to design Oracle CDC Instances.</span></span>  
  
 <span data-ttu-id="49010-136">El administrador del servicio CDC debe conceder los roles fijos de servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] public **y** dbcreator **de**.</span><span class="sxs-lookup"><span data-stu-id="49010-136">The CDC Service Administrator should be granted the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fixed server roles **public** and **dbcreator**.</span></span>  
  
 <span data-ttu-id="49010-137">Entre las tareas realizadas por el administrador del servicio CDC se incluyen:</span><span class="sxs-lookup"><span data-stu-id="49010-137">The tasks performed by the CDC Service Administrator include:</span></span>  
  
-   <span data-ttu-id="49010-138">Preparar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para hospedar instancias CDC de Oracle (que son bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="49010-138">Preparing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to host Oracle CDC Instances (which are [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases).</span></span> <span data-ttu-id="49010-139">En esta tarea, se crea una base de datos especial denominada MSXDBCDC en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49010-139">In this task, a special database called MSXDBCDC is created in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="49010-140">Crear una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-140">Creating an Oracle CDC Instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="49010-141">La tarea incluye habilitar la nueva base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para CDC, para la que se necesita un administrador del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (**sysadmin**).</span><span class="sxs-lookup"><span data-stu-id="49010-141">Task includes enabling the newly created [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for CDC, which requires a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator (**sysadmin**).</span></span>  
  
-   <span data-ttu-id="49010-142">Diseñar una instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-142">Designing an Oracle CDC Instance.</span></span> <span data-ttu-id="49010-143">Esta tarea incluye proporcionar información acerca de la base de datos de Oracle de origen y las tablas capturadas, lo que necesita un administrador de bases de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-143">This task includes providing information about the source Oracle database and captured tables, which requires an Oracle database administrator.</span></span>  
  
-   <span data-ttu-id="49010-144">Mantener la instancia CDC de Oracle a lo largo del tiempo, lo que incluye agregar y quitar instancias de captura y actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="49010-144">Maintaining the Oracle CDC Instance over time, which includes adding/removing capture instances and updating configuration.</span></span>  
  
-   <span data-ttu-id="49010-145">Habilitar o deshabilitar una instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-145">Enabling or disabling an Oracle CDC Instance.</span></span>  
  
-   <span data-ttu-id="49010-146">Supervisar el estado de una instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-146">Monitoring the state of an Oracle CDC Instance.</span></span>  
  
-   <span data-ttu-id="49010-147">Solucionar problemas que afectan a la instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-147">Troubleshooting issues that affect the Oracle CDC Instance.</span></span>  
  
 <span data-ttu-id="49010-148">El administrador del servicio CDC tiene, al menos inicialmente, el rol fijo de base de datos **db_owner** para la base de datos CDC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asociada a la instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-148">The CDC Service Administrator is, at least initially, in the **db_owner** fixed database role for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database associated with the Oracle CDC Instance.</span></span> <span data-ttu-id="49010-149">Esto proporciona al administrador del servicio CDC acceso a los datos modificados almacenados en la base de datos CDC.</span><span class="sxs-lookup"><span data-stu-id="49010-149">This gives the CDC Service Administrator access to the change data stored in the CDC database.</span></span> <span data-ttu-id="49010-150">Una vez creado, el rol **db_owner** de la base de datos CDC se puede asignar a otro usuario, que puede realizar todas las tareas indicadas anteriormente, excepto preparar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y crear otra instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-150">Once created, the **db_owner** role of the CDC database can be assigned to a different user who can carry out all of the tasks listed above except for preparing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and creating another Oracle CDC Instance).</span></span>  
  
 <span data-ttu-id="49010-151">El administrador del servicio CDC no necesita conocer la contraseña maestra especificada al crear el servicio de Windows CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-151">The CDC Service Administrator does not need to know the master password specified with the creation of the Oracle CDC Windows service.</span></span>  
  
### <a name="system-administrator"></a><span data-ttu-id="49010-152">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="49010-152">System Administrator</span></span>  
 <span data-ttu-id="49010-153">El administrador del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es un usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y necesita tener concedido el rol fijo de servidor **sysadmin** en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asociada a los servicios CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-153">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user and should be granted the fixed server **sysadmin** role on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance associated with the Oracle CDC Service(s).</span></span>  
  
 <span data-ttu-id="49010-154">Solo hay una tarea específica de CDC de Oracle que se realiza con el rol administrador del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y es habilitar la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para una instancia CDC de Oracle para CDC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49010-154">There is only one Oracle CDC specific task that carried out with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] System Administrator and that is to enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for an Oracle CDC Instance for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span></span> <span data-ttu-id="49010-155">Esta tarea se realiza mediante la Consola del diseñador CDC de Oracle al crear una nueva instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-155">This task is performed using the Oracle CDC Designer console when creating a new Oracle CDC Instance.</span></span>  
  
### <a name="oracle-cdc-service-user"></a><span data-ttu-id="49010-156">Usuario del servicio CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="49010-156">Oracle CDC Service User</span></span>  
 <span data-ttu-id="49010-157">El usuario del servicio CDC de Oracle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que el servicio CDC de Oracle emplea para realizar su trabajo en la base de datos MSXDBCDC y en todas las instancias CDC de Oracle (bases de datos CDC) administradas por este servicio.</span><span class="sxs-lookup"><span data-stu-id="49010-157">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service user is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login which is used by the Oracle CDC Service to perform its work against the MSXDBCDC and all of the Oracle CDC Instances (CDC databases) handled by this service.</span></span>  
  
 <span data-ttu-id="49010-158">El usuario del servicio CDC de Oracle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe ser lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49010-158">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service user should be granted the following:</span></span>  
  
-   <span data-ttu-id="49010-159">Miembro de los roles fijos de base de datos **db_dlladmin**, **db_datareader**y **db_datawriter** para todas las bases de datos CDC controladas por el servidor.</span><span class="sxs-lookup"><span data-stu-id="49010-159">Member of the fixed database roles **db_dlladmin**, **db_datareader**, and **db_datawriter** for all CDC databases handled by the server.</span></span>  
  
-   <span data-ttu-id="49010-160">Miembro de los roles fijos de base de datos **db_datareader** y **db_datawriter** para la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="49010-160">Member of the fixed database roles **db_datareader** and **db_datawriter** for the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="49010-161">Puesto que el servicio CDC de Oracle usa un único inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para trabajar con todas las bases de datos CDC y la base de datos MSXDBCDC, este inicio de sesión se debe asignar en todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="49010-161">Because the Oracle CDC Service uses a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to work with all CDC databases and the MSXDBCDC database, this login should be mapped in all of these databases.</span></span>  
  
### <a name="oracle-cdc-change-consumer"></a><span data-ttu-id="49010-162">Consumidor de cambios CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="49010-162">Oracle CDC Change Consumer</span></span>  
 <span data-ttu-id="49010-163">El consumidor de cambios CDC de Oracle es un usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usa los cambios almacenados en las tablas CDC de la base de datos de la instancia CDC de Oracle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49010-163">The Oracle CDC Change Consumer is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user that consumes changes stored in the CDC tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database.</span></span>  
  
 <span data-ttu-id="49010-164">Este usuario determina el rol de usuario necesario para tener acceso a cada una de las tablas CDC mediante las funciones CDC generadas por la infraestructura CDC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49010-164">This user determines the user role that is required for accessing each of the CDC tables through the CDC functions generated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC infrastructure.</span></span> <span data-ttu-id="49010-165">Si no se especifica ningún rol de usuario al especificar una instancia de captura, el acceso a los cambios está limitado al miembro del rol fijo de base de datos **db_owner** de la base de datos CDC.</span><span class="sxs-lookup"><span data-stu-id="49010-165">If no user role is specified when a capture instance is specified, access to the changes is limited to the member of the **db_owner** fixed database role of the CDC database.</span></span>  
  
## <a name="oracle-user-roles"></a><span data-ttu-id="49010-166">Roles de usuario de Oracle</span><span class="sxs-lookup"><span data-stu-id="49010-166">Oracle User Roles</span></span>  
 <span data-ttu-id="49010-167">A continuación se describen los roles de usuario de Oracle que el servicio CDC de Oracle emplea.</span><span class="sxs-lookup"><span data-stu-id="49010-167">The following describes the Oracle user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="database-administrator-dba"></a><span data-ttu-id="49010-168">Administrador de base de datos (DBA)</span><span class="sxs-lookup"><span data-stu-id="49010-168">Database Administrator (DBA)</span></span>  
 <span data-ttu-id="49010-169">El administrador de base de datos (DBA) de Oracle es un usuario de bases de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-169">The Oracle database administrator (DBA) is an Oracle database user.</span></span> <span data-ttu-id="49010-170">Entre las tareas realizadas por el DBA de Oracle se incluyen:</span><span class="sxs-lookup"><span data-stu-id="49010-170">The tasks performed by the Oracle DBA include:</span></span>  
  
-   <span data-ttu-id="49010-171">Configurar la base de datos de Oracle de origen para que funcione en modo ARCHIVELOG.</span><span class="sxs-lookup"><span data-stu-id="49010-171">Setting the source Oracle database to work in ARCHIVELOG mode.</span></span>  
  
-   <span data-ttu-id="49010-172">Configurar un usuario de minería de registros con los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="49010-172">Setting up a log mining user with the required permissions.</span></span>  
  
-   <span data-ttu-id="49010-173">Configurar el registro complementario para las tablas capturadas.</span><span class="sxs-lookup"><span data-stu-id="49010-173">Setting supplemental logging for captured tables.</span></span>  
  
-   <span data-ttu-id="49010-174">Ayudar a restaurar los archivos de registro de transacciones almacenados que ya no están disponibles para que se puedan procesar.</span><span class="sxs-lookup"><span data-stu-id="49010-174">Helping to restore archived transaction log files no longer available so they can be processed.</span></span>  
  
 <span data-ttu-id="49010-175">El administrador de bases de datos de Oracle puede obtener scripts SQL de Oracle que hay que ejecutar para que se puedan evaluar antes de ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="49010-175">The Oracle database administrator can get Oracle SQL scripts that need to run so they can be evaluated before running them.</span></span> <span data-ttu-id="49010-176">El administrador de base de datos de Oracle también puede ejecutar directamente scripts SQL de Oracle desde la Consola del diseñador CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="49010-176">The Oracle database administrator can also directly run Oracle SQL scripts from the Oracle CDC Designer console.</span></span>  
  
 <span data-ttu-id="49010-177">Si el administrador de base de datos de Oracle elige usar la Consola del diseñador CDC de Oracle, las credenciales del administrador no se conservan, a excepción del contexto (cuadro de diálogo) en el que se hayan usado.</span><span class="sxs-lookup"><span data-stu-id="49010-177">If the Oracle database administrator chooses to use the Oracle CDC Designer console, administrator's credentials are not kept except for the context (dialog) in which they were used.</span></span>  
  
 <span data-ttu-id="49010-178">El administrador de base de datos de Oracle trabaja en coordinación con el administrador del servicio CDC de Oracle en la configuración de las instancias CDC de Oracle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49010-178">The Oracle database administrator works in coordination with the Oracle CDC Service administrator on the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instances.</span></span>  
  
### <a name="log-mining-user"></a><span data-ttu-id="49010-179">Usuario de minería de registros</span><span class="sxs-lookup"><span data-stu-id="49010-179">Log Mining User</span></span>  
 <span data-ttu-id="49010-180">El usuario extractor de registros de Oracle es un usuario especial de base de datos de Oracle al que se conceden los privilegios necesarios para obtener acceso a los registros de transacciones de Oracle y procesarlos.</span><span class="sxs-lookup"><span data-stu-id="49010-180">The Oracle Log Miner user is a special Oracle database user that is granted the required privileges for accessing and processing the Oracle transaction logs.</span></span>  
  
 <span data-ttu-id="49010-181">Las credenciales de este usuario se almacenan en la base de datos de la instancia CDC de Oracle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante el cifrado de claves asimétricas.</span><span class="sxs-lookup"><span data-stu-id="49010-181">The credentials for this user are stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database using asymmetric key encryption.</span></span> <span data-ttu-id="49010-182">Solo son accesibles para el servicio CDC de Oracle, no para el propietario de la base de datos de la instancia CDC de Oracle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49010-182">They are accessible only to the Oracle CDC Service but not to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database owner.</span></span>  
  
 <span data-ttu-id="49010-183">En la lista siguiente se describen los privilegios necesarios que se deben conceder al usuario de minería de registros:</span><span class="sxs-lookup"><span data-stu-id="49010-183">The following list describes the required privileges of the log mining user should be granted:</span></span>  
  
-   <span data-ttu-id="49010-184">SELECT en \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="49010-184">SELECT on \<any-captured-table></span></span>  
  
-   <span data-ttu-id="49010-185">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="49010-185">SELECT ANY TRANSACTION</span></span>  
  
-   <span data-ttu-id="49010-186">EXECUTE en DBMS_LOGMNR</span><span class="sxs-lookup"><span data-stu-id="49010-186">EXECUTE on DBMS_LOGMNR</span></span>  
  
-   <span data-ttu-id="49010-187">SELECT en V$LOGMNR_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="49010-187">SELECT on V$LOGMNR_CONTENTS</span></span>  
  
-   <span data-ttu-id="49010-188">SELECT en V$ARCHIVED_LOG</span><span class="sxs-lookup"><span data-stu-id="49010-188">SELECT on V$ARCHIVED_LOG</span></span>  
  
-   <span data-ttu-id="49010-189">SELECT en V$LOG</span><span class="sxs-lookup"><span data-stu-id="49010-189">SELECT on V$LOG</span></span>  
  
-   <span data-ttu-id="49010-190">SELECT en V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="49010-190">SELECT on V$LOGFILE</span></span>  
  
-   <span data-ttu-id="49010-191">SELECT en V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="49010-191">SELECT on V$DATABASE</span></span>  
  
-   <span data-ttu-id="49010-192">SELECT en V$THREAD</span><span class="sxs-lookup"><span data-stu-id="49010-192">SELECT on V$THREAD</span></span>  
  
-   <span data-ttu-id="49010-193">SELECT en V$PARAMETER</span><span class="sxs-lookup"><span data-stu-id="49010-193">SELECT on V$PARAMETER</span></span>  
  
-   <span data-ttu-id="49010-194">SELECT en DBA_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="49010-194">SELECT on DBA_REGISTRY</span></span>  
  
-   <span data-ttu-id="49010-195">SELECT en ALL_INDEXES</span><span class="sxs-lookup"><span data-stu-id="49010-195">SELECT on ALL_INDEXES</span></span>  
  
-   <span data-ttu-id="49010-196">SELECT en ALL_OBJECTS</span><span class="sxs-lookup"><span data-stu-id="49010-196">SELECT on ALL_OBJECTS</span></span>  
  
-   <span data-ttu-id="49010-197">SELECT en DBA_OBJECTS</span><span class="sxs-lookup"><span data-stu-id="49010-197">SELECT on DBA_OBJECTS</span></span>  
  
-   <span data-ttu-id="49010-198">SELECT en ALL_TABLES</span><span class="sxs-lookup"><span data-stu-id="49010-198">SELECT on ALL_TABLES</span></span>  
  
 <span data-ttu-id="49010-199">Si alguno de estos privilegios no se puede conceder a un V$xxx, se debe conceder al V $xxx.</span><span class="sxs-lookup"><span data-stu-id="49010-199">If any of these privileges cannot be granted to a V$xxx, then they should be granted to the V $xxx.</span></span>  
  
### <a name="schema-user"></a><span data-ttu-id="49010-200">Usuario de esquema</span><span class="sxs-lookup"><span data-stu-id="49010-200">Schema User</span></span>  
 <span data-ttu-id="49010-201">El usuario de esquema de Oracle es un usuario de Oracle con acceso de lectura para el esquema de las tablas de Oracle que se van a capturar.</span><span class="sxs-lookup"><span data-stu-id="49010-201">The Oracle Schema User is an Oracle user with read access to the schema of the Oracle tables to be captured.</span></span> <span data-ttu-id="49010-202">Este usuario es necesario cuando se trabaja con la Consola del diseñador CDC de Oracle recuperar la lista de esquemas de Oracle, tablas que se van a capturar y sus columnas, índices y claves.</span><span class="sxs-lookup"><span data-stu-id="49010-202">This user is necessary when working with the Oracle CDC Designer console to retrieve the list of Oracle schema, tables to be captured and their columns, indexes and keys.</span></span>  
  
 <span data-ttu-id="49010-203">Las credenciales para este usuario nunca se almacenan.</span><span class="sxs-lookup"><span data-stu-id="49010-203">The credentials for this user are never stored.</span></span> <span data-ttu-id="49010-204">La Consola del diseñador CDC las solicita cada vez que son necesarias y se mantienen para las demás sesiones de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="49010-204">They are requested by the CDC Designer console each time they are needed and they are kept for the rest of the UI sessions.</span></span>  
  
  
