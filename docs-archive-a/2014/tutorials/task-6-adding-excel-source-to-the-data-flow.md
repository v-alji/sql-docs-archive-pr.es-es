---
title: 'Tarea 6: agregar el origen de Excel al flujo de datos | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0209055e-cb6b-4a07-909e-836596727a2c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ae183dee04619a407655026a49b189f7bb3ac6fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675685"
---
# <a name="task-6-adding-excel-source-to-the-data-flow"></a><span data-ttu-id="e400f-102">Tarea 6: Adición del origen de Excel al flujo de datos</span><span class="sxs-lookup"><span data-stu-id="e400f-102">Task 6: Adding Excel Source to the Data Flow</span></span>
  <span data-ttu-id="e400f-103">En esta tarea, agregará un origen de Excel al flujo de datos para leer datos de proveedor del archivo de Excel de origen.</span><span class="sxs-lookup"><span data-stu-id="e400f-103">In this task, you add an Excel Source to the data flow to read supplier data from the source Excel file.</span></span> <span data-ttu-id="e400f-104">El origen de Excel extrae datos de hojas de cálculo o de rangos de libros de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="e400f-104">The Excel Source extracts data from worksheets or ranges in Microsoft Excel workbooks.</span></span> <span data-ttu-id="e400f-105">Vea el tema [Origen de Excel](../integration-services/data-flow/excel-source.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="e400f-105">See [Excel Source](../integration-services/data-flow/excel-source.md) topic for more details.</span></span>

1.  <span data-ttu-id="e400f-106">Arrastrar y coloque **Origen de Excel** desde **Otros orígenes** en el **Cuadro de herramientas de SSIS** hasta la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="e400f-106">Drag-drop **Excel Source** from **Other Sources** in **SSIS Toolbox** to the **Data Flow** tab.</span></span>

2.  <span data-ttu-id="e400f-107">Haga clic con el botón secundario en **Origen de Excel** en la pestaña **Flujo de datos** y, a continuación, haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="e400f-107">Right-click on **Excel Source** in the **Data Flow** tab, and click **Rename**.</span></span>

3.  <span data-ttu-id="e400f-108">Escriba **Leer datos de proveedor de archivo de Excel** y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="e400f-108">Type **Read Supplier Data from Excel File** and press **ENTER**.</span></span>

4.  <span data-ttu-id="e400f-109">Haga doble clic en **Leer datos de proveedor de archivo de Excel** para abrir el cuadro de diálogo **Editor de origen de Excel** .</span><span class="sxs-lookup"><span data-stu-id="e400f-109">Double-click **Read Supplier Data from Excel File** to launch the **Excel Source Editor** dialog box.</span></span>

5.  <span data-ttu-id="e400f-110">En el cuadro de diálogo **Editor de origen de Excel** , haga clic en **Nuevo** para crear una conexión con Excel.</span><span class="sxs-lookup"><span data-stu-id="e400f-110">In the **Excel Source Editor** dialog box, click **New** to create an Excel connection.</span></span>

6.  <span data-ttu-id="e400f-111">En el cuadro de diálogo **Administrador de conexiones con Excel** , haga clic en **Examinar**y seleccione el archivo **Suppliers.xls** de la carpeta **EIM Tutorial** .</span><span class="sxs-lookup"><span data-stu-id="e400f-111">In the **Excel Connection Manager** dialog box, click **Browse**, and then select the **Suppliers.xls** file in the **EIM Tutorial** folder.</span></span> <span data-ttu-id="e400f-112">Confirme que **Microsoft Excel 97-2003** está seleccionado en el cuadro **Versión de Excel** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e400f-112">Confirm that **Microsoft Excel 97-2003** is selected in the **Excel Version** box and then click **OK**.</span></span>

     <span data-ttu-id="e400f-113">![Cuadro de diálogo Administrador de conexiones de Excel](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Cuadro de diálogo Administrador de conexiones de Excel")</span><span class="sxs-lookup"><span data-stu-id="e400f-113">![Excel Connection Manager Dialog Box](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Excel Connection Manager Dialog Box")</span></span>

7.  <span data-ttu-id="e400f-114">En el cuadro de diálogo **Editor de origen de Excel** , seleccione **IncomingSuppliers$** en el cuadro de lista **Nombre de la hoja de Excel** .</span><span class="sxs-lookup"><span data-stu-id="e400f-114">In the **Excel Source Editor** dialog box, select **IncomingSuppliers$** in the **Name of the Excel sheet** list box.</span></span>

     <span data-ttu-id="e400f-115">![Nombre de la hoja de Excel - Proveedores entrantes$](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Nombre de la hoja de Excel - Proveedores entrantes$")</span><span class="sxs-lookup"><span data-stu-id="e400f-115">![Name of Excel Sheet - Incoming Suppliers$](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Name of Excel Sheet - Incoming Suppliers$")</span></span>

8.  <span data-ttu-id="e400f-116">Haga clic en **Vista previa** para obtener una vista previa de los datos del archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="e400f-116">Click **Preview** to preview the data in Excel file.</span></span>

9. <span data-ttu-id="e400f-117">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e400f-117">Click **OK** to close the dialog box.</span></span>

10. <span data-ttu-id="e400f-118">Arrastre y coloque la transformación **Limpieza de DQS** de **Otras transformaciones** del **Cuadro de herramientas de SSIS** hasta la pestaña **Flujo de datos** bajo **Leer datos de proveedor de archivo de Excel**.</span><span class="sxs-lookup"><span data-stu-id="e400f-118">Drag-drop **DQS Cleansing** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Read Supplier Data from Excel File**.</span></span> <span data-ttu-id="e400f-119">La transformación Limpieza de DQS emplea Data Quality Services (DQS) para corregir datos aplicando reglas aprobadas de la base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="e400f-119">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data by applying approved rules in the knowledge base.</span></span> <span data-ttu-id="e400f-120">Esta transformación, en tiempo de ejecución, crea un proyecto de limpieza de DQS en el servidor de DQS.</span><span class="sxs-lookup"><span data-stu-id="e400f-120">This transform, at runtime, creates a DQS cleansing project on the DQS server.</span></span> <span data-ttu-id="e400f-121">Vea el tema [Transformación Limpieza de DQS](https://msdn.microsoft.com/library/ee677619.aspx) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="e400f-121">See [DQS Cleansing Transformation](https://msdn.microsoft.com/library/ee677619.aspx) topic for more details.</span></span>

## <a name="next-step"></a><span data-ttu-id="e400f-122">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="e400f-122">Next Step</span></span>

[<span data-ttu-id="e400f-123">Tarea 7: Adición de la transformación Limpieza de DQS al flujo de datos</span><span class="sxs-lookup"><span data-stu-id="e400f-123">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>](task-7-adding-dqs-cleansing-transform-to-the-data-flow.md)

### <a name="see-also"></a><span data-ttu-id="e400f-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e400f-124">See Also</span></span>

[<span data-ttu-id="e400f-125">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="e400f-125">Data Flow</span></span>](../integration-services/data-flow/data-flow.md)
