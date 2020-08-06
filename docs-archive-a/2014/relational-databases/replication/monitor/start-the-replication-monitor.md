---
title: Iniciar el Monitor de replicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, starting
ms.assetid: e037bd27-cc87-4ee9-9e5f-83f6d717cfa4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cff23206923825d0e86e47ad6921c19f45e68b35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750725"
---
# <a name="start-the-replication-monitor"></a><span data-ttu-id="4377d-102">Iniciar el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="4377d-102">Start the Replication Monitor</span></span>
  <span data-ttu-id="4377d-103">El Monitor de replicación se puede iniciar desde [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] en cualquier instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], o desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4377d-103">Replication Monitor can be started from [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] on any instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], or from the command prompt.</span></span> <span data-ttu-id="4377d-104">Tras iniciar el Monitor de replicación, agregue uno o más publicadores para supervisión.</span><span class="sxs-lookup"><span data-stu-id="4377d-104">After starting Replication Monitor, add one or more Publishers to monitor.</span></span> <span data-ttu-id="4377d-105">Para obtener más información, vea [Agregar y quitar publicadores del Monitor de replicación](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="4377d-105">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
### <a name="to-start-replication-monitor-from-sql-server-management-studio"></a><span data-ttu-id="4377d-106">Para iniciar el Monitor de replicación desde SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4377d-106">To start Replication Monitor from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="4377d-107">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="4377d-107">Connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="4377d-108">Haga clic con el botón secundario en la carpeta **Replicación** o en cualquiera de sus subcarpetas y, a continuación, haga clic en **Iniciar Monitor de replicación**.</span><span class="sxs-lookup"><span data-stu-id="4377d-108">Right-click the **Replication** folder or any of its subfolders, and then click **Launch Replication Monitor**.</span></span>  
  
### <a name="to-start-replication-monitor-from-the-command-prompt"></a><span data-ttu-id="4377d-109">Para iniciar el Monitor de replicación desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="4377d-109">To start Replication Monitor from the command prompt</span></span>  
  
1.  <span data-ttu-id="4377d-110">Desde el símbolo del sistema, navegue al directorio de instalación de herramientas.</span><span class="sxs-lookup"><span data-stu-id="4377d-110">From the command prompt, navigate to the tools installation directory.</span></span> <span data-ttu-id="4377d-111">La ruta de acceso predeterminada es [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\.</span><span class="sxs-lookup"><span data-stu-id="4377d-111">The default path is [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\ .</span></span>  
  
2.  <span data-ttu-id="4377d-112">Ejecute sqlmonitor.exe.</span><span class="sxs-lookup"><span data-stu-id="4377d-112">Run sqlmonitor.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4377d-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4377d-113">See Also</span></span>  
 [<span data-ttu-id="4377d-114">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="4377d-114">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
