---
title: Plantillas DMX | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a577e52-821d-4bd3-ba35-075a6be285c9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79c8615933baf4fa3d80974daae91b4d1c7fa101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676247"
---
# <a name="dmx-templates"></a><span data-ttu-id="31c5f-102">Plantillas DMX</span><span class="sxs-lookup"><span data-stu-id="31c5f-102">DMX Templates</span></span>
  <span data-ttu-id="31c5f-103">Las plantillas de minería de datos ayudan a crear rápidamente consultas sofisticadas.</span><span class="sxs-lookup"><span data-stu-id="31c5f-103">The data mining templates help you quickly build sophisticated queries.</span></span> <span data-ttu-id="31c5f-104">Aunque la sintaxis general de las consultas DMX está bien documentada, el uso de plantillas facilita la creación de consultas haciendo clic y apuntando a los argumentos y orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="31c5f-104">Although the general syntax for DMX queries is well documented, using the templates makes it easier to build queries by clicking and pointing to arguments and data sources.</span></span>  
  
## <a name="using-the-templates"></a><span data-ttu-id="31c5f-105">Usar las plantillas</span><span class="sxs-lookup"><span data-stu-id="31c5f-105">Using the Templates</span></span>  
  
1.  <span data-ttu-id="31c5f-106">En el cliente de minería de datos para Excel, haga clic en **consulta**.</span><span class="sxs-lookup"><span data-stu-id="31c5f-106">In the Data Mining Client for Excel, click **Query**.</span></span>  
  
2.  <span data-ttu-id="31c5f-107">En la página **Inicio** del asistente, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="31c5f-107">On the wizard **Start** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="31c5f-108">En la página, **Seleccione modelo**y haga clic en **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="31c5f-108">On the page, **Select Model**, click **Advanced**.</span></span>  
  
     <span data-ttu-id="31c5f-109">**Sugerencia:** Si va a crear una consulta de predicción en un modelo, puede seleccionar primero el modelo y, a continuación, hacer clic en **avanzadas**, para rellenar previamente la plantilla con el nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="31c5f-109">**Tip:** If you are going to create a prediction query on a model, you can select the model first, and then click **Advanced**, to prepopulate the template with the model name.</span></span>  
  
4.  <span data-ttu-id="31c5f-110">En el **Editor de consultas avanzadas de minería de datos**, haga clic en **plantillas DMX**y seleccione una plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c5f-110">In the **Data Mining Advanced Query Editor**, click **DMX Templates**, and select a template.</span></span>  
  
5.  <span data-ttu-id="31c5f-111">Presione ENTRAR para cargar la plantilla en el panel Consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="31c5f-111">Press ENTER to load the template into the DMX Query pane.</span></span>  
  
6.  <span data-ttu-id="31c5f-112">Siga haciendo clic en los vínculos de la plantilla y en cuanto aparezca el cuadro de diálogo, seleccione una salida, un modelo o un parámetro adecuado.</span><span class="sxs-lookup"><span data-stu-id="31c5f-112">Continue clicking the links in the template, and as the dialog box appears, select an appropriate output, model, or parameter.</span></span>  
  
     <span data-ttu-id="31c5f-113">Para las consultas de predicción, elija el conjunto de datos de entrada primero y asigne después las columnas.</span><span class="sxs-lookup"><span data-stu-id="31c5f-113">For prediction queries, choose the input dataset first, and then map the columns.</span></span>  
  
7.  <span data-ttu-id="31c5f-114">Haga clic en **Editar consulta** para cambiar a la vista del editor de texto y cambiar manualmente la consulta.</span><span class="sxs-lookup"><span data-stu-id="31c5f-114">Click **Edit Query** to switch to text editor view and manually change the query.</span></span>  
  
     <span data-ttu-id="31c5f-115">Sin embargo, tenga en cuenta que si cambia las vistas al trabajar en el editor de consultas, se borrará cualquier información que tuviera en la vista anterior.</span><span class="sxs-lookup"><span data-stu-id="31c5f-115">Be aware, however, that if you switch views when working in the query editor, any information that you had in the previous view will be cleared.</span></span> <span data-ttu-id="31c5f-116">Antes de cambiar de vista, guarde el trabajo; para ello, copie y pegue las instrucciones DMX en un archivo independiente.</span><span class="sxs-lookup"><span data-stu-id="31c5f-116">Before changing views, save your work by copying and pasting the DMX statements to a separate file.</span></span>  
  
8.  <span data-ttu-id="31c5f-117">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="31c5f-117">Click **Finish**.</span></span> <span data-ttu-id="31c5f-118">En el cuadro de diálogo **elegir destino** , especifique dónde desea que se guarde el resultado.</span><span class="sxs-lookup"><span data-stu-id="31c5f-118">In the **Choose Destination** dialog  box, specify where you want the result saved.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="31c5f-119">Si ha ejecutado una instrucción correctamente, la instrucción DMX que envió al servidor también se registra en la ventana de **seguimiento** .</span><span class="sxs-lookup"><span data-stu-id="31c5f-119">If you executed a statement successfully, the DMX statement that you sent to the server is also recorded in the **Trace** window.</span></span> <span data-ttu-id="31c5f-120">Para obtener más información sobre cómo usar la característica de seguimiento, vea [seguimiento &#40;cliente de minería de datos para Excel&#41;](trace-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="31c5f-120">For more information about how to use the Trace feature, see [Trace &#40;Data Mining Client for Excel&#41;](trace-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="31c5f-121">Para obtener más información sobre cómo usar el editor de consultas avanzadas de minería de datos, vea [&#40;de consultas SQL Server complementos de minería de datos&#41;](query-sql-server-data-mining-add-ins.md) y [Editor de consultas avanzadas de minería de datos](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="31c5f-121">For more information about how to use the Data Mining Advanced Query Editor, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) and [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="list-of-dmx-templates"></a><span data-ttu-id="31c5f-122">Lista de plantillas DMX</span><span class="sxs-lookup"><span data-stu-id="31c5f-122">List of DMX Templates</span></span>  
 <span data-ttu-id="31c5f-123">En el Cliente de minería de datos para Excel se incluyen las siguientes plantillas DMX.</span><span class="sxs-lookup"><span data-stu-id="31c5f-123">The following DMX templates are included in the Data Mining Client for Excel.</span></span>  
  
 <span data-ttu-id="31c5f-124">**Predicción**</span><span class="sxs-lookup"><span data-stu-id="31c5f-124">**Prediction**</span></span>  
  
 <span data-ttu-id="31c5f-125">Use estas plantillas para crear consultas de predicción avanzadas, incluidas las consultas no admitidas por los asistentes de los complementos, como consultas que usan tablas anidadas u orígenes de datos externos.</span><span class="sxs-lookup"><span data-stu-id="31c5f-125">Use these templates to create advanced prediction queries, including queries not supported by the wizards in the add-ins, such as queries that use nested tables or external data sources.</span></span>  
  
-   <span data-ttu-id="31c5f-126">Predicciones filtradas</span><span class="sxs-lookup"><span data-stu-id="31c5f-126">Filtered predictions</span></span>  
  
-   <span data-ttu-id="31c5f-127">Predicciones anidadas y filtradas</span><span class="sxs-lookup"><span data-stu-id="31c5f-127">Filtered nested predictions</span></span>  
  
-   <span data-ttu-id="31c5f-128">Predicciones anidadas</span><span class="sxs-lookup"><span data-stu-id="31c5f-128">Nested predictions</span></span>  
  
-   <span data-ttu-id="31c5f-129">Predicción de singleton</span><span class="sxs-lookup"><span data-stu-id="31c5f-129">Singleton predictions</span></span>  
  
-   <span data-ttu-id="31c5f-130">Predicciones estándar</span><span class="sxs-lookup"><span data-stu-id="31c5f-130">Standard predictions</span></span>  
  
-   <span data-ttu-id="31c5f-131">Predicciones de series temporales</span><span class="sxs-lookup"><span data-stu-id="31c5f-131">Time series predictions</span></span>  
  
-   <span data-ttu-id="31c5f-132">Consulta de predicción TOP</span><span class="sxs-lookup"><span data-stu-id="31c5f-132">TOP prediction query</span></span>  
  
-   <span data-ttu-id="31c5f-133">Consulta de predicción TOP en tabla anidada</span><span class="sxs-lookup"><span data-stu-id="31c5f-133">TOP prediction query on nested table</span></span>  
  
 <span data-ttu-id="31c5f-134">**Creación**</span><span class="sxs-lookup"><span data-stu-id="31c5f-134">**Create**</span></span>  
  
 <span data-ttu-id="31c5f-135">Use estas plantillas para crear modelos o estructuras de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="31c5f-135">Use these templates to build custom models or data structures.</span></span> <span data-ttu-id="31c5f-136">No está limitado a los modelos que admiten los asistentes: puede usar cualquier algoritmo de minería de datos admitido por la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a la que está conectado, incluidos los algoritmos de complemento.</span><span class="sxs-lookup"><span data-stu-id="31c5f-136">You are not limited to the models supported by the wizards - you can use any data mining algorithm supported by the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you are connected to, including plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="31c5f-137">Modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="31c5f-137">Mining model</span></span>  
  
-   <span data-ttu-id="31c5f-138">Estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="31c5f-138">Mining structure</span></span>  
  
-   <span data-ttu-id="31c5f-139">Estructura de minería con datos de exclusión</span><span class="sxs-lookup"><span data-stu-id="31c5f-139">Mining structure with holdout</span></span>  
  
-   <span data-ttu-id="31c5f-140">Modelo temporal</span><span class="sxs-lookup"><span data-stu-id="31c5f-140">Temporary model</span></span>  
  
-   <span data-ttu-id="31c5f-141">Estructura temporal</span><span class="sxs-lookup"><span data-stu-id="31c5f-141">Temporary structure</span></span>  
  
 <span data-ttu-id="31c5f-142">**Propiedades del modelo**</span><span class="sxs-lookup"><span data-stu-id="31c5f-142">**Model Properties**</span></span>  
  
 <span data-ttu-id="31c5f-143">Use estas plantillas para crear consultas que obtienen metadatos sobre el modelo y el conjunto de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="31c5f-143">Use these templates to create queries that get metadata about the model and the training set.</span></span> <span data-ttu-id="31c5f-144">También puede recuperar detalles del contenido del modelo u obtener un perfil estadístico de los datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="31c5f-144">You can also retrieve details from the model content, or get a statistical profile of the training data.</span></span>  
  
-   <span data-ttu-id="31c5f-145">Contenido del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="31c5f-145">Mining model content</span></span>  
  
-   <span data-ttu-id="31c5f-146">Valores de columna mínimos y máximos</span><span class="sxs-lookup"><span data-stu-id="31c5f-146">Minimum and maximum column values</span></span>  
  
-   <span data-ttu-id="31c5f-147">Casos de prueba/entrenamiento de estructura de minería</span><span class="sxs-lookup"><span data-stu-id="31c5f-147">Mining structure test/training cases</span></span>  
  
-   <span data-ttu-id="31c5f-148">Valores de columna discreta</span><span class="sxs-lookup"><span data-stu-id="31c5f-148">Discrete column values</span></span>  
  
 <span data-ttu-id="31c5f-149">**Administración**</span><span class="sxs-lookup"><span data-stu-id="31c5f-149">**Management**</span></span>  
  
 <span data-ttu-id="31c5f-150">Use estas plantillas para realizar cualquier tarea de administración admitida por DMX, lo que incluye importar y exportar modelos, eliminar modelos y borrar modelos o estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="31c5f-150">Use these templates to perform any management task supported by DMX, which includes importing and exporting models, deleting models, and clearing models or data structures.</span></span>  
  
-   <span data-ttu-id="31c5f-151">Borrar modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="31c5f-151">Clear mining model</span></span>  
  
-   <span data-ttu-id="31c5f-152">Borrar estructura y modelos</span><span class="sxs-lookup"><span data-stu-id="31c5f-152">Clear structure and models</span></span>  
  
-   <span data-ttu-id="31c5f-153">Borrar estructura de minería</span><span class="sxs-lookup"><span data-stu-id="31c5f-153">Clear mining structure</span></span>  
  
-   <span data-ttu-id="31c5f-154">Eliminar modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="31c5f-154">Delete mining model</span></span>  
  
-   <span data-ttu-id="31c5f-155">Eliminar estructura de minería</span><span class="sxs-lookup"><span data-stu-id="31c5f-155">Delete mining structure</span></span>  
  
-   <span data-ttu-id="31c5f-156">Cambiar nombre del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="31c5f-156">Rename mining model</span></span>  
  
-   <span data-ttu-id="31c5f-157">Cambiar nombre de la estructura de minería</span><span class="sxs-lookup"><span data-stu-id="31c5f-157">Rename mining structure</span></span>  
  
-   <span data-ttu-id="31c5f-158">Entrenar modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="31c5f-158">Train mining model</span></span>  
  
-   <span data-ttu-id="31c5f-159">Entrenar estructura de minería anidada</span><span class="sxs-lookup"><span data-stu-id="31c5f-159">Train nested mining structure</span></span>  
  
-   <span data-ttu-id="31c5f-160">Entrenar estructura de minería</span><span class="sxs-lookup"><span data-stu-id="31c5f-160">Train mining structure</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="31c5f-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31c5f-161">Requirements</span></span>  
 <span data-ttu-id="31c5f-162">Dependiendo de la plantilla que esté utilizando, es posible que necesite permisos administrativos para tener acceso al servidor de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="31c5f-162">Depending on which template you are using, you might need administrative permissions to access the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c5f-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31c5f-163">See Also</span></span>  
 [<span data-ttu-id="31c5f-164">Crear un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="31c5f-164">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
