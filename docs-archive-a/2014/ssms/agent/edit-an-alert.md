---
title: Modificar una alerta | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], modifying
- modifying alerts
ms.assetid: f518e528-cc8f-446a-b37d-98505b86e430
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1eae606b3c2ca4c18d088e650e774986d4e31387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673990"
---
# <a name="edit-an-alert"></a><span data-ttu-id="f0b9c-102">Edit an Alert</span><span class="sxs-lookup"><span data-stu-id="f0b9c-102">Edit an Alert</span></span>
  <span data-ttu-id="f0b9c-103">En este tema se describe cómo editar una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerta del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0b9c-103">This topic describes how to edit a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f0b9c-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f0b9c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f0b9c-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f0b9c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f0b9c-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f0b9c-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f0b9c-107">**Para editar una alerta, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="f0b9c-107">**To edit an alert, using:**</span></span>  
  
     [<span data-ttu-id="f0b9c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0b9c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f0b9c-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0b9c-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f0b9c-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f0b9c-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f0b9c-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f0b9c-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f0b9c-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="f0b9c-112">Permissions</span></span>  
 <span data-ttu-id="f0b9c-113">De forma predeterminada, los miembros del rol fijo de servidor **sysadmin** pueden editar la información de una alerta.</span><span class="sxs-lookup"><span data-stu-id="f0b9c-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="f0b9c-114">A otros usuarios debe concederse el rol fijo de base de datos **SQLAgentOperatorRole** en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="f0b9c-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f0b9c-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0b9c-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="f0b9c-116">Para modificar una alerta</span><span class="sxs-lookup"><span data-stu-id="f0b9c-116">To edit an alert</span></span>  
  
1.  <span data-ttu-id="f0b9c-117">En el **Explorador de objetos,** haga clic en el signo más para expandir el servidor que contiene la alerta que desea editar.</span><span class="sxs-lookup"><span data-stu-id="f0b9c-117">In **Object Explorer,** click the plus sign to expand the server containing the alert you want to edit.</span></span>  
  
2.  <span data-ttu-id="f0b9c-118">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f0b9c-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="f0b9c-119">Haga clic en el signo más para expandir la carpeta **Alertas** .</span><span class="sxs-lookup"><span data-stu-id="f0b9c-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="f0b9c-120">Haga clic con el botón derecho en la alerta que desea editar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f0b9c-120">Right-click the alert you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="f0b9c-121">Actualice las propiedades de la alerta en las páginas **General**, **Respuesta**y **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="f0b9c-121">Update the alert properties on the **General**, **Response**, and **Options** pages.</span></span>  
  
6.  <span data-ttu-id="f0b9c-122">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0b9c-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f0b9c-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0b9c-123">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="f0b9c-124">Para modificar una alerta</span><span class="sxs-lookup"><span data-stu-id="f0b9c-124">To edit an alert</span></span>  
  
1.  <span data-ttu-id="f0b9c-125">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0b9c-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0b9c-126">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f0b9c-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0b9c-127">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f0b9c-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="f0b9c-128">Para obtener más información, vea [sp_update_alert &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0b9c-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  
