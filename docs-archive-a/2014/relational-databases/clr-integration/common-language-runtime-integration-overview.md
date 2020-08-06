---
title: Información general sobre la integración de Common Language Runtime (CLR) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- managed code [SQL Server]
- common language runtime [SQL Server], about CLR integration
- cross-language integration
- integrating CLR [SQL Server]
- .NET Framework [SQL Server], common language runtime
- code access security [CLR integration]
- managed code [SQL Server], CLR integration
ms.assetid: 7be9e644-36a2-48fc-9206-faf59fdff4d7
author: rothja
ms.author: jroth
ms.openlocfilehash: 25345fd39fb8a77f62e4e352b75629a98cb9d7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672114"
---
# <a name="common-language-runtime-clr-integration-overview"></a><span data-ttu-id="12754-102">Información general sobre integración CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="12754-102">Common Language Runtime (CLR) Integration Overview</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="12754-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]ahora incluye la integración del componente Common Language Runtime (CLR) del .NET Framework para [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="12754-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] now features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="12754-104">El CLR proporciona código administrado con servicios como, por ejemplo, integración entre idiomas, seguridad de acceso del código, administración de la vigencia del objeto y compatibilidad con la depuración y la creación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="12754-104">The CLR supplies managed code with services such as cross-language integration, code access security, object lifetime management, and debugging and profiling support.</span></span> <span data-ttu-id="12754-105">Para los usuarios y programadores de aplicaciones de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], la integración CLR significa que ahora se pueden escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario (escalares y con valores de tabla) y funciones de agregado definidas por el usuario con cualquier lenguaje .NET Framework, incluidos [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET y [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="12754-105">For [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] users and application developers, CLR integration means that you can now write stored procedures, triggers, user-defined types, user-defined functions (scalar and table-valued), and user-defined aggregate functions using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="12754-106">incluye .NET Framework versión 4 preinstalado.</span><span class="sxs-lookup"><span data-stu-id="12754-106">includes the .NET Framework version 4 pre-installed.</span></span>  
  
 <span data-ttu-id="12754-107">Entre las ventajas principales de esta integración se encuentran las siguientes:</span><span class="sxs-lookup"><span data-stu-id="12754-107">Among the major benefits of this integration are:</span></span>  
  
-   <span data-ttu-id="12754-108">**Un mejor modelo de programación.**</span><span class="sxs-lookup"><span data-stu-id="12754-108">**A better programming model.**</span></span> <span data-ttu-id="12754-109">Los lenguajes de .NET Framework son en muchos aspectos más ricos que Transact-SQL, ya que proporcionan construcciones y funciones que antes no estaban disponibles para los desarrolladores de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12754-109">The .NET Framework languages are in many respects richer than Transact-SQL, offering constructs and capabilities previously not available to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developers.</span></span> <span data-ttu-id="12754-110">Los programadores también pueden aprovechar el potencial de la Biblioteca de .NET Framework, que proporciona un amplio conjunto de clases que se pueden utilizar de forma rápida y eficaz para solucionar problemas de programación.</span><span class="sxs-lookup"><span data-stu-id="12754-110">Developers may also leverage the power of the .NET Framework Library, which provides an extensive set of classes that can be used to quickly and efficiently solve programming problems.</span></span>  
  
-   <span data-ttu-id="12754-111">**Seguridad mejorada.**</span><span class="sxs-lookup"><span data-stu-id="12754-111">**Improved safety and security.**</span></span> <span data-ttu-id="12754-112">El código administrado se ejecuta en un entorno de Common Language Runtime, hospedado por el motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="12754-112">Managed code runs in a common language run-time environment, hosted by the Database Engine.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="12754-113">lo aprovecha para proporcionar una alternativa más segura a los procedimientos almacenados extendidos disponibles en versiones anteriores de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12754-113">leverages this to provide a safer and more secure alternative to the extended stored procedures available in earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="12754-114">**Capacidad de definir tipos de datos y funciones de agregado.**</span><span class="sxs-lookup"><span data-stu-id="12754-114">**Ability to define data types and aggregate functions.**</span></span> <span data-ttu-id="12754-115">Los tipos y agregados definidos por el usuario son dos nuevos objetos de base de datos administrados que amplían las capacidades de almacenamiento y consulta de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12754-115">User defined types and user defined aggregates are two new managed database objects which expand the storage and querying capabilities of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="12754-116">**Desarrollo mejorado gracias a un entorno normalizado.**</span><span class="sxs-lookup"><span data-stu-id="12754-116">**Streamlined development through a standardized environment.**</span></span> <span data-ttu-id="12754-117">El desarrollo de base de datos está integrado en versiones futuras del entorno de desarrollo [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="12754-117">Database development is integrated into future releases of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET development environment.</span></span> <span data-ttu-id="12754-118">Los programadores utilizan las mismas herramientas para desarrollar y depurar objetos de base de datos y scripts que las que usan para escribir componentes y servicios de .NET Framework de nivel medio o nivel de cliente.</span><span class="sxs-lookup"><span data-stu-id="12754-118">Developers use the same tools for developing and debugging database objects and scripts as they use to write middle-tier or client-tier .NET Framework components and services.</span></span>  
  
-   <span data-ttu-id="12754-119">**Potencial para un rendimiento y escalabilidad mejorados.**</span><span class="sxs-lookup"><span data-stu-id="12754-119">**Potential for improved performance and scalability.**</span></span> <span data-ttu-id="12754-120">En muchas situaciones, los modelos de compilación y ejecución de .NET Framework proporcionan un rendimiento mejorado con respecto a Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="12754-120">In many situations, the .NET Framework language compilation and execution models deliver improved performance over Transact-SQL.</span></span>  
  
 <span data-ttu-id="12754-121">En la siguiente tabla se muestran los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="12754-121">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="12754-122">Información general de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="12754-122">Overview of CLR Integration</span></span>](clr-integration-overview.md)  
 <span data-ttu-id="12754-123">Describe los tipos de objetos que pueden generarse utilizando la integración con CLR y revisa los requisitos para generar objetos de base de datos mediante la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="12754-123">Describes the kinds of objects that can be built using CLR integration, and reviews the requirements for building database objects using CLR integration.</span></span>  
  
 [<span data-ttu-id="12754-124">Novedades de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="12754-124">What's New in CLR Integration</span></span>](clr-integration-what-s-new.md)  
 <span data-ttu-id="12754-125">Describe las nuevas características de esta versión.</span><span class="sxs-lookup"><span data-stu-id="12754-125">Describes the new features in this release.</span></span>  
  
 [<span data-ttu-id="12754-126">Arquitectura de integración CLR</span><span class="sxs-lookup"><span data-stu-id="12754-126">Architecture of CLR Integration</span></span>](../../database-engine/dev-guide/architecture-of-clr-integration.md)  
 <span data-ttu-id="12754-127">Describe los objetivos de diseño de la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="12754-127">Describes the design goals of CLR integration.</span></span>  
  
 [<span data-ttu-id="12754-128">Habilitar la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="12754-128">Enabling CLR Integration</span></span>](clr-integration-enabling.md)  
 <span data-ttu-id="12754-129">Describe cómo habilitar la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="12754-129">Describes how to enable CLR integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12754-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12754-130">See Also</span></span>  
 <span data-ttu-id="12754-131">[Instalación del .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span><span class="sxs-lookup"><span data-stu-id="12754-131">[Installing the .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span></span>  
 [<span data-ttu-id="12754-132">Rendimiento de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="12754-132">Performance of CLR Integration</span></span>](clr-integration-architecture-performance.md)  
  
  
