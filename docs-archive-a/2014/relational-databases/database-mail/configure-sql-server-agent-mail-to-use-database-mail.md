---
title: Configuración del Agente SQL Server para que use el Correo electrónico de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], SQL Server Agent Mail
- SQL Server Agent Mail
ms.assetid: 4b8b61bd-4bd1-43cd-b6e5-c6ed2e101dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31d116c0bc8d7e148fc2ef6d2e344400516ad923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744131"
---
# <a name="configure-sql-server-agent-mail-to-use-database-mail"></a><span data-ttu-id="55234-102">Configurar el Agente SQL Server para que use el Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="55234-102">Configure SQL Server Agent Mail to Use Database Mail</span></span>
  <span data-ttu-id="55234-103">En este tema se describe cómo configurar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para usar Correo electrónico de base de datos a fin de enviar notificaciones y alertas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55234-103">This topic describes how to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use Database Mail to send notification and alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="55234-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="55234-104">**Before you begin:**</span></span>  
  
-   [<span data-ttu-id="55234-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="55234-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="55234-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="55234-106">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="55234-107">Para configurar el Agente SQL Server para que use el Correo electrónico de base de datos mediante Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55234-107">To Configure SQL Server Agent to use Database Mail, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="55234-108">Tareas de seguimiento</span><span class="sxs-lookup"><span data-stu-id="55234-108">Follow-up Tasks</span></span>](#Follow_Up)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="55234-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="55234-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="55234-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="55234-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="55234-111">Habilitar Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="55234-111">Enable Database Mail.</span></span>  
  
-   <span data-ttu-id="55234-112">Crear una cuenta de Correo electrónico de base de datos para la cuenta de servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que desea usar.</span><span class="sxs-lookup"><span data-stu-id="55234-112">Create a Database Mail account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use.</span></span>  
  
-   <span data-ttu-id="55234-113">Crear un perfil del Correo electrónico de base de datos para uso de la cuenta de servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y agregar el usuario a la función **DatabaseMailUserRole** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="55234-113">Create a Database Mail profile for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use and add the user to the **DatabaseMailUserRole** in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="55234-114">Establecer el perfil como perfil predeterminado de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="55234-114">Set the profile as the default profile for the **msdb** database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="55234-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="55234-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="55234-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="55234-116">Permissions</span></span>  
 <span data-ttu-id="55234-117">El usuario que crea cuentas de perfil y ejecuta procedimientos almacenados debe ser miembro del rol fijo de servidor sysadmin.</span><span class="sxs-lookup"><span data-stu-id="55234-117">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="55234-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55234-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="55234-119">**Para configurar el Agente SQL Server de modo que use el Correo electrónico de base de datos**</span><span class="sxs-lookup"><span data-stu-id="55234-119">**To configure SQL Server Agent to use Database Mail**</span></span>  
  
-   <span data-ttu-id="55234-120">En el Explorador de objetos, expanda una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55234-120">In Object Explorer, expand a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="55234-121">Haga clic con el botón derecho en **Agente SQL Server**y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="55234-121">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="55234-122">Haga clic en **Sistema de alerta**.</span><span class="sxs-lookup"><span data-stu-id="55234-122">Click **Alert System**.</span></span>  
  
-   <span data-ttu-id="55234-123">Seleccione **Habilitar perfil de correo**.</span><span class="sxs-lookup"><span data-stu-id="55234-123">Select **Enable Mail Profile**.</span></span>  
  
-   <span data-ttu-id="55234-124">En la lista **Sistema de correo** , seleccione **Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="55234-124">In the **Mail system** list, select **Database Mail**.</span></span>  
  
-   <span data-ttu-id="55234-125">En la lista **Perfil de correo**, seleccione un perfil de correo para el Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="55234-125">In the **Mail profile list**, select a mail profile for Database Mail.</span></span>  
  
-   <span data-ttu-id="55234-126">Reinicie el Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="55234-126">Restart SQL Server Agent.</span></span>  
  
##  <a name="follow-up-tasks"></a><a name="Follow_Up"></a> <span data-ttu-id="55234-127">Tareas de seguimiento</span><span class="sxs-lookup"><span data-stu-id="55234-127">Follow-up Tasks</span></span>  
 <span data-ttu-id="55234-128">Las siguientes tareas son necesarias para completar la configuración del agente con el fin de que envíe alertas y notificaciones.</span><span class="sxs-lookup"><span data-stu-id="55234-128">The following tasks are necessary to complete the configuration of Agent to send alerts and notifications.</span></span>  
  
-   [<span data-ttu-id="55234-129">Alertas</span><span class="sxs-lookup"><span data-stu-id="55234-129">Alerts</span></span>](../../ssms/agent/alerts.md)  
  
     <span data-ttu-id="55234-130">Las alertas se pueden configurar para notificar a un operador de una determinada condición de evento o de sistema operativo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="55234-130">Alerts can be configured to notify an operator of a particular database event or operating system condition.</span></span>  
  
-   [<span data-ttu-id="55234-131">Operadores</span><span class="sxs-lookup"><span data-stu-id="55234-131">Operators</span></span>](../../ssms/agent/operators.md)  
  
     <span data-ttu-id="55234-132">Los operadores son alias de personas o grupos que pueden recibir la notificación electrónica</span><span class="sxs-lookup"><span data-stu-id="55234-132">Operators are aliases for people or groups that can receive electronic notification</span></span>  
  
  
