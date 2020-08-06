---
title: Creación de desencadenadores CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- CRL triggers
- DML triggers, CLR triggers
- DDL triggers, CLR triggers
ms.assetid: 31f41703-134d-49fc-9850-76c297351c2c
author: rothja
ms.author: jroth
ms.openlocfilehash: 3afd841b4f1f9ca567a93c0a20c0a7609a5b45e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676944"
---
# <a name="create-clr-triggers"></a><span data-ttu-id="e4d69-102">Crear desencadenadores CLR</span><span class="sxs-lookup"><span data-stu-id="e4d69-102">Create CLR Triggers</span></span>
  <span data-ttu-id="e4d69-103">Es posible crear un objeto de base de datos dentro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] programado en un ensamblado creado en Common Language Runtime (CLR) de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4d69-103">You can create a database object inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is programmed in an assembly created in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language runtime (CLR).</span></span> <span data-ttu-id="e4d69-104">Los objetos de base de datos que pueden aprovechar el complejo modelo de programación que proporciona CLR incluyen desencadenadores DML, desencadenadores DDL, procedimientos almacenados, funciones, funciones de agregado y tipos.</span><span class="sxs-lookup"><span data-stu-id="e4d69-104">Database objects that can leverage the rich programming model provided by the CLR include DML triggers, DDL triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
 <span data-ttu-id="e4d69-105">Para crear un desencadenador CLR (DML o DDL) en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e4d69-105">Creating a CLR trigger (DML or DDL) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] involves the following steps:</span></span>  
  
-   <span data-ttu-id="e4d69-106">Defina el desencadenador como una clase en un lenguaje admitido por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e4d69-106">Define the trigger as a class in a .NET Framework-supported language.</span></span> <span data-ttu-id="e4d69-107">Para obtener más información sobre cómo programar desencadenadores en CLR, vea [Desencadenadores CLR](../../database-engine/dev-guide/clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="e4d69-107">For more information about how to program triggers in the CLR, see [CLR Triggers](../../database-engine/dev-guide/clr-triggers.md).</span></span> <span data-ttu-id="e4d69-108">A continuación, compile la clase para generar un ensamblado en [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] mediante el compilador del lenguaje adecuado.</span><span class="sxs-lookup"><span data-stu-id="e4d69-108">Then, compile the class to build an assembly in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] using the appropriate language compiler.</span></span>  
  
-   <span data-ttu-id="e4d69-109">Registrar el ensamblado en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la instrucción CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="e4d69-109">Register the assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="e4d69-110">Para obtener más información sobre ensamblados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Ensamblados &#40;motor de base de datos&#41;](../clr-integration/assemblies-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="e4d69-110">For more information about assemblies in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Assemblies &#40;Database Engine&#41;](../clr-integration/assemblies-database-engine.md).</span></span>  
  
-   <span data-ttu-id="e4d69-111">Cree el desencadenador que hace referencia al ensamblado registrado.</span><span class="sxs-lookup"><span data-stu-id="e4d69-111">Create the trigger that references the registered assembly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4d69-112">La implementación de un proyecto de SQL Server en [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registra un ensamblado en la base de datos especificada para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e4d69-112">Deploying a SQL Server Project in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registers an assembly in the database that was specified for the project.</span></span> <span data-ttu-id="e4d69-113">La implementación del proyecto también crea desencadenadores CLR en la base de datos para todos los métodos anotados con el atributo `SqlTrigger`.</span><span class="sxs-lookup"><span data-stu-id="e4d69-113">Deploying the project also creates CLR triggers in the database for all methods annotated with the `SqlTrigger` attribute.</span></span> <span data-ttu-id="e4d69-114">Para más información, consulte [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="e4d69-114">For more information, see [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4d69-115">La capacidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ejecutar el código CLR se encuentra desactivada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e4d69-115">The ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to execute CLR code is off by default.</span></span> <span data-ttu-id="e4d69-116">Puede crear, modificar y quitar objetos de base de datos que hacen referencia a los módulos de códigos administrados, pero estas referencias no se ejecutarán en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a menos que se haya habilitado [clr enabled (opción)](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) mediante [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e4d69-116">You can create, alter, and drop database objects that reference managed code modules, but these references will not execute in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unless the [clr enabled Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) is enabled using [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span></span>  
  
 <span data-ttu-id="e4d69-117">**Para crear, modificar o quitar un ensamblado**</span><span class="sxs-lookup"><span data-stu-id="e4d69-117">**To create, modify, or drop an assembly**</span></span>  
  
-   [<span data-ttu-id="e4d69-118">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e4d69-118">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
-   [<span data-ttu-id="e4d69-119">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e4d69-119">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
-   [<span data-ttu-id="e4d69-120">DROP ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e4d69-120">DROP ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-assembly-transact-sql)  
  
 <span data-ttu-id="e4d69-121">**Para crear un desencadenador CLR**</span><span class="sxs-lookup"><span data-stu-id="e4d69-121">**To create a CLR trigger**</span></span>  
  
-   [<span data-ttu-id="e4d69-122">CREATE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e4d69-122">CREATE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-trigger-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="e4d69-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4d69-123">See Also</span></span>  
 <span data-ttu-id="e4d69-124">[Desencadenadores DML](dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="e4d69-124">[DML Triggers](dml-triggers.md) </span></span>  
 <span data-ttu-id="e4d69-125">[Conceptos de programación en el ámbito de la integración de Common Language Runtime &#40;CLR&#41;](../clr-integration/common-language-runtime-clr-integration-programming-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="e4d69-125">[Common Language Runtime &#40;CLR&#41; Integration Programming Concepts](../clr-integration/common-language-runtime-clr-integration-programming-concepts.md) </span></span>  
 [<span data-ttu-id="e4d69-126">Acceso a datos de objetos de base de datos de CLR</span><span class="sxs-lookup"><span data-stu-id="e4d69-126">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
