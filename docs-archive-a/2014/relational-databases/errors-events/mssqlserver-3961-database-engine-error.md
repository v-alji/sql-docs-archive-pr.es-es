---
title: MSSQLSERVER_3961 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3961 (Database Engine error)
ms.assetid: 3bbc6965-6445-400c-940a-2d85b037513f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f55be9288b3c2e559633d0f67709829466fc8815
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676510"
---
# <a name="mssqlserver_3961"></a><span data-ttu-id="d3237-102">MSSQLSERVER_3961</span><span class="sxs-lookup"><span data-stu-id="d3237-102">MSSQLSERVER_3961</span></span>
    
## <a name="details"></a><span data-ttu-id="d3237-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d3237-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3237-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d3237-104">Product Name</span></span>|<span data-ttu-id="d3237-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3237-105">SQL Server</span></span>|  
|<span data-ttu-id="d3237-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d3237-106">Event ID</span></span>|<span data-ttu-id="d3237-107">3961</span><span class="sxs-lookup"><span data-stu-id="d3237-107">3961</span></span>|  
|<span data-ttu-id="d3237-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d3237-108">Event Source</span></span>|<span data-ttu-id="d3237-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d3237-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d3237-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d3237-110">Component</span></span>|<span data-ttu-id="d3237-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d3237-111">SQLEngine</span></span>|  
|<span data-ttu-id="d3237-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d3237-112">Symbolic Name</span></span>|<span data-ttu-id="d3237-113">XACT_METADATA_INVALID</span><span class="sxs-lookup"><span data-stu-id="d3237-113">XACT_METADATA_INVALID</span></span>|  
|<span data-ttu-id="d3237-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d3237-114">Message Text</span></span>|<span data-ttu-id="d3237-115">Error de la transacción de aislamiento de instantánea en la base de datos '%. \* ls' porque el objeto al que tuvo acceso la instrucción ha sido modificado por una instrucción DDL de otra transacción simultánea desde el inicio de esta transacción.</span><span class="sxs-lookup"><span data-stu-id="d3237-115">Snapshot isolation transaction failed in database '%.\*ls' because the object accessed by the statement has been modified by a DDL statement in another concurrent transaction since the start of this transaction.</span></span>  <span data-ttu-id="d3237-116">Está deshabilitada porque los metadatos no tienen versiones.</span><span class="sxs-lookup"><span data-stu-id="d3237-116">It is disallowed because the metadata is not versioned.</span></span> <span data-ttu-id="d3237-117">Una actualización simultánea de los metadatos puede dar lugar a incoherencias si se combina con el aislamiento de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="d3237-117">A concurrent update to metadata can lead to inconsistency if mixed with snapshot isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d3237-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="d3237-118">Explanation</span></span>  
 <span data-ttu-id="d3237-119">Este error se puede producir durante una consulta de metadatos en una transacción de aislamiento de la instantánea si una instrucción DDL simultánea actualiza los metadatos a los que esta transacción está accediendo.</span><span class="sxs-lookup"><span data-stu-id="d3237-119">This error can occur if you are querying metadata under snapshot isolation and there is a concurrent DDL statement that updates the metadata that is being accessed under snapshot isolation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d3237-120">no permite controlar las versiones de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="d3237-120">does not support versioning of metadata.</span></span> <span data-ttu-id="d3237-121">Por este motivo, hay restricciones en las operaciones de DDL que se pueden realizar en una transacción explícita que se ejecuta con aislamiento de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="d3237-121">For this reason, there are restrictions on what DDL operations can be performed within an explicit transaction running under snapshot isolation.</span></span> <span data-ttu-id="d3237-122">Una transacción implícita, por definición, es una única instrucción que hace que sea posible aplicar la semántica del aislamiento de la instantánea incluso con instrucciones DDL.</span><span class="sxs-lookup"><span data-stu-id="d3237-122">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span> <span data-ttu-id="d3237-123">No se permiten las siguientes instrucciones DDL en el aislamiento de instantánea después de una instrucción BEGIN TRANSACTION: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME o cualquier instrucción de DDL de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d3237-123">The following DDL statements are not permitted under snapshot isolation after a BEGIN TRANSACTION statement: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME, or any common language runtime (CLR) DDL statement.</span></span> <span data-ttu-id="d3237-124">Estas instrucciones se permiten cuando usa el aislamiento de la instantánea en transacciones implícitas.</span><span class="sxs-lookup"><span data-stu-id="d3237-124">These statements are permitted when you are using snapshot isolation within implicit transactions.</span></span> <span data-ttu-id="d3237-125">Una transacción implícita, por definición, es una única instrucción que hace que sea posible aplicar la semántica del aislamiento de la instantánea incluso con instrucciones DDL.</span><span class="sxs-lookup"><span data-stu-id="d3237-125">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d3237-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d3237-126">User Action</span></span>  
 <span data-ttu-id="d3237-127">Antes de consultar los metadatos, cambie el nivel de aislamiento a un nivel que no sea de aislamiento como, por ejemplo, lectura confirmada.</span><span class="sxs-lookup"><span data-stu-id="d3237-127">Change the snapshot isolation level to a non-snapshot isolation level such as read committed before querying metadata.</span></span>  
  
  
