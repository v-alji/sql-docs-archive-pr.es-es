---
title: Iniciar el Monitor de creación de reflejo de la base de datos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- monitoring database mirroring [SQL Server]
- Database Mirroring Monitor [SQL Server], starting
- database mirroring [SQL Server], monitoring
ms.assetid: 53165335-97ca-4f88-8e78-22f1839dee98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67c7b393b28d4d400535281c18c637146a5d8da7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662246"
---
# <a name="start-database-mirroring-monitor-sql-server-management-studio"></a><span data-ttu-id="e2fc3-102">Iniciar el Monitor de creación de reflejo de la base de datos (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e2fc3-102">Start Database Mirroring Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="e2fc3-103">El Monitor de creación de reflejo de la base de datos forma parte del Monitor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , que se inicia desde [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2fc3-103">The Database Mirroring Monitor is part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Monitor, which is launched from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2fc3-104">El Monitor de creación de reflejo de la base de datos no está disponible en todas las ediciones de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2fc3-104">Database Mirroring Monitor is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e2fc3-105">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="e2fc3-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
### <a name="to-launch-the-database-mirroring-monitor"></a><span data-ttu-id="e2fc3-106">Para iniciar el Monitor de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="e2fc3-106">To launch the Database Mirroring Monitor</span></span>  
  
1.  <span data-ttu-id="e2fc3-107">Después de conectarse a la instancia del servidor principal, en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol del servidor.</span><span class="sxs-lookup"><span data-stu-id="e2fc3-107">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="e2fc3-108">Expanda **Bases de datos**y seleccione la base de datos que desee supervisar.</span><span class="sxs-lookup"><span data-stu-id="e2fc3-108">Expand **Databases**, and select the database to be monitored.</span></span>  
  
3.  <span data-ttu-id="e2fc3-109">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, luego, haga clic en **Iniciar Monitor de creación de reflejo de la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="e2fc3-109">Right-click the database, select **Tasks**, and then click **Launch Database Mirroring Monitor**.</span></span>  
  
4.  <span data-ttu-id="e2fc3-110">En el cuadro de diálogo **Monitor de creación de reflejo de la base de datos** , haga clic en **Registrar base de datos reflejada** para registrar una o varias bases de datos reflejadas.</span><span class="sxs-lookup"><span data-stu-id="e2fc3-110">In the **Database Mirroring Monitor** dialog box, click **Register Mirrored Database** to register one or more mirrored database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e2fc3-111">Al registrar una base de datos en un asociado, la base de datos se registra automáticamente en el otro asociado.</span><span class="sxs-lookup"><span data-stu-id="e2fc3-111">When you register a database at one partner, the database is automatically registered at the other partner.</span></span> <span data-ttu-id="e2fc3-112">Si el monitor ya dispone de credenciales de conexión para la otra instancia de asociado, se utilizan para conectarse.</span><span class="sxs-lookup"><span data-stu-id="e2fc3-112">If the monitor already has connection credentials for the other partner instance, those are used to connect.</span></span> <span data-ttu-id="e2fc3-113">De lo contrario, el monitor intenta conectarse mediante Autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e2fc3-113">Otherwise the monitor attempts to connect using Windows Authentication.</span></span> <span data-ttu-id="e2fc3-114">Si desea cambiar las credenciales utilizadas para conectarse a una de las instancias del servidor, haga clic en **Mostrar el cuadro de diálogo para administrar conexiones de instancia del servidor cuando haga clic en Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e2fc3-114">If you want to change the credentials used to connect to either server instance, click **Show the Manage Server Connections dialog box when I click OK**.</span></span>  
  
 <span data-ttu-id="e2fc3-115">Para obtener más información sobre el Monitor de creación de reflejo de la base de datos, vea [Información general del Monitor de creación de reflejo de la base de datos](database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e2fc3-115">For more information about Database Mirroring Monitor, see [Database Mirroring Monitor Overview](database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2fc3-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2fc3-116">See Also</span></span>  
 <span data-ttu-id="e2fc3-117">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e2fc3-117">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="e2fc3-118">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e2fc3-118">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
  
