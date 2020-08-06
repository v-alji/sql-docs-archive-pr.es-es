---
title: Dar formato a las direcciones de buscapersonas para alertas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- pager addresses [SQL Server]
- SQL Server Agent, alerts
- formats [SQL Server], pager addresses
- pager notifications [SQL Server]
- addresses [SQL Server]
- alerts [SQL Server], pager addresses
ms.assetid: a9797d01-1050-442c-9038-ed4bfee1e76a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471f9a4958f51491b312d89239a2204c907e25e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662478"
---
# <a name="format-pager-addresses-for-alerts"></a><span data-ttu-id="360e4-102">Format Pager Addresses for Alerts</span><span class="sxs-lookup"><span data-stu-id="360e4-102">Format Pager Addresses for Alerts</span></span>
  <span data-ttu-id="360e4-103">En este tema se describe cómo dar formato a las direcciones de buscapersonas para las [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="360e4-103">This topic describes how to format pager addresses for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="360e4-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="360e4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="360e4-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="360e4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="360e4-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="360e4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="360e4-107">**Para dar formato a direcciones del buscapersonas, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="360e4-107">**To format pager addresses, using:**</span></span>  
  
     [<span data-ttu-id="360e4-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="360e4-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="360e4-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="360e4-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="360e4-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="360e4-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="360e4-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="360e4-111">Permissions</span></span>  
 <span data-ttu-id="360e4-112">De forma predeterminada, los miembros del rol fijo de servidor **sysadmin** pueden ver información acerca de una alerta.</span><span class="sxs-lookup"><span data-stu-id="360e4-112">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="360e4-113">A otros usuarios debe concederse el rol fijo de base de datos **SQLAgentOperatorRole** en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="360e4-113">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="360e4-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="360e4-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-format-pager-addresses"></a><span data-ttu-id="360e4-115">Para dar formato a direcciones del buscapersonas</span><span class="sxs-lookup"><span data-stu-id="360e4-115">To format pager addresses</span></span>  
  
1.  <span data-ttu-id="360e4-116">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la alerta que desea enviar a un buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="360e4-116">In **Object Explorer**, click the plus sign to expand the server that contains the alert that you want to send to a pager.</span></span>  
  
2.  <span data-ttu-id="360e4-117">Haga clic con el botón derecho en **Agente SQL Server** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="360e4-117">Right-click **SQL Server Agent** and select **Properties**</span></span>  
  
3.  <span data-ttu-id="360e4-118">En **Seleccionar una página**, seleccione **Sistema de alerta**.</span><span class="sxs-lookup"><span data-stu-id="360e4-118">Under **Select a page**, select **Alert System**.</span></span>  
  
4.  <span data-ttu-id="360e4-119">En los cuadros **Línea Para** y **Línea CC** del campo **Formato de dirección para correo electrónico de buscapersonas** , escriba el prefijo o el sufijo de la dirección del buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="360e4-119">In the **To line** and **CC line** boxes of the **Address formatting for pager e-mails** field, enter the pager address prefix or suffix.</span></span> <span data-ttu-id="360e4-120">La dirección del buscapersonas real del operador se inserta cuando se envía una notificación.</span><span class="sxs-lookup"><span data-stu-id="360e4-120">The operator's actual pager address is inserted when a notification is sent.</span></span>  
  
5.  <span data-ttu-id="360e4-121">En el cuadro **Asunto** , escriba el prefijo o el sufijo de la línea del asunto.</span><span class="sxs-lookup"><span data-stu-id="360e4-121">In the **Subject** box, enter the subject line prefix or suffix.</span></span>  
  
6.  <span data-ttu-id="360e4-122">Active la casilla **Incluir cuerpo del mensaje en la notificación** para incluir todo el mensaje de correo electrónico en el mensaje del buscapersonas (en vez de incluir solo la línea del asunto).</span><span class="sxs-lookup"><span data-stu-id="360e4-122">Select the **Include body of e-mail in notification page** check box to include the full e-mail message with the pager message (as opposed to the subject line only).</span></span>  
  
7.  <span data-ttu-id="360e4-123">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="360e4-123">When finished, click **OK**.</span></span>  
  
  
