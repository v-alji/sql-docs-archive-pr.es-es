---
title: Seguridad de la integración CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- authorization [CLR integration]
- common language runtime [SQL Server], security
- database objects [CLR integration], security
ms.assetid: 05d7a471-c5d5-4730-b903-e4edc8157bb4
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d99d32a061d8fe78a8ac3642a503cceb45f3809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671578"
---
# <a name="clr-integration-security"></a><span data-ttu-id="31fb8-102">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="31fb8-102">CLR Integration Security</span></span>
  <span data-ttu-id="31fb8-103">El modelo de seguridad del [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR) administra y protege el acceso entre los distintos tipos de objetos CLR y no CLR que se ejecutan dentro de [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] la instrucción u otro objeto CLR que se ejecuta en el servidor.</span><span class="sxs-lookup"><span data-stu-id="31fb8-103">The security model of the [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] statement or another CLR object running in the server.</span></span> <span data-ttu-id="31fb8-104">Las llamadas entre objetos reciben el nombre de vínculos.</span><span class="sxs-lookup"><span data-stu-id="31fb8-104">The calls between objects are referred to as links.</span></span> <span data-ttu-id="31fb8-105">Los tipos de comprobaciones de seguridad que se realizan en estos objetos dependen de los tipos de vínculos implicados.</span><span class="sxs-lookup"><span data-stu-id="31fb8-105">The types of security checks performed on these objects depend on the types of links involved.</span></span>  
  
 <span data-ttu-id="31fb8-106">El modelo de seguridad de la integración CLR tiene estos objetivos:</span><span class="sxs-lookup"><span data-stu-id="31fb8-106">The CLR integration security model has the following goals:</span></span>  
  
-   <span data-ttu-id="31fb8-107">De forma predeterminada, la ejecución de código de usuario administrado en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31fb8-107">By default, running managed user code on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="31fb8-108">La realización de operaciones que podrían poner en peligro la estabilidad de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] debería protegerse mediante los permisos de alto nivel pertinentes.</span><span class="sxs-lookup"><span data-stu-id="31fb8-108">Performing operations that potentially compromise the robustness of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should be protected by appropriate high-level permissions.</span></span>  
  
-   <span data-ttu-id="31fb8-109">El código de usuario administrado no debería obtener un acceso no autorizado a los datos del usuario ni a ningún otro código de usuario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="31fb8-109">Managed user code should not gain unauthorized access to user data or other user code in the database.</span></span> <span data-ttu-id="31fb8-110">El código definido por el usuario debería ejecutarse bajo el contexto de seguridad de la sesión del usuario que lo invocó y con los privilegios adecuados para ese contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="31fb8-110">User-defined code should run under the security context of the user-session that invoked it, and with the correct privileges for that security context.</span></span>  
  
-   <span data-ttu-id="31fb8-111">Debería haber controles que restringiesen el acceso del código de usuario a cualquier recurso situado fuera del servidor, y utilizarlo única y exclusivamente para el acceso a datos local y la realización de cálculos.</span><span class="sxs-lookup"><span data-stu-id="31fb8-111">There should be controls for restricting user code from accessing any resources outside the server, using it strictly for local data access and computation.</span></span>  
  
-   <span data-ttu-id="31fb8-112">El código definido por el usuario no debería poder obtener un acceso no autorizado a los recursos del sistema por el hecho de ejecutarse en el proceso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31fb8-112">User-defined code should not be able to gain unauthorized access to system resources by virtue of running in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="31fb8-113">con el modelo de seguridad basado en el acceso del código de CLR.</span><span class="sxs-lookup"><span data-stu-id="31fb8-113">with the code access-based security model of the CLR.</span></span> <span data-ttu-id="31fb8-114">Algunas de las ventajas que este enfoque combinado ofrece para la seguridad se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="31fb8-114">Some of the advantages of this combined approach to security are discussed in this section.</span></span>  
  
 <span data-ttu-id="31fb8-115">En la siguiente tabla se muestran los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="31fb8-115">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="31fb8-116">Seguridad de acceso del código de integración CLR</span><span class="sxs-lookup"><span data-stu-id="31fb8-116">CLR Integration Code Access Security</span></span>](clr-integration-code-access-security.md)  
 <span data-ttu-id="31fb8-117">Describe el modelo de seguridad de acceso del código (CAS) para el código administrado.</span><span class="sxs-lookup"><span data-stu-id="31fb8-117">Discusses the code access security (CAS) model for managed code.</span></span>  
  
 [<span data-ttu-id="31fb8-118">Atributos de protección del host y programación de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="31fb8-118">Host Protection Attributes and CLR Integration Programming</span></span>](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md)  
 <span data-ttu-id="31fb8-119">Ofrece información sobre los valores del atributo de protección de host (HPA) que no se permiten en los ensamblados SAFE y EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="31fb8-119">Provides information about the host protection attribute (HPA) values that are disallowed in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
 [<span data-ttu-id="31fb8-120">Vínculos en el ámbito de seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="31fb8-120">Links in CLR Integration Security</span></span>](../../../database-engine/dev-guide/links-in-clr-integration-security.md)  
 <span data-ttu-id="31fb8-121">Describe la forma en que los fragmentos de código del usuario pueden llamarse entre sí en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31fb8-121">Describes how pieces of user-code can call each other in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="31fb8-122">Suplantación y seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="31fb8-122">Impersonation and CLR Integration Security</span></span>](../../../database-engine/dev-guide/impersonation-and-clr-integration-security.md)  
 <span data-ttu-id="31fb8-123">Explica la forma en que el código administrado obtiene acceso a los recursos externos utilizando la suplantación.</span><span class="sxs-lookup"><span data-stu-id="31fb8-123">Discusses how managed code accesses external resources using impersonation.</span></span>  
  
 [<span data-ttu-id="31fb8-124">Permitir llamadores de confianza parcial</span><span class="sxs-lookup"><span data-stu-id="31fb8-124">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
 <span data-ttu-id="31fb8-125">Indica los problemas que surgen cuando un método administrado invoca a un método en una clase incluida dentro de otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="31fb8-125">Discusses issues that arise when a managed method invokes a method in a class contained in another assembly.</span></span>  
  
 [<span data-ttu-id="31fb8-126">Dominios de aplicación y seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="31fb8-126">Application Domains and CLR Integration Security</span></span>](../../../database-engine/dev-guide/application-domains-and-clr-integration-security.md)  
 <span data-ttu-id="31fb8-127">Describe la forma en que los ensamblados se cargan en los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="31fb8-127">Describes how assemblies are loaded into application domains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31fb8-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31fb8-128">See Also</span></span>  
 [<span data-ttu-id="31fb8-129">Administrar ensamblados de integración CLR</span><span class="sxs-lookup"><span data-stu-id="31fb8-129">Managing CLR Integration Assemblies</span></span>](../assemblies/managing-clr-integration-assemblies.md)  
  
  
