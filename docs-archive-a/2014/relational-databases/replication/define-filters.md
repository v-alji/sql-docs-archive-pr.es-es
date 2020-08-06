---
title: Definición de filtros | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.definefilters.f1
helpviewer_keywords:
- Define Filters dialog box
ms.assetid: 1fa71d22-ce5a-4aae-ba05-4d755842aeac
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5154f002c5a35bc78e2eb6777f2cc7bb3d56b635
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663403"
---
# <a name="define-filters"></a><span data-ttu-id="31fac-102">Definir filtros</span><span class="sxs-lookup"><span data-stu-id="31fac-102">Define Filters</span></span>
  <span data-ttu-id="31fac-103">El cuadro de diálogo **Definir filtros** permite definir filtros que posteriormente se aplican a conflictos de datos para obtener un subconjunto de conflictos en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="31fac-103">The **Define Filters** dialog box allows you to define filters that you then apply to data conflicts to see a subset of the conflicts in the grid.</span></span> <span data-ttu-id="31fac-104">Para definir un filtro, elija un operador del cuadro de lista desplegable **Operador** y, a continuación, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="31fac-104">To define a filter, choose an operator from the **Operator** drop-down list box and then enter a value.</span></span> <span data-ttu-id="31fac-105">Por ejemplo, si desea mostrar solamente los conflictos en los que el perdedor del conflicto es el servidor **ReplTest1**, seleccione **Igual a** en el cuadro de lista desplegable **Operador** y especifique **ReplTest1** en la primera columna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="31fac-105">For example, to show only those conflicts in which the conflict loser is server **ReplTest1**, select **Equal to** from the **Operator** drop-down list box and enter **ReplTest1** in the first **Value** column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="31fac-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="31fac-106">Options</span></span>  
 <span data-ttu-id="31fac-107">**Operador**</span><span class="sxs-lookup"><span data-stu-id="31fac-107">**Operator**</span></span>  
 <span data-ttu-id="31fac-108">Seleccione un operador para el filtro, como por ejemplo **Menor o igual que**.</span><span class="sxs-lookup"><span data-stu-id="31fac-108">Select an operator for the filter, such as **Less than or Equal to**.</span></span>  
  
 <span data-ttu-id="31fac-109">**Valor**</span><span class="sxs-lookup"><span data-stu-id="31fac-109">**Value**</span></span>  
 <span data-ttu-id="31fac-110">Escriba un valor para el filtro.</span><span class="sxs-lookup"><span data-stu-id="31fac-110">Enter a value for the filter.</span></span> <span data-ttu-id="31fac-111">La mayoría de los operadores solo requiere un valor en la primera columna **Valor** ; sin embargo, los operadores **Entre** y **No entre** requieren un valor en las dos columnas **Valor** .</span><span class="sxs-lookup"><span data-stu-id="31fac-111">Most operators only require a value in the first **Value** column, but the **Between** and **Not Between** operators require a value in both of the **Value** columns.</span></span>  
  
 <span data-ttu-id="31fac-112">**Borrar**</span><span class="sxs-lookup"><span data-stu-id="31fac-112">**Clear**</span></span>  
 <span data-ttu-id="31fac-113">Haga clic en este botón para borrar todos los filtros previamente definidos.</span><span class="sxs-lookup"><span data-stu-id="31fac-113">Click this button to clear all filters that have been previously defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31fac-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31fac-114">See Also</span></span>  
 <span data-ttu-id="31fac-115">[Visor de conflictos de replicación de Microsoft &#40;Replicación de mezcla&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="31fac-115">[Microsoft Replication Conflict Viewer &#40;Merge Replication&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span></span>  
 [<span data-ttu-id="31fac-116">Visor de conflictos de replicación de Microsoft &#40;Replicación transaccional&#41;</span><span class="sxs-lookup"><span data-stu-id="31fac-116">Microsoft Replication Conflict Viewer &#40;Transactional Replication&#41;</span></span>](microsoft-replication-conflict-viewer-transactional-replication.md)  
  
  
