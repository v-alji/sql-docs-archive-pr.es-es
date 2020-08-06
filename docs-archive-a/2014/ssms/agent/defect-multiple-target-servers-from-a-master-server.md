---
title: Dar de baja varios servidores de destino desde un servidor maestro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
- multiple target server defections
ms.assetid: 61a3713b-403a-4806-bfc4-66db72ca1156
author: stevestein
ms.author: sstein
ms.openlocfilehash: b31a8bc38968733de0a23f67a71772721c8baedd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745636"
---
# <a name="defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="2f94d-102">Defect Multiple Target Servers from a Master Server</span><span class="sxs-lookup"><span data-stu-id="2f94d-102">Defect Multiple Target Servers from a Master Server</span></span>
  <span data-ttu-id="2f94d-103">En este tema se describe cómo dar de baja varios servidores de destino desde una configuración de administración multiservidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f94d-103">This topic describes how to defect multiple target servers from a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2f94d-104">Ejecute este procedimiento en el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="2f94d-104">Run this procedure from the master server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2f94d-105">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f94d-105">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="2f94d-106">Para dar de baja varios servidores de destino desde un servidor maestro</span><span class="sxs-lookup"><span data-stu-id="2f94d-106">To defect multiple target servers from a master server</span></span>  
  
1.  <span data-ttu-id="2f94d-107">En el **Explorador de objetos**, expanda un servidor que esté configurado como servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="2f94d-107">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="2f94d-108">Haga clic con el botón derecho en **Agente SQL Server**, seleccione **Administración multiservidor**y, luego, haga clic en **Administrar servidores de destino**.</span><span class="sxs-lookup"><span data-stu-id="2f94d-108">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="2f94d-109">Haga clic en **Exponer instrucciones**, y, a continuación, en la lista **Tipo de instrucción** , haga clic en **Dar de baja**.</span><span class="sxs-lookup"><span data-stu-id="2f94d-109">Click **Post Instructions**, and then in the **Instruction type** list, select **Defect**.</span></span>  
  
4.  <span data-ttu-id="2f94d-110">En **Destinatarios**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2f94d-110">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="2f94d-111">Haga clic en **Todos los servidores de destino** para dar de baja todos los servidores de destino de este servidor principal.</span><span class="sxs-lookup"><span data-stu-id="2f94d-111">Click **All target servers** to defect all target servers of this master server.</span></span> <span data-ttu-id="2f94d-112">Utilice esta opción si desea desinstalar totalmente la configuración de la administración multiservidor actual.</span><span class="sxs-lookup"><span data-stu-id="2f94d-112">Use this option if you want to completely uninstall the current multiserver administration configuration.</span></span>  
  
    -   <span data-ttu-id="2f94d-113">Haga clic en **Estos servidores de destino**y, a continuación, active la casilla **Seleccionar** correspondiente para dar de baja algunos servidores de destino, pero no todos, de este servidor principal.</span><span class="sxs-lookup"><span data-stu-id="2f94d-113">Click **These target servers**, and then click the corresponding **Select** box, to defect some, but not all, target servers of this master server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f94d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f94d-114">See Also</span></span>  
 <span data-ttu-id="2f94d-115">[Crear un entorno multiservidor](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="2f94d-115">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="2f94d-116">[Administración automatizada en una empresa](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="2f94d-116">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="2f94d-117">Dar de baja un servidor de destino desde un servidor maestro</span><span class="sxs-lookup"><span data-stu-id="2f94d-117">Defect a Target Server from a Master Server</span></span>](defect-a-target-server-from-a-master-server.md)  
  
  
