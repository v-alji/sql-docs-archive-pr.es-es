---
title: Cuadro de diálogo Propiedades de la imagen, general (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10051"
- sql12.rtp.rptdesigner.pictureproperties.general.f1
ms.assetid: c2218b93-f7fe-46ef-995f-d7dadf9752ec
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e599a437ae367a38483dbde99ffff79f64b957ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751889"
---
# <a name="image-properties-dialog-box-general-report-builder-and-ssrs"></a><span data-ttu-id="23492-102">Cuadro de diálogo de Propiedades de la imagen, General (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="23492-102">Image Properties Dialog Box, General (Report Builder and SSRS)</span></span>
  <span data-ttu-id="23492-103">Seleccione **General** en el cuadro de diálogo **Propiedades de la imagen** para agregar una imagen, cambiar el nombre predeterminado de la imagen y agregar texto de información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="23492-103">Select **General** on the **Image Properties** dialog box to add a picture, change the default name of the image, and add ToolTip text.</span></span>  
  
## <a name="options"></a><span data-ttu-id="23492-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="23492-104">Options</span></span>  
 <span data-ttu-id="23492-105">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="23492-105">**Name**</span></span>  
 <span data-ttu-id="23492-106">Escriba el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="23492-106">Type a name for the item.</span></span> <span data-ttu-id="23492-107">El nombre debe ser único en el informe.</span><span class="sxs-lookup"><span data-stu-id="23492-107">The name must be unique within the report.</span></span> <span data-ttu-id="23492-108">De forma predeterminada, se asigna un nombre general como Image1 o Image2.</span><span class="sxs-lookup"><span data-stu-id="23492-108">By default, a general name, such as Image1 or Image2, is assigned.</span></span>  
  
 <span data-ttu-id="23492-109">**Información sobre herramientas**</span><span class="sxs-lookup"><span data-stu-id="23492-109">**Tooltip**</span></span>  
 <span data-ttu-id="23492-110">Escriba texto o una expresión que dé como resultado una información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="23492-110">Type text or an expression that evaluates to a ToolTip.</span></span> <span data-ttu-id="23492-111">Haga clic en el botón Expresión (*fx*) para editar la expresión.</span><span class="sxs-lookup"><span data-stu-id="23492-111">Click the Expression (*fx*) button to edit the expression.</span></span> <span data-ttu-id="23492-112">La **información sobre herramientas** aparece cuando el usuario pausa el puntero sobre el elemento en un informe HTML.</span><span class="sxs-lookup"><span data-stu-id="23492-112">The **Tooltip** appears when the user pauses the pointer over the item in an HTML report.</span></span>  
  
 <span data-ttu-id="23492-113">**Seleccionar el origen de la imagen**</span><span class="sxs-lookup"><span data-stu-id="23492-113">**Select the image source**</span></span>  
 <span data-ttu-id="23492-114">Indique dónde se encuentra almacenada la imagen para que al representar el informe, el procesador de informes sepa dónde puede obtenerla.</span><span class="sxs-lookup"><span data-stu-id="23492-114">Indicate where the image is stored so that when the report is rendered, the report processor will know where to get the image from.</span></span>  
  
-   <span data-ttu-id="23492-115">**Externo** : elija esta opción si desea que la imagen continúe existiendo como archivo en un servidor de informes o en un servidor web.</span><span class="sxs-lookup"><span data-stu-id="23492-115">**External** Choose this option when you want the image to continue to exist as a file on a report server or Web server.</span></span>  
  
-   <span data-ttu-id="23492-116">**Incrustada** : elija esta opción si desea incrustar la imagen en el informe.</span><span class="sxs-lookup"><span data-stu-id="23492-116">**Embedded** Choose this option when you want to embed the image into the report.</span></span>  
  
-   <span data-ttu-id="23492-117">**Base de datos** : elija esta opción si desea incluir un nombre de campo de base de datos que representa las imágenes que se van a incluir en el informe seleccionado.</span><span class="sxs-lookup"><span data-stu-id="23492-117">**Database** Choose this option when you want to include a database field name that represents the images that you want to include in your report.</span></span>  
  
 <span data-ttu-id="23492-118">**Usar esta imagen**</span><span class="sxs-lookup"><span data-stu-id="23492-118">**Use this image**</span></span>  
 <span data-ttu-id="23492-119">Esta opción aparece al seleccionar la opción **Incrustada** o **Externo** .</span><span class="sxs-lookup"><span data-stu-id="23492-119">This option appears when you select the **Embedded** or **External** option.</span></span>  
  
 <span data-ttu-id="23492-120">Si va a incrustar la imagen, elija la imagen que desea agregar al informe en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="23492-120">If you are embedding the image, choose the image that you want to add to the report from the drop-down list.</span></span> <span data-ttu-id="23492-121">Haga clic en el botón **Importar** para agregar la imagen a la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="23492-121">Click the **Import** button to add the image to the drop-down list.</span></span>  
  
 <span data-ttu-id="23492-122">Si selecciona la opción **Externo** , escriba la dirección URL de la imagen.</span><span class="sxs-lookup"><span data-stu-id="23492-122">If you select the **External** option, type the URL of the image.</span></span> <span data-ttu-id="23492-123">En el caso de un informe publicado en un servidor de informes configurado para el modo nativo, use una ruta de acceso completa o relativa.</span><span class="sxs-lookup"><span data-stu-id="23492-123">For a report published to a report server configured for native mode, use a full or relative path.</span></span> <span data-ttu-id="23492-124">Por ejemplo, http:// \<servername> /images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="23492-124">For example, http://\<servername>/images/image1.jpg.</span></span> <span data-ttu-id="23492-125">En el caso de un informe publicado en un servidor de informes configurado en el modo integrado de SharePoint, utilice una dirección URL completa.</span><span class="sxs-lookup"><span data-stu-id="23492-125">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL.</span></span> <span data-ttu-id="23492-126">Por ejemplo, http:// \<*SharePointservername*> / \<*site*> /Documents/images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="23492-126">For example, http://\<*SharePointservername*>/\<*site*>/Documents/images/image1.jpg.</span></span>  
  
 <span data-ttu-id="23492-127">**Importar**</span><span class="sxs-lookup"><span data-stu-id="23492-127">**Import**</span></span>  
 <span data-ttu-id="23492-128">Haga clic en esta opción para agregar una imagen a la lista desplegable **Usar esta imagen** .</span><span class="sxs-lookup"><span data-stu-id="23492-128">Click to add an image to the **Use this image** drop-down list.</span></span>  
  
 <span data-ttu-id="23492-129">**Usar este campo**</span><span class="sxs-lookup"><span data-stu-id="23492-129">**Use this field**</span></span>  
 <span data-ttu-id="23492-130">Esta opción aparece si selecciona la opción **Base de datos** .</span><span class="sxs-lookup"><span data-stu-id="23492-130">This option appears if you select the **Database** option.</span></span> <span data-ttu-id="23492-131">Seleccione el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="23492-131">Select the field name.</span></span>  
  
 <span data-ttu-id="23492-132">**Usar este tipo MIME**</span><span class="sxs-lookup"><span data-stu-id="23492-132">**Use this MIME type**</span></span>  
 <span data-ttu-id="23492-133">Elija el formato adecuado de las imágenes contenidas en la base de datos (por ejemplo, .bmp, .jpeg, .gif, .png y .x-png).</span><span class="sxs-lookup"><span data-stu-id="23492-133">Choose the appropriate format of the images contained in the database, for example, .bmp, .jpeg, .gif, .png, and .x-png.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23492-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23492-134">See Also</span></span>  
 <span data-ttu-id="23492-135">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="23492-135">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="23492-136">[Imágenes &#40;Generador de informes y SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="23492-136">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="23492-137">Ayuda del Generador de informes para cuadros de diálogo, paneles y asistentes</span><span class="sxs-lookup"><span data-stu-id="23492-137">Report Builder Help for Dialog Boxes, Panes, and Wizards</span></span>](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md)  
  
  
