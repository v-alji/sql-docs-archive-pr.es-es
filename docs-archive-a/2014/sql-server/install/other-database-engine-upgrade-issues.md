---
title: Otros problemas de actualización de Motor de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], upgrading
ms.assetid: 78a1d8e8-fa97-476f-8777-84617d145340
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db496112fc975304bb2d7da9d9ea1c52e6dd8bec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670762"
---
# <a name="other-database-engine-upgrade-issues"></a><span data-ttu-id="363cc-102">Otros problemas de actualización del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="363cc-102">Other Database Engine Upgrade Issues</span></span>
  <span data-ttu-id="363cc-103">La versión actual del Asesor de actualizaciones no podrá detectar los siguientes problemas de actualización.</span><span class="sxs-lookup"><span data-stu-id="363cc-103">The following upgrade issues cannot be detected by the current version of Upgrade Advisor.</span></span> <span data-ttu-id="363cc-104">Examine los problemas enumerados a continuación para evaluar su posible impacto en los sistemas.</span><span class="sxs-lookup"><span data-stu-id="363cc-104">Review the issues listed below to evaluate their potential impact to your systems.</span></span>  
  
## <a name="multiple-database-engine-deprecated-features"></a><span data-ttu-id="363cc-105">Varias características desusadas del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="363cc-105">Multiple Database Engine Deprecated Features</span></span>  
 <span data-ttu-id="363cc-106">Las siguientes instrucciones u opciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] están en desuso:</span><span class="sxs-lookup"><span data-stu-id="363cc-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or options are deprecated:</span></span>  
  
-   <span data-ttu-id="363cc-107">Las opciones NO_LOG y TRUNCATE_ONLY de BACKUP LOG</span><span class="sxs-lookup"><span data-stu-id="363cc-107">NO_LOG and TRUNCATE_ONLY options of BACKUP LOG</span></span>  
  
-   <span data-ttu-id="363cc-108">BACKUP TRANSACTION </span><span class="sxs-lookup"><span data-stu-id="363cc-108">BACKUP TRANSACTION</span></span>  
  
-   <span data-ttu-id="363cc-109">RESTORE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="363cc-109">RESTORE TRANSACTION</span></span>  
  
-   <span data-ttu-id="363cc-110">DUMP</span><span class="sxs-lookup"><span data-stu-id="363cc-110">DUMP</span></span>  
  
-   <span data-ttu-id="363cc-111">LOAD</span><span class="sxs-lookup"><span data-stu-id="363cc-111">LOAD</span></span>  
  
-   <span data-ttu-id="363cc-112">DBCC CONCURRENCYVIOLATION</span><span class="sxs-lookup"><span data-stu-id="363cc-112">DBCC CONCURRENCYVIOLATION</span></span>  
  
-   <span data-ttu-id="363cc-113">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="363cc-113">sp_addalias</span></span>  
  
-   <span data-ttu-id="363cc-114">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="363cc-114">sp_addgroup</span></span>  
  
-   <span data-ttu-id="363cc-115">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="363cc-115">sp_changegroup</span></span>  
  
-   <span data-ttu-id="363cc-116">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="363cc-116">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="363cc-117">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="363cc-117">sp_helpgroup</span></span>  
  
-   <span data-ttu-id="363cc-118">syssegments</span><span class="sxs-lookup"><span data-stu-id="363cc-118">syssegments</span></span>  
  
 <span data-ttu-id="363cc-119">El uso del protocolo VIA para conectarse a [!INCLUDE[ssDE](../../includes/ssde-md.md)] está desusado.</span><span class="sxs-lookup"><span data-stu-id="363cc-119">Use of the VIA protocol to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is deprecated.</span></span>  
  
## <a name="new-data-types"></a><span data-ttu-id="363cc-120">Nuevos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="363cc-120">New Data Types</span></span>  
 <span data-ttu-id="363cc-121">Los siguientes son los tipos del sistema reservados.</span><span class="sxs-lookup"><span data-stu-id="363cc-121">The following will be reserved system types.</span></span> <span data-ttu-id="363cc-122">Cambie el nombre de los tipos definidos por el usuario que entran en conflicto, ya sea antes o después de llevar a cabo la actualización.</span><span class="sxs-lookup"><span data-stu-id="363cc-122">Rename the existing conflicting user defined types either before or after upgrade.</span></span>  
  
-   <span data-ttu-id="363cc-123">Geography</span><span class="sxs-lookup"><span data-stu-id="363cc-123">Geography</span></span>  
  
-   <span data-ttu-id="363cc-124">Geometría</span><span class="sxs-lookup"><span data-stu-id="363cc-124">Geometry</span></span>  
  
-   <span data-ttu-id="363cc-125">Datetime2</span><span class="sxs-lookup"><span data-stu-id="363cc-125">Datetime2</span></span>  
  
-   <span data-ttu-id="363cc-126">HierarchyID</span><span class="sxs-lookup"><span data-stu-id="363cc-126">HierarchyID</span></span>  
  
## <a name="target-table-of-the-output-into-clause-cannot-have-any-defined-triggers"></a><span data-ttu-id="363cc-127">La tabla de destino de la cláusula OUTPUT INTO no puede tener ningún desencadenador definido</span><span class="sxs-lookup"><span data-stu-id="363cc-127">Target Table of the OUTPUT INTO Clause Cannot Have Any Defined Triggers</span></span>  
 <span data-ttu-id="363cc-128">No se admite la salida en una tabla de destino cuando la tabla tiene ningún desencadenador habilitado.</span><span class="sxs-lookup"><span data-stu-id="363cc-128">OUTPUT INTO a target table when the table has any enabled triggers is not supported.</span></span>  
  
## <a name="compile-time-error-for-udfs-when-the-target-of-an-output-into-clause-is-a-table"></a><span data-ttu-id="363cc-129">Error en tiempo de compilación con los UDF cuando el destino de una cláusula OUTPUT INTO sea una tabla</span><span class="sxs-lookup"><span data-stu-id="363cc-129">Compile Time Error for UDFs When the Target of an OUTPUT INTO Clause is a Table</span></span>  
 <span data-ttu-id="363cc-130">Las funciones definidas por el usuario (UDF) no se pueden utilizar para realizar acciones que modifiquen el estado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="363cc-130">User-defined functions (UDF) cannot be used to perform actions that modify the database state.</span></span> <span data-ttu-id="363cc-131">Por ejemplo, un UDF no puede realizar ninguna acción DDL (CREATE/ALTER/DROP) o DML (INSERT/UPDATE/DELETE) sobre ningún objeto, excepto para variables de tabla.</span><span class="sxs-lookup"><span data-stu-id="363cc-131">For example, a UDF cannot perform any DDL (CREATE/ALTER/DROP) or DML (INSERT/UPDATE/DELETE) actions on any objects, except for table variables.</span></span>  
  
## <a name="merge-is-a-reserved-keyword"></a><span data-ttu-id="363cc-132">MERGE es una palabra clave reservada.</span><span class="sxs-lookup"><span data-stu-id="363cc-132">MERGE is a Reserved Keyword</span></span>  
 <span data-ttu-id="363cc-133">MERGE es ahora una palabra clave totalmente reservada.</span><span class="sxs-lookup"><span data-stu-id="363cc-133">MERGE is now a fully-reserved keyword.</span></span> <span data-ttu-id="363cc-134">Las aplicaciones ya no pueden tener objetos (tablas, columnas, etc.) denominados MERGE.</span><span class="sxs-lookup"><span data-stu-id="363cc-134">Applications can no longer have objects (table, column, etc.) called MERGE.</span></span>  
  
## <a name="rename-cdc-schema"></a><span data-ttu-id="363cc-135">Cambiar el nombre del esquema CDC</span><span class="sxs-lookup"><span data-stu-id="363cc-135">Rename CDC Schema</span></span>  
 <span data-ttu-id="363cc-136">Hay un nombre de esquema denominado CDC.</span><span class="sxs-lookup"><span data-stu-id="363cc-136">There is a schema name called CDC.</span></span> <span data-ttu-id="363cc-137">Este nombre de esquema no se puede usar si la **captura de datos modificados** está habilitada para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="363cc-137">This schema name cannot be in used if **Change Data Capture** is enabled for the database.</span></span>  
  
 <span data-ttu-id="363cc-138">Debe quitar el esquema CDC antes de habilitar la **captura de datos modificados** para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="363cc-138">You must drop the CDC schema before you enable **Change Data Capture** for the database.</span></span> <span data-ttu-id="363cc-139">Este paso se puede hacer antes o después de la actualización.</span><span class="sxs-lookup"><span data-stu-id="363cc-139">This step can be done before or after the upgrade.</span></span> <span data-ttu-id="363cc-140">Para eliminar el esquema, siga los pasos que se detallan a continuación:</span><span class="sxs-lookup"><span data-stu-id="363cc-140">To drop the schema, use the following steps:</span></span>  
  
1.  <span data-ttu-id="363cc-141">Transfiera los objetos del esquema CDC a un nuevo nombre de esquema utilizando ALTER SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="363cc-141">Transfer the objects from CDC schema to a new schema name using ALTER SCHEMA.</span></span>  
  
2.  <span data-ttu-id="363cc-142">Compruebe los permisos para los objetos en el nuevo esquema.</span><span class="sxs-lookup"><span data-stu-id="363cc-142">Verify permissions for the objects in the new schema.</span></span>  
  
3.  <span data-ttu-id="363cc-143">Realice las modificaciones necesarias en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="363cc-143">Make necessary modifications to the application.</span></span>  
  
4.  <span data-ttu-id="363cc-144">Elimine el esquema CDC utilizando DROP SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="363cc-144">Drop the CDC schema using DROP SCHEMA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="363cc-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="363cc-145">See Also</span></span>  
 [<span data-ttu-id="363cc-146">Problemas de actualización del motor de la base de datos</span><span class="sxs-lookup"><span data-stu-id="363cc-146">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
  
