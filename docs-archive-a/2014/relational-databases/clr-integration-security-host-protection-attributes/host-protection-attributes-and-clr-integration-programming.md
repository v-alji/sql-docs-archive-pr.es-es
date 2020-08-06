---
title: Atributos de protección del host y programación de la integración CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- HostProtectionAttribute [CLR integration]
- common language runtime [SQL Server], host protection attributes
- disallowed types and members [CLR integration]
- common language runtime [SQL Server], disallowed types and members
- HPAs [CLR integration]
ms.assetid: 268078df-63ca-4c03-a8e7-7108bcea9697
author: rothja
ms.author: jroth
ms.openlocfilehash: 16ca1e4734e66b0eca85523764739e8f8b32634a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747640"
---
# <a name="host-protection-attributes-and-clr-integration-programming"></a><span data-ttu-id="44fe7-102">Atributos de protección del host y programación de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="44fe7-102">Host Protection Attributes and CLR Integration Programming</span></span>
  <span data-ttu-id="44fe7-103">El Common Language Runtime (CLR) proporciona un mecanismo para anotar interfaces de programación de aplicaciones (API) administradas que forman parte del .NET Framework con ciertos atributos que pueden ser de interés para un host del CLR, como [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], que se inició con [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44fe7-103">The common language runtime (CLR) provides a mechanism to annotate managed application programming interfaces (APIs) that are part of the .NET Framework with certain attributes that may be of interest to a host of the CLR, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="44fe7-104">Los ejemplos de estos atributos de protección del host (HPA) incluyen:</span><span class="sxs-lookup"><span data-stu-id="44fe7-104">Examples of such host protection attributes (HPAs) include:</span></span>  
  
-   <span data-ttu-id="44fe7-105">`SharedState`, que indica si la API expone la capacidad para crear o administrar el estado compartido (por ejemplo, campos clase estática).</span><span class="sxs-lookup"><span data-stu-id="44fe7-105">`SharedState`, which indicates whether the API exposes the ability to create or manage shared state (for example, static class fields).</span></span>  
  
-   <span data-ttu-id="44fe7-106">`Synchronization`, que indica si la API expone la capacidad de realizar la sincronización entre los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="44fe7-106">`Synchronization`, which indicates whether the API exposes the ability to perform synchronization between threads.</span></span>  
  
-   <span data-ttu-id="44fe7-107">`ExternalProcessMgmt`, que indica si la API expone una manera de controlar el proceso de host.</span><span class="sxs-lookup"><span data-stu-id="44fe7-107">`ExternalProcessMgmt`, which indicates whether the API exposes a way to control the host process.</span></span>  
  
 <span data-ttu-id="44fe7-108">Al proporcionar estos atributos, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especifica una lista de los HPA que no se permiten en el entorno hospedado a través de la seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="44fe7-108">Given these attributes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specifies a list of HPAs that are disallowed in the hosted environment through code access security (CAS).</span></span> <span data-ttu-id="44fe7-109">Los requisitos de CAS se especifican mediante uno de los tres conjuntos de permisos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: `SAFE`, `EXTERNAL_ACCESS` o `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="44fe7-109">The CAS requirements are specified by one of three [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission sets: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="44fe7-110">Uno de estos tres niveles de seguridad se especifica cuando el ensamblado se registra en el servidor mediante la instrucción `CREATE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="44fe7-110">One of these three security levels is specified when the assembly is registered on the server, using the `CREATE ASSEMBLY` statement.</span></span> <span data-ttu-id="44fe7-111">La ejecución de códigos desde los conjuntos de permiso `SAFE` o `EXTERNAL_ACCESS` debe evitar ciertos tipos o miembros que tienen aplicado el atributo `System.Security.Permissions.HostProtectionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="44fe7-111">Code executing within the `SAFE` or `EXTERNAL_ACCESS` permission sets must avoid certain types or members that have the `System.Security.Permissions.HostProtectionAttribute` attribute applied.</span></span> <span data-ttu-id="44fe7-112">Para obtener más información, vea [crear un ensamblado](../clr-integration/assemblies/creating-an-assembly.md) y restricciones del modelo de programación de la [integración CLR](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="44fe7-112">For more information, see [Creating an Assembly](../clr-integration/assemblies/creating-an-assembly.md) and [CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span></span>  
  
 <span data-ttu-id="44fe7-113">El atributo `HostProtectionAttribute` no es tanto un permiso de seguridad como una manera de mejorar la confiabilidad, en cuanto a que identifica construcciones de código específicas, bien sean tipos o métodos, que pueden no estar permitidas por el host.</span><span class="sxs-lookup"><span data-stu-id="44fe7-113">The `HostProtectionAttribute` is not a security permission as much as a way to improve reliability, in that it identifies specific code constructs, either types or methods, that the host may disallow.</span></span> <span data-ttu-id="44fe7-114">El uso del atributo `HostProtectionAttribute` exige un modelo de programación de ayuda para proteger la estabilidad del host.</span><span class="sxs-lookup"><span data-stu-id="44fe7-114">The use of the `HostProtectionAttribute` enforces a programming model that helps protect the stability of the host.</span></span>  
  
## <a name="host-protection-attributes"></a><span data-ttu-id="44fe7-115">Atributos de protección del host</span><span class="sxs-lookup"><span data-stu-id="44fe7-115">Host Protection Attributes</span></span>  
 <span data-ttu-id="44fe7-116">Los HPA identifican los tipos o miembros que no se ajustan al modelo de programación del host y representan los siguientes niveles crecientes de amenaza de confiabilidad:</span><span class="sxs-lookup"><span data-stu-id="44fe7-116">HPAs identify types or members that do not fit the host programming model and represent the following increasing levels of reliability threat:</span></span>  
  
-   <span data-ttu-id="44fe7-117">En caso contrario son favorables.</span><span class="sxs-lookup"><span data-stu-id="44fe7-117">Are otherwise benign.</span></span>  
  
-   <span data-ttu-id="44fe7-118">Podrían provocar la desestabilización del código de usuario administrado por servidor.</span><span class="sxs-lookup"><span data-stu-id="44fe7-118">Could lead to destabilization of server-managed user code.</span></span>  
  
-   <span data-ttu-id="44fe7-119">Podría provocar la desestabilización del propio proceso de servidor.</span><span class="sxs-lookup"><span data-stu-id="44fe7-119">Could lead to destabilization of the server process itself.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="44fe7-120">no permite el uso de un tipo o miembro que tenga un `HostProtectionAttribute` que especifique una `System.Security.Permissions.HostProtectionResource` enumeración con un valor de `ExternalProcessMgmt` , `ExternalThreading` , `MayLeakOnAbort` , `SecurityInfrastructure` , `SelfAffectingProcessMgmnt` , `SelfAffectingThreading` , `SharedState` , `Synchronization` o `UI` .</span><span class="sxs-lookup"><span data-stu-id="44fe7-120">disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, `SharedState`, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="44fe7-121">De esta forma, se evita que los ensamblados llamen a miembros que habiliten el estado compartido, ejecuten la sincronización, puedan causar una pérdida de recursos al terminar o afecten la integridad de los procesos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44fe7-121">This prevents the assemblies from calling members that enable sharing state, perform synchronization, might cause a resource leak on termination, or affect the integrity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="disallowed-types-and-members"></a><span data-ttu-id="44fe7-122">Tipos y miembros no permitidos</span><span class="sxs-lookup"><span data-stu-id="44fe7-122">Disallowed Types and Members</span></span>  
 <span data-ttu-id="44fe7-123">En los temas siguientes se identifican los tipos y miembros cuyos valores `HostProtectionResource` no se permiten en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44fe7-123">The following topics identify types and members whose `HostProtectionResource` values are disallowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44fe7-124">Las listas de estos temas se generaron a partir de los ensamblados admitidos.</span><span class="sxs-lookup"><span data-stu-id="44fe7-124">The lists in these topics were generated from the supported assemblies.</span></span>  <span data-ttu-id="44fe7-125">Para obtener más información, consulte [supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="44fe7-125">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44fe7-126">En esta sección</span><span class="sxs-lookup"><span data-stu-id="44fe7-126">In This Section</span></span>  
 [<span data-ttu-id="44fe7-127">Miembros y tipos no permitidos en Microsoft.VisualBasic.dll</span><span class="sxs-lookup"><span data-stu-id="44fe7-127">Disallowed Types and Members in Microsoft.VisualBasic.dll</span></span>](disallowed-types-and-members-in-microsoft-visualbasic-dll.md)  
 <span data-ttu-id="44fe7-128">Enumera los tipos y miembros de Microsoft.VisualBasic.dll cuyos valores de HPA no se permiten.</span><span class="sxs-lookup"><span data-stu-id="44fe7-128">Lists the types and members in Microsoft.VisualBasic.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="44fe7-129">Miembros y tipos no permitidos en mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="44fe7-129">Disallowed Types and Members in mscorlib.dll</span></span>](disallowed-types-and-members-in-mscorlib-dll.md)  
 <span data-ttu-id="44fe7-130">Enumera los tipos y miembros en mscorlib.dll cuyos valores HPA no se permiten.</span><span class="sxs-lookup"><span data-stu-id="44fe7-130">Lists the types and members in mscorlib.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="44fe7-131">Tipos y miembros no permitidos en System.dll</span><span class="sxs-lookup"><span data-stu-id="44fe7-131">Disallowed Types and Members in System.dll</span></span>](disallowed-types-and-members-in-system-dll.md)  
 <span data-ttu-id="44fe7-132">Enumera los tipos y miembros en System.dll cuyos valores HPA no se permiten.</span><span class="sxs-lookup"><span data-stu-id="44fe7-132">Lists the types and members in System.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="44fe7-133">Tipos y miembros no permitidos en System.Data.dll</span><span class="sxs-lookup"><span data-stu-id="44fe7-133">Disallowed Types and Members in System.Data.dll</span></span>](disallowed-types-and-members-in-system-data-dll.md)  
 <span data-ttu-id="44fe7-134">Enumera los tipos y miembros en System.Data.dll cuyos valores HPA no se permiten.</span><span class="sxs-lookup"><span data-stu-id="44fe7-134">Lists the types and members in System.Data.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="44fe7-135">Tipos y miembros no permitidos en System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="44fe7-135">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
 <span data-ttu-id="44fe7-136">Enumera los tipos y miembros en System.Core.dll cuyos valores HPA no se permiten.</span><span class="sxs-lookup"><span data-stu-id="44fe7-136">Lists the types and members in System.Core.dll whose HPA values are disallowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44fe7-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44fe7-137">See Also</span></span>  
 <span data-ttu-id="44fe7-138">[Seguridad de acceso del código de integración CLR](../clr-integration/security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="44fe7-138">[CLR Integration Code Access Security](../clr-integration/security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="44fe7-139">[Restricciones del modelo de programación de la integración CLR](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span><span class="sxs-lookup"><span data-stu-id="44fe7-139">[CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span></span>  
 [<span data-ttu-id="44fe7-140">Crear un ensamblado</span><span class="sxs-lookup"><span data-stu-id="44fe7-140">Creating an Assembly</span></span>](../clr-integration/assemblies/creating-an-assembly.md)  
  
  
