---
title: Establecer la orientación del cuadro de texto (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 64bd53f4-2f31-4732-8c2e-64c7b54b6972
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d509f1df29203fa5def79b61b74ae9db8f40d204
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662546"
---
# <a name="set-text-box-orientation-report-builder-and-ssrs"></a><span data-ttu-id="6bfaf-102">Establecer la orientación del cuadro de texto (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="6bfaf-102">Set Text Box Orientation (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6bfaf-103">Un cuadro de texto se puede orientar en direcciones diferentes: horizontalmente, verticalmente (el texto se lee de arriba abajo) o girado 270 grados (el texto se lee de abajo arriba).</span><span class="sxs-lookup"><span data-stu-id="6bfaf-103">A text box can be oriented in different directions: horizontally, vertically (text reading from top to bottom), or rotated by 270 degrees (text reading from bottom to top).</span></span> <span data-ttu-id="6bfaf-104">Dado que la orientación se establece en el cuadro de texto y no en el texto, se aplica a todo el texto del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="6bfaf-104">Because orientation is set on the text box not the text, the orientation applies to all the text in the text box.</span></span> <span data-ttu-id="6bfaf-105">No puede especificar orientaciones diferentes para las partes del texto.</span><span class="sxs-lookup"><span data-stu-id="6bfaf-105">You cannot specify different orientations for parts of the text.</span></span> <span data-ttu-id="6bfaf-106">Debe establecer manualmente el ancho de columna y el alto de fila para alojar el texto girado.</span><span class="sxs-lookup"><span data-stu-id="6bfaf-106">Size the column width and the row height manually to accommodate the rotated text.</span></span>  
  
 <span data-ttu-id="6bfaf-107">La propiedad WritingMode, que se usa para especificar la orientación del texto, no está disponible en el cuadro de diálogo **propiedades de cuadro de texto** .</span><span class="sxs-lookup"><span data-stu-id="6bfaf-107">The WritingMode property, which you use to specify text orientation, is not available in the **Text Box Properties** dialog box.</span></span> <span data-ttu-id="6bfaf-108">Debe abrir el panel de propiedades y establecer la propiedad en él.</span><span class="sxs-lookup"><span data-stu-id="6bfaf-108">You need to open the Properties pane and set the property there.</span></span> <span data-ttu-id="6bfaf-109">Los valores disponibles para la propiedad WritingMode son **horizontales** (el texto se lee de izquierda a derecha), **vertical** (el texto se lee de arriba abajo), **Rotate270** (el texto se lee de abajo arriba).</span><span class="sxs-lookup"><span data-stu-id="6bfaf-109">The available values for the WritingMode property are **Horizontal** (text reading left to right), **Vertical** (text reading top to bottom), **Rotate270** (text reading bottom to top).</span></span> <span data-ttu-id="6bfaf-110">Debe establecer manualmente el ancho de columna y el alto de fila para alojar el texto.</span><span class="sxs-lookup"><span data-stu-id="6bfaf-110">You must manually size the column width and the row height to accommodate the text.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-text-orientation"></a><span data-ttu-id="6bfaf-111">Para establecer la orientación del texto</span><span class="sxs-lookup"><span data-stu-id="6bfaf-111">To set text orientation</span></span>  
  
1.  <span data-ttu-id="6bfaf-112">Cree un nuevo informe o abra un informe existente.</span><span class="sxs-lookup"><span data-stu-id="6bfaf-112">Create a new report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="6bfaf-113">Si el panel de propiedades no está abierto, haga clic en la pestaña **Ver** y active la casilla **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="6bfaf-113">If the Properties pane is not open, click the **View** tab and select the **Properties** check box.</span></span>  
  
3.  <span data-ttu-id="6bfaf-114">Haga clic en el cuadro de texto para el que desea cambiar la orientación del texto.</span><span class="sxs-lookup"><span data-stu-id="6bfaf-114">Click the text box for which you want to change text orientation.</span></span>  
  
4.  <span data-ttu-id="6bfaf-115">Busque la propiedad WritingMode en el panel Propiedades y, en la lista desplegable, seleccione la orientación del texto que se va a aplicar al cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="6bfaf-115">Locate the WritingMode property in the Properties pane and in the drop-down list select the text orientation to apply to the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6bfaf-116">Cuando las propiedades del panel de propiedades se organizan en categorías, WritingMode está en la categoría **Localización** .</span><span class="sxs-lookup"><span data-stu-id="6bfaf-116">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span>  
  
5.  <span data-ttu-id="6bfaf-117">En el cuadro de lista, seleccione **Horizontal**, **Vertical**o **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="6bfaf-117">In the list box, select **Horizontal**, **Vertical**, or **Rotate270**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bfaf-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6bfaf-118">See Also</span></span>  
 <span data-ttu-id="6bfaf-119">[Cuadros de texto &#40;Generador de informes y SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6bfaf-119">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6bfaf-120">Tutorial: Dar formato a texto &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="6bfaf-120">Tutorial: Format Text &#40;Report Builder&#41;</span></span>](../tutorial-format-text-report-builder.md)  
  
  
