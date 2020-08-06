---
title: Designar un servidor de reenvío de eventos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- alerts [SQL Server], forwarded events
ms.assetid: 81dfcbe4-3000-4e77-99de-bf85fef63a12
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc5f01507bf893d1bffc682f65a01b9ff48ffa9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748481"
---
# <a name="designate-an-events-forwarding-server-sql-server-management-studio"></a><span data-ttu-id="5911b-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5911b-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5911b-103">En este tema se describe cómo designar un servidor al que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reenvía eventos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5911b-103">This topic describes how to designate a server to which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] forwards events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span></span> <span data-ttu-id="5911b-104">Observe que el reenvío de eventos se aplica a los eventos reenviados entre servidores, no a los eventos reenviados entre instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hospedadas en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="5911b-104">Note that event forwarding applies to events forwarded between servers, not to events forwarded between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hosted on a single computer.</span></span> <span data-ttu-id="5911b-105">Tenga en cuenta también que para recibir eventos reenviados, el servidor de administración de alertas debe ser una instancia predeterminada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5911b-105">Also note that in order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
 <span data-ttu-id="5911b-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5911b-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5911b-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5911b-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5911b-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5911b-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5911b-109">**Para designar un servidor de reenvío de eventos. utilizando:**</span><span class="sxs-lookup"><span data-stu-id="5911b-109">**To designate an events forwarding server, using:**</span></span>  
  
     [<span data-ttu-id="5911b-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5911b-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5911b-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5911b-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5911b-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5911b-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5911b-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="5911b-113">Permissions</span></span>  
 <span data-ttu-id="5911b-114">Requiere la pertenencia al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="5911b-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5911b-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5911b-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-an-events-forwarding-server"></a><span data-ttu-id="5911b-116">Para designar un servidor de reenvío de eventos</span><span class="sxs-lookup"><span data-stu-id="5911b-116">To designate an events forwarding server</span></span>  
  
1.  <span data-ttu-id="5911b-117">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor desde el que desea reenviar eventos a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="5911b-117">In **Object Explorer,** click the plus sign to expand the server from which you want to forward events to another server.</span></span>  
  
2.  <span data-ttu-id="5911b-118">Haga clic con el botón derecho en **Agente SQL Server** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5911b-118">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="5911b-119">En el cuadro de diálogo **Propiedades de Agente SQL Server -**_nombre_de_servidor_, en **Seleccionar una página**, haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="5911b-119">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Advanced**.</span></span>  

4.  <span data-ttu-id="5911b-120">En **Reenvío de eventos de SQL Server**, active la casilla **Reenviar eventos a otro servidor** .</span><span class="sxs-lookup"><span data-stu-id="5911b-120">Under **SQL Server event forwarding**, select the **Forward events to a different server** check box.</span></span>  
  
5.  <span data-ttu-id="5911b-121">En la lista **Servidor** , seleccione un servidor y, a continuación, en **Eventos**, realice una de las selecciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5911b-121">In the **Server** list, select a server, and then, under **Events**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="5911b-122">Seleccione la opción **No controlados** para reenviar solo los eventos que no han sido controlados por alertas locales.</span><span class="sxs-lookup"><span data-stu-id="5911b-122">Select **Unhandled events** to forward only the events that have not been handled by local alerts.</span></span>  
  
    -   <span data-ttu-id="5911b-123">Seleccione la opción **Todos los eventos** para reenviar todos los eventos, independientemente de si han sido controlados o no por alertas locales.</span><span class="sxs-lookup"><span data-stu-id="5911b-123">Select **All events** to forward all events regardless of whether they have been handled by local alerts.</span></span>  
  
6.  <span data-ttu-id="5911b-124">En la lista **Si el evento tiene una gravedad de o por encima de** , haga clic en el nivel de gravedad a partir del cual se reenvían los eventos al servidor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5911b-124">In the **If event has severity at or above** list, click the severity level at which events are forwarded to the selected server.</span></span>  
  
7.  <span data-ttu-id="5911b-125">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5911b-125">When finished, click **OK**.</span></span>  
  
  
