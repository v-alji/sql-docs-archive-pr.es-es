---
title: Agregar una imagen externa (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 81fd4a1f-79a9-4967-86d6-6229413c0995
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8d0030c8f29b14b2c62048be306daa15948cd8d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744484"
---
# <a name="add-an-external-image-report-builder-and-ssrs"></a><span data-ttu-id="a051f-102">Agregar una imagen externa (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="a051f-102">Add an External Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a051f-103">Las imágenes externas pueden estar en un servidor de informes en modo nativo o en modo integrado de SharePoint, o en cualquier otro sitio web.</span><span class="sxs-lookup"><span data-stu-id="a051f-103">External images can be on a report server in native mode or SharePoint integrated mode, or on any other Web site.</span></span> <span data-ttu-id="a051f-104">Cuando se incluyen imágenes externas en un informe, se debe comprobar que existen y que el lector del informe dispone de los permisos necesarios para tener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="a051f-104">When you include external images in your report, you must verify that the image exists and that the report reader has permissions to access the image.</span></span> <span data-ttu-id="a051f-105">Para obtener más información, vea [Imágenes &#40;Generador de informes y SSRS&#41;](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a051f-105">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-external-image"></a><span data-ttu-id="a051f-106">Agregar una imagen externa</span><span class="sxs-lookup"><span data-stu-id="a051f-106">To add an external image</span></span>  
  
1.  <span data-ttu-id="a051f-107">En la vista de diseño del informe, en la pestaña **Insertar** , haga clic en **Imagen**.</span><span class="sxs-lookup"><span data-stu-id="a051f-107">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="a051f-108">En la superficie de diseño, haga clic en un cuadro y, a continuación, arrástrelo hasta obtener el tamaño de la imagen que desee.</span><span class="sxs-lookup"><span data-stu-id="a051f-108">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="a051f-109">En la pestaña **General** del cuadro de diálogo **Propiedades de la imagen** , escriba un nombre en el cuadro de texto **Nombre** o acepte el nombre predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a051f-109">On the **General** tab of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="a051f-110">(Opcional) En el cuadro de texto **Información sobre herramientas** , escriba el texto que se mostrará cuando el usuario mantenga el mouse sobre la imagen en un informe representado para HTML.</span><span class="sxs-lookup"><span data-stu-id="a051f-110">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in a report rendered for HTML.</span></span>  
  
5.  <span data-ttu-id="a051f-111">En **Seleccionar el origen de la imagen**, seleccione **Externo**.</span><span class="sxs-lookup"><span data-stu-id="a051f-111">In **Select the image source**, select **External**.</span></span>  
  
     <span data-ttu-id="a051f-112">Para una imagen en un servidor de informes en modo nativo, escriba la ruta de acceso relativa de la imagen en el cuadro **Usar esta imagen** (por ejemplo, ../images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="a051f-112">For an image on a report server in native mode, type a relative path to the image in the **Use this image** box-for example, ../images/image1.jpg.</span></span>  
  
     <span data-ttu-id="a051f-113">En el caso de una imagen en un servidor de informes en el modo integrado de SharePoint, o en cualquier otro sitio web, escriba una dirección URL completa de la imagen en el cuadro **usar esta imagen** (por ejemplo, http:// \<SharePointservername> / \<site> /Documents/images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="a051f-113">For an image on a report server in SharePoint integrated mode, or any other Web site, type a full URL to the image in the **Use this image** box-for example, http://\<SharePointservername>/\<site>/Documents/images/image1.jpg.</span></span>  
  
     <span data-ttu-id="a051f-114">Para más información, vea [Especificar las rutas de acceso a los elementos externos &#40;Generador de informes y SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a051f-114">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="a051f-115">(Opcional) Haga clic en **Tamaño**, **Visibilidad**, **Acción**o **Borde** si quiere establecer propiedades adicionales para el elemento de informe de imagen.</span><span class="sxs-lookup"><span data-stu-id="a051f-115">(Optional) Click **Size**, **Visibility**, **Action**, or **Border** to set additional properties for the image report item.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a051f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a051f-116">See Also</span></span>  
 <span data-ttu-id="a051f-117">[Incrustar una imagen en un informe &#40;Generador de informes y SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a051f-117">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a051f-118">[Agregar una imagen de fondo &#40;Generador de informes y SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a051f-118">[Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a051f-119">Cuadro de diálogo de Propiedades de la imagen, General &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a051f-119">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
