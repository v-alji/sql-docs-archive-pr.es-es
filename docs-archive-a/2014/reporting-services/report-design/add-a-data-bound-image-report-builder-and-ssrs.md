---
title: Agregar una imagen enlazada a datos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df4c38d4-bfcc-41c4-aa6d-952ca6fd7a2e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ea85bdcd6eab04ff51c879a9e790b6e12f73a771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662568"
---
# <a name="add-a-data-bound-image-report-builder-and-ssrs"></a><span data-ttu-id="649a8-102">Agregar una imagen enlazada a datos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="649a8-102">Add a Data-Bound Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="649a8-103">Un informe puede incluir una referencia a una imagen que está almacenada en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="649a8-103">A report can include a reference to an image that is stored in a database.</span></span> <span data-ttu-id="649a8-104">Este tipo de imagen se conoce como *imagen enlazada a datos*.</span><span class="sxs-lookup"><span data-stu-id="649a8-104">Such an image is known as a *data-bound image*.</span></span> <span data-ttu-id="649a8-105">Las imágenes que aparecen junto a los nombres de producto de una lista de productos son ejemplos de imágenes enlazadas a datos.</span><span class="sxs-lookup"><span data-stu-id="649a8-105">The pictures that appear alongside product names in a product list are examples of data-bound images.</span></span>  
  
 <span data-ttu-id="649a8-106">Agregar una imagen enlazada a datos a un encabezado de página o a un pie de página requiere pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="649a8-106">Adding a data-bound image to a page header or page footer requires additional steps.</span></span> <span data-ttu-id="649a8-107">Para más información, vea [Encabezados y pies de página &#40;Generador de informes y SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="649a8-107">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-data-bound-image"></a><span data-ttu-id="649a8-108">Agregar una imagen enlazada a datos</span><span class="sxs-lookup"><span data-stu-id="649a8-108">To add a data-bound image</span></span>  
  
1.  <span data-ttu-id="649a8-109">En la vista de diseño del informe, cree una tabla con una conexión a un origen de datos y un conjunto de datos con un campo que contenga los datos binarios de la imagen.</span><span class="sxs-lookup"><span data-stu-id="649a8-109">In report design view, create a table with a data source connection and a dataset with a field that contains binary image data.</span></span> <span data-ttu-id="649a8-110">Para más información, vea [Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="649a8-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="649a8-111">Inserte una columna en la tabla.</span><span class="sxs-lookup"><span data-stu-id="649a8-111">Insert a column in your table.</span></span> <span data-ttu-id="649a8-112">Para más información, vea [Insertar o eliminar una columna &#40;Generador de informes y SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="649a8-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="649a8-113">En el menú **Insertar** , haga clic en **Imagen**y, a continuación, haga clic en la fila de datos de la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="649a8-113">On the **Insert** menu, click **Image**, and then click in the data row of the new column.</span></span>  
  
4.  <span data-ttu-id="649a8-114">En la página General del cuadro de diálogo **Propiedades de la imagen** , escriba un nombre en el cuadro de texto **Nombre** o acepte el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="649a8-114">On the General page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
5.  <span data-ttu-id="649a8-115">(Opcional) En el cuadro de texto **Información sobre herramientas** , escriba el texto que se debe mostrar cuando el usuario mantenga el mouse sobre la imagen en un informe representado para HTML.</span><span class="sxs-lookup"><span data-stu-id="649a8-115">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in the report rendered for HTML.</span></span>  
  
6.  <span data-ttu-id="649a8-116">En **Seleccionar el origen de la imagen**, seleccione **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="649a8-116">In **Select the image source**, select **Database**.</span></span>  
  
7.  <span data-ttu-id="649a8-117">En **Usar este campo**, seleccione el campo que contiene las imágenes en el informe.</span><span class="sxs-lookup"><span data-stu-id="649a8-117">In **Use this Field**, select the field that contains images in your report.</span></span>  
  
8.  <span data-ttu-id="649a8-118">En **Usar este tipo MIME**, seleccione el tipo MIME, o el formato de archivo, de la imagen, por ejemplo, bmp.</span><span class="sxs-lookup"><span data-stu-id="649a8-118">In **Use this MIME type**, select the MIME type, or file format, of the image-for example, bmp.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="649a8-119">Aparece un marcador de posición para la imagen en la superficie de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="649a8-119">An image placeholder appears on the report design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="649a8-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="649a8-120">See Also</span></span>  
 <span data-ttu-id="649a8-121">[Imágenes &#40;Generador de informes y SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="649a8-121">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="649a8-122">[Incrustar una imagen en un informe &#40;Generador de informes y SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="649a8-122">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="649a8-123">[Agregar una imagen externa &#40;Generador de informes y SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="649a8-123">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="649a8-124">Cuadro de diálogo de Propiedades de la imagen, General &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="649a8-124">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
