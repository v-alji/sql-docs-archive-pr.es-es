---
title: Acciones comunes que requieren una copia de seguridad actualizada | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], actions requiring a backup
- restoring [SQL Server replication], actions requiring a backup
- backups [SQL Server replication], actions requiring a backup
ms.assetid: a5975bf4-183e-42e3-b7d1-ad02f89d2e1d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3eb10bdca8ee188f7b322a46665c38129d57052b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744635"
---
# <a name="common-actions-requiring-an-updated-backup"></a><span data-ttu-id="af30e-102">Acciones comunes que requieren una copia de seguridad actualizada</span><span class="sxs-lookup"><span data-stu-id="af30e-102">Common Actions Requiring an Updated Backup</span></span>
  <span data-ttu-id="af30e-103">Si realiza regularmente copias de seguridad de registros, éstas deben capturar todos los cambios relacionados con la replicación.</span><span class="sxs-lookup"><span data-stu-id="af30e-103">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="af30e-104">Si no realiza copias de seguridad de registros, cree una copia de seguridad de las bases de datos de publicaciones, distribución, suscripciones, **msdb**y **maestra** después de realizar modificaciones en la topología o en el esquema de replicación.</span><span class="sxs-lookup"><span data-stu-id="af30e-104">If you don't perform log backups, perform a backup of the publication, distribution, subscription, **msdb**, and **master** databases after making modifications to your replication schema or topology.</span></span>  
  
## <a name="publication-database"></a><span data-ttu-id="af30e-105">Base de datos de publicaciones</span><span class="sxs-lookup"><span data-stu-id="af30e-105">Publication Database</span></span>  
 <span data-ttu-id="af30e-106">Haga una copia de seguridad de la base de datos de publicaciones después de:</span><span class="sxs-lookup"><span data-stu-id="af30e-106">Backup the publication database after:</span></span>  
  
-   <span data-ttu-id="af30e-107">Crear nuevas publicaciones.</span><span class="sxs-lookup"><span data-stu-id="af30e-107">Creating new publications.</span></span>  
  
-   <span data-ttu-id="af30e-108">Modificar una propiedad de publicación, incluido el filtro.</span><span class="sxs-lookup"><span data-stu-id="af30e-108">Changing any publication property, including filtering.</span></span>  
  
-   <span data-ttu-id="af30e-109">Agregar artículos a una publicación ya existente.</span><span class="sxs-lookup"><span data-stu-id="af30e-109">Adding articles to an existing publication.</span></span>  
  
-   <span data-ttu-id="af30e-110">Reinicializar las suscripciones de todas las publicaciones.</span><span class="sxs-lookup"><span data-stu-id="af30e-110">Performing a publication-wide reinitialization of subscriptions.</span></span>  
  
-   <span data-ttu-id="af30e-111">Realizar cambios de esquema en una tabla publicada.</span><span class="sxs-lookup"><span data-stu-id="af30e-111">Making a schema change on a published table.</span></span>  
  
-   <span data-ttu-id="af30e-112">Realizar la ejecución de script a petición con [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="af30e-112">Performing on-demand script execution with [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span>  
  
-   <span data-ttu-id="af30e-113">Cambiar cualquier propiedad de un artículo.</span><span class="sxs-lookup"><span data-stu-id="af30e-113">Changing any article property.</span></span>  
  
-   <span data-ttu-id="af30e-114">Quitar publicaciones.</span><span class="sxs-lookup"><span data-stu-id="af30e-114">Dropping any publications.</span></span>  
  
-   <span data-ttu-id="af30e-115">Quitar artículos.</span><span class="sxs-lookup"><span data-stu-id="af30e-115">Dropping any articles.</span></span>  
  
-   <span data-ttu-id="af30e-116">Deshabilitar la replicación.</span><span class="sxs-lookup"><span data-stu-id="af30e-116">Disabling replication.</span></span>  
  
## <a name="distribution-database"></a><span data-ttu-id="af30e-117">Base de datos de distribución</span><span class="sxs-lookup"><span data-stu-id="af30e-117">Distribution Database</span></span>  
 <span data-ttu-id="af30e-118">Haga una copia de seguridad de la base de datos de distribución después de:</span><span class="sxs-lookup"><span data-stu-id="af30e-118">Backup the distribution database after:</span></span>  
  
-   <span data-ttu-id="af30e-119">Crear o modificar perfiles de agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="af30e-119">Creating or modifying replication agent profiles.</span></span>  
  
-   <span data-ttu-id="af30e-120">Modificar parámetros de un perfil de agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="af30e-120">Modifying replication agent profile parameters.</span></span>  
  
-   <span data-ttu-id="af30e-121">Cambiar las propiedades del agente de replicación (incluidas las programaciones) para las suscripciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="af30e-121">Changing the replication agent properties (including schedules) for any push subscriptions.</span></span>  
  
-   <span data-ttu-id="af30e-122">La función de administración automática de intervalos de identidades asigna un nuevo intervalo de identidades.</span><span class="sxs-lookup"><span data-stu-id="af30e-122">A new range of identities is assigned by the automatic identity range management feature.</span></span>  
  
## <a name="subscription-database"></a><span data-ttu-id="af30e-123">Base de datos de suscripciones</span><span class="sxs-lookup"><span data-stu-id="af30e-123">Subscription Database</span></span>  
 <span data-ttu-id="af30e-124">Haga una copia de seguridad de la base de datos de suscripciones después de:</span><span class="sxs-lookup"><span data-stu-id="af30e-124">Backup the subscription database after:</span></span>  
  
-   <span data-ttu-id="af30e-125">Cambiar una propiedad de suscripción.</span><span class="sxs-lookup"><span data-stu-id="af30e-125">Changing any subscription property.</span></span>  
  
-   <span data-ttu-id="af30e-126">Cambiar la prioridad de una suscripción de mezcla en el publicador.</span><span class="sxs-lookup"><span data-stu-id="af30e-126">Changing the priority for a merge subscription at the Publisher.</span></span>  
  
-   <span data-ttu-id="af30e-127">Quitar suscripciones.</span><span class="sxs-lookup"><span data-stu-id="af30e-127">Dropping any subscriptions.</span></span>  
  
-   <span data-ttu-id="af30e-128">Deshabilitar la replicación.</span><span class="sxs-lookup"><span data-stu-id="af30e-128">Disabling replication.</span></span>  
  
## <a name="msdb-database"></a><span data-ttu-id="af30e-129">Base de datos msdb</span><span class="sxs-lookup"><span data-stu-id="af30e-129">msdb Database</span></span>  
 <span data-ttu-id="af30e-130">Cree una copia de seguridad de la base de datos **msdb** del sistema en el nodo apropiado después de:</span><span class="sxs-lookup"><span data-stu-id="af30e-130">Backup the **msdb** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="af30e-131">Habilitar o deshabilitar la replicación.</span><span class="sxs-lookup"><span data-stu-id="af30e-131">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="af30e-132">Agregar o quitar una base de datos de distribución (en el distribuidor).</span><span class="sxs-lookup"><span data-stu-id="af30e-132">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="af30e-133">Habilitar o deshabilitar la publicación de una base de datos (en el publicador).</span><span class="sxs-lookup"><span data-stu-id="af30e-133">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="af30e-134">Crear o modificar perfiles de agente de replicación (en el distribuidor).</span><span class="sxs-lookup"><span data-stu-id="af30e-134">Creating or modifying replication agent profiles (at the Distributor).</span></span>  
  
-   <span data-ttu-id="af30e-135">Modificar parámetros del perfil de agente de replicación (en el distribuidor).</span><span class="sxs-lookup"><span data-stu-id="af30e-135">Modifying any replication agent profile parameters (at the Distributor).</span></span>  
  
-   <span data-ttu-id="af30e-136">Cambiar las propiedades del agente de replicación (incluidas las programaciones) para las suscripciones de inserción (en el distribuidor).</span><span class="sxs-lookup"><span data-stu-id="af30e-136">Changing the replication agent properties (including schedules) for any push subscriptions (at the Distributor).</span></span>  
  
-   <span data-ttu-id="af30e-137">Cambiar las propiedades del agente de replicación (incluidas las programaciones) para las suscripciones de extracción (en el suscriptor).</span><span class="sxs-lookup"><span data-stu-id="af30e-137">Changing the replication agent properties (including schedules) for any pull subscriptions (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="af30e-138">Crear un paquete DTS asociado con una publicación transaccional que utilice suscripciones transformables (en el distribuidor y en el suscriptor).</span><span class="sxs-lookup"><span data-stu-id="af30e-138">Creating a DTS package associated with a transactional publication that uses transformable subscriptions (at the Distributor and Subscriber).</span></span>  
  
-   <span data-ttu-id="af30e-139">Agregar o quitar una suscripción transformable (en el distribuidor y en el suscriptor).</span><span class="sxs-lookup"><span data-stu-id="af30e-139">Adding or dropping a transformable subscription (at the Distributor and Subscriber).</span></span>  
  
## <a name="master-database"></a><span data-ttu-id="af30e-140">Base de datos maestra</span><span class="sxs-lookup"><span data-stu-id="af30e-140">master Database</span></span>  
 <span data-ttu-id="af30e-141">Cree una copia de seguridad de la base de datos del sistema **mestra** en el nodo apropiado después de:</span><span class="sxs-lookup"><span data-stu-id="af30e-141">Backup the **master** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="af30e-142">Habilitar o deshabilitar la replicación.</span><span class="sxs-lookup"><span data-stu-id="af30e-142">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="af30e-143">Agregar o quitar una base de datos de distribución (en el distribuidor).</span><span class="sxs-lookup"><span data-stu-id="af30e-143">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="af30e-144">Habilitar o deshabilitar la publicación de una base de datos (en el publicador).</span><span class="sxs-lookup"><span data-stu-id="af30e-144">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="af30e-145">Agregar la primera o quitar la última publicación en una base de datos (en el publicador).</span><span class="sxs-lookup"><span data-stu-id="af30e-145">Adding the first or dropping the last publication in any database (at the Publisher).</span></span>  
  
-   <span data-ttu-id="af30e-146">Agregar la primera o quitar la última suscripción en una base de datos (en el suscriptor).</span><span class="sxs-lookup"><span data-stu-id="af30e-146">Adding the first or dropping the last subscription in any database (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="af30e-147">Habilitar o deshabilitar un publicador en un publicador de distribución (en el publicador y el distribuidor).</span><span class="sxs-lookup"><span data-stu-id="af30e-147">Enabling or disabling a Publisher at a Distribution Publisher (at the Publisher and Distributor).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af30e-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af30e-148">See Also</span></span>  
 <span data-ttu-id="af30e-149">[Realizar copias de seguridad y restaurar bases de datos de SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="af30e-149">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="af30e-150">Hacer copias de seguridad y restaurar bases de datos replicadas</span><span class="sxs-lookup"><span data-stu-id="af30e-150">Back Up and Restore Replicated Databases</span></span>](back-up-and-restore-replicated-databases.md)  
  
  
