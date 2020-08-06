---
title: Otros problemas de actualización de replicación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system tables [SQL Server], replication
- passwords [SQL Server replication]
- versions [SQL Server replication]
- connections [SQL Server replication]
- scripts [SQL Server replication]
- ActiveX controls [SQL Server replication]
ms.assetid: 8a5e74be-4992-4f17-b20c-c3dce8f49329
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e8ce3f35ead9d3322c636462f682ef391703cfe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676317"
---
# <a name="other-replication-upgrade-issues"></a><span data-ttu-id="0e525-102">Otros problemas de actualización de replicación</span><span class="sxs-lookup"><span data-stu-id="0e525-102">Other Replication Upgrade Issues</span></span>
  <span data-ttu-id="0e525-103">En este tema se analiza una serie de problemas de actualización que el Asesor de actualizaciones no notifica.</span><span class="sxs-lookup"><span data-stu-id="0e525-103">This topic covers a number of upgrade issues that are not reported by Upgrade Advisor.</span></span>  
  
## <a name="versions-supported"></a><span data-ttu-id="0e525-104">Versiones admitidas</span><span class="sxs-lookup"><span data-stu-id="0e525-104">Versions Supported</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="0e525-105">admite la actualización de bases de datos replicadas de versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e525-105">supports upgrading replicated databases from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0e525-106">No es necesario detener la actividad en otros nodos mientras se actualiza un nodo.</span><span class="sxs-lookup"><span data-stu-id="0e525-106">You do not have to stop activity at other nodes while a node is being upgraded.</span></span> <span data-ttu-id="0e525-107">Asegúrese de cumplir las reglas relativas a las versiones admitidas en una topología.</span><span class="sxs-lookup"><span data-stu-id="0e525-107">Ensure that you adhere to the rules regarding which versions are supported in a topology.</span></span>  
  
 <span data-ttu-id="0e525-108">Cuando se usa la replicación entre versiones diferentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], normalmente se está limitado por las funciones de la versión más antigua que se está usando.</span><span class="sxs-lookup"><span data-stu-id="0e525-108">When you replicate between or among different versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you are usually limited to the functionality of the earliest version that is being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e525-109">Dado que el formato de almacenamiento en disco de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es el mismo en los entornos de 64 bits y de 32 bits, una topología de replicación puede combinar instancias del servidor que se ejecutan en un entorno de 32 bits e instancias del servidor que se ejecutan en un entorno de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="0e525-109">Because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on-disk storage format is the same in the 64-bit and 32-bit environments, a replication topology can combine server instances that run in a 32-bit environment and server instances that run in a 64-bit environment.</span></span>  
  
 <span data-ttu-id="0e525-110">Para todos los tipos de replicación, la versión del distribuidor no debe ser anterior a la versión del publicador.</span><span class="sxs-lookup"><span data-stu-id="0e525-110">For all types of replication, the Distributor version must be no earlier than the Publisher version.</span></span> <span data-ttu-id="0e525-111">(Con frecuencia, el distribuidor es la misma instancia que el publicador).</span><span class="sxs-lookup"><span data-stu-id="0e525-111">(Frequently, the Distributor is the same instance as the Publisher.)</span></span>  
  
 <span data-ttu-id="0e525-112">Para la replicación transaccional, un suscriptor de una publicación transaccional puede ser de cualquiera de las dos versiones del publicador.</span><span class="sxs-lookup"><span data-stu-id="0e525-112">For transactional replication, a Subscriber to a transactional publication can be any version within two versions of the Publisher version.</span></span>  
  
 <span data-ttu-id="0e525-113">Para la replicación de mezcla, un suscriptor para una publicación de combinación puede ser de cualquier versión que no sea posterior a la versión del publicador.</span><span class="sxs-lookup"><span data-stu-id="0e525-113">For merge replication, a Subscriber to a merge publication can be any version no later than the Publisher version.</span></span>  
  
## <a name="merge-replication-batches-changes"></a><span data-ttu-id="0e525-114">Cambios de lotes de replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="0e525-114">Merge Replication Batches Changes</span></span>  
 <span data-ttu-id="0e525-115">Los cambios realizados por el Agente de mezcla se ejecutan en lotes para mejorar el rendimiento; por lo tanto, se puede insertar, actualizar o eliminar más de una fila en una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="0e525-115">Changes that are made by the Merge Agent are batched to improve performance; therefore, more than one row can be inserted, updated, or deleted within a single statement.</span></span> <span data-ttu-id="0e525-116">Si las tablas publicadas en las bases de datos de publicaciones o suscripciones tienen desencadenadores, asegúrese de que estos pueden controlar inserciones, actualizaciones y eliminaciones en varias filas.</span><span class="sxs-lookup"><span data-stu-id="0e525-116">If any published tables in the publication or subscription databases have triggers, ensure that the triggers can handle multirow inserts, updates, and deletes.</span></span> <span data-ttu-id="0e525-117">Para obtener más información, vea "Consideraciones acerca de operaciones con varias filas para desencadenadores DML" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e525-117">For more information, see "Multirow Considerations for DML Triggers" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="activex-control-changes"></a><span data-ttu-id="0e525-118">Cambios de controles ActiveX</span><span class="sxs-lookup"><span data-stu-id="0e525-118">ActiveX Control Changes</span></span>  
 <span data-ttu-id="0e525-119">Se han realizado los cambios siguientes en los controles ActiveX de replicación:</span><span class="sxs-lookup"><span data-stu-id="0e525-119">The following changes have been made for replication ActiveX controls:</span></span>  
  
-   <span data-ttu-id="0e525-120">Todos los controles ActiveX están marcados como no seguros para scriptings e inicialización.</span><span class="sxs-lookup"><span data-stu-id="0e525-120">All ActiveX controls are marked as unsafe for scripting and initialization.</span></span>  
  
-   <span data-ttu-id="0e525-121">Se ha quitado el control ActiveX de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="0e525-121">The Snapshot ActiveX control has been dropped.</span></span> <span data-ttu-id="0e525-122">Puede crear y administrar instantáneas utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o mediante programación usando procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="0e525-122">You can create and manage snapshots by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or programmatically by using replication stored procedures.</span></span> <span data-ttu-id="0e525-123">Para obtener más información, vea los temas "Cómo crear y aplicar la instantánea inicial ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)])" y "Cómo crear la instantánea inicial (programación de la replicación con Transact-SQL)" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e525-123">For more information, see the topics "How to: Create and Apply the Initial Snapshot ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)])" and "How to: Create the Initial Snapshot (Replication Transact-SQL Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
-   <span data-ttu-id="0e525-124">El control ActiveX de distribución y el control ActiveX de mezcla han quedado desusados.</span><span class="sxs-lookup"><span data-stu-id="0e525-124">The Distribution ActiveX control and Merge ActiveX control have been deprecated.</span></span> <span data-ttu-id="0e525-125">Se proporciona una funcionalidad similar para las aplicaciones de código administrado mediante Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="0e525-125">Similar functionality is provided for managed code applications using Replication Management Objects (RMO).</span></span> <span data-ttu-id="0e525-126">Para obtener más información, vea "Sincronizar suscripciones (Programación con RMO)" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e525-126">For more information, see "Synchronizing Subscriptions (RMO Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e525-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e525-127">See Also</span></span>  
 [<span data-ttu-id="0e525-128">Problemas de actualización de replicación</span><span class="sxs-lookup"><span data-stu-id="0e525-128">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
