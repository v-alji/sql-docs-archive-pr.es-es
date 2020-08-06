---
title: Ver el estado de una base de datos reflejada (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- states [SQL Server], database mirroring
- database mirroring [SQL Server], states
ms.assetid: 544f4194-253e-4c57-96ca-31c16301434f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc691e8b746a816ab88448e3399aebad6d8844e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671669"
---
# <a name="view-the-state-of-a-mirrored-database-sql-server-management-studio"></a><span data-ttu-id="a96a8-102">Ver el estado de una base de datos reflejada (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a96a8-102">View the State of a Mirrored Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="a96a8-103">Durante una sesión de creación de reflejo de la base de datos, puede ver el estado en la página **Creación de reflejos** del cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="a96a8-103">During a database mirroring session, you can view the status on the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
### <a name="to-view-the-status-of-a-database-mirroring-session"></a><span data-ttu-id="a96a8-104">Para ver el estado de una sesión de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="a96a8-104">To view the status of a database mirroring session</span></span>  
  
1.  <span data-ttu-id="a96a8-105">Después de conectarse a la instancia del servidor principal, en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol del servidor.</span><span class="sxs-lookup"><span data-stu-id="a96a8-105">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="a96a8-106">Expanda **Bases de datos**y seleccione la base de datos que se va a reflejar.</span><span class="sxs-lookup"><span data-stu-id="a96a8-106">Expand **Databases**, and select the database to be mirrored.</span></span>  
  
3.  <span data-ttu-id="a96a8-107">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, luego, haga clic en **Reflejado**.</span><span class="sxs-lookup"><span data-stu-id="a96a8-107">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="a96a8-108">Así se abre la página **Creación de reflejo** del cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="a96a8-108">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="a96a8-109">Una vez que se inicie la creación de reflejo, en el panel **Estado** se muestra el estado de la sesión de creación de reflejo de la base de datos a partir del momento en que seleccionó la página **Creación de reflejos** o hizo clic en el botón **Actualizar** .</span><span class="sxs-lookup"><span data-stu-id="a96a8-109">After mirroring begins, the **Status** panel displays the status of the database mirroring session as of when you selected the **Mirroring** page or clicked the **Refresh** button.</span></span> <span data-ttu-id="a96a8-110">Los posibles estados son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a96a8-110">The possible states are as follows:</span></span>  
  
    |<span data-ttu-id="a96a8-111">States</span><span class="sxs-lookup"><span data-stu-id="a96a8-111">States</span></span>|<span data-ttu-id="a96a8-112">Explicación</span><span class="sxs-lookup"><span data-stu-id="a96a8-112">Explanation</span></span>|  
    |------------|-----------------|  
    |\<blank>|<span data-ttu-id="a96a8-113">No existe ninguna sesión de creación de reflejo de la base de datos y no hay actividad de la que informar en la página **Creación de reflejo** .</span><span class="sxs-lookup"><span data-stu-id="a96a8-113">No database mirroring session exists and there is no activity to report on the **Mirroring** page.</span></span>|  
    |<span data-ttu-id="a96a8-114">En pausa</span><span class="sxs-lookup"><span data-stu-id="a96a8-114">Paused</span></span>|<span data-ttu-id="a96a8-115">La base de datos principal está en ejecución pero no envía ningún registro al servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="a96a8-115">The principal database is running but is not sending any logs to the mirror server.</span></span> <span data-ttu-id="a96a8-116">La copia reflejada de la base de datos no está disponible.</span><span class="sxs-lookup"><span data-stu-id="a96a8-116">The mirror copy of the database is not available.</span></span>|  
    |<span data-ttu-id="a96a8-117">Sin conexión</span><span class="sxs-lookup"><span data-stu-id="a96a8-117">No connection</span></span>|<span data-ttu-id="a96a8-118">La instancia de servidor principal no puede conectar con su asociado o con la instancia de servidor testigo (si la hay)</span><span class="sxs-lookup"><span data-stu-id="a96a8-118">The principal server instance cannot connect to its partner or to the witness server instance (if any)</span></span>|  
    |<span data-ttu-id="a96a8-119">Sincronizando</span><span class="sxs-lookup"><span data-stu-id="a96a8-119">Synchronizing</span></span>|<span data-ttu-id="a96a8-120">El contenido de la base de datos reflejada está atrasado con respecto al contenido de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a96a8-120">The contents of the mirror database are lagging behind the contents of the principal database.</span></span> <span data-ttu-id="a96a8-121">La instancia de servidor principal envía las entradas de registro a la instancia del servidor reflejado, que aplica los cambios en la base de datos reflejada para confirmarla.</span><span class="sxs-lookup"><span data-stu-id="a96a8-121">The principal server instance is sending log records to the mirror server instance, which is applying the changes to the mirror database to roll it forward.</span></span><br /><br /> <span data-ttu-id="a96a8-122">Al inicio de una sesión de creación de reflejo de la base de datos, las bases de datos reflejada y principal se encuentran en el estado de sincronización.</span><span class="sxs-lookup"><span data-stu-id="a96a8-122">At the start of a database mirroring session, the mirror and principal databases are in the synchronizing state.</span></span>|  
    |<span data-ttu-id="a96a8-123">Conmutación por error</span><span class="sxs-lookup"><span data-stu-id="a96a8-123">Failover</span></span>|<span data-ttu-id="a96a8-124">En la instancia de servidor principal se ha iniciado una conmutación por error manual (intercambio de roles) pero el servidor reflejado todavía no la ha aceptado.</span><span class="sxs-lookup"><span data-stu-id="a96a8-124">On the principal server instance, a manual failover (role swap) has begun but has not yet accepted by the mirror.</span></span>|  
    |<span data-ttu-id="a96a8-125">Sincronizado</span><span class="sxs-lookup"><span data-stu-id="a96a8-125">Synchronized</span></span>|<span data-ttu-id="a96a8-126">La base de datos reflejada contiene los mismos datos que la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a96a8-126">The mirror database contains the same data as the principal database.</span></span> <span data-ttu-id="a96a8-127">La conmutación por error manual y automática es posible *solo* en el estado sincronizado.</span><span class="sxs-lookup"><span data-stu-id="a96a8-127">Manual and automatic failover are possible *only* in the synchronized state.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a96a8-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a96a8-128">See Also</span></span>  
 [<span data-ttu-id="a96a8-129">Estados de creación de reflejo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a96a8-129">Mirroring States &#40;SQL Server&#41;</span></span>](mirroring-states-sql-server.md)  
  
  
