---
title: 'Tarea 13: agregar OLE DB destino para escribir datos en la tabla de ensayo de MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: e6c67fa9-bb52-44a9-82f6-d86551cf12b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77799782518a3be2441b4c461467e3132781298d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745553"
---
# <a name="task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table"></a><span data-ttu-id="08770-102">Tarea 13: Adición del destino de OLE DB para escribir datos en la tabla de ensayo de MDS</span><span class="sxs-lookup"><span data-stu-id="08770-102">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>
  <span data-ttu-id="08770-103">Ahora que ha agregado los valores de **ImportType** y **BatchTag** a todos los registros, está listo para enviarlos a MDS para el almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="08770-103">Now that you have added **ImportType** and **BatchTag** values to all records, you are ready to send them over to MDS for staging.</span></span> <span data-ttu-id="08770-104">En esta tarea, usará el destino OLE DB para escribir los datos en **STG. supplier_Leaf** tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="08770-104">In this task, you use the OLE DB Destination to write the data into **stg.supplier_Leaf** staging table.</span></span>  
  
1.  <span data-ttu-id="08770-105">Arrastre **OLE DB destino** desde la sección **otros destinos** del **cuadro de herramientas de SSIS** hasta la pestaña **flujo de datos** y colóquelo en **Agregar columnas requeridas por MDS**.</span><span class="sxs-lookup"><span data-stu-id="08770-105">Drag **OLE DB Destination** from **Other Destinations** section in the **SSIS Toolbox** to the **Data Flow** tab and drop it under **Add Columns Required by MDS**.</span></span>  
  
2.  <span data-ttu-id="08770-106">Haga clic con el botón secundario en **OLE DB destino** en la pestaña **flujo de datos** y haga clic en **cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="08770-106">Right-click **OLE DB Destination** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="08770-107">Escriba **escribir datos de proveedor en la tabla de ensayo de MDS** y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="08770-107">Type **Write Supplier Data to MDS Staging Table** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="08770-108">Conecte las **columnas Add required by MDS** para **escribir datos de proveedor en la tabla de ensayo de MDS** mediante el conector azul.</span><span class="sxs-lookup"><span data-stu-id="08770-108">Connect the **Add Columns Required by MDS** to **Write Supplier Data to MDS Staging Table** using the blue connector.</span></span>  
  
4.  <span data-ttu-id="08770-109">Haga doble clic en **escribir datos de proveedor en la tabla de ensayo de MDS** en la pestaña flujo de **datos** .</span><span class="sxs-lookup"><span data-stu-id="08770-109">Double-click **Write Supplier Data to MDS Staging Table** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="08770-110">En el cuadro de diálogo **Editor de destino de OLE DB** , asegúrese de que **(local). MDS** (o **localhost). MDS**) se selecciona para el campo **Administrador de conexiones de OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="08770-110">In the **OLE DB Destination Editor** Dialog box, make sure that **(local).MDS** (or **localhost.MDS**) is selected for the **OLE DB Connection Manager** field.</span></span>  
  
6.  <span data-ttu-id="08770-111">Seleccione **STG. Supplier_Leaf** tabla de la lista de **nombres de la tabla o la vista**.</span><span class="sxs-lookup"><span data-stu-id="08770-111">Select **stg.Supplier_Leaf** table from the list of **Name of the table or the view**.</span></span>  
  
     <span data-ttu-id="08770-112">![Editor de destino OLEDB](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "Editor de destino OLEDB")</span><span class="sxs-lookup"><span data-stu-id="08770-112">![OLEDB Destination Editor](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "OLEDB Destination Editor")</span></span>  
  
7.  <span data-ttu-id="08770-113">Cambie a la página **asignaciones** ; para ello, haga clic en **asignación** en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="08770-113">Switch to the **Mappings** page by clicking **Mapping** on the menu on left.</span></span>  
  
8.  <span data-ttu-id="08770-114">Asigne las columnas de **entrada** y de **destino** como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="08770-114">Map **input** and **destination** columns as shown in the following table.</span></span>  
  
     <span data-ttu-id="08770-115">![Editor de destino de OLEDB - Asignaciones](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "Editor de destino de OLEDB - Asignaciones")</span><span class="sxs-lookup"><span data-stu-id="08770-115">![OLEDB Destination Editor - Mappings](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "OLEDB Destination Editor - Mappings")</span></span>  
  
9. <span data-ttu-id="08770-116">Confirme que está usando **_Output** columnas para las columnas de entrada, no para las columnas de **_Status** o **_Source** .</span><span class="sxs-lookup"><span data-stu-id="08770-116">Confirm that you are using **_Output** columns for Input Columns, not the **_Status** or **_Source** columns.</span></span> <span data-ttu-id="08770-117">**_Output** columnas contienen los valores de salida de limpieza de DQS.</span><span class="sxs-lookup"><span data-stu-id="08770-117">**_Output** columns contain the output values from DQS Cleansing.</span></span>  
  
10. <span data-ttu-id="08770-118">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Editor de destino de OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="08770-118">Click **OK** to close the **OLE DB Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="08770-119">El flujo de datos debe ser similar al de la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="08770-119">The data flow should like the following image.</span></span>  
  
     <span data-ttu-id="08770-120">![Flujo de datos completado](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Flujo de datos completado")</span><span class="sxs-lookup"><span data-stu-id="08770-120">![Completed Data Flow](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Completed Data Flow")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="08770-121">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="08770-121">Next Step</span></span>  
 [<span data-ttu-id="08770-122">Tarea 14: Adición de la tarea Ejecutar SQL al flujo de control para ejecutar el procedimiento almacenado de MDS</span><span class="sxs-lookup"><span data-stu-id="08770-122">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>](../../2014/tutorials/task-14-add-execute-to-control-flow-run-mds-stored-procedure.md)  
  
  
