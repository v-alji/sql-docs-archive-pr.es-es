---
title: Agregar un medidor a un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 45da4fef-2b02-40e1-977c-f8f80d87155e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7125080d95e9c7b882df8d715cce5c6cf8aa6344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748665"
---
# <a name="add-a-gauge-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="fa75c-102">Agregar un medidor a un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="fa75c-102">Add a Gauge to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fa75c-103">Si desea resumir datos y presentarlos con un formato visual, puede usar una región de datos del medidor.</span><span class="sxs-lookup"><span data-stu-id="fa75c-103">When you want to summarize data in a visual format, you can use a Gauge data region.</span></span> <span data-ttu-id="fa75c-104">Después de agregar una región de datos del medidor a la superficie de diseño, puede arrastrar los campos de conjunto de datos de informe a un panel de datos del medidor.</span><span class="sxs-lookup"><span data-stu-id="fa75c-104">After you add a Gauge data region to the design surface, you can drag report dataset fields to a data pane on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-gauge-to-your-report"></a><span data-ttu-id="fa75c-105">Para agregar un medidor a un informe</span><span class="sxs-lookup"><span data-stu-id="fa75c-105">To add a gauge to your report</span></span>  
  
1.  <span data-ttu-id="fa75c-106">Cree un informe o abra un informe existente.</span><span class="sxs-lookup"><span data-stu-id="fa75c-106">Create a report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="fa75c-107">En la pestaña Insertar, haga doble clic en Medidor.</span><span class="sxs-lookup"><span data-stu-id="fa75c-107">On the Insert tab, double-click Gauge.</span></span> <span data-ttu-id="fa75c-108">Se abre el cuadro de diálogo **Seleccionar tipo de medidor** .</span><span class="sxs-lookup"><span data-stu-id="fa75c-108">The **Select Gauge Type** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="fa75c-109">Seleccione el tipo de medidor que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="fa75c-109">Select the type of gauge you want to add.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="fa75c-110">A diferencia de las regiones de datos Gráfico, la región de datos Medidor solo tiene dos tipos de medidores: lineal y radial.</span><span class="sxs-lookup"><span data-stu-id="fa75c-110">Unlike Chart, Gauge has only two types: linear and radial.</span></span> <span data-ttu-id="fa75c-111">Los medidores disponibles en el cuadro de diálogo **Seleccionar tipo de medidor** son plantillas para estos dos tipos de medidores.</span><span class="sxs-lookup"><span data-stu-id="fa75c-111">The available gauges in the **Select a Gauge Type** dialog box are templates for these two types of gauges.</span></span> <span data-ttu-id="fa75c-112">Por esta razón, no puede cambiar el tipo de medidor después de agregar el medidor a su informe.</span><span class="sxs-lookup"><span data-stu-id="fa75c-112">For this reason, you cannot change the gauge type after you add the gauge to your report.</span></span> <span data-ttu-id="fa75c-113">Para cambiar el tipo de un medidor, debe eliminarlo y volver a agregarlo.</span><span class="sxs-lookup"><span data-stu-id="fa75c-113">You must delete and re-add a gauge to change its type.</span></span>  
  
     <span data-ttu-id="fa75c-114">Si el informe no tiene origen de datos y conjunto de datos, se abre el cuadro de diálogo **Propiedades del origen de datos** , que le guía en los pasos necesarios para crear ambos.</span><span class="sxs-lookup"><span data-stu-id="fa75c-114">If the report has no data source and dataset the **Data Source Properties** dialog box opens and takes you through the steps to create both.</span></span> <span data-ttu-id="fa75c-115">Para obtener más información, vea [Agregar y comprobar una conexión de datos o un origen de datos &#40;generador de informes y SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fa75c-115">For more information see, [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="fa75c-116">Si el informe tiene un origen de datos, pero no un conjunto de datos, se abre el cuadro de diálogo **Propiedades del conjunto de datos** , que le guía en los pasos necesarios para crear uno.</span><span class="sxs-lookup"><span data-stu-id="fa75c-116">If the report has a data source, but no dataset the **Dataset Properties** dialog box opens and takes you through the steps to create one.</span></span> <span data-ttu-id="fa75c-117">Para obtener más información, vea [Crear un conjunto de datos compartido o un conjunto de datos incrustado &#40;Generador de informes y SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fa75c-117">For more information, see [Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span></span>  
  
4.  <span data-ttu-id="fa75c-118">Haga clic en el medidor para mostrar el panel de datos.</span><span class="sxs-lookup"><span data-stu-id="fa75c-118">Click the gauge to display the data pane.</span></span> <span data-ttu-id="fa75c-119">De forma predeterminada, un medidor tiene un puntero que corresponde a un valor.</span><span class="sxs-lookup"><span data-stu-id="fa75c-119">By default, a gauge has one pointer corresponding to one value.</span></span> <span data-ttu-id="fa75c-120">Puede agregar punteros adicionales.</span><span class="sxs-lookup"><span data-stu-id="fa75c-120">You can add additional pointers.</span></span>  
  
5.  <span data-ttu-id="fa75c-121">Agregue un campo del conjunto de datos a la zona de colocación de campos de datos.</span><span class="sxs-lookup"><span data-stu-id="fa75c-121">Add one field from the dataset to the data field drop-zone.</span></span> <span data-ttu-id="fa75c-122">Puede agregar solo un campo.</span><span class="sxs-lookup"><span data-stu-id="fa75c-122">You can add only one field.</span></span> <span data-ttu-id="fa75c-123">Si desea mostrar varios, debe agregar punteros adicionales, uno para cada campo.</span><span class="sxs-lookup"><span data-stu-id="fa75c-123">If you want to display multiple fields, you must add additional pointers, one for each field.</span></span>  
  
     <span data-ttu-id="fa75c-124">Haga doble clic en la escala del medidor y seleccione **Propiedades de escala**.</span><span class="sxs-lookup"><span data-stu-id="fa75c-124">Right-click the gauge scale, and select **Scale Properties**.</span></span> <span data-ttu-id="fa75c-125">Especifique los valores **Mínimo** y **Máximo** de la escala.</span><span class="sxs-lookup"><span data-stu-id="fa75c-125">Type a value for the **Minimum** and **Maximum** of the scale.</span></span> <span data-ttu-id="fa75c-126">Para más información, vea [Establecer un valor mínimo o máximo en un medidor &#40;Generador de informes y SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fa75c-126">For more information, see [Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa75c-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa75c-127">See Also</span></span>  
 <span data-ttu-id="fa75c-128">[Anidar regiones de datos &#40;Generador de informes y SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fa75c-128">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="fa75c-129">Medidores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fa75c-129">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
