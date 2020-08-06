---
title: Cambiar la cuenta de proxy para el conjunto de recopilación de la utilidad en un Instancia administrada de SQL Server (Utilidad de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ff37ba8b-a08c-4109-b6e2-5748c995a52c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19f60c607ed661ef42c1c1c0e48854cdfd69a912
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669688"
---
# <a name="change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server-sql-server-utility"></a><span data-ttu-id="2c513-102">Cambiar la cuenta de proxy para el conjunto de recopilación de la utilidad en una instancia administrada de SQL Server (utilidad de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2c513-102">Change the Proxy Account for the Utility Collection Set on a Managed Instance of SQL Server (SQL Server Utility)</span></span>
  <span data-ttu-id="2c513-103">En este tema se describe cómo cambiar la cuenta de proxy para el conjunto de recopilación de utilidades en una instancia administrada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c513-103">This topic describes how to change the proxy account for the Utility Collection Set on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2c513-104">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2c513-104">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server"></a><span data-ttu-id="2c513-105">Para cambiar la cuenta de proxy para el conjunto de recopilación de utilidades en una instancia administrada de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c513-105">To change the proxy account for the utility collection set on a managed instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="2c513-106">Quite la instancia administrada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c513-106">Remove the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
    -   <span data-ttu-id="2c513-107">En **Explorador de la utilidad** de SSMS, haga clic en el nodo **Instancias administradas** .</span><span class="sxs-lookup"><span data-stu-id="2c513-107">In **Utility Explorer** in SSMS, click on the **Managed Instances** node.</span></span>  
  
    -   <span data-ttu-id="2c513-108">En la vista de lista del **Explorador de la utilidad**, haga clic con el botón derecho en el nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y seleccione **Quitar instancia administrada...** . Para obtener más información, vea [Quitar una instancia de SQL Server de la Utilidad de SQL Server](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2c513-108">In the **Utility Explorer** list view, right-click the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name, and select **Remove Managed Instance...**. For more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
2.  <span data-ttu-id="2c513-109">Vuelva a inscribir la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c513-109">Enroll the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility again.</span></span>  
  
    -   <span data-ttu-id="2c513-110">En el **Explorador de la utilidad** de SSMS, haga clic con el botón derecho en el nodo **Instancias administradas** y seleccione **Agregar instancia administrada...** .</span><span class="sxs-lookup"><span data-stu-id="2c513-110">In **Utility Explorer** in SSMS, right-click on the **Managed Instances** node, and select **Add Managed Instance...**.</span></span>  
  
    -   <span data-ttu-id="2c513-111">Siga las indicaciones para completar el asistente y especifique la nueva cuenta de proxy.</span><span class="sxs-lookup"><span data-stu-id="2c513-111">Follow prompts to complete the wizard, specifying the new proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c513-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c513-112">See Also</span></span>  
 <span data-ttu-id="2c513-113">[Características y tareas de la utilidad de SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="2c513-113">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="2c513-114">Solucionar problemas de la Utilidad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c513-114">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
