---
title: Conceptos de programación de la integración con Common Language Runtime (CLR) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- CLR [SQL Server] See common language runtime [SQL Server]
- Database Engine [SQL Server], .NET Framework
- .NET Framework [SQL Server], Database Engine programming
- common language runtime [SQL Server]
- .NET Framework [SQL Server]
ms.assetid: 951bf851-3e6e-4361-ae6a-2bcd5b837ebd
author: rothja
ms.author: jroth
ms.openlocfilehash: 38323b0145132ad60d59c001d5147a7d19942462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671581"
---
# <a name="common-language-runtime-clr-integration-programming-concepts"></a><span data-ttu-id="d63d5-102">Conceptos de programación en el ámbito de la integración de Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="d63d5-102">Common Language Runtime (CLR) Integration Programming Concepts</span></span>
  <span data-ttu-id="d63d5-103">A partir de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] incorpora la integración del componente Common Language Runtime (CLR) de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework para Windows.</span><span class="sxs-lookup"><span data-stu-id="d63d5-103">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="d63d5-104">Esto significa que ahora puede escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario, así como funciones con valores de tabla de transmisión por secuencias mediante cualquier lenguaje de .NET Framework, incluidos [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET y [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d63d5-104">This means that you can now write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="d63d5-105">El espacio de nombres Microsoft.SqlServer.Server incluye funcionalidad básica para la programación CLR en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d63d5-105">The Microsoft.SqlServer.Server namespace includes core functionality for CLR programming in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d63d5-106">Sin embargo, el espacio de nombres Microsoft.SqlServer.Server se documenta en el SDK de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d63d5-106">However, the Microsoft.SqlServer.Server namespace is documented in the .NET Framework SDK.</span></span> <span data-ttu-id="d63d5-107">Esta documentación no está incluida en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d63d5-107">This documentation is not included in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d63d5-108">De forma predeterminada, .NET Framework se instala con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], pero no es así para .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="d63d5-108">By default, the .NET Framework is installed with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but the .NET Framework SDK is not.</span></span> <span data-ttu-id="d63d5-109">Sin el SDK instalado en su equipo e incluido en la colección de Libros en pantalla, no funcionan los vínculos al contenido de SDK de esta sección.</span><span class="sxs-lookup"><span data-stu-id="d63d5-109">Without the SDK installed on your computer and included in the Books Online collection, links to SDK content in this section do not work.</span></span> <span data-ttu-id="d63d5-110">Instale .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="d63d5-110">Install the .NET Framework SDK.</span></span> <span data-ttu-id="d63d5-111">Una vez instalado, agregue el SDK a la colección de libros en pantalla y a la tabla de contenido siguiendo las instrucciones de [instalación del SDK de .NET Framework](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="d63d5-111">Once installed, add the SDK to the Books Online collection and table of contents by following the instructions in [Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span></span>  
  
 <span data-ttu-id="d63d5-112">En la siguiente tabla se muestran los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="d63d5-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="d63d5-113">Información general sobre la integración de Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="d63d5-113">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](common-language-runtime-integration-overview.md)  
 <span data-ttu-id="d63d5-114">Proporciona una breve introducción a CLR y describe cómo y por qué se ha utilizado esta tecnología en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d63d5-114">Provides a brief overview of the CLR, and describes how and why this technology has been used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d63d5-115">Describe las ventajas de usar CLR para crear objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d63d5-115">Describes the benefits of using the CLR to create database objects.</span></span>  
  
 [<span data-ttu-id="d63d5-116">Ensamblados &#40;motor de la base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d63d5-116">Assemblies &#40;Database Engine&#41;</span></span>](assemblies-database-engine.md)  
 <span data-ttu-id="d63d5-117">Describe cómo se utilizan los ensamblados en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para implementar funciones, procedimientos almacenados, desencadenadores, agregados y tipos definidos por el usuario, escritos en uno de los lenguajes de código administrado (no en [!INCLUDE[msCoName](../../../includes/msconame-md.md)]) y que se hospedan en Common Language Runtime (CLR) de [!INCLUDE[tsql](../../../includes/tsql-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d63d5-117">Describes how assemblies are used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework common language runtime (CLR), and not written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 [<span data-ttu-id="d63d5-118">Crear objetos de base de datos con Common Language Runtime &#40;CLR&#41; Integration</span><span class="sxs-lookup"><span data-stu-id="d63d5-118">Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration</span></span>](database-objects/building-database-objects-with-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="d63d5-119">Describe los tipos de objetos que pueden estar generados mediante CLR y revisa los requisitos para generar objetos de base de datos de CLR.</span><span class="sxs-lookup"><span data-stu-id="d63d5-119">Describes the kinds of objects that can be built using the CLR, and reviews the requirements for building CLR database objects.</span></span>  
  
 [<span data-ttu-id="d63d5-120">Acceso a datos de objetos de base de datos de CLR</span><span class="sxs-lookup"><span data-stu-id="d63d5-120">Data Access from CLR Database Objects</span></span>](data-access/data-access-from-clr-database-objects.md)  
 <span data-ttu-id="d63d5-121">Describe cómo una rutina CLR puede tener acceso a los datos almacenados en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d63d5-121">Describes how a CLR routine can access data stored in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="d63d5-122">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="d63d5-122">CLR Integration Security</span></span>](security/clr-integration-security.md)  
 <span data-ttu-id="d63d5-123">Describe el modelo de seguridad de la integración CLR.</span><span class="sxs-lookup"><span data-stu-id="d63d5-123">Describes the CLR integration security model.</span></span>  
  
 [<span data-ttu-id="d63d5-124">Depurar objetos de base de datos CLR</span><span class="sxs-lookup"><span data-stu-id="d63d5-124">Debugging CLR Database Objects</span></span>](debugging-clr-database-objects.md)  
 <span data-ttu-id="d63d5-125">Describe las limitaciones y los requisitos para depurar los objetos de la base de datos de CLR.</span><span class="sxs-lookup"><span data-stu-id="d63d5-125">Describes limitations of and requirements for debugging CLR database objects.</span></span>  
  
 [<span data-ttu-id="d63d5-126">Implementar objetos de base de datos CLR</span><span class="sxs-lookup"><span data-stu-id="d63d5-126">Deploying CLR Database Objects</span></span>](deploying-clr-database-objects.md)  
 <span data-ttu-id="d63d5-127">Describe los ensamblados de implementación a servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="d63d5-127">Describes deploying assemblies to production servers.</span></span>  
  
 [<span data-ttu-id="d63d5-128">Administrar ensamblados de integración CLR</span><span class="sxs-lookup"><span data-stu-id="d63d5-128">Managing CLR Integration Assemblies</span></span>](assemblies/managing-clr-integration-assemblies.md)  
 <span data-ttu-id="d63d5-129">Describe cómo crear y quitar los ensamblados de integración CLR.</span><span class="sxs-lookup"><span data-stu-id="d63d5-129">Describes how to create and drop CLR integration assemblies.</span></span>  
  
 [<span data-ttu-id="d63d5-130">Supervisar y solucionar problemas de objetos de base de datos administrados</span><span class="sxs-lookup"><span data-stu-id="d63d5-130">Monitoring and Troubleshooting Managed Database Objects</span></span>](monitoring-and-troubleshooting-managed-database-objects.md)  
 <span data-ttu-id="d63d5-131">Se proporciona información sobre las herramientas que se pueden utilizar para supervisar y solucionar problemas de los objetos de base de datos administrados y ensamblados que se ejecutan en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d63d5-131">Provides information about the tools that can be used to monitor and troubleshoot managed database objects and assemblies running in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="d63d5-132">Escenarios de uso y ejemplos para la integración de Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="d63d5-132">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="d63d5-133">Describe escenarios de uso y ejemplos de código que usan objetos CLR.</span><span class="sxs-lookup"><span data-stu-id="d63d5-133">Describes usage scenarios and code samples using CLR objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d63d5-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d63d5-134">See Also</span></span>  
 <span data-ttu-id="d63d5-135">[Ensamblados &#40;Motor de base de datos&#41;](assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="d63d5-135">[Assemblies &#40;Database Engine&#41;](assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="d63d5-136">[Instalar .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d63d5-136">[Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span></span>  
  
  
