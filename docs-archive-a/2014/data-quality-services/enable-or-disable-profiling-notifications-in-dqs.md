---
title: Habilitar o deshabilitar notificaciones de generación de perfiles en DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- enable notifications
- notifications,enable
- notifications,disable
ms.assetid: e439bb29-60cc-4afd-a79a-f629b8d843c1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b3b5e8cec1cac3eb1ce4357480c0f994a33d4c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745983"
---
# <a name="enable-or-disable-profiling-notifications-in-dqs"></a><span data-ttu-id="08020-102">Habilitar o deshabilitar notificaciones de generación de perfiles en DQS</span><span class="sxs-lookup"><span data-stu-id="08020-102">Enable or Disable Profiling Notifications in DQS</span></span>
  <span data-ttu-id="08020-103">En este tema se describe cómo habilitar o deshabilitar las notificaciones de generación de perfiles en [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="08020-103">This topic describes how to enable or disable profiling notifications in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="08020-104">De forma predeterminada, las notificaciones de generación de perfiles están habilitadas en DQS.</span><span class="sxs-lookup"><span data-stu-id="08020-104">By default, profiling notifications are enabled in DQS.</span></span> <span data-ttu-id="08020-105">Las notificaciones de generación de perfiles le permiten conocer hechos importantes sobre el origen de datos y la eficacia de la actividad actual llevada a cabo en los datos.</span><span class="sxs-lookup"><span data-stu-id="08020-105">Profiling notifications tell you important facts about the data source and the effectiveness of the current activity performed on the data.</span></span> <span data-ttu-id="08020-106">Para obtener más información, consulte [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="08020-106">For more information, see [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="08020-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="08020-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="08020-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="08020-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="08020-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="08020-109">Permissions</span></span>  
 <span data-ttu-id="08020-110">Debe disponer del rol dqs_administrator en la base de datos DQS_MAIN para habilitar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="08020-110">You must have the dqs_administrator role on the DQS_MAIN database to enable notifications.</span></span>  
  
##  <a name="enable-or-disable-profiling-notifications"></a><a name="Enable"></a><span data-ttu-id="08020-111">Habilitar o deshabilitar las notificaciones de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="08020-111">Enable or Disable Profiling Notifications</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="08020-112">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="08020-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="08020-113">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="08020-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="08020-114">A continuación, haga clic en la pestaña **Configuración general** .</span><span class="sxs-lookup"><span data-stu-id="08020-114">Next, click the **General Settings** tab.</span></span>  
  
4.  <span data-ttu-id="08020-115">Active o desactive la casilla **Habilitar notificaciones** para deshabilitar o habilitar las notificaciones de generación de perfiles en distintas actividades en DQS.</span><span class="sxs-lookup"><span data-stu-id="08020-115">Clear or select the **Enable Notifications** check box to disable or enable profiling notifications for various activities in DQS.</span></span>  
  
5.  <span data-ttu-id="08020-116">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="08020-116">Click **Close**.</span></span>  
  
  
