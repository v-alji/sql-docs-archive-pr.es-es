---
title: Especificar convenciones de nomenclatura (Asistente para generar esquemas) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.namingconventions.f1
ms.assetid: 02d830ea-5b1f-4485-9f94-d64b8bea592b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e9588b49331934041cad888142d29d189fc1a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675551"
---
# <a name="specify-naming-conventions-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="98319-102">Especificar convenciones de nomenclatura (Asistente para generar esquemas) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="98319-102">Specify Naming Conventions (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="98319-103">Utilice la página **Especificar convenciones de nomenclatura** para definir las convenciones de nomenclatura que el Asistente para generar esquemas utiliza al crear objetos de esquemas.</span><span class="sxs-lookup"><span data-stu-id="98319-103">Use the **Specify Naming Conventions** page to define the naming conventions that the Schema Generation Wizard uses when creating schema objects.</span></span>  
  
## <a name="options"></a><span data-ttu-id="98319-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="98319-104">Options</span></span>  
 <span data-ttu-id="98319-105">**Opción**</span><span class="sxs-lookup"><span data-stu-id="98319-105">**Option**</span></span>  
 <span data-ttu-id="98319-106">Especifique las convenciones de nomenclatura que debe utilizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="98319-106">Specify the naming conventions for the wizard to use.</span></span> <span data-ttu-id="98319-107">La siguiente tabla describe las opciones que puede especificar.</span><span class="sxs-lookup"><span data-stu-id="98319-107">The following table describes the options you can specify.</span></span>  
  
|<span data-ttu-id="98319-108">Opción</span><span class="sxs-lookup"><span data-stu-id="98319-108">Option</span></span>|<span data-ttu-id="98319-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="98319-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="98319-110">**Separador**</span><span class="sxs-lookup"><span data-stu-id="98319-110">**Separator**</span></span>|<span data-ttu-id="98319-111">Especifica el carácter que separa las palabras en el nombre de un objeto.</span><span class="sxs-lookup"><span data-stu-id="98319-111">Specifies the character that separates words in an object name.</span></span> <span data-ttu-id="98319-112">En la columna **Valor** , seleccione **Carácter de subrayado**, **Espacio**o **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="98319-112">In the **Value** column, select **Underscore**, **Space**, or **None**.</span></span> <span data-ttu-id="98319-113">El valor predeterminado es **Carácter de subrayado**.</span><span class="sxs-lookup"><span data-stu-id="98319-113">The default is **Underscore**.</span></span>|  
|<span data-ttu-id="98319-114">**Prefijo de la columna de clave principal**</span><span class="sxs-lookup"><span data-stu-id="98319-114">**Primary key column prefix**</span></span>|<span data-ttu-id="98319-115">Especifica la cadena del prefijo correspondiente al nombre de cada columna de clave principal.</span><span class="sxs-lookup"><span data-stu-id="98319-115">Specifies the string to prefix the name of each primary key column.</span></span> <span data-ttu-id="98319-116">El valor predeterminado es **PK**.</span><span class="sxs-lookup"><span data-stu-id="98319-116">The default is **PK**.</span></span>|  
|<span data-ttu-id="98319-117">**Prefijo de la columna de clave externa**</span><span class="sxs-lookup"><span data-stu-id="98319-117">**Foreign key column prefix**</span></span>|<span data-ttu-id="98319-118">Especifica la cadena del prefijo correspondiente al nombre de cada columna de clave externa.</span><span class="sxs-lookup"><span data-stu-id="98319-118">Specifies the string to prefix the name of each foreign key column.</span></span> <span data-ttu-id="98319-119">El valor predeterminado es **FK**.</span><span class="sxs-lookup"><span data-stu-id="98319-119">The default is **FK**.</span></span>|  
|<span data-ttu-id="98319-120">**Sufijo del nombre del atributo**</span><span class="sxs-lookup"><span data-stu-id="98319-120">**Attribute name suffix**</span></span>|<span data-ttu-id="98319-121">Especifica la cadena que se debe anexar al nombre de cada columna de atributos.</span><span class="sxs-lookup"><span data-stu-id="98319-121">Specifies the string to be appended to the name of each attribute column.</span></span> <span data-ttu-id="98319-122">El valor predeterminado es **Name**.</span><span class="sxs-lookup"><span data-stu-id="98319-122">The default is **Name**.</span></span>|  
|<span data-ttu-id="98319-123">**Sufijo del resumen personalizado**</span><span class="sxs-lookup"><span data-stu-id="98319-123">**Custom rollup suffix**</span></span>|<span data-ttu-id="98319-124">Especifica la cadena que se debe anexar al nombre de cada columna de resúmenes.</span><span class="sxs-lookup"><span data-stu-id="98319-124">Specifies the string to be appended to the name of each rollup column.</span></span> <span data-ttu-id="98319-125">El valor predeterminado es **CustomRollup**.</span><span class="sxs-lookup"><span data-stu-id="98319-125">The default is **CustomRollup**.</span></span>|  
|<span data-ttu-id="98319-126">**Sufijo de propiedades del resumen personalizado**</span><span class="sxs-lookup"><span data-stu-id="98319-126">**Custom rollup Properties suffix**</span></span>|<span data-ttu-id="98319-127">Especifica la cadena que se debe anexar al nombre de cada columna de propiedades del resumen.</span><span class="sxs-lookup"><span data-stu-id="98319-127">Specifies the string to be appended to the name of each rollup property column.</span></span> <span data-ttu-id="98319-128">El valor predeterminado es **CustomRollupProperties**.</span><span class="sxs-lookup"><span data-stu-id="98319-128">The default is **CustomRollupProperties**.</span></span>|  
|<span data-ttu-id="98319-129">**Sufijo del operador unario**</span><span class="sxs-lookup"><span data-stu-id="98319-129">**Unary operator suffix**</span></span>|<span data-ttu-id="98319-130">Especifica la cadena que se debe anexar al nombre de cada columna de operador unario.</span><span class="sxs-lookup"><span data-stu-id="98319-130">Specifies the string to be appended to the name of each unary operator column.</span></span> <span data-ttu-id="98319-131">El valor predeterminado es **UnaryOperator**.</span><span class="sxs-lookup"><span data-stu-id="98319-131">The default is **UnaryOperator**.</span></span>|  
  
 <span data-ttu-id="98319-132">**Valor**</span><span class="sxs-lookup"><span data-stu-id="98319-132">**Value**</span></span>  
 <span data-ttu-id="98319-133">Especifica un valor para la opción especificada en **Opción** que quiera usar cuando se genera el esquema.</span><span class="sxs-lookup"><span data-stu-id="98319-133">Specify a value for the option specified in **Option** that you want to use when the schema is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98319-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98319-134">See Also</span></span>  
 <span data-ttu-id="98319-135">[Asistente para generar esquemas ayuda F1 &#40;Analysis Services-datos multidimensionales&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="98319-135">[Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="98319-136">Analysis Services asistentes &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="98319-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
