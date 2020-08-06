---
title: Solucionador interactivo de conflictos de replicación de Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.interactiveresolver.f1
ms.assetid: d3d4a480-782b-4b1d-b839-565c8cf6cb24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8cbd2231ab1ab357321f9887bced986e182e608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750742"
---
# <a name="microsoft-replication-interactive-conflict-resolver"></a><span data-ttu-id="6f432-102">Solucionador interactivo de conflictos de replicación de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6f432-102">Microsoft Replication Interactive Conflict Resolver</span></span>
  <span data-ttu-id="6f432-103">El Solucionador interactivo de conflictos se puede utilizar para las suscripciones de mezcla que se sincronizan con el Administrador de sincronización de Windows.</span><span class="sxs-lookup"><span data-stu-id="6f432-103">The Interactive Conflict Resolver can be used for merge subscriptions that are synchronized using Windows Synchronization Manager.</span></span> <span data-ttu-id="6f432-104">Permite ver, comparar, modificar y seleccionar el resultado de los conflictos de datos.</span><span class="sxs-lookup"><span data-stu-id="6f432-104">It allows you to view, compare, edit, and select the outcome for data conflicts.</span></span> <span data-ttu-id="6f432-105">La replicación incluye también el Visor de conflictos, que permite ver y modificar los resultados de los conflictos una vez que se han confirmado.</span><span class="sxs-lookup"><span data-stu-id="6f432-105">Replication also includes the Conflict Viewer, which allows you to view and modify conflict outcomes after they have been committed.</span></span> <span data-ttu-id="6f432-106">El Solucionador interactivo de conflictos permite seleccionar el resultado durante la sincronización.</span><span class="sxs-lookup"><span data-stu-id="6f432-106">The Interactive Conflict Resolver allows you to select the outcome during synchronization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f432-107">Los conflictos que implican registros lógicos no se muestran en el Solucionador interactivo.</span><span class="sxs-lookup"><span data-stu-id="6f432-107">Conflicts that involve logical records are not displayed in the Interactive Resolver.</span></span> <span data-ttu-id="6f432-108">Para ver información acerca de estos conflictos, utilice procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="6f432-108">To view information about these conflicts, use replication stored procedures.</span></span> <span data-ttu-id="6f432-109">Para obtener más información, vea [Ver información de conflictos para publicaciones de mezcla &#40;programación de la replicación con Transact-SQL&#41;](view-conflict-information-for-merge-publications.md).</span><span class="sxs-lookup"><span data-stu-id="6f432-109">For more information, see [View Conflict Information for Merge Publications &#40;Replication Transact-SQL Programming&#41;](view-conflict-information-for-merge-publications.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6f432-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="6f432-110">Options</span></span>  
 <span data-ttu-id="6f432-111">**Nombre de la columna**</span><span class="sxs-lookup"><span data-stu-id="6f432-111">**Column name**</span></span>  
 <span data-ttu-id="6f432-112">Nombre de todas las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6f432-112">The name of all columns in the table.</span></span> <span data-ttu-id="6f432-113">Una o varias columnas pueden tener datos en conflicto.</span><span class="sxs-lookup"><span data-stu-id="6f432-113">One or more columns might have conflicting data.</span></span> <span data-ttu-id="6f432-114">Independientemente de las columnas que tengan conflictos, toda la fila ganadora sobrescribirá toda la fila perdedora.</span><span class="sxs-lookup"><span data-stu-id="6f432-114">Regardless of which columns conflict, the entire winning row will overwrite the entire losing row.</span></span>  
  
 <span data-ttu-id="6f432-115">**Resolución sugerida**</span><span class="sxs-lookup"><span data-stu-id="6f432-115">**Suggested Resolution**</span></span>  
 <span data-ttu-id="6f432-116">La resolución sugerida proporcionada por el solucionador de conflictos del artículo.</span><span class="sxs-lookup"><span data-stu-id="6f432-116">The suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="6f432-117">**Publicador**</span><span class="sxs-lookup"><span data-stu-id="6f432-117">**Publisher**</span></span>  
 <span data-ttu-id="6f432-118">Valor de datos en el publicador.</span><span class="sxs-lookup"><span data-stu-id="6f432-118">The data value at the Publisher.</span></span>  
  
 <span data-ttu-id="6f432-119">**Suscriptor**</span><span class="sxs-lookup"><span data-stu-id="6f432-119">**Subscriber**</span></span>  
 <span data-ttu-id="6f432-120">Valor de datos en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="6f432-120">The data value at the Subscriber.</span></span>  
  
 <span data-ttu-id="6f432-121">**Aceptar sugerencia**, **Aceptar publicador**, y **Aceptar suscriptor**</span><span class="sxs-lookup"><span data-stu-id="6f432-121">**Accept Suggested**, **Accept Publisher**, and **Accept Subscriber**</span></span>  
 <span data-ttu-id="6f432-122">Haga clic para aceptar la fila que se aplicará al publicador o al suscriptor en función del que haya perdido el conflicto.</span><span class="sxs-lookup"><span data-stu-id="6f432-122">Click to accept the row that will be applied at either the Publisher or the Subscriber, depending on which one lost the conflict.</span></span> <span data-ttu-id="6f432-123">Si el publicador ha perdido el conflicto, todos los demás suscriptores recibirán la fila ganadora la próxima vez que se sincronicen con el publicador.</span><span class="sxs-lookup"><span data-stu-id="6f432-123">If the Publisher lost the conflict, all other Subscribers will receive the winning row the next time they synchronize with the Publisher.</span></span>  
  
 <span data-ttu-id="6f432-124">**Solucionar los conflictos restantes automáticamente**</span><span class="sxs-lookup"><span data-stu-id="6f432-124">**Resolve remaining conflicts automatically**</span></span>  
 <span data-ttu-id="6f432-125">Resuelva todos los conflictos restantes utilizando la sugerencia proporcionada por el solucionador de conflictos del artículo.</span><span class="sxs-lookup"><span data-stu-id="6f432-125">Resolve all remaining conflicts using the suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="6f432-126">**Registrar los detalles del conflicto para consultarlos más adelante**</span><span class="sxs-lookup"><span data-stu-id="6f432-126">**Log the details of the conflict for later reference**</span></span>  
 <span data-ttu-id="6f432-127">Registra los detalles del conflicto en tablas del sistema.</span><span class="sxs-lookup"><span data-stu-id="6f432-127">Logs the details of the conflict in system tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f432-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f432-128">See Also</span></span>  
 <span data-ttu-id="6f432-129">[Resolución interactiva de conflictos](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="6f432-129">[Interactive Conflict Resolution](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span></span>  
 <span data-ttu-id="6f432-130">[Ver y resolver conflictos de datos para publicaciones de mezcla &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span><span class="sxs-lookup"><span data-stu-id="6f432-130">[View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span></span>  
 <span data-ttu-id="6f432-131">[Sincronizar una suscripción mediante el Administrador de sincronización de Windows &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span><span class="sxs-lookup"><span data-stu-id="6f432-131">[Synchronize a Subscription Using Windows Synchronization Manager &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span></span>  
 [<span data-ttu-id="6f432-132">Replicación de mezcla avanzada: detección y resolución de conflictos</span><span class="sxs-lookup"><span data-stu-id="6f432-132">Advanced Merge Replication Conflict Detection and Resolution</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
