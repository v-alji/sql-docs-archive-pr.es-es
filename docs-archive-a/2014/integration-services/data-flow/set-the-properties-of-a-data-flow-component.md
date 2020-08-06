---
title: Establecer las propiedades de un componente de flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], properties
ms.assetid: 73000ef6-52a2-4dec-8320-0e79acf0c2c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1fd045ba076eed2d65d801015b881a477976f5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676111"
---
# <a name="set-the-properties-of-a-data-flow-component"></a><span data-ttu-id="8bac5-102">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="8bac5-102">Set the Properties of a Data Flow Component</span></span>
  <span data-ttu-id="8bac5-103">Para establecer las propiedades de los componentes de flujo de datos, que incluyen orígenes, destinos y transformaciones, utilice una de las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bac5-103">To set the properties of data flow components, which include sources, destinations, and transformations, use one of the following features:</span></span>  
  
-   <span data-ttu-id="8bac5-104">Los editores de componentes que [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] proporciona.</span><span class="sxs-lookup"><span data-stu-id="8bac5-104">The component editors that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides.</span></span> <span data-ttu-id="8bac5-105">Estos editores incluyen solo las propiedades personalizadas de cada componente de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="8bac5-105">These editors include only the custom properties of each data flow component.</span></span>  
  
-   <span data-ttu-id="8bac5-106">La ventana **Propiedades** enumera las propiedades personalizadas de nivel de componente de cada elemento, al igual que las propiedades que son comunes a todos los elementos de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="8bac5-106">The **Properties** window lists the component-level custom properties of each element, as well as the properties common to all data flow elements.</span></span>  
  
-   <span data-ttu-id="8bac5-107">El cuadro de diálogo **Editor avanzado** proporciona acceso a las propiedades personalizadas de cada componente.</span><span class="sxs-lookup"><span data-stu-id="8bac5-107">The **Advanced Editor** dialog box provides access to custom properties for each component.</span></span> <span data-ttu-id="8bac5-108">El cuadro de diálogo **Editor avanzado** también permite acceder a las propiedades comunes de todos los componentes de flujo de datos (propiedades de entradas, salidas, salidas de error, columnas y columnas externas).</span><span class="sxs-lookup"><span data-stu-id="8bac5-108">The **Advanced Editor** dialog box also provides access to the properties common to all data flow components-the properties of inputs, outputs, error outputs, columns, and external columns.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-a-component-editor"></a><span data-ttu-id="8bac5-109">Para establecer las propiedades de un componente de flujo de datos mediante un editor de componentes</span><span class="sxs-lookup"><span data-stu-id="8bac5-109">To set the properties of a data flow component by using a component editor</span></span>  
  
1.  <span data-ttu-id="8bac5-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="8bac5-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8bac5-111">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="8bac5-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8bac5-112">Haga clic en la pestaña **Flujo de control** y luego haga doble clic en la tarea Flujo de datos que contiene el flujo de datos con el componente cuyas propiedades quiere ver y modificar.</span><span class="sxs-lookup"><span data-stu-id="8bac5-112">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow with the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="8bac5-113">Haga doble clic en el componente de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="8bac5-113">Double-click the data flow component.</span></span>  
  
5.  <span data-ttu-id="8bac5-114">En el editor de componentes, vea o modifique los valores de las propiedades y luego cierre el editor.</span><span class="sxs-lookup"><span data-stu-id="8bac5-114">In the component editor, view or modify the property values, and then close the editor.</span></span>  
  
6.  <span data-ttu-id="8bac5-115">Para guardar el paquete actualizado, en el menú **Archivo** , haga clic en **Guardar los elementos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="8bac5-115">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-properties-window"></a><span data-ttu-id="8bac5-116">Para establecer las propiedades de un componente de flujo de datos mediante una ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="8bac5-116">To set the properties of a data flow component by using the Properties window</span></span>  
  
1.  <span data-ttu-id="8bac5-117">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="8bac5-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8bac5-118">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="8bac5-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8bac5-119">Haga clic en la pestaña **Flujo de control** y luego haga doble clic en la tarea Flujo de datos que contiene el componente cuyas propiedades quiere ver y modificar.</span><span class="sxs-lookup"><span data-stu-id="8bac5-119">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="8bac5-120">Haga clic con el botón derecho en el componente de flujo de datos y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8bac5-120">Right-click the data flow component, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="8bac5-121">Vea o modifique los valores de la propiedad y luego cierre la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="8bac5-121">View or modify the property values, and then close the **Properties** window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8bac5-122">Muchas propiedades son de solo lectura y no pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="8bac5-122">Many properties are read-only, and cannot be modified.</span></span>  
  
6.  <span data-ttu-id="8bac5-123">Para guardar el paquete actualizado, en el menú **Archivo** , haga clic en **Guardar los elementos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="8bac5-123">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-advanced-editor"></a><span data-ttu-id="8bac5-124">Para establecer las propiedades de un componente de flujo de datos mediante el Editor avanzado</span><span class="sxs-lookup"><span data-stu-id="8bac5-124">To set the properties of a data flow component by using the Advanced Editor</span></span>  
  
1.  <span data-ttu-id="8bac5-125">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="8bac5-125">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8bac5-126">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="8bac5-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8bac5-127">Haga clic en la pestaña **Flujo de control** y luego haga doble clic en la tarea Flujo de datos que contiene el componente que quiere ver o modificar.</span><span class="sxs-lookup"><span data-stu-id="8bac5-127">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component you want to view or modify.</span></span>  
  
4.  <span data-ttu-id="8bac5-128">En el diseñador de flujos de datos, haga clic con el botón derecho en el componente de flujo de datos y luego haga clic en **Mostrar editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="8bac5-128">In the data flow designer, right-click the data flow component, and then click **Show Advanced Editor**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8bac5-129">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], los componentes de flujo de datos que admiten varias entradas no pueden usar el **Editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="8bac5-129">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data flow components that support multiple inputs cannot use the **Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="8bac5-130">En el cuadro de diálogo **Editor avanzado** , realice cualquiera de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bac5-130">In the **Advanced Editor** dialog box, do any of the following steps:</span></span>  
  
    -   <span data-ttu-id="8bac5-131">Para ver y especificar la conexión que el componente utiliza, haga clic en la pestaña **Administradores de conexiones** .</span><span class="sxs-lookup"><span data-stu-id="8bac5-131">To view and specify the connection that the component uses, click the **Connection Managers** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8bac5-132">La pestaña **Administradores de conexiones** está disponible solamente para los componentes de flujo de datos que usan administradores de conexiones para conectarse a orígenes de datos como archivos y bases de datos</span><span class="sxs-lookup"><span data-stu-id="8bac5-132">The **Connection Managers** tab is available only to data flow components that use connection managers to connect to data sources such as files and databases</span></span>  
  
    -   <span data-ttu-id="8bac5-133">Para ver y modificar propiedades de nivel de componente, haga clic en la pestaña **Propiedades de componente** .</span><span class="sxs-lookup"><span data-stu-id="8bac5-133">To view and modify component-level properties, click the **Component Properties** tab.</span></span>  
  
    -   <span data-ttu-id="8bac5-134">Para ver y modificar asignaciones entre columnas externas y la salida disponible, haga clic en la pestaña **Asignaciones de columnas** .</span><span class="sxs-lookup"><span data-stu-id="8bac5-134">To view and modify mappings between external columns and the available output, click the **Column Mappings** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8bac5-135">La pestaña **Asignaciones de columnas** solo está disponible al ver o editar orígenes o destinos.</span><span class="sxs-lookup"><span data-stu-id="8bac5-135">The **Column Mappings** tab is available only when viewing or editing sources or destinations.</span></span>  
  
    -   <span data-ttu-id="8bac5-136">Para ver una lista de las columnas de entrada disponibles y para actualizar los nombres de las columnas de salida, haga clic en la pestaña **Columnas de entrada** .</span><span class="sxs-lookup"><span data-stu-id="8bac5-136">To view a list of the available input columns and to update the names of output columns, click the **Input Columns** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8bac5-137">La pestaña Columnas de entrada está disponible solamente cuando se trabaja con transformaciones o destinos.</span><span class="sxs-lookup"><span data-stu-id="8bac5-137">The Input Columns tab is available only when working with transformations or destinations.</span></span> <span data-ttu-id="8bac5-138">Para más información, consulte [Integration Services Transformations](transformations/integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="8bac5-138">For more information, see [Integration Services Transformations](transformations/integration-services-transformations.md).</span></span>  
  
    -   <span data-ttu-id="8bac5-139">Para ver y modificar las propiedades de las entradas, salidas y salidas de errores, y las propiedades de las columnas que contienen, haga clic en la pestaña **Propiedades de entrada y salida** .</span><span class="sxs-lookup"><span data-stu-id="8bac5-139">To view and modify the properties of inputs, outputs, and error outputs, and the properties of the columns they contain, click the **Input and Output Properties** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8bac5-140">Los orígenes no tienen entradas.</span><span class="sxs-lookup"><span data-stu-id="8bac5-140">Sources have no inputs.</span></span> <span data-ttu-id="8bac5-141">Los destinos no tienen salidas, excepto una salida de errores opcional.</span><span class="sxs-lookup"><span data-stu-id="8bac5-141">Destinations have no outputs, except for an optional error output.</span></span>  
  
6.  <span data-ttu-id="8bac5-142">Vea o modifique los valores de propiedades.</span><span class="sxs-lookup"><span data-stu-id="8bac5-142">View or modify the property values.</span></span>  
  
7.  <span data-ttu-id="8bac5-143">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="8bac5-143">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="8bac5-144">Para guardar el paquete actualizado, en el menú **Archivo** , haga clic en **Guardar los elementos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="8bac5-144">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bac5-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bac5-145">See Also</span></span>  
 [<span data-ttu-id="8bac5-146">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="8bac5-146">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
