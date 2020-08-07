---
title: Deshabilitar o volver a activar una alerta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], reactivating
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- alerts [SQL Server], disabling
- reactivating alerts
- removing alerts
ms.assetid: 4cb37dc6-1134-405d-8590-58b44dcf63b2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3eec4ea7288f4847c0e9b861d80f23eb9c9ddba8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747419"
---
# <a name="disable-or-reactivate-an-alert"></a><span data-ttu-id="27c94-102">Disable or Reactivate an Alert</span><span class="sxs-lookup"><span data-stu-id="27c94-102">Disable or Reactivate an Alert</span></span>
  <span data-ttu-id="27c94-103">En este tema se describe cómo deshabilitar o volver a activar una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerta del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27c94-103">This topic describes how to disable or reactivate a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="27c94-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="27c94-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="27c94-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="27c94-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="27c94-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="27c94-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="27c94-107">**Para deshabilitar o volver a activar una alerta, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="27c94-107">**To disable or reactivate an alert, using:**</span></span>  
  
     [<span data-ttu-id="27c94-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27c94-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="27c94-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27c94-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="27c94-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="27c94-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="27c94-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="27c94-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="27c94-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="27c94-112">Permissions</span></span>  
 <span data-ttu-id="27c94-113">De forma predeterminada, los miembros del rol fijo de servidor **sysadmin** pueden editar la información de una alerta.</span><span class="sxs-lookup"><span data-stu-id="27c94-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="27c94-114">A otros usuarios debe concederse el rol fijo de base de datos **SQLAgentOperatorRole** en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="27c94-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="27c94-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27c94-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="27c94-116">Para deshabilitar o volver a activar una alerta</span><span class="sxs-lookup"><span data-stu-id="27c94-116">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="27c94-117">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la alerta que desea deshabilitar o volver a activar.</span><span class="sxs-lookup"><span data-stu-id="27c94-117">In **Object Explorer**, click the plus sign to expand server that contains the alert you wish to disable or reactivate.</span></span>  
  
2.  <span data-ttu-id="27c94-118">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="27c94-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="27c94-119">Haga clic en el signo más para expandir la carpeta **Alertas** .</span><span class="sxs-lookup"><span data-stu-id="27c94-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="27c94-120">Haga clic con el botón derecho en la alerta que desea habilitar y seleccione **Habilitar** . Para deshabilitar una alerta, haga clic con el botón derecho en la alerta que desea deshabilitar y seleccione **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="27c94-120">Right-click the alert you wish to enable and select **Enable** To disable an alert, right-click the alert you want to disable and select **Disable**.</span></span>  
  
5.  <span data-ttu-id="27c94-121">Aparece el cuadro de diálogo **Deshabilitar la alerta** o **Habilitar la alerta** con el estado del proceso.</span><span class="sxs-lookup"><span data-stu-id="27c94-121">The **Disable Alert** or **Enable Alert** dialog box displays showing the status of the process.</span></span> <span data-ttu-id="27c94-122">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="27c94-122">When finished, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="27c94-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27c94-123">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="27c94-124">Para deshabilitar o volver a activar una alerta</span><span class="sxs-lookup"><span data-stu-id="27c94-124">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="27c94-125">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27c94-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="27c94-126">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="27c94-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="27c94-127">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="27c94-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="27c94-128">Para obtener más información, vea [sp_update_alert &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="27c94-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  
