---
title: Administración de categorías de directiva | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.policycategories.f1
ms.assetid: d188a819-731f-4029-98aa-780d3299a0ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 168d05dd88286263da1dca5456a2c6072e946786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670998"
---
# <a name="manage-policy-categories"></a><span data-ttu-id="30ae4-102">Administrar categorías de directiva</span><span class="sxs-lookup"><span data-stu-id="30ae4-102">Manage Policy Categories</span></span>
  <span data-ttu-id="30ae4-103">En este tema se describe cómo se aplica una o todas las directivas disponibles en una categoría a toda la instancia de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30ae4-103">This topic describes how to apply any or all available policies in a category to the whole instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="30ae4-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="30ae4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="30ae4-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="30ae4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="30ae4-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="30ae4-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="30ae4-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="30ae4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="30ae4-108">**Para aplicar directivas de categoría a una instancia de SQL Server con:**</span><span class="sxs-lookup"><span data-stu-id="30ae4-108">**To apply category policies to a SQL Server instance, using:**</span></span>  
  
     [<span data-ttu-id="30ae4-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30ae4-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="30ae4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30ae4-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="30ae4-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="30ae4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="30ae4-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="30ae4-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="30ae4-113">Cuando se usa [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], si la casilla **Suscripciones de base de datos de mandatos** no está activada, la categoría de directiva debe aplicarse individualmente a cada parte correspondiente del servidor, por ejemplo, a una o varias bases de datos o tablas.</span><span class="sxs-lookup"><span data-stu-id="30ae4-113">When using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], if the **Mandate Database Subscriptions** check box is not selected, the policy category must be individually applied to each relevant portion of the server, such as one or more databases or tables.</span></span>  
  
-   <span data-ttu-id="30ae4-114">Si especifica una categoría de directiva que no existe, se crea una categoría de directiva nueva y la suscripción se asigna para todas las bases de datos al ejecutar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="30ae4-114">If you specify a policy category that does not exist, a new policy category is created and the subscription is mandated for all databases when you execute the stored procedure.</span></span> <span data-ttu-id="30ae4-115">Si luego borra la suscripción asignada para la nueva categoría, la suscripción solo se aplicará para la base de datos que especificó como *target_object*.</span><span class="sxs-lookup"><span data-stu-id="30ae4-115">If you then clear the mandated subscription for the new category, the subscription will only apply for the database that you specified as the *target_object*.</span></span> <span data-ttu-id="30ae4-116">Para obtener más información sobre cómo cambiar una configuración de suscripción asignada, vea [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30ae4-116">For more information about how to change a mandated subscription setting, see [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="30ae4-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="30ae4-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="30ae4-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="30ae4-118">Permissions</span></span>  
 <span data-ttu-id="30ae4-119">Este procedimiento almacenado se ejecuta en el contexto del propietario actual del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="30ae4-119">This stored procedure runs in the context of the current owner of the stored procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="30ae4-120">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30ae4-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="30ae4-121">Para aplicar directivas de categoría a una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="30ae4-121">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="30ae4-122">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que aplicará las directivas de categoría.</span><span class="sxs-lookup"><span data-stu-id="30ae4-122">In **Object Explorer**, click the plus sign to expand the server where you will apply category policies.</span></span>  
  
2.  <span data-ttu-id="30ae4-123">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="30ae4-123">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="30ae4-124">Haga clic con el botón derecho en **Administración de directivas** y seleccione **Administrar categorías**.</span><span class="sxs-lookup"><span data-stu-id="30ae4-124">Right-click **Policy Management** and select **Manage Categories**.</span></span>  
  
     <span data-ttu-id="30ae4-125">La siguiente información está disponible en el cuadro de diálogo **Administrar categorías de directiva** :</span><span class="sxs-lookup"><span data-stu-id="30ae4-125">The following information is available in the **Manage Policy Categories** dialog box:</span></span>  
  
     <span data-ttu-id="30ae4-126">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="30ae4-126">**Name**</span></span>  
     <span data-ttu-id="30ae4-127">Nombre de la categoría de directiva.</span><span class="sxs-lookup"><span data-stu-id="30ae4-127">The name of the policy category.</span></span>  
  
     <span data-ttu-id="30ae4-128">**Suscripciones de base de datos de mandatos**</span><span class="sxs-lookup"><span data-stu-id="30ae4-128">**Mandate Database Subscriptions**</span></span>  
     <span data-ttu-id="30ae4-129">Obliga a que todas las bases de datos de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exijan directivas en la categoría de directiva.</span><span class="sxs-lookup"><span data-stu-id="30ae4-129">Forces all databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to enforce policies in the policy category.</span></span>  
  
4.  <span data-ttu-id="30ae4-130">Active o desactive alguna o todas las casillas situadas bajo **Suscripciones de base de datos de mandatos** para aplicar esa categoría de directiva a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30ae4-130">Select or clear any or all check boxes under **Mandate Database Subscriptions** to apply that policy category to the SQL Server instance.</span></span>  
  
5.  <span data-ttu-id="30ae4-131">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30ae4-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="30ae4-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30ae4-132">Using Transact-SQL</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="30ae4-133">Para aplicar directivas de categoría a una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="30ae4-133">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="30ae4-134">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30ae4-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="30ae4-135">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="30ae4-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="30ae4-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="30ae4-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    -- configures the specified database to subscribe to a policy category that is named 'Table Naming Policies'.  
    EXEC dbo.sp_syspolicy_add_policy_category_subscription @target_type = N'DATABASE'  
    , @target_object = N'AdventureWorks2012'  
    , @policy_category = N'Table Naming Policies';  
    GO  
    ```  
  
 <span data-ttu-id="30ae4-137">Para obtener más información, vea [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30ae4-137">For more information, see [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span></span>  
  
  
