---
title: Establecer fórmulas de miembro personalizado para los atributos de una dimensión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Business Intelligence enhancements [Analysis Services], custom member formulas
- member formulas [Analysis Services]
- dimensions [Analysis Services], Business Intelligence enhancements
- custom member formulas [Analysis Services]
- CustomRollupColumn property
ms.assetid: c4467b08-ce59-4de7-a2d9-c22e246bdd52
author: minewiskan
ms.author: owend
ms.openlocfilehash: 112f8944bd20b2b6a464b0d84fb8ac1a0e89d976
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670656"
---
# <a name="set-custom-member-formulas-for-attributes-in-a-dimension"></a><span data-ttu-id="d48f2-102">Configurar fórmulas de miembro personalizado para los atributos de una dimensión</span><span class="sxs-lookup"><span data-stu-id="d48f2-102">Set Custom Member Formulas for Attributes in a Dimension</span></span>
  <span data-ttu-id="d48f2-103">Agregar una fórmula de miembro personalizado a un cubo o dimensión para reemplazar la agregación predeterminada asociada a un miembro de dimensión con los resultados de una expresión de Expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="d48f2-103">Add a custom member formula enhancement to a cube or dimension to replace the default aggregation that is associated with a dimension member with the results of a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="d48f2-104">(Esta mejora establece la propiedad `CustomRollupColumn` en un atributo especificado en una dimensión).</span><span class="sxs-lookup"><span data-stu-id="d48f2-104">(This enhancement sets the `CustomRollupColumn` property on a specified attribute in a dimension.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d48f2-105">Hay una fórmula de miembro personalizado disponible solamente para dimensiones que se basan en orígenes de datos existentes.</span><span class="sxs-lookup"><span data-stu-id="d48f2-105">A custom member formula is available only for dimensions that are based on existing data sources.</span></span> <span data-ttu-id="d48f2-106">Para las dimensiones creadas sin usar un origen de datos, debe ejecutar el Asistente para generar esquemas para crear una vista del origen de datos antes de agregar una fórmula de miembro personalizado.</span><span class="sxs-lookup"><span data-stu-id="d48f2-106">For dimensions that were created without using a data source, you must run the Schema Generation Wizard to create a data source view before adding a custom member formula.</span></span>  
  
 <span data-ttu-id="d48f2-107">Para agregar una fórmula de miembro personalizado, se usa el Asistente de Business Intelligence y se selecciona la opción **Crear una fórmula de miembro personalizado** en la página **Elegir mejora** .</span><span class="sxs-lookup"><span data-stu-id="d48f2-107">To add a custom member formula, you use the Business Intelligence Wizard, and select the **Create a custom member formula** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="d48f2-108">A continuación, este asistente le guía por los pasos para seleccionar una dimensión a la que desee aplicar una fórmula de miembro personalizado y habilitar dicha fórmula.</span><span class="sxs-lookup"><span data-stu-id="d48f2-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply a custom member formula and enabling the custom member formula.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="d48f2-109">Seleccionar una dimensión</span><span class="sxs-lookup"><span data-stu-id="d48f2-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="d48f2-110">En la primera página del asistente **Crear una fórmula de miembro personalizado** se especifica la dimensión a la que se desea aplicar una fórmula de miembro personalizado.</span><span class="sxs-lookup"><span data-stu-id="d48f2-110">On the first **Create a Custom Member Formula** page of the wizard, you specify the dimension to which you want to apply a custom member formula.</span></span> <span data-ttu-id="d48f2-111">La mejora de fórmula de miembro personalizado agregada a esta dimensión seleccionada produce cambios en la dimensión.</span><span class="sxs-lookup"><span data-stu-id="d48f2-111">The custom member formula enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="d48f2-112">Estos cambios son heredados por todos los cubos que incluyan la dimensión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d48f2-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="enabling-a-custom-member-formula"></a><span data-ttu-id="d48f2-113">Habilitar una fórmula de miembro personalizado</span><span class="sxs-lookup"><span data-stu-id="d48f2-113">Enabling a Custom Member Formula</span></span>  
 <span data-ttu-id="d48f2-114">En la segunda página de **Crear una fórmula de miembro personalizado** , se asocia la columna de origen que contiene la fórmula de miembro personalizado a uno o más atributos de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="d48f2-114">On the second **Create a Custom Member Formula** page, you associate the source column that contains the custom member formula with one or more attributes in the dimension.</span></span> <span data-ttu-id="d48f2-115">En la columna **Atributo** , se activa la casilla situada junto al atributo que se desea asociar a la columna de fórmula de miembro personalizado.</span><span class="sxs-lookup"><span data-stu-id="d48f2-115">In the **Attribute** column, select the check box next to the attribute that you want to associate with the custom member formula column.</span></span> <span data-ttu-id="d48f2-116">Después de seleccionar cada atributo, el asistente muestra un cuadro de diálogo **Seleccionar una columna** .</span><span class="sxs-lookup"><span data-stu-id="d48f2-116">After you select each attribute, the wizard displays the **Select a Column** dialog box.</span></span> <span data-ttu-id="d48f2-117">En este cuadro de diálogo, haga clic en la columna de la tabla de dimensiones que contiene la fórmula.</span><span class="sxs-lookup"><span data-stu-id="d48f2-117">In this dialog box, click the column in the dimension table that contains the formula.</span></span> <span data-ttu-id="d48f2-118">Si quiere cambiar la selección después de cerrar el cuadro de diálogo **Seleccionar una columna** , haga clic en la celda **Columna de origen** que quiera cambiar y haga clic en el botón de puntos suspensivos (**…**) para volver a abrir el cuadro de diálogo **Seleccionar una columna** .</span><span class="sxs-lookup"><span data-stu-id="d48f2-118">If you want to change a selection after you close the **Select a Column** dialog box, click the **Source Column** cell that you want to change, and then click the ellipsis (**...**) to open the **Select a Column** dialog box again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d48f2-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d48f2-119">See Also</span></span>  
 [<span data-ttu-id="d48f2-120">Usar el Asistente de Business Intelligence para mejorar dimensiones</span><span class="sxs-lookup"><span data-stu-id="d48f2-120">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
  
  
