---
title: 'Tarea 14: agregar la tarea ejecutar SQL al flujo de control para ejecutar el procedimiento almacenado para MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9a5d1b52-d505-4e6f-8a89-569329c094e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da8e80b25706c40e749fc364baeb578681e76b42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745538"
---
# <a name="task-14-adding-execute-sql-task-to-control-flow-to-run-the-stored-procedure-for-mds"></a><span data-ttu-id="63807-102">Tarea 14: Adición de la tarea Ejecutar SQL al flujo de control para ejecutar el procedimiento almacenado de MDS</span><span class="sxs-lookup"><span data-stu-id="63807-102">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>
  <span data-ttu-id="63807-103">Después de cargar datos en las tablas de ensayo de MDS, hay que ejecutar un procedimiento almacenado asociado a esa tabla para cargar los datos de las tablas de ensayo en las tablas adecuadas de la base de datos de MDS.</span><span class="sxs-lookup"><span data-stu-id="63807-103">After loading data into the staging tables of MDS, you run a stored procedure associated with that table to load the data from staging into the appropriate tables in the MDS database.</span></span> <span data-ttu-id="63807-104">Este procedimiento almacenado tiene dos parámetros requeridos que tiene que pasar: LogFlag y VersionName.</span><span class="sxs-lookup"><span data-stu-id="63807-104">This stored procedure has two required parameters that you need to pass: LogFlag and VersionName.</span></span> <span data-ttu-id="63807-105">LogFlag especifica si las transacciones se registran durante el proceso de almacenamiento provisional y VersionName representa la versión del modelo.</span><span class="sxs-lookup"><span data-stu-id="63807-105">LogFlag specifies whether transactions are logged during the staging process and VersionName represents the version of the model.</span></span> <span data-ttu-id="63807-106">Vea el tema sobre [procedimientos almacenados preconfigurados](https://msdn.microsoft.com/library/hh231028.aspx) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="63807-106">See [Staged Stored Procedure](https://msdn.microsoft.com/library/hh231028.aspx) topic for more details.</span></span>

 <span data-ttu-id="63807-107">En esta tarea, agregará la tarea Ejecutar SQL al flujo de control para invocar el procedimiento almacenado con el fin de cargar los datos almacenados provisionalmente en las tablas adecuadas de MDS.</span><span class="sxs-lookup"><span data-stu-id="63807-107">In this task, you add the Execute SQL Task to the control flow to invoke the stored procedure to load the staged data into appropriate MDS tables.</span></span>

1.  <span data-ttu-id="63807-108">Ahora, cambie a la pestaña **flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="63807-108">Now, switch to the **Control Flow** tab.</span></span>

2.  <span data-ttu-id="63807-109">Arrastre y coloque la **tarea ejecutar SQL** desde el **cuadro de herramientas de SSIS** hasta la pestaña flujo de **control** .</span><span class="sxs-lookup"><span data-stu-id="63807-109">Drag-drop **Execute SQL Task** from the **SSIS Toolbox** to the **Control Flow** tab.</span></span>

3.  <span data-ttu-id="63807-110">Haga clic con el botón secundario en **tarea ejecutar SQL** en la pestaña **flujo de control** y haga clic en **cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="63807-110">Right-click **Execute SQL Task** in the **Control Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="63807-111">Escriba **desencadenar procedimiento almacenado para cargar datos en MDS** y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="63807-111">Type **Trigger Stored Procedure to Load Data into MDS** and press **ENTER**.</span></span>

4.  <span data-ttu-id="63807-112">Conecte **Receive, cleane, Match y ajustar Supplier Data** para **desencadenar el procedimiento almacenado para cargar datos** mediante el conector verde.</span><span class="sxs-lookup"><span data-stu-id="63807-112">Connect **Receive, Cleanse, Match, and Curate Supplier Data** to **Trigger Stored Procedure to Load Data** using the green connector.</span></span>

     <span data-ttu-id="63807-113">![Conexión a tarea Ejecutar SQL](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Conexión a tarea Ejecutar SQL")</span><span class="sxs-lookup"><span data-stu-id="63807-113">![Connect to Execute SQL Task](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Connect to Execute SQL Task")</span></span>

5.  <span data-ttu-id="63807-114">Mediante la ventana **variables** , agregue dos nuevas variables con la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="63807-114">Using the **Variables** window, add two new variables with the following settings.</span></span> <span data-ttu-id="63807-115">Si no ve la ventana **variables** , haga clic en **SSIS** en la barra de menús y, a continuación, haga clic en **variables**.</span><span class="sxs-lookup"><span data-stu-id="63807-115">If you do not see the **Variables** window, click **SSIS** on the menu bar and click **Variables**.</span></span>

    |<span data-ttu-id="63807-116">Nombre</span><span class="sxs-lookup"><span data-stu-id="63807-116">Name</span></span>|<span data-ttu-id="63807-117">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="63807-117">Data Type</span></span>|<span data-ttu-id="63807-118">Value</span><span class="sxs-lookup"><span data-stu-id="63807-118">Value</span></span>|
    |----------|---------------|-----------|
    |<span data-ttu-id="63807-119">LogFlag</span><span class="sxs-lookup"><span data-stu-id="63807-119">LogFlag</span></span>|<span data-ttu-id="63807-120">Int32</span><span class="sxs-lookup"><span data-stu-id="63807-120">Int32</span></span>|<span data-ttu-id="63807-121">1</span><span class="sxs-lookup"><span data-stu-id="63807-121">1</span></span>|
    |<span data-ttu-id="63807-122">VersionName</span><span class="sxs-lookup"><span data-stu-id="63807-122">VersionName</span></span>|<span data-ttu-id="63807-123">String</span><span class="sxs-lookup"><span data-stu-id="63807-123">String</span></span>|<span data-ttu-id="63807-124">VERSION_1</span><span class="sxs-lookup"><span data-stu-id="63807-124">VERSION_1</span></span>|

     <span data-ttu-id="63807-125">![Ventana Variables de SSIS](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "Ventana Variables de SSIS")</span><span class="sxs-lookup"><span data-stu-id="63807-125">![SSIS Variables Window](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "SSIS Variables Window")</span></span>

6.  <span data-ttu-id="63807-126">Haga doble clic en **procedimiento almacenado de desencadenador para cargar datos en MDS**.</span><span class="sxs-lookup"><span data-stu-id="63807-126">Double-click **Trigger Stored Procedure to Load Data into MDS**.</span></span>

7.  <span data-ttu-id="63807-127">En el cuadro de diálogo Editor de la **tarea ejecutar SQL** , seleccione **(local). MDS** (o **localhost). MDS**) para la **conexión**.</span><span class="sxs-lookup"><span data-stu-id="63807-127">In the **Execute SQL Task Editor** dialog box, select **(local).MDS** (or **localhost.MDS**) for **Connection**.</span></span>

8.  <span data-ttu-id="63807-128">Escriba **exec [STG]. [ udp_Supplier_Leaf]?,?,?**</span><span class="sxs-lookup"><span data-stu-id="63807-128">Type **EXEC [stg].[udp_Supplier_Leaf] ?, ?, ?**</span></span> <span data-ttu-id="63807-129">**instrucción SQL**.</span><span class="sxs-lookup"><span data-stu-id="63807-129">for **SQL Statement**.</span></span> <span data-ttu-id="63807-130">Puede comprobar el nombre mediante SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="63807-130">You can verify the name by using SQL Server Management Studio.</span></span>

     <span data-ttu-id="63807-131">![Cuadro de diálogo Editor de la tarea Ejecutar SQL - Configuración general](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Cuadro de diálogo Editor de la tarea Ejecutar SQL - Configuración general")</span><span class="sxs-lookup"><span data-stu-id="63807-131">![Execute SQL Editor Dialog Box - General Settings](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Execute SQL Editor Dialog Box - General Settings")</span></span>

9. <span data-ttu-id="63807-132">Haga clic en **asignación de parámetros** en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="63807-132">Click **Parameter Mapping** from the menu on left.</span></span>

10. <span data-ttu-id="63807-133">En la página **asignación de parámetros** , haga clic en **Agregar** para agregar una asignación.</span><span class="sxs-lookup"><span data-stu-id="63807-133">In the **Parameter Mapping** page, click **Add** to add a mapping.</span></span> <span data-ttu-id="63807-134">Maximice la ventana y cambie el tamaño de las columnas de forma que pueda ver correctamente los valores de las listas desplegables.</span><span class="sxs-lookup"><span data-stu-id="63807-134">Maximize the window and resize columns so that you can see values in drop-down lists properly.</span></span>

11. <span data-ttu-id="63807-135">Seleccione **User:: VersionName** en la lista desplegable del nombre de la **variable**.</span><span class="sxs-lookup"><span data-stu-id="63807-135">Select **User::VersionName** from the drop-down list for the **Variable Name**.</span></span>

12. <span data-ttu-id="63807-136">Seleccione **nvarchar** en **tipo de datos**.</span><span class="sxs-lookup"><span data-stu-id="63807-136">Select **NVARCHAR** for **Data Type**.</span></span>

13. <span data-ttu-id="63807-137">Escriba **0** (cero) para **el nombre del parámetro**.</span><span class="sxs-lookup"><span data-stu-id="63807-137">Type **0** (zero) for **Parameter Name**.</span></span>

14. <span data-ttu-id="63807-138">Repita los cuatro pasos anteriores para agregar dos variables más.</span><span class="sxs-lookup"><span data-stu-id="63807-138">Repeat the previous four steps to add two more variables.</span></span>

    |<span data-ttu-id="63807-139">Nombre de la variable</span><span class="sxs-lookup"><span data-stu-id="63807-139">Variable Name</span></span>|<span data-ttu-id="63807-140">Tipo de datos (importante)</span><span class="sxs-lookup"><span data-stu-id="63807-140">Data Type (important)</span></span>|<span data-ttu-id="63807-141">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="63807-141">Parameter Name</span></span>|
    |-------------------|-----------------------------|--------------------|
    |<span data-ttu-id="63807-142">User::LogFlag</span><span class="sxs-lookup"><span data-stu-id="63807-142">User::LogFlag</span></span>|<span data-ttu-id="63807-143">LONG</span><span class="sxs-lookup"><span data-stu-id="63807-143">LONG</span></span>|<span data-ttu-id="63807-144">1</span><span class="sxs-lookup"><span data-stu-id="63807-144">1</span></span>|
    |<span data-ttu-id="63807-145">User::BatchTag</span><span class="sxs-lookup"><span data-stu-id="63807-145">User::BatchTag</span></span>|<span data-ttu-id="63807-146">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="63807-146">NVARCHAR</span></span>|<span data-ttu-id="63807-147">2</span><span class="sxs-lookup"><span data-stu-id="63807-147">2</span></span>|

     <span data-ttu-id="63807-148">![Editor de la tarea Ejecutar SQL - Asignación de parámetros](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Editor de la tarea Ejecutar SQL - Asignación de parámetros")</span><span class="sxs-lookup"><span data-stu-id="63807-148">![Execute SQL Task Editor - Parameter Mapping](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Execute SQL Task Editor - Parameter Mapping")</span></span>

15. <span data-ttu-id="63807-149">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Editor de ejecutar SQL** .</span><span class="sxs-lookup"><span data-stu-id="63807-149">Click **OK** to close the **Execute SQL Editor** dialog box.</span></span>

## <a name="next-step"></a><span data-ttu-id="63807-150">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="63807-150">Next Step</span></span>
 [<span data-ttu-id="63807-151">Tarea 15: Compilación y ejecución del proyecto de SSIS</span><span class="sxs-lookup"><span data-stu-id="63807-151">Task 15: Building and Running the SSIS Project</span></span>](../../2014/tutorials/task-15-building-and-running-the-ssis-project.md)


