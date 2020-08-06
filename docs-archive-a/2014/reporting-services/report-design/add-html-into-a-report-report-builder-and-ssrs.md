---
title: Agregar HTML a un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 30bd631a-f774-48e7-a13a-b6c2eb54d9bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 605c84843d62fb664a8a665a3fc3b024f8f87186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748649"
---
# <a name="add-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="f5a10-102">Agregar HTML a un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="f5a10-102">Add HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f5a10-103">Mediante un marcador de posición, puede importar HTML de un campo del conjunto de datos para usarlo en el informe.</span><span class="sxs-lookup"><span data-stu-id="f5a10-103">Using a placeholder, you can import HTML from a field in your dataset for use in the report.</span></span> <span data-ttu-id="f5a10-104">De forma predeterminada, un marcador de posición representa texto simple, por lo que deberá cambiar el tipo de marcado del marcador de posición a HTML.</span><span class="sxs-lookup"><span data-stu-id="f5a10-104">By default, a placeholder represents plain text, so you will need to change the placeholder mark-up type to HTML.</span></span> <span data-ttu-id="f5a10-105">Para más información, vea [Importar HTML en un informe &#40;Generador de informes y SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f5a10-105">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-html-from-a-field-in-your-dataset-into-a-text-box"></a><span data-ttu-id="f5a10-106">Para agregar HTML de un campo del conjunto de datos en un cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="f5a10-106">To add HTML from a field in your dataset into a text box</span></span>  
  
1.  <span data-ttu-id="f5a10-107">En la pestaña **Insertar** , haga clic en **Lista**.</span><span class="sxs-lookup"><span data-stu-id="f5a10-107">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="f5a10-108">Haga clic en la superficie de diseño y, a continuación, arrastre para crear un cuadro que tenga el tamaño que desee.</span><span class="sxs-lookup"><span data-stu-id="f5a10-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
     <span data-ttu-id="f5a10-109">Se abre el cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="f5a10-109">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="f5a10-110">En el informe, podrá utilizar un conjunto de datos compartido o un conjunto de datos incrustado.</span><span class="sxs-lookup"><span data-stu-id="f5a10-110">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="f5a10-111">Para más información, haga clic en [Propiedades del conjunto de datos (cuadro de diálogo), Consulta &#40;Generador de informes&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) o [Propiedades del conjunto de datos (cuadro de diálogo), Consulta](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="f5a10-111">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="f5a10-112">En la pestaña **Insertar** , haga clic en **Cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="f5a10-112">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="f5a10-113">Haga clic en la lista y, a continuación, arrastre para crear un cuadro que tenga el tamaño que desee.</span><span class="sxs-lookup"><span data-stu-id="f5a10-113">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="f5a10-114">Arrastre un campo HTML desde el conjunto de datos hasta el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="f5a10-114">Drag an HTML field from your dataset into the text box.</span></span> <span data-ttu-id="f5a10-115">Se crea un marcador de posición para el campo.</span><span class="sxs-lookup"><span data-stu-id="f5a10-115">A placeholder is created for your field.</span></span>  
  
4.  <span data-ttu-id="f5a10-116">Haga clic con el botón derecho en el marcador de posición y, después, haga clic en **Propiedades de marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="f5a10-116">Right-click the placeholder, and then click **Placeholder Properties**.</span></span>  
  
5.  <span data-ttu-id="f5a10-117">En la pestaña **General** , compruebe que el cuadro **Valor** contiene una expresión que se evalúa como el campo que colocó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="f5a10-117">On the **General** tab, verify that the **Value** box contains an expression that evaluates to the field you dropped in step 3.</span></span>  
  
6.  <span data-ttu-id="f5a10-118">Haga clic en **HTML - Interpretar etiquetas HTML como estilos**.</span><span class="sxs-lookup"><span data-stu-id="f5a10-118">Click **HTML - Interpret HTML tags as styles**.</span></span> <span data-ttu-id="f5a10-119">Esto provocará que el campo se evalúe como HTML.</span><span class="sxs-lookup"><span data-stu-id="f5a10-119">This causes the field to be evaluated as HTML.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5a10-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5a10-120">See Also</span></span>  
 <span data-ttu-id="f5a10-121">[Aplicar formato a números y fechas &#40;Generador de informes y SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f5a10-121">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f5a10-122">[Aplicar formato a líneas, colores e imágenes &#40;Generador de informes y SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f5a10-122">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f5a10-123">Cuadro de diálogo Propiedades del marcador de posición, General &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f5a10-123">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
