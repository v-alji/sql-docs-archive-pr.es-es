---
title: Crear una estructura de modelo de minería de datos de destino de correo directo (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9c67f29-0c47-4a5a-862b-db0f5213c2c9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 6a27f818b29120e40248044091c78205dad945bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747321"
---
# <a name="creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial"></a><span data-ttu-id="2766c-102">Crear una estructura del modelo de minería de datos de distribución de correo directo (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="2766c-102">Creating a Targeted Mailing Mining Model Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="2766c-103">El primer paso para crear un escenario de correo directo (Targeted Mailing) consiste en usar el Asistente para minería de datos de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] con el fin de crear una estructura de minería de datos y un modelo de minería de datos de árbol de decisión.</span><span class="sxs-lookup"><span data-stu-id="2766c-103">The first step in creating a targeted mailing scenario is to use the Data Mining Wizard in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new mining structure and decision tree mining model.</span></span>  
  
 <span data-ttu-id="2766c-104">En esta tarea configurará una nueva estructura de minería de datos y agregará un modelo de minería de datos inicial basado en el [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo de árboles de decisión de.</span><span class="sxs-lookup"><span data-stu-id="2766c-104">In this task you will set up a new mining structure, and add an initial mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="2766c-105">Para crear la estructura, primero seleccionará las tablas y vistas, y a continuación identificará qué columnas se utilizarán para el entrenamiento y cuáles para pruebas.</span><span class="sxs-lookup"><span data-stu-id="2766c-105">To create the structure, you will first select tables and views and then identify which columns will be used for training and which for testing.</span></span>  
  
### <a name="to-create-a-mining-structure-for-the-targeted-mailing-scenario"></a><span data-ttu-id="2766c-106">Para crear una estructura de minería de datos para un escenario de distribución de correo directo</span><span class="sxs-lookup"><span data-stu-id="2766c-106">To create a mining structure for the targeted mailing scenario</span></span>  
  
1.  <span data-ttu-id="2766c-107">En Explorador de soluciones, haga clic con el botón secundario en **estructuras de minería** de datos y seleccione **nueva estructura de minería** de datos para iniciar el Asistente para minería de datos.</span><span class="sxs-lookup"><span data-stu-id="2766c-107">In Solution Explorer, right-click **Mining Structures** and select **New Mining Structure** to start the Data Mining Wizard.</span></span>  
  
2.  <span data-ttu-id="2766c-108">En la página de inicio del **Asistente para minería de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2766c-108">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="2766c-109">En la página **seleccionar el método de definición** , compruebe que la opción **de base de datos relacional o del almacenamiento de datos existente** está seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2766c-109">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2766c-110">En la página **crear la estructura de minería de datos** , en **¿qué técnica de minería de datos desea utilizar?**, seleccione **árboles de decisión de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="2766c-110">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Decision Trees**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2766c-111">Si aparece una advertencia de que no se puede encontrar ningún algoritmo de minería de datos, puede que las propiedades del proyecto no estén configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="2766c-111">If you get a warning that no data mining algorithms can be found, the project properties might not be configured correctly.</span></span> <span data-ttu-id="2766c-112">Esta advertencia se produce cuando el proyecto intenta recuperar una lista de algoritmos de minería de datos del servidor de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y no puede encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="2766c-112">This warning occurs when the project attempts to retrieve a list of data mining algorithms from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and cannot find the server.</span></span> <span data-ttu-id="2766c-113">De forma predeterminada, usará [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] **localhost** como servidor.</span><span class="sxs-lookup"><span data-stu-id="2766c-113">By default, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] will use **localhost** as the server.</span></span> <span data-ttu-id="2766c-114">Si está utilizando una instancia diferente o una instancia con nombre, debe cambiar las propiedades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2766c-114">If you are using a different instance, or a named instance, you must change the project properties.</span></span> <span data-ttu-id="2766c-115">Para obtener más información, vea [crear un proyecto de Analysis Services &#40;tutorial básico de minería de datos&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="2766c-115">For more information, see [Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="2766c-116">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="2766c-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="2766c-117">En la página **seleccionar vista del origen de datos** , en el panel vistas del origen de **datos disponibles** , seleccione **destinatario de correo**directo.</span><span class="sxs-lookup"><span data-stu-id="2766c-117">On the **Select Data Source View** page, in the **Available data source views** pane, select **Targeted Mailing**.</span></span> <span data-ttu-id="2766c-118">Puede hacer clic en **examinar** para ver las tablas de la vista del origen de datos y, a continuación, hacer clic en **cerrar** para volver al asistente.</span><span class="sxs-lookup"><span data-stu-id="2766c-118">You can click **Browse** to view the tables in the data source view and then click **Close** to return to the wizard.</span></span>  
  
7.  <span data-ttu-id="2766c-119">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="2766c-119">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="2766c-120">En la página **especificar tipos de tablas** , active la casilla de la columna **caso** de vTargetMail para usarla como la tabla de casos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2766c-120">On the **Specify Table Types** page, select the check box in the **Case** column for vTargetMail to use it as the case table, and then click **Next**.</span></span> <span data-ttu-id="2766c-121">Utilizará la tabla ProspectiveBuyer posteriormente para pruebas; pásela por alto por ahora.</span><span class="sxs-lookup"><span data-stu-id="2766c-121">You will use the ProspectiveBuyer table later for testing; ignore it for now.</span></span>  
  
9. <span data-ttu-id="2766c-122">En la página **especificar los datos de entrenamiento** , se identificará al menos una columna de predicción, una columna de clave y una columna de entrada para el modelo.</span><span class="sxs-lookup"><span data-stu-id="2766c-122">On the **Specify the Training Data** page, you will identify at least one predictable column, one key column, and one input column for your model.</span></span> <span data-ttu-id="2766c-123">Active la casilla de la columna de **predicción** de la fila **BikeBuyer** .</span><span class="sxs-lookup"><span data-stu-id="2766c-123">Select the check box in the **Predictable** column in the **BikeBuyer** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2766c-124">Observe la advertencia en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="2766c-124">Notice the warning at the bottom of the window.</span></span> <span data-ttu-id="2766c-125">No podrá navegar a la página siguiente hasta que seleccione al menos una **entrada** y una columna de **predicción** .</span><span class="sxs-lookup"><span data-stu-id="2766c-125">You will not be able to navigate to the next page until you select at least one **Input** and one **Predictable** column.</span></span>  
  
10. <span data-ttu-id="2766c-126">Haga clic en **sugerir** para abrir el cuadro de diálogo **sugerir columnas relacionadas** .</span><span class="sxs-lookup"><span data-stu-id="2766c-126">Click **Suggest** to open the **Suggest Related Columns** dialog box.</span></span>  
  
     <span data-ttu-id="2766c-127">El botón **sugerir** está habilitado cuando se ha seleccionado al menos un atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="2766c-127">The **Suggest** button is enabled whenever at least one predictable attribute has been selected.</span></span> <span data-ttu-id="2766c-128">En el cuadro de diálogo **sugerir columnas relacionadas** se muestran las columnas que están más estrechamente relacionadas con la columna de predicción y se ordenan los atributos por su correlación con el atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="2766c-128">The **Suggest Related Columns** dialog box lists the columns that are most closely related to the predictable column, and orders the attributes by their correlation with the predictable attribute.</span></span> <span data-ttu-id="2766c-129">Las columnas con una correlación significativa (con una confianza mayor del 95%) se seleccionan automáticamente para incluirse en el modelo.</span><span class="sxs-lookup"><span data-stu-id="2766c-129">Columns with a significant correlation (confidence greater than 95%) are automatically selected to be included in the model.</span></span>  
  
     <span data-ttu-id="2766c-130">Revise las sugerencias y, a continuación, haga clic en **Cancelar** toignore las sugerencias.</span><span class="sxs-lookup"><span data-stu-id="2766c-130">Review the suggestions, and then click **Cancel** toignore the suggestions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2766c-131">Si hace clic en **Aceptar**, todas las sugerencias de la lista se marcarán como columnas de entrada en el asistente.</span><span class="sxs-lookup"><span data-stu-id="2766c-131">If you click **OK**, all listed suggestions will be marked as input columns in the wizard.</span></span> <span data-ttu-id="2766c-132">Si está de acuerdo con solamente algunas de las sugerencias, debe cambiar los valores manualmente.</span><span class="sxs-lookup"><span data-stu-id="2766c-132">If you agree with only some of the suggestions, you must change the values manually.</span></span>  
  
11. <span data-ttu-id="2766c-133">Compruebe que la casilla de la columna de **clave** está seleccionada en la fila **CustomerKey** .</span><span class="sxs-lookup"><span data-stu-id="2766c-133">Verify that the check box in the **Key** column is selected in the **CustomerKey** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2766c-134">Si la tabla de origen de la vista del origen de datos muestra una clave, el Asistente para minería de datos elegirá automáticamente esa columna como clave para el modelo.</span><span class="sxs-lookup"><span data-stu-id="2766c-134">If the source table from the data source view indicates a key, the Data Mining Wizard automatically chooses that column as a key for the model.</span></span>  
  
12. <span data-ttu-id="2766c-135">Active las casillas de verificación de la columna de **entrada** en las filas siguientes.</span><span class="sxs-lookup"><span data-stu-id="2766c-135">Select the check boxes in the **Input** column in the following rows.</span></span> <span data-ttu-id="2766c-136">Puede activar varias columnas resaltando un rango de celdas y presionando CTRL mientras activa una casilla.</span><span class="sxs-lookup"><span data-stu-id="2766c-136">You can check multiple columns by highlighting a range of cells and pressing CTRL while selecting a check box.</span></span>  
  
    -   <span data-ttu-id="2766c-137">**Age**</span><span class="sxs-lookup"><span data-stu-id="2766c-137">**Age**</span></span>  
  
    -   <span data-ttu-id="2766c-138">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="2766c-138">**CommuteDistance**</span></span>  
  
    -   <span data-ttu-id="2766c-139">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="2766c-139">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="2766c-140">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="2766c-140">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="2766c-141">**Mujer**</span><span class="sxs-lookup"><span data-stu-id="2766c-141">**Gender**</span></span>  
  
    -   <span data-ttu-id="2766c-142">**GeographyKey**</span><span class="sxs-lookup"><span data-stu-id="2766c-142">**GeographyKey**</span></span>  
  
    -   <span data-ttu-id="2766c-143">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="2766c-143">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="2766c-144">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="2766c-144">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="2766c-145">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="2766c-145">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="2766c-146">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="2766c-146">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="2766c-147">**Región**</span><span class="sxs-lookup"><span data-stu-id="2766c-147">**Region**</span></span>  
  
    -   <span data-ttu-id="2766c-148">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="2766c-148">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="2766c-149">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="2766c-149">**YearlyIncome**</span></span>  
  
13. <span data-ttu-id="2766c-150">En la columna izquierda de la página, active las casillas de las filas siguientes.</span><span class="sxs-lookup"><span data-stu-id="2766c-150">On the far left column of the page, select the check boxes in the following rows.</span></span>  
  
    -   <span data-ttu-id="2766c-151">**AddressLine1**</span><span class="sxs-lookup"><span data-stu-id="2766c-151">**AddressLine1**</span></span>  
  
    -   <span data-ttu-id="2766c-152">**AddressLine2**</span><span class="sxs-lookup"><span data-stu-id="2766c-152">**AddressLine2**</span></span>  
  
    -   <span data-ttu-id="2766c-153">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="2766c-153">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="2766c-154">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="2766c-154">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="2766c-155">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2766c-155">**FirstName**</span></span>  
  
    -   <span data-ttu-id="2766c-156">**Apellidos**</span><span class="sxs-lookup"><span data-stu-id="2766c-156">**LastName**</span></span>  
  
     <span data-ttu-id="2766c-157">Asegúrese de que estas filas solo tienen marcas en la columna izquierda.</span><span class="sxs-lookup"><span data-stu-id="2766c-157">Ensure that these rows have checks only in the left column.</span></span> <span data-ttu-id="2766c-158">Estas columnas se agregarán a la estructura, pero no se incluirán en el modelo.</span><span class="sxs-lookup"><span data-stu-id="2766c-158">These columns will be added to your structure but will not be included in the model.</span></span> <span data-ttu-id="2766c-159">Sin embargo, una vez generado el modelo, estarán disponibles para la obtención de detalles y las pruebas.</span><span class="sxs-lookup"><span data-stu-id="2766c-159">However, after the model is built, they will be available for drillthrough and testing.</span></span> <span data-ttu-id="2766c-160">Para obtener más información sobre la obtención de detalles, vea [consultas de obtención de detalles &#40;minería de datos&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="2766c-160">For more information about drillthrough, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
14. <span data-ttu-id="2766c-161">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="2766c-161">Click **Next**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2766c-162">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="2766c-162">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2766c-163">Especificar el tipo de datos y el tipo de contenido &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2766c-163">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="2766c-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2766c-164">See Also</span></span>  
 <span data-ttu-id="2766c-165">[Especificar tipos de tablas &#40;Asistente para minería de datos&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="2766c-165">[Specify Table Types &#40;Data Mining Wizard&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="2766c-166">[Diseñador de minería de datos](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="2766c-166">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="2766c-167">Algoritmo de árboles de decisión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2766c-167">Microsoft Decision Trees Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)  
  
  
