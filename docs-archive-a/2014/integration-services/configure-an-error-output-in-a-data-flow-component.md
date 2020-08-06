---
title: Configurar una salida de error en un componente de flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- errors [Integration Services], data flow components
- components [Integration Services], data flow
- error outputs [Integration Services]
ms.assetid: 53d7eeea-927d-4b45-8ea9-084e65ad5390
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebd44383e27daa465576bb056a67f6dacad87b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750094"
---
# <a name="configure-an-error-output-in-a-data-flow-component"></a><span data-ttu-id="1721f-102">Configurar una salida de error en un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="1721f-102">Configure an Error Output in a Data Flow Component</span></span>
  <span data-ttu-id="1721f-103">Un gran número de componentes de flujo de datos admiten salidas de errores y, dependiendo del componente, el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] proporciona diferentes maneras de configurar una salida de error.</span><span class="sxs-lookup"><span data-stu-id="1721f-103">Many data flow components support error outputs, and depending on the component, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides different ways to configure an error output.</span></span> <span data-ttu-id="1721f-104">Además de configurar una salida de error, también puede configurar sus columnas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="1721f-104">In addition to configuring an error output, you can also configure the columns of an error output.</span></span> <span data-ttu-id="1721f-105">Esto incluye configurar las columnas **ErrorCode** y **ErrorColumn** agregadas por el componente.</span><span class="sxs-lookup"><span data-stu-id="1721f-105">This includes configuring the **ErrorCode** and **ErrorColumn** columns that are added by the component.</span></span>  
  
## <a name="configuring-an-error-output"></a><span data-ttu-id="1721f-106">Configurar una salida de error</span><span class="sxs-lookup"><span data-stu-id="1721f-106">Configuring an Error Output</span></span>  
 <span data-ttu-id="1721f-107">Para configurar una salida de error, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="1721f-107">To configure an error output, you have two options:</span></span>  
  
-   <span data-ttu-id="1721f-108">Utilice el cuadro de diálogo **Configurar la salida de errores** .</span><span class="sxs-lookup"><span data-stu-id="1721f-108">Use the **Configure Error Output** dialog box.</span></span> <span data-ttu-id="1721f-109">Puede usar este cuadro de diálogo para configurar una salida de error en cualquier componente de flujo de datos que la admita.</span><span class="sxs-lookup"><span data-stu-id="1721f-109">You can use this dialog box to configure an error output on any data flow component that supports an error output.</span></span>  
  
-   <span data-ttu-id="1721f-110">Utilice el cuadro de diálogo del editor para el componente.</span><span class="sxs-lookup"><span data-stu-id="1721f-110">Use the editor dialog box for the component.</span></span> <span data-ttu-id="1721f-111">Algunos componentes permiten configurar directamente salidas de errores en el cuadro de diálogo de su editor.</span><span class="sxs-lookup"><span data-stu-id="1721f-111">Some components let you configure error outputs directly from their editor dialog box.</span></span> <span data-ttu-id="1721f-112">Sin embargo, no se pueden configurar salidas de errores en el cuadro de diálogo del editor para el origen de ADO NET, la transformación Importar columna, la transformación Comando de OLE DB o el destino de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="1721f-112">However, you cannot configure error outputs from the editor dialog box for the ADO NET source, the Import Column transformation, the OLE DB Command transformation, or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact destination.</span></span>  
  
 <span data-ttu-id="1721f-113">Los procedimientos siguientes describen cómo utilizar estos cuadros de diálogo para configurar salidas de errores.</span><span class="sxs-lookup"><span data-stu-id="1721f-113">The following procedures describe how to use these dialog boxes to configure error outputs.</span></span>  
  
#### <a name="to-configure-an-error-output-using-the-configure-error-output-dialog-box"></a><span data-ttu-id="1721f-114">Para configurar una salida de error mediante el cuadro de diálogo Configurar la salida de errores</span><span class="sxs-lookup"><span data-stu-id="1721f-114">To configure an error output using the Configure Error Output dialog box</span></span>  
  
1.  <span data-ttu-id="1721f-115">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="1721f-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="1721f-116">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="1721f-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="1721f-117">En el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , haga clic en la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="1721f-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="1721f-118">Arrastre la salida de error, representada por una flecha roja, del componente de origen de los errores a otro componente de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="1721f-118">Drag the error output, represented by the red arrow, from the component that is the source of the errors to another component in the data flow.</span></span>  
  
5.  <span data-ttu-id="1721f-119">En el cuadro de diálogo **Configurar la salida de errores** , seleccione una acción de las columnas **Error** y **Truncamiento** para cada columna de la entrada de componentes.</span><span class="sxs-lookup"><span data-stu-id="1721f-119">In the **Configure Error Output** dialog box, select an action in the **Error** and **Truncation** columns for each column in the component input.</span></span>  
  
6.  <span data-ttu-id="1721f-120">Para guardar el paquete actualizado, en el menú **Archivo** , haga clic en **Guardar los elementos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="1721f-120">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
#### <a name="to-add-an-error-output-using-the-editor-dialog-box-for-the-component"></a><span data-ttu-id="1721f-121">Para agregar una salida de error mediante el cuadro de diálogo del editor para el componente</span><span class="sxs-lookup"><span data-stu-id="1721f-121">To add an error output using the editor dialog box for the component</span></span>  
  
1.  <span data-ttu-id="1721f-122">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="1721f-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="1721f-123">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="1721f-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="1721f-124">En el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , haga clic en la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="1721f-124">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="1721f-125">Haga doble clic en los componentes de flujo de datos en los que desee configurar una salida de error y, en función del componente, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1721f-125">Double-click the data flow components in which you want to configure an error output and, depending on the component, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="1721f-126">Haga clic en **Configurar la salida de errores**.</span><span class="sxs-lookup"><span data-stu-id="1721f-126">Click **Configure Error Output**.</span></span>  
  
    -   <span data-ttu-id="1721f-127">Haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="1721f-127">Click **Error Output**.</span></span>  
  
5.  <span data-ttu-id="1721f-128">Establezca la opción **Error** para cada columna.</span><span class="sxs-lookup"><span data-stu-id="1721f-128">Set the **Error** option for each column.</span></span>  
  
6.  <span data-ttu-id="1721f-129">Establezca la opción **Truncamiento** para cada columna.</span><span class="sxs-lookup"><span data-stu-id="1721f-129">Set the **Truncation** option for each column.</span></span>  
  
7.  <span data-ttu-id="1721f-130">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="1721f-130">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="1721f-131">Para guardar el paquete actualizado, en el menú **Archivo** , haga clic en **Guardar los elementos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="1721f-131">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="configuring-error-output-columns"></a><span data-ttu-id="1721f-132">Configurar columnas de salida de error</span><span class="sxs-lookup"><span data-stu-id="1721f-132">Configuring Error Output Columns</span></span>  
 <span data-ttu-id="1721f-133">Para configurar columnas de salida de error, tiene que utilizar la pestaña **Propiedades de entrada y salida** del cuadro de diálogo **Editor avanzado** .</span><span class="sxs-lookup"><span data-stu-id="1721f-133">To configure the error output columns, you have to use the **Input and Output Properties** tab of the **Advanced Editor** dialog box.</span></span>  
  
#### <a name="to-configure-error-output-columns"></a><span data-ttu-id="1721f-134">Para configurar columnas de salida de error</span><span class="sxs-lookup"><span data-stu-id="1721f-134">To configure error output columns</span></span>  
  
1.  <span data-ttu-id="1721f-135">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="1721f-135">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="1721f-136">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="1721f-136">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="1721f-137">En el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , haga clic en la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="1721f-137">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="1721f-138">Haga clic con el botón derecho en el componente cuyas columnas de salida de error quiere configurar y haga clic en **Mostrar editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="1721f-138">Right-click the component whose error output columns you want to configure and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="1721f-139">Haga clic en la pestaña **Propiedades de entrada y salida** y expanda **Salida de error de \<component name>** y, después, expanda **Columnas de salida**.</span><span class="sxs-lookup"><span data-stu-id="1721f-139">Click the **Input and Output Properties** tab and expand **\<component name> Error Output** and then expand **Output Columns**.</span></span>  
  
6.  <span data-ttu-id="1721f-140">Haga clic en una columna y actualice sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="1721f-140">Click a column and update its properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1721f-141">La lista de columnas incluye las columnas de la entrada de componentes, las columnas **ErrorCode** y **ErrorColumn** agregadas por salidas de errores previas, y las columnas **ErrorCode** y **ErrorColumn** agregadas por este componente.</span><span class="sxs-lookup"><span data-stu-id="1721f-141">The list of columns includes the columns in the component input, the **ErrorCode** and **ErrorColumn** columns added by previous error outputs, and the **ErrorCode** and **ErrorColumn** columns added by this component.</span></span>  
  
7.  <span data-ttu-id="1721f-142">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1721f-142">Click **OK.**</span></span>  
  
8.  <span data-ttu-id="1721f-143">Para guardar el paquete actualizado, en el menú **Archivo** , haga clic en **Guardar los elementos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="1721f-143">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1721f-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1721f-144">See Also</span></span>  
 [<span data-ttu-id="1721f-145">Control de errores en los datos</span><span class="sxs-lookup"><span data-stu-id="1721f-145">Error Handling in Data</span></span>](data-flow/error-handling-in-data.md)  
  
  
