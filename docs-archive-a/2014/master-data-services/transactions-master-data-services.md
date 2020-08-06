---
title: Transacciones (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], about transactions
- transactions [Master Data Services]
ms.assetid: 4cd2fa6f-9c76-4b7a-ae18-d4e5fd2f03f5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c693b550e0c1adb8f5910d99c7125c85f41abb8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749365"
---
# <a name="transactions-master-data-services"></a><span data-ttu-id="637ff-102">Transacciones (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="637ff-102">Transactions (Master Data Services)</span></span>
  <span data-ttu-id="637ff-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], se registra una transacción cada vez que se realiza una acción en un miembro.</span><span class="sxs-lookup"><span data-stu-id="637ff-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a transaction is recorded each time action is taken on a member.</span></span> <span data-ttu-id="637ff-104">Todos los usuarios pueden ver las transacciones y los administradores pueden invertirlas.</span><span class="sxs-lookup"><span data-stu-id="637ff-104">Transactions can be viewed by all users and reversed by administrators.</span></span> <span data-ttu-id="637ff-105">Las transacciones muestran la fecha, la hora, el usuario que aplicó la acción y otros detalles.</span><span class="sxs-lookup"><span data-stu-id="637ff-105">Transactions show the date, time, and user who took the action, along with other details.</span></span> <span data-ttu-id="637ff-106">Los usuarios pueden agregar una anotación a una transacción para indicar por qué tuvo lugar una transacción.</span><span class="sxs-lookup"><span data-stu-id="637ff-106">Users can add an annotation to a transaction, to indicate why a transaction took place.</span></span>  
  
## <a name="when-transaction-are-recorded"></a><span data-ttu-id="637ff-107">Cuándo se registran las transacciones</span><span class="sxs-lookup"><span data-stu-id="637ff-107">When Transaction Are Recorded</span></span>  
 <span data-ttu-id="637ff-108">Las transacciones se registran cuando los miembros:</span><span class="sxs-lookup"><span data-stu-id="637ff-108">Transactions are recorded when members:</span></span>  
  
-   <span data-ttu-id="637ff-109">se crean, eliminan o reactivan.</span><span class="sxs-lookup"><span data-stu-id="637ff-109">Are created, deleted, or reactivated.</span></span>  
  
-   <span data-ttu-id="637ff-110">se les cambian los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="637ff-110">Have attribute values changed.</span></span>  
  
-   <span data-ttu-id="637ff-111">se cambian de lugar en una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="637ff-111">Are moved in a hierarchy.</span></span>  
  
 <span data-ttu-id="637ff-112">No se graban las transacciones cuando las reglas de negocios cambian los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="637ff-112">Transactions are not recorded when business rules change attribute values.</span></span>  
  
## <a name="view-and-manage-transactions"></a><span data-ttu-id="637ff-113">Ver y administrar transacciones</span><span class="sxs-lookup"><span data-stu-id="637ff-113">View and Manage Transactions</span></span>  
 <span data-ttu-id="637ff-114">En el área funcional del **Explorador** , puede ver y anotar (agregar comentarios a) las transacciones que haya realizado por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="637ff-114">In the **Explorer** functional area, you can view and annotate (add comments to) the transactions that you made yourself.</span></span>  
  
 <span data-ttu-id="637ff-115">En el área funcional de **Administración de versiones** , los administradores pueden ver todas las transacciones de todos los usuarios para los modelos a los que tienen acceso e invertirlas.</span><span class="sxs-lookup"><span data-stu-id="637ff-115">In the **Version Management** functional area, administrators can view all transactions for all users for the models they have access to, and reverse any of these transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="637ff-116">Los administradores pueden ver todas las transacciones de todos los usuarios siempre y cuando no tengan aplicado el nivel de permiso de solo lectura en el área funcional **Administración de versiones**.</span><span class="sxs-lookup"><span data-stu-id="637ff-116">Administrators can view all transactions for all users as long as they don't have the read-only permission level applied in the **Version Management** functional area .</span></span> <span data-ttu-id="637ff-117">Por ejemplo, si se establece el nivel de permiso de solo lectura y el nivel de permiso de actualización para el administrador, este no podrá ver otras transacciones de usuario porque el permiso de solo lectura tendrá prioridad sobre el permiso de actualización.</span><span class="sxs-lookup"><span data-stu-id="637ff-117">For example, if the read-only permission and update permission level is set for the administrator, the administrator will not be able to see other user transactions because the read-only permission will take precedence over the update permission.</span></span>

## <a name="system-settings"></a><span data-ttu-id="637ff-118">Configuración del sistema</span><span class="sxs-lookup"><span data-stu-id="637ff-118">System Settings</span></span>  
 <span data-ttu-id="637ff-119">Hay un valor en [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] que hace que las transacciones se graben o no cuando se cargan registros de almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="637ff-119">There is a setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affects whether or not transactions are recorded when records are staged.</span></span> <span data-ttu-id="637ff-120">Este valor solo afecta a SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="637ff-120">This setting affects SQL Server 2008 R2 only.</span></span> <span data-ttu-id="637ff-121">Puede ajustar este valor en [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] o directamente en la tabla Configuración del sistema de la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="637ff-121">You can adjust this setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="637ff-122">Para obtener más información, vea [Configuración del sistema &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="637ff-122">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
 <span data-ttu-id="637ff-123">Al importar los datos en esta versión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], puede especificar si registrar o no las transacciones al iniciar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="637ff-123">When importing data in this version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify whether or not to log transactions when initiating the stored procedure.</span></span> <span data-ttu-id="637ff-124">Para obtener más información, consulte [Procedimiento almacenado de almacenamiento provisional &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="637ff-124">For more information, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="concurrency"></a><span data-ttu-id="637ff-125">Simultaneidad</span><span class="sxs-lookup"><span data-stu-id="637ff-125">Concurrency</span></span>  
 <span data-ttu-id="637ff-126">Si un valor de entidad determinado se muestra de forma simultánea en más de una sesión del Explorador, es posible que se efectúen modificaciones en paralelo en el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="637ff-126">If a particular entity value is shown simultaneously in more than one Explorer session, concurrent edits to the same value are possible.</span></span> <span data-ttu-id="637ff-127">MDS no detecta las modificaciones simultáneas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="637ff-127">Concurrent edits will not be detected automatically by MDS.</span></span> <span data-ttu-id="637ff-128">Esto puede producirse cuando hay varios usuarios que están utilizando MDS Explorer en el explorador web desde varias sesiones, por ejemplo, desde diversos equipos, diversas pestañas o ventanas del explorador o desde múltiples cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="637ff-128">This can occur when multiple users use the MDS Explorer in the Web browser from multiple sessions, for example from multiple computers, multiple browser tabs or windows, or multiple user accounts.</span></span>  
  
 <span data-ttu-id="637ff-129">Varios usuarios pueden actualizar los mismos valores de entidad sin que se produzcan errores pese a que estén habilitadas transacciones.</span><span class="sxs-lookup"><span data-stu-id="637ff-129">More than one user can update the same entity values without error despite transactions being enabled.</span></span> <span data-ttu-id="637ff-130">Por lo general, prevalecerá la última modificación a un valor en una secuencia temporal.</span><span class="sxs-lookup"><span data-stu-id="637ff-130">Typically the last edit to the value in a sequence of time will take precedence.</span></span> <span data-ttu-id="637ff-131">El conflicto de modificación duplicada se puede observar en el historial de transacciones y lo puede corregir el administrador manualmente.</span><span class="sxs-lookup"><span data-stu-id="637ff-131">The duplicate edit conflict can be manually observed in the transaction history and can be reversed manually by the administrator.</span></span> <span data-ttu-id="637ff-132">El historial de transacciones mostrará las transacciones individuales para **Valor anterior** y **Valor nuevo** para el atributo relevante en cada sesión, pero no solucionará automáticamente el conflicto cuando haya varios **Valores nuevos** para el mismo valor antiguo.</span><span class="sxs-lookup"><span data-stu-id="637ff-132">The transaction history will show the individual transactions for the **Prior value** and **New value** for the attribute in question from each session, but will not automatically resolve the conflict when multiple **New Values** exist for the same old value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="637ff-133">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="637ff-133">Related Tasks</span></span>  
  
|<span data-ttu-id="637ff-134">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="637ff-134">Task Description</span></span>|<span data-ttu-id="637ff-135">Tema</span><span class="sxs-lookup"><span data-stu-id="637ff-135">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="637ff-136">Deshacer una acción invirtiendo una transacción (solo administradores).</span><span class="sxs-lookup"><span data-stu-id="637ff-136">Undo an action by reversing a transaction (administrators only).</span></span>|[<span data-ttu-id="637ff-137">Invertir una transacción &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="637ff-137">Reverse a Transaction &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reverse-a-transaction-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="637ff-138">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="637ff-138">Related Content</span></span>  
  
-   [<span data-ttu-id="637ff-139">Administradores &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="637ff-139">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
-   [<span data-ttu-id="637ff-140">Anotaciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="637ff-140">Annotations &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/annotations-master-data-services.md)  
  
  
