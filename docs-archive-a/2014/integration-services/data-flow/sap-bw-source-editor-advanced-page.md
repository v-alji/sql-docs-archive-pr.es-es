---
title: Editor de origen de SAP BW (página Opciones avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 44f3c991-9e8f-4126-a9a2-2d9da779fb11
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c78d40555a30031bf39abda18048fda9c648d01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749395"
---
# <a name="sap-bw-source-editor-advanced-page"></a><span data-ttu-id="650af-102">Editor de origen de SAP BW (página Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="650af-102">SAP BW Source Editor (Advanced Page)</span></span>
  <span data-ttu-id="650af-103">Use la página **Avanzadas** del **Editor de origen de SAP BW** para especificar la regla de conversión de cadenas y el tiempo de espera, así como para restablecer el estado de un determinado identificador de solicitud.</span><span class="sxs-lookup"><span data-stu-id="650af-103">Use the **Advanced** page of the **SAP BW Source Editor** to specify the string conversion rule and the time-out period, and also to reset the status of a particular Request ID.</span></span>  
  
 <span data-ttu-id="650af-104">Para obtener más información sobre el componente de origen de SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Origen de SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="650af-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="650af-105">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="650af-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="650af-106">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="650af-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="650af-107">La extracción de datos de SAP Netweaver BW requiere una licencia SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="650af-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="650af-108">Póngase en contacto con SAP para comprobar estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="650af-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="650af-109">**Para abrir la página Administrador de conexiones**</span><span class="sxs-lookup"><span data-stu-id="650af-109">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="650af-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="650af-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="650af-111">En la pestaña **Flujo de datos** , haga doble clic en el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="650af-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="650af-112">En **Editor de origen de SAP BW**, haga clic en **Opciones avanzadas** para abrir la página **Opciones avanzadas** del editor.</span><span class="sxs-lookup"><span data-stu-id="650af-112">In the **SAP BW Source Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="650af-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="650af-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="650af-114">Si no conoce todos los valores necesarios para configurar el origen, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="650af-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="650af-115">**Conversión de cadenas**</span><span class="sxs-lookup"><span data-stu-id="650af-115">**String Conversion**</span></span>  
 <span data-ttu-id="650af-116">Permite especificar la regla que se va a aplicar en la conversión de cadenas.</span><span class="sxs-lookup"><span data-stu-id="650af-116">Specify the rule to apply for string conversion.</span></span>  
  
|<span data-ttu-id="650af-117">Opción</span><span class="sxs-lookup"><span data-stu-id="650af-117">Option</span></span>|<span data-ttu-id="650af-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="650af-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="650af-119">**Conversión de cadena automática**</span><span class="sxs-lookup"><span data-stu-id="650af-119">**Automatic string conversion**</span></span>|<span data-ttu-id="650af-120">Permite convertir todas las cadenas a `nvarchar` cuando el sistema SAP Netweaver BW es un sistema de Unicode.</span><span class="sxs-lookup"><span data-stu-id="650af-120">Convert all strings to `nvarchar` when the SAP Netweaver BW system is a Unicode system.</span></span> <span data-ttu-id="650af-121">Si no es así, convierte todas las cadenas a `varchar`.</span><span class="sxs-lookup"><span data-stu-id="650af-121">Otherwise, convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="650af-122">**Convertir cadenas a varchar**</span><span class="sxs-lookup"><span data-stu-id="650af-122">**Convert strings to varchar**</span></span>|<span data-ttu-id="650af-123">Permite convertir todas las cadenas a `varchar`.</span><span class="sxs-lookup"><span data-stu-id="650af-123">Convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="650af-124">**Convertir cadenas a nvarchar**</span><span class="sxs-lookup"><span data-stu-id="650af-124">**Convert strings to nvarchar**</span></span>|<span data-ttu-id="650af-125">Permite convertir todas las cadenas a `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="650af-125">Convert all strings to `nvarchar`.</span></span>|  
  
 <span data-ttu-id="650af-126">**Tiempo de espera en segundos**</span><span class="sxs-lookup"><span data-stu-id="650af-126">**Timeout (seconds)**</span></span>  
 <span data-ttu-id="650af-127">Permite especificar el número máximo de segundos que debe esperar el origen.</span><span class="sxs-lookup"><span data-stu-id="650af-127">Specify the maximum number of seconds that the source should wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="650af-128">Esta opción solo es válida si ha seleccionado **W - Esperar notificación** como el valor de **Modo de ejecución** en la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="650af-128">This option is only valid if you have selected **W - Wait for Notify** as the value of **Execution Mode** on the **Connection Manager** page of the editor.</span></span> <span data-ttu-id="650af-129">Para más información, vea [Editor de origen de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="650af-129">For more information, see [SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md).</span></span>  
  
 <span data-ttu-id="650af-130">**Id. de solicitud**</span><span class="sxs-lookup"><span data-stu-id="650af-130">**Request ID**</span></span>  
 <span data-ttu-id="650af-131">Permite especificar el identificador de solicitud cuyo estado quiere restablecer a “G - Verde” al hacer clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="650af-131">Specify the Request ID whose status you want to reset to "G - Green" when you click **Reset**.</span></span>  
  
 <span data-ttu-id="650af-132">**Reset**</span><span class="sxs-lookup"><span data-stu-id="650af-132">**Reset**</span></span>  
 <span data-ttu-id="650af-133">Permite restablecer el estado del identificador de solicitud especificado a “G - Verde”, después de solicitarle la confirmación.</span><span class="sxs-lookup"><span data-stu-id="650af-133">Lets you reset the status of the specified Request ID to "G - Green", after prompting you for confirmation.</span></span> <span data-ttu-id="650af-134">Esto puede resultar útil en caso de que se produzcan problemas y el sistema SAP Netweaver BW haya marcado la solicitud con un estado de amarillo o rojo.</span><span class="sxs-lookup"><span data-stu-id="650af-134">This can be useful when a problem has occurred, and the SAP Netweaver BW system has flagged the request with a yellow or red status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650af-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="650af-135">See Also</span></span>  
 <span data-ttu-id="650af-136">[Editor de origen de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="650af-136">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="650af-137">[Editor de origen de SAP BW &#40;página Columnas&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="650af-137">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="650af-138">[Editor de origen de SAP BW &#40;página Salida de error&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="650af-138">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="650af-139">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="650af-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
