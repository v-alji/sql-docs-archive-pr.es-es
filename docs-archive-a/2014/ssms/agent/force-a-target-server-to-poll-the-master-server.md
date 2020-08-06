---
title: Forzar que un servidor de destino sondee el servidor maestro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- forcing master server polling
- polling master servers [SQL Server]
- master servers [SQL Server], polling
- target servers [SQL Server], polling the master server
ms.assetid: f1189a47-5ac3-45e2-9c5f-847810672279
author: stevestein
ms.author: sstein
ms.openlocfilehash: b37bf19bfe8e8fb55c29c8d94c28a341d06df5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662482"
---
# <a name="force-a-target-server-to-poll-the-master-server"></a><span data-ttu-id="6be78-102">Force a Target Server to Poll the Master Server</span><span class="sxs-lookup"><span data-stu-id="6be78-102">Force a Target Server to Poll the Master Server</span></span>
  <span data-ttu-id="6be78-103">En este tema se describe cómo forzar que un servidor de destino sondee el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="6be78-103">This topic describes how to force a target server to poll the master server.</span></span> <span data-ttu-id="6be78-104">El servidor de destino debe ser un servidor registrado en el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="6be78-104">The target server must be a registered server on the master server.</span></span>  
  
 <span data-ttu-id="6be78-105">Un trabajo es una serie especificada de acciones que realiza el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6be78-105">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="6be78-106">Un trabajo multiservidor es un trabajo que ejecuta un servidor maestro en uno o más servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="6be78-106">A multiserver job is a job that a master server runs on one or more target servers.</span></span> <span data-ttu-id="6be78-107">Cada servidor de destino puede ejecutar una instancia del mismo trabajo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="6be78-107">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="6be78-108">Cada servidor de destino sondea periódicamente al servidor maestro, descarga una copia de cualquier nuevo trabajo asignado al servidor de destino y, a continuación, se desconecta.</span><span class="sxs-lookup"><span data-stu-id="6be78-108">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="6be78-109">El servidor de destino ejecuta el trabajo de manera local y, a continuación, se vuelve a conectar al servidor maestro para cargar el estado del resultado del trabajo.</span><span class="sxs-lookup"><span data-stu-id="6be78-109">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6be78-110">Si no es posible el acceso al servidor maestro cuando el servidor de destino intenta cargar el estado del trabajo, dicho estado de trabajo se coloca en la cola hasta que se pueda obtener acceso al servidor principal.</span><span class="sxs-lookup"><span data-stu-id="6be78-110">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
-   <span data-ttu-id="6be78-111">**Antes de empezar:**  [Limitaciones y restricciones](#Restrictions), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="6be78-111">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="6be78-112">**Acción de forzar que un servidor de destino sondee el servidor maestro utilizando lo siguiente:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="6be78-112">**To force a target server to poll the master server, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6be78-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6be78-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6be78-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6be78-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="6be78-115">El servidor de destino debe ser un servidor registrado en el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="6be78-115">The target server must be a registered server on the master server.</span></span> <span data-ttu-id="6be78-116">Debe ejecutar las instrucciones proporcionadas en este tema desde el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="6be78-116">You must run the instructions given in this topic from the master server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6be78-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6be78-117">Security</span></span>  
 <span data-ttu-id="6be78-118">Para obtener información detallada, vea [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) y [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="6be78-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="6be78-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6be78-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6be78-120">**Para forzar que un servidor de destino sondee el servidor maestro**</span><span class="sxs-lookup"><span data-stu-id="6be78-120">**To force a target server to poll the master server**</span></span>  
  
1.  <span data-ttu-id="6be78-121">En el **Explorador de objetos**, expanda el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="6be78-121">In **Object Explorer**, expand the master server.</span></span>  
  
2.  <span data-ttu-id="6be78-122">Haga clic con el botón derecho en **Agente SQL Server**, seleccione **Administración multiservidor**y, luego, haga clic en **Administrar servidores de destino**.</span><span class="sxs-lookup"><span data-stu-id="6be78-122">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="6be78-123">Haga clic en un servidor de destino y, a continuación, haga clic en **Forzar sondeo**.</span><span class="sxs-lookup"><span data-stu-id="6be78-123">Click a target server, and then click **Force Poll**.</span></span>  
  
  
