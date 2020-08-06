---
title: Apertura del Monitor de actividad (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server], setting the refresh interval
- refresh interval for Activity Monitor
- Activity Monitor [SQL Server], opening
- opening Activity Monitor
ms.assetid: 0a6eeb16-f02b-479d-9a60-543e40ebf46b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea74122ad18a0a1ede5eef1e09684606ca0ce073
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749241"
---
# <a name="open-activity-monitor-sql-server-management-studio"></a><span data-ttu-id="d59aa-102">Abrir el Monitor de actividad (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d59aa-102">Open Activity Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="d59aa-103">En este tema se describe cómo abrir el Monitor de actividad para obtener información sobre los procesos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y la forma en que estos procesos afectan a la instancia actual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d59aa-103">This topic describes how to open the Activity Monitor to obtain information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d59aa-104">También se describe cómo establecer el intervalo de actualización del Monitor de actividad.</span><span class="sxs-lookup"><span data-stu-id="d59aa-104">It also describes how to set the refresh interval of the Activity Monitor.</span></span>  
  
 <span data-ttu-id="d59aa-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d59aa-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d59aa-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="d59aa-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d59aa-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d59aa-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d59aa-108">**Para abrir el Monitor de actividad con:**</span><span class="sxs-lookup"><span data-stu-id="d59aa-108">**To open the Activity Monitor using:**</span></span>  
  
     [<span data-ttu-id="d59aa-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d59aa-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="d59aa-110">**Configuración del intervalo de actualización utilizando lo siguiente:**  [SQL Server Management Studio](#Refresh)</span><span class="sxs-lookup"><span data-stu-id="d59aa-110">**To set the refresh interval using:**  [SQL Server Management Studio](#Refresh)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d59aa-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d59aa-111">Before You Begin</span></span>  
 <span data-ttu-id="d59aa-112">El Monitor de actividad ejecuta consultas en la instancia supervisada para obtener información de sus paneles de información.</span><span class="sxs-lookup"><span data-stu-id="d59aa-112">Activity Monitor runs queries on the monitored instance to obtain information for the Activity Monitor display panes.</span></span> <span data-ttu-id="d59aa-113">Cuando el intervalo de actualización se establece en menos de 10 segundos, el tiempo utilizado para ejecutar estas consultas puede afectar al rendimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="d59aa-113">When the refresh interval is set to less than 10 seconds, the time that is used to run these queries can affect server performance</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d59aa-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d59aa-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d59aa-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="d59aa-115">Permissions</span></span>  
 <span data-ttu-id="d59aa-116">Para ver el Monitor de actividad, el usuario debe tener el permiso VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="d59aa-116">To view the Activity Monitor, a user must have VIEW SERVER STATE permission.</span></span> <span data-ttu-id="d59aa-117">Para ver la sección de E/S de archivo de datos del Monitor de actividad, debe tener permisos CREATE DATABASE, ALTER ANY DATABASE o VIEW ANY DEFINITION además de VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="d59aa-117">To view the Data File I/O section of Activity Monitor, you must have CREATE DATABASE, ALTER ANY DATABASE, or VIEW ANY DEFINITION permission in addition to VIEW SERVER STATE.</span></span>  
  
 <span data-ttu-id="d59aa-118">Para detener (KILL) un proceso, el usuario debe ser miembro de los roles fijos de servidor sysadmin o processadmin.</span><span class="sxs-lookup"><span data-stu-id="d59aa-118">To KILL a process, a user must be a member of the sysadmin or processadmin fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d59aa-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d59aa-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-open-activity-monitor-in-sql-server-management-studio"></a><span data-ttu-id="d59aa-120">Para abrir el Monitor de actividad en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d59aa-120">To open Activity Monitor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="d59aa-121">En la barra de herramientas estándar de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , haga clic en **Monitor de actividad**.</span><span class="sxs-lookup"><span data-stu-id="d59aa-121">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] standard toolbar, click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="d59aa-122">En el cuadro de diálogo **Conectar al servidor** , seleccione el nombre del servidor y el modo de autenticación y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="d59aa-122">In the **Connect to Server** dialog box, select the server name and authentication mode, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="d59aa-123">También puede abrir el Monitor de actividad en cualquier momento presionando CTRL+ALT A.</span><span class="sxs-lookup"><span data-stu-id="d59aa-123">You can also open Activity Monitor at any time by pressing CTRL+ALT A.</span></span>  
  
#### <a name="to-open-activity-monitor-in-object-explorer"></a><span data-ttu-id="d59aa-124">Para abrir el Monitor de actividad en el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="d59aa-124">To open Activity Monitor in Object Explorer</span></span>  
  
-   <span data-ttu-id="d59aa-125">En el Explorador de objetos, haga clic con el botón secundario en el nombre de instancia y, a continuación, seleccione **Monitor de actividad**.</span><span class="sxs-lookup"><span data-stu-id="d59aa-125">In Object Explorer, right-click the instance name, and then select **Activity Monitor**.</span></span>  
  
#### <a name="to-open-activity-monitor-when-opening-sql-server-management-studio"></a><span data-ttu-id="d59aa-126">Para abrir el Monitor de actividad al abrir SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d59aa-126">To open Activity Monitor when opening SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="d59aa-127">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="d59aa-127">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="d59aa-128">En el cuadro de diálogo **Opciones** , expanda **Entorno**y, a continuación, seleccione **General**.</span><span class="sxs-lookup"><span data-stu-id="d59aa-128">In the **Options** dialog box, expand **Environment**, and then select **General**.</span></span>  
  
3.  <span data-ttu-id="d59aa-129">En el cuadro **Al iniciar** , seleccione **Abrir el Explorador de objetos y el Monitor de actividad**.</span><span class="sxs-lookup"><span data-stu-id="d59aa-129">In the **At startup** box, select **Open Object Explorer and Activity Monitor**.</span></span>  
  
4.  <span data-ttu-id="d59aa-130">Para activar los cambios, cierre y vuelva a abrir [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d59aa-130">To activate the changes, close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-set-the-activity-monitor-refresh-interval"></a><a name="Refresh"></a><span data-ttu-id="d59aa-131">Para establecer el intervalo de actualización del monitor de actividad</span><span class="sxs-lookup"><span data-stu-id="d59aa-131">To Set the Activity Monitor Refresh Interval</span></span>  
  
-   <span data-ttu-id="d59aa-132">Abra el Monitor de actividad.</span><span class="sxs-lookup"><span data-stu-id="d59aa-132">Open the Activity Monitor.</span></span>  
  
-   <span data-ttu-id="d59aa-133">Haga clic con el botón derecho en **Información general**, seleccione **Intervalo de actualización**y después seleccione el intervalo en el que el Monitor de actividad debería obtener nueva información de la instancia.</span><span class="sxs-lookup"><span data-stu-id="d59aa-133">Right-click **Overview**, select **Refresh Interval**, and then select the interval in which Activity Monitor should obtain new instance information.</span></span>  
  
  
