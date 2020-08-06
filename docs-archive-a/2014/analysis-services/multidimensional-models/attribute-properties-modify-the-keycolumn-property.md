---
title: Modifique la propiedad KeyColumn de un atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- binding attributes [Analysis Services]
- attributes [Analysis Services], binding
- key columns [Analysis Services]
ms.assetid: a2643be4-8123-4cc3-baf9-e5ec54a1669d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3367a7aec84ba59efd118a56745bb76fc5266061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750330"
---
# <a name="modify-the-keycolumn-property-of-an-attribute"></a><span data-ttu-id="bd017-102">Modificar la propiedad KeyColumns de un atributo</span><span class="sxs-lookup"><span data-stu-id="bd017-102">Modify the KeyColumn Property of an Attribute</span></span>
  <span data-ttu-id="bd017-103">Puede modificar la propiedad **KeyColumns** de un atributo.</span><span class="sxs-lookup"><span data-stu-id="bd017-103">You can modify the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="bd017-104">Por ejemplo, es posible que desee especificar una clave compuesta en lugar de una sola clave como clave del atributo.</span><span class="sxs-lookup"><span data-stu-id="bd017-104">For example, you might want to specify a composite key instead of a single key as the key for the attribute.</span></span>  
  
### <a name="to-modify-the-keycolumns-property-of-an-attribute"></a><span data-ttu-id="bd017-105">Para modificar la propiedad KeyColumns de un atributo</span><span class="sxs-lookup"><span data-stu-id="bd017-105">To modify the KeyColumns property of an attribute</span></span>  
  
1.  <span data-ttu-id="bd017-106">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto cuya propiedad **KeyColumns** quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="bd017-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project in which you want to modify the **KeyColumns** property.</span></span>  
  
2.  <span data-ttu-id="bd017-107">Abra el Diseñador de dimensiones siguiendo uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="bd017-107">Open Dimension Designer by doing one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="bd017-108">En el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta **Dimensiones** y, después, haga clic en **Abrir** o en **Diseñador de vistas**.</span><span class="sxs-lookup"><span data-stu-id="bd017-108">In **Solution Explorer**, right-click the dimension in the **Dimensions** folder, and then either click **Open** or **View Designer**.</span></span>  
  
         <span data-ttu-id="bd017-109">O bien</span><span class="sxs-lookup"><span data-stu-id="bd017-109">-or-</span></span>  
  
    -   <span data-ttu-id="bd017-110">En el diseñador de cubos, en la pestaña **estructura de cubo** , expanda la dimensión de cubo en el panel **dimensiones** y haga clic en \*\*Editar \<dimension> \*\*.</span><span class="sxs-lookup"><span data-stu-id="bd017-110">In Cube Designer, on the **Cube Structure** tab, expand the cube dimension in the **Dimensions** pane and click **Edit \<dimension>**.</span></span>  
  
3.  <span data-ttu-id="bd017-111">En el panel **Atributos** de la pestaña **Estructura de dimensión** , haga clic en el atributo cuya propiedad **KeyColumns** desee modificar.</span><span class="sxs-lookup"><span data-stu-id="bd017-111">On the **Dimension Structure** tab, in the **Attributes** pane, click the attribute whose **KeyColumns** property you want to modify.</span></span>  
  
4.  <span data-ttu-id="bd017-112">En la ventana **Propiedades** , haga clic en el valor de la propiedad **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="bd017-112">In the **Properties** window, click the value for the **KeyColumns** property.</span></span>  
  
5.  <span data-ttu-id="bd017-113">Haga clic en el botón Examinar **(…)** que aparece en la celda de valor del cuadro de propiedades.</span><span class="sxs-lookup"><span data-stu-id="bd017-113">Click the browse **(...)** button that appears in the value cell of the property box.</span></span>  
  
     <span data-ttu-id="bd017-114">Se abre el cuadro de diálogo **Columnas de clave** .</span><span class="sxs-lookup"><span data-stu-id="bd017-114">The **Key Columns** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="bd017-115">Para quitar una columna de clave existente, en la lista **Columnas de clave** , seleccione la columna y, después, haga clic en el botón **\<** .</span><span class="sxs-lookup"><span data-stu-id="bd017-115">To remove an existing key column, in the **Key Columns** list, select the column, and then click the **\<** button.</span></span>  
  
7.  <span data-ttu-id="bd017-116">Para agregar una columna de clave, en la lista **Columnas disponibles** , seleccione la columna y, después, haga clic en el botón **>** .</span><span class="sxs-lookup"><span data-stu-id="bd017-116">To add a key column, in the **Available Columns** list, select the column, and then click the **>** button.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bd017-117">Si define varias columnas de clave, el orden en el que esas columnas aparecen en la lista **Columnas de clave** afecta al orden de presentación.</span><span class="sxs-lookup"><span data-stu-id="bd017-117">If you define multiple key columns, the order in which those columns appear in the **Key Columns** list affects the display order.</span></span> <span data-ttu-id="bd017-118">Por ejemplo, un atributo de mes tiene dos columnas de clave: mes y año.</span><span class="sxs-lookup"><span data-stu-id="bd017-118">For example, a month attribute has two key columns: month and year.</span></span> <span data-ttu-id="bd017-119">Si la columna de año aparece en la lista antes de la columna de mes, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ordenarán por año y a continuación por mes.</span><span class="sxs-lookup"><span data-stu-id="bd017-119">If the year column appears in the list before the month column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by year and then by month.</span></span> <span data-ttu-id="bd017-120">Si la columna de mes aparece en la lista antes de la de año, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ordenarán por mes y a continuación por año.</span><span class="sxs-lookup"><span data-stu-id="bd017-120">If the month column appears before the year column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by month and then by year.</span></span>  
  
8.  <span data-ttu-id="bd017-121">Para cambiar el orden de las columnas de clave, seleccione una columna y, después, haga clic en el botón **Subir** o **Bajar** .</span><span class="sxs-lookup"><span data-stu-id="bd017-121">To change the order of key columns, select a column, and then click the **Up** or **Down** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd017-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd017-122">See Also</span></span>  
 [<span data-ttu-id="bd017-123">Referencia de las propiedades de los atributos de dimensión</span><span class="sxs-lookup"><span data-stu-id="bd017-123">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
