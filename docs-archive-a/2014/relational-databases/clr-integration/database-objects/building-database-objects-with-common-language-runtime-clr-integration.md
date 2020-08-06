---
title: Crear objetos de base de datos con la integración de Common Language Runtime (CLR) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- database objects [CLR integration], building
- common language runtime [SQL Server], building database objects
- managed code [SQL Server], database objects
- building database objects [CLR integration]
- .NET Framework routines [SQL Server]
ms.assetid: ce34132c-bfa3-447b-9131-b6e17c672efe
author: rothja
ms.author: jroth
ms.openlocfilehash: 3c849c095a3be1c590e6fcb3ce87a0725eb795c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674155"
---
# <a name="building-database-objects-with-common-language-runtime-clr-integration"></a><span data-ttu-id="e9b13-102">Generar objetos de base de datos con la integración de Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="e9b13-102">Building Database Objects with Common Language Runtime (CLR) Integration</span></span>
  <span data-ttu-id="e9b13-103">Puede crear objetos de base de datos mediante el al que [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se hace referencia como "rutina de CLR".</span><span class="sxs-lookup"><span data-stu-id="e9b13-103">You can build database objects using the [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is referred to as a "CLR routine."</span></span> <span data-ttu-id="e9b13-104">Estas rutinas incluyen:</span><span class="sxs-lookup"><span data-stu-id="e9b13-104">These routines include:</span></span>  
  
-   <span data-ttu-id="e9b13-105">Funciones definidas por el usuario con valores escalares (UDF escalares)</span><span class="sxs-lookup"><span data-stu-id="e9b13-105">Scalar-valued user-defined functions (scalar UDFs)</span></span>  
  
-   <span data-ttu-id="e9b13-106">Funciones definidas por el usuario con valores de tabla (TVF)</span><span class="sxs-lookup"><span data-stu-id="e9b13-106">Table-valued user-defined functions (TVFs)</span></span>  
  
-   <span data-ttu-id="e9b13-107">Procedimientos definidos por el usuario (UDP)</span><span class="sxs-lookup"><span data-stu-id="e9b13-107">User-defined procedures (UDPs)</span></span>  
  
-   <span data-ttu-id="e9b13-108">Desencadenadores definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="e9b13-108">User-defined triggers</span></span>  
  
 <span data-ttu-id="e9b13-109">Las rutinas CLR tienen la misma estructura en código administrado.</span><span class="sxs-lookup"><span data-stu-id="e9b13-109">CLR routines have the same structure in managed code.</span></span> <span data-ttu-id="e9b13-110">Están asignadas a los métodos público, estático (compartidos en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) de una clase.</span><span class="sxs-lookup"><span data-stu-id="e9b13-110">They are mapped to public, static (shared in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) methods of a class.</span></span> <span data-ttu-id="e9b13-111">Además de las rutinas, los tipos definidos por el usuario (UDT) y las funciones de agregado definidas por el usuario también se pueden definir mediante .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9b13-111">In addition to routines, user-defined types (UDTs) and user-defined aggregate functions can also be defined using the .NET Framework.</span></span> <span data-ttu-id="e9b13-112">Los UDT y los agregados definidos por el usuario están asignados a las clases de .NET Framework completas.</span><span class="sxs-lookup"><span data-stu-id="e9b13-112">UDTs and user-defined aggregates are mapped to entire .NET Framework classes.</span></span>  
  
 <span data-ttu-id="e9b13-113">Cada tipo de .NET Framework rutina tiene un [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] que [!INCLUDE[tsql](../../../includes/tsql-md.md)] se puede usar el equivalente.</span><span class="sxs-lookup"><span data-stu-id="e9b13-113">Each type of .NET Framework routine has a [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] that the [!INCLUDE[tsql](../../../includes/tsql-md.md)] equivalent can be used.</span></span> <span data-ttu-id="e9b13-114">Por ejemplo, los UDF escalares se pueden usar en cualquier expresión escalar.</span><span class="sxs-lookup"><span data-stu-id="e9b13-114">For instance, scalar UDFs can be used in any scalar expression.</span></span> <span data-ttu-id="e9b13-115">Un TVF se puede usar en cualquier cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="e9b13-115">A TVF can be used in any FROM clause.</span></span> <span data-ttu-id="e9b13-116">Un procedimiento se puede invocar en una instrucción EXEC o bien, desde una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="e9b13-116">A procedure can be invoked in an EXEC statement or invoked from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9b13-117">La ejecución de un objeto CLR (función definida por el usuario, tipo definido por el usuario o desencadenador) en el Common Language Runtime puede tener lugar en varios subprocesos (el plan paralelo), si el optimizador de consultas decide que es beneficioso.</span><span class="sxs-lookup"><span data-stu-id="e9b13-117">Execution of a CLR object (user-defined function, user-defined type, or trigger) on the common language runtime can take place on multiple threads (parallel plan), if the query optimizer decides it is beneficial.</span></span> <span data-ttu-id="e9b13-118">Sin embargo, si una función definida por el usuario tiene acceso a los datos, la ejecución estará en un plan de serie.</span><span class="sxs-lookup"><span data-stu-id="e9b13-118">However, if a user-defined function accesses data, execution will be  on a serial plan.</span></span> <span data-ttu-id="e9b13-119">Cuando se ejecuta en una versión de servidor anterior a [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], si una función definida por el usuario contiene parámetros LOB o valores devueltos, la ejecución también debe estar en un plan en serie.</span><span class="sxs-lookup"><span data-stu-id="e9b13-119">When executed on a server version prior to [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], if a user-defined function contains LOB parameters or return values, execution also must be on a serial plan.</span></span>  
  
 <span data-ttu-id="e9b13-120">En la siguiente tabla se enumeran los temas incluidos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="e9b13-120">The following table lists the topics covered in this section.</span></span>  
  
 [<span data-ttu-id="e9b13-121">Introducción a la integración CLR</span><span class="sxs-lookup"><span data-stu-id="e9b13-121">Getting Started with CLR Integration</span></span>](getting-started-with-clr-integration.md)  
 <span data-ttu-id="e9b13-122">Proporciona una breve información general de las bibliotecas y los espacios de nombres requeridos para compilar objetos mediante la integración CLR con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9b13-122">Provides a brief overview of the libraries and namespaces required to compile object using CLR integration with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e9b13-123">Incluye un procedimiento almacenado CLR "Hello World" de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e9b13-123">Includes an example "Hello World" CLR stored procedure.</span></span>  
  
 [<span data-ttu-id="e9b13-124">Bibliotecas de .NET Framework admitidas</span><span class="sxs-lookup"><span data-stu-id="e9b13-124">Supported .NET Framework Libraries</span></span>](supported-net-framework-libraries.md)  
 <span data-ttu-id="e9b13-125">Proporciona información sobre las bibliotecas de .NET Framework admitidas por la integración CLR.</span><span class="sxs-lookup"><span data-stu-id="e9b13-125">Provides information on the .NET Framework libraries supported by CLR integration.</span></span>  
  
 [<span data-ttu-id="e9b13-126">Restricciones del modelo de programación de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="e9b13-126">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
 <span data-ttu-id="e9b13-127">Proporciona información sobre las restricciones del modelo de programación de integración CLR.</span><span class="sxs-lookup"><span data-stu-id="e9b13-127">Provides information about CLR integration programming model restrictions.</span></span>  
  
 [<span data-ttu-id="e9b13-128">Tipos de datos de SQL Server en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e9b13-128">SQL Server Data Types in the .NET Framework</span></span>](../../clr-integration-database-objects-types-net-framework/sql-server-data-types-in-the-net-framework.md)  
 <span data-ttu-id="e9b13-129">Información general de tipos de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y sus equivalentes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9b13-129">An overview of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types and their .NET Framework equivalents.</span></span>  
  
 [<span data-ttu-id="e9b13-130">Información general de los atributos personalizados de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="e9b13-130">Overview of CLR Integration Custom Attributes</span></span>](../../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md)  
 <span data-ttu-id="e9b13-131">Proporciona información sobre los atributos personalizados de integración CLR.</span><span class="sxs-lookup"><span data-stu-id="e9b13-131">Provides information about CLR integration custom attributes.</span></span>  
  
 [<span data-ttu-id="e9b13-132">Funciones CLR definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="e9b13-132">CLR User-Defined Functions</span></span>](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md)  
 <span data-ttu-id="e9b13-133">Describe cómo implementar y usar los distintos tipos de funciones CLR: funciones de agregado definidas por el usuario, escalares y con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="e9b13-133">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="e9b13-134">Tipos definidos por el usuario CLR</span><span class="sxs-lookup"><span data-stu-id="e9b13-134">CLR User-Defined Types</span></span>](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md)  
 <span data-ttu-id="e9b13-135">Describe cómo implementar y usar los tipos definidos por el usuario CLR.</span><span class="sxs-lookup"><span data-stu-id="e9b13-135">Describes how to implement and use CLR user-defined types.</span></span>  
  
 [<span data-ttu-id="e9b13-136">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="e9b13-136">CLR Stored Procedures</span></span>](../../../database-engine/dev-guide/clr-stored-procedures.md)  
 <span data-ttu-id="e9b13-137">Describe cómo implementar y usar los procedimientos almacenados CLR.</span><span class="sxs-lookup"><span data-stu-id="e9b13-137">Describes how to implement and use CLR stored procedures.</span></span>  
  
 [<span data-ttu-id="e9b13-138">Desencadenadores de CLR</span><span class="sxs-lookup"><span data-stu-id="e9b13-138">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
 <span data-ttu-id="e9b13-139">Describe cómo implementar y usar los desencadenadores CLR.</span><span class="sxs-lookup"><span data-stu-id="e9b13-139">Describes how to implement and use CLR triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b13-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9b13-140">See Also</span></span>  
 [<span data-ttu-id="e9b13-141">Información general sobre la integración de Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="e9b13-141">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](../common-language-runtime-integration-overview.md)  
  
  
