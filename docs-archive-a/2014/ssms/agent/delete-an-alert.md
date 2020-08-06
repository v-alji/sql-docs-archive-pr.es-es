---
title: Eliminar una alerta | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], deleting
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- removing alerts
ms.assetid: c982b208-e2d1-4d34-8cee-940b9baf6586
author: stevestein
ms.author: sstein
ms.openlocfilehash: 15fdae19b150a5a06a32e91ec1947a0acfa5f900
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675103"
---
# <a name="delete-an-alert"></a><span data-ttu-id="f65be-102">Delete an Alert</span><span class="sxs-lookup"><span data-stu-id="f65be-102">Delete an Alert</span></span>
  <span data-ttu-id="f65be-103">En este tema se describe cómo eliminar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f65be-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f65be-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f65be-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f65be-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f65be-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f65be-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f65be-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f65be-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f65be-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f65be-108">**Para eliminar una alerta, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="f65be-108">**To delete an alert, using:**</span></span>  
  
     [<span data-ttu-id="f65be-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f65be-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f65be-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f65be-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f65be-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f65be-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f65be-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f65be-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f65be-113">Si se quita una alerta, también se quitan las notificaciones asociadas con ella.</span><span class="sxs-lookup"><span data-stu-id="f65be-113">Removing an alert also removes any notifications associated with the alert.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f65be-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f65be-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f65be-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="f65be-115">Permissions</span></span>  
 <span data-ttu-id="f65be-116">De forma predeterminada, solo los miembros del rol fijo de servidor **sysadmin** pueden eliminar alertas.</span><span class="sxs-lookup"><span data-stu-id="f65be-116">By default, only members of the **sysadmin** fixed server role can delete alerts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f65be-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f65be-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="f65be-118">Para eliminar una alerta</span><span class="sxs-lookup"><span data-stu-id="f65be-118">To delete an alert</span></span>  
  
1.  <span data-ttu-id="f65be-119">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor que contiene la alerta del Agente SQL Server que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="f65be-119">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent alert that you want to delete.</span></span>  
  
2.  <span data-ttu-id="f65be-120">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f65be-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="f65be-121">Haga clic en el signo más para expandir la carpeta **Alertas** .</span><span class="sxs-lookup"><span data-stu-id="f65be-121">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="f65be-122">Haga clic con el botón derecho en la alerta que desea eliminar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f65be-122">Right-click the alert you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="f65be-123">En el cuadro de diálogo **Eliminar objeto** , confirme que está seleccionada la alerta correcta y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f65be-123">In the **Delete Object** dialog box, confirm that the correct alert is selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f65be-124">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f65be-124">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="f65be-125">Para eliminar una alerta</span><span class="sxs-lookup"><span data-stu-id="f65be-125">To delete an alert</span></span>  
  
1.  <span data-ttu-id="f65be-126">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f65be-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f65be-127">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f65be-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f65be-128">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f65be-128">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the SQL Server Agent alert called 'Test Alert.'  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_alert  
       @name = N'Test Alert' ;  
    GO  
    ```  
  
 <span data-ttu-id="f65be-129">Para obtener más información, vea s[sp_delete_alert &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f65be-129">For more information, see s[sp_delete_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span></span>  
  
  
