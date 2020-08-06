---
title: 'Lección 11: crear particiones | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 92eb21a8-5fc4-4999-ad37-1332ce26431d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4db5edd5d47fe424ef6e6ad2a822106110209059
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662314"
---
# <a name="lesson-11-create-partitions"></a><span data-ttu-id="14839-102">Lección 11: Crear particiones</span><span class="sxs-lookup"><span data-stu-id="14839-102">Lesson 11: Create Partitions</span></span>
  <span data-ttu-id="14839-103">En esta lección, creará particiones para dividir la tabla Internet Sales en piezas lógicas más pequeñas que puedan procesarse (actualizarse) independientemente de otras particiones.</span><span class="sxs-lookup"><span data-stu-id="14839-103">In this lesson, you will create partitions to divide the Internet Sales table into smaller logical parts that can be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="14839-104">De forma predeterminada, cada tabla que se incluye en el modelo tiene una partición que incluye todas las columnas y filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="14839-104">By default, every table you include in your model has one partition which includes all of the table's columns and rows.</span></span> <span data-ttu-id="14839-105">En la tabla Internet sales, queremos dividir los datos por año. una partición para cada uno de los cinco años de la tabla.</span><span class="sxs-lookup"><span data-stu-id="14839-105">For the Internet Sales table, we want to divide the data by year; one partition for each of the table's five years.</span></span>  <span data-ttu-id="14839-106">Cada partición se podrá procesar entonces independientemente.</span><span class="sxs-lookup"><span data-stu-id="14839-106">Each partition can then be processed independently.</span></span> <span data-ttu-id="14839-107">Para obtener más información, consulte [Particiones &#40;SSAS tabular&#41;](tabular-models/partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="14839-107">To learn more, see [Partitions &#40;SSAS Tabular&#41;](tabular-models/partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="14839-108">Tiempo estimado para completar esta lección: **15 minutos**</span><span class="sxs-lookup"><span data-stu-id="14839-108">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="14839-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="14839-109">Prerequisites</span></span>  
 <span data-ttu-id="14839-110">Este tema forma parte de un tutorial de modelado tabular, que se debe completar en orden.</span><span class="sxs-lookup"><span data-stu-id="14839-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="14839-111">Antes de realizar las tareas de esta lección, debe haber completado la lección anterior: [Lección 10: Crear jerarquías](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="14839-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
## <a name="create-partitions"></a><span data-ttu-id="14839-112">Crear particiones</span><span class="sxs-lookup"><span data-stu-id="14839-112">Create Partitions</span></span>  
  
#### <a name="to-create-partitions-in-the-internet-sales-table"></a><span data-ttu-id="14839-113">Para crear particiones en la tabla Internet Sales</span><span class="sxs-lookup"><span data-stu-id="14839-113">To create partitions in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="14839-114">En el diseñador de modelos, haga clic en la tabla **Internet Sales** , haga clic en el menú **Tabla** y luego en **Particiones**.</span><span class="sxs-lookup"><span data-stu-id="14839-114">In the model designer, click on the **Internet Sales** table, then click on the **Table** menu, and then click **Partitions**.</span></span>  
  
     <span data-ttu-id="14839-115">Se abrirá el cuadro de diálogo **Administrador de partición** .</span><span class="sxs-lookup"><span data-stu-id="14839-115">The **Partition Manager** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="14839-116">En el cuadro de diálogo **Administrador de particiones** , en **particiones**, haga clic en la partición **Internet sales** .</span><span class="sxs-lookup"><span data-stu-id="14839-116">In the **Partition Manager** dialog box, in **Partitions**, click the **Internet Sales** partition.</span></span>  
  
3.  <span data-ttu-id="14839-117">En **nombre de partición**, cambie el nombre a `Internet Sales 2005` .</span><span class="sxs-lookup"><span data-stu-id="14839-117">In **Partition Name**, change the name to `Internet Sales 2005`.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="14839-118">Antes de continuar con el paso siguiente, observe que los nombres de columna de la ventana Vista previa de la tabla muestran las columnas incluidas (activadas) en la tabla del modelo con los nombres de columna del origen.</span><span class="sxs-lookup"><span data-stu-id="14839-118">Before continuing to the next step, notice the column names in the Table Preview window display those columns included in the model table (checked) with the column names from the source.</span></span> <span data-ttu-id="14839-119">Esto es porque la ventana Vista previa de la tabla muestra las columnas de la tabla de origen, no de la tabla del modelo.</span><span class="sxs-lookup"><span data-stu-id="14839-119">This is because the Table Preview window displays columns from the source table, not from the model table.</span></span>  
  
4.  <span data-ttu-id="14839-120">Seleccione el botón **Editor de consultas** situado sobre el margen derecho de la ventana de vista previa.</span><span class="sxs-lookup"><span data-stu-id="14839-120">Select the **Query Editor** button just above the right side of the preview window.</span></span>  
  
     <span data-ttu-id="14839-121">Como desea que la partición solo incluya las filas de un determinado período, debe incluir una cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="14839-121">Because you want the partition to include only those rows within a certain period, you must include a WHERE clause.</span></span> <span data-ttu-id="14839-122">Solo puede crear una cláusula WHERE usando una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="14839-122">You can only create a WHERE clause by using a SQL Statement.</span></span>  
  
5.  <span data-ttu-id="14839-123">En el campo **Instrucción SQL** , pegue la instrucción siguiente para reemplazar la instrucción existente:</span><span class="sxs-lookup"><span data-stu-id="14839-123">In the **SQL Statement** field, replace the existing statement by pasting in the following statement:</span></span>  
  
    ```  
    SELECT   
    [dbo].[FactInternetSales].[ProductKey],  
    [dbo].[FactInternetSales].[CustomerKey],  
    [dbo].[FactInternetSales].[PromotionKey],  
    [dbo].[FactInternetSales].[CurrencyKey],  
    [dbo].[FactInternetSales].[SalesTerritoryKey],  
    [dbo].[FactInternetSales].[SalesOrderNumber],  
    [dbo].[FactInternetSales].[SalesOrderLineNumber],  
    [dbo].[FactInternetSales].[RevisionNumber],  
    [dbo].[FactInternetSales].[OrderQuantity],  
    [dbo].[FactInternetSales].[UnitPrice],  
    [dbo].[FactInternetSales].[ExtendedAmount],  
    [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
    [dbo].[FactInternetSales].[DiscountAmount],  
    [dbo].[FactInternetSales].[ProductStandardCost],  
    [dbo].[FactInternetSales].[TotalProductCost],  
    [dbo].[FactInternetSales].[SalesAmount],  
    [dbo].[FactInternetSales].[TaxAmt],  
    [dbo].[FactInternetSales].[Freight],  
    [dbo].[FactInternetSales].[CarrierTrackingNumber],  
    [dbo].[FactInternetSales].[CustomerPONumber],  
    [dbo].[FactInternetSales].[OrderDate],  
    [dbo].[FactInternetSales].[DueDate],  
    [dbo].[FactInternetSales].[ShipDate]   
    FROM [dbo].[FactInternetSales]  
    WHERE (([OrderDate] >= N'2005-01-01 00:00:00') AND ([OrderDate] < N'2006-01-01 00:00:00'))  
    ```  
  
     <span data-ttu-id="14839-124">Esta instrucción especifica que la partición debe incluir todos los datos de las filas en las que OrderDate corresponda al año del calendario 2005, tal como se especifica en la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="14839-124">This statement specifies the partition should include all of the data in those rows where the OrderDate is for the 2005 calendar year as specified in the WHERE clause.</span></span>  
  
6.  <span data-ttu-id="14839-125">Haga clic en **Validar**.</span><span class="sxs-lookup"><span data-stu-id="14839-125">Click **Validate**.</span></span>  
  
     <span data-ttu-id="14839-126">Observe que se muestra una advertencia en la que se indica que algunas columnas no existen en el origen.</span><span class="sxs-lookup"><span data-stu-id="14839-126">Notice a warning is displayed stating that certain columns are not present in source.</span></span> <span data-ttu-id="14839-127">Esto se debe a que en la [Lección 3: cambiar el nombre](rename-columns.md)de las columnas, ha cambiado el nombre de las columnas de la tabla Internet sales del modelo para que sean diferentes de las mismas columnas en el origen.</span><span class="sxs-lookup"><span data-stu-id="14839-127">This is because in [Lesson 3: Rename Columns](rename-columns.md), you renamed those columns in the Internet Sales table in the model to be different from those same columns at the source.</span></span>  
  
#### <a name="to-create-a-partition-for-the-2006-year-in-the-internet-sales-table"></a><span data-ttu-id="14839-128">Para crear una partición para el año 2006 en la tabla ventas por Internet</span><span class="sxs-lookup"><span data-stu-id="14839-128">To create a partition for the 2006 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="14839-129">En el cuadro de diálogo **Administrador de particiones** , en **particiones**, haga clic en la `Internet Sales 2005` partición que acaba de crear y, a continuación, **copie**.</span><span class="sxs-lookup"><span data-stu-id="14839-129">In the **Partition Manager** dialog box, in **Partitions**, click the `Internet Sales 2005` partition you just created, and then **Copy**.</span></span>  
  
2.  <span data-ttu-id="14839-130">En **nombre de partición**, escriba `Internet Sales 2006` .</span><span class="sxs-lookup"><span data-stu-id="14839-130">In **Partition Name**, type `Internet Sales 2006`.</span></span>  
  
3.  <span data-ttu-id="14839-131">En la instrucción SQL, para que la partición incluya solo las filas del año 2006, reemplace la cláusula WHERE por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="14839-131">In the SQL Statement, in-order for the partition to include only those rows for the 2006 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2006-01-01 00:00:00') AND ([OrderDate] < N'2007-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2007-year-in-the-internet-sales-table"></a><span data-ttu-id="14839-132">Para crear una partición para el año 2007 en la tabla ventas por Internet</span><span class="sxs-lookup"><span data-stu-id="14839-132">To create a partition for the 2007 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="14839-133">En el cuadro de diálogo **Administrador de partición** , haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="14839-133">In the **Partition Manager** dialog box, click **Copy**.</span></span>  
  
2.  <span data-ttu-id="14839-134">En **nombre de partición**, escriba `Internet Sales 2007` .</span><span class="sxs-lookup"><span data-stu-id="14839-134">In **Partition Name**, type `Internet Sales 2007`.</span></span>  
  
3.  <span data-ttu-id="14839-135">En **cambiar a**, seleccione **Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="14839-135">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="14839-136">En la instrucción SQL, para que la partición incluya solo las filas del año 2007, reemplace la cláusula WHERE por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="14839-136">In the SQL Statement, in-order for the partition to include only those rows for the 2007 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2007-01-01 00:00:00') AND ([OrderDate] < N'2008-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2008-year-in-the-internet-sales-table"></a><span data-ttu-id="14839-137">Para crear una partición para el año 2008 en la tabla ventas por Internet</span><span class="sxs-lookup"><span data-stu-id="14839-137">To create a partition for the 2008 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="14839-138">En el cuadro de diálogo **Administrador de partición** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="14839-138">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="14839-139">En **nombre de partición**, escriba `Internet Sales 2008` .</span><span class="sxs-lookup"><span data-stu-id="14839-139">In **Partition Name**, type `Internet Sales 2008`.</span></span>  
  
3.  <span data-ttu-id="14839-140">En **cambiar a**, seleccione **Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="14839-140">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="14839-141">En la instrucción SQL, para que la partición incluya solo las filas del año 2008, reemplace la cláusula WHERE por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="14839-141">In the SQL Statement, in-order for the partition to include only those rows for the 2008 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2008-01-01 00:00:00') AND ([OrderDate] < N'2009-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2009-year-in-the-internet-sales-table"></a><span data-ttu-id="14839-142">Para crear una partición para el año 2009 en la tabla Internet Sales</span><span class="sxs-lookup"><span data-stu-id="14839-142">To create a partition for the 2009 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="14839-143">En el cuadro de diálogo **Administrador de partición** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="14839-143">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="14839-144">En **nombre de partición**, escriba `Internet Sales 2009` .</span><span class="sxs-lookup"><span data-stu-id="14839-144">In **Partition Name**, type `Internet Sales 2009`.</span></span>  
  
3.  <span data-ttu-id="14839-145">En **cambiar a**, seleccione **Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="14839-145">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="14839-146">En la instrucción SQL, para que la partición incluya solamente las filas del año 2009, reemplace la cláusula WHERE por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="14839-146">In the SQL Statement, in-order for the partition to include only those rows for the 2009 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2009-01-01 00:00:00') AND ([OrderDate] < N'2010-01-01 00:00:00'))  
    ```  
  
## <a name="process-partitions"></a><span data-ttu-id="14839-147">Procesar particiones</span><span class="sxs-lookup"><span data-stu-id="14839-147">Process Partitions</span></span>  
 <span data-ttu-id="14839-148">En el cuadro de diálogo **Administrador de partición** , observe el asterisco (**\***) situado junto a los nombres de particiones de cada una de las nuevas particiones que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="14839-148">In the **Partition Manager** dialog box, notice the asterisk (**\***) next to the partition names for each of the new partitions you just created.</span></span> <span data-ttu-id="14839-149">Este asterisco indica que la partición no se ha procesado (actualizado).</span><span class="sxs-lookup"><span data-stu-id="14839-149">This indicates that the partition has not been processed (refreshed).</span></span> <span data-ttu-id="14839-150">Cuando crea nuevas particiones, debe ejecutar una operación Procesar particiones o Procesar tabla para actualizar los datos de esas particiones.</span><span class="sxs-lookup"><span data-stu-id="14839-150">When you create new partitions, you should run a Process Partitions or Process Table operation to refresh the data in those partitions.</span></span>  
  
#### <a name="to-process-internet-sales-partitions"></a><span data-ttu-id="14839-151">Para procesar particiones de Internet Sales</span><span class="sxs-lookup"><span data-stu-id="14839-151">To process Internet Sales partitions</span></span>  
  
1.  <span data-ttu-id="14839-152">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Administrador de partición** .</span><span class="sxs-lookup"><span data-stu-id="14839-152">Click **OK** to close the **Partition Manager** dialog box.</span></span>  
  
2.  <span data-ttu-id="14839-153">En el diseñador de modelos, haga clic en la tabla **Internet Sales** , después haga clic en el menú **Modelo** , elija **Procesar** (actualizar) y, después, haga clic en **Procesar las particiones**.</span><span class="sxs-lookup"><span data-stu-id="14839-153">In the model designer, click the **Internet Sales** table, then click the **Model** menu, then point to **Process** (Refresh), and then click **Process Partitions**.</span></span>  
  
3.  <span data-ttu-id="14839-154">En el cuadro de diálogo **Procesar las particiones** , compruebe que **Modo** está establecido en **Proceso predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="14839-154">In the **Process Partitions** dialog box, verify the **Mode** is set to **Process Default**.</span></span>  
  
4.  <span data-ttu-id="14839-155">Seleccione la casilla de la columna **Proceso** de cada una de las cinco particiones que ha creado y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="14839-155">Select the checkbox in the **Process** column for each of the five partitions you created, and then click **OK**.</span></span>  
  
     <span data-ttu-id="14839-156">Si se le piden credenciales de suplantación, especifique el nombre de usuario y la contraseña de Windows que especificó en la lección 2, paso 6.</span><span class="sxs-lookup"><span data-stu-id="14839-156">If you are prompted for Impersonation credentials, enter the Windows user name and password you specified in Lesson 2, step 6.</span></span>  
  
     <span data-ttu-id="14839-157">A continuación, aparece el cuadro de diálogo **proceso de datos** y muestra los detalles del proceso de cada partición.</span><span class="sxs-lookup"><span data-stu-id="14839-157">The **Data Process** dialog box then appears and displays process details for each partition.</span></span> <span data-ttu-id="14839-158">Observe que se ha transferido un número diferente de filas para cada partición.</span><span class="sxs-lookup"><span data-stu-id="14839-158">Notice that a different number of rows for each partition are transferred.</span></span> <span data-ttu-id="14839-159">Esto es porque cada partición incluye solamente las filas del año especificado en la cláusula WHERE de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="14839-159">This is because each partition includes only those rows for the year specified in the WHERE clause in the SQL Statement.</span></span> <span data-ttu-id="14839-160">No hay datos para el año 2010.</span><span class="sxs-lookup"><span data-stu-id="14839-160">There is no data for the 2010 year.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="14839-161">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="14839-161">Next Steps</span></span>  
 <span data-ttu-id="14839-162">Para continuar este tutorial, vaya a la lección siguiente: [Lección 12: Crear roles](lesson-11-create-roles.md).</span><span class="sxs-lookup"><span data-stu-id="14839-162">To continue this tutorial, go to the next lesson: Lesson: [Lesson 12: Create Roles](lesson-11-create-roles.md).</span></span>  
  
  
