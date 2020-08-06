---
title: 'Lección 5: Diseñar el informe secundario usando el Asistente para informes | Microsoft Docs'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19a3f927-ea97-4f40-a5f8-cd5f2598e4da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f188a914fc2a2bb8370843191a31474a54c02aa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669508"
---
# <a name="lesson-5-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="bec35-102">Lección 5: Diseñar el informe secundario usando el Asistente para informes</span><span class="sxs-lookup"><span data-stu-id="bec35-102">Lesson 5: Design the Child Report using the Report Wizard</span></span>
  <span data-ttu-id="bec35-103">Después de crear una conexión de datos y una tabla de datos para el informe secundario, el paso siguiente consiste en diseñar dicho informe usando el Asistente para informes del Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="bec35-103">After you create a data connection and data table for the child report, your next step is to design the child report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="bec35-104">Para más información sobre el Diseñador de informes, vea [Diseñar informes con el Diseñador de informes &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bec35-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="bec35-105">Para diseñar el informe secundario usando el Asistente para informes</span><span class="sxs-lookup"><span data-stu-id="bec35-105">To design the child report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="bec35-106">Asegúrese de que el sitio web de nivel superior está seleccionado en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="bec35-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="bec35-107">Haga clic con el botón derecho en el sitio web y seleccione **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="bec35-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="bec35-108">En el cuadro de diálogo **Agregar nuevo elemento** , haga clic en **Asistente para informes**, escriba un nombre para el archivo de informe y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bec35-108">In the **Add New Item** dialog box, click **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="bec35-109">Así se inicia el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="bec35-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="bec35-110">En la página **propiedades del conjunto** de datos, en el cuadro origen de **datos** , haga clic en **DataSet2**.</span><span class="sxs-lookup"><span data-stu-id="bec35-110">In the **Dataset Properties** page, in the **Data source** box, click **DataSet2**.</span></span>  
  
     <span data-ttu-id="bec35-111">El cuadro **Conjuntos de datos disponibles** se actualiza automáticamente con el elemento DataTable que ha creado.</span><span class="sxs-lookup"><span data-stu-id="bec35-111">The **Available datasets** box is automatically updated with the DataTable you created.</span></span>  
  
5.  <span data-ttu-id="bec35-112">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="bec35-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="bec35-113">En la página **Organizar campos** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bec35-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="bec35-114">Arrastre **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**y **StockedQty** desde **Campos disponibles** hasta el cuadro **Valores** .</span><span class="sxs-lookup"><span data-stu-id="bec35-114">Drag **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**, and **StockedQty** from **Available Fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="bec35-115">Haga clic en la flecha situada junto a **SUM (ProductID)**, **SUM (PurchaseOrderID)**, **SUM (PurchaseOrderDetailID)**, **SUM (OrderQty)**, **SUM (ReceivedQty)**, **SUM (RejectedQty)** y **SUM (StockedQty)** y desactive la selección de **suma** .</span><span class="sxs-lookup"><span data-stu-id="bec35-115">Click the arrow next to **Sum(ProductID)**, **Sum(PurchaseOrderID)**, **Sum(PurchaseOrderDetailID)**, **Sum(OrderQty)**, **Sum(ReceivedQty)**, **Sum(RejectedQty)**, and **Sum(StockedQty)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="bec35-116">Haga clic en **siguiente** dos veces y, a continuación, haga clic en **Finalizar** para cerrar el **Asistente para informes**.</span><span class="sxs-lookup"><span data-stu-id="bec35-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="bec35-117">Ahora ha creado el archivo .rdlc.</span><span class="sxs-lookup"><span data-stu-id="bec35-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="bec35-118">El archivo se abre en el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="bec35-118">The file opens in Report Designer.</span></span> <span data-ttu-id="bec35-119">El Tablix que se diseñó se muestra en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="bec35-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="bec35-120">Con el archivo .rdlc abierto, agregue un parámetro haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bec35-120">With the .rdlc file open, add a parameter by doing the following:</span></span>  
  
    1.  <span data-ttu-id="bec35-121">Haga clic en **parámetros** en el panel **datos de informe** y, a continuación, haga clic en **agregar parámetros**.</span><span class="sxs-lookup"><span data-stu-id="bec35-121">Click **Parameters** in the **Report Data** pane, and then click **Add Parameters**.</span></span>  
  
    2.  <span data-ttu-id="bec35-122">Escriba **productid** en el cuadro **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="bec35-122">Enter **productid** in the **Name** box.</span></span>  
  
    3.  <span data-ttu-id="bec35-123">Confirme que **Entero** está seleccionado en el cuadro de lista **Tipo de datos** .</span><span class="sxs-lookup"><span data-stu-id="bec35-123">Confirm that **Integer** is selected in the **Data Type** list box.</span></span>  
  
    4.  <span data-ttu-id="bec35-124">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="bec35-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="bec35-125">Guarde el archivo .rdlc.</span><span class="sxs-lookup"><span data-stu-id="bec35-125">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="bec35-126">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="bec35-126">Next Task</span></span>  
 <span data-ttu-id="bec35-127">Ha diseñado correctamente el informe secundario usando el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="bec35-127">You have successfully designed the child report by using the Report Wizard.</span></span> <span data-ttu-id="bec35-128">Luego, agregará un control ReportViewer a la aplicación de sitio Web.</span><span class="sxs-lookup"><span data-stu-id="bec35-128">Next, you will add a ReportViewer control to the website application.</span></span>  
  
  
