---
title: Especificar una imagen como puntero en un medidor (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d73b3c3-a068-4868-a2be-0cd261b6e92b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c694cdb90fb668c43eb7e9971bba967bad8dd9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747431"
---
# <a name="specify-an-image-as-a-pointer-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="265c8-102">Especificar una imagen como puntero en un medidor (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="265c8-102">Specify an Image as a Pointer on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="265c8-103">El medidor contiene tres estilos integrados que se pueden usar para personalizar la apariencia del puntero.</span><span class="sxs-lookup"><span data-stu-id="265c8-103">The gauge contains three built-in styles that can be used to customize the appearance of the pointer.</span></span> <span data-ttu-id="265c8-104">En el caso de un medidor radial, los estilos integrados son: aguja, marcador y barra.</span><span class="sxs-lookup"><span data-stu-id="265c8-104">For a radial gauge, the built in styles are: Needle, Marker and Bar.</span></span> <span data-ttu-id="265c8-105">En el caso de un medidor lineal, los estilos integrados son: marcador, barra y termómetro.</span><span class="sxs-lookup"><span data-stu-id="265c8-105">For a linear gauge, the built-in styles are Marker, Bar, and Thermometer.</span></span> <span data-ttu-id="265c8-106">Si se requiere un puntero único, el usuario puede crear y especificar una imagen que se puede usar como un puntero totalmente funcional.</span><span class="sxs-lookup"><span data-stu-id="265c8-106">If a unique pointer is required, the user can create and specify an image which can be used as a fully functional pointer.</span></span>  
  
 <span data-ttu-id="265c8-107">Cuando se especifica una imagen para el puntero, dicha imagen debe tener las especificaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="265c8-107">When you are specifying an image for the pointer, your image must have the following specifications:</span></span>  
  
-   <span data-ttu-id="265c8-108">El origen del puntero, o centro de giro, debe estar en la parte superior de la imagen.</span><span class="sxs-lookup"><span data-stu-id="265c8-108">The origin of the pointer, or center of rotation, must be at the top of the image.</span></span>  
  
-   <span data-ttu-id="265c8-109">El final del puntero debe apuntar hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="265c8-109">The end of the pointer must be pointing down.</span></span>  
  
 <span data-ttu-id="265c8-110">Puesto que el puntero tiene forma irregular, deberá especificar un color de transparencia para ocultar las partes innecesarias de la imagen.</span><span class="sxs-lookup"><span data-stu-id="265c8-110">Since the pointer is an irregular shape, you will need to specify a transparency color to hide the unnecessary portions of the image.</span></span> <span data-ttu-id="265c8-111">Considere la posibilidad de usar un color que no se mostraría normalmente en el medidor como color de transparencia, ya que los colores especificados no aparecerán en el medidor.</span><span class="sxs-lookup"><span data-stu-id="265c8-111">Consider using a color that would not normally be shown on the gauge as the transparency color, since the colors specified will not appear on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-an-image-as-a-pointer-on-the-gauge"></a><span data-ttu-id="265c8-112">Especificar una imagen como un puntero en el medidor</span><span class="sxs-lookup"><span data-stu-id="265c8-112">To specify an image as a pointer on the gauge</span></span>  
  
1.  <span data-ttu-id="265c8-113">En la vista Diseño, haga clic en el puntero del medidor.</span><span class="sxs-lookup"><span data-stu-id="265c8-113">In Design view, click the pointer of the gauge.</span></span>  
  
2.  <span data-ttu-id="265c8-114">Opta Si no existe ningún puntero en el medidor, haga clic con el botón derecho en el medidor y seleccione **Agregar puntero**.</span><span class="sxs-lookup"><span data-stu-id="265c8-114">(Optional) If no pointer exists on the gauge, right-click on the gauge and select **Add Pointer**.</span></span> <span data-ttu-id="265c8-115">Se agregará un puntero al medidor.</span><span class="sxs-lookup"><span data-stu-id="265c8-115">A pointer is added to the gauge.</span></span>  
  
3.  <span data-ttu-id="265c8-116">Haga clic en la pestaña **Insertar** de la cinta de opciones y haga doble clic en el icono de imagen.</span><span class="sxs-lookup"><span data-stu-id="265c8-116">Click the **Insert** tab on the ribbon and double-click the image icon.</span></span> <span data-ttu-id="265c8-117">Se abrirá el cuadro de diálogo **Propiedades de la imagen**.</span><span class="sxs-lookup"><span data-stu-id="265c8-117">The **Image Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="265c8-118">Agregue una imagen al informe.</span><span class="sxs-lookup"><span data-stu-id="265c8-118">Add an image to your report.</span></span> <span data-ttu-id="265c8-119">Para obtener más información, vea [incrustar una imagen en un informe &#40;generador de informes y SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="265c8-119">For more information, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="265c8-120">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="265c8-120">Open the Properties pane.</span></span>  
  
6.  <span data-ttu-id="265c8-121">En la superficie de diseño, haga clic en el puntero.</span><span class="sxs-lookup"><span data-stu-id="265c8-121">On the design surface, click on the pointer.</span></span> <span data-ttu-id="265c8-122">Las propiedades del puntero se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="265c8-122">The properties for the pointer are displayed in the Properties pane.</span></span>  
  
7.  <span data-ttu-id="265c8-123">Expanda el nodo PointerImage.</span><span class="sxs-lookup"><span data-stu-id="265c8-123">Expand the PointerImage node.</span></span>  
  
8.  <span data-ttu-id="265c8-124">En **origen**, seleccione **incrustado** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="265c8-124">In **Source**, select **Embedded** from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="265c8-125">Si la imagen está almacenada en la base de datos o en Internet, puede especificar la opción adecuada para esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="265c8-125">If your image is stored in the database or on the web, you can specify the appropriate option for this property.</span></span> <span data-ttu-id="265c8-126">Para obtener más información, vea propiedades de la [imagen (cuadro de diálogo), General &#40;generador de informes y SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="265c8-126">For more information, see [Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span></span>  
  
9. <span data-ttu-id="265c8-127">En **valor**, seleccione el nombre de la imagen en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="265c8-127">In **Value**, select the name of your image from the drop-down list.</span></span>  
  
10. <span data-ttu-id="265c8-128">En **TransparentColor**, seleccione un valor de color que desee quitar de la imagen.</span><span class="sxs-lookup"><span data-stu-id="265c8-128">In **TransparentColor**, pick a color value that you want to remove from the image.</span></span> <span data-ttu-id="265c8-129">Esto creará un aspecto uniforme para el puntero en el medidor.</span><span class="sxs-lookup"><span data-stu-id="265c8-129">This will create a seamless appearance for the pointer in the gauge.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265c8-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="265c8-130">See Also</span></span>  
 <span data-ttu-id="265c8-131">[Aplicar formato a los punteros de un medidor &#40;Generador de informes y SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="265c8-131">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="265c8-132">[Agregar un medidor a un informe &#40;Generador de informes y SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="265c8-132">[Add a Gauge to a Report &#40;Report Builder and SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="265c8-133">[Aplicar formato a líneas, colores e imágenes &#40;Generador de informes y SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="265c8-133">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="265c8-134">Medidores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="265c8-134">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
