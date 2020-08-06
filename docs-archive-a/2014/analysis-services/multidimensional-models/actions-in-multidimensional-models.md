---
title: Acciones en modelos multidimensionales | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- actions [Analysis Services], creating
- report actions [Analysis Services]
- drillthrough actions [Analysis Services]
- cubes [Analysis Services], actions
ms.assetid: b9fee2b9-05a5-4077-848d-d8457326dc27
author: minewiskan
ms.author: owend
ms.openlocfilehash: ce42907190363be085e8f4d8e9adfbab52a70590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671754"
---
# <a name="actions-in-multidimensional-models"></a><span data-ttu-id="79aa2-102">Acciones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="79aa2-102">Actions in Multidimensional Models</span></span>
  <span data-ttu-id="79aa2-103">Una acción es una operación iniciada por el usuario final en un cubo seleccionado o en una parte de un cubo.</span><span class="sxs-lookup"><span data-stu-id="79aa2-103">An action is an end user-initiated operation upon a selected cube or portion of a cube.</span></span> <span data-ttu-id="79aa2-104">La operación puede iniciar una aplicación con el elemento seleccionado como parámetro o recuperar información acerca del elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="79aa2-104">The operation can start an application with the selected item as a parameter, or it can retrieve information about the selected item.</span></span> <span data-ttu-id="79aa2-105">Para más información sobre las acciones, vea [Acciones &#40;Analysis Services - Datos multidimensionales&#41;](actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="79aa2-105">For more information about actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](actions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="79aa2-106">Use la pestaña **Acciones** del Diseñador de cubos para generar acciones para un cubo.</span><span class="sxs-lookup"><span data-stu-id="79aa2-106">Use the **Actions** tab of Cube Designer to build actions for a cube.</span></span> <span data-ttu-id="79aa2-107">Especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="79aa2-107">Specify the following:</span></span>  
  
 <span data-ttu-id="79aa2-108">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="79aa2-108">**Name**</span></span>  
 <span data-ttu-id="79aa2-109">Seleccione un nombre que identifique la acción.</span><span class="sxs-lookup"><span data-stu-id="79aa2-109">Select a name that identifies the action.</span></span>  
  
 <span data-ttu-id="79aa2-110">**Destino de la acción**</span><span class="sxs-lookup"><span data-stu-id="79aa2-110">**Action Target**</span></span>  
 <span data-ttu-id="79aa2-111">Seleccione el objeto al que se adjunta la acción.</span><span class="sxs-lookup"><span data-stu-id="79aa2-111">Select the object to which the action is attached.</span></span> <span data-ttu-id="79aa2-112">Normalmente, en aplicaciones cliente, la acción se muestra cuando los usuarios finales seleccionan el objeto de destino; no obstante, la aplicación cliente determina la operación del usuario final que muestra las acciones.</span><span class="sxs-lookup"><span data-stu-id="79aa2-112">Generally, in client applications, the action is displayed when end users select the target object; however, the client application determines which end-user operation displays actions.</span></span> <span data-ttu-id="79aa2-113">En **Tipo de destino**, seleccione entre los siguientes objetos:</span><span class="sxs-lookup"><span data-stu-id="79aa2-113">For **Target type**, select from the following objects:</span></span>  
  
-   <span data-ttu-id="79aa2-114">Miembros del atributo</span><span class="sxs-lookup"><span data-stu-id="79aa2-114">Attribute members</span></span>  
  
-   <span data-ttu-id="79aa2-115">Celdas</span><span class="sxs-lookup"><span data-stu-id="79aa2-115">Cells</span></span>  
  
-   <span data-ttu-id="79aa2-116">Cubo</span><span class="sxs-lookup"><span data-stu-id="79aa2-116">Cube</span></span>  
  
-   <span data-ttu-id="79aa2-117">miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="79aa2-117">Dimension members</span></span>  
  
-   <span data-ttu-id="79aa2-118">Hierarchy</span><span class="sxs-lookup"><span data-stu-id="79aa2-118">Hierarchy</span></span>  
  
-   <span data-ttu-id="79aa2-119">Miembros de la jerarquía</span><span class="sxs-lookup"><span data-stu-id="79aa2-119">Hierarchy members</span></span>  
  
-   <span data-ttu-id="79aa2-120">Nivel</span><span class="sxs-lookup"><span data-stu-id="79aa2-120">Level</span></span>  
  
-   <span data-ttu-id="79aa2-121">Miembros del nivel</span><span class="sxs-lookup"><span data-stu-id="79aa2-121">Level members</span></span>  
  
 <span data-ttu-id="79aa2-122">Después de seleccionar el tipo de objeto de destino, en **Objeto de destino**, seleccione el objeto de cubo del tipo designado.</span><span class="sxs-lookup"><span data-stu-id="79aa2-122">After you select the target object type, under **Target object**, select the cube object of the designated type.</span></span>  
  
 <span data-ttu-id="79aa2-123">**Condición (opcional)**</span><span class="sxs-lookup"><span data-stu-id="79aa2-123">**Condition (Optional)**</span></span>  
 <span data-ttu-id="79aa2-124">Especifique una expresión opcional de Expresiones multidimensionales (MDX) que se resuelva en un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="79aa2-124">Specify an optional Multidimensional Expressions (MDX) expression that resolves to a Boolean value.</span></span> <span data-ttu-id="79aa2-125">Si el valor es `True`, la acción se realiza en el destino especificado.</span><span class="sxs-lookup"><span data-stu-id="79aa2-125">If the value is `True`, the action is performed on the specified target.</span></span> <span data-ttu-id="79aa2-126">Si el valor es `False`, la acción no se realiza.</span><span class="sxs-lookup"><span data-stu-id="79aa2-126">If the value is `False`, the action is not performed.</span></span>  
  
 <span data-ttu-id="79aa2-127">**Contenido de la acción**</span><span class="sxs-lookup"><span data-stu-id="79aa2-127">**Action Content**</span></span>  
 <span data-ttu-id="79aa2-128">Seleccione el tipo de acción.</span><span class="sxs-lookup"><span data-stu-id="79aa2-128">Select the type of action.</span></span> <span data-ttu-id="79aa2-129">La siguiente tabla contiene los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="79aa2-129">The following table summarizes the available types.</span></span>  
  
|<span data-ttu-id="79aa2-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="79aa2-130">Type</span></span>|<span data-ttu-id="79aa2-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="79aa2-131">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="79aa2-132">Conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="79aa2-132">Data Set</span></span>|<span data-ttu-id="79aa2-133">Recupera un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="79aa2-133">Retrieves a dataset.</span></span>|  
|<span data-ttu-id="79aa2-134">Propietario</span><span class="sxs-lookup"><span data-stu-id="79aa2-134">Proprietary</span></span>|<span data-ttu-id="79aa2-135">Ejecuta una operación con una interfaz que no aparece en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="79aa2-135">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="79aa2-136">Conjunto de filas</span><span class="sxs-lookup"><span data-stu-id="79aa2-136">Row Set</span></span>|<span data-ttu-id="79aa2-137">Recupera un conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="79aa2-137">Retrieves a rowset.</span></span>|  
|<span data-ttu-id="79aa2-138">Instrucción</span><span class="sxs-lookup"><span data-stu-id="79aa2-138">Statement</span></span>|<span data-ttu-id="79aa2-139">Ejecuta un comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="79aa2-139">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="79aa2-140">URL</span><span class="sxs-lookup"><span data-stu-id="79aa2-140">URL</span></span>|<span data-ttu-id="79aa2-141">Muestra una página variable en un explorador de Internet.</span><span class="sxs-lookup"><span data-stu-id="79aa2-141">Displays a variable page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="79aa2-142">En **Expresión de acción**, especifique los parámetros que se pasan cuando se ejecuta la acción.</span><span class="sxs-lookup"><span data-stu-id="79aa2-142">For **Action Expression**, specify the parameters that are passed when the action is run.</span></span> <span data-ttu-id="79aa2-143">La sintaxis se debe evaluar como una cadena, y debe incluirse una expresión escrita en MDX.</span><span class="sxs-lookup"><span data-stu-id="79aa2-143">The syntax must evaluate to a string, and you must include an expression written in MDX.</span></span> <span data-ttu-id="79aa2-144">Por ejemplo, la expresión MDX puede indicar una parte del cubo incluida en la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="79aa2-144">For example, your MDX expression can indicate a part of the cube that is included in the syntax.</span></span> <span data-ttu-id="79aa2-145">Las expresiones MDX se evalúan antes de pasar los parámetros.</span><span class="sxs-lookup"><span data-stu-id="79aa2-145">MDX expressions are evaluated before the parameters are passed.</span></span> <span data-ttu-id="79aa2-146">Además, el Generador MDX ayuda a generar expresiones MDX.</span><span class="sxs-lookup"><span data-stu-id="79aa2-146">Also, MDX Builder is available to help you build MDX expressions.</span></span>  
  
 <span data-ttu-id="79aa2-147">**Propiedades adicionales**</span><span class="sxs-lookup"><span data-stu-id="79aa2-147">**Additional Properties**</span></span>  
 <span data-ttu-id="79aa2-148">Seleccione la propiedad.</span><span class="sxs-lookup"><span data-stu-id="79aa2-148">Select the property.</span></span> <span data-ttu-id="79aa2-149">En la siguiente tabla se resumen las propiedades disponibles.</span><span class="sxs-lookup"><span data-stu-id="79aa2-149">The following table summarizes the available properties.</span></span>  
  
|<span data-ttu-id="79aa2-150">Propiedad</span><span class="sxs-lookup"><span data-stu-id="79aa2-150">Property</span></span>|<span data-ttu-id="79aa2-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="79aa2-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="79aa2-152">**Invocación**</span><span class="sxs-lookup"><span data-stu-id="79aa2-152">**Invocation**</span></span>|<span data-ttu-id="79aa2-153">Especifica cómo se ejecuta la acción.</span><span class="sxs-lookup"><span data-stu-id="79aa2-153">Specifies how the action is run.</span></span> <span data-ttu-id="79aa2-154">Interactiva, que es la opción predeterminada, especifica que la acción se ejecuta cuando un usuario tiene acceso a un objeto.</span><span class="sxs-lookup"><span data-stu-id="79aa2-154">Interactive, the default, specifies that the action is run when a user accesses an object.</span></span> <span data-ttu-id="79aa2-155">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="79aa2-155">The possible settings are:</span></span><br /><br /> <span data-ttu-id="79aa2-156">Batch</span><span class="sxs-lookup"><span data-stu-id="79aa2-156">Batch</span></span><br /><br /> <span data-ttu-id="79aa2-157">Interactive</span><span class="sxs-lookup"><span data-stu-id="79aa2-157">Interactive</span></span><br /><br /> <span data-ttu-id="79aa2-158">Al abrir</span><span class="sxs-lookup"><span data-stu-id="79aa2-158">On Open</span></span>|  
|<span data-ttu-id="79aa2-159">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="79aa2-159">**Application**</span></span>|<span data-ttu-id="79aa2-160">Describe la aplicación de la acción.</span><span class="sxs-lookup"><span data-stu-id="79aa2-160">Describes the application of the action.</span></span>|  
|<span data-ttu-id="79aa2-161">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="79aa2-161">**Description**</span></span>|<span data-ttu-id="79aa2-162">Describe la acción.</span><span class="sxs-lookup"><span data-stu-id="79aa2-162">Describes the action.</span></span>|  
|<span data-ttu-id="79aa2-163">**Caption**</span><span class="sxs-lookup"><span data-stu-id="79aa2-163">**Caption**</span></span>|<span data-ttu-id="79aa2-164">Proporciona un título que se muestra para la acción.</span><span class="sxs-lookup"><span data-stu-id="79aa2-164">Provides a caption that is displayed for the action.</span></span> <span data-ttu-id="79aa2-165">Si el título es MDX, especifique `True` para **título es MDX**.</span><span class="sxs-lookup"><span data-stu-id="79aa2-165">If the caption is MDX, specify `True` for **Caption is MDX**.</span></span>|  
|<span data-ttu-id="79aa2-166">**El título es MDX**</span><span class="sxs-lookup"><span data-stu-id="79aa2-166">**Caption is MDX**</span></span>|<span data-ttu-id="79aa2-167">Especifique `True` si el título es MDX o `False` si no lo es.</span><span class="sxs-lookup"><span data-stu-id="79aa2-167">Specify `True` if the caption is MDX or `False` if it is not.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="79aa2-168">Debe usar Lenguaje de scripting de Analysis Services (ASSL) u Objetos de administración de análisis (AMO) para definir tipos de acciones de la línea de comandos y HTML.</span><span class="sxs-lookup"><span data-stu-id="79aa2-168">You must use Analysis Services Scripting Language (ASSL) or Analysis Management Objects (AMO) to define HTML and Command Line action types.</span></span> <span data-ttu-id="79aa2-169">Para más información, vea [Elemento Action &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Elemento Type &#40;Action&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl) y [Programar objetos avanzados OLAP en AMO](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span><span class="sxs-lookup"><span data-stu-id="79aa2-169">For more information, see [Action Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Type Element &#40;Action&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl), and [Programming AMO OLAP Advanced Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span></span>  
  
## <a name="creating-a-reporting-action"></a><span data-ttu-id="79aa2-170">Crear una acción de informe</span><span class="sxs-lookup"><span data-stu-id="79aa2-170">Creating a Reporting Action</span></span>  
 <span data-ttu-id="79aa2-171">El servidor de informes responde a las solicitudes basadas en URL para los informes.</span><span class="sxs-lookup"><span data-stu-id="79aa2-171">The report server responds to URL-based requests for reports.</span></span> <span data-ttu-id="79aa2-172">Para crear una acción de informe, en el menú **Cubo** , haga clic en **Nueva acción de informe**.</span><span class="sxs-lookup"><span data-stu-id="79aa2-172">To create a reporting action, on the **Cube** menu, click **New Reporting Action**.</span></span> <span data-ttu-id="79aa2-173">Las siguientes opciones son específicas de una acción de informe.</span><span class="sxs-lookup"><span data-stu-id="79aa2-173">The following options are specific to a reporting action.</span></span>  
  
 <span data-ttu-id="79aa2-174">**Servidor de informes**</span><span class="sxs-lookup"><span data-stu-id="79aa2-174">**Report Server**</span></span>  
 <span data-ttu-id="79aa2-175">Las propiedades descritas en la siguiente tabla se especifican para el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="79aa2-175">The properties described in the following table are specified for the report server.</span></span>  
  
|<span data-ttu-id="79aa2-176">Propiedad</span><span class="sxs-lookup"><span data-stu-id="79aa2-176">Property</span></span>|<span data-ttu-id="79aa2-177">Descripción</span><span class="sxs-lookup"><span data-stu-id="79aa2-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="79aa2-178">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="79aa2-178">**Server name**</span></span>|<span data-ttu-id="79aa2-179">Nombre del equipo en el que se ejecuta el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="79aa2-179">The name of the computer running report server.</span></span>|  
|<span data-ttu-id="79aa2-180">**Ruta de acceso al servidor**</span><span class="sxs-lookup"><span data-stu-id="79aa2-180">**Server path**</span></span>|<span data-ttu-id="79aa2-181">La ruta de acceso expuesta por un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="79aa2-181">The path exposed by report server.</span></span>|  
|<span data-ttu-id="79aa2-182">**Formato de informe**</span><span class="sxs-lookup"><span data-stu-id="79aa2-182">**Report format**</span></span>|<span data-ttu-id="79aa2-183">HTML5, HTML3, Excel o PDF.</span><span class="sxs-lookup"><span data-stu-id="79aa2-183">HTML5, HTML3, Excel, or PDF.</span></span>|  
  
 <span data-ttu-id="79aa2-184">**Parámetros (opcional)**</span><span class="sxs-lookup"><span data-stu-id="79aa2-184">**Parameters (Optional)**</span></span>  
 <span data-ttu-id="79aa2-185">Los parámetros se envían al servidor como parte de la cadena URL cuando se crea la acción.</span><span class="sxs-lookup"><span data-stu-id="79aa2-185">The parameters are sent to the server as part of the URL string when the action is created.</span></span> <span data-ttu-id="79aa2-186">Incluyen **Nombre de parámetro** y **Valor de parámetro**, que es una expresión MDX.</span><span class="sxs-lookup"><span data-stu-id="79aa2-186">They include **Parameter Name** and **Parameter Value**, which is an MDX expression.</span></span>  
  
 <span data-ttu-id="79aa2-187">La URL del servidor de informes se genera de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="79aa2-187">The report server URL is constructed as follows:</span></span>  
  
```  
  
http://  
host  
/  
virtualdirectory  
/Path&  
parametername1  
=  
parametervalue1  
& ...  
```  
  
 <span data-ttu-id="79aa2-188">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="79aa2-188">For example:</span></span>  
  
```  
http://localhost/ReportServer/Sales/YearlySalesByCategory?rs:Command=Render&Region=West  
```  
  
## <a name="creating-a-drillthrough-action"></a><span data-ttu-id="79aa2-189">Crear una acción de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="79aa2-189">Creating a Drillthrough Action</span></span>  
 <span data-ttu-id="79aa2-190">Una acción de obtención de detalles se define mediante una acción de conjunto de filas, que se devuelve a la aplicación cliente como una instrucción de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="79aa2-190">A drillthrough action is defined by a rowset action, which is returned to the client application as a drillthrough statement.</span></span> <span data-ttu-id="79aa2-191">El destino de la acción es un miembro de un grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="79aa2-191">The action target is a member of a measure group.</span></span> <span data-ttu-id="79aa2-192">Para crear una acción de obtención de detalles, en el menú **Cubo** , haga clic en **Nueva acción de obtención de detalles**.</span><span class="sxs-lookup"><span data-stu-id="79aa2-192">To create a new drillthrough action, on the **Cube** menu, click **New Drillthrough Action**.</span></span> <span data-ttu-id="79aa2-193">Las siguientes opciones son específicas de una acción de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="79aa2-193">The following options are specific to a drillthrough action:</span></span>  
  
 <span data-ttu-id="79aa2-194">**Columnas de obtención de detalles**</span><span class="sxs-lookup"><span data-stu-id="79aa2-194">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="79aa2-195">Seleccione una o más dimensiones y, para cada dimensión, las columnas de obtención de detalles devueltas a la aplicación cliente por la acción.</span><span class="sxs-lookup"><span data-stu-id="79aa2-195">Select one or more dimensions and, for each dimension, the drillthrough columns returned to the client application by the action.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79aa2-196">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79aa2-196">See Also</span></span>  
 [<span data-ttu-id="79aa2-197">Cubos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="79aa2-197">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
