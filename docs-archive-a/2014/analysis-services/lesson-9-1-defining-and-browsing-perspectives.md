---
title: Definir y examinar perspectivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 766004b9-6578-4914-a445-6f44843a5fb0
author: minewiskan
ms.author: owend
ms.openlocfilehash: c9658098180618c2d5d6d6d9e00e7a7e4a6c4231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747232"
---
# <a name="defining-and-browsing-perspectives"></a><span data-ttu-id="9d736-102">Definir y examinar perspectivas</span><span class="sxs-lookup"><span data-stu-id="9d736-102">Defining and Browsing Perspectives</span></span>
  <span data-ttu-id="9d736-103">Una perspectiva puede simplificar la vista de un cubo para fines específicos.</span><span class="sxs-lookup"><span data-stu-id="9d736-103">A perspective can simplify the view of a cube for specific purposes.</span></span> <span data-ttu-id="9d736-104">De manera predeterminada, los usuarios pueden ver todos los elementos de un cubo para los que tengan permisos.</span><span class="sxs-lookup"><span data-stu-id="9d736-104">By default, users can see all of the elements in a cube to which they have permissions.</span></span> <span data-ttu-id="9d736-105">Lo que observan los usuarios cuando ven un cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] entero es la perspectiva predeterminada del cubo.</span><span class="sxs-lookup"><span data-stu-id="9d736-105">What users are viewing when they view an entire [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube is the default perspective for the cube.</span></span> <span data-ttu-id="9d736-106">Una vista de todo el cubo puede resultar muy compleja para que los usuarios naveguen por ella, en especial aquellos usuarios que solo necesitan interactuar con una pequeña parte del cubo a fin de satisfacer sus requisitos de informes e inteligencia empresarial.</span><span class="sxs-lookup"><span data-stu-id="9d736-106">A view of the whole cube can be very complex for users to navigate, especially for users who only need to interact with a small part of the cube to satisfy their business intelligence and reporting requirements.</span></span>  
  
 <span data-ttu-id="9d736-107">Para reducir la aparente complejidad de un cubo, puede crear subconjuntos visibles del cubo, denominados *perspectivas*, que solo muestran a los usuarios una parte de los grupos de medida, medidas, dimensiones, atributos, jerarquías, indicadores clave de rendimiento (KPI), acciones y miembros calculados del cubo.</span><span class="sxs-lookup"><span data-stu-id="9d736-107">To reduce the apparent complexity of a cube, you can create viewable subsets of the cube, called *perspectives*, which show users only a part of the measure groups, measures, dimensions, attributes, hierarchies, Key Performance Indicators (KPIs), actions, and calculated members in the cube.</span></span> <span data-ttu-id="9d736-108">Esto puede ser especialmente útil para trabajar con aplicaciones cliente que se escribieron para una versión anterior de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d736-108">This can be particularly useful for working with client applications that were written for a previous release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="9d736-109">Estos clientes, por ejemplo, no tienen el concepto de carpetas o perspectivas para mostrar, pero aparece una perspectiva para los clientes antiguos como si fuera un cubo.</span><span class="sxs-lookup"><span data-stu-id="9d736-109">These clients have no concept of display folders or perspectives, for example, but a perspective appears to older clients as if it were a cube.</span></span> <span data-ttu-id="9d736-110">Para obtener más información, vea [Perspectivas](multidimensional-models-olap-logical-cube-objects/perspectives.md)y [Perspectivas de modelos multidimensionales](multidimensional-models/perspectives-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="9d736-110">For more information, see [Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md), and [Perspectives in Multidimensional Models](multidimensional-models/perspectives-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9d736-111">Una perspectiva no es un mecanismo de seguridad sino, más bien, una herramienta para proporcionar una mejor experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="9d736-111">A perspective is not a security mechanism, but instead is a tool for providing a better user experience.</span></span> <span data-ttu-id="9d736-112">Toda la seguridad de una perspectiva se hereda del cubo subyacente.</span><span class="sxs-lookup"><span data-stu-id="9d736-112">All security for a perspective is inherited from the underlying cube.</span></span>  
  
 <span data-ttu-id="9d736-113">En las tareas de este tema, definirá varias perspectivas diferentes y, a continuación, examinará el cubo a través de cada una de estas nuevas perspectivas.</span><span class="sxs-lookup"><span data-stu-id="9d736-113">In the tasks in this topic, you will define several different perspectives and then browse the cube through each of these new perspectives.</span></span>  
  
## <a name="defining-an-internet-sales-perspective"></a><span data-ttu-id="9d736-114">Definir una perspectiva Internet Sales</span><span class="sxs-lookup"><span data-stu-id="9d736-114">Defining an Internet Sales Perspective</span></span>  
  
1.  <span data-ttu-id="9d736-115">Abra el Diseñador de cubos para el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y, después, haga clic en la pestaña **Perspectivas** .</span><span class="sxs-lookup"><span data-stu-id="9d736-115">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Perspectives** tab.</span></span>  
  
     <span data-ttu-id="9d736-116">Todos los objetos y sus tipos de objeto aparecen en el panel **Perspectivas** , como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="9d736-116">All the objects and their object types appear in the **Perspectives** pane, as shown in the following image.</span></span>  
  
     <span data-ttu-id="9d736-117">![Panel Perspectivas del Diseñador de cubos](../../2014/tutorials/media/l9-perspectives-1.gif "Panel Perspectivas del Diseñador de cubos")</span><span class="sxs-lookup"><span data-stu-id="9d736-117">![Perspectives pane of Cube Designer](../../2014/tutorials/media/l9-perspectives-1.gif "Perspectives pane of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="9d736-118">En la barra de herramientas de la pestaña **Perspectivas** , haga clic en el botón **Nueva perspectiva** .</span><span class="sxs-lookup"><span data-stu-id="9d736-118">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
     <span data-ttu-id="9d736-119">Una nueva perspectiva aparece en la columna **Nombre de perspectiva** con el nombre predeterminado de **Perspectiva**, como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="9d736-119">A new perspective appears in the **Perspective Name** column with a default name of **Perspective**, as shown in the following image.</span></span> <span data-ttu-id="9d736-120">Observe que la casilla de cada objeto está seleccionada; hasta que no desactive la casilla de un objeto, esta perspectiva será idéntica a la perspectiva predeterminada de este cubo.</span><span class="sxs-lookup"><span data-stu-id="9d736-120">Notice that the check box for every object is selected; until you clear the check box for an object, this perspective is identical to the default perspective of this cube.</span></span>  
  
     <span data-ttu-id="9d736-121">![Nueva perspectiva en la columna Nombre de perspectiva](../../2014/tutorials/media/l9-perspectives-2.gif "Nueva perspectiva en la columna Nombre de perspectiva")</span><span class="sxs-lookup"><span data-stu-id="9d736-121">![New perspective in Perspective Name column](../../2014/tutorials/media/l9-perspectives-2.gif "New perspective in Perspective Name column")</span></span>  
  
3.  <span data-ttu-id="9d736-122">Cambie el nombre de la perspectiva a `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="9d736-122">Change the perspective name to `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="9d736-123">En la fila siguiente, establezca DefaultMeasure en **Internet Sales-Sales Amount**.</span><span class="sxs-lookup"><span data-stu-id="9d736-123">On the next row, set the DefaultMeasure to **Internet Sales-Sales Amount**.</span></span>  
  
     <span data-ttu-id="9d736-124">Cuando los usuarios examinen el cubo mediante esta perspectiva, esta será la medida que los usuarios verán a menos que especifiquen alguna otra medida.</span><span class="sxs-lookup"><span data-stu-id="9d736-124">When users browse the cube by using this perspective, this will be the measure that the users see unless they specify some other measure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d736-125">También puede establecer la medida predeterminada para todo el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en la ventana Propiedades de la pestaña **Estructura de cubo** del cubo.</span><span class="sxs-lookup"><span data-stu-id="9d736-125">You can also set the default measure for the whole [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube in the Properties window on the **Cube Structure** tab for the cube.</span></span>  
  
5.  <span data-ttu-id="9d736-126">Desactive la casilla de los siguientes objetos:</span><span class="sxs-lookup"><span data-stu-id="9d736-126">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="9d736-127">`Reseller Sales`Grupo de medida</span><span class="sxs-lookup"><span data-stu-id="9d736-127">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="9d736-128">Grupo de medida**Sales Quotas**</span><span class="sxs-lookup"><span data-stu-id="9d736-128">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="9d736-129">Grupo de medida**Sales Quotas 1**</span><span class="sxs-lookup"><span data-stu-id="9d736-129">**Sales Quotas 1** measure group</span></span>  
  
    -   <span data-ttu-id="9d736-130">Dimensión de cubo**Reseller**</span><span class="sxs-lookup"><span data-stu-id="9d736-130">**Reseller** cube dimension</span></span>  
  
    -   <span data-ttu-id="9d736-131">Dimensión de cubo**Reseller Geography**</span><span class="sxs-lookup"><span data-stu-id="9d736-131">**Reseller Geography** cube dimension</span></span>  
  
    -   <span data-ttu-id="9d736-132">Dimensión del cubo**Sales Territory**</span><span class="sxs-lookup"><span data-stu-id="9d736-132">**Sales Territory** cube dimension</span></span>  
  
    -   <span data-ttu-id="9d736-133">Dimensión de cubo**Employee**</span><span class="sxs-lookup"><span data-stu-id="9d736-133">**Employee** cube dimension</span></span>  
  
    -   <span data-ttu-id="9d736-134">Dimensión de cubo**Promotion**</span><span class="sxs-lookup"><span data-stu-id="9d736-134">**Promotion** cube dimension</span></span>  
  
    -   <span data-ttu-id="9d736-135">**Reseller Revenue**</span><span class="sxs-lookup"><span data-stu-id="9d736-135">**Reseller Revenue** KPI</span></span>  
  
    -   <span data-ttu-id="9d736-136">Conjunto con nombre**Large Resellers**</span><span class="sxs-lookup"><span data-stu-id="9d736-136">**Large Resellers** named set</span></span>  
  
    -   <span data-ttu-id="9d736-137">Miembro calculado**Total Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="9d736-137">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="9d736-138">Miembro calculado**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="9d736-138">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="9d736-139">Miembro calculado**Reseller GPM**</span><span class="sxs-lookup"><span data-stu-id="9d736-139">**Reseller GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="9d736-140">Miembro calculado**Total GPM**</span><span class="sxs-lookup"><span data-stu-id="9d736-140">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="9d736-141">Miembro calculado**Reseller Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="9d736-141">**Reseller Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="9d736-142">Miembro calculado**Total Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="9d736-142">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="9d736-143">Estos objetos no tienen relación con Internet Sales.</span><span class="sxs-lookup"><span data-stu-id="9d736-143">These objects do not relate to Internet sales.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d736-144">Dentro de cada dimensión, también puede seleccionar individualmente las jerarquías definidas por el usuario y los atributos que desee que aparezcan en una perspectiva.</span><span class="sxs-lookup"><span data-stu-id="9d736-144">Within each dimension, you can also individually select the user-defined hierarchies and attributes that you want to appear in a perspective.</span></span>  
  
## <a name="defining-a-reseller-sales-perspective"></a><span data-ttu-id="9d736-145">Definir una perspectiva Reseller Sales</span><span class="sxs-lookup"><span data-stu-id="9d736-145">Defining a Reseller Sales Perspective</span></span>  
  
1.  <span data-ttu-id="9d736-146">En la barra de herramientas de la pestaña **Perspectivas** , haga clic en el botón **Nueva perspectiva** .</span><span class="sxs-lookup"><span data-stu-id="9d736-146">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="9d736-147">Cambie el nombre de la nueva perspectiva a `Reseller Sales` .</span><span class="sxs-lookup"><span data-stu-id="9d736-147">Change the name of the new perspective to `Reseller Sales`.</span></span>  
  
3.  <span data-ttu-id="9d736-148">Establezca **Reseller Sales-Sales Amount** como medida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9d736-148">Set **Reseller Sales-Sales Amount** as the default measure.</span></span>  
  
     <span data-ttu-id="9d736-149">Cuando los usuarios examinen el cubo mediante esta perspectiva, esta medida será la medida que los usuarios verán a menos que especifiquen alguna otra medida.</span><span class="sxs-lookup"><span data-stu-id="9d736-149">When users browse the cube by using this perspective, this measure will be the measure that the users will see unless they specify some other measure.</span></span>  
  
4.  <span data-ttu-id="9d736-150">Desactive la casilla de los siguientes objetos:</span><span class="sxs-lookup"><span data-stu-id="9d736-150">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="9d736-151">`Internet Sales`Grupo de medida</span><span class="sxs-lookup"><span data-stu-id="9d736-151">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="9d736-152">Grupo de medida**Internet Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="9d736-152">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="9d736-153">Dimensión de cubo**Customer**</span><span class="sxs-lookup"><span data-stu-id="9d736-153">**Customer** cube dimension</span></span>  
  
    -   <span data-ttu-id="9d736-154">Dimensión de cubo**Internet Sales Order Details**</span><span class="sxs-lookup"><span data-stu-id="9d736-154">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="9d736-155">Dimensión de cubo**Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="9d736-155">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="9d736-156">Acción de obtención de detalles**Internet Sales Details Drillthrough Action**</span><span class="sxs-lookup"><span data-stu-id="9d736-156">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
    -   <span data-ttu-id="9d736-157">Miembro calculado**Total Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="9d736-157">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="9d736-158">Miembro calculado**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="9d736-158">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="9d736-159">Miembro calculado**Internet GPM**</span><span class="sxs-lookup"><span data-stu-id="9d736-159">**Internet GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="9d736-160">Miembro calculado**Total GPM**</span><span class="sxs-lookup"><span data-stu-id="9d736-160">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="9d736-161">Miembro calculado**Internet Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="9d736-161">**Internet Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="9d736-162">Miembro calculado**Total Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="9d736-162">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="9d736-163">Estos objetos no tienen relación con Resellers Sales.</span><span class="sxs-lookup"><span data-stu-id="9d736-163">These objects do not relate to resellers sales.</span></span>  
  
## <a name="defining-a-sales-summary-perspective"></a><span data-ttu-id="9d736-164">Definir una perspectiva Sales Summary</span><span class="sxs-lookup"><span data-stu-id="9d736-164">Defining a Sales Summary Perspective</span></span>  
  
1.  <span data-ttu-id="9d736-165">En la barra de herramientas de la pestaña **Perspectivas** , haga clic en el botón **Nueva perspectiva** .</span><span class="sxs-lookup"><span data-stu-id="9d736-165">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="9d736-166">Cambie el nombre de la nueva perspectiva a `Sales Summary` .</span><span class="sxs-lookup"><span data-stu-id="9d736-166">Change the name of the new perspective to `Sales Summary`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d736-167">No puede especificar una medida calculada como medida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9d736-167">You cannot specify a calculated measure as the default measure.</span></span>  
  
3.  <span data-ttu-id="9d736-168">Desactive la casilla de los siguientes objetos:</span><span class="sxs-lookup"><span data-stu-id="9d736-168">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="9d736-169">`Internet Sales`Grupo de medida</span><span class="sxs-lookup"><span data-stu-id="9d736-169">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="9d736-170">`Reseller Sales`Grupo de medida</span><span class="sxs-lookup"><span data-stu-id="9d736-170">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="9d736-171">Grupo de medida**Internet Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="9d736-171">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="9d736-172">Grupo de medida**Sales Quotas**</span><span class="sxs-lookup"><span data-stu-id="9d736-172">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="9d736-173">Grupo de medida**Sales Quotas1**</span><span class="sxs-lookup"><span data-stu-id="9d736-173">**Sales Quotas1** measure group</span></span>  
  
    -   <span data-ttu-id="9d736-174">Dimensión de cubo**Internet Sales Order Details**</span><span class="sxs-lookup"><span data-stu-id="9d736-174">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="9d736-175">Dimensión de cubo**Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="9d736-175">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="9d736-176">Acción de obtención de detalles**Internet Sales Details Drillthrough Action**</span><span class="sxs-lookup"><span data-stu-id="9d736-176">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
4.  <span data-ttu-id="9d736-177">Active la casilla de los siguientes objetos:</span><span class="sxs-lookup"><span data-stu-id="9d736-177">Select the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="9d736-178">Medida**Internet Sales Count**</span><span class="sxs-lookup"><span data-stu-id="9d736-178">**Internet Sales Count** measure</span></span>  
  
    -   <span data-ttu-id="9d736-179">Medida**Reseller Sales Count**</span><span class="sxs-lookup"><span data-stu-id="9d736-179">**Reseller Sales Count** measure</span></span>  
  
## <a name="browsing-the-cube-through-each-perspective"></a><span data-ttu-id="9d736-180">Examinar el cubo a través de cada perspectiva</span><span class="sxs-lookup"><span data-stu-id="9d736-180">Browsing the Cube Through Each Perspective</span></span>  
  
1.  <span data-ttu-id="9d736-181">En el menú **Compilar** , haga clic en **Tutorial de Implementar Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="9d736-181">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="9d736-182">Cuando la implementación se haya completado correctamente, vaya a la pestaña **Explorador** y, después, haga clic en el botón **Volver a conectar** .</span><span class="sxs-lookup"><span data-stu-id="9d736-182">When deployment has successfully completed, switch to the **Browser** tab, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="9d736-183">Inicie Excel.</span><span class="sxs-lookup"><span data-stu-id="9d736-183">Start Excel.</span></span>  
  
4.  <span data-ttu-id="9d736-184">Analizar en Excel le pedirá que elija qué perspectiva desea usar al examinar el modelo en Excel, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="9d736-184">Analyze in Excel prompts you to choose which perspective to use when browsing the model in Excel, as shown in the following image.</span></span>  
  
     <span data-ttu-id="9d736-185">![Objetos de la perspectiva Internet Sales](../../2014/tutorials/media/l9-perspectives-3.gif "Objetos de la perspectiva Internet Sales")</span><span class="sxs-lookup"><span data-stu-id="9d736-185">![Objects for the Internet Sales perspective](../../2014/tutorials/media/l9-perspectives-3.gif "Objects for the Internet Sales perspective")</span></span>  
  
5.  <span data-ttu-id="9d736-186">Como alternativa, puede iniciar Excel en el menú Inicio de Windows, definir una conexión a la base de datos Tutorial de Analysis Services en localhost y elegir una perspectiva en el Asistente para la conexión de datos, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="9d736-186">Alternatively, you can start Excel from the Windows Start menu, define a connection to the Analysis Services Tutorial database on localhost, and choose a perspective in the Data Connection wizard, as shown in the following image.</span></span>  
  
     <span data-ttu-id="9d736-187">![Asistente para la conexión de datos de Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Asistente para la conexión de datos de Excel")</span><span class="sxs-lookup"><span data-stu-id="9d736-187">![Data Connection wizard in Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Data Connection wizard in Excel")</span></span>  
  
6.  <span data-ttu-id="9d736-188">Seleccione `Internet Sales` en la lista **perspectiva** y, a continuación, revise las medidas y las dimensiones en el panel Metadatos.</span><span class="sxs-lookup"><span data-stu-id="9d736-188">Select `Internet Sales` in the **Perspective** list and then review the measures and dimensions in the metadata pane.</span></span>  
  
     <span data-ttu-id="9d736-189">Observe que solo aparecen aquellos objetos especificados para la perspectiva Internet Sales.</span><span class="sxs-lookup"><span data-stu-id="9d736-189">Notice that only those objects that are specified for the Internet Sales perspective appear.</span></span>  
  
7.  <span data-ttu-id="9d736-190">En el panel de metadatos, expanda **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="9d736-190">In the metadata pane, expand **Measures**.</span></span>  
  
     <span data-ttu-id="9d736-191">Observe que solo `Internet Sales` aparece el grupo de medida, junto con los miembros calculados **Internet GPM** e **Internet sales ratio to All Products** .</span><span class="sxs-lookup"><span data-stu-id="9d736-191">Notice that only the `Internet Sales` measure group appears, together with the **Internet GPM** and **Internet Sales Ratio to All Products** calculated members.</span></span>  
  
8.  <span data-ttu-id="9d736-192">En el modelo, seleccione Excel de nuevo.</span><span class="sxs-lookup"><span data-stu-id="9d736-192">In the model, select Excel again.</span></span> <span data-ttu-id="9d736-193">Seleccione `Sales Summary`.</span><span class="sxs-lookup"><span data-stu-id="9d736-193">Select `Sales Summary`.</span></span>  
  
     <span data-ttu-id="9d736-194">Observe que en cada uno de estos grupos de medida, solo aparece una única medida, tal como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="9d736-194">Notice that in each of these measure groups, only a single measure appears, as shown in the following image.</span></span>  
  
     <span data-ttu-id="9d736-195">![Medidas Internet Sales y Reseller Sales](../../2014/tutorials/media/l9-perspectives-4.gif "Medidas Internet Sales y Reseller Sales")</span><span class="sxs-lookup"><span data-stu-id="9d736-195">![Internet Sales and Reseller Sales measures](../../2014/tutorials/media/l9-perspectives-4.gif "Internet Sales and Reseller Sales measures")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9d736-196">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="9d736-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9d736-197">Definir y examinar traducciones</span><span class="sxs-lookup"><span data-stu-id="9d736-197">Defining and Browsing Translations</span></span>](lesson-9-2-defining-and-browsing-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="9d736-198">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d736-198">See Also</span></span>  
 <span data-ttu-id="9d736-199">[Distintas](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span><span class="sxs-lookup"><span data-stu-id="9d736-199">[Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span></span>  
 [<span data-ttu-id="9d736-200">Perspectivas de modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="9d736-200">Perspectives in Multidimensional Models</span></span>](multidimensional-models/perspectives-in-multidimensional-models.md)  
  
  
