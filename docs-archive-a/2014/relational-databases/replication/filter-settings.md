---
title: Configuración del filtro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.filtersettings.f1
ms.assetid: 1b401d7d-db8a-4ba1-acb1-b8dec14e3311
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d82d5f38eb460f392f1eb2ed3387ce3d97757db5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663364"
---
# <a name="filter-settings"></a><span data-ttu-id="ffcd3-102">Configuración del filtro</span><span class="sxs-lookup"><span data-stu-id="ffcd3-102">Filter Settings</span></span>
  <span data-ttu-id="ffcd3-103">El cuadro de diálogo **Configuración del filtro** permite definir los filtros para las cuadrículas del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="ffcd3-103">The **Filter Settings** dialog box lets you define filters for grids in Replication Monitor.</span></span> <span data-ttu-id="ffcd3-104">Por ejemplo, para mostrar únicamente las suscripciones activas en la pestaña **Todas las suscripciones** , seleccione **Estado** en la columna **Nombre de columna** , **Es igual a** en la columna **Operador** y **Activo** en la columna **Valor1** .</span><span class="sxs-lookup"><span data-stu-id="ffcd3-104">For example, to show only those subscriptions that are active on the **All Subscriptions** tab, select **Status** from the **Column Name** column, **Equals** from the **Operator** column, and **Active** from the **Value1** column.</span></span> <span data-ttu-id="ffcd3-105">Después de definir un filtro basado en una o más columnas, se aplica el filtro para que la cuadrícula muestre solo el subconjunto de filas que coinciden con los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="ffcd3-105">After you define a filter that is based one or more columns, the filter is applied so that the grid displays only the subset of rows that match the filter criteria.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ffcd3-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="ffcd3-106">Options</span></span>  
 <span data-ttu-id="ffcd3-107">**Nombre de la columna**</span><span class="sxs-lookup"><span data-stu-id="ffcd3-107">**Column Name**</span></span>  
 <span data-ttu-id="ffcd3-108">Seleccione el nombre de la columna en la que desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="ffcd3-108">Select the name of the column on which you want to filter.</span></span> <span data-ttu-id="ffcd3-109">Puede basar un filtro en una o más columnas.</span><span class="sxs-lookup"><span data-stu-id="ffcd3-109">You can base a filter on one or more columns.</span></span>  
  
 <span data-ttu-id="ffcd3-110">**Operador**</span><span class="sxs-lookup"><span data-stu-id="ffcd3-110">**Operator**</span></span>  
 <span data-ttu-id="ffcd3-111">Seleccione un operador para el filtro, como por ejemplo **Menor o igual que**.</span><span class="sxs-lookup"><span data-stu-id="ffcd3-111">Select an operator for the filter, such as **Less than or Equal to**.</span></span>  
  
 <span data-ttu-id="ffcd3-112">**Valor1** y **Valor2**</span><span class="sxs-lookup"><span data-stu-id="ffcd3-112">**Value1** and **Value2**</span></span>  
 <span data-ttu-id="ffcd3-113">Escriba o seleccione un valor para el filtro.</span><span class="sxs-lookup"><span data-stu-id="ffcd3-113">Enter or select a value for the filter.</span></span> <span data-ttu-id="ffcd3-114">La mayoría de los operadores solo requieren un valor en la columna **Valor1** ; sin embargo, los operadores **Entre** y **No entre** también requieren un valor en la do columna **Valor2** .</span><span class="sxs-lookup"><span data-stu-id="ffcd3-114">Most operators only require a value in the **Value1** column, but the **Between** and **Not Between** operators also require a value in the **Value2** column.</span></span>  
  
 <span data-ttu-id="ffcd3-115">**Borrar filtro**</span><span class="sxs-lookup"><span data-stu-id="ffcd3-115">**Clear Filter**</span></span>  
 <span data-ttu-id="ffcd3-116">Haga clic en este botón para borrar todos los filtros definidos.</span><span class="sxs-lookup"><span data-stu-id="ffcd3-116">Click this button to clear all filters that have been defined.</span></span> <span data-ttu-id="ffcd3-117">Para quitar un único filtro, seleccione el filtro y presione la tecla Supr.</span><span class="sxs-lookup"><span data-stu-id="ffcd3-117">To remove a single filter, select the filter row and press the Delete key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffcd3-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ffcd3-118">See Also</span></span>  
 [<span data-ttu-id="ffcd3-119">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="ffcd3-119">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
