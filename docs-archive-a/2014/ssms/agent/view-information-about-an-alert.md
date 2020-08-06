---
title: Ver información sobre una alerta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- viewing alerts
- alerts [SQL Server], viewing
- displaying alerts
- status information [SQL Server], alerts
ms.assetid: a0e3a8c4-e3c2-42a5-b2f8-aa06061d3fa6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ee72512a507299e71f13fee689709a9403bb04e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671315"
---
# <a name="view-information-about-an-alert"></a><span data-ttu-id="7b7fc-102">Ver información acerca de una alerta</span><span class="sxs-lookup"><span data-stu-id="7b7fc-102">View Information About an Alert</span></span>
  <span data-ttu-id="7b7fc-103">En este tema se describe cómo ver información acerca de las [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b7fc-103">This topic describes how to view information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7b7fc-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="7b7fc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7b7fc-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="7b7fc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7b7fc-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7b7fc-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7b7fc-107">**Para ver información acerca de una alerta, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="7b7fc-107">**To view information about an alert, using:**</span></span>  
  
     [<span data-ttu-id="7b7fc-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b7fc-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7b7fc-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b7fc-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7b7fc-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7b7fc-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7b7fc-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7b7fc-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7b7fc-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="7b7fc-112">Permissions</span></span>  
 <span data-ttu-id="7b7fc-113">De forma predeterminada, los miembros del rol fijo de servidor **sysadmin** pueden ver información acerca de una alerta.</span><span class="sxs-lookup"><span data-stu-id="7b7fc-113">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="7b7fc-114">A otros usuarios debe concederse el rol fijo de base de datos **SQLAgentOperatorRole** en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="7b7fc-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7b7fc-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b7fc-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="7b7fc-116">Para ver información acerca de una alerta</span><span class="sxs-lookup"><span data-stu-id="7b7fc-116">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="7b7fc-117">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor en el que desea ver información acerca de una alerta.</span><span class="sxs-lookup"><span data-stu-id="7b7fc-117">In **Object Explorer,** click the plus sign to expand the server where you want to view information about an alert.</span></span>  
  
2.  <span data-ttu-id="7b7fc-118">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7b7fc-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="7b7fc-119">Haga clic en el signo más para expandir la carpeta **Alertas** .</span><span class="sxs-lookup"><span data-stu-id="7b7fc-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="7b7fc-120">Haga clic con el botón derecho en la alerta que tiene la información que desea ver y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7b7fc-120">Right-click the alert that has the information you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="7b7fc-121">Para más información sobre las opciones disponibles presentes en el cuadro de diálogo _nombre_alerta_**Propiedades de la alerta** , consulte:</span><span class="sxs-lookup"><span data-stu-id="7b7fc-121">For more information on the available options contained in the _alert_name_**alert properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="7b7fc-122">Propiedades de alerta-nueva alerta &#40;página general&#41;</span><span class="sxs-lookup"><span data-stu-id="7b7fc-122">Alert Properties-New Alert &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="7b7fc-123">Propiedades de alerta-nueva página de respuesta de &#40;de alerta&#41;</span><span class="sxs-lookup"><span data-stu-id="7b7fc-123">Alert Properties-New Alert &#40;Response Page&#41;</span></span>](alert-properties-new-alert-response-page.md)  
  
    -   [<span data-ttu-id="7b7fc-124">Propiedades de alerta: nueva página de opciones de &#40;de alertas&#41;</span><span class="sxs-lookup"><span data-stu-id="7b7fc-124">Alert Properties: New Alert &#40;Options Page&#41;</span></span>](alert-properties-new-alert-options-page.md)  
  
    -   [<span data-ttu-id="7b7fc-125">Propiedades de alerta &#40;Página Historial&#41;</span><span class="sxs-lookup"><span data-stu-id="7b7fc-125">Alert Properties &#40;History Page&#41;</span></span>](alert-properties-history-page.md)  
  
5.  <span data-ttu-id="7b7fc-126">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b7fc-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7b7fc-127">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b7fc-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="7b7fc-128">Para ver información acerca de una alerta</span><span class="sxs-lookup"><span data-stu-id="7b7fc-128">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="7b7fc-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b7fc-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7b7fc-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="7b7fc-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7b7fc-131">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7b7fc-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about the Demo: Sev. 25 Errors alert  
    -- This example assumes that the 'Demo: Sev. 25 Errors' alert exists.  
    USE msdb ;  
    GO  
  
    EXEC sp_help_alert @alert_name = 'Demo: Sev. 25 Errors'  
    GO  
    ```  
  
 <span data-ttu-id="7b7fc-132">Para obtener más información, vea [sp_help_alert &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7b7fc-132">For more information, see [sp_help_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span></span>  
  
  
