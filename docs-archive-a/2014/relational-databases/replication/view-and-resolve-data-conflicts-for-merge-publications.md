---
title: Ver y resolver conflictos de datos para publicaciones de combinación (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], viewing conflicts
- viewing conflict information
- conflict resolution [SQL Server replication], merge replication
ms.assetid: aeee9546-4480-49f9-8b1e-c71da1f056c7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 77aa9ece0073149c017f6eca35a756b22751a74b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671468"
---
# <a name="view-and-resolve-data-conflicts-for-merge-publications-sql-server-management-studio"></a><span data-ttu-id="9cf40-102">Ver y resolver conflictos de datos para publicaciones de mezcla (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9cf40-102">View and Resolve Data Conflicts for Merge Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="9cf40-103">Los conflictos en la replicación de mezcla se solucionan con el solucionador especificado para cada artículo.</span><span class="sxs-lookup"><span data-stu-id="9cf40-103">Conflicts in merge replication are resolved based on the resolver specified for each article.</span></span> <span data-ttu-id="9cf40-104">De manera predeterminada, los conflictos se resuelven sin necesidad de intervención del usuario.</span><span class="sxs-lookup"><span data-stu-id="9cf40-104">By default, conflicts are resolved without the need for user intervention.</span></span> <span data-ttu-id="9cf40-105">No obstante, es posible ver los conflictos y modificar el resultado de la resolución en el Visor de conflictos de replicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9cf40-105">But conflicts can be viewed, and the outcome of the resolution can be changed, in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replication Conflict Viewer.</span></span>  
  
 <span data-ttu-id="9cf40-106">Los datos de conflictos están disponibles en el Visor de conflictos de replicación durante el tiempo especificado como período de retención de conflictos (con un valor predeterminado de 14 días).</span><span class="sxs-lookup"><span data-stu-id="9cf40-106">Conflict data is available in the Replication Conflict Viewer for the amount of time specified for the conflict retention period (with a default of 14 days).</span></span> <span data-ttu-id="9cf40-107">Para configurar el período de retención de conflictos:</span><span class="sxs-lookup"><span data-stu-id="9cf40-107">To set the conflict retention period, either:</span></span>  
  
-   <span data-ttu-id="9cf40-108">Especifique un valor de retención para el **@conflict_retention** parámetro de [sp_addmergepublication &#40;&#41;de TRANSACT-SQL ](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9cf40-108">Specify a retention value for the **@conflict_retention** parameter of [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span></span>  
  
-   <span data-ttu-id="9cf40-109">Especifique un valor de **conflict_retention** para el **@property** parámetro y un valor de retención para el **@value** parámetro de [sp_changemergepublication &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9cf40-109">Specify a value of **conflict_retention** for the **@property** parameter and a retention value for the **@value** parameter of [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span>  
  
 <span data-ttu-id="9cf40-110">De manera predeterminada, la información del conflicto se almacena:</span><span class="sxs-lookup"><span data-stu-id="9cf40-110">By default, conflict information is stored:</span></span>  
  
-   <span data-ttu-id="9cf40-111">En el publicador y en el suscriptor, si el nivel de compatibilidad de la publicación es igual o superior a 90RTM.</span><span class="sxs-lookup"><span data-stu-id="9cf40-111">At the Publisher and Subscriber if the publication compatibility level is 90RTM or higher.</span></span>  
  
-   <span data-ttu-id="9cf40-112">En el publicador, si el nivel de compatibilidad de la publicación es inferior a 80RTM.</span><span class="sxs-lookup"><span data-stu-id="9cf40-112">At the Publisher if the publication compatibility level is lower than 80RTM.</span></span>  
  
-   <span data-ttu-id="9cf40-113">En el publicador, si los suscriptores utilizan [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cf40-113">At the Publisher if Subscribers are running [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="9cf40-114">No se pueden almacenar datos en conflicto en los suscriptores de [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9cf40-114">Conflict data cannot be stored on [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscribers.</span></span>  
  
 <span data-ttu-id="9cf40-115">La propiedad **conflict_logging** de la publicación controla el almacenamiento de la información del conflicto.</span><span class="sxs-lookup"><span data-stu-id="9cf40-115">Storage of conflict information is controlled by the **conflict_logging** publication property.</span></span> <span data-ttu-id="9cf40-116">Para más información, vea [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql) y [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9cf40-116">For more information, see [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql) and [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span>  
  
 <span data-ttu-id="9cf40-117">Los conflictos también se pueden solucionar de forma interactiva durante la sincronización, con el Solucionador interactivo de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9cf40-117">Conflicts can also be resolved interactively during synchronization using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Interactive Resolver.</span></span> <span data-ttu-id="9cf40-118">El Solucionador interactivo está disponible a través del Administrador de sincronización de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="9cf40-118">The Interactive Resolver is available through the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Synchronization Manager.</span></span> <span data-ttu-id="9cf40-119">Para más información, vea [Sincronizar una suscripción mediante el Administrador de sincronización de Windows &#40;Administrador de sincronización de Windows&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9cf40-119">For more information, see [Synchronize a Subscription Using Windows Synchronization Manager &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md).</span></span>  
  
### <a name="to-view-and-resolve-conflicts-for-merge-publications"></a><span data-ttu-id="9cf40-120">Para ver y solucionar conflictos de publicaciones de combinación</span><span class="sxs-lookup"><span data-stu-id="9cf40-120">To view and resolve conflicts for merge publications</span></span>  
  
1.  <span data-ttu-id="9cf40-121">Conéctese al publicador (o al suscriptor, si procede) en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y, a continuación, expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="9cf40-121">Connect to the Publisher (or Subscriber if appropriate) in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="9cf40-122">Expanda la carpeta **Replicación** y, a continuación, expanda la carpeta **Publicaciones locales** .</span><span class="sxs-lookup"><span data-stu-id="9cf40-122">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="9cf40-123">Haga clic con el botón secundario en la publicación para la que desea ver los conflictos y, a continuación, haga clic en **Ver conflictos**.</span><span class="sxs-lookup"><span data-stu-id="9cf40-123">Right-click the publication for which you want to view conflicts, and then click **View Conflicts**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9cf40-124">Si especificó el valor **'subscriber'** para la propiedad **conflict_logging** , la opción de menú **Ver conflictos** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="9cf40-124">If you specified a value of **'subscriber'** for the **conflict_logging** property, the **View Conflicts** menu option is not available.</span></span> <span data-ttu-id="9cf40-125">Para ver los conflictos, inicie ConflictViewer.exe desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9cf40-125">To view conflicts, start ConflictViewer.exe from the command prompt.</span></span> <span data-ttu-id="9cf40-126">De forma predeterminada, ConflictViewer.exe se encuentra en el siguiente directorio: Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="9cf40-126">By default, ConflictViewer.exe is located in the following directory: Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE.</span></span> <span data-ttu-id="9cf40-127">Para obtener una lista de parámetros de inicio válidos, ejecute ConflictViewer.exe -?.</span><span class="sxs-lookup"><span data-stu-id="9cf40-127">For a list of valid startup parameters, run ConflictViewer.exe -?.</span></span>  
  
4.  <span data-ttu-id="9cf40-128">En el cuadro de diálogo **Seleccionar tabla de conflictos** , seleccione una base de datos, una publicación y una tabla para ver los conflictos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9cf40-128">In the **Select Conflict Table** dialog box, select a database, publication, and table for which to view conflicts.</span></span>  
  
5.  <span data-ttu-id="9cf40-129">En el Visor de conflictos de replicación, puede:</span><span class="sxs-lookup"><span data-stu-id="9cf40-129">In the Replication Conflict Viewer, you can:</span></span>  
  
    -   <span data-ttu-id="9cf40-130">Filtrar filas con los botones que aparecen a la derecha de la cuadrícula superior.</span><span class="sxs-lookup"><span data-stu-id="9cf40-130">Filter rows with the buttons to the right of the upper grid.</span></span>  
  
    -   <span data-ttu-id="9cf40-131">Seleccionar una fila en la cuadrícula superior para ver la información de esa fila en la cuadrícula inferior.</span><span class="sxs-lookup"><span data-stu-id="9cf40-131">Select a row in the upper grid to display information on that row in the lower grid.</span></span>  
  
    -   <span data-ttu-id="9cf40-132">Seleccionar una o más filas en la cuadrícula superior y hacer clic en **Quitar**, lo que equivale a hacer clic en el botón **Enviar ganador** (sin realizar cambios en los datos).</span><span class="sxs-lookup"><span data-stu-id="9cf40-132">Select one or more rows in the upper grid, and then click **Remove**, which is equivalent to clicking the **Submit Winner** button (without making any changes to the data).</span></span>  
  
    -   <span data-ttu-id="9cf40-133">Hacer clic en el botón de propiedades (**...**) para ver más información sobre la columna involucrada en el conflicto.</span><span class="sxs-lookup"><span data-stu-id="9cf40-133">Click the properties button (**...**) to view more information on a column involved in a conflict.</span></span>  
  
    -   <span data-ttu-id="9cf40-134">Editar datos en la columna **Ganador del conflicto** o **Perdedor del conflicto** antes de enviar los datos (los datos son de solo lectura si la columna está en color gris).</span><span class="sxs-lookup"><span data-stu-id="9cf40-134">Edit data in the **Conflict winner** or **Conflict loser** column before submitting the data (data is read-only if the column is gray).</span></span>  
  
    -   <span data-ttu-id="9cf40-135">Hacer clic en **Enviar ganador** para aceptar la fila designada como ganador del conflicto.</span><span class="sxs-lookup"><span data-stu-id="9cf40-135">Click **Submit Winner** to accept the row designated as the winner of the conflict.</span></span>  
  
    -   <span data-ttu-id="9cf40-136">Hacer clic en **Enviar perdedor** para anular la resolución y propagar el valor designado como perdedor del conflicto a todos los nodos de la topología.</span><span class="sxs-lookup"><span data-stu-id="9cf40-136">Click **Submit Loser** to override the resolution and to propagate the value designated as the loser of the conflict to all nodes in the topology.</span></span>  
  
    -   <span data-ttu-id="9cf40-137">Seleccionar **Registrar los detalles de este conflicto** para registrar los datos del conflicto en un archivo.</span><span class="sxs-lookup"><span data-stu-id="9cf40-137">Select **Log the details of this conflict** to log conflict data to a file.</span></span> <span data-ttu-id="9cf40-138">Para especificar la ubicación del archivo, elija el menú **Ver** y haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="9cf40-138">To specify a location for the file, point to the **View** menu, and then click **Options**.</span></span> <span data-ttu-id="9cf40-139">Escriba un valor o haga clic en el botón Examinar (**...**) y navegue al archivo apropiado.</span><span class="sxs-lookup"><span data-stu-id="9cf40-139">Enter a value, or click the browse button (**...**), and then navigate to the appropriate file.</span></span> <span data-ttu-id="9cf40-140">Haga clic en **Aceptar** para salir del cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="9cf40-140">Click **OK** to exit the **Options** dialog box.</span></span>  
  
6.  <span data-ttu-id="9cf40-141">Cierre el Visor de conflictos de replicación.</span><span class="sxs-lookup"><span data-stu-id="9cf40-141">Close the Replication Conflict Viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf40-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cf40-142">See Also</span></span>  
 <span data-ttu-id="9cf40-143">[Detección y resolución de conflictos de replicación de mezcla avanzada](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="9cf40-143">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 [<span data-ttu-id="9cf40-144">Especificar un solucionador de artículos de mezcla</span><span class="sxs-lookup"><span data-stu-id="9cf40-144">Specify a Merge Article Resolver</span></span>](publish/specify-a-merge-article-resolver.md)  
  
  
