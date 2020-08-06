---
title: Ensamblados (Motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration]
- assemblies [CLR integration], about assemblies
- managed code [SQL Server], assemblies
ms.assetid: 4b146437-3061-47f6-9e8c-26eeea10b54e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7edb18ccfa9954fe52093f87948f956c2eacc1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747639"
---
# <a name="assemblies-database-engine"></a><span data-ttu-id="7ec5f-102">Ensamblados (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="7ec5f-102">Assemblies (Database Engine)</span></span>
  <span data-ttu-id="7ec5f-103">En los temas de esta sección se ofrece información que le ayudará a comprender, diseñar e implementar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-103">The topics in this section provide information to help you understand, design, and implement assemblies.</span></span>  
  
 <span data-ttu-id="7ec5f-104">Los ensamblados son archivos DLL que se utilizan en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para implementar funciones, procedimientos almacenados, desencadenadores, agregados definidos por el usuario y tipos definidos por el usuario que se escriben en uno de los lenguajes de código administrado hospedados por el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR), en lugar de en [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ec5f-104">Assemblies are DLL files used in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime (CLR), instead of in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7ec5f-105">Un ensamblado en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] es un objeto que hace referencia a un módulo de aplicación administrada (archivo .dll) creado en [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-105">An assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is an object that references a managed application module (.dll file) that was created in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime.</span></span> <span data-ttu-id="7ec5f-106">Un ensamblado contiene metadatos de clase y código administrado.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-106">An assembly contains class metadata and managed code.</span></span> <span data-ttu-id="7ec5f-107">El primer paso para crear los siguientes objetos de base de datos es cargar un ensamblado en una instancia de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="7ec5f-107">Uploading an assembly to an instance of SQL Server is the first step toward creating any of the following database objects:</span></span>  
  
-   <span data-ttu-id="7ec5f-108">Funciones CLR.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-108">CLR functions.</span></span> <span data-ttu-id="7ec5f-109">Para obtener más información, vea [Create CLR Functions](../user-defined-functions/create-clr-functions.md).</span><span class="sxs-lookup"><span data-stu-id="7ec5f-109">For more information, see [Create CLR Functions](../user-defined-functions/create-clr-functions.md).</span></span>  
  
-   <span data-ttu-id="7ec5f-110">Procedimientos almacenados CLR.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-110">CLR stored procedures.</span></span> <span data-ttu-id="7ec5f-111">Para obtener más información, vea [procedimientos almacenados CLR](../../database-engine/dev-guide/clr-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7ec5f-111">For more information, see [CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md).</span></span>  
  
-   <span data-ttu-id="7ec5f-112">Desencadenadores CLR.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-112">CLR triggers.</span></span> <span data-ttu-id="7ec5f-113">Para obtener más información, vea [crear desencadenadores CLR](../triggers/create-clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="7ec5f-113">For more information, see [Create CLR Triggers](../triggers/create-clr-triggers.md).</span></span>  
  
-   <span data-ttu-id="7ec5f-114">Funciones de agregado definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-114">User-defined aggregate functions.</span></span> <span data-ttu-id="7ec5f-115">Para obtener más información, consulte [crear agregados definidos por el usuario](../user-defined-functions/create-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="7ec5f-115">For more information, see [Create User-defined Aggregates](../user-defined-functions/create-user-defined-aggregates.md).</span></span>  
  
-   <span data-ttu-id="7ec5f-116">Tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-116">User-defined types.</span></span> <span data-ttu-id="7ec5f-117">Para obtener más información, vea [Tipos definidos por el usuario de CLR](../native-client/features/using-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="7ec5f-117">For more information, see [Using User-Defined Types](../native-client/features/using-user-defined-types.md).</span></span>  
  
 <span data-ttu-id="7ec5f-118">Los ensamblados realizan las funciones siguientes en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7ec5f-118">Assemblies perform the following functions in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="7ec5f-119">Contienen el código administrado que ejecuta la funcionalidad de uno o más de los objetos de base de datos CLR antes mencionados.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-119">Contain the managed code that runs the functionality of one or more of the CLR database objects previously listed.</span></span>  
  
-   <span data-ttu-id="7ec5f-120">Contienen metadatos que incluyen el número de versión y la referencia cultural del ensamblado, una clave pública opcional que identifica de manera única la lista de clases del ensamblado, los métodos definidos en el ensamblado y la arquitectura de procesador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-120">Contain metadata that includes the version number and culture of the assembly, an optional public key that uniquely identifies the list of classes of the assembly, the methods that are defined in the assembly, and the processor architecture of the assembly.</span></span>  
  
-   <span data-ttu-id="7ec5f-121">Administran el grado en el que el código administrado puede tener acceso a los recursos externos mediante la regulación de los permisos de acceso a código.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-121">Manage the degree to which managed code can access outside resources by regulating code access permissions.</span></span>  
  
-   <span data-ttu-id="7ec5f-122">Contienen metadatos sobre las dependencias de otros ensamblados a los que el ensamblado hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-122">Contain metadata about dependencies on other assemblies that are referenced by the assembly.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ec5f-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7ec5f-123">In This Section</span></span>  
  
|<span data-ttu-id="7ec5f-124">Tema</span><span class="sxs-lookup"><span data-stu-id="7ec5f-124">Topic</span></span>|<span data-ttu-id="7ec5f-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ec5f-125">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7ec5f-126">Diseñar ensamblados</span><span class="sxs-lookup"><span data-stu-id="7ec5f-126">Designing Assemblies</span></span>](assemblies-designing.md)|<span data-ttu-id="7ec5f-127">Explica las consideraciones previas a la creación de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-127">Explains what you have to consider before creating an assembly.</span></span> <span data-ttu-id="7ec5f-128">Se incluyen el empaquetado de los ensamblados, los permisos de acceso a código y otras restricciones.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-128">This includes packaging assemblies, code access permissions, and other restrictions.</span></span>|  
|[<span data-ttu-id="7ec5f-129">Implementar ensamblados</span><span class="sxs-lookup"><span data-stu-id="7ec5f-129">Implementing Assemblies</span></span>](assemblies-implementing.md)|<span data-ttu-id="7ec5f-130">Se explica cómo crear y quitar ensamblados, cómo y cuándo se pueden modificar y cómo se recuperan los metadatos sobre los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-130">Explains how to create and drop assemblies, how and when to modify assemblies, and how to retrieve metadata about assemblies.</span></span>|  
|[<span data-ttu-id="7ec5f-131">Obtener información acerca de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="7ec5f-131">Getting Information About Assemblies</span></span>](assemblies-getting-information.md)|<span data-ttu-id="7ec5f-132">Enumera las vistas de catálogo y las funciones que se pueden utilizar para consultar metadatos sobre ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7ec5f-132">Lists the catalog views and functions that can be queried for metadata about assemblies.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ec5f-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ec5f-133">See Also</span></span>  
 [<span data-ttu-id="7ec5f-134">Conceptos de programación en el ámbito de la integración de Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="7ec5f-134">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
