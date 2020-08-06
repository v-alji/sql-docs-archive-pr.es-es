---
title: Obtener acceso al proveedor WMI para la administración de configuración mediante WQL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
ms.assetid: 26499530-d93b-452b-bbe4-217ef1d11e68
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b58297c5e292ceb18a6e2e50e2b25b9aa352e2fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661831"
---
# <a name="access-wmi-provider-for-configuration-management-using-wql"></a><span data-ttu-id="3a872-102">Obtener acceso al proveedor WMI para la administración de configuración mediante WQL</span><span class="sxs-lookup"><span data-stu-id="3a872-102">Access WMI Provider for Configuration Management using WQL</span></span>
  <span data-ttu-id="3a872-103">En esta sección se describe cómo ejecutar instrucciones WQL (Lenguaje de consulta de Instrumental de administración de Windows) de [!INCLUDE[msCoName](../../includes/msconame-md.md)] con el proveedor WMI para la Administración de equipos.</span><span class="sxs-lookup"><span data-stu-id="3a872-103">This section describes how to execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Management Instrumentation Query Language (WQL) statements against the WMI Provider for Computer Management.</span></span>  
  
 <span data-ttu-id="3a872-104">En el ejemplo se usa un editor WQL, WBEMtest.exe, para ejecutar las consultas WQL con el proveedor WMI y enumerar servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], protocolos de red y alias.</span><span class="sxs-lookup"><span data-stu-id="3a872-104">The example uses a WQL editor, WBEMtest.exe, to run WQL queries against the WMI Provider to enumerate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network protocols, and aliases.</span></span>  
  
### <a name="querying-services-using-wbemtest"></a><span data-ttu-id="3a872-105">Consultar los servicios mediante WBEMtest</span><span class="sxs-lookup"><span data-stu-id="3a872-105">Querying services using WBEMtest</span></span>  
  
1.  <span data-ttu-id="3a872-106">En el menú **Inicio** , haga clic en **Ejecutar**y, a continuación, escriba `WBEMtest` .</span><span class="sxs-lookup"><span data-stu-id="3a872-106">From the **Start** menu, click **Run**, and then enter `WBEMtest`.</span></span>  
  
2.  <span data-ttu-id="3a872-107">El diálogo de WBEMtest.exe aparece.</span><span class="sxs-lookup"><span data-stu-id="3a872-107">The WBEMtest.exe dialog appears.</span></span> <span data-ttu-id="3a872-108">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="3a872-108">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="3a872-109">En el primer campo de texto, escriba el espacio de nombres del proveedor WMI de Administración de equipos: raíz\Microsoft\SqlServer\ComputerManagement11.</span><span class="sxs-lookup"><span data-stu-id="3a872-109">In the first text field, type the WMI Provider for Computer Management namespace: root\Microsoft\SqlServer\ComputerManagement11.</span></span> <span data-ttu-id="3a872-110">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="3a872-110">Click **Connect**.</span></span>  
  
4.  <span data-ttu-id="3a872-111">Haga clic en **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3a872-111">Click **Query**.</span></span> <span data-ttu-id="3a872-112">Escriba una consulta que devuelva los servicios actuales que se ejecutan en el equipo local: **SELECT \* from SqlService.**</span><span class="sxs-lookup"><span data-stu-id="3a872-112">Type a query that returns the current services running on the local computer: **SELECT \* FROM SqlService.**</span></span> <span data-ttu-id="3a872-113">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="3a872-113">Click **Apply**.</span></span>  
  
5.  <span data-ttu-id="3a872-114">Además, refine la consulta agregando `WHERE ServiceName = "MSSQLSERVER"`.</span><span class="sxs-lookup"><span data-stu-id="3a872-114">Further refine the query by adding `WHERE ServiceName = "MSSQLSERVER"`.</span></span>  
  
  
