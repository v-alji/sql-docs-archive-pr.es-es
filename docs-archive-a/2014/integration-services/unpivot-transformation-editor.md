---
title: Editor de transformación anulación de dinamización | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottransformation.f1
helpviewer_keywords:
- Unpivot Transformation Editor
ms.assetid: 72a36ef0-4070-4f6c-9c74-0720109617dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c3b93370b34440b73b4c9c78dc7d19fa4095275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669735"
---
# <a name="unpivot-transformation-editor"></a><span data-ttu-id="a6065-102">Editor de transformación Anulación de dinamización</span><span class="sxs-lookup"><span data-stu-id="a6065-102">Unpivot Transformation Editor</span></span>
  <span data-ttu-id="a6065-103">Use el cuadro de diálogo **Editor de transformación Anulación de dinamización** para seleccionar las columnas que se van a dinamizar en filas y especificar la columna de datos y la nueva columna de salida del valor dinámico.</span><span class="sxs-lookup"><span data-stu-id="a6065-103">Use the **Unpivot Transformation Editor** dialog box to select the columns to pivot into rows, and to specify the data column and the new pivot value output column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6065-104"> Este tema utiliza el escenario Anulación de dinamización descrito en [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) para ilustrar el uso de las opciones.</span><span class="sxs-lookup"><span data-stu-id="a6065-104">This topic relies on the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) to illustrate the use of the options.</span></span>  
  
 <span data-ttu-id="a6065-105">Para obtener más información acerca de la transformación Anulación de dinamización, vea [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a6065-105">To learn more about the Unpivot transformation, see [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a6065-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="a6065-106">Options</span></span>  
 <span data-ttu-id="a6065-107">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="a6065-107">**Available Input Columns**</span></span>  
 <span data-ttu-id="a6065-108">Especifique las columnas que deben pasar a ser filas mediante las casillas.</span><span class="sxs-lookup"><span data-stu-id="a6065-108">Using the check boxes, specify the columns to pivot into rows.</span></span>  
  
 <span data-ttu-id="a6065-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a6065-109">**Name**</span></span>  
 <span data-ttu-id="a6065-110">Muestra el nombre de la columna de entrada disponible.</span><span class="sxs-lookup"><span data-stu-id="a6065-110">View the name of the available input column.</span></span>  
  
 <span data-ttu-id="a6065-111">**Paso a través**</span><span class="sxs-lookup"><span data-stu-id="a6065-111">**Pass Through**</span></span>  
 <span data-ttu-id="a6065-112">Indique si desea incluir la columna en la salida de anulación de dinamización.</span><span class="sxs-lookup"><span data-stu-id="a6065-112">Indicate whether to include the column in the unpivoted output.</span></span>  
  
 <span data-ttu-id="a6065-113">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="a6065-113">**Input Column**</span></span>  
 <span data-ttu-id="a6065-114">Seleccione de la lista de entradas disponibles las columnas para cada fila.</span><span class="sxs-lookup"><span data-stu-id="a6065-114">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="a6065-115">Las selecciones se reflejan en las casillas activadas en la tabla **Columnas de entrada disponibles** .</span><span class="sxs-lookup"><span data-stu-id="a6065-115">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="a6065-116">En el escenario Anulación de dinamización descrito en [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), las columnas de entrada son las columnas **Ham**, **Soda**, **Milk**, **Beer**y **Chips** .</span><span class="sxs-lookup"><span data-stu-id="a6065-116">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Input Columns are the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns.</span></span>  
  
 <span data-ttu-id="a6065-117">**Columna de destino**</span><span class="sxs-lookup"><span data-stu-id="a6065-117">**Destination Column**</span></span>  
 <span data-ttu-id="a6065-118">Escriba un nombre para la columna de datos.</span><span class="sxs-lookup"><span data-stu-id="a6065-118">Provide a name for the data column.</span></span>  
  
 <span data-ttu-id="a6065-119">En el escenario Anulación de dinamización descrito en [Transformación Anulación de dinamización](data-flow/transformations/unpivot-transformation.md), la columna de destino es la columna de cantidad (**Qty**).</span><span class="sxs-lookup"><span data-stu-id="a6065-119">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Destination Column is the quantity (**Qty**) column.</span></span>  
  
 <span data-ttu-id="a6065-120">**Valor de clave dinámica**</span><span class="sxs-lookup"><span data-stu-id="a6065-120">**Pivot Key Value**</span></span>  
 <span data-ttu-id="a6065-121">Escriba el nombre del valor de dinamización.</span><span class="sxs-lookup"><span data-stu-id="a6065-121">Provide a name for the pivot value.</span></span> <span data-ttu-id="a6065-122">El nombre predeterminado es el de la columna de entrada, pero puede elegir cualquier nombre descriptivo único.</span><span class="sxs-lookup"><span data-stu-id="a6065-122">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="a6065-123">Puede especificar el valor de esta propiedad con una expresión de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a6065-123">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="a6065-124">En el escenario Anulación de dinamización descrito en [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), los valores de dinamización se mostrarán como valores de texto en la nueva columna Product, designada en la opción **Nombre de la columna del valor de clave dinámica** , como los valores de texto **Ham**, **Soda**, **Milk**, **Beer**y **Chips**.</span><span class="sxs-lookup"><span data-stu-id="a6065-124">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Values will appear in the new Product column designated by the **Pivot Key Value Column Name** option, as the text values **Ham**, **Soda**, **Milk**, **Beer**, and **Chips**.</span></span>  
  
 <span data-ttu-id="a6065-125">**Nombre de la columna del valor de clave dinámica**</span><span class="sxs-lookup"><span data-stu-id="a6065-125">**Pivot Key Value Column Name**</span></span>  
 <span data-ttu-id="a6065-126">Escriba un nombre para la columna del valor de dinamización.</span><span class="sxs-lookup"><span data-stu-id="a6065-126">Provide a name for the pivot value column.</span></span> <span data-ttu-id="a6065-127">El valor predeterminado es "Valor de clave dinámica", pero podrá elegir cualquier nombre descriptivo único.</span><span class="sxs-lookup"><span data-stu-id="a6065-127">The default is "Pivot Key Value"; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="a6065-128">En el escenario Anulación de dinamización descrito en [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), el Nombre de la columna del valor de clave dinámica es **Product** y designa la nueva columna **Product** en la que se anula la dinamización de las columnas **Ham**, **Soda**, **Milk**, **Beer**y **Chips** .</span><span class="sxs-lookup"><span data-stu-id="a6065-128">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Key Value Column Name is **Product** and designates the new **Product** column into which the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns are unpivoted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6065-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6065-129">See Also</span></span>  
 <span data-ttu-id="a6065-130">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a6065-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="a6065-131">Transformación dinámica</span><span class="sxs-lookup"><span data-stu-id="a6065-131">Pivot Transformation</span></span>](data-flow/transformations/pivot-transformation.md)  
  
  
