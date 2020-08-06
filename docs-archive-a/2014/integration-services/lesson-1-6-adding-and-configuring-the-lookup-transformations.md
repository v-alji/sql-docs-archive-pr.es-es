---
title: 'Paso 6: Agregar y configurar transformaciones de búsqueda | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c59f723-9707-4407-80ae-f05f483cf65f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96b0a848508c19eb24cf1538244a39fcec57361a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673121"
---
# <a name="step-6-adding-and-configuring-the-lookup-transformations"></a><span data-ttu-id="a4fa5-102">Paso 6: Adición y configuración de transformaciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="a4fa5-102">Step 6: Adding and Configuring the Lookup Transformations</span></span>
  <span data-ttu-id="a4fa5-103">Tras configurar el origen de archivo plano para extraer datos del archivo de origen, la siguiente tarea consiste en definir las transformaciones de búsqueda necesarias para obtener los valores para las claves **CurrencyKey** y **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-103">After you have configured the Flat File source to extract data from the source file, the next task is to define the Lookup transformations needed to obtain the values for the **CurrencyKey** and **DateKey**.</span></span> <span data-ttu-id="a4fa5-104">Una transformación Búsqueda realiza una búsqueda combinando datos de la columna de entrada especificada en una columna de un conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-104">A Lookup transformation performs a lookup by joining data in the specified input column to a column in a reference dataset.</span></span> <span data-ttu-id="a4fa5-105">El conjunto de datos de referencia puede ser una tabla o una vista existente, una tabla nueva o el resultado de una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-105">The reference dataset can be an existing table or view, a new table, or the result of an SQL statement.</span></span> <span data-ttu-id="a4fa5-106">En este tutorial, la transformación Búsqueda utiliza un administrador de conexiones OLE DB para conectar con la base de datos que contiene los datos que constituyen el origen del conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-106">In this tutorial, the Lookup transformation uses an OLE DB connection manager to connect to the database that contains the data that is the source of the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4fa5-107">También puede configurar la transformación de Búsqueda para conectar con una caché que contiene el conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-107">You can also configure the Lookup transformation to connect to a cache that contains the reference dataset.</span></span> <span data-ttu-id="a4fa5-108">Para más información, consulte [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a4fa5-108">For more information, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="a4fa5-109">Para este tutorial, agregará y configurará los dos componentes de la transformación Búsqueda en el paquete:</span><span class="sxs-lookup"><span data-stu-id="a4fa5-109">For this tutorial, you will add and configure the following two Lookup transformation components to the package:</span></span>  
  
-   <span data-ttu-id="a4fa5-110">Una transformación para realizar una búsqueda de valores de la columna **CurrencyKey** de la tabla de dimensiones **DimCurrency** basada en la coincidencia de valores de la columna **CurrencyID** del archivo plano.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-110">One transformation to perform a lookup of values from the **CurrencyKey** column of the **DimCurrency** dimension table based on matching **CurrencyID** column values from the flat file.</span></span>  
  
-   <span data-ttu-id="a4fa5-111">Una transformación para realizar una búsqueda de valores de la columna **DateKey** de la tabla de dimensiones **DimDate** basada en la coincidencia de valores de la columna **CurrencyDate** del archivo plano.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-111">One transformation to perform a lookup of values from the **DateKey** column of the **DimDate** dimension table based on matching **CurrencyDate** column values from the flat file.</span></span>  
  
 <span data-ttu-id="a4fa5-112">En ambos casos, la transformación de búsqueda usará el administrador de conexiones OLE DB creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-112">In both cases, the Lookup transformation will utilize the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-lookup-currency-key-transformation"></a><span data-ttu-id="a4fa5-113">Para agregar y configurar la transformación Lookup Currency Key</span><span class="sxs-lookup"><span data-stu-id="a4fa5-113">To add and configure the Lookup Currency Key transformation</span></span>  
  
1.  <span data-ttu-id="a4fa5-114">En el **cuadro de herramientas de SSIS**, expanda **común**y arrastre **búsqueda** en la superficie de diseño de la pestaña **flujo de datos** . Coloque la búsqueda directamente debajo del origen de **datos Extract Sample Currency** .</span><span class="sxs-lookup"><span data-stu-id="a4fa5-114">In the **SSIS Toolbox**, expand **Common**, and then drag **Lookup** onto the design surface of the **Data Flow** tab. Place Lookup directly below the **Extract Sample Currency Data** source.</span></span>  
  
2.  <span data-ttu-id="a4fa5-115">Haga clic en el origen de archivo plano **Extract Sample Currency Data** y arrastre la flecha verde a la transformación **Búsqueda** que acaba de agregar para conectar los dos componentes.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-115">Click the **Extract Sample Currency Data** flat file source and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="a4fa5-116">En la superficie de diseño **Flujo de datos** , haga clic en **Búsqueda** en la transformación **Búsqueda** y cambie el nombre por **Lookup Currency Key**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-116">On the **Data Flow** design surface, click **Lookup** in the **Lookup** transformation, and change the name to **Lookup Currency Key**.</span></span>  
  
4.  <span data-ttu-id="a4fa5-117">Haga doble clic en la transformación **Lookup CurrencyKey** para mostrar el Editor de transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-117">Double-click the **Lookup CurrencyKey** transformation to display the Lookup Transformation Editor.</span></span>  
  
5.  <span data-ttu-id="a4fa5-118">En la página **General** , realice las selecciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4fa5-118">On the **General** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="a4fa5-119">Seleccione **Caché completa**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-119">Select **Full cache**.</span></span>  
  
    2.  <span data-ttu-id="a4fa5-120">En el área **Tipo de conexión** , seleccione **Administrador de conexiones OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-120">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
6.  <span data-ttu-id="a4fa5-121">En la página **Conexión** , realice las selecciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4fa5-121">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="a4fa5-122">En el cuadro de diálogo **Administrador de conexiones OLE DB** , asegúrese de que se muestra **localhost.AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="a4fa5-122">In the **OLE DB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="a4fa5-123">Seleccione **Usar los resultados de una consulta SQL**y, a continuación, escriba o copie la instrucción SQL siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4fa5-123">Select **Use results of an SQL query**, and then type or copy the following SQL statement:</span></span>  
  
        ```  
        select * from (select * from [dbo].[DimCurrency]) as refTable  
        where [refTable].[CurrencyAlternateKey] = 'ARS'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'AUD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'BRL'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CAD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CNY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'DEM'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'EUR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'FRF'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'GBP'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'JPY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'MXN'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'SAR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'USD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'VEB'  
        ```  
  
7.  <span data-ttu-id="a4fa5-124">En la página **Columnas** , realice las selecciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4fa5-124">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="a4fa5-125">En el panel **Columnas de entrada disponibles** , arrastre **CurrencyID** al panel **Columnas de búsqueda disponibles** y suéltelo en **CurrencyAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-125">In the **Available Input Columns** panel, drag **CurrencyID** to the **Available Lookup Columns** panel and drop it on **CurrencyAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="a4fa5-126">En la lista **Columnas de búsqueda disponibles** , active la casilla situada a la izquierda de **CurrencyKey**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-126">In the **Available Lookup Columns** list, select the check box to the left of **CurrencyKey**.</span></span>  
  
8.  <span data-ttu-id="a4fa5-127">Haga clic en **Aceptar** para volver a la superficie de diseño **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="a4fa5-127">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
9. <span data-ttu-id="a4fa5-128">Haga clic con el botón derecho en la transformación Lookup Currency Key y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-128">Right-click the Lookup Currency Key transformation, click **Properties**.</span></span>  
  
10. <span data-ttu-id="a4fa5-129">En el ventana Propiedades, compruebe que la `LocaleID` propiedad está establecida en **inglés (Estados Unidos)** y que la propiedad **DefaultCodePage** está establecida en **1252**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-129">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
### <a name="to-add-and-configure-the--lookup-datekey-transformation"></a><span data-ttu-id="a4fa5-130">Para agregar y configurar la transformación Lookup Date Key</span><span class="sxs-lookup"><span data-stu-id="a4fa5-130">To add and configure the  Lookup DateKey transformation</span></span>  
  
1.  <span data-ttu-id="a4fa5-131">En el **cuadro de herramientas de SSIS**, arrastre **Búsqueda** a la superficie de diseño **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="a4fa5-131">In the **SSIS Toolbox**, drag **Lookup** onto the **Data Flow** design surface.</span></span> <span data-ttu-id="a4fa5-132">Coloque Búsqueda justo debajo de la transformación **Lookup Currency Key** .</span><span class="sxs-lookup"><span data-stu-id="a4fa5-132">Place Lookup directly below the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="a4fa5-133">Haga clic en la transformación **Lookup Currency Key** y arrastre la flecha verde hasta la transformación **Búsqueda** que acaba de agregar para conectar los dos componentes.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-133">Click the **Lookup Currency Key** transformation and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="a4fa5-134">En el cuadro de diálogo **Selección de entrada y salida** , en el cuadro de lista **Salida** , haga clic en **Salida de entradas coincidentes de búsqueda** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-134">In the **Input Output Selection** dialog box, click **Lookup Match Output** in the **Output** list box, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="a4fa5-135">En la superficie de diseño **Flujo de datos** , haga clic en **Búsqueda** en la transformación **Búsqueda** recién agregada y cambie el nombre por **Lookup Date Key**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-135">On the **Data Flow** design surface, click **Lookup** in the newly added **Lookup** transformation, and change the name to **Lookup Date Key**.</span></span>  
  
5.  <span data-ttu-id="a4fa5-136">Haga doble clic en la transformación **Lookup Date Key** .</span><span class="sxs-lookup"><span data-stu-id="a4fa5-136">Double-click the **Lookup Date Key** transformation.</span></span>  
  
6.  <span data-ttu-id="a4fa5-137">En la página **General** , seleccione **Caché parcial**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-137">On the **General** page, select **Partial cache**.</span></span>  
  
7.  <span data-ttu-id="a4fa5-138">En la página **Conexión** , realice las selecciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4fa5-138">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="a4fa5-139">En el cuadro de diálogo **Administrador de conexiones OLEDB** , asegúrese de que se muestra **localhost.AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="a4fa5-139">In the **OLEDB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="a4fa5-140">En el cuadro **Usar una tabla o vista** , escriba o seleccione **[dbo].[DimDate]**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-140">In the **Use a table or view** box, type or select **[dbo].[DimDate]**.</span></span>  
  
8.  <span data-ttu-id="a4fa5-141">En la página **Columnas** , realice las selecciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4fa5-141">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="a4fa5-142">En el panel **Columnas de entrada disponibles** , arrastre **CurrencyDate** al panel **Columnas de búsqueda disponibles** y suéltelo en **FullDateAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-142">In the **Available Input Columns** panel, drag **CurrencyDate** to the **Available Lookup Columns** panel and drop it on **FullDateAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="a4fa5-143">En la lista **Columnas de búsqueda disponibles** , active la casilla situada a la izquierda de **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-143">In the **Available Lookup Columns** list, select the check box to the left of **DateKey**.</span></span>  
  
9. <span data-ttu-id="a4fa5-144">En la página **Avanzadas** , revise las opciones de almacenamiento en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-144">On the **Advanced** page, review the caching options.</span></span>  
  
10. <span data-ttu-id="a4fa5-145">Haga clic en **Aceptar** para volver a la superficie de diseño **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="a4fa5-145">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
11. <span data-ttu-id="a4fa5-146">Haga clic con el botón derecho en la transformación Lookup Date Key y haga clic en **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="a4fa5-146">Right-click the Lookup Date Key transformation and click **Properties.**</span></span>  
  
12. <span data-ttu-id="a4fa5-147">En el ventana Propiedades, compruebe que la `LocaleID` propiedad está establecida en **inglés (Estados Unidos)** y que la propiedad **DefaultCodePage** está establecida en **1252**.</span><span class="sxs-lookup"><span data-stu-id="a4fa5-147">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a4fa5-148">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="a4fa5-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a4fa5-149">Paso 7: Adición y configuración del destino de OLE DB</span><span class="sxs-lookup"><span data-stu-id="a4fa5-149">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
## <a name="see-also"></a><span data-ttu-id="a4fa5-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a4fa5-150">See Also</span></span>  
 [<span data-ttu-id="a4fa5-151">Transformación Búsqueda</span><span class="sxs-lookup"><span data-stu-id="a4fa5-151">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
