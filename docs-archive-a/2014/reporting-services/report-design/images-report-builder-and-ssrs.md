---
title: Imágenes (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fcc2db5c-5c26-4607-ae2b-f65c80360536
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f0840a10cc1082ba8dc7912862f7cf34c64972d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745050"
---
# <a name="images-report-builder-and-ssrs"></a><span data-ttu-id="96f55-102">Imágenes (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="96f55-102">Images (Report Builder and SSRS)</span></span>
  <span data-ttu-id="96f55-103">Una imagen es un elemento de informe que contiene una referencia a una imagen incrustada en el informe, o almacenada en una base de datos, en el servidor de informes o en cualquier lugar de Internet.</span><span class="sxs-lookup"><span data-stu-id="96f55-103">An image is a report item that contains a reference to an image that is embedded in the report, stored in a database, stored on the report server, or stored elsewhere on the Web.</span></span> <span data-ttu-id="96f55-104">Una imagen puede ser una imagen que se repite con filas de datos.</span><span class="sxs-lookup"><span data-stu-id="96f55-104">An image can be a picture that is repeated with rows of data.</span></span> <span data-ttu-id="96f55-105">También se puede utilizar una imagen como fondo para determinados elementos del informe.</span><span class="sxs-lookup"><span data-stu-id="96f55-105">You can also use an image as a background for certain report items.</span></span>  
  
 <span data-ttu-id="96f55-106">Almacenar los logotipos en un servidor es una buena idea porque puede utilizar el mismo logotipo en muchos informes.</span><span class="sxs-lookup"><span data-stu-id="96f55-106">Storing logos on a server is a good idea because you can use the same logo in many reports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="comparing-external-embedded-and-data-bound-images"></a><a name="ComparingImages"></a> <span data-ttu-id="96f55-107">Comparar imágenes externas, incrustadas y enlazadas a datos</span><span class="sxs-lookup"><span data-stu-id="96f55-107">Comparing External, Embedded, and Data-Bound Images</span></span>  
 <span data-ttu-id="96f55-108">Al utilizar una imagen que está en un servidor o en una ubicación externa, el elemento de imagen contiene una ruta de acceso que señala a una imagen del servidor de informes o de su ubicación en Internet.</span><span class="sxs-lookup"><span data-stu-id="96f55-108">When you use a server-based or other external image in a report, the image item contains a path that points to an image on the report server or wherever it exists on the Web.</span></span> <span data-ttu-id="96f55-109">No obstante, si se utiliza una imagen incrustada, los datos de dicha imagen se almacenan en la definición de informe y no existe en este caso un archivo independiente.</span><span class="sxs-lookup"><span data-stu-id="96f55-109">When you use an embedded image, however, the image data is stored within the report definition and does not exist as a separate file.</span></span>  
  
 <span data-ttu-id="96f55-110">Las imágenes basadas en servidor están especialmente indicadas para los logotipos e imágenes estáticas que comparten varios informes o páginas web.</span><span class="sxs-lookup"><span data-stu-id="96f55-110">Server-based images work well for logos and static pictures that are shared among several reports or Web pages.</span></span> <span data-ttu-id="96f55-111">Las imágenes incrustadas, por su parte, garantizan una disponibilidad permanente en el informe, pero no se pueden compartir.</span><span class="sxs-lookup"><span data-stu-id="96f55-111">Embedded images ensure that the images are always available to the report, but they cannot be shared.</span></span> <span data-ttu-id="96f55-112">Las definiciones de informe con imágenes externas son más pequeñas que las definiciones con imágenes incrustadas.</span><span class="sxs-lookup"><span data-stu-id="96f55-112">Report definitions with external images are smaller than definitions with embedded images.</span></span>  
  
 <span data-ttu-id="96f55-113">También se pueden mostrar imágenes enlazadas a datos a partir de datos binarios almacenados en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="96f55-113">Data-bound images can also be displayed from binary data stored in a database.</span></span> <span data-ttu-id="96f55-114">Por ejemplo, las imágenes que aparecen junto a los nombres de producto de una lista de productos son imágenes de base de datos.</span><span class="sxs-lookup"><span data-stu-id="96f55-114">For example, the pictures that appear alongside product names in a product list are database images.</span></span> <span data-ttu-id="96f55-115">En la siguiente imagen, las imágenes de bicicletas están almacenadas en una base de datos y se recuperan en el informe para ilustrar cada producto.</span><span class="sxs-lookup"><span data-stu-id="96f55-115">In the following picture, the images of bicycles are stored in a database and retrieved in the report to illustrate each product.</span></span>  
  
 <span data-ttu-id="96f55-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span><span class="sxs-lookup"><span data-stu-id="96f55-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span></span>  
  

  
##  <a name="images-as-report-parts"></a><a name="ImagesReportParts"></a> <span data-ttu-id="96f55-117">Imágenes como elementos de informe</span><span class="sxs-lookup"><span data-stu-id="96f55-117">Images as Report Parts</span></span>  
 <span data-ttu-id="96f55-118">Puede guardar imágenes por separado de un informe como elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="96f55-118">You can save images separately from a report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 
  
##  <a name="embedding-images"></a><a name="EmbedImages"></a> <span data-ttu-id="96f55-119">Incrustar imágenes</span><span class="sxs-lookup"><span data-stu-id="96f55-119">Embedding Images</span></span>  
 <span data-ttu-id="96f55-120">Se pueden incrustar imágenes en un informe de manera que todos los datos de imagen se almacenen en la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="96f55-120">You can embed images in a report so that all image data is stored within the report definition.</span></span> <span data-ttu-id="96f55-121">Cuando se incrusta una imagen, esta se codifica como MIME y se almacena como texto en la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="96f55-121">When you embed an image, the image is MIME-encoded and stored as text in the report definition.</span></span> <span data-ttu-id="96f55-122">El uso de imágenes incrustadas garantiza su disponibilidad permanente en el informe, pero también aumenta el tamaño de la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="96f55-122">Using an embedded image ensures that the image is always available to the report, but it also increases the size of the report definition.</span></span>  
  
 <span data-ttu-id="96f55-123">Para obtener más información sobre cómo insertar una imagen, vea [Incrustar una imagen en un informe &#40;Generador de informes y SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="96f55-123">For more information about embedding an image, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="external-images"></a><a name="ExternalImages"></a> <span data-ttu-id="96f55-124">Imágenes externas</span><span class="sxs-lookup"><span data-stu-id="96f55-124">External Images</span></span>  
 <span data-ttu-id="96f55-125">Puede incluir imágenes almacenadas en un informe especificando una dirección URL para la imagen.</span><span class="sxs-lookup"><span data-stu-id="96f55-125">You can include stored images in a report by specifying a URL to the image.</span></span> <span data-ttu-id="96f55-126">Cuando se utiliza una imagen externa en un informe, el origen de la imagen se establece en `External` y el valor de la imagen es su dirección URL o ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="96f55-126">When you use an external image in a report, the image source is set to `External` and the value for the image is the URL address or path to the image.</span></span>  
  
 <span data-ttu-id="96f55-127">Para más información, vea [Especificar las rutas de acceso a los elementos externos &#40;Generador de informes y SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="96f55-127">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="96f55-128">Cuando el informe se ejecuta en el Generador de informes o en el Diseñador de informes, la vista previa usa las credenciales del usuario para mostrar la imagen.</span><span class="sxs-lookup"><span data-stu-id="96f55-128">When the report is run in Report Builder or Report Designer, preview uses the credentials of the user to display the image.</span></span> <span data-ttu-id="96f55-129">Cuando el informe se ejecuta en el servidor de informes, no se puede mostrar la imagen del informe si las credenciales del servidor no son suficientes para tener acceso a la imagen.</span><span class="sxs-lookup"><span data-stu-id="96f55-129">When the report is run on the report server, the image in the report may not be displayed if the server credentials are not sufficient to access the image.</span></span> <span data-ttu-id="96f55-130">En ese caso, póngase en contacto con su administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="96f55-130">In that case, contact your system administrator.</span></span>  
  
 <span data-ttu-id="96f55-131">Para obtener más información sobre cómo agregar una imagen externa a un informe, vea [Agregar una imagen externa &#40;Generador de informes y SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="96f55-131">For more information about adding an external image to a report, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="background-images"></a><a name="BackgroundImages"></a> <span data-ttu-id="96f55-132">Imágenes de fondo</span><span class="sxs-lookup"><span data-stu-id="96f55-132">Background Images</span></span>  
 <span data-ttu-id="96f55-133">Puede utilizarse una imagen como imagen de fondo en el cuerpo del informe o en el interior de un rectángulo, cuadro de texto, lista, matriz o tabla.</span><span class="sxs-lookup"><span data-stu-id="96f55-133">You can use an image as a background image in the body of the report or in a rectangle, text box, list, matrix, or table.</span></span> <span data-ttu-id="96f55-134">Las imágenes de fondo tienen propiedades similares a las de las demás imágenes.</span><span class="sxs-lookup"><span data-stu-id="96f55-134">A background image and an image have similar properties.</span></span> <span data-ttu-id="96f55-135">También es posible especificar el modo de repetición de una imagen para rellenar el fondo de un elemento.</span><span class="sxs-lookup"><span data-stu-id="96f55-135">You can also specify how the image is repeated to fill the background of the item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96f55-136">Algunas extensiones de representación, como la extensión de representación en HTML, representan la imagen de fondo del cuerpo del informe en el cuerpo, el encabezado de página y el pie de página.</span><span class="sxs-lookup"><span data-stu-id="96f55-136">Some rendering extensions, like the HTML rendering extension, render the background image for the report body in the body, the page header, and the page footer.</span></span> <span data-ttu-id="96f55-137">Se puede definir una imagen de fondo diferente para el encabezado y pie de página, pero, si no se define ninguna, el informe usa la imagen de fondo del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="96f55-137">You can define a separate background image for the page header and footer, but if no image is defined, the report uses the background image of the body.</span></span> <span data-ttu-id="96f55-138">Otras extensiones de representación, como la extensión de representación en imágenes, no representan la imagen de fondo del cuerpo en el encabezado y pie de página.</span><span class="sxs-lookup"><span data-stu-id="96f55-138">Other rendering extensions, like the Image rendering extension, do not render the body background image in the page header and footer.</span></span>  
  
 <span data-ttu-id="96f55-139">Para obtener más información sobre cómo agregar una imagen de fondo, vea [Agregar una imagen de fondo &#40;Generador de informes y SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="96f55-139">For more information about adding a background image, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="data-bound-images"></a><a name="DataboundImages"></a> <span data-ttu-id="96f55-140">Imágenes enlazadas a datos</span><span class="sxs-lookup"><span data-stu-id="96f55-140">Data-bound Images</span></span>  
 <span data-ttu-id="96f55-141">Es posible agregar imágenes almacenadas en una base de datos a los informes.</span><span class="sxs-lookup"><span data-stu-id="96f55-141">You can add images that are stored in a database to your report.</span></span> <span data-ttu-id="96f55-142">Se puede usar el mismo elemento de informe de imagen que para las imágenes estáticas, pero con un conjunto de propiedades que indica que la imagen está almacenada en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="96f55-142">You use the same image report item as the one used for static images, but with a set of properties that indicate that the image is stored in a database.</span></span> <span data-ttu-id="96f55-143">Para obtener instrucciones sobre cómo trabajar con imágenes enlazadas a datos, vea [Agregar una imagen enlazada a datos &#40;Generador de informes y SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="96f55-143">To view instructions about working with data-bound images, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a> <span data-ttu-id="96f55-144">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="96f55-144">How-to Topics</span></span>  
 [<span data-ttu-id="96f55-145">Agregar una imagen externa &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="96f55-145">Add an External Image &#40;Report Builder and SSRS&#41;</span></span>](add-an-external-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="96f55-146">Incrustar una imagen en un informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="96f55-146">Embed an Image in a Report &#40;Report Builder and SSRS&#41;</span></span>](embed-an-image-in-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="96f55-147">Agregar una imagen de fondo &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="96f55-147">Add a Background Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-background-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="96f55-148">Agregar una imagen enlazada a datos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="96f55-148">Add a Data-Bound Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-data-bound-image-report-builder-and-ssrs.md)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="96f55-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96f55-149">See Also</span></span>  
 <span data-ttu-id="96f55-150">[Exportar a un archivo de imagen &#40;Generador de informes y SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="96f55-150">[Exporting to an Image File &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="96f55-151">Comportamientos de la representación &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="96f55-151">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
