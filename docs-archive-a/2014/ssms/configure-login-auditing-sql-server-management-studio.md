---
title: Configurar la auditoría de inicio de sesión (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], logins
- logins [SQL Server], auditing
ms.assetid: 16961116-57ac-4eef-8037-791b26ade548
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7e05f6c254e098a67a5ce00435c009cd450af44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677344"
---
# <a name="configure-login-auditing-sql-server-management-studio"></a><span data-ttu-id="3358f-102">Configurar la auditoría de inicio de sesión (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3358f-102">Configure Login Auditing (SQL Server Management Studio)</span></span>
  <span data-ttu-id="3358f-103">En este tema se describe cómo configurar la auditoría de inicio de sesión en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] para supervisar la actividad de inicio de sesión de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3358f-103">This topic describes how to configure login auditing in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] to monitor [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] login activity.</span></span> <span data-ttu-id="3358f-104">Se puede configurar para que escriba en el registro de errores cuando se produzcan los eventos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="3358f-104">Login auditing can be configured to write to the error log on the following events.</span></span>  
  
-   <span data-ttu-id="3358f-105">Inicios de sesión erróneos</span><span class="sxs-lookup"><span data-stu-id="3358f-105">Failed logins</span></span>  
  
-   <span data-ttu-id="3358f-106">Inicios de sesión correctos</span><span class="sxs-lookup"><span data-stu-id="3358f-106">Successful logins</span></span>  
  
-   <span data-ttu-id="3358f-107">Inicios de sesión correctos y erróneos</span><span class="sxs-lookup"><span data-stu-id="3358f-107">Both failed and successful logins</span></span>  
  
 <span data-ttu-id="3358f-108">Para que esta opción surta efecto, debe reiniciar [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3358f-108">You must restart [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before this option will take effect.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3358f-109">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3358f-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-login-auditing"></a><span data-ttu-id="3358f-110">Para configurar la auditoría de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="3358f-110">To configure login auditing</span></span>  
  
1.  <span data-ttu-id="3358f-111">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], conéctese a una instancia de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] con el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="3358f-111">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="3358f-112">En el Explorador de objetos, haga clic con el botón derecho en el nombre del servidor y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3358f-112">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3358f-113">En la página **Seguridad** , bajo **Auditoría de inicio de sesión** , haga clic en la opción que desee y cierre la página **Propiedades del servidor** .</span><span class="sxs-lookup"><span data-stu-id="3358f-113">On the **Security** page, under **Login** auditing, click the desired option and close the **Server Properties** page.</span></span>  
  
4.  <span data-ttu-id="3358f-114">En el Explorador de objetos, haga clic con el botón derecho en el nombre del servidor y, luego, haga clic en **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="3358f-114">In Object Explorer, right-click the server name, and then click **Restart**.</span></span>  
  
  
