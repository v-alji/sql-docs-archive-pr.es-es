---
title: Agregar minigráficos y barras de datos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0b297c2e-d48b-41b0-aabd-29680cdcdb05
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55ec15354cdc78dd9678b9466f30d2fca0a73adc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663919"
---
# <a name="add-sparklines-and-data-bars-report-builder-and-ssrs"></a><span data-ttu-id="6b77a-102">Agregar minigráficos y barras de datos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="6b77a-102">Add Sparklines and Data Bars (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6b77a-103">Los minigráficos y barras de datos son gráficos pequeños y accesorios que comunican mucha información con pocos detalles.</span><span class="sxs-lookup"><span data-stu-id="6b77a-103">Sparklines and data bars are small, spare charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="6b77a-104">Para más información, vea [Minigráficos y barras de datos &#40;Generador de informes y SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6b77a-104">For more information about them, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="6b77a-105">Los minigráficos y las barras de datos se suelen colocar en celdas en una tabla o matriz.</span><span class="sxs-lookup"><span data-stu-id="6b77a-105">Sparklines and data bars are most commonly placed in cells in a table or matrix.</span></span> <span data-ttu-id="6b77a-106">Normalmente, los minigráficos solo muestran una serie cada uno.</span><span class="sxs-lookup"><span data-stu-id="6b77a-106">Sparklines usually display only one series each.</span></span> <span data-ttu-id="6b77a-107">Las barras de datos puede contener uno o varios puntos de datos.</span><span class="sxs-lookup"><span data-stu-id="6b77a-107">Data bars can contain one or more data points.</span></span> <span data-ttu-id="6b77a-108">El efecto de los minigráficos y las barras de datos deriva de la repetición de la información de la serie para cada fila de la tabla o matriz.</span><span class="sxs-lookup"><span data-stu-id="6b77a-108">Both sparklines and data bars derive their impact from repeating the series information for each row in the table or matrix.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-sparkline-or-data-bar-to-a-table-or-matrix"></a><span data-ttu-id="6b77a-109">Para agregar un minigráfico o una barra de datos a una tabla o matriz</span><span class="sxs-lookup"><span data-stu-id="6b77a-109">To add a sparkline or data bar to a table or matrix</span></span>  
  
1.  <span data-ttu-id="6b77a-110">Si aún no lo ha hecho, cree una tabla o matriz con los datos que desee mostrar.</span><span class="sxs-lookup"><span data-stu-id="6b77a-110">If you have not done so already, create a table or matrix with the data you want to display.</span></span> <span data-ttu-id="6b77a-111">Para obtener más información, vea [Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) y [Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6b77a-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="6b77a-112">Inserte una columna en la tabla o matriz.</span><span class="sxs-lookup"><span data-stu-id="6b77a-112">Insert a column in your table or matrix.</span></span> <span data-ttu-id="6b77a-113">Para más información, vea [Insertar o eliminar una columna &#40;Generador de informes y SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6b77a-113">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="6b77a-114">En la pestaña **Insertar** , haga clic en **Minigráfico** o en **Barra de datos**y, a continuación, haga clic en una celda de la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="6b77a-114">On the **Insert** tab, click **Sparkline** or **Data Bar**, and then click in a cell in the new column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6b77a-115">No se pueden colocar minigráficos en un grupo de detalles de una tabla.</span><span class="sxs-lookup"><span data-stu-id="6b77a-115">You cannot place sparklines in a detail group in a table.</span></span> <span data-ttu-id="6b77a-116">Deben estar en una celda asociada a un grupo.</span><span class="sxs-lookup"><span data-stu-id="6b77a-116">They must go in a cell associated with a group.</span></span>  
  
4.  <span data-ttu-id="6b77a-117">En el cuadro de diálogo **Cambiar tipo de minigráfico o barra de datos** , haga clic en el tipo de minigráfico o barra de datos que prefiera y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6b77a-117">In the **Change Sparkline/Data Bar Type** dialog box, click the kind of sparkline or data bar you want, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="6b77a-118">Haga clic en el minigráfico o barra de datos.</span><span class="sxs-lookup"><span data-stu-id="6b77a-118">Click the sparkline or data bar.</span></span>  
  
     <span data-ttu-id="6b77a-119">El panel **Datos del gráfico** se abre.</span><span class="sxs-lookup"><span data-stu-id="6b77a-119">The **Chart Data** pane opens.</span></span>  
  
6.  <span data-ttu-id="6b77a-120">En el área **Valores** , haga clic en el signo más ( **) de** Agregar campos**+** y, después, haga clic en el campo cuyos valores quiera incluir en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="6b77a-120">In the **Values** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want charted.</span></span>  
  
7.  <span data-ttu-id="6b77a-121">En el área **Grupos de categorías** , haga clic en el signo más ( **) de** Agregar campos**+** y, después, haga clic en el campo por cuyos valores quiera agrupar.</span><span class="sxs-lookup"><span data-stu-id="6b77a-121">In the **Category Groups** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want to group by.</span></span>  
  
     <span data-ttu-id="6b77a-122">Normalmente, para los minigráficos y barras de datos, no se agregará un campo al área **Grupo de series** porque solo se desea una serie para cada fila.</span><span class="sxs-lookup"><span data-stu-id="6b77a-122">Typically for sparklines and data bars, you will not add a field to the **Series Group** area because you only want one series for each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b77a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b77a-123">See Also</span></span>  
 <span data-ttu-id="6b77a-124">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6b77a-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6b77a-125">Alinear los datos en un gráfico en una tabla o una matriz &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6b77a-125">Align the Data in a Chart in a Table or Matrix &#40;Report Builder and SSRS&#41;</span></span>](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)  
  
  
