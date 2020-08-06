---
title: Bases de datos del sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system databases [SQL Server]
- displaying system database data
- modifying system data
- viewing system database data
ms.assetid: 30468a7c-4225-4d35-aa4a-ffa7da4f1282
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65deee685c2205a7c6e41ed86f71c69639555d7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744113"
---
# <a name="system-databases"></a><span data-ttu-id="c3a85-102">Bases de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="c3a85-102">System Databases</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c3a85-103">incluye las siguientes bases de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="c3a85-103">includes the following system databases.</span></span>  
  
|<span data-ttu-id="c3a85-104">Base de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="c3a85-104">System database</span></span>|<span data-ttu-id="c3a85-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3a85-105">Description</span></span>|  
|---------------------|-----------------|  
|[<span data-ttu-id="c3a85-106">Base de datos maestra</span><span class="sxs-lookup"><span data-stu-id="c3a85-106">master Database</span></span>](master-database.md)|<span data-ttu-id="c3a85-107">Registra toda la información del sistema para una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3a85-107">Records all the system-level information for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="c3a85-108">Base de datos msdb</span><span class="sxs-lookup"><span data-stu-id="c3a85-108">msdb Database</span></span>](msdb-database.md)|<span data-ttu-id="c3a85-109">La utiliza el Agente SQL Server para programar alertas y trabajos.</span><span class="sxs-lookup"><span data-stu-id="c3a85-109">Is used by SQL Server Agent for scheduling alerts and jobs.</span></span>|  
|[<span data-ttu-id="c3a85-110">Base de datos model</span><span class="sxs-lookup"><span data-stu-id="c3a85-110">model Database</span></span>](model-database.md)|<span data-ttu-id="c3a85-111">Se utiliza como plantilla para todas las bases de datos creadas en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3a85-111">Is used as the template for all databases created on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c3a85-112">Las modificaciones hechas a la base de datos **model** , como el tamaño de la base de datos, la intercalación, el modelo de recuperación y otras opciones de base de datos, se aplicarán a las bases de datos que se creen con posterioridad.</span><span class="sxs-lookup"><span data-stu-id="c3a85-112">Modifications made to the **model** database, such as database size, collation, recovery model, and other database options, are applied to any databases created afterward.</span></span>|  
|[<span data-ttu-id="c3a85-113">Base de datos Resource</span><span class="sxs-lookup"><span data-stu-id="c3a85-113">Resource Database</span></span>](resource-database.md)|<span data-ttu-id="c3a85-114">Base de datos de solo lectura que contiene objetos del sistema que se incluyen con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3a85-114">Is a read-only database that contains system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c3a85-115">Los objetos del sistema persisten físicamente en la base de datos **Resource** , pero aparecen lógicamente en el esquema **sys** de cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3a85-115">System objects are physically persisted in the **Resource** database, but they logically appear in the **sys** schema of every database.</span></span>|  
|[<span data-ttu-id="c3a85-116">Base de datos tempdb</span><span class="sxs-lookup"><span data-stu-id="c3a85-116">tempdb Database</span></span>](tempdb-database.md)|<span data-ttu-id="c3a85-117">Área de trabajo que contiene objetos temporales o conjuntos de resultados intermedios.</span><span class="sxs-lookup"><span data-stu-id="c3a85-117">Is a workspace for holding temporary objects or intermediate result sets.</span></span>|  
  
## <a name="modifying-system-data"></a><span data-ttu-id="c3a85-118">modificar datos del sistema</span><span class="sxs-lookup"><span data-stu-id="c3a85-118">Modifying System Data</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c3a85-119">no permite a los usuarios actualizar directamente la información de objetos del sistema, como tablas del sistema, procedimientos almacenados del sistema y vistas de catálogo.</span><span class="sxs-lookup"><span data-stu-id="c3a85-119">does not support users directly updating the information in system objects such as system tables, system stored procedures, and catalog views.</span></span> <span data-ttu-id="c3a85-120">En vez de eso, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona un completo conjunto de herramientas administrativas con las que los usuarios pueden administrar totalmente el sistema, los usuarios y los objetos de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3a85-120">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides a complete set of administrative tools that let users fully administer their system and manage all users and objects in a database.</span></span> <span data-ttu-id="c3a85-121">Entre ellas, figuran:</span><span class="sxs-lookup"><span data-stu-id="c3a85-121">These include the following:</span></span>  
  
-   <span data-ttu-id="c3a85-122">Utilidades de administración, como [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3a85-122">Administration utilities, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="c3a85-123">API de SQL-SMO.</span><span class="sxs-lookup"><span data-stu-id="c3a85-123">SQL-SMO API.</span></span> <span data-ttu-id="c3a85-124">Permite a los programadores incluir funcionalidad completa para administrar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c3a85-124">This lets programmers include complete functionality for administering [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in their applications.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="c3a85-125">.</span><span class="sxs-lookup"><span data-stu-id="c3a85-125">scripts and stored procedures.</span></span> <span data-ttu-id="c3a85-126">Pueden utilizar procedimientos almacenados del sistema e instrucciones DDL de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3a85-126">These can use system stored procedures and [!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statements.</span></span>  
  
 <span data-ttu-id="c3a85-127">Estas herramientas protegen a las aplicaciones de cambios en los objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="c3a85-127">These tools shield applications from changes in the system objects.</span></span> <span data-ttu-id="c3a85-128">Por ejemplo, en ocasiones [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiene que cambiar las tablas del sistema de nuevas versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que admitan las nuevas funciones agregadas.</span><span class="sxs-lookup"><span data-stu-id="c3a85-128">For example, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sometimes has to change the system tables in new versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to support new functionality that is being added in that version.</span></span> <span data-ttu-id="c3a85-129">Las aplicaciones que utilizan instrucciones SELECT que hacen referencia directa a tablas del sistema suelen basarse en el formato anterior de estas tablas.</span><span class="sxs-lookup"><span data-stu-id="c3a85-129">Applications issuing SELECT statements that directly reference system tables are frequently dependent on the old format of the system tables.</span></span> <span data-ttu-id="c3a85-130">Los sitios tal vez no se puedan actualizar a una nueva versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hasta que hayan reescrito las aplicaciones que realizan operaciones de selección de las tablas del sistema.</span><span class="sxs-lookup"><span data-stu-id="c3a85-130">Sites may not be able to upgrade to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until they have rewritten applications that are selecting from system tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c3a85-131">tiene en cuenta los procedimientos almacenados del sistema, DDL y las interfaces publicadas de SQL-SMO, y trabaja para mantener la compatibilidad con versiones anteriores de estas interfaces.</span><span class="sxs-lookup"><span data-stu-id="c3a85-131">considers the system stored procedures, DDL, and SQL-SMO published interfaces, and works to maintain the backward compatibility of these interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c3a85-132">no admite la definición de desencadenadores en las tablas del sistema, debido a que podrían alterar el funcionamiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="c3a85-132">does not support triggers defined on the system tables, because they might modify the operation of the system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3a85-133">Las bases de datos del sistema no pueden residir en directorios de recursos compartidos UNC.</span><span class="sxs-lookup"><span data-stu-id="c3a85-133">System databases cannot reside on UNC share directories.</span></span>  
  
## <a name="viewing-system-database-data"></a><span data-ttu-id="c3a85-134">ver datos de bases de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="c3a85-134">Viewing System Database Data</span></span>  
 <span data-ttu-id="c3a85-135">No debe utilizar en sus programas instrucciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] que consulten directamente las tablas del sistema, a menos que ese sea el único modo de obtener la información que requiere la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3a85-135">You should not code [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that directly query the system tables, unless that is the only way to obtain the information that is required by the application.</span></span> <span data-ttu-id="c3a85-136">En su lugar, las aplicaciones deben obtener información de catálogo y del sistema mediante el uso de:</span><span class="sxs-lookup"><span data-stu-id="c3a85-136">Instead, applications should obtain catalog and system information by using the following:</span></span>  
  
-   <span data-ttu-id="c3a85-137">Vistas de catálogo del sistema</span><span class="sxs-lookup"><span data-stu-id="c3a85-137">System catalog views</span></span>  
  
-   <span data-ttu-id="c3a85-138">SQL-SMO.</span><span class="sxs-lookup"><span data-stu-id="c3a85-138">SQL-SMO</span></span>  
  
-   <span data-ttu-id="c3a85-139">Interfaz de Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="c3a85-139">Windows Management Instrumentation (WMI) interface</span></span>  
  
-   <span data-ttu-id="c3a85-140">Funciones de catálogo, métodos, atributos o propiedades de la API de datos usada en la aplicación, como ADO, OLE DB u ODBC.</span><span class="sxs-lookup"><span data-stu-id="c3a85-140">Catalog functions, methods, attributes, or properties of the data API used in the application, such as ADO, OLE DB, or ODBC.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="c3a85-141">procedimientos almacenados del sistema y funciones integradas.</span><span class="sxs-lookup"><span data-stu-id="c3a85-141">system stored procedures and built-in functions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c3a85-142">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c3a85-142">Related Tasks</span></span>  
 [<span data-ttu-id="c3a85-143">Realizar copias de seguridad y restaurar bases de datos del sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3a85-143">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="c3a85-144">Ocultar objetos del sistema en Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="c3a85-144">Hide System Objects in Object Explorer</span></span>](../../ssms/object/object-explorer.md)  
  
## <a name="related-content"></a><span data-ttu-id="c3a85-145">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="c3a85-145">Related Content</span></span>  
 [<span data-ttu-id="c3a85-146">Vistas de catálogo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3a85-146">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
 [<span data-ttu-id="c3a85-147">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="c3a85-147">Databases</span></span>](databases.md)  
  
  
