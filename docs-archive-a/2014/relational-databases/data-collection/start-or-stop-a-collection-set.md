---
title: Iniciar o detener un conjunto de recopilación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection sets [SQL Server], stopping
- collection sets [SQL Server], starting
ms.assetid: 48a7b2fe-6bc3-4278-a7ec-1babc1290345
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e37d4b2edcd7a6e048c405b072bcbf9b1fef78c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676015"
---
# <a name="start-or-stop-a-collection-set"></a><span data-ttu-id="f71eb-102">Iniciar o detener un conjunto de recopilación</span><span class="sxs-lookup"><span data-stu-id="f71eb-102">Start or Stop a Collection Set</span></span>
  <span data-ttu-id="f71eb-103">En este tema se describe cómo iniciar o detener un conjunto de recopilación en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f71eb-103">This topic describes how to start or stop a collection set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f71eb-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f71eb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f71eb-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f71eb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f71eb-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f71eb-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f71eb-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f71eb-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="f71eb-108">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="f71eb-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f71eb-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f71eb-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f71eb-110">**Para iniciar o detener un conjunto de recopilación, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="f71eb-110">**To start or stop a collection set, using:**</span></span>  
  
     [<span data-ttu-id="f71eb-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f71eb-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f71eb-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f71eb-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f71eb-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f71eb-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f71eb-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f71eb-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f71eb-115">Los procedimientos almacenados y las vistas de catálogo del recopilador de datos se almacenan en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="f71eb-115">Data Collector stored procedures and catalog views are stored in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="f71eb-116">A diferencia de los procedimientos almacenados normales, los parámetros de los procedimientos del  recopilador de datos deben escribirse de forma precisa y no admiten la conversión automática de tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="f71eb-116">Unlike regular stored procedures, the parameters for data collector stored procedures are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="f71eb-117">Si no se llama a estos parámetros con los tipos de datos de parámetros de entrada correctos, según se especifica en la descripción del argumento, el procedimiento almacenado devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="f71eb-117">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f71eb-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f71eb-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="f71eb-119">Debe iniciarse el Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f71eb-119">SQL Server Agent must be started.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f71eb-120">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="f71eb-120">Recommendations</span></span>  
  
-   <span data-ttu-id="f71eb-121">Para obtener información sobre los conjuntos de recopilación, consulte la vista de catálogo [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="f71eb-121">To obtain information about collection sets, query the [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) catalog view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f71eb-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f71eb-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f71eb-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="f71eb-123">Permissions</span></span>  
 <span data-ttu-id="f71eb-124">Requiere la pertenencia al rol fijo de base de datos **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="f71eb-124">Requires membership in the **dc_operator** fixed database role.</span></span> <span data-ttu-id="f71eb-125">Si el conjunto de recopilación no tiene una cuenta de proxy, es necesaria la pertenencia al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f71eb-125">If the collection set does not have a proxy account, membership in the **sysadmin** fixed server role is required.Examples</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f71eb-126">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f71eb-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="f71eb-127">Para iniciar un conjunto de recopilación</span><span class="sxs-lookup"><span data-stu-id="f71eb-127">To start a collection set</span></span>  
  
1.  <span data-ttu-id="f71eb-128">En el Explorador de objetos, expanda el nodo **Administración** , expanda **Recopilación de datos**y, después, **Conjuntos de recopilación de datos del sistema**.</span><span class="sxs-lookup"><span data-stu-id="f71eb-128">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="f71eb-129">Haga clic con el botón derecho en el conjunto de recopilación que quiere iniciar y, luego, haga clic en **Iniciar conjunto de recopilación de datos**.</span><span class="sxs-lookup"><span data-stu-id="f71eb-129">Right-click the collection set that you want to start, and then click **Start Data Collection Set**.</span></span>  
  
     <span data-ttu-id="f71eb-130">Un cuadro de mensaje muestra los resultados de esta acción y una flecha verde en el icono para el conjunto de recopilación indica que el conjunto de recopilación se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="f71eb-130">A message box displays the results of this action, and a green arrow on the icon for the collection set indicates that the collection set has started.</span></span>  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="f71eb-131">Para detener un conjunto de recopilación</span><span class="sxs-lookup"><span data-stu-id="f71eb-131">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="f71eb-132">En el Explorador de objetos, expanda el nodo **Administración** , expanda **Recopilación de datos**y, después, **Conjuntos de recopilación de datos del sistema**.</span><span class="sxs-lookup"><span data-stu-id="f71eb-132">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="f71eb-133">Haga clic con el botón derecho en el conjunto de recopilación que quiere detener y, luego, haga clic en **Detener conjunto de recopilación de datos**.</span><span class="sxs-lookup"><span data-stu-id="f71eb-133">Right-click the collection set that you want to stop, and then click **Stop Data Collection Set**.</span></span>  
  
     <span data-ttu-id="f71eb-134">Un cuadro de mensaje muestra los resultados de esta acción y un círculo rojo en el icono para el conjunto de recopilación indica que el conjunto de recopilación se ha detenido.</span><span class="sxs-lookup"><span data-stu-id="f71eb-134">A message box displays the results of this action, and a red circle on the icon for the collection set indicates that the collection set has stopped.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f71eb-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f71eb-135">Using Transact-SQL</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="f71eb-136">Para iniciar un conjunto de recopilación</span><span class="sxs-lookup"><span data-stu-id="f71eb-136">To start a collection set</span></span>  
  
1.  <span data-ttu-id="f71eb-137">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f71eb-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f71eb-138">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f71eb-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f71eb-139">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f71eb-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f71eb-140">En este ejemplo se usa [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) para iniciar el conjunto de recopilación cuyo identificador es `1`.</span><span class="sxs-lookup"><span data-stu-id="f71eb-140">This example uses [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) to start the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_start_collection_set @collection_set_id = 1;  
```  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="f71eb-141">Para detener un conjunto de recopilación</span><span class="sxs-lookup"><span data-stu-id="f71eb-141">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="f71eb-142">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f71eb-142">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f71eb-143">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f71eb-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f71eb-144">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f71eb-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f71eb-145">En este ejemplo se usa [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) para detener el conjunto de recopilación cuyo identificador es `1`.</span><span class="sxs-lookup"><span data-stu-id="f71eb-145">This example uses [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) to stop the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_stop_collection_set @collection_set_id = 1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="f71eb-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f71eb-146">See Also</span></span>  
 <span data-ttu-id="f71eb-147">[Vistas del recopilador de datos &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f71eb-147">[Data Collector Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span></span>  
 [<span data-ttu-id="f71eb-148">Recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="f71eb-148">Data Collection</span></span>](data-collection.md)  
  
  
