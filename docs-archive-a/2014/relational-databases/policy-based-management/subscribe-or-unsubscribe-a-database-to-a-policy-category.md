---
title: Suscribir una base de datos a una categoría de directiva o anular la suscripción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.groupsubscription.f1
ms.assetid: d2c31769-7098-428e-ad9c-ef56541b7c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2b4ca6f804352b57b30b42012da93e0d031be8d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745713"
---
# <a name="subscribe-or-unsubscribe-a-database--to-a-policy-category"></a><span data-ttu-id="2e2c0-102">Suscribir una base de datos a una categoría de directiva o anular la suscripción</span><span class="sxs-lookup"><span data-stu-id="2e2c0-102">Subscribe or Unsubscribe a Database  to a Policy Category</span></span>
  <span data-ttu-id="2e2c0-103">En este tema se describe cómo se suscribe una base de datos a una categoría de directiva o se cancela la suscripción en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e2c0-103">This topic describes how to subscribe or unsubscribe a database to a policy category.in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2e2c0-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="2e2c0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2e2c0-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="2e2c0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2e2c0-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2e2c0-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2e2c0-107">**Para suscribir una base de datos a una categoría de directiva o anular la suscripción con:**</span><span class="sxs-lookup"><span data-stu-id="2e2c0-107">**To subscribe or unsubscribe a database to a policy category., using:**</span></span>  
  
     [<span data-ttu-id="2e2c0-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e2c0-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2e2c0-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e2c0-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2e2c0-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2e2c0-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2e2c0-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2e2c0-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2e2c0-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="2e2c0-112">Permissions</span></span>  
 <span data-ttu-id="2e2c0-113">Requiere pertenencia al rol fijo de base de datos db_owner.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-113">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2e2c0-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e2c0-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-subscribe-or-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="2e2c0-115">Para suscribir una base de datos a una categoría de directiva o anular la suscripción</span><span class="sxs-lookup"><span data-stu-id="2e2c0-115">To subscribe or unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="2e2c0-116">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la base de datos en la que se encuentran las suscripciones de categorías que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-116">In **Object Explorer**, click the plus sign to expand the server that contains the database wherein you want to manage category subscriptions.</span></span>  
  
2.  <span data-ttu-id="2e2c0-117">Haga clic en el signo más para expandir la carpeta **Bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="2e2c0-117">Click the plus sign to expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="2e2c0-118">Haga clic con el botón derecho en la base de datos que contiene las suscripciones que quiera administrar, seleccione **Directivas**y, después, seleccione **Categorías**.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-118">Right-click the database wherein you want to manage category subscriptions, point to **Policies**, and select **Categories**</span></span>  
  
     <span data-ttu-id="2e2c0-119">En el cuadro de diálogo **Categorías** están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2e2c0-119">The following options are available in the **Categories** dialog box:</span></span>  
  
     <span data-ttu-id="2e2c0-120">Expandir columna</span><span class="sxs-lookup"><span data-stu-id="2e2c0-120">Expand column</span></span>  
     <span data-ttu-id="2e2c0-121">Haga clic para expandir una categoría de directiva.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-121">Click to expand a policy category.</span></span> <span data-ttu-id="2e2c0-122">De este modo se muestra una lista de todas las directivas que están incluidas en la categoría.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-122">This lists all the policies that are included in the category.</span></span>  
  
     <span data-ttu-id="2e2c0-123">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2e2c0-123">**Name**</span></span>  
     <span data-ttu-id="2e2c0-124">Nombre de la categoría de directiva.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-124">The name of the policy category.</span></span>  
  
     <span data-ttu-id="2e2c0-125">**Suscrito**</span><span class="sxs-lookup"><span data-stu-id="2e2c0-125">**Subscribed**</span></span>  
     <span data-ttu-id="2e2c0-126">Indica si el destino se ha suscrito a la categoría de directiva.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-126">Indicates whether the target has subscribed to the policy category.</span></span> <span data-ttu-id="2e2c0-127">Si esta casilla está deshabilitada, la categoría de directiva está establecida para **Suscripciones de base de datos de mandatos**.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-127">If this check box is disabled, the policy category is set for **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="2e2c0-128">Esto significa que la categoría de directiva se aplica a todas las bases de datos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-128">This means that the policy category applies to all databases on the server.</span></span>  
  
     <span data-ttu-id="2e2c0-129">**Directiva**</span><span class="sxs-lookup"><span data-stu-id="2e2c0-129">**Policy**</span></span>  
     <span data-ttu-id="2e2c0-130">Cuando se expanden los grupos de directivas, muestra las directivas de la categoría de directiva.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-130">When policy groups are expanded, displays the policies in the policy category.</span></span>  
  
     <span data-ttu-id="2e2c0-131">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="2e2c0-131">**Enabled**</span></span>  
     <span data-ttu-id="2e2c0-132">Indica si las directivas están habilitadas o deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-132">Indicates whether the policies are enabled or disabled.</span></span>  
  
     <span data-ttu-id="2e2c0-133">**Modo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="2e2c0-133">**Execution Mode**</span></span>  
     <span data-ttu-id="2e2c0-134">Muestra el modo de ejecución de la directiva.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-134">Displays the execution mode of the policy.</span></span>  
  
     <span data-ttu-id="2e2c0-135">**Historial**</span><span class="sxs-lookup"><span data-stu-id="2e2c0-135">**History**</span></span>  
     <span data-ttu-id="2e2c0-136">Haga clic en el hipervínculo Ver historial para abrir el Visor del archivo de registros para ver el historial de directiva.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-136">Click the View History hyperlink to open the Log File Viewer to see the policy history.</span></span>  
  
4.  <span data-ttu-id="2e2c0-137">Para suscribirse a una categoría de administración basada en directivas, active la casilla de la categoría en la columna **Subscribed** .</span><span class="sxs-lookup"><span data-stu-id="2e2c0-137">To subscribe to a Policy-Based Management category, select the category's check box under the **Subscribed** column.</span></span> <span data-ttu-id="2e2c0-138">Para anular la suscripción de una categoría, desactive la casilla.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-138">To unsubscribe from a category, clear the check box.</span></span>  
  
5.  <span data-ttu-id="2e2c0-139">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-139">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2e2c0-140">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e2c0-140">Using Transact-SQL</span></span>  
  
#### <a name="to-subscribe-a-database-to-a-policy-category"></a><span data-ttu-id="2e2c0-141">Para suscribir una base de datos a una categoría de directiva</span><span class="sxs-lookup"><span data-stu-id="2e2c0-141">To subscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="2e2c0-142">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e2c0-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2e2c0-143">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2e2c0-144">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Adds a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_subscribe_to_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="2e2c0-145">Para obtener más información, vea [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2e2c0-145">For more information, see [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span></span>  
  
#### <a name="to-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="2e2c0-146">Para anular la suscripción de una base de datos a una categoría de directiva</span><span class="sxs-lookup"><span data-stu-id="2e2c0-146">To unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="2e2c0-147">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e2c0-147">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2e2c0-148">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-148">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2e2c0-149">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2e2c0-149">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Deletes a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_unsubscribe_from_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="2e2c0-150">Para obtener más información, vea [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2e2c0-150">For more information, see [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span></span>  
  
  
