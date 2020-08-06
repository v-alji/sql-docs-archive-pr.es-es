---
title: Diseñar ensamblados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- designing assemblies [SQL Server]
- assemblies [CLR integration], designing
ms.assetid: 9c07f706-6508-41aa-a4d7-56ce354f9061
author: rothja
ms.author: jroth
ms.openlocfilehash: 785ab80a529140a52ec18ef96ccaaeafd03698cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747637"
---
# <a name="designing-assemblies"></a><span data-ttu-id="c79d9-102">Diseñar ensamblados</span><span class="sxs-lookup"><span data-stu-id="c79d9-102">Designing Assemblies</span></span>
  <span data-ttu-id="c79d9-103">En este tema se describen los siguientes aspectos que se deben tener en cuenta al diseñar ensamblados:</span><span class="sxs-lookup"><span data-stu-id="c79d9-103">This topic describes the following factors you should consider when you design assemblies:</span></span>  
  
-   <span data-ttu-id="c79d9-104">Empaquetar ensamblados</span><span class="sxs-lookup"><span data-stu-id="c79d9-104">Packaging assemblies</span></span>  
  
-   <span data-ttu-id="c79d9-105">Administrar la seguridad de ensamblados</span><span class="sxs-lookup"><span data-stu-id="c79d9-105">Managing assembly security</span></span>  
  
-   <span data-ttu-id="c79d9-106">Restricciones en ensamblados</span><span class="sxs-lookup"><span data-stu-id="c79d9-106">Restrictions on assemblies</span></span>  
  
## <a name="packaging-assemblies"></a><span data-ttu-id="c79d9-107">Empaquetar ensamblados</span><span class="sxs-lookup"><span data-stu-id="c79d9-107">Packaging Assemblies</span></span>  
 <span data-ttu-id="c79d9-108">Un ensamblado puede contener funcionalidad para más de un tipo o una rutina de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en sus clases y métodos.</span><span class="sxs-lookup"><span data-stu-id="c79d9-108">An assembly can contain functionality for more than one [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] routine or type in its classes and methods.</span></span> <span data-ttu-id="c79d9-109">En la mayoría de los casos, resulta conveniente empaquetar la funcionalidad de rutinas que ejecutan funciones relacionadas dentro del mismo ensamblado, especialmente si estas rutinas comparten clases cuyos métodos se llaman unos a otros.</span><span class="sxs-lookup"><span data-stu-id="c79d9-109">Most of the time, it makes sense to package the functionality of routines that perform related functions within the same assembly, especially if these routines share classes whose methods call one another.</span></span> <span data-ttu-id="c79d9-110">Por ejemplo, las clases que efectúan tareas de administración de entradas de datos para desencadenadores de Common Language Runtime (CLR) y procedimientos almacenados de CLR se pueden empaquetar en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c79d9-110">For example, classes that perform data entry management tasks for common language runtime (CLR) triggers and CLR stored procedures can be packaged in the same assembly.</span></span> <span data-ttu-id="c79d9-111">Esto se debe a que los métodos correspondientes a estas clases tienen más probabilidad de llamarse unos a otros que los de tareas menos relacionadas.</span><span class="sxs-lookup"><span data-stu-id="c79d9-111">This is because the methods for these classes are more likely to call each other than those of less related tasks.</span></span>  
  
 <span data-ttu-id="c79d9-112">Cuando empaquete código en un ensamblado, debe tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c79d9-112">When you are packaging code into assembly, you should consider the following:</span></span>  
  
-   <span data-ttu-id="c79d9-113">Los índices y tipos definidos por el usuario CLR que dependan de funciones definidas por el usuario CLR pueden provocar que haya datos almacenados en la base de datos que dependan del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c79d9-113">CLR user-defined types and indexes that depend on CLR user-defined functions can cause persisted data to be in the database that depends on the assembly.</span></span> <span data-ttu-id="c79d9-114">Normalmente, modificar el código de un ensamblado resulta más complejo cuando hay datos almacenados que dependen del ensamblado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c79d9-114">Modifying the code of an assembly is frequently more complex when there is persisted data that depends on the assembly in the database.</span></span> <span data-ttu-id="c79d9-115">Por lo tanto, en general es mejor separar el código en el que se basan las dependencias de datos almacenados (como los tipos y los índices definidos por el usuario que utilizan funciones definidas por el usuario) del código que no tiene tales dependencias de datos almacenados.</span><span class="sxs-lookup"><span data-stu-id="c79d9-115">Therefore, it is generally better to separate code on which persisted data dependencies rely (such as user-defined types and indexes using user-defined functions) from code that does not have such persisted data dependencies.</span></span> <span data-ttu-id="c79d9-116">Para obtener más información, vea [implementar ensamblados](assemblies-implementing.md) y [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c79d9-116">For more information, see [Implementing Assemblies](assemblies-implementing.md) and [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
-   <span data-ttu-id="c79d9-117">Si parte del código administrado requiere un permiso de mayor nivel, es mejor separar ese código en un ensamblado diferente del correspondiente al código que no requiere ese nivel de permiso.</span><span class="sxs-lookup"><span data-stu-id="c79d9-117">If a piece of managed code requires higher permission, it is better to separate that code into a separate assembly from code that does not require higher permission.</span></span>  
  
## <a name="managing-assembly-security"></a><span data-ttu-id="c79d9-118">Administrar la seguridad de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="c79d9-118">Managing Assembly Security</span></span>  
 <span data-ttu-id="c79d9-119">Es posible controlar el grado de acceso de un ensamblado a los recursos protegidos mediante la seguridad de acceso del código de .NET mientras ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="c79d9-119">You can control how much an assembly can access resources protected by .NET Code Access Security when it runs managed code.</span></span> <span data-ttu-id="c79d9-120">Para ello, tiene que especificar uno de estos tres conjuntos de permisos al crear o modificar un ensamblado: SAFE, EXTERNAL_ACCESS o UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="c79d9-120">You do this by specifying one of three permission sets when you create or modify an assembly: SAFE, EXTERNAL_ACCESS, or UNSAFE.</span></span>  
  
### <a name="safe"></a><span data-ttu-id="c79d9-121">SAFE</span><span class="sxs-lookup"><span data-stu-id="c79d9-121">SAFE</span></span>  
 <span data-ttu-id="c79d9-122">SAFE es el conjunto de permisos predeterminado y es el más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="c79d9-122">SAFE is the default permission set and it is the most restrictive.</span></span> <span data-ttu-id="c79d9-123">El código ejecutado por un ensamblado con permisos SAFE no podrá tener acceso a recursos externos del sistema, como los archivos, la red, las variables de entorno o el registro.</span><span class="sxs-lookup"><span data-stu-id="c79d9-123">Code run by an assembly with SAFE permissions cannot access external system resources such as files, the network, environment variables, or the registry.</span></span> <span data-ttu-id="c79d9-124">El código SAFE puede tener acceso a datos de las bases de datos locales de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o puede ejecutar cálculos y lógica de negocios que no impliquen acceso a recursos ajenos a las bases de datos locales.</span><span class="sxs-lookup"><span data-stu-id="c79d9-124">SAFE code can access data from the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases or perform computations and business logic that do not involve accessing resources outside the local databases.</span></span>  
  
 <span data-ttu-id="c79d9-125">La mayoría de ensamblados realizan cálculos y tareas de administración de datos sin necesidad de tener acceso a recursos ajenos a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c79d9-125">Most assemblies perform computation and data management tasks without having to access resources outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c79d9-126">Por lo tanto, se recomienda SAFE como conjunto de permisos de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="c79d9-126">Therefore, we recommend SAFE as the assembly permission set.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="c79d9-127">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="c79d9-127">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="c79d9-128">EXTERNAL_ACCESS permite a los ensamblados obtener acceso a ciertos recursos externos del sistema, como los archivos, las redes, los servicios web, las variables de entorno y el registro.</span><span class="sxs-lookup"><span data-stu-id="c79d9-128">EXTERNAL_ACCESS allows for assemblies to access certain external system resources such as files, networks, Web services, environmental variables, and the registry.</span></span> <span data-ttu-id="c79d9-129">Solo los inicios de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con permisos EXTERNAL ACCESS pueden crear ensamblados con EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="c79d9-129">Only [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins with EXTERNAL ACCESS permissions can create EXTERNAL_ACCESS assemblies.</span></span>  
  
 <span data-ttu-id="c79d9-130">Los ensamblados con SAFE y EXTERNAL_ACCESS pueden incluir código con seguridad de tipos comprobable.</span><span class="sxs-lookup"><span data-stu-id="c79d9-130">SAFE and EXTERNAL_ACCESS assemblies can contain only code that is verifiably type-safe.</span></span> <span data-ttu-id="c79d9-131">Esto significa que dichos ensamblados solo tienen acceso a clases a través de puntos de entrada bien definidos que son válidos para la definición de tipos.</span><span class="sxs-lookup"><span data-stu-id="c79d9-131">This means that these assemblies can only access classes through well-defined entry points that are valid for the type definition.</span></span> <span data-ttu-id="c79d9-132">Por lo tanto, no pueden tener acceso arbitrariamente a búferes de memoria que no pertenezcan al código.</span><span class="sxs-lookup"><span data-stu-id="c79d9-132">Therefore, they cannot arbitrarily access memory buffers not owned by the code.</span></span> <span data-ttu-id="c79d9-133">Además, no pueden realizar operaciones que puedan tener un efecto adverso en la estabilidad del proceso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c79d9-133">Additionally, they cannot perform operations that might have an adverse effect on the robustness of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="c79d9-134">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="c79d9-134">UNSAFE</span></span>  
 <span data-ttu-id="c79d9-135">UNSAFE proporciona a los ensamblados un acceso sin límites a los recursos situados tanto dentro como fuera de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c79d9-135">UNSAFE gives assemblies unrestricted access to resources, both within and outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c79d9-136">El código que se ejecuta desde un ensamblado con UNSAFE puede llamar a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="c79d9-136">Code that is running from within an UNSAFE assembly can call unmanaged code.</span></span>  
  
 <span data-ttu-id="c79d9-137">Además, si se especifica UNSAFE, el código incluido en el ensamblado puede realizar operaciones que la comprobación de CLR considera sin seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="c79d9-137">Also, specifying UNSAFE allows for the code in the assembly to perform operations that are considered type-unsafe by the CLR verifier.</span></span> <span data-ttu-id="c79d9-138">Estas operaciones pueden tener acceso a búferes de memoria en el espacio del proceso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de forma incontrolada.</span><span class="sxs-lookup"><span data-stu-id="c79d9-138">These operations can potentially access memory buffers in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process space in an uncontrolled manner.</span></span> <span data-ttu-id="c79d9-139">Los ensamblados UNSAFE también pueden trastornar potencialmente el sistema de seguridad de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c79d9-139">UNSAFE assemblies can also potentially subvert the security system of either [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the common language runtime.</span></span> <span data-ttu-id="c79d9-140">Los permisos UNSAFE solo deben concederlos programadores o administradores experimentados a ensamblados de mucha confianza.</span><span class="sxs-lookup"><span data-stu-id="c79d9-140">UNSAFE permissions should be granted only to highly trusted assemblies by experienced developers or administrators.</span></span> <span data-ttu-id="c79d9-141">Solo los miembros del rol fijo de servidor **sysadmin** pueden crear ensamblados no seguros.</span><span class="sxs-lookup"><span data-stu-id="c79d9-141">Only members of the **sysadmin** fixed server role can create UNSAFE assemblies.</span></span>  
  
## <a name="restrictions-on-assemblies"></a><span data-ttu-id="c79d9-142">Restricciones en los ensamblados</span><span class="sxs-lookup"><span data-stu-id="c79d9-142">Restrictions on Assemblies</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="c79d9-143">impone ciertas restricciones en el código administrado de los ensamblados para asegurarse de que puedan ejecutarse de manera confiable y escalable.</span><span class="sxs-lookup"><span data-stu-id="c79d9-143">puts certain restrictions on managed code in assemblies to make sure that they can run in a reliable and scalable manner.</span></span> <span data-ttu-id="c79d9-144">Esto significa que, en los ensamblados con SAFE y EXTERNAL_ACCESS, no se permiten ciertas operaciones que pueden comprometer la estabilidad del servidor.</span><span class="sxs-lookup"><span data-stu-id="c79d9-144">This means that certain operations that can compromise the robustness of the server are not permitted in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
### <a name="disallowed-custom-attributes"></a><span data-ttu-id="c79d9-145">Atributos personalizados no permitidos</span><span class="sxs-lookup"><span data-stu-id="c79d9-145">Disallowed Custom Attributes</span></span>  
 <span data-ttu-id="c79d9-146">Los ensamblados no se pueden anotar con los siguientes atributos personalizados:</span><span class="sxs-lookup"><span data-stu-id="c79d9-146">Assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.ContextStaticAttribute  
System.MTAThreadAttribute  
System.Runtime.CompilerServices.MethodImplAttribute  
System.Runtime.CompilerServices.CompilationRelaxationsAttribute  
System.Runtime.Remoting.Contexts.ContextAttribute  
System.Runtime.Remoting.Contexts.SynchronizationAttribute  
System.Runtime.InteropServices.DllImportAttribute   
System.Security.Permissions.CodeAccessSecurityAttribute  
System.STAThreadAttribute  
System.ThreadStaticAttribute  
```  
  
 <span data-ttu-id="c79d9-147">Además, los ensamblados con SAFE y EXTERNAL_ACCESS no se pueden anotar con los siguientes atributos personalizados:</span><span class="sxs-lookup"><span data-stu-id="c79d9-147">Additionally, SAFE and EXTERNAL_ACCESS assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.Security.SuppressUnmanagedCodeSecurityAttribute  
System.Security.UnverifiableCodeAttribute  
```  
  
### <a name="disallowed-net-framework-apis"></a><span data-ttu-id="c79d9-148">API de .NET Framework no permitidas</span><span class="sxs-lookup"><span data-stu-id="c79d9-148">Disallowed .NET Framework APIs</span></span>  
 <span data-ttu-id="c79d9-149">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] No se puede llamar a ninguna API anotada con uno de los **HostProtectionAttributes** no permitidos desde ensamblados seguros y external_access.</span><span class="sxs-lookup"><span data-stu-id="c79d9-149">Any [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API that is annotated with one of the disallowed **HostProtectionAttributes** cannot be called from SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
```  
eSelfAffectingProcessMgmt  
eSelfAffectingThreading  
eSynchronization  
eSharedState   
eExternalProcessMgmt  
eExternalThreading  
eSecurityInfrastructure  
eMayLeakOnAbort  
eUI  
```  
  
### <a name="supported-net-framework-assemblies"></a><span data-ttu-id="c79d9-150">Ensamblados de .NET Framework admitidos</span><span class="sxs-lookup"><span data-stu-id="c79d9-150">Supported .NET Framework Assemblies</span></span>  
 <span data-ttu-id="c79d9-151">Cualquier ensamblado al que haga referencia el suyo personalizado se debe cargar en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="c79d9-151">Any assembly that is referenced by your custom assembly must be loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using CREATE ASSEMBLY.</span></span> <span data-ttu-id="c79d9-152">Los siguientes ensamblados de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] ya están cargados en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y, por lo tanto, se les puede hacer referencia mediante ensamblados personalizados sin la necesidad de utilizar CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="c79d9-152">The following [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assemblies are already loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and, therefore, can be referenced by custom assemblies without having to use CREATE ASSEMBLY.</span></span>  
  
```  
custommarshallers.dll  
Microsoft.visualbasic.dll  
Microsoft.visualc.dll  
mscorlib.dll  
system.data.dll  
System.Data.SqlXml.dll  
system.dll  
system.security.dll  
system.web.services.dll  
system.xml.dll  
System.Transactions  
System.Data.OracleClient  
System.Configuration  
```  
  
## <a name="see-also"></a><span data-ttu-id="c79d9-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c79d9-153">See Also</span></span>  
 <span data-ttu-id="c79d9-154">[Ensamblados &#40;Motor de base de datos&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="c79d9-154">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 [<span data-ttu-id="c79d9-155">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="c79d9-155">CLR Integration Security</span></span>](security/clr-integration-security.md)  
  
  
