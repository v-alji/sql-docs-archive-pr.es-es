---
title: Modificar nombres de tabla predeterminados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ddd97483-a76d-43c1-8b40-fc7cc57fb0c2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 254f797be95f60211983400b019415431d4cf39c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662316"
---
# <a name="modifying-default-table-names"></a><span data-ttu-id="8229d-102">Modificar los nombres de tabla predeterminados</span><span class="sxs-lookup"><span data-stu-id="8229d-102">Modifying Default Table Names</span></span>
  <span data-ttu-id="8229d-103">Puede cambiar el valor de la propiedad **FriendlyName** para los objetos de la vista del origen de datos para que sean más fáciles de identificar y usar.</span><span class="sxs-lookup"><span data-stu-id="8229d-103">You can change the value of the **FriendlyName** property for objects in the data source view to make them easier to notice and use.</span></span>  
  
 <span data-ttu-id="8229d-104">En la tarea siguiente, cambiará el nombre descriptivo de cada tabla de la vista del origen de datos quitando los prefijos "**Dim**" y "**Fact**" de dichas tablas.</span><span class="sxs-lookup"><span data-stu-id="8229d-104">In the following task, you will change the friendly name of each table in the data source view by removing the "**Dim**" and "**Fact**" prefixes from these tables.</span></span> <span data-ttu-id="8229d-105">Esto hará que los objetos del cubo y la dimensión (que definirá en la siguiente lección) sean más fáciles de identificar y usar.</span><span class="sxs-lookup"><span data-stu-id="8229d-105">This will make the cube and dimension objects (that you will define in the next lesson) easier to notice and use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8229d-106">También puede cambiar los nombres descriptivos de las columnas, definir columnas calculadas y combinar tablas o vistas en la vista del origen de datos para que sean más fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="8229d-106">You can also change the friendly names of columns, define calculated columns, and join tables or views in the data source view to make them easier to use.</span></span>  
  
### <a name="to-modify-the-default-name-of-a-table"></a><span data-ttu-id="8229d-107">Para modificar el nombre predeterminado de una tabla</span><span class="sxs-lookup"><span data-stu-id="8229d-107">To modify the default name of a table</span></span>  
  
1.  <span data-ttu-id="8229d-108">En el panel **Tablas** del **Diseñador de vistas del origen de datos**, haga clic con el botón derecho en la tabla **FactInternetSales** y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8229d-108">In the **Tables** pane of **Data Source View Designer**, right-click the **FactInternetSales** table, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="8229d-109">Si la ventana Propiedades situada en la parte derecha de la ventana de Microsoft Visual Studio no se muestra, haga clic en el botón **Ocultar automáticamente** de la barra de título de la ventana Propiedades para que esta ventana permanezca visible.</span><span class="sxs-lookup"><span data-stu-id="8229d-109">If the Properties window on the right side of the Microsoft Visual Studio window is not displayed, click the **Auto Hide** button on the title bar of the Properties window so that this window remains visible.</span></span>  
  
     <span data-ttu-id="8229d-110">Es más fácil cambiar las propiedades de cada tabla en la vista del origen de datos cuando la ventana Propiedades permanece abierta.</span><span class="sxs-lookup"><span data-stu-id="8229d-110">It is easier to change the properties for each table in the data source view when the Properties window remains open.</span></span> <span data-ttu-id="8229d-111">Si no fija la ventana abierta mediante el botón **Ocultar automáticamente** , la ventana se cerrará al hacer clic en un objeto distinto del panel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="8229d-111">If you do not pin the window open by using the **Auto Hide** button, the window will close when you click a different object in the **Diagram** pane.</span></span>  
  
3.  <span data-ttu-id="8229d-112">Cambie la propiedad **FriendlyName** del objeto **FactInternetSales** a *`InternetSales`* .</span><span class="sxs-lookup"><span data-stu-id="8229d-112">Change the **FriendlyName** property for the **FactInternetSales** object to *`InternetSales`*.</span></span>  
  
     <span data-ttu-id="8229d-113">Al hacer clic fuera de la celda de la propiedad **FriendlyName** , se aplica el cambio.</span><span class="sxs-lookup"><span data-stu-id="8229d-113">When you click away from the cell for the **FriendlyName** property, the change is applied.</span></span> <span data-ttu-id="8229d-114">En la siguiente lección, definirá un grupo de medida que se basa en esta tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="8229d-114">In the next lesson, you will define a measure group that is based on this fact table.</span></span> <span data-ttu-id="8229d-115">El nombre de la tabla de hechos será InternetSales en lugar de FactInternetSales debido al cambio realizado en esta lección.</span><span class="sxs-lookup"><span data-stu-id="8229d-115">The name of the fact table will be InternetSales instead of FactInternetSales because of the change you made in this lesson.</span></span>  
  
4.  <span data-ttu-id="8229d-116">Haga clic en **DimProduct** en el panel **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="8229d-116">Click **DimProduct** in the **Tables** pane.</span></span> <span data-ttu-id="8229d-117">En el ventana Propiedades, cambie la propiedad **FriendlyName** a *`Product`* .</span><span class="sxs-lookup"><span data-stu-id="8229d-117">In the Properties window, change the **FriendlyName** property to *`Product`*.</span></span>  
  
5.  <span data-ttu-id="8229d-118">Cambie la propiedad **FriendlyName** de cada una de las tablas restantes en la vista del origen de datos del mismo modo, para eliminar el prefijo "**Dim**".</span><span class="sxs-lookup"><span data-stu-id="8229d-118">Change the **FriendlyName** property of each remaining table in the data source view in the same way, to remove the "**Dim**" prefix.</span></span>  
  
6.  <span data-ttu-id="8229d-119">Cuando haya finalizado, haga clic en el botón **Ocultar automáticamente** para ocultar de nuevo la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="8229d-119">When you have finished, click the **Auto Hide** button to hide the Properties window again.</span></span>  
  
7.  <span data-ttu-id="8229d-120">En el menú **Archivo** , o en la barra de herramientas de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en **Guardar todo** para guardar los cambios que ha realizado hasta este momento en el proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8229d-120">On the **File** menu, or on the toolbar of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Save All** to save the changes you have made to this point in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="8229d-121">Si lo desea, puede detener aquí el tutorial y reanudarlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="8229d-121">You can stop the tutorial here if you want and resume it later.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="8229d-122">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="8229d-122">Next Lesson</span></span>  
 [<span data-ttu-id="8229d-123">Lección 2: definir e implementar un cubo</span><span class="sxs-lookup"><span data-stu-id="8229d-123">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="8229d-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8229d-124">See Also</span></span>  
 <span data-ttu-id="8229d-125">[Vistas del origen de datos en modelos multidimensionales](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="8229d-125">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="8229d-126">Cambiar las propiedades de una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8229d-126">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/change-properties-in-a-data-source-view-analysis-services.md)  
  
  
