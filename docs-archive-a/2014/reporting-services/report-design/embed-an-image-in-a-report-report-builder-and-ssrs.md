---
title: Insertar una imagen en un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.embeddedimages.f1
- "10060"
ms.assetid: aed77345-5eeb-41f0-96c9-db6b4a11ec6f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6599092e0ef37dd9bbc15f4815c0315c77e7943b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743980"
---
# <a name="embed-an-image-in-a-report-report-builder-and-ssrs"></a><span data-ttu-id="dbc9d-102">Incrustar una imagen en un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="dbc9d-102">Embed an Image in a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dbc9d-103">Un informe puede incluir una imagen incrustada.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-103">A report can include an embedded image.</span></span> <span data-ttu-id="dbc9d-104">El empleo de imágenes incrustadas asegura su disponibilidad permanente en un informe, pero también afecta al tamaño de la definición de informe, el archivo que lo define.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-104">Embedding an image ensures that the image is always available to a report, but can affect the size of the report definition, the file that defines the report.</span></span> <span data-ttu-id="dbc9d-105">Las imágenes incrustadas en un informe se enumeran en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-105">The images embedded in a report are listed in the Report Data pane.</span></span>  
  
 <span data-ttu-id="dbc9d-106">Podría ser conveniente incrustar una imagen en la definición de informe antes de agregarla a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-106">You might want to embed an image in the report definition before adding the image to the design surface.</span></span> <span data-ttu-id="dbc9d-107">Para más información, vea [Agregar una imagen de fondo &#40;Generador de informes y SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dbc9d-107">For more information, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-a-report"></a><span data-ttu-id="dbc9d-108">Incrustar una imagen en un informe</span><span class="sxs-lookup"><span data-stu-id="dbc9d-108">To embed an image in a report</span></span>  
  
1.  <span data-ttu-id="dbc9d-109">En la vista de diseño del informe, en la pestaña **Insertar** , haga clic en **Imagen**.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-109">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="dbc9d-110">En la superficie de diseño, haga clic en un cuadro y, a continuación, arrástrelo hasta obtener el tamaño de la imagen que desee.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-110">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="dbc9d-111">En la página **General** del cuadro de diálogo **Propiedades de la imagen** , escriba un nombre en el cuadro de texto **Nombre** o acepte el nombre predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-111">In the **General** page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="dbc9d-112">(Opcional) En el cuadro de texto de **Información sobre herramientas** , escriba el texto que quiere que aparezca cuando el usuario mantenga el mouse sobre la imagen en el informe representado.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-112">(Optional) In the **ToolTip** text box, type the text that you want to appear when the user hovers over the image in the rendered report.</span></span>  
  
5.  <span data-ttu-id="dbc9d-113">En **Seleccionar el origen de la imagen**, seleccione **Incrustado**.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-113">In **Select the image source**, select **Embedded**.</span></span>  
  
6.  <span data-ttu-id="dbc9d-114">Hacer clic en el botón **Importar** al lado del cuadro de texto **Usar esta imagen**</span><span class="sxs-lookup"><span data-stu-id="dbc9d-114">Click the **Import** button next to the **Use this image** text box</span></span>  
  
7.  <span data-ttu-id="dbc9d-115">En **Archivos de tipo**, seleccione el tipo de archivo de imagen, navegue al archivo y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-115">In **Files of type**, select the image file type, navigate to the file, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="dbc9d-116">En el cuadro de diálogo **Propiedades de la imagen** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-116">In the **Image Properties** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="dbc9d-117">La imagen se muestra en el cuadro que dibujó en la superficie del diseño, y el archivo se muestra bajo la carpeta Imágenes en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-117">The image is displayed in the box you drew on the design surface, and the file is displayed under the Images folder in the Report Data pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbc9d-118">El tipo MIME (por ejemplo, bmp) se deriva automáticamente cuando se importa la imagen.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-118">The MIME type (for example, bmp) is derived automatically when the image is imported.</span></span> <span data-ttu-id="dbc9d-119">Para cambiar el tipo MIME, vea el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-119">To change the MIME type, see the next procedure.</span></span>  
  
### <a name="optional-to-change-the-mime-type-of-an-imported-image"></a><span data-ttu-id="dbc9d-120">(Opcional) Cambiar el tipo MIME de una imagen importada</span><span class="sxs-lookup"><span data-stu-id="dbc9d-120">(optional) To change the MIME type of an imported image</span></span>  
  
1.  <span data-ttu-id="dbc9d-121">Abra el informe en la vista Diseño.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-121">Open the report in Design view.</span></span>  
  
2.  <span data-ttu-id="dbc9d-122">Seleccione la imagen en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-122">Select the image on the design surface.</span></span> <span data-ttu-id="dbc9d-123">El panel **Propiedades** muestra las propiedades de la imagen.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-123">The **Properties** pane displays the image properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbc9d-124">Si el panel de propiedades no está visible, en la pestaña **Vista** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-124">If the Properties pane is not visible, on the **View** tab, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="dbc9d-125">Haga clic en el cuadro de texto situado junto a la propiedad **MIMEType** y seleccione un nuevo tipo MIME en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="dbc9d-125">Click in the text box next to the **MIMEType** property and select a new MIME type from the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc9d-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbc9d-126">See Also</span></span>  
 <span data-ttu-id="dbc9d-127">[Imágenes &#40;Generador de informes y SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dbc9d-127">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dbc9d-128">[Agregar una imagen enlazada a datos &#40;Generador de informes y SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dbc9d-128">[Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dbc9d-129">Cuadro de diálogo de Propiedades de la imagen, General &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dbc9d-129">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
