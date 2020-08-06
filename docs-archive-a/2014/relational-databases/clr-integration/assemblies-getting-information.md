---
title: Obtener información acerca de los ensamblados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], metadata
- status information [SQL Server], assemblies
- metadata [SQL Server], assemblies
ms.assetid: 6aa7f18e-baad-4481-9777-8c3b230b392f
author: rothja
ms.author: jroth
ms.openlocfilehash: ec559ba5ccbb53dd92f3a5e1175a10a59fbaf43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747636"
---
# <a name="getting-information-about-assemblies"></a><span data-ttu-id="2aee5-102">Obtener información acerca de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="2aee5-102">Getting Information About Assemblies</span></span>
  <span data-ttu-id="2aee5-103">Se pueden realizar consultas de metadatos acerca de ensamblados en las siguientes vistas de catálogo y funciones.</span><span class="sxs-lookup"><span data-stu-id="2aee5-103">The following catalog views and functions can be queried for metadata about assemblies.</span></span>  
  
 <span data-ttu-id="2aee5-104">**Para obtener información acerca de ensamblados individuales**</span><span class="sxs-lookup"><span data-stu-id="2aee5-104">**To get information about individual assemblies**</span></span>  
  
-   [<span data-ttu-id="2aee5-105">ASSEMBLYPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2aee5-105">ASSEMBLYPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/assemblyproperty-transact-sql)  
  
 <span data-ttu-id="2aee5-106">**Para obtener información acerca de todos los ensamblados de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="2aee5-106">**To get information about all assemblies in the database**</span></span>  
  
-   [<span data-ttu-id="2aee5-107">Sys. Assemblies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2aee5-107">sys.assemblies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assemblies-transact-sql)  
  
 <span data-ttu-id="2aee5-108">**Para obtener información acerca de archivos de ensamblado, incluyendo binarios, archivos de origen y archivos de depuración**</span><span class="sxs-lookup"><span data-stu-id="2aee5-108">**To get information about assembly files, including assembly binaries, source files, and debug files**</span></span>  
  
-   [<span data-ttu-id="2aee5-109">Sys. assembly_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2aee5-109">sys.assembly_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-files-transact-sql)  
  
 <span data-ttu-id="2aee5-110">**Para obtener información acerca de referencias entre ensamblados**</span><span class="sxs-lookup"><span data-stu-id="2aee5-110">**To get information about cross-assembly references**</span></span>  
  
-   [<span data-ttu-id="2aee5-111">Sys. assembly_references &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2aee5-111">sys.assembly_references &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-references-transact-sql)  
  
 <span data-ttu-id="2aee5-112">**Para obtener información de ensamblado acerca de tipos definidos por el usuario**</span><span class="sxs-lookup"><span data-stu-id="2aee5-112">**To get assembly information about user-defined types**</span></span>  
  
-   [<span data-ttu-id="2aee5-113">Sys. assembly_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2aee5-113">sys.assembly_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-types-transact-sql)  
  
-   [<span data-ttu-id="2aee5-114">sys.types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2aee5-114">sys.types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-types-transact-sql)  
  
 <span data-ttu-id="2aee5-115">**Para obtener información de ensamblado acerca de procedimientos almacenados, desencadenadores y funciones de Common Language Runtime (CLR)**</span><span class="sxs-lookup"><span data-stu-id="2aee5-115">**To get assembly information about common language runtime (CLR) stored procedures, triggers, and functions**</span></span>  
  
-   [<span data-ttu-id="2aee5-116">sys.assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2aee5-116">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
 <span data-ttu-id="2aee5-117">**Para obtener información acerca de objetos no CLR**</span><span class="sxs-lookup"><span data-stu-id="2aee5-117">**To get information about non-CLR objects**</span></span>  
  
-   [<span data-ttu-id="2aee5-118">sys.sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2aee5-118">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="2aee5-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2aee5-119">See Also</span></span>  
 <span data-ttu-id="2aee5-120">[Ensamblados &#40;Motor de base de datos&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="2aee5-120">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="2aee5-121">[Diseñar ensamblados](../../relational-databases/clr-integration/assemblies-designing.md) </span><span class="sxs-lookup"><span data-stu-id="2aee5-121">[Designing Assemblies](../../relational-databases/clr-integration/assemblies-designing.md) </span></span>  
 [<span data-ttu-id="2aee5-122">Implementar ensamblados</span><span class="sxs-lookup"><span data-stu-id="2aee5-122">Implementing Assemblies</span></span>](assemblies-implementing.md)  
  
  
