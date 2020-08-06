---
title: 'Tarea 12: agregar la transformación columna derivada para agregar las columnas requeridas por MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 98ccb271-04da-4126-9729-67e9a479aaef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a4a70dd4d288e425beb2821f6b2aaf440b1d1930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747298"
---
# <a name="task-12-adding-derived-column-transform-to-add-columns-required-by-mds"></a><span data-ttu-id="9556d-102">Tarea 12: Adición de la transformación Columna derivada para agregar las columnas necesarias en MDS</span><span class="sxs-lookup"><span data-stu-id="9556d-102">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>
  <span data-ttu-id="9556d-103">En esta tarea, agregará la transformación Columna derivada al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="9556d-103">In this task, you add the Derive Column Transform to the data flow.</span></span> <span data-ttu-id="9556d-104">Agrega dos columnas derivadas, **ImportType** y **BatchTag**, a los registros que se pasan a esta transformación.</span><span class="sxs-lookup"><span data-stu-id="9556d-104">You add two derived columns, **ImportType** and **BatchTag**, to the records passed to this transform.</span></span> <span data-ttu-id="9556d-105">Debe agregar estas columnas antes de cargar los datos en las tablas de ensayo en MDS.</span><span class="sxs-lookup"><span data-stu-id="9556d-105">You should add these columns before uploading the data to staging tables in MDS.</span></span> <span data-ttu-id="9556d-106">Son dos columnas necesarias para las tablas de ensayo en MDS.</span><span class="sxs-lookup"><span data-stu-id="9556d-106">These two are required columns for the staging tables in MDS.</span></span> <span data-ttu-id="9556d-107">Consulte [tablas de almacenamiento provisional de miembros hoja](../master-data-services/leaf-member-staging-table-master-data-services.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="9556d-107">See [Leaf Member Staging Tables](../master-data-services/leaf-member-staging-table-master-data-services.md) for more details.</span></span>  
  
1.  <span data-ttu-id="9556d-108">Arrastre y coloque la **transformación columna derivada** desde la sección **común** del **cuadro de herramientas de SSIS** hasta la pestaña flujo de **datos** .</span><span class="sxs-lookup"><span data-stu-id="9556d-108">Drag-drop **Derived Column transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="9556d-109">Haga clic con el botón secundario en transformación de **columna derivada** en la pestaña **flujo de datos** y haga clic en **cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="9556d-109">Right-click **Derived Column** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="9556d-110">Escriba **Add Columns required by MDS** y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="9556d-110">Type **Add Columns Required by MDS** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="9556d-111">Conecte **filtros duplicados** para **Agregar las columnas requeridas por MDS** mediante el conector azul.</span><span class="sxs-lookup"><span data-stu-id="9556d-111">Connect **Filter Duplicates** to **Add Columns Required by MDS** using the blue connector.</span></span> <span data-ttu-id="9556d-112">Debería ver el cuadro de diálogo **selección de entrada y salida** .</span><span class="sxs-lookup"><span data-stu-id="9556d-112">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="9556d-113">En el cuadro de diálogo **selección de salida de entrada** , seleccione **Registros únicos**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9556d-113">In the **Input Output Selection** dialog box, select **Unique Records**, and click **OK**.</span></span>  
  
     <span data-ttu-id="9556d-114">![Cuadro de diálogo Selección de entrada y salida](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Cuadro de diálogo Selección de entrada y salida")</span><span class="sxs-lookup"><span data-stu-id="9556d-114">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="9556d-115">Haga clic en **SSIS** en la barra de menús y haga clic en **variables**.</span><span class="sxs-lookup"><span data-stu-id="9556d-115">Click **SSIS** on the menu bar and click **Variables**.</span></span>  
  
6.  <span data-ttu-id="9556d-116">En la ventana **variables** , haga clic en el botón **Agregar variable** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="9556d-116">In the **Variables** window, click **Add Variable** button on the toolbar.</span></span>  
  
     <span data-ttu-id="9556d-117">![Ventana Variables de SSIS](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "Ventana Variables de SSIS")</span><span class="sxs-lookup"><span data-stu-id="9556d-117">![SSIS Variables Window](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "SSIS Variables Window")</span></span>  
  
7.  <span data-ttu-id="9556d-118">Escriba **ImportType** para el **nombre** y **2** para el **valor**.</span><span class="sxs-lookup"><span data-stu-id="9556d-118">Type **ImportType** for the **Name** and **2** for the **value**.</span></span> <span data-ttu-id="9556d-119">Debe especificar el valor 2 porque desea agregar dos miembros nuevos a una entidad en MDS.</span><span class="sxs-lookup"><span data-stu-id="9556d-119">You specify the value as 2 because you want to add new members to an entity in MDS.</span></span> <span data-ttu-id="9556d-120">Para obtener más información sobre este parámetro, consulte [tabla de almacenamiento provisional de miembros hoja](../master-data-services/leaf-member-staging-table-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9556d-120">For details about this parameter, see [Leaf Member Staging Table](../master-data-services/leaf-member-staging-table-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="9556d-121">Haga clic de nuevo en el botón **Agregar variable** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="9556d-121">Click **Add Variable** toolbar button again.</span></span>  
  
9. <span data-ttu-id="9556d-122">Escriba **BatchTag** para el **nombre**, seleccione **cadena** para el **tipo de datos**y **EIMBatch** para el **valor**.</span><span class="sxs-lookup"><span data-stu-id="9556d-122">Type **BatchTag** for the **Name**, select **String** for the **Data type**, and **EIMBatch** for the **Value**.</span></span> <span data-ttu-id="9556d-123">**BatchTag** es simplemente un nombre único para el lote que se va a enviar a MDS.</span><span class="sxs-lookup"><span data-stu-id="9556d-123">**BatchTag** is just a unique name for the batch you will be submitting to MDS.</span></span>  
  
10. <span data-ttu-id="9556d-124">En la pestaña **flujo de datos** , haga doble clic en **Agregar columnas requeridas por MDS**.</span><span class="sxs-lookup"><span data-stu-id="9556d-124">In the **Data Flow** tab, double-click **Add Columns Required by MDS**.</span></span>  
  
11. <span data-ttu-id="9556d-125">En el cuadro de diálogo **Editor de transformación columna derivada** , en el **cuadro de lista del panel inferior**, escriba **ImportType** para el nombre de la **columna derivada**.</span><span class="sxs-lookup"><span data-stu-id="9556d-125">In the **Derived Column Transformation Editor** dialog box, in the **list box in the bottom pane**, type **ImportType** for the **Derived Column Name**.</span></span>  
  
12. <span data-ttu-id="9556d-126">Expanda **variables y parámetros** en el panel superior izquierdo, arrastre y coloque **User:: ImportType** a la columna **Expression** .</span><span class="sxs-lookup"><span data-stu-id="9556d-126">Expand **Variables and Parameters** in the top-left pane, drag-drop **User::ImportType** to the **Expression** column.</span></span>  
  
     <span data-ttu-id="9556d-127">![Columna derivada, editor de transformación](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Columna derivada, editor de transformación")</span><span class="sxs-lookup"><span data-stu-id="9556d-127">![Derived Column Transformation Editor](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Derived Column Transformation Editor")</span></span>  
  
13. <span data-ttu-id="9556d-128">Escriba **BatchTag** en la siguiente fila del nombre de la **columna derivada**.</span><span class="sxs-lookup"><span data-stu-id="9556d-128">Type **BatchTag** in the next row for the **Derived Column Name**.</span></span>  
  
14. <span data-ttu-id="9556d-129">Arrastre y coloque **User:: BatchTag** desde **variables y parámetros** a la columna **Expression** .</span><span class="sxs-lookup"><span data-stu-id="9556d-129">Drag-drop **User::BatchTag** from **Variables and Parameters** to the **Expression** column.</span></span>  
  
15. <span data-ttu-id="9556d-130">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **transformación columna derivada** .</span><span class="sxs-lookup"><span data-stu-id="9556d-130">Click **OK** to close the **Derived Column Transformation** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="9556d-131">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="9556d-131">Next Step</span></span>  
 [<span data-ttu-id="9556d-132">Tarea 13: Adición del destino de OLE DB para escribir datos en la tabla de ensayo de MDS</span><span class="sxs-lookup"><span data-stu-id="9556d-132">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>](../../2014/tutorials/task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table.md)  
  
  
