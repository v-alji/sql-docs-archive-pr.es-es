---
title: Agregar o eliminar un grupo en un gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0445b0ac-acae-4462-80fb-fe9735ac66db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ac558ccbd8855018877228b2b38debf769f1573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749111"
---
# <a name="add-or-delete-a-group-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="d1105-102">Agregar o eliminar un grupo en un gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="d1105-102">Add or Delete a Group in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d1105-103">Haga clic en la región de datos del gráfico para mostrar el panel **Datos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="d1105-103">Click in the chart data region to display the **Chart Data** pane.</span></span> <span data-ttu-id="d1105-104">Cree grupos arrastrando los campos del conjunto de datos a las áreas **Grupos de categorías** y **Grupos de series** .</span><span class="sxs-lookup"><span data-stu-id="d1105-104">Create groups by dragging dataset fields to the **Category Groups** and **Series Groups** areas.</span></span> <span data-ttu-id="d1105-105">Para agregar grupos anidados, agregue varios campos al área.</span><span class="sxs-lookup"><span data-stu-id="d1105-105">To add nested groups, add multiple fields to the area.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-group-to-a-chart"></a><span data-ttu-id="d1105-106">Para agregar un grupo primario o secundario a un gráfico</span><span class="sxs-lookup"><span data-stu-id="d1105-106">To add a parent or child group to a chart</span></span>  
  
1.  <span data-ttu-id="d1105-107">En la superficie de diseño del informe, haga clic en cualquier lugar del gráfico para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="d1105-107">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="d1105-108">Aparece el panel **Datos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="d1105-108">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="d1105-109">Arrastre un campo de la ventana **Datos del informe** al área **Grupos de categorías** o **Grupos de series** .</span><span class="sxs-lookup"><span data-stu-id="d1105-109">Drag a field from the **Report Data** window to the **Category Groups** or **Series Groups** area.</span></span> <span data-ttu-id="d1105-110">Para agregar un grupo primario, coloque el cursor delante de un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="d1105-110">To add a parent group, position the cursor in front of an existing group.</span></span> <span data-ttu-id="d1105-111">Para agregar un grupo secundario, coloque el cursor detrás de un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="d1105-111">To add a child group, position the cursor after an existing group.</span></span>  
  
### <a name="to-edit-a-category-group-on-a-chart"></a><span data-ttu-id="d1105-112">Para editar un grupo de categorías de un gráfico</span><span class="sxs-lookup"><span data-stu-id="d1105-112">To edit a category group on a chart</span></span>  
  
1.  <span data-ttu-id="d1105-113">En la superficie de diseño del informe, haga clic en cualquier lugar del gráfico para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="d1105-113">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="d1105-114">Aparece el panel **Datos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="d1105-114">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="d1105-115">Haga clic con el botón derecho en el área **Grupos de categorías** y, después, en **Propiedades del grupo de categorías**.</span><span class="sxs-lookup"><span data-stu-id="d1105-115">Right-click the group in the **Category Groups** area, and then click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="d1105-116">Agregue o quite expresiones de grupo, filtros, expresiones de ordenación y variables de grupo.</span><span class="sxs-lookup"><span data-stu-id="d1105-116">Add or remove group expressions, filters, sort expressions, and group variables.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-series-group-on-a-chart"></a><span data-ttu-id="d1105-117">Para editar un grupo series de un gráfico</span><span class="sxs-lookup"><span data-stu-id="d1105-117">To edit a series group on a chart</span></span>  
  
1.  <span data-ttu-id="d1105-118">En la superficie de diseño del informe, haga clic en cualquier lugar del gráfico para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="d1105-118">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="d1105-119">Aparece el panel **Datos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="d1105-119">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="d1105-120">Haga clic con el botón derecho en el grupo en el área **Grupos de la serie** y, después, haga clic en **Propiedades del grupo de series**.</span><span class="sxs-lookup"><span data-stu-id="d1105-120">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
3.  <span data-ttu-id="d1105-121">Agregue o quite expresiones de grupo, filtros, expresiones de ordenación y variables de grupo.</span><span class="sxs-lookup"><span data-stu-id="d1105-121">Add or remove group expressions, filters, sort expressions, and group variables.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-chart"></a><span data-ttu-id="d1105-122">Para eliminar un grupo de un gráfico</span><span class="sxs-lookup"><span data-stu-id="d1105-122">To delete a group from a chart</span></span>  
  
1.  <span data-ttu-id="d1105-123">En la superficie de diseño del informe, haga clic en cualquier lugar del gráfico para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="d1105-123">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="d1105-124">Aparece el panel **Datos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="d1105-124">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="d1105-125">Haga clic con el botón derecho en el grupo en las áreas **Grupos de categorías** o **Grupos de series** y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d1105-125">Right-click the group in the **Category Groups** or **Series Groups** area, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1105-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1105-126">See Also</span></span>  
 [<span data-ttu-id="d1105-127">Gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1105-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
