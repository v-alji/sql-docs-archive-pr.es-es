---
title: 'Lección 3: Diseñar el informe primario mediante el Asistente para informes | Microsoft Docs'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2f69dcd3-cd6d-45a9-a62a-ba6f5f3179d8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3cb6a0972a2bb63e82e80c02b3ce90912ba01c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669514"
---
# <a name="lesson-3-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="e4ef4-102">Lección 3: Diseñar el informe primario usando el Asistente para informes</span><span class="sxs-lookup"><span data-stu-id="e4ef4-102">Lesson 3: Design the Parent Report using the Report Wizard</span></span>
  <span data-ttu-id="e4ef4-103">Después de crear una conexión de datos y una tabla de datos para el informe primario, el paso siguiente consiste en diseñar dicho informe usando el Asistente para informes del Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-103">After you create a data connection and a data table for the parent report, your next step is to design the parent report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="e4ef4-104">Para más información sobre el Diseñador de informes, vea [Diseñar informes con el Diseñador de informes &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e4ef4-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="e4ef4-105">Para diseñar el informe primario usando el Asistente para informes</span><span class="sxs-lookup"><span data-stu-id="e4ef4-105">To design the parent report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="e4ef4-106">Asegúrese de que el sitio web de nivel superior está seleccionado en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="e4ef4-107">Haga clic con el botón derecho en el sitio web y seleccione **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="e4ef4-108">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Asistente para informes**, escriba un nombre para el archivo de informe y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-108">In the **Add New Item** dialog box, select **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="e4ef4-109">Así se inicia el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="e4ef4-110">En la página **Propiedades de conjunto de datos** , en el cuadro **Origen de datos** , seleccione el **DataSet1** que creó en la [Lección 2: Definir una conexión de datos y una tabla de datos para el informe primario](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span><span class="sxs-lookup"><span data-stu-id="e4ef4-110">On the **Dataset Properties** page, in the **Data source** box, select the **DataSet1** you created in [Lesson 2: Define a Data Connection and Data Table for Parent Report](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span></span>  
    <span data-ttu-id="e4ef4-111">El cuadro **Conjuntos de datos disponibles** se actualiza automáticamente con la **DataTable** que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-111">The **Available datasets** box is automatically updated with the **DataTable** you created above.</span></span>  
  
5.  <span data-ttu-id="e4ef4-112">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="e4ef4-113">En la página **Organizar campos** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4ef4-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="e4ef4-114">Arrastre **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**y **ReorderLevel** desde **Campos disponibles** hasta el cuadro **Valores** .</span><span class="sxs-lookup"><span data-stu-id="e4ef4-114">Drag **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**, and **ReorderLevel** from **Available fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="e4ef4-115">Haga clic en la flecha situada junto a **SUM (ProductID)**, **SUM (SafetyStockLevel)**, **SUM (ReorderLevel)** y desactive la selección de **suma** .</span><span class="sxs-lookup"><span data-stu-id="e4ef4-115">Click the arrow next to **Sum(ProductID)**, **Sum(SafetyStockLevel)**, **Sum(ReorderLevel)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="e4ef4-116">Haga clic en **siguiente** dos veces y, a continuación, haga clic en **Finalizar** para cerrar el **Asistente para informes**.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="e4ef4-117">Ahora ha creado el archivo .rdlc.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="e4ef4-118">El archivo se abre en el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-118">The file opens in Report Designer.</span></span> <span data-ttu-id="e4ef4-119">El Tablix que se diseñó se muestra en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="e4ef4-120">Guarde el archivo .rdlc.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-120">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="e4ef4-121">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="e4ef4-121">Next Task</span></span>  
 <span data-ttu-id="e4ef4-122">Ha diseñado correctamente el informe primario usando el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-122">You have successfully designed the parent report using the Report Wizard.</span></span> <span data-ttu-id="e4ef4-123">A continuación, creará una conexión de datos y una tabla de datos para el informe secundario.</span><span class="sxs-lookup"><span data-stu-id="e4ef4-123">Next, you will create a data connection and a data table for the child report.</span></span>  
  
  
