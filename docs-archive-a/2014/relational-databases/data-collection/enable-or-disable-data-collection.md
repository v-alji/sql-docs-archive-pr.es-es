---
title: Habilitar o deshabilitar la recopilación de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], disabling
- data collector [SQL Server], enabling
ms.assetid: 0137971b-fb48-4a3e-822a-3df2b9bb09d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af5cc647a63d3a9451086fc9e2211dec809e88fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669699"
---
# <a name="enable-or-disable-data-collection"></a><span data-ttu-id="d26af-102">Habilitar o deshabilitar la recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="d26af-102">Enable or Disable Data Collection</span></span>
  <span data-ttu-id="d26af-103">En este tema se describe cómo habilitar o deshabilitar una recopilación de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d26af-103">This topic describes how to enable or disable data collection in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d26af-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d26af-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d26af-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="d26af-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d26af-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d26af-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d26af-107">**Para habilitar o deshabilitar una recopilación de datos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="d26af-107">**To enable or disable data collection, using:**</span></span>  
  
     [<span data-ttu-id="d26af-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d26af-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d26af-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d26af-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d26af-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d26af-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d26af-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d26af-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d26af-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="d26af-112">Permissions</span></span>  
 <span data-ttu-id="d26af-113">Requiere la pertenencia al rol fijo de base de datos **dc_admin** o **dc_operator** (con permiso EXECUTE) para ejecutar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d26af-113">Requires membership in the **dc_admin** or **dc_operator** (with EXECUTE permission) fixed database role to execute this procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d26af-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d26af-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="d26af-115">Para habilitar el recopilador de datos</span><span class="sxs-lookup"><span data-stu-id="d26af-115">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="d26af-116">En el Explorador de objetos, expanda el nodo **Administración** .</span><span class="sxs-lookup"><span data-stu-id="d26af-116">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="d26af-117">Haga clic con el botón derecho en **Recopilación de datos**y, luego, haga clic en **Habilitar recopilación de datos**.</span><span class="sxs-lookup"><span data-stu-id="d26af-117">Right-click **Data Collection**, and then click **Enable Data Collection**.</span></span>  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="d26af-118">Para deshabilitar el recopilador de datos</span><span class="sxs-lookup"><span data-stu-id="d26af-118">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="d26af-119">En el Explorador de objetos, expanda el nodo **Administración** .</span><span class="sxs-lookup"><span data-stu-id="d26af-119">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="d26af-120">Haga clic con el botón derecho en **Recopilación de datos**y luego haga clic en **Deshabilitar recopilación de datos**.</span><span class="sxs-lookup"><span data-stu-id="d26af-120">Right-click **Data Collection**, and then click **Disable Data Collection**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d26af-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d26af-121">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="d26af-122">Para habilitar el recopilador de datos</span><span class="sxs-lookup"><span data-stu-id="d26af-122">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="d26af-123">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d26af-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d26af-124">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d26af-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d26af-125">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d26af-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d26af-126">En este ejemplo se usa [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) para habilitar el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="d26af-126">This example uses [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) to enable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_enable_collector ;  
```  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="d26af-127">Para deshabilitar el recopilador de datos</span><span class="sxs-lookup"><span data-stu-id="d26af-127">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="d26af-128">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d26af-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d26af-129">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d26af-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d26af-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d26af-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d26af-131">En este ejemplo se usa [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) para deshabilitar el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="d26af-131">This example uses [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) to disable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_disable_collector;  
```  
  
## <a name="see-also"></a><span data-ttu-id="d26af-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d26af-132">See Also</span></span>  
 <span data-ttu-id="d26af-133">[Recopilación de datos](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="d26af-133">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="d26af-134">Procedimientos almacenados del sistema &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d26af-134">System Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql)  
  
  
