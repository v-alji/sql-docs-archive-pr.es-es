---
title: Cuadro de diálogo Agregar dimensión de cubo (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.addcubedimensiondialog.f1
helpviewer_keywords:
- Add Cube Dimension dialog box
ms.assetid: 625a3b1f-183b-445f-9bb7-96945c324767
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0de75c02c39b0690184f35f2b0b6a07d7ed9a4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663809"
---
# <a name="add-cube-dimension-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="12e72-102">Cuadro de diálogo Agregar dimensión de cubo (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="12e72-102">Add Cube Dimension Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="12e72-103">Use el cuadro de diálogo **Agregar dimensión de cubo** en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para agregar una referencia a una dimensión de base de datos a un cubo.</span><span class="sxs-lookup"><span data-stu-id="12e72-103">Use the **Add Cube Dimension** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to add a reference to a database dimension to a cube.</span></span> <span data-ttu-id="12e72-104">Para visualizar el cuadro de diálogo **Agregar dimensión de cubo** , puede realizar una de estas acciones:</span><span class="sxs-lookup"><span data-stu-id="12e72-104">You can display the **Add Cube Dimension** dialog box by doing one of the following:</span></span>  
  
-   <span data-ttu-id="12e72-105">Hacer clic en **Agregar dimensión de cubo** en el panel **Barra de herramientas** de la pestaña **Estructura de cubo** o **Uso de dimensiones** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="12e72-105">Click **Add Cube Dimension** in the **Toolbar** pane on the **Cube Structure** or **Dimension Usage** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="12e72-106">Hacer clic con el botón derecho en el panel **Dimensiones** de la pestaña **Estructura de cubo** del Diseñador de cubos y seleccionar **Agregar dimensión de cubo** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="12e72-106">Right-click the **Dimensions** pane on the **Cube Structure** tab in Cube Designer and select **Add Cube Dimension** from the context menu.</span></span>  
  
-   <span data-ttu-id="12e72-107">Hacer clic con el botón derecho en el panel **Cuadrícula** de la pestaña **Uso de dimensiones** del Diseñador de cubos y seleccionar **Agregar dimensión de cubo** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="12e72-107">Right-click the **Grid** pane on the **Dimension Usage** tab in Cube Designer and select **Add Cube Dimension** from the context menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12e72-108">Cada dimensión de cubo puede tener únicamente una relación con un grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="12e72-108">Each cube dimension can have only one relationship to a measure group.</span></span> <span data-ttu-id="12e72-109">No obstante, puede crear más de una dimensión de cubo y agregarla al cubo si la dimensión de la base de datos en la cual se basa la dimensión de cubo se relaciona con los grupos de medida a través de más de una relación en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="12e72-109">However, you can create more than one cube dimension and add it to the cube, if the database dimension on which the cube dimension is based is related to measure groups through more than one relationship in the data source view.</span></span> <span data-ttu-id="12e72-110">Se hace referencia a estas dimensiones como dimensiones realizadoras de roles y normalmente se producen con dimensiones de tiempo.</span><span class="sxs-lookup"><span data-stu-id="12e72-110">Such dimensions are referred to as role-playing dimensions and commonly occur with time dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="12e72-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="12e72-111">Options</span></span>  
 <span data-ttu-id="12e72-112">**Seleccionar dimensión**</span><span class="sxs-lookup"><span data-stu-id="12e72-112">**Select dimension**</span></span>  
 <span data-ttu-id="12e72-113">Seleccione una dimensión de base de datos existente para agregar una dimensión de cubo que se base en ella al cubo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="12e72-113">Select an existing database dimension to add a cube dimension based on it to the selected cube.</span></span> <span data-ttu-id="12e72-114">Es posible definir varias dimensiones de cubo a partir de la misma dimensión de base de datos.</span><span class="sxs-lookup"><span data-stu-id="12e72-114">Multiple cube dimensions can be defined from the same database dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12e72-115">Si se agrega a un cubo más de una dimensión de cubo basada en la misma dimensión de base de datos, las dimensiones de cubo adicionales se denominan dimensiones realizadoras de roles.</span><span class="sxs-lookup"><span data-stu-id="12e72-115">If more than one cube dimension based on the same database dimension is added to a cube, the additional cube dimensions are called role-playing dimensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e72-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12e72-116">See Also</span></span>  
 [<span data-ttu-id="12e72-117">Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="12e72-117">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
