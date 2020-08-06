---
title: Ver conflictos de datos para publicaciones transaccionales (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- conflict resolution [SQL Server replication], queued updating subscriptions
- queued updating subscriptions [SQL Server replication]
- viewing conflict information
ms.assetid: 9977dd75-b0de-4376-9c13-86d80567d8aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 228753c113bcf43ed276d989a3996e9bf23bfc16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675805"
---
# <a name="view-data-conflicts-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="342ef-102">Ver conflictos de datos para publicaciones transaccionales (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="342ef-102">View Data Conflicts for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="342ef-103">Puede ver los conflictos surgidos en la replicación transaccional punto a punto y la replicación transaccional con suscripciones de actualización en cola en el [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visor de conflictos de replicación.</span><span class="sxs-lookup"><span data-stu-id="342ef-103">You can view conflicts for peer-to-peer transactional replication and transactional replication with queued updating subscriptions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replication Conflict Viewer.</span></span> <span data-ttu-id="342ef-104">Para obtener información sobre cómo se detectan y resuelven los conflictos, vea [Detección de conflictos en la replicación punto a punto](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) y [Establecer opciones de resolución de conflictos de actualización en cola &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="342ef-104">For information about how conflicts are detected and resolved, see [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) and [Set Queued Updating Conflict Resolution Options &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span></span>  
  
 <span data-ttu-id="342ef-105">Que haya datos disponibles sobre los conflictos depende del tipo de replicación y del período de retención del conflicto.</span><span class="sxs-lookup"><span data-stu-id="342ef-105">The availability of conflict data depends on the type of replication and the conflict retention period:</span></span>  
  
-   <span data-ttu-id="342ef-106">En el caso de la replicación punto a punto, el Agente de distribución genera un error de forma predeterminada cuando detecta un conflicto.</span><span class="sxs-lookup"><span data-stu-id="342ef-106">For peer-to-peer replication, by default, the Distribution Agent fails when it detects a conflict.</span></span> <span data-ttu-id="342ef-107">Se registra un error de conflicto en el registro de errores, pero no se registra ningún dato de conflicto en la tabla de conflictos, por lo que no está disponible para verse.</span><span class="sxs-lookup"><span data-stu-id="342ef-107">A conflict error is logged into the error log, but no conflict data is logged into the conflict table; therefore it is not available for viewing.</span></span> <span data-ttu-id="342ef-108">Si el Agente de distribución puede continuar, se registra un conflicto localmente en cada nodo donde se detectó.</span><span class="sxs-lookup"><span data-stu-id="342ef-108">If the Distribution Agent is allowed to continue, a conflict is logged locally on each node where it was detected.</span></span> <span data-ttu-id="342ef-109">Para obtener más información, vea "Controlar los conflictos" en [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span><span class="sxs-lookup"><span data-stu-id="342ef-109">For more information, see "Handling Conflicts" in [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span></span>  
  
-   <span data-ttu-id="342ef-110">En el caso de las suscripciones de actualización en cola, hay datos disponibles de cada conflicto.</span><span class="sxs-lookup"><span data-stu-id="342ef-110">For queued updating subscriptions, data is available for every conflict.</span></span> <span data-ttu-id="342ef-111">Los datos de conflictos están disponibles en el Visor de conflictos de replicación durante el tiempo especificado como período de retención de conflictos, con un valor predeterminado de 14 días.</span><span class="sxs-lookup"><span data-stu-id="342ef-111">Conflict data is available in the Replication Conflict Viewer for the amount of time specified for the conflict retention period, with a default of 14 days.</span></span> <span data-ttu-id="342ef-112">Para establecer el período de retención de conflictos, realice cualquiera de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="342ef-112">To set the conflict retention period, perform either of the following:</span></span>  
  
    -   <span data-ttu-id="342ef-113">Especifique un valor de retención para el parámetro @conflict_retention de [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="342ef-113">Specify a retention value for the @conflict_retention parameter of [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span>  
  
    -   <span data-ttu-id="342ef-114">Especifique un valor de `'conflict_retention'` para el @property parámetro y un valor de retención para el @value parámetro de [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="342ef-114">Specify a value of `'conflict_retention'` for the @property parameter and a retention value for the @value parameter of [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span>  
  
### <a name="to-view-conflicts"></a><span data-ttu-id="342ef-115">Para ver conflictos</span><span class="sxs-lookup"><span data-stu-id="342ef-115">To view conflicts</span></span>  
  
1.  <span data-ttu-id="342ef-116">Conéctese al servidor adecuado en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y, a continuación, expanda el nodo de servidor:</span><span class="sxs-lookup"><span data-stu-id="342ef-116">Connect to the appropriate server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="342ef-117">En el caso de la replicación punto a punto, éste es el nodo en el que se produjo el conflicto.</span><span class="sxs-lookup"><span data-stu-id="342ef-117">For peer-to-peer replication, this is the node at which the conflict occurred.</span></span>  
  
    -   <span data-ttu-id="342ef-118">Para las suscripciones de actualización, es el publicador.</span><span class="sxs-lookup"><span data-stu-id="342ef-118">For queued updating subscriptions, this is the Publisher.</span></span>  
  
2.  <span data-ttu-id="342ef-119">Expanda la carpeta **Replicación** y, a continuación, expanda la carpeta **Publicaciones locales** .</span><span class="sxs-lookup"><span data-stu-id="342ef-119">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="342ef-120">Haga clic con el botón secundario en la publicación para la que desea ver los conflictos y, a continuación, haga clic en **Ver conflictos**.</span><span class="sxs-lookup"><span data-stu-id="342ef-120">Right-click the publication for which you want to view conflicts, and then click **View Conflicts**.</span></span>  
  
4.  <span data-ttu-id="342ef-121">En el cuadro de diálogo **Seleccionar tabla de conflictos** , seleccione una base de datos, una publicación y una tabla para ver los conflictos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="342ef-121">In the **Select Conflict Table** dialog box, select a database, publication, and table for which to view conflicts.</span></span>  
  
5.  <span data-ttu-id="342ef-122">En el Visor de conflictos de replicación, puede:</span><span class="sxs-lookup"><span data-stu-id="342ef-122">In the Replication Conflict Viewer, you can:</span></span>  
  
    -   <span data-ttu-id="342ef-123">Filtrar filas con los botones que aparecen a la derecha de la cuadrícula superior.</span><span class="sxs-lookup"><span data-stu-id="342ef-123">Filter rows with the buttons to the right of the upper grid.</span></span>  
  
    -   <span data-ttu-id="342ef-124">Seleccionar una fila en la cuadrícula superior para ver la información de esa fila en la cuadrícula inferior.</span><span class="sxs-lookup"><span data-stu-id="342ef-124">Select a row in the upper grid to display information on that row in the lower grid.</span></span>  
  
    -   <span data-ttu-id="342ef-125">Seleccionar una o más filas en la cuadrícula superior y hacer clic en **Quitar**para quitar las filas de la tabla de metadatos de conflictos.</span><span class="sxs-lookup"><span data-stu-id="342ef-125">Select one or more rows in the upper grid, and then click **Remove**, which removes the row from the conflicts metadata table.</span></span>  
  
    -   <span data-ttu-id="342ef-126">Hacer clic en el botón de propiedades (**...**) para ver más información sobre la columna involucrada en el conflicto.</span><span class="sxs-lookup"><span data-stu-id="342ef-126">Click the properties button (**...**) to view more information on a column involved in a conflict.</span></span>  
  
    -   <span data-ttu-id="342ef-127">Seleccionar **Registrar los detalles de este conflicto** para registrar los datos del conflicto en un archivo.</span><span class="sxs-lookup"><span data-stu-id="342ef-127">Select **Log the details of this conflict** to log conflict data to a file.</span></span> <span data-ttu-id="342ef-128">Para especificar la ubicación del archivo, elija el menú **Ver** y haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="342ef-128">To specify a location for the file, point to the **View** menu, and then click **Options**.</span></span> <span data-ttu-id="342ef-129">Escriba un valor o haga clic en el botón Examinar (**...**) y navegue al archivo apropiado.</span><span class="sxs-lookup"><span data-stu-id="342ef-129">Enter a value, or click the browse button (**...**), and then navigate to the appropriate file.</span></span> <span data-ttu-id="342ef-130">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="342ef-130">Click **OK** to close the **Options** dialog box.</span></span>  
  
6.  <span data-ttu-id="342ef-131">Cierre el Visor de conflictos de replicación.</span><span class="sxs-lookup"><span data-stu-id="342ef-131">Close the Replication Conflict Viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="342ef-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="342ef-132">See Also</span></span>  
 <span data-ttu-id="342ef-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="342ef-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="342ef-134">Queued Updating Conflict Detection and Resolution</span><span class="sxs-lookup"><span data-stu-id="342ef-134">Queued Updating Conflict Detection and Resolution</span></span>](transactional/updatable-subscriptions-queued-updating-conflict-resolution.md)  
  
  
