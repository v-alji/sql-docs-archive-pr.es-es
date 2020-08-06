---
title: Conexión a una utilidad de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: b9b90b8d-241f-4b74-ac14-de7b10ea1821
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8e59a28e083fc302faebbcba932c18a04e73a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669681"
---
# <a name="connect-to-a-sql-server-utility"></a><span data-ttu-id="e1971-102">Conectarse a una utilidad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1971-102">Connect to a SQL Server Utility</span></span>
  <span data-ttu-id="e1971-103">Antes de poder conectarse a una utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , debe crear un punto de control de la utilidad (UCP).</span><span class="sxs-lookup"><span data-stu-id="e1971-103">Before you can connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, you must create a utility control point (UCP).</span></span> <span data-ttu-id="e1971-104">Para obtener más información, vea [Características y tareas de la utilidad de SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="e1971-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>

 <span data-ttu-id="e1971-105">Para ver y administrar el mantenimiento de los recursos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) para conectar a una utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1971-105">To view and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource health, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>

 <span data-ttu-id="e1971-106">Para conectarse a una utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a través de SSMS:</span><span class="sxs-lookup"><span data-stu-id="e1971-106">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility through SSMS:</span></span>

1.  <span data-ttu-id="e1971-107">Inicie SSMS.</span><span class="sxs-lookup"><span data-stu-id="e1971-107">Launch SSMS.</span></span>

2.  <span data-ttu-id="e1971-108">En SSMS, conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1971-108">In SSMS, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

3.  <span data-ttu-id="e1971-109">Haga clic en **Ver** y, a continuación, en **Explorador de la utilidad**.</span><span class="sxs-lookup"><span data-stu-id="e1971-109">Click **View** and then **Utility Explorer**.</span></span>

4.  <span data-ttu-id="e1971-110">En el panel de navegación del Explorador de la utilidad, haga clic en ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Conectar con la utilidad**.</span><span class="sxs-lookup"><span data-stu-id="e1971-110">In the Utility Explorer navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span>

5.  <span data-ttu-id="e1971-111">En el cuadro de diálogo **Conectar con el servidor** , especifique el nombre de instancia del UCP y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="e1971-111">In the **Connect to Server** dialog box, specify the UCP instance name, then click **Connect**.</span></span>

6.  <span data-ttu-id="e1971-112">Vea el panel de navegación del explorador de la utilidad para obtener una vista de árbol de los recursos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el UCP.</span><span class="sxs-lookup"><span data-stu-id="e1971-112">View the Utility Explorer Navigation Pane to see a tree view of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources in the UCP.</span></span>

 <span data-ttu-id="e1971-113">Cuando cree un UCP nuevo, también se conectará a la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1971-113">Creating a new UCP also connects you to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="e1971-114">Para obtener más información, vea [Crear un punto de control de la Utilidad de SQL Server &#40;Utilidad de SQL Server&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="e1971-114">For more information, see [Create a SQL Server Utility Control Point &#40;SQL Server Utility&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1971-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1971-115">See Also</span></span>
 <span data-ttu-id="e1971-116">[Utilidad de SQL Server características y tareas](sql-server-utility-features-and-tasks.md) [vista Resource Health resultados de la directiva &#40;utilidad de SQL Server&#41;](view-resource-health-policy-results-sql-server-utility.md)</span><span class="sxs-lookup"><span data-stu-id="e1971-116">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) [View Resource Health Policy Results &#40;SQL Server Utility&#41;](view-resource-health-policy-results-sql-server-utility.md)</span></span>


