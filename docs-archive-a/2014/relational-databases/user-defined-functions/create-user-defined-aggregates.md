---
title: Creación de funciones de agregado definidas por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aggregate functions [SQL Server], user-defined
- user-defined functions [CLR integration]
ms.assetid: c278b746-6323-4b32-b460-239915acc067
author: rothja
ms.author: jroth
ms.openlocfilehash: c91179cb194bbfb79e8e7a8476e9725877b88afa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749681"
---
# <a name="create-user-defined-aggregates"></a><span data-ttu-id="d06f7-102">Crear funciones de agregado definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="d06f7-102">Create User-defined Aggregates</span></span>
  <span data-ttu-id="d06f7-103">Es posible crear en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] un objeto de base de datos programado en un ensamblado CLR.</span><span class="sxs-lookup"><span data-stu-id="d06f7-103">You can create a database object inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is programmed in a CLR assembly.</span></span> <span data-ttu-id="d06f7-104">Los objetos de base de datos que pueden aprovechar el completo modelo de programación que proporciona CLR incluyen desencadenadores, procedimientos almacenados, funciones, funciones de agregado y tipos.</span><span class="sxs-lookup"><span data-stu-id="d06f7-104">Database objects that can leverage the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
 <span data-ttu-id="d06f7-105">Al igual que las funciones de agregado integradas que proporciona [!INCLUDE[tsql](../../includes/tsql-md.md)], las funciones de agregado definidas por el usuario realizan un cálculo en un conjunto de valores y devuelven un único valor.</span><span class="sxs-lookup"><span data-stu-id="d06f7-105">Like the built-in aggregate functions provided in [!INCLUDE[tsql](../../includes/tsql-md.md)], user-defined aggregate functions perform a calculation on a set of values and return a single value.</span></span>  
  
 <span data-ttu-id="d06f7-106">La creación de una función de agregado definida por el usuario en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implica estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d06f7-106">Creating a user-defined aggregate function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] involves the following steps:</span></span>  
  
-   <span data-ttu-id="d06f7-107">Establecer la función de agregado definida por el usuario como una clase en un lenguaje de [!INCLUDE[msCoName](../../includes/msconame-md.md)] compatible con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d06f7-107">Define the user-defined aggregate function as a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework-supported language.</span></span> <span data-ttu-id="d06f7-108">Para obtener más información sobre cómo programar funciones de agregado definidas por el usuario en CRL, vea [Agregados definidos por el usuario de CLR](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="d06f7-108">For more information about how to program user-defined aggregates in the CLR, see [CLR User-Defined Aggregates](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span></span> <span data-ttu-id="d06f7-109">Compile esta clase para generar un ensamblado CRL con el compilador de lenguaje correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d06f7-109">Compile this class to build a CLR assembly using the appropriate language compiler.</span></span>  
  
-   <span data-ttu-id="d06f7-110">Registrar el ensamblado en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la instrucción CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="d06f7-110">Register the assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="d06f7-111">Para obtener más información sobre ensamblados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Ensamblados &#40;motor de base de datos&#41;](../clr-integration/assemblies-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="d06f7-111">For more information about assemblies in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Assemblies &#40;Database Engine&#41;](../clr-integration/assemblies-database-engine.md).</span></span>  
  
-   <span data-ttu-id="d06f7-112">Crear la función de agregado definida por el usuario que hace referencia al ensamblado registrado con la instrucción CREATE AGGREGATE.</span><span class="sxs-lookup"><span data-stu-id="d06f7-112">Create the user-defined aggregate that references the registered assembly using the CREATE AGGREGATE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d06f7-113">La implementación de un proyecto de SQL Server en [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registra un ensamblado en la base de datos especificada para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d06f7-113">Deploying a SQL Server Project in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registers an assembly in the database that was specified for the project.</span></span> <span data-ttu-id="d06f7-114">La implementación del proyecto también crea un agregado definido por el usuario en la base de datos para todas las definiciones de clase anotadas con el atributo `SqlUserDefinedAggregate`.</span><span class="sxs-lookup"><span data-stu-id="d06f7-114">Deploying the project also creates a user-defined aggregate in the database for all class definitions annotated with the `SqlUserDefinedAggregate` attribute.</span></span> <span data-ttu-id="d06f7-115">Para más información, consulte [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="d06f7-115">For more information, see [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d06f7-116">La capacidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ejecutar el código CLR se encuentra desactivada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d06f7-116">The ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to execute CLR code is off by default.</span></span> <span data-ttu-id="d06f7-117">Puede crear, modificar y quitar objetos de base de datos que hacen referencia a los módulos de códigos administrados; pero, estas referencias no se ejecutarán en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a menos que se haya habilitado la opción [clr enabled Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) por medio de [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d06f7-117">You can create, alter and drop database objects that reference managed code modules, but these references will not execute in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unless the [clr enabled Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) is enabled using [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span></span>  
  
 <span data-ttu-id="d06f7-118">**Para crear, modificar o quitar un ensamblado**</span><span class="sxs-lookup"><span data-stu-id="d06f7-118">**To create, modify, or drop an assembly**</span></span>  
  
-   [<span data-ttu-id="d06f7-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d06f7-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
-   [<span data-ttu-id="d06f7-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d06f7-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
-   [<span data-ttu-id="d06f7-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d06f7-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-assembly-transact-sql)  
  
 <span data-ttu-id="d06f7-122">**Para crear una función de agregado definida por el usuario**</span><span class="sxs-lookup"><span data-stu-id="d06f7-122">**To create a user-defined aggregate**</span></span>  
  
-   [<span data-ttu-id="d06f7-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d06f7-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-aggregate-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="d06f7-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d06f7-124">See Also</span></span>  
 [<span data-ttu-id="d06f7-125">Conceptos de programación en el ámbito de la integración de Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="d06f7-125">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](../clr-integration/common-language-runtime-clr-integration-programming-concepts.md)  
  
  
