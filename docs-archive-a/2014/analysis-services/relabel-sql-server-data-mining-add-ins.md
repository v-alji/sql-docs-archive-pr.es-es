---
title: Cambiar etiquetas (SQL Server complementos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- relabel
- data cleaning
ms.assetid: af041b39-fdd1-4cb5-a5ef-2f3ddab84614
author: minewiskan
ms.author: owend
ms.openlocfilehash: a625676f60e2da32e19b85a94002b51eeb9ac816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673285"
---
# <a name="relabel-sql-server-data-mining-add-ins"></a><span data-ttu-id="11a94-102">Cambiar etiquetas (Complementos de minería de datos de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="11a94-102">Relabel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="11a94-103">![Icono de Office 13 para la herramienta Relabel](media/dm13-relabel.gif "Icono de Office 13 para la herramienta Relabel")</span><span class="sxs-lookup"><span data-stu-id="11a94-103">![Office 13 icon for Relabel tool](media/dm13-relabel.gif "Office 13 icon for Relabel tool")</span></span>

 <span data-ttu-id="11a94-104">El Cliente de minería de datos para Excel le permite crear nuevas etiquetas para los datos con el fin de simplificar la comprensión de los resultados del análisis.</span><span class="sxs-lookup"><span data-stu-id="11a94-104">The Data Mining Client for Excel helps you create new labels for data to make it easier to understand the results of analysis.</span></span>

 <span data-ttu-id="11a94-105">Algunos motivos para cambiar las etiquetas son:</span><span class="sxs-lookup"><span data-stu-id="11a94-105">Reasons for relabeling include:</span></span>

-   <span data-ttu-id="11a94-106">Los datos incluyen los resultados que se codificaron, como 1 para Hombre y 2 para Mujer.</span><span class="sxs-lookup"><span data-stu-id="11a94-106">The data includes results that were coded, such as 1 for Male and 2 for Female.</span></span>

-   <span data-ttu-id="11a94-107">Va a crear depósitos con los valores numéricos y desea proporcionar a los intervalos un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="11a94-107">You are bucketing numeric values and want to give the ranges a descriptive name.</span></span>

-   <span data-ttu-id="11a94-108">Desea simplificar los nombres largos.</span><span class="sxs-lookup"><span data-stu-id="11a94-108">You want to simplify long names.</span></span>

## <a name="using-the-relabel-wizard"></a><span data-ttu-id="11a94-109">Usar el Asistente para cambiar etiquetas</span><span class="sxs-lookup"><span data-stu-id="11a94-109">Using the Relabel Wizard</span></span>

1.  <span data-ttu-id="11a94-110">En la cinta de opciones **minería de datos** , haga clic en **limpiar** y seleccione **cambiar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="11a94-110">In the **Data Mining** ribbon, click **Clean** and then select **Re-Label**.</span></span>

2.  <span data-ttu-id="11a94-111">Seleccione la tabla o el intervalo de datos que tenga los datos que desee corregir.</span><span class="sxs-lookup"><span data-stu-id="11a94-111">Select the table or data range that has the data you want to fix.</span></span>

3.  <span data-ttu-id="11a94-112">En la página **cambiar etiqueta** del asistente, seleccione una sola columna; para ello, elija la columna en la lista desplegable o haga clic en la columna en el panel **muestras de datos** .</span><span class="sxs-lookup"><span data-stu-id="11a94-112">In the **Re-label** page of the wizard, select a single column, either by choosing the column from the dropdown list, or by clicking the column in the **Data samples** pane.</span></span>

     <span data-ttu-id="11a94-113">En el panel de **ejemplos de datos** solo se muestran aproximadamente 50 filas de datos, pero se muestrean para asegurarse de que ve una buena distribución de valores.</span><span class="sxs-lookup"><span data-stu-id="11a94-113">The **Data samples** pane only shows about 50 rows of data, but they are sampled to ensure that you see a good spread of values.</span></span>

     <span data-ttu-id="11a94-114">Haga clic en el encabezado de columna de **recuento** para ordenar por el recuento de cada valor.</span><span class="sxs-lookup"><span data-stu-id="11a94-114">Click the column header for **Count** to sort by the count of each value.</span></span>

     <span data-ttu-id="11a94-115">También puede ordenar por **etiquetas originales**, lo que resulta útil si desea volver a etiquetar primero todos los valores más altos o más bajos.</span><span class="sxs-lookup"><span data-stu-id="11a94-115">You can also sort by **Original Labels**, which is handy if you want to re-label all the highest or lowest values first.</span></span>

4.  <span data-ttu-id="11a94-116">En la página **cambiar etiquetas** de datos del asistente, revise los valores de la columna **etiquetas originales** y decida cómo desea agruparlos o editarlos.</span><span class="sxs-lookup"><span data-stu-id="11a94-116">In the **Re-label** data page of the wizard, review the values in the **Original Labels** column, and decide how you want to group or edit them.</span></span>

5.  <span data-ttu-id="11a94-117">Escriba un nuevo valor en la fila bajo **etiquetas nuevas**.</span><span class="sxs-lookup"><span data-stu-id="11a94-117">Type a new value into the row under **New Labels**.</span></span> <span data-ttu-id="11a94-118">También puede elegir un valor de la lista de valores existentes.</span><span class="sxs-lookup"><span data-stu-id="11a94-118">You can also choose a value from the list of existing values.</span></span> <span data-ttu-id="11a94-119">A medida que escribe nuevos valores, estos están disponibles inmediatamente para su reutilización.</span><span class="sxs-lookup"><span data-stu-id="11a94-119">As you type new values, they become available for re-use right away.</span></span>

6.  <span data-ttu-id="11a94-120">Cuando haya especificado suficientes filas, haga clic en **siguiente**y, en la página **Seleccionar destino** , elija dónde guardará los datos cambiados de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="11a94-120">When you have entered enough rows, click **Next**, and on the **Select Destination** page, choose where you'll save the relabeled data.</span></span>

    -   <span data-ttu-id="11a94-121">**Agregar a la hoja de cálculo actual como una nueva columna**</span><span class="sxs-lookup"><span data-stu-id="11a94-121">**Add as a new column to the current worksheet**</span></span>

         <span data-ttu-id="11a94-122">Haga clic en esta opción para agregar una columna nueva a la tabla que contiene los valores nuevos.</span><span class="sxs-lookup"><span data-stu-id="11a94-122">Click to add a new column to the table that contains the new values.</span></span>

    -   <span data-ttu-id="11a94-123">**Copiar datos de hoja con cambios a una nueva hoja de cálculo**</span><span class="sxs-lookup"><span data-stu-id="11a94-123">**Copy sheet data with changes to a new worksheet**</span></span>

         <span data-ttu-id="11a94-124">Haga clic en esta opción para crear una hoja de cálculo nueva que contenga los datos actualizados.</span><span class="sxs-lookup"><span data-stu-id="11a94-124">Click to create a new worksheet that contains the updated data.</span></span>

    -   <span data-ttu-id="11a94-125">**Cambiar datos en su lugar**</span><span class="sxs-lookup"><span data-stu-id="11a94-125">**Change data in place**</span></span>

         <span data-ttu-id="11a94-126">Haga clic en esta opción para sustituir los datos originales por los valores nuevos.</span><span class="sxs-lookup"><span data-stu-id="11a94-126">Click to replace the original data with the new values.</span></span>

## <a name="see-also"></a><span data-ttu-id="11a94-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11a94-127">See Also</span></span>
 [<span data-ttu-id="11a94-128">Explorar y limpiar datos</span><span class="sxs-lookup"><span data-stu-id="11a94-128">Exploring and Cleaning Data</span></span>](exploring-and-cleaning-data.md)


