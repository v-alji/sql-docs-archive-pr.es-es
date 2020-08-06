---
title: Seleccionar atributos de dimensión (Asistente para dimensiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionattributes.f1
ms.assetid: f58a3e14-ab27-44d3-8c26-f5c9ee7583b0
author: minewiskan
ms.author: owend
ms.openlocfilehash: a4961092517ce1d38cfd4086ec083a939242652d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670636"
---
# <a name="select-dimension-attributes-dimension-wizard"></a><span data-ttu-id="3a9f0-102">Seleccionar los atributos de la dimensión (Asistente para dimensiones)</span><span class="sxs-lookup"><span data-stu-id="3a9f0-102">Select Dimension Attributes (Dimension Wizard)</span></span>
  <span data-ttu-id="3a9f0-103">Utilice la página **Seleccionar los atributos de la dimensión** para seleccionar y modificar los atributos para la dimensión que debe crearse.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-103">Use the **Select Dimension Attributes** page to select and modify the attributes for the dimension to be created.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a9f0-104">Si no puede leer los valores de cualquier columna, maximice la ventana del asistente y cambie el ancho de cada encabezado de columna hasta que lea los valores.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-104">If you cannot read the values for any column, maximize the wizard window and change the width of each column heading until you can read the values.</span></span>  
  
 <span data-ttu-id="3a9f0-105">**Para abrir el Asistente para dimensiones**</span><span class="sxs-lookup"><span data-stu-id="3a9f0-105">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="3a9f0-106">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], en el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta **Dimensiones** para un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y, luego, haga clic en **Nueva dimensión**.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3a9f0-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="3a9f0-107">Options</span></span>  
 <span data-ttu-id="3a9f0-108">(Columna con casillas)</span><span class="sxs-lookup"><span data-stu-id="3a9f0-108">(Column with check boxes)</span></span>  
 <span data-ttu-id="3a9f0-109">Active las casillas para incluir atributos en la dimensión.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-109">Select to include an attribute in the dimension.</span></span>  
  
 <span data-ttu-id="3a9f0-110">Para incluir un atributo específico, active la casilla de dicho atributo.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-110">To include a specific attribute, select the check box for that attribute.</span></span>  
  
 <span data-ttu-id="3a9f0-111">Para incluir todos los atributos, active la casilla del encabezado de la columna.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-111">To include all attributes, select the check box in the column header.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a9f0-112">No se puede desactivar la casilla para el atributo clave.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-112">The check box for the key attribute cannot be cleared.</span></span>  
  
 <span data-ttu-id="3a9f0-113">**Nombre del atributo**</span><span class="sxs-lookup"><span data-stu-id="3a9f0-113">**Attribute Name**</span></span>  
 <span data-ttu-id="3a9f0-114">Enumera los atributos disponibles.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-114">Lists the available attributes.</span></span>  
  
 <span data-ttu-id="3a9f0-115">Para cambiar el nombre de un atributo, haga clic en el nombre del atributo y escriba otro nombre.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-115">To change the name of an attribute, click the attribute name and type a new name for the attribute.</span></span>  
  
 <span data-ttu-id="3a9f0-116">**Habilitar exploración**</span><span class="sxs-lookup"><span data-stu-id="3a9f0-116">**Enable Browsing**</span></span>  
 <span data-ttu-id="3a9f0-117">Seleccione esta opción para que el atributo esté disponible para que el usuario final pueda examinar y filtrar.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-117">Select to make the attribute available to the end user for browsing and filtering.</span></span> <span data-ttu-id="3a9f0-118">La opción**Habilitar exploración** debe estar seleccionada para el atributo clave.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-118">**Enable Browsing** must be selected for the key attribute.</span></span> <span data-ttu-id="3a9f0-119">Para los atributos no clave, el valor predeterminado es no tener la opción **Habilitar exploración** seleccionada, lo que hace que se muestren los atributos no clave solo como propiedades de miembro.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-119">For non-key attributes, the default is not to have **Enable Browsing** selected, which causes the non-key attributes to be shown only as member properties.</span></span>  
  
 <span data-ttu-id="3a9f0-120">En la mayoría de los casos, el atributo se convierte en disponible o no disponible para examinar estableciendo la propiedad `AttributeHierarchyEnabled` en `True` o `False`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-120">In most cases, the attribute is made available or not available for browsing by setting the `AttributeHierarchyEnabled` property to `True` or `False`, respectively.</span></span> <span data-ttu-id="3a9f0-121">Sin embargo, en los tres casos siguientes, el asistente usa valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-121">However, in the following three cases, the wizard uses different settings.</span></span>  
  
|<span data-ttu-id="3a9f0-122">Caso</span><span class="sxs-lookup"><span data-stu-id="3a9f0-122">Case</span></span>|<span data-ttu-id="3a9f0-123">Configuración</span><span class="sxs-lookup"><span data-stu-id="3a9f0-123">Settings</span></span>|  
|----------|--------------|  
|<span data-ttu-id="3a9f0-124">Una dimensión contiene una jerarquía de elementos primarios y secundarios, y la opción **Habilitar exploración** no está seleccionada</span><span class="sxs-lookup"><span data-stu-id="3a9f0-124">A dimension contains a parent-child hierarchy and **Enable Browsing** is not selected</span></span>|<span data-ttu-id="3a9f0-125">El asistente deja la propiedad `AttributeHierarchyEnabled` establecida en `True`y establece el atributo `AttributeHierarchyVisible` en `False` para el atributo clave.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-125">The wizard leaves the `AttributeHierarchyEnabled` property set to `True`, and sets the `AttributeHierarchyVisible` attribute to `False` for the key attribute.</span></span>|  
|<span data-ttu-id="3a9f0-126">Una tabla de una dimensión contiene una clave externa a una tabla que no se encuentra en la dimensión.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-126">A table in a dimension contains a foreign key to a table that is not in the dimension</span></span>|<span data-ttu-id="3a9f0-127">El asistente selecciona la clave externa como un atributo que se va a incluir pero no seleccionará **Habilitar exploración**.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-127">The wizard selects the foreign key as an attribute to be included, but will not select **Enable Browsing**.</span></span> <span data-ttu-id="3a9f0-128">Si mantiene esta configuración, la propiedad `AttributeHiearchyEnabled` del atributo se establecerá en `True`y la propiedad `AttributeHierarchyVisible` se establecerá en `False`.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-128">If you keep these settings, the `AttributeHiearchyEnabled` property of the attribute will be set to `True`, and the `AttributeHierarchyVisible` property will be set to `False`.</span></span>|  
|<span data-ttu-id="3a9f0-129">Una dimensión contiene tablas de copo de nieve a las que se tiene acceso a través de columnas de clave externa que admiten valores NULL</span><span class="sxs-lookup"><span data-stu-id="3a9f0-129">A dimension contains snowflake tables that are reached through nullable foreign key columns</span></span><br /><br /> <span data-ttu-id="3a9f0-130">- y -</span><span class="sxs-lookup"><span data-stu-id="3a9f0-130">-and-</span></span><br /><br /> <span data-ttu-id="3a9f0-131">la opción Habilitar exploración para el atributo que está basado en la clave de la tabla de copo de nieve no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-131">Enable Browsing for the attribute that is based on the key of the snowflake table is not selected</span></span>|<span data-ttu-id="3a9f0-132">El asistente creará el nuevo atributo que tiene la propiedad `AttributeHiearchyEnabled` establecida en `True`y la propiedad `AttributeHierarchyVisible` establecida en `False`.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-132">The wizard will create the new attribute that has the `AttributeHiearchyEnabled` property set to `True`, and the `AttributeHierarchyVisible` property set to `False`.</span></span>|  
  
 <span data-ttu-id="3a9f0-133">**Tipo de atributo**</span><span class="sxs-lookup"><span data-stu-id="3a9f0-133">**Attribute Type**</span></span>  
 <span data-ttu-id="3a9f0-134">(Opcional) Establezca el tipo para el atributo.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-134">(Optional) Set the type for the attribute.</span></span> <span data-ttu-id="3a9f0-135">El valor predeterminado es **Regular**.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-135">The default value is **Regular**.</span></span> <span data-ttu-id="3a9f0-136">El tipo de atributo proporciona orientación a las aplicaciones cliente sobre qué información podría contener el atributo.</span><span class="sxs-lookup"><span data-stu-id="3a9f0-136">The attribute type provides guidance to client applications on what information the attribute might contain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a9f0-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a9f0-137">See Also</span></span>  
 <span data-ttu-id="3a9f0-138">[Asistente para dimensiones (ayuda F1)](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="3a9f0-138">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="3a9f0-139">[Dimensiones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3a9f0-139">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3a9f0-140">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="3a9f0-140">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
