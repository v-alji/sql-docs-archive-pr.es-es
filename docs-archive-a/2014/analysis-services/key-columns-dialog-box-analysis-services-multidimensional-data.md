---
title: Cuadro de diálogo columnas de clave (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.dataitemCollection.f1
helpviewer_keywords:
- DataItem Collection dialog box
ms.assetid: 585f27f2-d5eb-4516-b29a-2084010b7d51
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a72a9e137700ddee822e68901bfde971637d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669949"
---
# <a name="key-columns-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="33394-102">Cuadro de diálogo Columnas de clave (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="33394-102">Key Columns Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="33394-103">Use el cuadro de diálogo **Columnas de clave** para cambiar la propiedad **KeyColumns** de un atributo.</span><span class="sxs-lookup"><span data-stu-id="33394-103">Use the **Key Columns** dialog box to change the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="33394-104">Para más información, vea [Modificar la propiedad KeyColumns de un atributo](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="33394-104">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
 <span data-ttu-id="33394-105">**Para mostrar el cuadro de diálogo Columnas de clave**</span><span class="sxs-lookup"><span data-stu-id="33394-105">**To display the Key Columns dialog box**</span></span>  
  
-   <span data-ttu-id="33394-106">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], seleccione un atributo y, en la ventana **Propiedades** , haga clic en el botón de puntos suspensivos (**…**) asociado a la propiedad **KeyColumns** de dicho atributo.</span><span class="sxs-lookup"><span data-stu-id="33394-106">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select an attribute, and in the **Properties** window, click the ellipsis button (**...**) associated with the **KeyColumns** property of that attribute.</span></span>  
  
## <a name="options"></a><span data-ttu-id="33394-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="33394-107">Options</span></span>  
 <span data-ttu-id="33394-108">**Tabla de origen**</span><span class="sxs-lookup"><span data-stu-id="33394-108">**Source table**</span></span>  
 <span data-ttu-id="33394-109">Seleccione la tabla de origen para la que desea seleccionar sus columnas de clave.</span><span class="sxs-lookup"><span data-stu-id="33394-109">Select the source table for which you want to select its key columns.</span></span> <span data-ttu-id="33394-110">Puede seleccionar la tabla de origen en una lista de todas las tablas en la Vista de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="33394-110">You can select the source table from a list of all tables in the Data Source View.</span></span>  
  
 <span data-ttu-id="33394-111">**Columnas disponibles**</span><span class="sxs-lookup"><span data-stu-id="33394-111">**Available Columns**</span></span>  
 <span data-ttu-id="33394-112">Seleccione las columnas que desea usar como columnas de clave.</span><span class="sxs-lookup"><span data-stu-id="33394-112">Select the columns that you want to use as key columns.</span></span> <span data-ttu-id="33394-113">Puede seleccionar las columnas en una lista de columnas en la **Tabla de origen** especificada que no haya seleccionado todavía como columnas de clave.</span><span class="sxs-lookup"><span data-stu-id="33394-113">You can select the columns from a list of columns in the specified **Source table** that have not yet been selected as key columns.</span></span>  
  
 <span data-ttu-id="33394-114">Para agregar las columnas seleccionadas a la lista **Columnas de clave** , haga clic en el botón **>** .</span><span class="sxs-lookup"><span data-stu-id="33394-114">To add the selected columns to the **Key Columns** list, click the **>** button.</span></span>  
  
 <span data-ttu-id="33394-115">**Columnas de clave**</span><span class="sxs-lookup"><span data-stu-id="33394-115">**Key Columns**</span></span>  
 <span data-ttu-id="33394-116">Defina el orden de las columnas de clave seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="33394-116">Define the order of the selected key columns.</span></span> <span data-ttu-id="33394-117">El orden de las columnas de clave es importante para definir la clave compuesta correcta.</span><span class="sxs-lookup"><span data-stu-id="33394-117">The order of the key columns is important in defining the correct composite key.</span></span> <span data-ttu-id="33394-118">Para ordenar o cambiar el orden de las columnas de clave, seleccione una columna y, a continuación, haga clic en el botón **Subir** o **Bajar** .</span><span class="sxs-lookup"><span data-stu-id="33394-118">To order or reorder the list of key columns, select a column, and then click the **Up** or **Down** buttons.</span></span>  
  
 <span data-ttu-id="33394-119">Para quitar una columna de la lista **Columnas de clave** , seleccione la columna y haga clic en el botón **\<** .</span><span class="sxs-lookup"><span data-stu-id="33394-119">To remove a column from the **Key Columns** list, select the column and click the **\<** button.</span></span>  
  
 <span data-ttu-id="33394-120">**Arriba**</span><span class="sxs-lookup"><span data-stu-id="33394-120">**Up**</span></span>  
 <span data-ttu-id="33394-121">Haga clic para subir una posición la columna seleccionada en **Columnas de clave** .</span><span class="sxs-lookup"><span data-stu-id="33394-121">Click to move the column selected in **Key Columns** up one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33394-122">Esta opción solo está habilitada si la lista contiene más de una columna y está seleccionada una columna.</span><span class="sxs-lookup"><span data-stu-id="33394-122">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 <span data-ttu-id="33394-123">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="33394-123">**Down**</span></span>  
 <span data-ttu-id="33394-124">Haga clic para bajar una posición la columna seleccionada en **Columnas de clave** .</span><span class="sxs-lookup"><span data-stu-id="33394-124">Click to move the column selected in **Key Columns** down one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33394-125">Esta opción solo está habilitada si la lista contiene más de una columna y está seleccionada una columna.</span><span class="sxs-lookup"><span data-stu-id="33394-125">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 **>**  
 <span data-ttu-id="33394-126">Haga clic para agregar una nueva columna al final de las columnas de lista **Columnas de clave**.</span><span class="sxs-lookup"><span data-stu-id="33394-126">Click to add a new column to the end of the columns listed in **Key Columns**.</span></span>  
  
 **<**  
 <span data-ttu-id="33394-127">Haga clic para quitar la columna seleccionada de las columnas de la lista **Columnas de clave**.</span><span class="sxs-lookup"><span data-stu-id="33394-127">Click to remove the selected column from the columns listed in **Key Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33394-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33394-128">See Also</span></span>  
 [<span data-ttu-id="33394-129">Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="33394-129">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
