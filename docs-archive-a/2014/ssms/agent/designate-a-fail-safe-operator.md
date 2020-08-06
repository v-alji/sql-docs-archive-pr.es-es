---
title: Designar un operador para notificaciones de error | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- fail-safe operator [SQL Server]
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 0f4eb513-5c0a-4523-974e-e85c1deeb57f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 714ed78875bd289f2fe2d64a5699c59bce58ced0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748483"
---
# <a name="designate-a-fail-safe-operator"></a><span data-ttu-id="f22bd-102">Designar un operador para notificaciones de error</span><span class="sxs-lookup"><span data-stu-id="f22bd-102">Designate a Fail-Safe Operator</span></span>
  <span data-ttu-id="f22bd-103">Un operador para notificaciones de error es un usuario que recibe la alerta si ésta no llega al operador designado.</span><span class="sxs-lookup"><span data-stu-id="f22bd-103">A fail-safe operator is a user who receives the alert if the designated operator cannot be reached.</span></span> <span data-ttu-id="f22bd-104">En este tema se describe cómo establecer un operador para notificaciones de error para recibir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] notificaciones de alerta del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f22bd-104">This topic describes how to set a fail-safe operator to receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f22bd-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f22bd-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f22bd-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f22bd-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f22bd-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f22bd-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f22bd-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f22bd-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f22bd-109">**Para designar un operador para notificaciones de error, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="f22bd-109">**To designate a fail-safe operator, using:**</span></span>  
  
     [<span data-ttu-id="f22bd-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f22bd-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f22bd-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f22bd-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f22bd-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f22bd-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f22bd-113">Las opciones Buscapersonas y **net send** se quitarán del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una versión futura de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f22bd-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f22bd-114">Evite utilizar estas características en los nuevos trabajos de programación y planee modificar las aplicaciones que actualmente las utilizan.</span><span class="sxs-lookup"><span data-stu-id="f22bd-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="f22bd-115">Tenga en cuenta que deberá configurar el Agente SQL Server para que utilice el Correo electrónico de base de datos para enviar a los operadores notificaciones por correo electrónico o buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="f22bd-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="f22bd-116">Para obtener más información, vea el tema sobre [asignación de alertas a un operador](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f22bd-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="f22bd-117">ofrece un método gráfico sencillo para administrar trabajos y es el método recomendado para crear y administrar la infraestructura de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f22bd-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f22bd-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f22bd-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f22bd-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="f22bd-119">Permissions</span></span>  
 <span data-ttu-id="f22bd-120">Solo los miembros del rol fijo de servidor **sysadmin** pueden designar operadores para notificaciones de error.</span><span class="sxs-lookup"><span data-stu-id="f22bd-120">Only members of the **sysadmin** fixed server role can designate fail-safe operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f22bd-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f22bd-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-a-fail-safe-operator"></a><span data-ttu-id="f22bd-122">Para designar un operador para notificaciones de error</span><span class="sxs-lookup"><span data-stu-id="f22bd-122">To designate a fail-safe operator</span></span>  
  
1.  <span data-ttu-id="f22bd-123">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor que contiene el operador del Agente SQL Server que desea designar como operador para notificaciones de error.</span><span class="sxs-lookup"><span data-stu-id="f22bd-123">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent operator that you want to designate as a fail-safe.</span></span>  
  
2.  <span data-ttu-id="f22bd-124">Haga clic con el botón derecho en **Agente SQL Server** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f22bd-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="f22bd-125">En el cuadro de diálogo **propiedades de Agente SQL Server-**_Server_name_ , en **seleccionar una página**, seleccione **sistema de alerta**.</span><span class="sxs-lookup"><span data-stu-id="f22bd-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Alert System**.</span></span>  
 
4.  <span data-ttu-id="f22bd-126">En **Operador para notificaciones de error**, seleccione **Habilitar operador para notificaciones de error**.</span><span class="sxs-lookup"><span data-stu-id="f22bd-126">Under **Fail-safe operator**, select **Enable fail-safe operator**.</span></span>  
  
5.  <span data-ttu-id="f22bd-127">En la lista **Operador** , seleccione el operador que desee que sea el operador para notificaciones de error.</span><span class="sxs-lookup"><span data-stu-id="f22bd-127">In the **Operator** list, select the operator that you want to make a fail-safe.</span></span>  
  
6.  <span data-ttu-id="f22bd-128">Active alguna o la totalidad de las siguientes casillas para especificar cómo se notificará al operador: **Correo electrónico**, **Buscapersonas**o **Net send**.</span><span class="sxs-lookup"><span data-stu-id="f22bd-128">Select either any or all of the following check boxes to specify how the operator will be notified: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="f22bd-129">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f22bd-129">When finished, click **OK**.</span></span>  
  
  
