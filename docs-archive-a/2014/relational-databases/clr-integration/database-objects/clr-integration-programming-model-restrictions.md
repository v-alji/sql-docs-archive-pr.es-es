---
title: Restricciones del modelo de programación de la integración CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], programming model restrictions
- assemblies [CLR integration], CREATE ASSEMBLY checks
- programming model restrictions [CLR integration]
- assemblies [CLR integration], runtime checks
ms.assetid: 2446afc2-9d21-42d3-9847-7733d3074de9
author: rothja
ms.author: jroth
ms.openlocfilehash: 01a32e1460ad9c49061b39b1bdc419c7cd2f1342
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662099"
---
# <a name="clr-integration-programming-model-restrictions"></a><span data-ttu-id="8bca5-102">Restricciones del modelo de programación de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="8bca5-102">CLR Integration Programming Model Restrictions</span></span>
  <span data-ttu-id="8bca5-103">Al compilar un procedimiento almacenado administrado u otro objeto de base de datos administrado, algunas comprobaciones de código realizadas por [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] realiza comprobaciones en el ensamblado de código administrado cuando se registra por primera vez en la base de datos, mediante la `CREATE ASSEMBLY` instrucción y también en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8bca5-103">When you are building a managed stored procedure or other managed database object, there are certain code checks performed by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs checks on the managed code assembly when it is first registered in the database, using the `CREATE ASSEMBLY` statement, and also at runtime.</span></span> <span data-ttu-id="8bca5-104">El código administrado también se comprueba en tiempo de ejecución porque en un ensamblado puede haber rutas de acceso al código que nunca se hayan alcanzado realmente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8bca5-104">The managed code is also checked at runtime because in an assembly there may be code paths that may never actually be reached at runtime.</span></span>  <span data-ttu-id="8bca5-105">Esto proporciona flexibilidad para registrar ensamblados de terceros, de manera especial, de forma que no se debe bloquear un ensamblado donde haya un código 'no seguro' diseñado para que se ejecute en un entorno cliente pero nunca se ejecutaría en el CLR hospedado.</span><span class="sxs-lookup"><span data-stu-id="8bca5-105">This provides flexibility for registering third party assemblies, especially, so that an assembly wouldn't be blocked where there is 'unsafe' code designed to run in a client environment but would never be executed in the hosted CLR.</span></span> <span data-ttu-id="8bca5-106">Los requisitos que debe cumplir el código administrado dependen de si el ensamblado está registrado como `SAFE` , `EXTERNAL_ACCESS` o `UNSAFE` , `SAFE` siendo el más estricto y se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="8bca5-106">The requirements that the managed code must meet depend on whether the assembly is registered as `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`, `SAFE` being the strictest, and are listed below.</span></span>  
  
 <span data-ttu-id="8bca5-107">Además de las restricciones que se ubican en los ensamblados de código administrado, también hay permisos de seguridad de código que se conceden.</span><span class="sxs-lookup"><span data-stu-id="8bca5-107">In addition to restrictions being placed on the managed code assemblies, there are also code security permissions that are granted.</span></span> <span data-ttu-id="8bca5-108">Common Language Runtime (CLR) admite un modelo de seguridad denominado seguridad de acceso del código (CAS) para el código administrado.</span><span class="sxs-lookup"><span data-stu-id="8bca5-108">The common language runtime (CLR) supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="8bca5-109">En este modelo, se conceden permisos a los ensamblados basados en la identidad del código.</span><span class="sxs-lookup"><span data-stu-id="8bca5-109">In this model, permissions are granted to assemblies based on the identity of the code.</span></span> <span data-ttu-id="8bca5-110">Los ensamblados `SAFE`, `EXTERNAL_ACCESS` y `UNSAFE` tienen permisos de CAS diferentes.</span><span class="sxs-lookup"><span data-stu-id="8bca5-110">`SAFE`, `EXTERNAL_ACCESS`, and `UNSAFE` assemblies have different CAS permissions.</span></span> <span data-ttu-id="8bca5-111">Para obtener más información, vea [seguridad de acceso del código de integración CLR](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="8bca5-111">For more information, see [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="create-assembly-checks"></a><span data-ttu-id="8bca5-112">Comprobaciones de CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="8bca5-112">CREATE ASSEMBLY Checks</span></span>  
 <span data-ttu-id="8bca5-113">Cuando se ejecuta la instrucción `CREATE ASSEMBLY` las comprobaciones siguientes se realizan para cada nivel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8bca5-113">When the `CREATE ASSEMBLY` statement is run, the following checks are performed for each security level.</span></span>  <span data-ttu-id="8bca5-114">Si se produce un error en cualquier comprobación, se producirá un error en `CREATE ASSEMBLY` con un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="8bca5-114">If any check fails, `CREATE ASSEMBLY` will fail with an error message.</span></span>  
  
### <a name="global-any-security-level"></a><span data-ttu-id="8bca5-115">Global (cualquier nivel de seguridad)</span><span class="sxs-lookup"><span data-stu-id="8bca5-115">Global (any security level)</span></span>  
 <span data-ttu-id="8bca5-116">Todos los ensamblados a los que se hace referencia deben cumplir uno o más de los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bca5-116">All referenced assemblies must meet one or more of the following criteria:</span></span>  
  
-   <span data-ttu-id="8bca5-117">El ensamblado ya está registrado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8bca5-117">The assembly is already registered in the database.</span></span>  
  
-   <span data-ttu-id="8bca5-118">El ensamblado es uno de los ensamblados compatibles.</span><span class="sxs-lookup"><span data-stu-id="8bca5-118">The assembly is one of the supported assemblies.</span></span> <span data-ttu-id="8bca5-119">Para obtener más información, consulte [supported .NET Framework Libraries](supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="8bca5-119">For more information, see [Supported .NET Framework Libraries](supported-net-framework-libraries.md).</span></span>  
  
-   <span data-ttu-id="8bca5-120">Está utilizando `CREATE ASSEMBLY FROM` \* \<location> ,\* y todos los ensamblados a los que se hace referencia y sus dependencias están disponibles en *\<location>* .</span><span class="sxs-lookup"><span data-stu-id="8bca5-120">You are using `CREATE ASSEMBLY FROM`*\<location>,* and all the referenced assemblies and their dependencies are available in *\<location>*.</span></span>  
  
-   <span data-ttu-id="8bca5-121">Está usando `CREATE ASSEMBLY FROM` \* \<bytes ...> \* y todas las referencias se especifican mediante bytes separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="8bca5-121">You are using `CREATE ASSEMBLY FROM`*\<bytes ...>,* and all the references are specified via space separated bytes.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="8bca5-122">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="8bca5-122">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="8bca5-123">Todos los ensamblados `EXTERNAL_ACCESS` deben cumplir los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bca5-123">All `EXTERNAL_ACCESS` assemblies must meet the following criteria:</span></span>  
  
-   <span data-ttu-id="8bca5-124">Los campos estáticos no se usan para almacenar información.</span><span class="sxs-lookup"><span data-stu-id="8bca5-124">Static fields are not used to store information.</span></span> <span data-ttu-id="8bca5-125">Se permiten los campos estáticos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8bca5-125">Read-only static fields are allowed.</span></span>  
  
-   <span data-ttu-id="8bca5-126">Se pasa la prueba PEVerify.</span><span class="sxs-lookup"><span data-stu-id="8bca5-126">PEVerify test is passed.</span></span> <span data-ttu-id="8bca5-127">La herramienta PEVerify (peverify.exe), que comprueba que el código MSIL y los metadatos asociados cumplen los requisitos de seguridad de tipos, se proporciona con .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="8bca5-127">The PEVerify tool (peverify.exe), which checks that the MSIL code and associated metadata meet type safety requirements, is provided with the .NET Framework SDK.</span></span>  
  
-   <span data-ttu-id="8bca5-128">La sincronización, por ejemplo no se usa con la clase `SynchronizationAttribute`.</span><span class="sxs-lookup"><span data-stu-id="8bca5-128">Synchronization, for example with the `SynchronizationAttribute` class, is not used.</span></span>  
  
-   <span data-ttu-id="8bca5-129">No se usan métodos de finalizador.</span><span class="sxs-lookup"><span data-stu-id="8bca5-129">Finalizer methods are not used.</span></span>  
  
 <span data-ttu-id="8bca5-130">Los atributos personalizados siguientes no se permiten en ensamblados `EXTERNAL_ACCESS`:</span><span class="sxs-lookup"><span data-stu-id="8bca5-130">The following custom attributes are disallowed in `EXTERNAL_ACCESS` assemblies:</span></span>  
  
-   <span data-ttu-id="8bca5-131">System.ContextStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-131">System.ContextStaticAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-132">System.MTAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-132">System.MTAThreadAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-133">System.Runtime.CompilerServices.MethodImplAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-133">System.Runtime.CompilerServices.MethodImplAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-135">System.Runtime.Remoting.Contexts.ContextAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-135">System.Runtime.Remoting.Contexts.ContextAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-137">System.Runtime.InteropServices.DllImportAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-137">System.Runtime.InteropServices.DllImportAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-138">System.Security.Permissions.CodeAccessSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-138">System.Security.Permissions.CodeAccessSecurityAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-140">System.Security.UnverifiableCodeAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-140">System.Security.UnverifiableCodeAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-141">System.STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-141">System.STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="8bca5-142">System.ThreadStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="8bca5-142">System.ThreadStaticAttribute</span></span>  
  
### <a name="safe"></a><span data-ttu-id="8bca5-143">SAFE</span><span class="sxs-lookup"><span data-stu-id="8bca5-143">SAFE</span></span>  
  
-   <span data-ttu-id="8bca5-144">Se comprueban todas las condiciones del ensamblado `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="8bca5-144">All `EXTERNAL_ACCESS` assembly conditions are checked.</span></span>  
  
## <a name="runtime-checks"></a><span data-ttu-id="8bca5-145">Comprobaciones en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8bca5-145">Runtime Checks</span></span>  
 <span data-ttu-id="8bca5-146">En tiempo de ejecución, el ensamblado de código se comprueba para las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="8bca5-146">At runtime, the code assembly is checked for the following conditions.</span></span> <span data-ttu-id="8bca5-147">Si se encuentra cualquiera de estas condiciones, el código administrado no se puede ejecutar y se iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="8bca5-147">If any of these conditions are found, the managed code will not be allowed to run and an exception will be thrown.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="8bca5-148">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="8bca5-148">UNSAFE</span></span>  
 <span data-ttu-id="8bca5-149">La carga de un ensamblado, ya sea explícitamente llamando al `System.Reflection.Assembly.Load()` método desde una matriz de bytes o implícitamente a través del uso del `Reflection.Emit` espacio de nombres, no se permite.</span><span class="sxs-lookup"><span data-stu-id="8bca5-149">Loading an assembly-either explicitly by calling the `System.Reflection.Assembly.Load()` method from a byte array, or implicitly through the use of `Reflection.Emit` namespace-is not permitted.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="8bca5-150">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="8bca5-150">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="8bca5-151">Se comprueban todas las condiciones `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="8bca5-151">All `UNSAFE` conditions are checked.</span></span>  
  
 <span data-ttu-id="8bca5-152">Todos los tipos y métodos anotados con los siguientes valores de atributo de protección de host (HPA) en la lista compatible de ensamblados no están admitidos.</span><span class="sxs-lookup"><span data-stu-id="8bca5-152">All types and methods annotated with the following host protection attribute (HPA) values in the supported list of assemblies are disallowed.</span></span>  
  
-   <span data-ttu-id="8bca5-153">SelfAffectingProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="8bca5-153">SelfAffectingProcessMgmt</span></span>  
  
-   <span data-ttu-id="8bca5-154">SelfAffectingThreading</span><span class="sxs-lookup"><span data-stu-id="8bca5-154">SelfAffectingThreading</span></span>  
  
-   <span data-ttu-id="8bca5-155">Sincronización</span><span class="sxs-lookup"><span data-stu-id="8bca5-155">Synchronization</span></span>  
  
-   <span data-ttu-id="8bca5-156">SharedState</span><span class="sxs-lookup"><span data-stu-id="8bca5-156">SharedState</span></span>  
  
-   <span data-ttu-id="8bca5-157">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="8bca5-157">ExternalProcessMgmt</span></span>  
  
-   <span data-ttu-id="8bca5-158">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="8bca5-158">ExternalThreading</span></span>  
  
-   <span data-ttu-id="8bca5-159">SecurityInfrastructure</span><span class="sxs-lookup"><span data-stu-id="8bca5-159">SecurityInfrastructure</span></span>  
  
-   <span data-ttu-id="8bca5-160">MayLeakOnAbort</span><span class="sxs-lookup"><span data-stu-id="8bca5-160">MayLeakOnAbort</span></span>  
  
-   <span data-ttu-id="8bca5-161">IU</span><span class="sxs-lookup"><span data-stu-id="8bca5-161">UI</span></span>  
  
 <span data-ttu-id="8bca5-162">Para obtener más información sobre hPa y una lista de tipos y miembros no permitidos en los ensamblados admitidos, vea [atributos de protección del host y programación de la integración CLR](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span><span class="sxs-lookup"><span data-stu-id="8bca5-162">For more information about HPAs and a list of disallowed types and members in the supported assemblies, see [Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span></span>  
  
### <a name="safe"></a><span data-ttu-id="8bca5-163">SAFE</span><span class="sxs-lookup"><span data-stu-id="8bca5-163">SAFE</span></span>  
 <span data-ttu-id="8bca5-164">Se comprueban todas las condiciones `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="8bca5-164">All `EXTERNAL_ACCESS` conditions are checked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bca5-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bca5-165">See Also</span></span>  
 <span data-ttu-id="8bca5-166">[Bibliotecas de .NET Framework compatibles](supported-net-framework-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="8bca5-166">[Supported .NET Framework Libraries](supported-net-framework-libraries.md) </span></span>  
 <span data-ttu-id="8bca5-167">[Seguridad de acceso del código de integración CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="8bca5-167">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="8bca5-168">[Atributos de protección del host y programación de la integración CLR](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="8bca5-168">[Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 [<span data-ttu-id="8bca5-169">Crear un ensamblado</span><span class="sxs-lookup"><span data-stu-id="8bca5-169">Creating an Assembly</span></span>](../assemblies/creating-an-assembly.md)  
  
  
