---
title: Agregar una imagen de fondo (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c777fefb-8695-44a7-b5cd-a18c587583f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7bc15e1b063a73c463cdb1e7e99075af2a3dce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749126"
---
# <a name="add-a-background-image-report-builder-and-ssrs"></a><span data-ttu-id="2230a-102">Agregar una imagen de fondo (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="2230a-102">Add a Background Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2230a-103">Puede agregar una imagen de fondo a un elemento del informe, como un rectángulo, cuadro de texto, lista, matriz, tabla y algunas partes de un gráfico; o a una sección del informe, como el encabezado de página, el pie de página o el cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="2230a-103">You can add a background image to a report item such as a rectangle, text box, list, matrix, table, and some parts of a chart, or a report section such as the page header, page footer, or report body.</span></span> <span data-ttu-id="2230a-104">Puede definir una imagen de fondo para cualquier elemento seleccionado en la superficie de diseño del informe que muestre **BackgroundImage** en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="2230a-104">You can define a background image for any selected item on the report design surface that displays **BackgroundImage** in the Properties pane.</span></span> <span data-ttu-id="2230a-105">Al igual que otras imágenes, la imagen de fondo puede ser una dirección URL a una imagen del servidor de informes, a una imagen de un campo de conjunto de datos o a una imagen incrustada en la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="2230a-105">Like other images, the background image can be a URL to an image on the report server, an image from a dataset field, or an image embedded in the report definition.</span></span> <span data-ttu-id="2230a-106">Para usar una imagen incrustada en el informe, primero debe agregar la imagen a la definición de informe, antes de agregarla a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="2230a-106">To use an image embedded in the report, you must first add the image to the report definition before you can add the image to the design surface.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-the-report-definition"></a><span data-ttu-id="2230a-107">Incrustar una imagen en la definición de informe</span><span class="sxs-lookup"><span data-stu-id="2230a-107">To embed an image in the report definition</span></span>  
  
1.  <span data-ttu-id="2230a-108">En el panel Datos de informe, haga clic con el botón derecho en el nodo **Imágenes** y, después, haga clic en **Agregar imagen**.</span><span class="sxs-lookup"><span data-stu-id="2230a-108">In the Report Data pane, right-click the **Images** node, and then click **Add Image**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2230a-109">Si el panel Datos de informe no está visible, haga clic en **Datos de informe** en la pestaña **Ver**.</span><span class="sxs-lookup"><span data-stu-id="2230a-109">If the Report Data pane is not visible, on the **View** tab, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="2230a-110">Navegue hasta la imagen que desea incrustar en la definición de informe y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2230a-110">Navigate to the image you want to embed in your report definition, and then click **OK**.</span></span>  
  
### <a name="to-add-a-background-image"></a><span data-ttu-id="2230a-111">Agregar una imagen de fondo</span><span class="sxs-lookup"><span data-stu-id="2230a-111">To add a background image</span></span>  
  
1.  <span data-ttu-id="2230a-112">En la vista de diseño del informe, seleccione el elemento de informe al que desea agregar una imagen de fondo.</span><span class="sxs-lookup"><span data-stu-id="2230a-112">In report design view, select the report item to which you want to add a background image.</span></span>  
  
2.  <span data-ttu-id="2230a-113">Si el panel de propiedades no está visible, en la pestaña **Ver** , seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2230a-113">If the Properties pane is not visible, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="2230a-114">En el panel de propiedades, expanda **BackgroundImage**y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2230a-114">In the Properties pane, expand **BackgroundImage**, and then do the following:</span></span>  
  
    -   <span data-ttu-id="2230a-115">Para una imagen incrustada:</span><span class="sxs-lookup"><span data-stu-id="2230a-115">For an embedded image:</span></span>  
  
         <span data-ttu-id="2230a-116">Establezca **Origen** en **Incrustada**.</span><span class="sxs-lookup"><span data-stu-id="2230a-116">Set **Source** to **Embedded**.</span></span>  
  
         <span data-ttu-id="2230a-117">Establezca **Valor** en el nombre de una imagen que esté incrustada en el informe.</span><span class="sxs-lookup"><span data-stu-id="2230a-117">Set **Value** to the name of an image that is embedded in the report.</span></span>  
  
    -   <span data-ttu-id="2230a-118">Para una imagen externa:</span><span class="sxs-lookup"><span data-stu-id="2230a-118">For an external image:</span></span>  
  
         <span data-ttu-id="2230a-119">Establezca **Origen** en **Externo**.</span><span class="sxs-lookup"><span data-stu-id="2230a-119">Set **Source** to **External**.</span></span>  
  
         <span data-ttu-id="2230a-120">Establezca **Valor** en una ruta de acceso válida a una imagen.</span><span class="sxs-lookup"><span data-stu-id="2230a-120">Set **Value** to a valid path to an image.</span></span> <span data-ttu-id="2230a-121">Puede tratarse de un servidor de informes en modo nativo o en modo integrado de SharePoint, o puede ser cualquier otro sitio web.</span><span class="sxs-lookup"><span data-stu-id="2230a-121">This can be on a report server in native mode or SharePoint integrated mode, or it can be on any other Web site.</span></span> <span data-ttu-id="2230a-122">Para más información, vea [Agregar una imagen externa &#40;Generador de informes y SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2230a-122">For more information, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
    -   <span data-ttu-id="2230a-123">Para una imagen que esté contenida en un campo en la base de datos a la que está conectado el elemento de informe:</span><span class="sxs-lookup"><span data-stu-id="2230a-123">For an image is that is contained in a field in the database to which the report item is connected:</span></span>  
  
         <span data-ttu-id="2230a-124">Establezca **Origen** en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="2230a-124">Set **Source** to **Database**.</span></span>  
  
         <span data-ttu-id="2230a-125">Establezca **Valor** en el nombre de un campo en el conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="2230a-125">Set **Value** to the name of a field in the report dataset.</span></span> <span data-ttu-id="2230a-126">Para más información, vea [Agregar una imagen enlazada a datos &#40;Generador de informes y SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2230a-126">For more information, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  
         <span data-ttu-id="2230a-127">En **MIMEType**, o el formato de archivo, seleccione el tipo MIME que corresponda a la imagen, por ejemplo, .bmp.</span><span class="sxs-lookup"><span data-stu-id="2230a-127">For **MIMEType**, or file format, select the appropriate MIME type for the image-for example, .bmp.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2230a-128">MIMEType solamente se aplica si la propiedad **Origen** se establece en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="2230a-128">MIMEType applies only if the **Source** property is set to **Database**.</span></span> <span data-ttu-id="2230a-129">Si la propiedad **Source** se establece como **External** o **Embedded**, el valor de **MIMEType** no se tiene en cuenta.</span><span class="sxs-lookup"><span data-stu-id="2230a-129">If the **Source** property is set to **External** or **Embedded**, the value of **MIMEType** is ignored.</span></span>  
  
    -   <span data-ttu-id="2230a-130">Para **BackgroundRepeat**, seleccione una expresión, **Default**, **Repeat**, **RepeatX**, o **RepeatY**o **Clip**.</span><span class="sxs-lookup"><span data-stu-id="2230a-130">For **BackgroundRepeat**, select an expression, **Default**, **Repeat**, **RepeatX**, or **RepeatY**, or **Clip**.</span></span>  
  
         <span data-ttu-id="2230a-131">Para las imágenes de fondo en los gráficos, **BackgroundRepeat** se puede establecer en **Default**, **Repeat**, **Fit**y **Clip**, pero no en **RepeatX** ni **RepeatY**.</span><span class="sxs-lookup"><span data-stu-id="2230a-131">For background images in a chart, **BackgroundRepeat** can be set to **Default**, **Repeat**, **Fit**, and **Clip**, but not **RepeatX** or **RepeatY**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2230a-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2230a-132">See Also</span></span>  
 <span data-ttu-id="2230a-133">[Imágenes &#40;Generador de informes y SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2230a-133">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2230a-134">Cuadro de diálogo de Propiedades de la imagen, General &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2230a-134">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
