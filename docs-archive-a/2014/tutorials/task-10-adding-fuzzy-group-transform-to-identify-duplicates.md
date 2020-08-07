---
title: 'Tarea 10: agregar una transformación agrupación aproximada para identificar duplicados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 90b2b323-babd-464a-8914-9dc5e66aca74
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 086625197850fdfd6381e9c0a4a7deac8ce3ae45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745562"
---
# <a name="task-10-adding-fuzzy-group-transform-to-identify-duplicates"></a><span data-ttu-id="3eb53-102">Tarea 10: Adición de la transformación Agrupación aproximada para identificar duplicados</span><span class="sxs-lookup"><span data-stu-id="3eb53-102">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>
  <span data-ttu-id="3eb53-103">En esta tarea, agregará una transformación Agrupación aproximada al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="3eb53-103">In this task, you add a Fuzzy Group Transform to the data flow.</span></span> <span data-ttu-id="3eb53-104">La transformación Agrupación aproximada puede ayudar a identificar duplicados en los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="3eb53-104">The Fuzzy Group transformation can help identify duplicates in the source data.</span></span> <span data-ttu-id="3eb53-105">Vea [transformación agrupación aproximada](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="3eb53-105">See [Fuzzy Grouping Transformation](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) for more details.</span></span>  
  
1.  <span data-ttu-id="3eb53-106">Arrastre y coloque la transformación **agrupación aproximada** en **otras transformaciones** del **cuadro de herramientas de SSIS** en la pestaña flujo de **datos** en **combinar registros correctos y corregidos**.</span><span class="sxs-lookup"><span data-stu-id="3eb53-106">Drag-drop **Fuzzy Group** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Combine Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="3eb53-107">Haga clic con el botón secundario en transformación **agrupación aproximada** en la pestaña **flujo de datos** y haga clic en **cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="3eb53-107">Right-click **Fuzzy Group** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="3eb53-108">Escriba **grupos de proveedores con identificadores coincidentes** y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="3eb53-108">Type **Group Suppliers with matching IDs** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="3eb53-109">Conecte **combinar registros correctos y corregidos** para **agrupar proveedores con ID. coincidentes** mediante el conector azul.</span><span class="sxs-lookup"><span data-stu-id="3eb53-109">Connect **Combine Correct and Corrected Records** to **Group Suppliers with matching IDs** using the blue connector.</span></span>  
  
     <span data-ttu-id="3eb53-110">![Conexión a grupos de proveedores con Id. coincidentes](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Conexión a grupos de proveedores con Id. coincidentes")</span><span class="sxs-lookup"><span data-stu-id="3eb53-110">![Connection to Group Suppliers with Matching IDs](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Connection to Group Suppliers with Matching IDs")</span></span>  
  
4.  <span data-ttu-id="3eb53-111">Haga doble clic en **agrupar proveedores con identificadores coincidentes**.</span><span class="sxs-lookup"><span data-stu-id="3eb53-111">Double-click **Group Suppliers with matching IDs**.</span></span>  
  
5.  <span data-ttu-id="3eb53-112">En el **Editor de transformación agrupación aproximada**, haga clic en **nuevo** junto a **OLE DB lista** desplegable administrador de conexiones para abrir el cuadro de diálogo **configurar el administrador de conexiones OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="3eb53-112">In the **Fuzzy Group Transformation Editor**, click **New** next to **OLE DB Connection Manager drop-down list** to launch **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
6.  <span data-ttu-id="3eb53-113">En el cuadro de diálogo, haga clic en **nuevo** para iniciar el cuadro de diálogo **Administrador de conexiones** .</span><span class="sxs-lookup"><span data-stu-id="3eb53-113">In the dialog box, click **New** to launch **Connection Manager** dialog box.</span></span>  
  
7.  <span data-ttu-id="3eb53-114">Escriba **(local)** o **punto** (.) como nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="3eb53-114">Type **(local)** or **period** (.) for the Server name.</span></span>  
  
8.  <span data-ttu-id="3eb53-115">Seleccione **MDS** para **Seleccione o escriba un** campo de nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3eb53-115">Select **MDS** for **Select or enter a database name** field.</span></span> <span data-ttu-id="3eb53-116">Usará la base de datos de MDS como almacenamiento temporal para la **transformación agrupación aproximada**.</span><span class="sxs-lookup"><span data-stu-id="3eb53-116">You will use the MDS database as the temporary storage for the **Fuzzy Group Transform**.</span></span> <span data-ttu-id="3eb53-117">La transformación **agrupación aproximada** requiere una conexión a una instancia de SQL Server para crear las tablas temporales de SQL Server que requiere el algoritmo de transformación para realizar su trabajo.</span><span class="sxs-lookup"><span data-stu-id="3eb53-117">The **Fuzzy Grouping** transformation requires a connection to an instance of SQL Server to create the temporary SQL Server tables that the transformation algorithm requires to do its work.</span></span> <span data-ttu-id="3eb53-118">Puede crear una base de datos o usar otra base de datos existente con este fin.</span><span class="sxs-lookup"><span data-stu-id="3eb53-118">You can create a database or use another existing database for this purpose.</span></span>  
  
9. <span data-ttu-id="3eb53-119">Haga clic en **probar conexión** para probar la conexión y haga clic en **Aceptar** en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3eb53-119">Click **Test Connection** to test the connection and click **OK** on the message box.</span></span>  
  
10. <span data-ttu-id="3eb53-120">En el cuadro de diálogo **Administrador de conexiones** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3eb53-120">In the **Connection Manager** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="3eb53-121">Seleccione **(local). MDS** (o **localhost). MDS**) de la **lista de conexiones de datos** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3eb53-121">Select **(local).MDS** (or **localhost.MDS**) from the **list of Data Connections** and click **OK**.</span></span>  
  
12. <span data-ttu-id="3eb53-122">En el **Editor de transformación agrupación aproximada**, confirme que **(local). MDS** o **localhost. MDS** está seleccionado para el **Administrador de conexiones de OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="3eb53-122">In the **Fuzzy Grouping Transformation Editor**, confirm that **(local).MDS** or **localhost.MDS** is selected for the **OLE DB Connection Manager**.</span></span>  
  
13. <span data-ttu-id="3eb53-123">Cambie a la pestaña **columnas** .</span><span class="sxs-lookup"><span data-stu-id="3eb53-123">Switch to the **Columns** tab.</span></span>  
  
14. <span data-ttu-id="3eb53-124">Active (casilla) **SupplierID_Output** de la lista de **columnas de entrada disponibles**.</span><span class="sxs-lookup"><span data-stu-id="3eb53-124">Select (check box) **SupplierID_Output** from the list of **Available Input Columns**.</span></span> <span data-ttu-id="3eb53-125">Para configurar la transformación, seleccione las columnas de entrada que se usarán al identificar duplicados.</span><span class="sxs-lookup"><span data-stu-id="3eb53-125">To configure the transformation, select the input columns to use when identifying duplicates.</span></span> <span data-ttu-id="3eb53-126">Por simplificar, use solo la columna SupplierID en este paso.</span><span class="sxs-lookup"><span data-stu-id="3eb53-126">To keep it simple, you only use the SupplierID in this step.</span></span>  
  
     <span data-ttu-id="3eb53-127">![Agrupación aproximada, editor de transformación](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Agrupación aproximada, editor de transformación")</span><span class="sxs-lookup"><span data-stu-id="3eb53-127">![Fuzzy Grouping Transformation Editor](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Fuzzy Grouping Transformation Editor")</span></span>  
  
15. <span data-ttu-id="3eb53-128">Haga clic en **Aceptar** para cerrar el **Editor de transformación agrupación aproximada**.</span><span class="sxs-lookup"><span data-stu-id="3eb53-128">Click **OK** to close the **Fuzzy Group Transformation Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="3eb53-129">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="3eb53-129">Next Step</span></span>  
 [<span data-ttu-id="3eb53-130">Tarea 11: Adición de la transformación División condicional para filtrar duplicados</span><span class="sxs-lookup"><span data-stu-id="3eb53-130">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>](../../2014/tutorials/task-11-adding-conditional-split-transform-to-filter-duplicates.md)  
  
  
