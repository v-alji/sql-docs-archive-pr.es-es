---
title: Cambiar iconos de indicador y conjuntos de indicadores (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8a056adf-4473-473d-9b0c-314675af7bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 398d21319ab6da22f2b10c3607baf8f110d6e65b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748645"
---
# <a name="change-indicator-icons-and-indicator-sets-report-builder-and-ssrs"></a><span data-ttu-id="4d049-102">Cambiar iconos de indicador y conjuntos de indicadores (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="4d049-102">Change Indicator Icons and Indicator Sets (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="4d049-103">proporciona conjuntos de indicadores preconfigurados, que es posible que no siempre representen los datos de manera eficaz y funcionen bien en el informe entregado.</span><span class="sxs-lookup"><span data-stu-id="4d049-103">provides preconfigured indicators sets, which might not always depict your data effectively and work well in the delivered report.</span></span> <span data-ttu-id="4d049-104">En este tema se ofrecen procedimientos para cambiar la apariencia de los iconos de indicador y cambiar los conjuntos de indicadores para que contengan más o menos iconos, o iconos distintos.</span><span class="sxs-lookup"><span data-stu-id="4d049-104">This topic provides procedures to change the appearance of indicator icons and change the indicator sets to include different, more, or fewer indicator icons.</span></span>  
  
 <span data-ttu-id="4d049-105">Opciones como los colores se pueden establecer mediante expresiones.</span><span class="sxs-lookup"><span data-stu-id="4d049-105">Options such as colors can be set by using expressions.</span></span> <span data-ttu-id="4d049-106">Para más información, vea [Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4d049-106">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-color-of-an-indicator-icon"></a><span data-ttu-id="4d049-107">Para cambiar el color de un icono de indicador</span><span class="sxs-lookup"><span data-stu-id="4d049-107">To change the color of an indicator icon</span></span>  
  
1.  <span data-ttu-id="4d049-108">Haga clic con el botón derecho en el indicador que quiera cambiar y seleccione **Propiedades de indicador**.</span><span class="sxs-lookup"><span data-stu-id="4d049-108">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="4d049-109">Haga clic en **Valores y estados** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4d049-109">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="4d049-110">Haga clic en la flecha hacia abajo de la columna **Color** , al lado del icono que desea cambiar, y haga clic en el color que se debe usar, en **Ningún color**o en **Más colores**.</span><span class="sxs-lookup"><span data-stu-id="4d049-110">Click the down arrow in the **Color** column next to the icon that you want to change and click the color to use, **No Color**, or **More colors**.</span></span>  
  
     <span data-ttu-id="4d049-111">Si quiere, haga clic en el botón **Expresión** (*fx*) para modificar la expresión que establece el valor de la opción **Color** .</span><span class="sxs-lookup"><span data-stu-id="4d049-111">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Color** option.</span></span>  
  
     <span data-ttu-id="4d049-112">Si hace clic en **Más colores**, se abre el cuadro de diálogo **Seleccionar color** , en el que puede elegir entre muchos colores.</span><span class="sxs-lookup"><span data-stu-id="4d049-112">If you clicked **More Colors**, the **Select Color** dialog box opens, where you can choose from a wide array of colors.</span></span> <span data-ttu-id="4d049-113">Para obtener más información sobre las opciones, vea [Cuadro de diálogo Seleccionar color &#40;Generador de informes y SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4d049-113">For more information about its options, see [Select Color Dialog Box &#40;Report Builder and SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="4d049-114">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Seleccionar color** .</span><span class="sxs-lookup"><span data-stu-id="4d049-114">Click **OK** to close the **Select Color** dialog box.</span></span>  
  
4.  <span data-ttu-id="4d049-115">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d049-115">Click **OK**.</span></span>  
  
### <a name="to-change-the-icon"></a><span data-ttu-id="4d049-116">Para cambiar el icono</span><span class="sxs-lookup"><span data-stu-id="4d049-116">To change the icon</span></span>  
  
1.  <span data-ttu-id="4d049-117">Haga clic con el botón derecho en el indicador que quiera cambiar y seleccione **Propiedades de indicador**.</span><span class="sxs-lookup"><span data-stu-id="4d049-117">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="4d049-118">Haga clic en **Valores y estados** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4d049-118">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="4d049-119">Haga clic en la flecha hacia abajo que hay al lado del icono que desea cambiar y seleccione otro icono.</span><span class="sxs-lookup"><span data-stu-id="4d049-119">Click the down arrow next to the icon that you want to change and select a different icon.</span></span>  
  
     <span data-ttu-id="4d049-120">Si quiere, haga clic en el botón **Expresión** (*fx*) para modificar la expresión que establece el valor de la opción **Icono** .</span><span class="sxs-lookup"><span data-stu-id="4d049-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Icon** option.</span></span>  
  
4.  <span data-ttu-id="4d049-121">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d049-121">Click **OK**.</span></span>  
  
### <a name="to-use-a-custom-image-as-an-indicator-icon"></a><span data-ttu-id="4d049-122">Para usar una imagen personalizada como icono de indicador</span><span class="sxs-lookup"><span data-stu-id="4d049-122">To use a custom image as an indicator icon</span></span>  
  
1.  <span data-ttu-id="4d049-123">Haga clic con el botón derecho en el indicador que quiera cambiar y seleccione **Propiedades de indicador**.</span><span class="sxs-lookup"><span data-stu-id="4d049-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="4d049-124">Haga clic en **Valores y estados** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4d049-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="4d049-125">Haga clic en la flecha hacia abajo que hay al lado del icono que desea cambiar y seleccione **Imagen**.</span><span class="sxs-lookup"><span data-stu-id="4d049-125">Click the down arrow next to the icon that you wan to change and select **Image**.</span></span>  
  
4.  <span data-ttu-id="4d049-126">En la lista **Seleccionar el origen de la imagen** , haga clic en **Externo**, **Incrustado**o **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="4d049-126">In the **Select the image source** list, click **External**, **Embedded**, or **Database**.</span></span>  
  
5.  <span data-ttu-id="4d049-127">Dependiendo del origen de la imagen, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4d049-127">Depending on the source of the image, do the one of the following:</span></span>  
  
    -   <span data-ttu-id="4d049-128">Para utilizar una imagen almacenada fuera del informe, haga clic en **Examinar** y busque la imagen.</span><span class="sxs-lookup"><span data-stu-id="4d049-128">To use an image that is stored externally to the report, click **Browse** and locate the image.</span></span> <span data-ttu-id="4d049-129">El informe incluirá una referencia a la imagen.</span><span class="sxs-lookup"><span data-stu-id="4d049-129">The report will include a reference to the image.</span></span>  
  
    -   <span data-ttu-id="4d049-130">Para utilizar una imagen que esté incrustada en el informe, haga clic en **Importar** y busque la imagen.</span><span class="sxs-lookup"><span data-stu-id="4d049-130">To use an image that is embedded in the report, click **Import** and locate the image.</span></span> <span data-ttu-id="4d049-131">La imagen se agregará a la definición de informe y se guardará con él.</span><span class="sxs-lookup"><span data-stu-id="4d049-131">The image will be added to the report definition and saved with it.</span></span>  
  
    -   <span data-ttu-id="4d049-132">Para usar una imagen que está en una base de datos, en la lista **Usar este campo** ,</span><span class="sxs-lookup"><span data-stu-id="4d049-132">To use an image that is in a database, in the **Use this field** list.</span></span> <span data-ttu-id="4d049-133">seleccione el campo en la lista y, a continuación, en la lista **Usar este tipo MIME** , seleccione el tipo MIME de la imagen.</span><span class="sxs-lookup"><span data-stu-id="4d049-133">select the field from the list and then in the **Use this MIME type** list, select the MIME type of the image.</span></span>  
  
6.  <span data-ttu-id="4d049-134">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d049-134">Click **OK**.</span></span>  
  
### <a name="to-add-an-icon-to-the-indicator-set"></a><span data-ttu-id="4d049-135">Para agregar un icono al conjunto de indicadores</span><span class="sxs-lookup"><span data-stu-id="4d049-135">To add an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="4d049-136">Haga clic con el botón derecho en el indicador que quiera cambiar y seleccione **Propiedades de indicador**.</span><span class="sxs-lookup"><span data-stu-id="4d049-136">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="4d049-137">Haga clic en **Valores y estados** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4d049-137">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="4d049-138">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4d049-138">Click **Add**.</span></span> <span data-ttu-id="4d049-139">Se agrega un indicador, utilizando el icono predeterminado y la opción **Ningún color** .</span><span class="sxs-lookup"><span data-stu-id="4d049-139">An indicator is added, using the default icon and the **No Color** option.</span></span>  
  
     <span data-ttu-id="4d049-140">Configure el indicador de forma que use el icono y el color que desee.</span><span class="sxs-lookup"><span data-stu-id="4d049-140">Configure the indictor to use the icon and color you want.</span></span> <span data-ttu-id="4d049-141">En procedimientos anteriores de este tema se describe cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="4d049-141">Procedures earlier in this topic describe the steps to do this.</span></span>  
  
4.  <span data-ttu-id="4d049-142">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d049-142">Click **OK**.</span></span>  
  
### <a name="to-delete-an-icon-to-the-indicator-set"></a><span data-ttu-id="4d049-143">Para eliminar un icono del conjunto de indicadores</span><span class="sxs-lookup"><span data-stu-id="4d049-143">To delete an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="4d049-144">Haga clic con el botón derecho en el indicador que quiera cambiar y seleccione **Propiedades de indicador**.</span><span class="sxs-lookup"><span data-stu-id="4d049-144">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="4d049-145">Haga clic en **Valores y estados** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4d049-145">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="4d049-146">Seleccione el icono que desea eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4d049-146">Select the icon to delete, and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="4d049-147">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d049-147">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d049-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d049-148">See Also</span></span>  
 [<span data-ttu-id="4d049-149">Indicadores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4d049-149">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
