---
title: Cuadro de diálogo relleno (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportbody.fill.f1
- "10065"
- "10501"
- sql12.rtp.rptdesigner.shared.filldv.f1
- sql12.rtp.rptdesigner.rectangleproperties.fill.f1
- "10064"
- sql12.rtp.rptdesigner.textboxproperties.fill.f1
- "10124"
ms.assetid: 93a91d02-d558-4a0e-8d17-3fdf21e208d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ae7f2b05d4d108c77f1dcae9ce7fefe5073e2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673502"
---
# <a name="fill-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="39cec-102">Cuadro de diálogo Relleno (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="39cec-102">Fill Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="39cec-103">En la pestaña **Relleno** , puede especificar opciones de color para el fondo de una o varias celdas dentro de una región de datos o de un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="39cec-103">On the **Fill** tab, you can specify color options for the background of a single cell or multiple cells within a data region or a text box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="39cec-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="39cec-104">Options</span></span>  
 <span data-ttu-id="39cec-105">**Color de relleno**</span><span class="sxs-lookup"><span data-stu-id="39cec-105">**Fill Color**</span></span>  
 <span data-ttu-id="39cec-106">Haga clic en el botón de color para seleccionar un color de relleno para el rectángulo.</span><span class="sxs-lookup"><span data-stu-id="39cec-106">Click the color button to select a fill color for the rectangle.</span></span> <span data-ttu-id="39cec-107">Haga clic en el botón **Expresión**_(fx)_ para editar la expresión, que puede ser un valor hexadecimal para el color RGB o uno de los nombres de colores predefinidos del cuadro de diálogo **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="39cec-107">Click the **Expression**_(fx)_ button to edit the expression, which can be a hexadecimal value for the RGB color or one of the predefined color names that are provided in the **Expression** dialog box.</span></span> <span data-ttu-id="39cec-108">Para ver una lista de los colores predefinidos, seleccione **Web** en el panel **Elemento**.</span><span class="sxs-lookup"><span data-stu-id="39cec-108">To see a list of predefined colors, in the **Item** pane, select **Web**.</span></span> <span data-ttu-id="39cec-109">Los nombres de colores del panel **Título** pueden escribirse en el panel de texto de expresiones.</span><span class="sxs-lookup"><span data-stu-id="39cec-109">The color names listed in the **Title** pane can be typed into the expression text pane.</span></span> <span data-ttu-id="39cec-110">No use el signo igual (=) ni comillas ("") cuando escriba el nombre del color.</span><span class="sxs-lookup"><span data-stu-id="39cec-110">Do not use an equal sign (=) or quotation marks ("") when typing the color name.</span></span>  
  
 <span data-ttu-id="39cec-111">**Seleccionar el origen de la imagen**</span><span class="sxs-lookup"><span data-stu-id="39cec-111">**Select the image source**</span></span>  
 <span data-ttu-id="39cec-112">Indique dónde se encuentra almacenada la imagen para que, a la hora de representar el informe, el procesador de informes pueda mostrarla.</span><span class="sxs-lookup"><span data-stu-id="39cec-112">Indicate where the image is stored so that when the report is rendered, the report processor can display it.</span></span>  
  
-   <span data-ttu-id="39cec-113">**Externo** : elija esta opción si desea que la imagen continúe existiendo como archivo en un servidor de informes o en un servidor web.</span><span class="sxs-lookup"><span data-stu-id="39cec-113">**External** Choose this option when you want the image to continue to exist as a file on a report server or Web server.</span></span>  
  
-   <span data-ttu-id="39cec-114">**Incrustada** : elija esta opción si desea incrustar la imagen en el informe.</span><span class="sxs-lookup"><span data-stu-id="39cec-114">**Embedded** Choose this option when you want to embed the image into the report.</span></span>  
  
-   <span data-ttu-id="39cec-115">**Base de datos** : elija esta opción si desea incluir un nombre de campo de base de datos que representa las imágenes que se van a incluir en el informe seleccionado.</span><span class="sxs-lookup"><span data-stu-id="39cec-115">**Database** Choose this option when you want to include a database field name that represents the images that you want to include in your report.</span></span>  
  
 <span data-ttu-id="39cec-116">**Usar esta imagen**</span><span class="sxs-lookup"><span data-stu-id="39cec-116">**Use this image**</span></span>  
 <span data-ttu-id="39cec-117">Esta opción aparece al seleccionar la opción **Incrustada** o **Externo** .</span><span class="sxs-lookup"><span data-stu-id="39cec-117">This option appears when you select the **Embedded** or **External** option.</span></span>  
  
 <span data-ttu-id="39cec-118">Si va a incrustar la imagen, elija la imagen que quiere agregar al informe en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="39cec-118">If you are embedding the image, choose the picture that you want to add to the report from the drop-down list.</span></span> <span data-ttu-id="39cec-119">Haga clic en **Importar** para agregar la imagen a la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="39cec-119">Click **Import** to add the image to the drop-down list.</span></span> <span data-ttu-id="39cec-120">Si agregó una imagen al panel **Datos** , podrá seleccionarla eligiendo **Incrustada** y seleccionando la imagen en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="39cec-120">If you added an image to the **Data** pane, you can select that image by choosing **Embedded** and then selecting the image from the drop-down list.</span></span>  
  
 <span data-ttu-id="39cec-121">Si selecciona la opción **Externo** , escriba la dirección URL de la imagen.</span><span class="sxs-lookup"><span data-stu-id="39cec-121">If you select the **External** option, type the URL of the image.</span></span> <span data-ttu-id="39cec-122">En el caso de un informe publicado en un servidor de informes configurado para el modo nativo, use una ruta de acceso completa o relativa (por ejemplo, http:// *\<servername>* /images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="39cec-122">For a report published to a report server configured for native mode, use a full or relative path (for example, http://*\<servername>*/images/image1.jpg).</span></span> <span data-ttu-id="39cec-123">En el caso de un informe publicado en un servidor de informes configurado en el modo integrado de SharePoint, use una dirección URL completa (por ejemplo, http:// *\<SharePointservername>/\<site>* /Documents/images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="39cec-123">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
 <span data-ttu-id="39cec-124">**Importar**</span><span class="sxs-lookup"><span data-stu-id="39cec-124">**Import**</span></span>  
 <span data-ttu-id="39cec-125">Esta opción está disponible cuando se selecciona **Incrustada**.</span><span class="sxs-lookup"><span data-stu-id="39cec-125">Available when you select **Embedded**.</span></span> <span data-ttu-id="39cec-126">Haga clic en esta opción para agregar una imagen a la lista desplegable **Usar esta imagen** .</span><span class="sxs-lookup"><span data-stu-id="39cec-126">Click to add an image to the **Use this image** drop-down list.</span></span>  
  
 <span data-ttu-id="39cec-127">**Usar este campo**</span><span class="sxs-lookup"><span data-stu-id="39cec-127">**Use this field**</span></span>  
 <span data-ttu-id="39cec-128">Esta opción está disponible cuando se selecciona **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="39cec-128">Available when you select **Database**.</span></span> <span data-ttu-id="39cec-129">Seleccione el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="39cec-129">Select the field name.</span></span>  
  
 <span data-ttu-id="39cec-130">**Usar este tipo MIME**</span><span class="sxs-lookup"><span data-stu-id="39cec-130">**Use this MIME type**</span></span>  
 <span data-ttu-id="39cec-131">Elija el formato adecuado de las imágenes contenidas en la base de datos (por ejemplo, .bmp, .jpeg, .gif, .png o .x-png).</span><span class="sxs-lookup"><span data-stu-id="39cec-131">Choose the appropriate format of the pictures contained in the database (for example, .bmp, .jpeg, .gif, .png, or .x-png).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39cec-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39cec-132">See Also</span></span>  
 <span data-ttu-id="39cec-133">[Aplicar formato a los elementos de informe &#40;Generador de informes y SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="39cec-133">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="39cec-134">[Aplicar formato a texto y a marcadores de posición &#40;Generador de informes y SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="39cec-134">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="39cec-135">Imágenes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="39cec-135">Images &#40;Report Builder and SSRS&#41;</span></span>](report-design/images-report-builder-and-ssrs.md)  
  
  
