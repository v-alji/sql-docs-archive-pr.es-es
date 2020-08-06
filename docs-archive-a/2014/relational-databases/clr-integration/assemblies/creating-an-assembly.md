---
title: Crear un ensamblado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- creating assemblies
- UNSAFE assemblies
- CREATE ASSEMBLY statement
- SAFE assemblies
- EXTERNAL_ACCESS assemblies
- assemblies [CLR integration], creating
ms.assetid: a2bc503d-b6b2-4963-8beb-c11c323f18e0
author: rothja
ms.author: jroth
ms.openlocfilehash: 9dea1f8fe57691f05274cac353a1064420309e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747625"
---
# <a name="creating-an-assembly"></a><span data-ttu-id="fda8d-102">Crear un ensamblado</span><span class="sxs-lookup"><span data-stu-id="fda8d-102">Creating an Assembly</span></span>
  <span data-ttu-id="fda8d-103">Los objetos de base de datos administrados, como procedimientos almacenados o desencadenadores, se compilan y, a continuación, se implementan en unidades denominadas ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fda8d-103">Managed database objects, such as stored procedures or triggers, are compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="fda8d-104">Los ensamblados de archivos DLL administrados deben registrarse en [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] para poder usar la funcionalidad que proporciona el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fda8d-104">Managed DLL assemblies must be registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] before the functionality the assembly provides can be used.</span></span> <span data-ttu-id="fda8d-105">Para registrar un ensamblado en una base de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , use la instrucción CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="fda8d-105">To register an assembly in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, use the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="fda8d-106">En este tema se explica cómo registrar un ensamblado en una base de datos mediante la instrucción CREATE ASSEMBLY y cómo especificar la configuración de seguridad del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fda8d-106">This topic discusses how to register an assembly in a database using the CREATE ASSEMBLY statement, and how to specify the security settings for the assembly.</span></span>  
  
## <a name="the-create-assembly-statement"></a><span data-ttu-id="fda8d-107">La instrucción CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="fda8d-107">The CREATE ASSEMBLY Statement</span></span>  
 <span data-ttu-id="fda8d-108">La instrucción CREATE ASSEMBLY se usa para crear un ensamblado en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="fda8d-108">The CREATE ASSEMBLY statement is used to create an assembly in a database.</span></span> <span data-ttu-id="fda8d-109">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fda8d-109">Here is an example:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="fda8d-110">La cláusula FROM especifica el nombre de ruta de acceso del ensamblado que va a crearse.</span><span class="sxs-lookup"><span data-stu-id="fda8d-110">The FROM clause specifies the pathname of the assembly to create.</span></span> <span data-ttu-id="fda8d-111">Esta ruta de acceso puede ser una ruta de acceso UNC (Convención de nomenclatura universal) o una ruta de acceso al archivo físico local en el equipo.</span><span class="sxs-lookup"><span data-stu-id="fda8d-111">This path can either be a Universal Naming Convention (UNC) path or a physical file path that is local to the machine.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="fda8d-112">no permite registrar distintas versiones de un ensamblado con el mismo nombre, referencia cultural y clave pública.</span><span class="sxs-lookup"><span data-stu-id="fda8d-112">does not allow registering different versions of an assembly with the same name, culture and public key.</span></span>  
  
 <span data-ttu-id="fda8d-113">Es posible crear ensamblados que hagan referencia a otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fda8d-113">It is possible to create assemblies that reference other assemblies.</span></span> <span data-ttu-id="fda8d-114">Cuando se crea un ensamblado en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , también crea los ensamblados a los que hace referencia el ensamblado de nivel raíz, si los ensamblados a los que se hace referencia aún no se han creado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fda8d-114">When an assembly is created in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] also creates the assemblies referenced by the root-level assembly, if the referenced assemblies are not already created into the database.</span></span>  
  
 <span data-ttu-id="fda8d-115">Se conceden permisos a los usuarios de base de datos o a los roles de usuario para crear y, por tanto, establecerse como propietarios de los ensamblados de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="fda8d-115">Database users or user roles are given permissions to create, and thereby own, assemblies in a database.</span></span> <span data-ttu-id="fda8d-116">Para crear ensamblados, el rol o el usuario de base de datos debe disponer del permiso CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="fda8d-116">In order to create assemblies, the database user or role should have the CREATE ASSEMBLY permission.</span></span>  
  
 <span data-ttu-id="fda8d-117">Un ensamblado solo puede hacer referencia correctamente a otros ensamblados si:</span><span class="sxs-lookup"><span data-stu-id="fda8d-117">An assembly can only succeed in referencing other assemblies if:</span></span>  
  
-   <span data-ttu-id="fda8d-118">El ensamblado al que se llama o se hace referencia es propiedad del mismo usuario o del mismo rol.</span><span class="sxs-lookup"><span data-stu-id="fda8d-118">The assembly that is called or referenced is owned by the same user or role.</span></span>  
  
-   <span data-ttu-id="fda8d-119">El ensamblado al que se llama o se hace referencia se creó en la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="fda8d-119">The assembly that is called or referenced was created in the same database.</span></span>  
  
## <a name="specifying-security-when-creating-assemblies"></a><span data-ttu-id="fda8d-120">Especificar la seguridad al crear ensamblados</span><span class="sxs-lookup"><span data-stu-id="fda8d-120">Specifying Security When Creating Assemblies</span></span>  
 <span data-ttu-id="fda8d-121">Al crear un ensamblado en una base de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], puede especificar uno de los tres niveles distintos de seguridad en los que puede ejecutarse el código: `SAFE`, `EXTERNAL_ACCESS` o `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="fda8d-121">When creating an assembly into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, you can specify one of three different levels of security in which your code can run: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="fda8d-122">Cuando se ejecuta la instrucción `CREATE ASSEMBLY`, se realizan determinadas comprobaciones en el ensamblado de código que pueden provocar que el ensamblado no se registre en el servidor.</span><span class="sxs-lookup"><span data-stu-id="fda8d-122">When the `CREATE ASSEMBLY` statement is run, certain checks are performed on the code assembly which may cause the assembly to fail to register on the server.</span></span> <span data-ttu-id="fda8d-123">Para obtener más información, vea el ejemplo de suplantación en [CodePlex](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="fda8d-123">For more information, see the Impersonation sample on [CodePlex](https://msftengprodsamples.codeplex.com/).</span></span>  
  
 <span data-ttu-id="fda8d-124">`SAFE` es el conjunto de permisos predeterminado y funciona en la mayoría de los escenarios.</span><span class="sxs-lookup"><span data-stu-id="fda8d-124">`SAFE` is the default permission set and works for the majority of scenarios.</span></span> <span data-ttu-id="fda8d-125">Para especificar un nivel de seguridad determinado, debe modificar la sintaxis de la instrucción CREATE ASSEMBLY tal y como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="fda8d-125">To specify a given security level, you modify the syntax of the CREATE ASSEMBLY statement as follows:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = SAFE;  
```  
  
 <span data-ttu-id="fda8d-126">También es posible crear un ensamblado con el conjunto de permisos `SAFE` simplemente omitiendo la tercera línea del código anterior:</span><span class="sxs-lookup"><span data-stu-id="fda8d-126">It is also possible to create an assembly with the `SAFE` permission set by simply omitting the third line of code above:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="fda8d-127">Cuando el código de un ensamblado se ejecuta con el conjunto de permisos `SAFE`, solo puede realizar tareas de cálculo y acceso a datos en el servidor a través del proveedor administrado en proceso.</span><span class="sxs-lookup"><span data-stu-id="fda8d-127">When code in an assembly runs under the `SAFE` permission set, it can only do computation and data access within the server through the in-process managed provider.</span></span>  
  
### <a name="creating-external_access-and-unsafe-assemblies"></a><span data-ttu-id="fda8d-128">Crear ensamblados EXTERNAL_ACCESS y UNSAFE</span><span class="sxs-lookup"><span data-stu-id="fda8d-128">Creating EXTERNAL_ACCESS and UNSAFE Assemblies</span></span>  
 <span data-ttu-id="fda8d-129">`EXTERNAL_ACCESS` se usa en escenarios en los que el código necesita tener acceso a recursos fuera del servidor, como archivos, la red, el Registro y variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="fda8d-129">`EXTERNAL_ACCESS` addresses scenarios in which the code needs to access resources outside the server, such as files, network, registry, and environment variables.</span></span> <span data-ttu-id="fda8d-130">Cuando el servidor obtiene acceso a un recurso externo, suplanta el contexto de seguridad del usuario que llama al código administrado.</span><span class="sxs-lookup"><span data-stu-id="fda8d-130">Whenever the server accesses an external resource, it impersonates the security context of the user calling the managed code.</span></span>  
  
 <span data-ttu-id="fda8d-131">El permiso de código `UNSAFE` se usa en escenarios en los que no puede comprobarse la seguridad de un ensamblado o el ensamblado requiere acceso adicional a recursos restringidos, como la API Win32 de [!INCLUDE[msCoName](../../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fda8d-131">`UNSAFE` code permission is for those situations in which an assembly is not verifiably safe or requires additional access to restricted resources, such as the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 API.</span></span>  
  
 <span data-ttu-id="fda8d-132">Para crear un ensamblado `EXTERNAL_ACCESS` o `UNSAFE` en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], debe cumplirse una de las dos condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="fda8d-132">To create an `EXTERNAL_ACCESS` or `UNSAFE` assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], one of the following two conditions must be met:</span></span>  
  
1.  <span data-ttu-id="fda8d-133">El ensamblado está firmado con un nombre seguro o firmado mediante Authenticode con un certificado.</span><span class="sxs-lookup"><span data-stu-id="fda8d-133">The assembly is strong name signed or Authenticode signed with a certificate.</span></span> <span data-ttu-id="fda8d-134">Este nombre seguro (o certificado) se crea dentro de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como una clave asimétrica (o certificado) y dispone de un inicio de sesión correspondiente con permiso `EXTERNAL ACCESS ASSEMBLY` (para ensamblados de acceso externo) o permiso `UNSAFE ASSEMBLY` (para ensamblados no seguros).</span><span class="sxs-lookup"><span data-stu-id="fda8d-134">This strong name (or certificate) is created inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as an asymmetric key (or certificate), and has a corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission (for external access assemblies) or `UNSAFE ASSEMBLY` permission (for unsafe assemblies).</span></span>  
  
2.  <span data-ttu-id="fda8d-135">El propietario de la base de datos (DBO) tiene `EXTERNAL ACCESS ASSEMBLY` `EXTERNAL ACCESS` el permiso (para ensamblados) o `UNSAFE ASSEMBLY` (para `UNSAFE` ensamblados), y la base de datos tiene la [propiedad de base de datos TRUSTWORTHY](../../security/trustworthy-database-property.md) establecida en `ON` .</span><span class="sxs-lookup"><span data-stu-id="fda8d-135">The database owner (DBO) has `EXTERNAL ACCESS ASSEMBLY` (for `EXTERNAL ACCESS` assemblies) or `UNSAFE ASSEMBLY` (for `UNSAFE` assemblies) permission, and the database has the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) set to `ON`.</span></span>  
  
 <span data-ttu-id="fda8d-136">Las dos condiciones indicadas anteriormente también se comprueban en el momento de carga del ensamblado (que incluye la ejecución).</span><span class="sxs-lookup"><span data-stu-id="fda8d-136">The two conditions listed above are also checked at assembly load time (which includes execution).</span></span> <span data-ttu-id="fda8d-137">Para cargar el ensamblado debe cumplirse al menos una de las condiciones.</span><span class="sxs-lookup"><span data-stu-id="fda8d-137">At least one of the conditions must be met in order to load the assembly.</span></span>  
  
 <span data-ttu-id="fda8d-138">Se recomienda que la [propiedad de base de datos TRUSTWORTHY](../../security/trustworthy-database-property.md) de una base de datos no se establezca en `ON` solo para ejecutar el código de Common Language Runtime (CLR) en el proceso de servidor.</span><span class="sxs-lookup"><span data-stu-id="fda8d-138">We recommend that the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) on a database not be set to `ON` only to run common language runtime (CLR) code in the server process.</span></span> <span data-ttu-id="fda8d-139">En lugar de ello, es aconsejable crear una clave asimétrica a partir del archivo de ensamblado de la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="fda8d-139">Instead, we recommend that an asymmetric key be created from the assembly file in the master database.</span></span> <span data-ttu-id="fda8d-140">A continuación debe crearse un inicio de sesión asignado a esta clave asimétrica y debe concederse el permiso `EXTERNAL ACCESS ASSEMBLY` o `UNSAFE ASSEMBLY` al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="fda8d-140">A login mapped to this asymmetric key must then be created, and the login must be granted `EXTERNAL ACCESS ASSEMBLY` or `UNSAFE ASSEMBLY` permission.</span></span>  
  
 <span data-ttu-id="fda8d-141">Las [!INCLUDE[tsql](../../../includes/tsql-md.md)] instrucciones siguientes antes de ejecutar la instrucción CREATE Assembly.</span><span class="sxs-lookup"><span data-stu-id="fda8d-141">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll'     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey     
GRANT EXTERNAL ACCESS ASSEMBLY TO SQLCLRTestLogin;   
GO   
```  
  
> [!NOTE]  
>  <span data-ttu-id="fda8d-142">Debe crear un nuevo inicio de sesión para asociarlo a la clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="fda8d-142">You must create a new login to associate with the asymmetric key.</span></span> <span data-ttu-id="fda8d-143">Este inicio de sesión solamente se usa para conceder permisos; no tiene que asociarse a ningún usuario ni usarse dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fda8d-143">This login is only used to grant permissions; it does not have to be associated with a user, or used within the application.</span></span>  
  
 <span data-ttu-id="fda8d-144">Para crear un ensamblado `EXTERNAL ACCESS`, el creador debe contar con permiso `EXTERNAL ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="fda8d-144">To create an `EXTERNAL ACCESS` assembly, the creator needs to have `EXTERNAL ACCESS` permission.</span></span> <span data-ttu-id="fda8d-145">Este permiso se especifica al crear el ensamblado:</span><span class="sxs-lookup"><span data-stu-id="fda8d-145">This is specified when creating the assembly:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
```  
  
 <span data-ttu-id="fda8d-146">Las [!INCLUDE[tsql](../../../includes/tsql-md.md)] instrucciones siguientes antes de ejecutar la instrucción CREATE Assembly.</span><span class="sxs-lookup"><span data-stu-id="fda8d-146">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll';     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey ;    
GRANT UNSAFE ASSEMBLY TO SQLCLRTestLogin ;  
GO  
```  
  
 <span data-ttu-id="fda8d-147">Para especificar que un ensamblado se cargue con el permiso `UNSAFE`, debe especificar el conjunto de permisos `UNSAFE` al cargar el ensamblado en el servidor:</span><span class="sxs-lookup"><span data-stu-id="fda8d-147">To specify that an assembly loads with `UNSAFE` permission, you specify the `UNSAFE` permission set when loading the assembly into the server:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = UNSAFE;  
```  
  
 <span data-ttu-id="fda8d-148">Para obtener más información sobre los permisos de cada configuración, vea [CLR Integration Security](../security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="fda8d-148">For more details about the permissions for each of the settings, see [CLR Integration Security](../security/clr-integration-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda8d-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fda8d-149">See Also</span></span>  
 <span data-ttu-id="fda8d-150">[Administrar ensamblados de integración CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="fda8d-150">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="fda8d-151">[Modificar un ensamblado](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="fda8d-151">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="fda8d-152">[Quitar un ensamblado](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="fda8d-152">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 <span data-ttu-id="fda8d-153">[Seguridad de acceso del código de integración CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="fda8d-153">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="fda8d-154">[Propiedad de base de datos TRUSTWORTHY](../../security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="fda8d-154">[TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="fda8d-155">Permitir llamadores de confianza parcial</span><span class="sxs-lookup"><span data-stu-id="fda8d-155">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
  
