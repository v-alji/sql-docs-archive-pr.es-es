---
title: Realizar manualmente la conmutación por error de una sesión de creación de reflejo de la base de datos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 4ecf9c63-b3a4-4c54-b553-5bc37973232b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f7f4547058b2dfd4229142dca73a7d9b4bdb239
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751454"
---
# <a name="manually-fail-over-a-database-mirroring-session-sql-server-management-studio"></a><span data-ttu-id="84c45-102">Realizar manualmente la conmutación por error de una sesión de creación de reflejo de la base de datos (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="84c45-102">Manually Fail Over a Database Mirroring Session (SQL Server Management Studio)</span></span>
  <span data-ttu-id="84c45-103">Cuando la base de datos reflejada se sincroniza (es decir, cuando el estado de la base de datos es SYNCHRONIZED), el propietario de la base de datos puede iniciar una conmutación por error manual en el servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="84c45-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span>  
  
 <span data-ttu-id="84c45-104">Durante una conmutación por error manual, los roles de servidor principal y reflejado se intercambian en la base de datos en la que se produce la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="84c45-104">During a manual failover, the principal and mirror server roles are swapped for the database on which the failover occurs.</span></span> <span data-ttu-id="84c45-105">La base de datos reflejada se convierte en la base de datos principal, y la base de datos principal se convierte en la reflejada.</span><span class="sxs-lookup"><span data-stu-id="84c45-105">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span> <span data-ttu-id="84c45-106">Por ejemplo, en la siguiente tabla se muestra cómo una conmutación por error manual intercambia los roles de dos asociados de creación de reflejo: `SQLDBENGINE0_1` y `SQLDBENGINE0_2`.</span><span class="sxs-lookup"><span data-stu-id="84c45-106">For example, the following table shows the how a manual failover swaps the roles of two mirroring partners: `SQLDBENGINE0_1` and `SQLDBENGINE0_2`.</span></span>  
  
|<span data-ttu-id="84c45-107">Server</span><span class="sxs-lookup"><span data-stu-id="84c45-107">Server</span></span>|<span data-ttu-id="84c45-108">Antes de la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="84c45-108">Before failover</span></span>|<span data-ttu-id="84c45-109">Después de la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="84c45-109">After failover</span></span>|  
|------------|---------------------|--------------------|  
|`SQLDBENGINE0_1`|<span data-ttu-id="84c45-110">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="84c45-110">PRINCIPAL</span></span>|<span data-ttu-id="84c45-111">MIRROR</span><span class="sxs-lookup"><span data-stu-id="84c45-111">MIRROR</span></span>|  
|`SQLDBENGINE0_2`|<span data-ttu-id="84c45-112">MIRROR</span><span class="sxs-lookup"><span data-stu-id="84c45-112">MIRROR</span></span>|<span data-ttu-id="84c45-113">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="84c45-113">PRINCIPAL</span></span>|  
  
 <span data-ttu-id="84c45-114">Observe que los roles de servidor de las demás sesiones de creación de reflejo de la base de datos no se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="84c45-114">Note that the server roles for other database mirroring sessions are not affected.</span></span> <span data-ttu-id="84c45-115">Para obtener más información, vea [Conmutación de roles durante una sesión de creación de reflejo de la base de datos &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="84c45-115">For more information, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
### <a name="to-manually-fail-over-database-mirroring"></a><span data-ttu-id="84c45-116">Para realizar manualmente una conmutación por error de la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="84c45-116">To manually fail over database mirroring</span></span>  
  
1.  <span data-ttu-id="84c45-117">Conéctese a la instancia de servidor principal y, en el panel **Explorador de objetos** , haga clic en el nombre del servidor para expandir el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="84c45-117">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="84c45-118">Expanda **Bases de datos**y seleccione la base de datos de la que se va a realizar la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="84c45-118">Expand **Databases**, and select the database to be failed over.</span></span>  
  
3.  <span data-ttu-id="84c45-119">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, luego, haga clic en **Reflejado**.</span><span class="sxs-lookup"><span data-stu-id="84c45-119">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="84c45-120">Así se abre la página **Creación de reflejo** del cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="84c45-120">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="84c45-121">Haga clic en **Conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="84c45-121">Click **Failover**.</span></span>  
  
     <span data-ttu-id="84c45-122">Aparece un cuadro de confirmación.</span><span class="sxs-lookup"><span data-stu-id="84c45-122">A confirmation box appears.</span></span>  <span data-ttu-id="84c45-123">El servidor principal intenta conectarse al servidor reflejado mediante la Autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="84c45-123">The principal server begins by trying to connect to the mirror server by using Windows Authentication.</span></span> <span data-ttu-id="84c45-124">Si la Autenticación de Windows no funciona, el servidor principal muestra el cuadro de diálogo **Conectar con el servidor** .</span><span class="sxs-lookup"><span data-stu-id="84c45-124">If Windows Authentication does not work, the principal server displays the **Connect to Server** dialog box.</span></span> <span data-ttu-id="84c45-125">Si el servidor reflejado usa la Autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , seleccione **Autenticación de SQL Server** en el cuadro **Autenticación** .</span><span class="sxs-lookup"><span data-stu-id="84c45-125">If the mirror server uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, select **SQL Server Authentication** in the **Authentication** box.</span></span> <span data-ttu-id="84c45-126">En el cuadro de texto **Inicio de sesión** , especifique la cuenta de inicio de sesión para conectar con el servidor reflejado, y en el cuadro de texto **Contraseña** , especifique la contraseña correspondiente a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="84c45-126">In the **Login** text box, specify the login account to connect with on the mirror server, and in the **Password** text box, specify the password for that account.</span></span>  
  
     <span data-ttu-id="84c45-127">Si la conmutación por error se realiza correctamente, se cierra el cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="84c45-127">If failover succeeds, the **Database Properties** dialog box closes.</span></span> <span data-ttu-id="84c45-128">La base de datos reflejada se convierte en la base de datos principal, y la base de datos principal se convierte en la reflejada.</span><span class="sxs-lookup"><span data-stu-id="84c45-128">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span>  
  
     <span data-ttu-id="84c45-129">Si no se puede efectuar la conmutación por error, aparece un mensaje de error y el cuadro de diálogo permanece abierto.</span><span class="sxs-lookup"><span data-stu-id="84c45-129">If failover fails, an error message is displayed and the dialog box remains open.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="84c45-130">Si ha modificado alguna propiedad desde que se abrió la página **Creación de reflejos** , estos cambios no se guardarán.</span><span class="sxs-lookup"><span data-stu-id="84c45-130">If you have modified any properties since opening the **Mirroring** page, those changes will not be saved.</span></span>  
  
     <span data-ttu-id="84c45-131">El cuadro de diálogo se cierra automáticamente.</span><span class="sxs-lookup"><span data-stu-id="84c45-131">The dialog box closes automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c45-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84c45-132">See Also</span></span>  
 <span data-ttu-id="84c45-133">[Propiedades de la base de datos &#40;página Creación de reflejo&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="84c45-133">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="84c45-134">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="84c45-134">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="84c45-135">[Realizar una conmutación por error manualmente de una sesión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="84c45-135">[Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="84c45-136">[Pausar o reanudar una sesión de creación de reflejo de la base de datos &#40;SQL Server&#41;](pause-or-resume-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="84c45-136">[Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;](pause-or-resume-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="84c45-137">Quitar la creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="84c45-137">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
  
