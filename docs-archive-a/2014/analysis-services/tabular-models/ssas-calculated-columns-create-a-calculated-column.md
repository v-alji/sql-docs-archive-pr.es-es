---
title: Crear una columna calculada (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.as.daxref.CreataCalculatedColumn.f1
ms.assetid: 59440510-2d76-41dc-9b55-edc15259f9da
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdb56ffb2b42aa8225b7eff76b11315ea511fd81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743635"
---
# <a name="create-a-calculated-column-ssas-tabular"></a><span data-ttu-id="b98ee-102">Crear una columna calculada (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="b98ee-102">Create a Calculated Column (SSAS Tabular)</span></span>
  <span data-ttu-id="b98ee-103">Las columnas calculadas permiten agregar nuevos datos al modelo.</span><span class="sxs-lookup"><span data-stu-id="b98ee-103">Calculated columns allow you to add new data to your model.</span></span> <span data-ttu-id="b98ee-104">En lugar de pegar o importar valores en la columna, se crea una fórmula DAX que define los valores de nivel de fila de la columna.</span><span class="sxs-lookup"><span data-stu-id="b98ee-104">Instead of pasting or importing values into the column, you create a DAX formula that defines the column's row level values.</span></span> <span data-ttu-id="b98ee-105">Los valores de cada fila de una columna calculada se calculan y se rellenan al crear una fórmula válida y hacer clic en ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b98ee-105">The values in each row of a calculated column are calculated and populated when you create a valid formula and then click ENTER.</span></span> <span data-ttu-id="b98ee-106">A continuación, la columna calculada se puede agregar a una aplicación de informes o de análisis como cualquier otra columna de datos.</span><span class="sxs-lookup"><span data-stu-id="b98ee-106">The calculated column can then be added to a reporting or analysis application just as would any other column of data.</span></span> <span data-ttu-id="b98ee-107">En este tema se describe cómo crear una nueva columna calculada con la barra de fórmulas DAX del diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="b98ee-107">This topic describes how to create a new calculated column by using the DAX formula bar in the model designer.</span></span>  
  
#### <a name="to-create-a-new-calculated-column"></a><span data-ttu-id="b98ee-108">Para crear una nueva columna calculada</span><span class="sxs-lookup"><span data-stu-id="b98ee-108">To create a new calculated column</span></span>  
  
1.  <span data-ttu-id="b98ee-109">En el diseñador de modelos, en Vista de datos, seleccione la tabla a la que desea agregar una columna calculada, haga clic en el menú **Columna** y, a continuación, haga clic en **Agregar columna**.</span><span class="sxs-lookup"><span data-stu-id="b98ee-109">In the model designer, in Data View, select the table to which you want to add a calculated column, then click the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="b98ee-110">**Agregar columna** se resalta sobre la columna vacía situada a la derecha y el cursor se mueve a la barra de fórmulas.</span><span class="sxs-lookup"><span data-stu-id="b98ee-110">**Add Column** is highlighted over the empty rightmost column, and the cursor moves to the formula bar.</span></span>  
  
     <span data-ttu-id="b98ee-111">Para crear una columna entre dos columnas existentes, haga clic con el botón derecho en una columna existente y, después, haga clic en **Insertar columna**.</span><span class="sxs-lookup"><span data-stu-id="b98ee-111">To create a new column between two existing columns, right-click an existing column, and then click **Insert Column**.</span></span>  
  
2.  <span data-ttu-id="b98ee-112">En la barra de fórmulas, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b98ee-112">In the formula bar, do one of the following:</span></span>  
  
    -   <span data-ttu-id="b98ee-113">Escriba un signo igual seguido de una fórmula.</span><span class="sxs-lookup"><span data-stu-id="b98ee-113">Type an equal sign followed by a formula.</span></span>  
  
    -   <span data-ttu-id="b98ee-114">Escriba un signo igual seguido de una función DAX y, a continuación, especifique los argumentos y los parámetros que requiere la función.</span><span class="sxs-lookup"><span data-stu-id="b98ee-114">Type an equal sign, followed by a DAX function, followed by arguments and parameters as required by the function.</span></span>  
  
    -   <span data-ttu-id="b98ee-115">Haga clic en el botón de función (**fx**), seleccione una categoría y una función en el cuadro de diálogo **Insertar función** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b98ee-115">Click the function button (**fx**), then in the **Insert Function** dialog box, select a category and function, and then click **OK**.</span></span> <span data-ttu-id="b98ee-116">En la barra de fórmulas, escriba los argumentos y los parámetros restantes que requiere la función.</span><span class="sxs-lookup"><span data-stu-id="b98ee-116">In the formula bar, type the remaining arguments and parameters as required by the function.</span></span>  
  
3.  <span data-ttu-id="b98ee-117">Presione ENTRAR para aceptar la fórmula.</span><span class="sxs-lookup"><span data-stu-id="b98ee-117">Press ENTER to accept the formula.</span></span>  
  
     <span data-ttu-id="b98ee-118">Toda la columna se rellena con la fórmula y se calcula un valor para cada fila.</span><span class="sxs-lookup"><span data-stu-id="b98ee-118">The entire column is populated with the formula, and a value is calculated for each row.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="b98ee-119">Puede usar la función Autocompletar fórmula de DAX en medio de una fórmula existente con funciones anidadas.</span><span class="sxs-lookup"><span data-stu-id="b98ee-119">You can use DAX Formula AutoComplete in the middle of an existing formula with nested functions.</span></span> <span data-ttu-id="b98ee-120">El texto situado inmediatamente antes del punto de inserción se usa para mostrar los valores de la lista desplegable, mientras que todo el texto situado después del punto de inserción se mantiene inalterado.</span><span class="sxs-lookup"><span data-stu-id="b98ee-120">The text immediately before the insertion point is used to display values in the drop-down list, and all of the text after the insertion point remains unchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b98ee-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b98ee-121">See Also</span></span>  
 <span data-ttu-id="b98ee-122">[Columnas calculadas &#40;&#41;tabular de SSAS](ssas-calculated-columns.md) </span><span class="sxs-lookup"><span data-stu-id="b98ee-122">[Calculated Columns &#40;SSAS Tabular&#41;](ssas-calculated-columns.md) </span></span>  
 [<span data-ttu-id="b98ee-123">Medidas &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="b98ee-123">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
