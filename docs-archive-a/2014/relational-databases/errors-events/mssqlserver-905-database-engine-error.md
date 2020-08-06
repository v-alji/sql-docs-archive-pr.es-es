---
title: MSSQLSERVER_905 | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 905 (Database Engine error)
ms.assetid: c828bb2e-e554-4f81-b76c-2b3740d2b944
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7dd3c8c5a287e2d123e2a9d1430ecd49b27f29f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672036"
---
# <a name="mssqlserver_905"></a><span data-ttu-id="88bda-102">MSSQLSERVER_905</span><span class="sxs-lookup"><span data-stu-id="88bda-102">MSSQLSERVER_905</span></span>
    
## <a name="details"></a><span data-ttu-id="88bda-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="88bda-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88bda-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="88bda-104">Product Name</span></span>|<span data-ttu-id="88bda-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="88bda-105">SQL Server</span></span>|  
|<span data-ttu-id="88bda-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="88bda-106">Event ID</span></span>|<span data-ttu-id="88bda-107">905</span><span class="sxs-lookup"><span data-stu-id="88bda-107">905</span></span>|  
|<span data-ttu-id="88bda-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="88bda-108">Event Source</span></span>|<span data-ttu-id="88bda-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="88bda-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="88bda-110">Componente</span><span class="sxs-lookup"><span data-stu-id="88bda-110">Component</span></span>|<span data-ttu-id="88bda-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="88bda-111">SQLEngine</span></span>|  
|<span data-ttu-id="88bda-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="88bda-112">Symbolic Name</span></span>|<span data-ttu-id="88bda-113">DBSTARTUP_EE_PARTITIONING</span><span class="sxs-lookup"><span data-stu-id="88bda-113">DBSTARTUP_EE_PARTITIONING</span></span>|  
|<span data-ttu-id="88bda-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="88bda-114">Message Text</span></span>|<span data-ttu-id="88bda-115">La base de datos '%. \* ls' no se puede iniciar en esta edición de SQL Server porque contiene una función de partición '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="88bda-115">Database '%.\*ls' cannot be started in this edition of SQL Server because it contains a partition function '%.\*ls'.</span></span> <span data-ttu-id="88bda-116">Únicamente la edición Enterprise de SQL Server admite particionamiento.</span><span class="sxs-lookup"><span data-stu-id="88bda-116">Only Enterprise edition of SQL Server supports partitioning.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="88bda-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="88bda-117">Explanation</span></span>  
 <span data-ttu-id="88bda-118">La base de datos contiene una o varias tablas o índices con particiones.</span><span class="sxs-lookup"><span data-stu-id="88bda-118">The database contains one or more partitioned tables or indexes.</span></span> <span data-ttu-id="88bda-119">Esta edición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no puede utilizar particionamiento.</span><span class="sxs-lookup"><span data-stu-id="88bda-119">This edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot use partitioning.</span></span> <span data-ttu-id="88bda-120">En consecuencia, la base de datos no se puede iniciar correctamente.</span><span class="sxs-lookup"><span data-stu-id="88bda-120">Therefore, the database cannot be started correctly.</span></span> <span data-ttu-id="88bda-121">Las tablas e índices con particiones no están disponibles en todas las ediciones de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88bda-121">Partitioned tables and indexes are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="88bda-122">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="88bda-122">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="88bda-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="88bda-123">User Action</span></span>  
 <span data-ttu-id="88bda-124">Separe la base de datos mediante el procedimiento almacenado sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="88bda-124">Detach the database by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="88bda-125">Mueva los archivos si es necesario, y, a continuación, asocie la base de datos a una instancia de una edición [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando CREATE DATABASE con las opciones FOR ATTACH o FOR ATTACH_REBUILD_LOG.</span><span class="sxs-lookup"><span data-stu-id="88bda-125">Move the files if it is needed, and then attach the database to an instance of a supported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition by using the CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="88bda-126">Deshabilite el particionamiento en todas las tablas y quite las funciones de particionamiento.</span><span class="sxs-lookup"><span data-stu-id="88bda-126">Disable partitioning on all tables and remove the partitioning functions.</span></span> <span data-ttu-id="88bda-127">Desasocie la base de datos de nuevo y vuelva a adjuntarla al servidor actual.</span><span class="sxs-lookup"><span data-stu-id="88bda-127">Detach the database again, and reattach the database to the current server.</span></span>  
  
  
