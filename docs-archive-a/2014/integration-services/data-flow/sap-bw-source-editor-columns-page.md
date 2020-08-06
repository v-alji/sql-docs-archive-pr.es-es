---
title: Editor de origen de SAP BW (página Columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c2ec8bb7-be9b-4783-ad88-32512de784b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba605360d01abc520cedfbc457dd89319ed83c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748847"
---
# <a name="sap-bw-source-editor-columns-page"></a><span data-ttu-id="06c3a-102">Editor de origen de SAP BW (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="06c3a-102">SAP BW Source Editor (Columns Page)</span></span>
  <span data-ttu-id="06c3a-103">Use la página **Columnas** del **Editor de origen de SAP BW** para asignar una columna de salida a cada columna externa (origen).</span><span class="sxs-lookup"><span data-stu-id="06c3a-103">Use the **Columns** page of the **SAP BW Source Editor** to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="06c3a-104">Para obtener más información sobre el componente de origen de SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Origen de SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="06c3a-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="06c3a-105">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="06c3a-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="06c3a-106">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="06c3a-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="06c3a-107">La extracción de datos de SAP Netweaver BW requiere una licencia SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="06c3a-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="06c3a-108">Póngase en contacto con SAP para comprobar estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="06c3a-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="06c3a-109">**Para abrir la página Columnas**</span><span class="sxs-lookup"><span data-stu-id="06c3a-109">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="06c3a-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="06c3a-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="06c3a-111">En la pestaña **Flujo de datos** , haga doble clic en el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="06c3a-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="06c3a-112">En **Editor de origen de SAP BW**, haga clic en **Columnas** para abrir la página **Columnas** del editor.</span><span class="sxs-lookup"><span data-stu-id="06c3a-112">In the **SAP BW Source Editor**, click **Columns** to open the **Columns** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="06c3a-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="06c3a-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="06c3a-114">Si no conoce todos los valores necesarios para configurar el origen, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="06c3a-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="06c3a-115">**Columnas externas disponibles**</span><span class="sxs-lookup"><span data-stu-id="06c3a-115">**Available External Columns**</span></span>  
 <span data-ttu-id="06c3a-116">Permite ver la lista de columnas externas disponibles en el origen de datos y, posteriormente, seleccionar las columnas que se van a incluir en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="06c3a-116">View the list of available external columns in the data source, and then select the columns to be included in the data flow.</span></span>  
  
 <span data-ttu-id="06c3a-117">Para incluir una columna en el flujo de datos, active la casilla que se corresponde con esa columna.</span><span class="sxs-lookup"><span data-stu-id="06c3a-117">To include a column in the data flow, select the check box that corresponds to that column.</span></span> <span data-ttu-id="06c3a-118">El orden en el que se activen las casillas determina el orden en el que se generarán las columnas.</span><span class="sxs-lookup"><span data-stu-id="06c3a-118">The order in which you select the check boxes determines the order in which columns will be output.</span></span> <span data-ttu-id="06c3a-119">Es decir, la primera casilla que selecciona será la primera columna de salida, la segunda casilla será la segunda columna de salida y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="06c3a-119">That is, the first check box that you select will be the first output column, the second check box will be the second output columns, and so on.</span></span>  
  
 <span data-ttu-id="06c3a-120">**Columna externa**</span><span class="sxs-lookup"><span data-stu-id="06c3a-120">**External Column**</span></span>  
 <span data-ttu-id="06c3a-121">Permite ver las columnas externas (origen) seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="06c3a-121">View the selected external (source) columns.</span></span> <span data-ttu-id="06c3a-122">Las columnas seleccionadas aparecen en el orden en el que verá las columnas de salida correspondientes cuando configure los componentes de nivel inferior que utilizan datos de este origen.</span><span class="sxs-lookup"><span data-stu-id="06c3a-122">The selected columns appear in the order in which you will see their corresponding output columns when you configure downstream components that consume data from this source.</span></span>  
  
 <span data-ttu-id="06c3a-123">Para cambiar el orden de las columnas, en la lista de **Columnas externas disponibles** , desactive las casillas de todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="06c3a-123">To change the order of the columns, in the **Available External Columns** list, clear the check boxes for all columns.</span></span> <span data-ttu-id="06c3a-124">A continuación, seleccione las columnas en el orden en que desea que aparezcan.</span><span class="sxs-lookup"><span data-stu-id="06c3a-124">Then, select the columns in the order that you want them to appear.</span></span>  
  
 <span data-ttu-id="06c3a-125">**Columna de salida**</span><span class="sxs-lookup"><span data-stu-id="06c3a-125">**Output Column**</span></span>  
 <span data-ttu-id="06c3a-126">Permite proporcionar un nombre único para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="06c3a-126">Provide a unique name for each output column.</span></span> <span data-ttu-id="06c3a-127">El valor predeterminado es el nombre de la columna externa (origen) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="06c3a-127">The default is the name of the selected external (source) column.</span></span> <span data-ttu-id="06c3a-128">Sin embargo, puede especificarse cualquier nombre único que sea descriptivo.</span><span class="sxs-lookup"><span data-stu-id="06c3a-128">However, you can enter any unique, descriptive name.</span></span> [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="06c3a-129">mostrará los nombres de la **Columna de salida** para las columnas al configurar los componentes de nivel inferior que utilizan datos de este origen.</span><span class="sxs-lookup"><span data-stu-id="06c3a-129">Designer will display the **Output Column** names for the columns when you configure downstream components that consume data from this source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c3a-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06c3a-130">See Also</span></span>  
 <span data-ttu-id="06c3a-131">[Editor de origen de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="06c3a-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="06c3a-132">[Editor de origen de SAP BW &#40;página Salida de error&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="06c3a-132">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="06c3a-133">[Editor de origen de SAP BW &#40;página Opciones avanzadas&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="06c3a-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="06c3a-134">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="06c3a-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
