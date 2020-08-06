---
title: Cuadro de diálogo enlace de objetos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.objectbinding.f1
helpviewer_keywords:
- Object Binding dialog box
ms.assetid: 2bb5ad7c-2962-4559-8c95-cf7148bd2e72
author: minewiskan
ms.author: owend
ms.openlocfilehash: a10c91e0222b826066aeede96aa665cc22540637
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674384"
---
# <a name="object-binding-dialog-box"></a><span data-ttu-id="15092-102">Enlace de objetos (cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="15092-102">Object Binding Dialog Box</span></span>
  <span data-ttu-id="15092-103">Use el cuadro de diálogo **Enlace de objetos** en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para definir enlaces entre la propiedad de un objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y una tabla o columna en una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="15092-103">Use the **Object Binding** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define bindings between the property of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object and a table or column in a data source view.</span></span> <span data-ttu-id="15092-104">Para mostrar el cuadro de diálogo **Enlace de objetos** , seleccione **(nuevo)** en la lista desplegable del valor de las propiedades siguientes de un objeto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en la ventana **Propiedades** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="15092-104">You can display the **Object Binding** dialog box by selecting **(new)** from the drop-down list for the value of the following properties of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span></span>  
  
-   <span data-ttu-id="15092-105">NameColumn</span><span class="sxs-lookup"><span data-stu-id="15092-105">NameColumn</span></span>  
  
-   <span data-ttu-id="15092-106">ValueColumn</span><span class="sxs-lookup"><span data-stu-id="15092-106">ValueColumn</span></span>  
  
-   <span data-ttu-id="15092-107">CustomRollupColumn</span><span class="sxs-lookup"><span data-stu-id="15092-107">CustomRollupColumn</span></span>  
  
-   <span data-ttu-id="15092-108">CustomRollupPropertiesColumn</span><span class="sxs-lookup"><span data-stu-id="15092-108">CustomRollupPropertiesColumn</span></span>  
  
-   <span data-ttu-id="15092-109">UnaryOperatorColumn</span><span class="sxs-lookup"><span data-stu-id="15092-109">UnaryOperatorColumn</span></span>  
  
## <a name="options"></a><span data-ttu-id="15092-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="15092-110">Options</span></span>  
 <span data-ttu-id="15092-111">**Tipo de enlace**</span><span class="sxs-lookup"><span data-stu-id="15092-111">**Binding type**</span></span>  
 <span data-ttu-id="15092-112">Seleccione el enlace que utilizará para el objeto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15092-112">Select the binding to use for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="15092-113">Se pueden utilizar los siguientes tipos de enlaces:</span><span class="sxs-lookup"><span data-stu-id="15092-113">The following types of binding can be used:</span></span>  
  
 <span data-ttu-id="15092-114">Enlace de columna</span><span class="sxs-lookup"><span data-stu-id="15092-114">Column binding</span></span>  
 <span data-ttu-id="15092-115">Enlaza el objeto a una tabla y columna existentes en una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="15092-115">Binds the object to an existing table and column within a data source view.</span></span>  
  
 <span data-ttu-id="15092-116">Generar columna</span><span class="sxs-lookup"><span data-stu-id="15092-116">Generate column</span></span>  
 <span data-ttu-id="15092-117">Indica que se definirá una nueva columna en la vista del origen de datos y, a continuación, el enlace de columna se asociará a ella.</span><span class="sxs-lookup"><span data-stu-id="15092-117">Indicates that a new column is to be defined in the data source view, and a column binding is then associated with it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15092-118">Si selecciona esta opción, debe ejecutar el **Asistente para generar esquemas** antes de implementar el objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15092-118">If this option is selected, you must run the **Schema Generation Wizard** before deploying the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="15092-119">Enlace de fila</span><span class="sxs-lookup"><span data-stu-id="15092-119">Row binding</span></span>  
 <span data-ttu-id="15092-120">Enlaza el objeto a una fila de una tabla de hechos y se usa para facilitar medidas de recuento basadas en el número de filas procesadas en la tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="15092-120">Binds the object to a row in a fact table and is used to facilitate count measures based on the number of rows processed in the fact table.</span></span>  
  
 <span data-ttu-id="15092-121">**Tabla de origen**</span><span class="sxs-lookup"><span data-stu-id="15092-121">**Source table**</span></span>  
 <span data-ttu-id="15092-122">Muestra una lista de tablas en la vista del origen de datos asociadas con el objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15092-122">Displays a list of tables in the data source view associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="15092-123">**Columna de origen**</span><span class="sxs-lookup"><span data-stu-id="15092-123">**Source column**</span></span>  
 <span data-ttu-id="15092-124">Muestra una lista de columnas de la tabla seleccionada en **Tabla de origen**.</span><span class="sxs-lookup"><span data-stu-id="15092-124">Displays a list of columns in the table selected in **Source table**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15092-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15092-125">See Also</span></span>  
 [<span data-ttu-id="15092-126">Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="15092-126">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
