---
title: SQL Server 2014 Express LocalDB | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- user instances
- LocalDB, described
- local database runtime
- file database
- LocalDB
ms.assetid: 5a641a46-7cfb-4d7b-a90d-6e4625719d74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af60935af0d183ab7ed6d1c10f84229b7ead3730
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677873"
---
# <a name="sql-server-2014-express-localdb"></a><span data-ttu-id="1aeac-102">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="1aeac-102">SQL Server 2014 Express LocalDB</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="1aeac-103">[!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] `LocalDB` es un modo de ejecución de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] destinado a los desarrolladores de programas.</span><span class="sxs-lookup"><span data-stu-id="1aeac-103">[!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] `LocalDB` is an execution mode of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] targeted to program developers.</span></span> <span data-ttu-id="1aeac-104">`LocalDB`la instalación copia un conjunto mínimo de archivos necesarios para iniciar el [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1aeac-104">`LocalDB` installation copies a minimal set of files necessary to start the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="1aeac-105">Una vez `LocalDB` instalado, los desarrolladores inician una conexión mediante una cadena de conexión especial.</span><span class="sxs-lookup"><span data-stu-id="1aeac-105">Once `LocalDB` is installed, developers initiate a connection by using a special connection string.</span></span> <span data-ttu-id="1aeac-106">Cuando se realiza la conexión, se crea y se inicia automáticamente la infraestructura de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] necesaria, permitiendo que la aplicación use la base de datos sin tareas de configuración complejas o prolongadas en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="1aeac-106">When connecting, the necessary [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] infrastructure is automatically created and started, enabling the application to use the database without complex or time consuming configuration tasks.</span></span> <span data-ttu-id="1aeac-107">Las herramientas de desarrollo pueden proporcionar a los desarrolladores de software un [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que les permite escribir y probar el código de [!INCLUDE[tsql](../../includes/tsql-md.md)] sin tener que administrar una instancia de servidor completa de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1aeac-107">Developer Tools can provide developers with a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that lets them write and test [!INCLUDE[tsql](../../includes/tsql-md.md)] code without having to manage a full server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1aeac-108">Una instancia de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] `LocalDB` se administra mediante la `SqlLocalDB.exe` utilidad.</span><span class="sxs-lookup"><span data-stu-id="1aeac-108">An instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]`LocalDB` is managed by using the `SqlLocalDB.exe` utility.</span></span> [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]<span data-ttu-id="1aeac-109">`LocalDB`debe usarse en lugar de la [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] característica de instancia de usuario, que está en desuso.</span><span class="sxs-lookup"><span data-stu-id="1aeac-109">`LocalDB` should be used in place of the [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] user instance feature which is deprecated.</span></span>  
  
## <a name="installing-localdb"></a><span data-ttu-id="1aeac-110">Instalar LocalDB</span><span class="sxs-lookup"><span data-stu-id="1aeac-110">Installing LocalDB</span></span>  
 <span data-ttu-id="1aeac-111">El método principal de instalación `LocalDB` es mediante el programa SqlLocalDB.msi.</span><span class="sxs-lookup"><span data-stu-id="1aeac-111">The primary method of installing `LocalDB` is by using the SqlLocalDB.msi program.</span></span> <span data-ttu-id="1aeac-112">`LocalDB`es una opción al instalar cualquier SKU de [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1aeac-112">`LocalDB` is an option when installing any SKU of [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)].</span></span> <span data-ttu-id="1aeac-113">Seleccione `LocalDB` en la página **selección de características** durante la instalación de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1aeac-113">Select `LocalDB` on the **Feature Selection** page during installation of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="1aeac-114">Solo puede haber una instalación de los `LocalDB` archivos binarios para cada [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] versión principal.</span><span class="sxs-lookup"><span data-stu-id="1aeac-114">There can be only one installation of the `LocalDB` binary files for each major [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] version.</span></span> <span data-ttu-id="1aeac-115">Se pueden iniciar varios procesos de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y todos usarán los mismos binarios.</span><span class="sxs-lookup"><span data-stu-id="1aeac-115">Multiple [!INCLUDE[ssDE](../../includes/ssde-md.md)] processes can be started and will all use the same binaries.</span></span> <span data-ttu-id="1aeac-116">Una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] iniciado como `LocalDB` tiene las mismas limitaciones que[!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aeac-116">An instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] started as the `LocalDB` has the same limitations as [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]</span></span>  
  
## <a name="description"></a><span data-ttu-id="1aeac-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aeac-117">Description</span></span>  
 <span data-ttu-id="1aeac-118">El `LocalDB` programa de instalación utiliza el programa SqlLocalDB.msi para instalar los archivos necesarios en el equipo.</span><span class="sxs-lookup"><span data-stu-id="1aeac-118">The `LocalDB` setup program uses the SqlLocalDB.msi program to install the necessary files on the computer.</span></span> <span data-ttu-id="1aeac-119">Una vez instalada, `LocalDB` es una instancia de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] que puede crear y abrir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bases de datos de.</span><span class="sxs-lookup"><span data-stu-id="1aeac-119">Once installed, `LocalDB` is an instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] that can create and open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="1aeac-120">Los archivos de base de datos del sistema para la base de datos se almacenan normalmente en la ruta de acceso de AppData local de los usuarios, que suele estar oculta.</span><span class="sxs-lookup"><span data-stu-id="1aeac-120">The system database files for the database are stored in the users' local AppData path which is normally hidden.</span></span> <span data-ttu-id="1aeac-121">Por ejemplo, **C:\Users\\<usuario\>\AppData\Local\Microsoft\Microsoft SQL Server Local DB\Instances\LocalDBApp1\\**.</span><span class="sxs-lookup"><span data-stu-id="1aeac-121">For example **C:\Users\\<user\>\AppData\Local\Microsoft\Microsoft SQL Server Local DB\Instances\LocalDBApp1\\**.</span></span> <span data-ttu-id="1aeac-122">Los archivos de base de datos de usuario se almacenan donde indique el usuario, normalmente en alguna ubicación de la carpeta **C:\Usuarios\\<usuario\>\Documentos\\**.</span><span class="sxs-lookup"><span data-stu-id="1aeac-122">User database files are stored where the user designates, typically somewhere in the **C:\Users\\<user\>\Documents\\** folder.</span></span>  
  
 <span data-ttu-id="1aeac-123">Para obtener más información acerca `LocalDB` de cómo incluir en una aplicación, consulte la [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentación [información general sobre datos locales](https://msdn.microsoft.com/library/ms233817\(VS.110\).aspx), [Tutorial: creación de una base](https://msdn.microsoft.com/library/ms233763\(VS.110\).aspx)de datos de SQL Server LocalDB y [tutorial: conectarse a datos en una SQL Server base de datos LocalDB (Windows Forms)](https://msdn.microsoft.com/library/ms171890\(VS.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="1aeac-123">For more information about including `LocalDB` in an application, see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation [Local Data Overview](https://msdn.microsoft.com/library/ms233817\(VS.110\).aspx), [Walkthrough: Creating a SQL Server LocalDB Database](https://msdn.microsoft.com/library/ms233763\(VS.110\).aspx), and [Walkthrough: Connecting to Data in a SQL Server LocalDB Database (Windows Forms)](https://msdn.microsoft.com/library/ms171890\(VS.110\).aspx).</span></span>  
  
 <span data-ttu-id="1aeac-124">Para obtener más información sobre la `LocalDB` API, vea [SQL Server Express referencia de API de instancia de LocalDB](https://msdn.microsoft.com/library/hh234692\(SQL.110\).aspx) y la [función LocalDBStartInstance](https://msdn.microsoft.com/library/hh217143\(SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="1aeac-124">For more information about the `LocalDB` API, see [SQL Server Express LocalDB Instance API Reference](https://msdn.microsoft.com/library/hh234692\(SQL.110\).aspx) and [LocalDBStartInstance Function](https://msdn.microsoft.com/library/hh217143\(SQL.110\).aspx).</span></span>  
  
 <span data-ttu-id="1aeac-125">La utilidad SqlLocalDb puede crear nuevas instancias de `LocalDB` , iniciar y detener una instancia de `LocalDB` , e incluye opciones para ayudarle a administrar `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="1aeac-125">The SqlLocalDb utility can create new instances of `LocalDB`, start and stop an instance of `LocalDB`, and includes options to help you manage `LocalDB`.</span></span>  <span data-ttu-id="1aeac-126">Para obtener más información sobre la utilidad SqlLocalDb, vea [SqlLocalDB (utilidad)](../../tools/sqllocaldb-utility.md).</span><span class="sxs-lookup"><span data-stu-id="1aeac-126">For more information about the SqlLocalDb utility, see [SqlLocalDB Utility](../../tools/sqllocaldb-utility.md).</span></span>  
  
 <span data-ttu-id="1aeac-127">La intercalación de la instancia de `LocalDB` está establecida en SQL_LATIN1_GENERAL_CP1_CI_AS y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="1aeac-127">The instance collation for `LocalDB` is set to SQL_Latin1_General_CP1_CI_AS and cannot be changed.</span></span> <span data-ttu-id="1aeac-128">Normalmente se admiten las intercalaciones de nivel de base de datos, nivel de columna y nivel de expresión.</span><span class="sxs-lookup"><span data-stu-id="1aeac-128">Database-level, column-level, and expression-level collations are supported normally.</span></span> <span data-ttu-id="1aeac-129">Las bases de datos independientes siguen las reglas de las intercalaciones de metadatos y tempdb definidas por [Contained Database Collations](../../relational-databases/databases/contained-database-collations.md).</span><span class="sxs-lookup"><span data-stu-id="1aeac-129">Contained databases follow the metadata and tempdb collations rules defined by [Contained Database Collations](../../relational-databases/databases/contained-database-collations.md).</span></span>  
  
### <a name="restrictions"></a><span data-ttu-id="1aeac-130">Restricciones</span><span class="sxs-lookup"><span data-stu-id="1aeac-130">Restrictions</span></span>  
 <span data-ttu-id="1aeac-131">`LocalDB`no puede ser un suscriptor de replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="1aeac-131">`LocalDB` cannot be a merge replication subscriber.</span></span>  
  
 <span data-ttu-id="1aeac-132">`LocalDB`no admite FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="1aeac-132">`LocalDB` does not support FILESTREAM.</span></span>  
  
 <span data-ttu-id="1aeac-133">`LocalDB`solo permite colas locales para Service Broker.</span><span class="sxs-lookup"><span data-stu-id="1aeac-133">`LocalDB` only allows local queues for Service Broker.</span></span>  
  
 <span data-ttu-id="1aeac-134">Una instancia de `LocalDB` propiedad de las cuentas integradas, como NT AUTHORITY\SYSTEM, puede tener problemas de capacidad de administración debido a la redirección del sistema de archivos de Windows. En su lugar, use una cuenta de Windows normal como propietario.</span><span class="sxs-lookup"><span data-stu-id="1aeac-134">An instance of `LocalDB` owned by the built-in accounts such as NT AUTHORITY\SYSTEM can have manageability issues due to windows file system redirection; Instead use a normal windows account as the owner.</span></span>  
  
### <a name="automatic-and-named-instances"></a><span data-ttu-id="1aeac-135">Instancias automáticas y con nombre</span><span class="sxs-lookup"><span data-stu-id="1aeac-135">Automatic and Named Instances</span></span>  
 <span data-ttu-id="1aeac-136">`LocalDB`admite dos tipos de instancias: instancias automáticas e instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="1aeac-136">`LocalDB` supports two kinds of instances: Automatic instances and named instances.</span></span>  
  
-   <span data-ttu-id="1aeac-137">Las instancias automáticas de `LocalDB` son públicas.</span><span class="sxs-lookup"><span data-stu-id="1aeac-137">Automatic instances of `LocalDB` are public.</span></span> <span data-ttu-id="1aeac-138">Se crean y se administran automáticamente para el usuario y se pueden utilizar en cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="1aeac-138">They are created and managed automatically for the user and can be used by any application.</span></span> <span data-ttu-id="1aeac-139">Existe una instancia automática de `LocalDB` para cada versión de `LocalDB` instalada en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="1aeac-139">One automatic instance of `LocalDB` exists for every version of `LocalDB` installed on the user's computer.</span></span> <span data-ttu-id="1aeac-140">Las instancias automáticas de `LocalDB` proporcionan administración de instancias sin problemas.</span><span class="sxs-lookup"><span data-stu-id="1aeac-140">Automatic instances of `LocalDB` provide seamless instance management.</span></span> <span data-ttu-id="1aeac-141">No hay ninguna necesidad de crear la instancia; solo funciona.</span><span class="sxs-lookup"><span data-stu-id="1aeac-141">There is no need to create the instance; it just works.</span></span> <span data-ttu-id="1aeac-142">Esto permite la instalación y migración fáciles de las aplicaciones en un equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="1aeac-142">This allows for easy application installation and migration to a different computer.</span></span> <span data-ttu-id="1aeac-143">Si la máquina de destino tiene la versión especificada de `LocalDB` instalada, la instancia automática de `LocalDB` de esa versión también estará disponible en la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="1aeac-143">If the target machine has the specified version of `LocalDB` installed, the automatic instance of `LocalDB` for that version is available on the target machine as well.</span></span> <span data-ttu-id="1aeac-144">Las instancias automáticas de `LocalDB` tienen un patrón especial para el nombre de instancia que pertenece a un espacio de nombres reservado.</span><span class="sxs-lookup"><span data-stu-id="1aeac-144">Automatic instances of `LocalDB` have a special pattern for the instance name that belongs to a reserved namespace.</span></span> <span data-ttu-id="1aeac-145">Esto evita conflictos de nombres con las instancias con nombre de `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="1aeac-145">This prevents name conflicts with named instances of `LocalDB`.</span></span> <span data-ttu-id="1aeac-146">El nombre de la instancia automática es **MSSQLLocalDB**.</span><span class="sxs-lookup"><span data-stu-id="1aeac-146">The name for the automatic instance is **MSSQLLocalDB**.</span></span>  
  
-   <span data-ttu-id="1aeac-147">Las instancias con nombre de `LocalDB` son privadas.</span><span class="sxs-lookup"><span data-stu-id="1aeac-147">Named instances of `LocalDB` are private.</span></span> <span data-ttu-id="1aeac-148">Son propiedad de una sola aplicación que es la responsable de la creación y administración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="1aeac-148">They are owned by a single application that is responsible for creating and managing the instance.</span></span> <span data-ttu-id="1aeac-149">Las instancias con nombre proporcionan el aislamiento de otras instancias y pueden mejorar el rendimiento reduciendo la contención de recursos con otros usuarios de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="1aeac-149">Named instances provide isolation from other instances and can improve performance by reducing resource contention with other database users.</span></span> <span data-ttu-id="1aeac-150">El usuario debe crear explícitamente las instancias con nombre a través de la `LocalDB` API de administración o implícitamente a través del archivo de app.config para una aplicación administrada (aunque la aplicación administrada también puede usar la API, si lo desea).</span><span class="sxs-lookup"><span data-stu-id="1aeac-150">Named instances must be created explicitly by the user through the `LocalDB` management API or implicitly via the app.config file for a managed application (although managed application may also use the API, if desired).</span></span> <span data-ttu-id="1aeac-151">Cada instancia con nombre de `LocalDB` tiene una `LocalDB` versión asociada que señala al conjunto respectivo de `LocalDB` binarios.</span><span class="sxs-lookup"><span data-stu-id="1aeac-151">Each named instance of `LocalDB` has an associated `LocalDB` version that points to the respective set of `LocalDB` binaries.</span></span> <span data-ttu-id="1aeac-152">El nombre de instancia de un `LocalDB` tipo de datos de es `sysname` y puede tener hasta 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="1aeac-152">The instance name of a `LocalDB` is `sysname` data type and can have up to 128 characters.</span></span> <span data-ttu-id="1aeac-153">(Esto difiere de las instancias con nombre normales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , que limita los nombres a nombres NetBIOS normales de 16 caracteres ASCII). El nombre de una instancia de `LocalDB` puede contener cualquier carácter Unicode que sea válido dentro de un nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="1aeac-153">(This differs from regular named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], which limits names to regular NetBIOS names of 16 ASCII chars.) The name of an instance of `LocalDB` can contain any Unicode characters that are legal within a filename.</span></span>  <span data-ttu-id="1aeac-154">Una instancia con nombre que utiliza un nombre de instancia automática se convierte en una instancia automática.</span><span class="sxs-lookup"><span data-stu-id="1aeac-154">A named instance that uses an automatic instance name becomes an automatic instance.</span></span>  
  
 <span data-ttu-id="1aeac-155">Usuarios diferentes de un equipo pueden tener instancias con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="1aeac-155">Different users of a computer can have instances with the same name.</span></span> <span data-ttu-id="1aeac-156">Cada instancia es un proceso diferente que se ejecuta como un usuario diferente.</span><span class="sxs-lookup"><span data-stu-id="1aeac-156">Each instance is a different processes running as a different user.</span></span>  
  
## <a name="shared-instances-of-localdb"></a><span data-ttu-id="1aeac-157">Instancias compartidas de LocalDB</span><span class="sxs-lookup"><span data-stu-id="1aeac-157">Shared Instances of LocalDB</span></span>  
 <span data-ttu-id="1aeac-158">Para admitir escenarios donde varios usuarios del equipo necesitan conectarse a una sola instancia de `LocalDB` , admite el `LocalDB` uso compartido de instancias.</span><span class="sxs-lookup"><span data-stu-id="1aeac-158">To support scenarios where multiple users of the computer need to connect to a single instance of `LocalDB`, `LocalDB` supports instance sharing.</span></span> <span data-ttu-id="1aeac-159">Un propietario de una instancia puede decidir permitir que otros usuarios del equipo se conecten a la instancia.</span><span class="sxs-lookup"><span data-stu-id="1aeac-159">An instance owner can choose to allow the other users on the computer to connect to his instance.</span></span> <span data-ttu-id="1aeac-160">Se pueden compartir instancias automáticas y con nombre de `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="1aeac-160">Both automatic and named instances of `LocalDB` can be shared.</span></span> <span data-ttu-id="1aeac-161">Para compartir una instancia de `LocalDB`, un usuario selecciona un nombre compartido (alias) para ella.</span><span class="sxs-lookup"><span data-stu-id="1aeac-161">To share an instance of `LocalDB` a user selects a shared name (alias) for it.</span></span> <span data-ttu-id="1aeac-162">Dado que el nombre compartido está visible para todos los usuarios del equipo, este nombre compartido debe ser único en el equipo.</span><span class="sxs-lookup"><span data-stu-id="1aeac-162">Because the shared name is visible to all users of the computer, this shared name must be unique on the computer.</span></span> <span data-ttu-id="1aeac-163">El nombre compartido de una instancia de `LocalDB` tiene el mismo formato que la instancia con nombre de `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="1aeac-163">The shared name for an instance of `LocalDB` has the same format as the named instance of `LocalDB`.</span></span>  
  
 <span data-ttu-id="1aeac-164">Solo un administrador del equipo puede crear una instancia compartida de `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="1aeac-164">Only an administrator on the computer can create a shared instance of `LocalDB`.</span></span> <span data-ttu-id="1aeac-165">Un `LocalDB` Administrador o el propietario de la instancia compartida de pueden dejar de compartir una instancia compartida de `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="1aeac-165">A shared instance of `LocalDB` can be unshared by an administrator or by the owner of the shared instance of `LocalDB`.</span></span> <span data-ttu-id="1aeac-166">Para compartir y dejar de compartir una instancia de `LocalDB` , use los `LocalDBShareInstance` `LocalDBUnShareInstance` métodos y de la `LocalDB` API, o las opciones compartir y no compartir de la utilidad SqlLocalDb.</span><span class="sxs-lookup"><span data-stu-id="1aeac-166">To share and unshared an instance of `LocalDB`, use the `LocalDBShareInstance` and `LocalDBUnShareInstance` methods of the `LocalDB` API, or the share and unshared options of the SqlLocalDb utility.</span></span>  
  
## <a name="starting-localdb-and-connecting-to-localdb"></a><span data-ttu-id="1aeac-167">Iniciar LocalDB y conectarse a LocalDB</span><span class="sxs-lookup"><span data-stu-id="1aeac-167">Starting LocalDB and Connecting to LocalDB</span></span>  
  
### <a name="connecting-to-the-automatic-instance"></a><span data-ttu-id="1aeac-168">Conectarse con la instancia automática</span><span class="sxs-lookup"><span data-stu-id="1aeac-168">Connecting to the Automatic Instance</span></span>  
 <span data-ttu-id="1aeac-169">La forma más fácil de usar `LocalDB` es conectarse a la instancia automática propiedad del usuario actual mediante la cadena de conexión **"Server = (LocalDB) \MSSQLLocalDB; Integrated Security = true"**.</span><span class="sxs-lookup"><span data-stu-id="1aeac-169">The easiest way to use `LocalDB` is to connect to the automatic instance owned by the current user by using the connection string **"Server=(localdb)\MSSQLLocalDB;Integrated Security=true"**.</span></span> <span data-ttu-id="1aeac-170">Para conectarse a una base de datos concreta con el nombre de archivo, conéctese mediante una cadena de conexión similar a **"Server=(LocalDB)\MSSQLLocalDB; Integrated Security=true ;AttachDbFileName=D:\Data\MyDB1.mdf"**.</span><span class="sxs-lookup"><span data-stu-id="1aeac-170">To connect to a specific database by using the file name, connect using a connection string similar to **"Server=(LocalDB)\MSSQLLocalDB; Integrated Security=true ;AttachDbFileName=D:\Data\MyDB1.mdf"**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1aeac-171">La primera vez que un usuario de un equipo intenta conectarse a `LocalDB` , se debe crear e iniciar la instancia automática.</span><span class="sxs-lookup"><span data-stu-id="1aeac-171">The first time a user on a computer tries to connect to `LocalDB`, the automatic instance must be both created and started.</span></span> <span data-ttu-id="1aeac-172">El tiempo adicional para la creación de la instancia puede hacer que el intento de conexión deje de funcionar con un mensaje de fin de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1aeac-172">The extra time for the instance to be created can cause the connection attempt to fail with a timeout message.</span></span> <span data-ttu-id="1aeac-173">Cuando sucede esto, espere unos segundos para que el proceso de creación se complete y, a continuación, conéctese de nuevo.</span><span class="sxs-lookup"><span data-stu-id="1aeac-173">When this happens, wait a few seconds to let the creation process complete, and then connect again.</span></span>  
  
### <a name="creating-and-connecting-to-a-named-instances"></a><span data-ttu-id="1aeac-174">Crear instancias con nombre y conectarse a ellas</span><span class="sxs-lookup"><span data-stu-id="1aeac-174">Creating and Connecting to a Named Instances</span></span>  
 <span data-ttu-id="1aeac-175">Además de la instancia automática, `LocalDB` también admite instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="1aeac-175">In addition to the automatic instance, `LocalDB` also supports named instances.</span></span> <span data-ttu-id="1aeac-176">Utilice el programa SqlLocalDB.exe para crear, iniciar y detener una instancia con nombre de `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="1aeac-176">Use the SqlLocalDB.exe program to create, start, and stop an named instance of `LocalDB`.</span></span> <span data-ttu-id="1aeac-177">Para obtener más información sobre SqlLocalDB.exe, vea [SqlLocalDB (utilidad)](../../tools/sqllocaldb-utility.md).</span><span class="sxs-lookup"><span data-stu-id="1aeac-177">For more information about SqlLocalDB.exe, see [SqlLocalDB Utility](../../tools/sqllocaldb-utility.md).</span></span>  
  
```ms-dos  
REM Create an instance of LocalDB  
"C:\Program Files\Microsoft SQL Server\120\Tools\Binn\SqlLocalDB.exe" create LocalDBApp1  
REM Start the instance of LocalDB  
"C:\Program Files\Microsoft SQL Server\120\Tools\Binn\SqlLocalDB.exe" start LocalDBApp1  
REM Gather information about the instance of LocalDB  
"C:\Program Files\Microsoft SQL Server\120\Tools\Binn\SqlLocalDB.exe" info LocalDBApp1  
```  
  
 <span data-ttu-id="1aeac-178">La última línea anterior devuelve información similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="1aeac-178">The last line above, returns information similar to the following.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1aeac-179">Nombre</span><span class="sxs-lookup"><span data-stu-id="1aeac-179">Name</span></span>|<span data-ttu-id="1aeac-180">"LocalDBApp1"</span><span class="sxs-lookup"><span data-stu-id="1aeac-180">"LocalDBApp1"</span></span>|  
|<span data-ttu-id="1aeac-181">Versión</span><span class="sxs-lookup"><span data-stu-id="1aeac-181">Version</span></span>|\<Current Version>|  
|<span data-ttu-id="1aeac-182">Nombre compartido</span><span class="sxs-lookup"><span data-stu-id="1aeac-182">Shared name</span></span>|<span data-ttu-id="1aeac-183">""</span><span class="sxs-lookup"><span data-stu-id="1aeac-183">""</span></span>|  
|<span data-ttu-id="1aeac-184">Propietario</span><span class="sxs-lookup"><span data-stu-id="1aeac-184">Owner</span></span>|<span data-ttu-id="1aeac-185">"\<Your Windows User>"</span><span class="sxs-lookup"><span data-stu-id="1aeac-185">"\<Your Windows User>"</span></span>|  
|<span data-ttu-id="1aeac-186">Creación automática</span><span class="sxs-lookup"><span data-stu-id="1aeac-186">Auto create</span></span>|<span data-ttu-id="1aeac-187">No</span><span class="sxs-lookup"><span data-stu-id="1aeac-187">No</span></span>|  
|<span data-ttu-id="1aeac-188">State</span><span class="sxs-lookup"><span data-stu-id="1aeac-188">State</span></span>|<span data-ttu-id="1aeac-189">en ejecución</span><span class="sxs-lookup"><span data-stu-id="1aeac-189">running</span></span>|  
|<span data-ttu-id="1aeac-190">Última hora de inicio</span><span class="sxs-lookup"><span data-stu-id="1aeac-190">Last start time</span></span>|\<Date and Time>|  
|<span data-ttu-id="1aeac-191">Nombre de canalización de instancia</span><span class="sxs-lookup"><span data-stu-id="1aeac-191">Instance pipe name</span></span>|<span data-ttu-id="1aeac-192">np:\\\\.\pipe\LOCALDB#F365A78E\tsql\query</span><span class="sxs-lookup"><span data-stu-id="1aeac-192">np:\\\\.\pipe\LOCALDB#F365A78E\tsql\query</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="1aeac-193">Si su aplicación usa una versión de .NET anterior a la 4.0.2, debe conectarse directamente a la canalización con nombre de `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="1aeac-193">If your application uses a version of .NET before 4.0.2 you must connect directly to the named pipe of the `LocalDB`.</span></span> <span data-ttu-id="1aeac-194">El valor de nombre de canalización de instancia es la canalización con nombre en la que escucha la instancia de `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="1aeac-194">The Instance pipe name value is the named pipe that the instance of `LocalDB` is listening on.</span></span> <span data-ttu-id="1aeac-195">La parte del nombre de la canalización de la instancia después de LOCALDB # cambiará cada vez que se inicie la instancia de `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="1aeac-195">The portion of the Instance pipe name after LOCALDB# will change each time the instance of `LocalDB` is started.</span></span> <span data-ttu-id="1aeac-196">Para conectarse a la instancia de mediante `LocalDB` [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , escriba el nombre de la canalización de instancia en el cuadro **nombre del servidor** del cuadro de diálogo \*\*conectar con [!INCLUDE[ssDE](../../includes/ssde-md.md)] \*\* .</span><span class="sxs-lookup"><span data-stu-id="1aeac-196">To connect to the instance of `LocalDB` by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], type the Instance pipe name in the **Server name** box of the **Connect to [!INCLUDE[ssDE](../../includes/ssde-md.md)]** dialog box.</span></span> <span data-ttu-id="1aeac-197">En el programa personalizado puede establecer conexión con la instancia de `LocalDB` mediante una cadena de conexión similar a`SqlConnection conn = new SqlConnection(@"Server=np:\\.\pipe\LOCALDB#F365A78E\tsql\query");`</span><span class="sxs-lookup"><span data-stu-id="1aeac-197">From your custom program you can establish connection to the instance of `LocalDB` using a connection string similar to `SqlConnection conn = new SqlConnection(@"Server=np:\\.\pipe\LOCALDB#F365A78E\tsql\query");`</span></span>  
  
### <a name="connecting-to-a-shared-instance-of-localdb"></a><span data-ttu-id="1aeac-198">Conectarse a una instancia compartida de LocalDB</span><span class="sxs-lookup"><span data-stu-id="1aeac-198">Connecting to a Shared Instance of LocalDB</span></span>  
 <span data-ttu-id="1aeac-199">Para conectarse a una instancia compartida de `LocalDB` Add \*\* \\ \*\* (punto + barra diagonal inversa) a la cadena de conexión para hacer referencia al espacio de nombres reservado para las instancias compartidas.</span><span class="sxs-lookup"><span data-stu-id="1aeac-199">To connect to a shared instance of `LocalDB` add **.\\** (dot + backslash) to the connection string to reference the namespace reserved for shared instances.</span></span> <span data-ttu-id="1aeac-200">Por ejemplo, para conectarse a una instancia compartida de `LocalDB` denominada, `AppData` use una cadena de conexión como `(localdb)\.\AppData` como parte de la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="1aeac-200">For example, to connect to a shared instance of `LocalDB` named `AppData` use a connection string such as `(localdb)\.\AppData` as part of the connection string.</span></span> <span data-ttu-id="1aeac-201">Un usuario que se conecta a una instancia compartida de `LocalDB` que no es de su propiedad debe tener un inicio de sesión de autenticación de Windows o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autenticación de.</span><span class="sxs-lookup"><span data-stu-id="1aeac-201">A user connecting to a shared instance of `LocalDB` that they do not own must have a Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication login.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1aeac-202">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="1aeac-202">Troubleshooting</span></span>  
 <span data-ttu-id="1aeac-203">Para obtener información acerca de la solución de problemas `LocalDB` , consulte [solución de problemas SQL Server 2012 Express LocalDB](https://social.technet.microsoft.com/wiki/contents/articles/4609.aspx).</span><span class="sxs-lookup"><span data-stu-id="1aeac-203">For information about troubleshooting `LocalDB`, see [Troubleshooting SQL Server 2012 Express LocalDB](https://social.technet.microsoft.com/wiki/contents/articles/4609.aspx).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="1aeac-204">Permisos</span><span class="sxs-lookup"><span data-stu-id="1aeac-204">Permissions</span></span>  
 <span data-ttu-id="1aeac-205">Una instancia de [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] `LocalDB` es una instancia creada por un usuario para su uso.</span><span class="sxs-lookup"><span data-stu-id="1aeac-205">An instance of [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)]`LocalDB` is an instance created by a user for their use.</span></span> <span data-ttu-id="1aeac-206">Cualquier usuario del equipo puede crear una base de datos mediante una instancia de `LocalDB` , almacenando archivos en su perfil de usuario y ejecutando el proceso con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="1aeac-206">Any user on the computer can create a database using an instance of `LocalDB`, storing files under their user profile and running the process under their credentials.</span></span> <span data-ttu-id="1aeac-207">De forma predeterminada, el acceso a la instancia de `LocalDB` está limitado a su propietario.</span><span class="sxs-lookup"><span data-stu-id="1aeac-207">By default, access to the instance of `LocalDB` is limited to its owner.</span></span> <span data-ttu-id="1aeac-208">Los datos contenidos en `LocalDB` están protegidos por el acceso al sistema de archivos a los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1aeac-208">The data contained in the `LocalDB` is protected by file system access to the database files.</span></span> <span data-ttu-id="1aeac-209">Si los archivos de base de datos de usuario se almacenan en una ubicación compartida, cualquier usuario con acceso al sistema de archivos en esa ubicación puede abrir la base de datos mediante una instancia de la `LocalDB` que poseen.</span><span class="sxs-lookup"><span data-stu-id="1aeac-209">If user database files are stored in a shared location, the database can be opened by anyone with file system access to that location by using an instance of `LocalDB` that they own.</span></span> <span data-ttu-id="1aeac-210">Si los archivos de base de datos están en una ubicación protegida, como la carpeta de datos de los usuarios, solo el usuario y los administradores con acceso a la carpeta pueden abrir la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1aeac-210">If the database files are in a protected location, such as the users data folder, only that user, and any administrators with access to that folder, can open the database.</span></span> <span data-ttu-id="1aeac-211">Los `LocalDB` archivos solo se pueden abrir en una instancia de `LocalDB` a la vez.</span><span class="sxs-lookup"><span data-stu-id="1aeac-211">The `LocalDB` files can only be opened by one instance of `LocalDB` at a time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1aeac-212">`LocalDB`siempre se ejecuta en el contexto de seguridad de los usuarios. es decir, `LocalDB` nunca se ejecuta con credenciales del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="1aeac-212">`LocalDB` always runs under the users security context; that is, `LocalDB` never runs with credentials from the local Administrator's group.</span></span> <span data-ttu-id="1aeac-213">Esto significa que todos los archivos de base de datos usados por una `LocalDB` instancia de deben ser accesibles mediante la cuenta de Windows del usuario propietario, sin considerar la pertenencia al grupo local Administradores.</span><span class="sxs-lookup"><span data-stu-id="1aeac-213">This means that all database files used by a `LocalDB` instance must be accessible using the owning user's Windows account, without considering membership in the local Administrators group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aeac-214">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1aeac-214">See Also</span></span>  
 [<span data-ttu-id="1aeac-215">SqlLocalDB (utilidad)</span><span class="sxs-lookup"><span data-stu-id="1aeac-215">SqlLocalDB Utility</span></span>](../../tools/sqllocaldb-utility.md)  
  
  