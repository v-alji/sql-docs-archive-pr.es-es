---
title: Crear una dimensión generando una tabla que no sea de tiempos en el origen de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data sources [Analysis Services], dimensions without data source
- dimensions [Analysis Services], standard
- dimensions [Analysis Services], creating without data source
- standard dimensions [Analysis Services]
ms.assetid: a37f7a46-7451-4582-ba19-2595196d97bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 49dbfb0c1fc15c1cbf703514e0fc693dfabf1e9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748350"
---
# <a name="create-a-dimension-by-generating-a-non-time-table-in-the-data-source"></a><span data-ttu-id="424a8-102">Crear una dimensión generando una tabla que no sea de tiempos en el origen de datos</span><span class="sxs-lookup"><span data-stu-id="424a8-102">Create a Dimension by Generating a Non-Time Table in the Data Source</span></span>
  <span data-ttu-id="424a8-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , puede utilizar el Asistente para dimensiones de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para crear una dimensión sin utilizar un origen de datos existente.</span><span class="sxs-lookup"><span data-stu-id="424a8-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the Dimension Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to create a dimension without using an existing data source.</span></span> <span data-ttu-id="424a8-104">Para ello, debe seleccionar la opción **Generar una tabla que no sea de tiempos en el origen de datos** en la página **Seleccionar método de creación** del asistente.</span><span class="sxs-lookup"><span data-stu-id="424a8-104">You do this by selecting the **Generate a non-time table in the data source** option of the **Select Creation Method** page of the wizard.</span></span> <span data-ttu-id="424a8-105">Para crear una tabla de dimensiones en el origen de datos subyacente, debe tener permisos para crear objetos en ese origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="424a8-105">To create a new dimension table in the underlying data source, you must have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="424a8-106">Al definir una dimensión sin una vista del origen de datos predefinida, puede definirla desde cero o usando una plantilla de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="424a8-106">When defining a dimension without a predefined data source view, you can either define the dimension from scratch or use a dimension template.</span></span>  
  
 <span data-ttu-id="424a8-107">El Asistente para dimensiones proporciona plantillas de dimensiones de muestra que puede usar para generar un tipo de dimensión frecuente.</span><span class="sxs-lookup"><span data-stu-id="424a8-107">The Dimension Wizard provides sample dimension templates from which you can build a common dimension type.</span></span> <span data-ttu-id="424a8-108">Puede elegir entre los siguientes tipos de dimensiones:</span><span class="sxs-lookup"><span data-stu-id="424a8-108">You can select from the following types of dimensions:</span></span>  
  
-   <span data-ttu-id="424a8-109">Cuenta</span><span class="sxs-lookup"><span data-stu-id="424a8-109">Account</span></span>  
  
-   <span data-ttu-id="424a8-110">Customer</span><span class="sxs-lookup"><span data-stu-id="424a8-110">Customer</span></span>  
  
-   <span data-ttu-id="424a8-111">Date</span><span class="sxs-lookup"><span data-stu-id="424a8-111">Date</span></span>  
  
-   <span data-ttu-id="424a8-112">department</span><span class="sxs-lookup"><span data-stu-id="424a8-112">Department</span></span>  
  
-   <span data-ttu-id="424a8-113">Destination Currency</span><span class="sxs-lookup"><span data-stu-id="424a8-113">Destination Currency</span></span>  
  
-   <span data-ttu-id="424a8-114">Empleado</span><span class="sxs-lookup"><span data-stu-id="424a8-114">Employee</span></span>  
  
-   <span data-ttu-id="424a8-115">Geography</span><span class="sxs-lookup"><span data-stu-id="424a8-115">Geography</span></span>  
  
-   <span data-ttu-id="424a8-116">Internet Sales Order Details</span><span class="sxs-lookup"><span data-stu-id="424a8-116">Internet Sales Order Details</span></span>  
  
-   <span data-ttu-id="424a8-117">Organización</span><span class="sxs-lookup"><span data-stu-id="424a8-117">Organization</span></span>  
  
-   <span data-ttu-id="424a8-118">Producto</span><span class="sxs-lookup"><span data-stu-id="424a8-118">Product</span></span>  
  
-   <span data-ttu-id="424a8-119">Promoción</span><span class="sxs-lookup"><span data-stu-id="424a8-119">Promotion</span></span>  
  
-   <span data-ttu-id="424a8-120">Reseller Sales Order Details</span><span class="sxs-lookup"><span data-stu-id="424a8-120">Reseller Sales Order Details</span></span>  
  
-   <span data-ttu-id="424a8-121">Vendedor</span><span class="sxs-lookup"><span data-stu-id="424a8-121">Reseller</span></span>  
  
-   <span data-ttu-id="424a8-122">Sales Channel</span><span class="sxs-lookup"><span data-stu-id="424a8-122">Sales Channel</span></span>  
  
-   <span data-ttu-id="424a8-123">Sales Reason</span><span class="sxs-lookup"><span data-stu-id="424a8-123">Sales Reason</span></span>  
  
-   <span data-ttu-id="424a8-124">Sales Summary Order Details</span><span class="sxs-lookup"><span data-stu-id="424a8-124">Sales Summary Order Details</span></span>  
  
-   <span data-ttu-id="424a8-125">Sales Territory</span><span class="sxs-lookup"><span data-stu-id="424a8-125">Sales Territory</span></span>  
  
-   <span data-ttu-id="424a8-126">Escenario</span><span class="sxs-lookup"><span data-stu-id="424a8-126">Scenario</span></span>  
  
-   <span data-ttu-id="424a8-127">Source Currency</span><span class="sxs-lookup"><span data-stu-id="424a8-127">Source Currency</span></span>  
  
 <span data-ttu-id="424a8-128">Cada una de las plantillas estándar admite atributos que puede incluir en la dimensión.</span><span class="sxs-lookup"><span data-stu-id="424a8-128">Each of the standard templates supports attributes that you can choose to include in the dimension.</span></span> <span data-ttu-id="424a8-129">También puede agregar sus propios archivos de plantilla para dimensiones que normalmente se usan con sus datos.</span><span class="sxs-lookup"><span data-stu-id="424a8-129">You can also add your own template files for dimensions that are commonly used with your data.</span></span> <span data-ttu-id="424a8-130">Las plantillas de dimensiones se ubican en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="424a8-130">The dimension templates are located in the following folder:</span></span>  
  
 `C:\Program Files\Microsoft SQL Server\100\Tools\Templates\olap\1033\Dimension Templates`  
  
 <span data-ttu-id="424a8-131">Puede utilizar el Diseñador de dimensiones una vez finalizado el Asistente para dimensiones para agregar, quitar o configurar atributos y jerarquías de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="424a8-131">You can use Dimension Designer after you complete the Dimension Wizard to add, remove, and configure attributes and hierarchies in the dimension.</span></span>  
  
 <span data-ttu-id="424a8-132">Si va a crear una dimensión que no sea de tiempos sin utilizar un origen de datos, el Asistente para dimensiones lo guía por los pasos necesarios para especificar el tipo de dimensión, identificar el atributo clave y las dimensiones variables.</span><span class="sxs-lookup"><span data-stu-id="424a8-132">When you are creating a non-time dimension without using a data source, the Dimension Wizard guides you through the steps of specifying the dimension type, and identifying the key attribute and slowly changing dimensions.</span></span>  
  
## <a name="specify-dimension-type"></a><span data-ttu-id="424a8-133">Especificar el tipo de dimensión</span><span class="sxs-lookup"><span data-stu-id="424a8-133">Specify Dimension Type</span></span>  
 <span data-ttu-id="424a8-134">En la página **Especificar tipo de dimensión** del Asistente para dimensiones, puede especificar el tipo de dimensión.</span><span class="sxs-lookup"><span data-stu-id="424a8-134">On the **Specify Dimension Type** page of the Dimension Wizard, you can specify the dimension type.</span></span> <span data-ttu-id="424a8-135">Si está generando la dimensión basada en una plantilla, el tipo de dimensión ya está definido.</span><span class="sxs-lookup"><span data-stu-id="424a8-135">If you are building the dimension based on a template, the dimension type is defined for you.</span></span> <span data-ttu-id="424a8-136">En esta página también puede seleccionar atributos estándar para el tipo de dimensión especificado si hay alguno disponible.</span><span class="sxs-lookup"><span data-stu-id="424a8-136">On this page, you can also select standard attributes for the specified dimension type if any are available.</span></span>  
  
 <span data-ttu-id="424a8-137">Si selecciona una plantilla que corresponde a un tipo de dimensión, esta página se llena con las opciones para este tipo de dimensión.</span><span class="sxs-lookup"><span data-stu-id="424a8-137">If you selected a template that corresponds to a dimension type, this page is populated with the options for that dimension type.</span></span> <span data-ttu-id="424a8-138">Si no selecciona una plantilla, o bien si no hay ningún tipo de dimensión correspondiente, el tipo predeterminado de dimensión es **Normal**.</span><span class="sxs-lookup"><span data-stu-id="424a8-138">If you did not select a template, or if there is no corresponding dimension type, the default dimension type is **Regular**.</span></span> <span data-ttu-id="424a8-139">Si no se encuentra ya seleccionado un tipo de dimensión, elija el más apropiado para la dimensión que se crea.</span><span class="sxs-lookup"><span data-stu-id="424a8-139">If a dimension type is not already selected, select the most appropriate type for the dimension that you are creating.</span></span> <span data-ttu-id="424a8-140">Si no hay ningún tipo apropiado enumerado para **Tipo de dimensión**, use **Normal**.</span><span class="sxs-lookup"><span data-stu-id="424a8-140">If no appropriate type is listed for **Dimension type**, use **Regular**.</span></span>  
  
 <span data-ttu-id="424a8-141">Cuando se elige un tipo de dimensión, el asistente muestra los tipos de atributo que son aplicables a esta dimensión en **Atributos de dimensión**.</span><span class="sxs-lookup"><span data-stu-id="424a8-141">When you select a dimension type, the wizard lists the attribute types that apply to this dimension under **Dimension attributes**.</span></span> <span data-ttu-id="424a8-142">Para seleccionar un tipo de atributo, active la casilla **Incluir** , situada junto al tipo de atributo, y escriba el nombre del atributo en **Atributo de dimensión**.</span><span class="sxs-lookup"><span data-stu-id="424a8-142">To select an attribute type, select the **Include** check box next to the attribute type, and type the name for the attribute under **Dimension Attribute**.</span></span> <span data-ttu-id="424a8-143">El nombre predeterminado es el mismo que el **Tipo de atributo**.</span><span class="sxs-lookup"><span data-stu-id="424a8-143">The default name is the same as **Attribute Type**.</span></span>  
  
## <a name="identify-key-attribute-and-changing-dimensions"></a><span data-ttu-id="424a8-144">Identificar el atributo clave y dimensiones variables</span><span class="sxs-lookup"><span data-stu-id="424a8-144">Identify Key Attribute and Changing Dimensions</span></span>  
 <span data-ttu-id="424a8-145">En la página **Especificar clave y tipo de dimensión** , seleccione el atributo que desee que sea el atributo clave para la dimensión.</span><span class="sxs-lookup"><span data-stu-id="424a8-145">On the **Specify Dimension Key and Type** page, select the attribute that you want to be the key attribute for the dimension.</span></span> <span data-ttu-id="424a8-146">Normalmente, el atributo clave corresponde a la columna de clave principal en la tabla de dimensión principal, y normalmente indiza los miembros hoja de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="424a8-146">The key attribute typically corresponds to the primary key column in the main dimension table, and it typically indexes the leaf members of the dimension.</span></span>  
  
 <span data-ttu-id="424a8-147">Si selecciona una plantilla, y en la plantilla se define un atributo clave, ése es el atributo clave predeterminado.</span><span class="sxs-lookup"><span data-stu-id="424a8-147">If you selected a template, and a key attribute is defined in the template, that attribute is the default key attribute.</span></span> <span data-ttu-id="424a8-148">Si selecciona una plantilla pero no tiene definido ningún atributo clave, el atributo clave predeterminado es el primero de la lista.</span><span class="sxs-lookup"><span data-stu-id="424a8-148">If you selected a template but no key attribute is defined in the template, the default is the first attribute in the list.</span></span> <span data-ttu-id="424a8-149">La lista contiene todos los atributos que seleccionó en la página **Especificar tipo de dimensión** .</span><span class="sxs-lookup"><span data-stu-id="424a8-149">The list contains all the attributes that you selected on the **Specify Dimension Type** page.</span></span> <span data-ttu-id="424a8-150">Puede elegir como atributo clave cualquiera de los atributos que seleccionó en la página **Especificar tipo de dimensión** .</span><span class="sxs-lookup"><span data-stu-id="424a8-150">You can select any one of the attributes that you selected on the **Specify Dimension Type** page to be the key attribute.</span></span> <span data-ttu-id="424a8-151">Si no ha seleccionado ningún atributo, el asistente crea automáticamente un atributo clave y lo nombra concatenando el nombre de dimensión y el "Id.".</span><span class="sxs-lookup"><span data-stu-id="424a8-151">If you did not select any attributes, the wizard automatically creates a key attribute and names it by concatenating the dimension name and "ID".</span></span>  
  
 <span data-ttu-id="424a8-152">Finalmente, especifique si esta dimensión es una dimensión variable.</span><span class="sxs-lookup"><span data-stu-id="424a8-152">Finally, specify whether this dimension is a changing dimension.</span></span> <span data-ttu-id="424a8-153">Los miembros de una dimensión variable se mueven con el tiempo a diferentes ubicaciones en una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="424a8-153">Members in a changing dimension move over time to different locations in the hierarchy.</span></span> <span data-ttu-id="424a8-154">El asistente genera columnas adicionales y crea atributos que correspondan a esas columnas.</span><span class="sxs-lookup"><span data-stu-id="424a8-154">The wizard generates additional columns and creates attributes that correspond to those columns.</span></span> <span data-ttu-id="424a8-155">Estas columnas permitirán a los usuarios consultar la dimensión de forma que se tenga en cuenta el cambio.</span><span class="sxs-lookup"><span data-stu-id="424a8-155">These columns will let users query the dimension in such a way as to factor in the change.</span></span> <span data-ttu-id="424a8-156">Cualquier paquete que se cree posteriormente con el Asistente para generar esquemas administra claves suplentes basándose en las características de dimensión variable lenta de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="424a8-156">Any packages that you subsequently create with the Schema Generation Wizard manage surrogate keys based on slowly changing dimension characteristics of the dimension.</span></span>  
  
 <span data-ttu-id="424a8-157">Al activar la casilla **Es una dimensión variable** , el Asistente para dimensiones define los atributos indicados en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="424a8-157">When you select the **This is a changing dimension** check box, the Dimension Wizard defines the attributes indicated in the following table:</span></span>  
  
|<span data-ttu-id="424a8-158">Atributo</span><span class="sxs-lookup"><span data-stu-id="424a8-158">Attribute</span></span>|<span data-ttu-id="424a8-159">Tipo</span><span class="sxs-lookup"><span data-stu-id="424a8-159">Type</span></span>|  
|---------------|----------|  
|<span data-ttu-id="424a8-160">Id. original de DVL</span><span class="sxs-lookup"><span data-stu-id="424a8-160">SCD OriginalID</span></span>|<span data-ttu-id="424a8-161">SCDOriginalID</span><span class="sxs-lookup"><span data-stu-id="424a8-161">SCDOriginalID</span></span>|  
|<span data-ttu-id="424a8-162">Fecha finalización de DVL</span><span class="sxs-lookup"><span data-stu-id="424a8-162">SCD End Date</span></span>|<span data-ttu-id="424a8-163">SCDEndDate</span><span class="sxs-lookup"><span data-stu-id="424a8-163">SCDEndDate</span></span>|  
|<span data-ttu-id="424a8-164">Fecha inicio de DVL</span><span class="sxs-lookup"><span data-stu-id="424a8-164">SCD Start Date</span></span>|<span data-ttu-id="424a8-165">SCDStartDate</span><span class="sxs-lookup"><span data-stu-id="424a8-165">SCDStartDate</span></span>|  
|<span data-ttu-id="424a8-166">Estado de SCD</span><span class="sxs-lookup"><span data-stu-id="424a8-166">SCD Status</span></span>|<span data-ttu-id="424a8-167">SCDStatus</span><span class="sxs-lookup"><span data-stu-id="424a8-167">SCDStatus</span></span>|  
  
 <span data-ttu-id="424a8-168">La casilla **Es una dimensión variable** se activa de forma predeterminada si se usa una plantilla que tenga definidos estos atributos de dimensión de variación lenta.</span><span class="sxs-lookup"><span data-stu-id="424a8-168">By default, the **This is a changing dimension** check box is selected if you use a template that has these slowly changing dimension attributes defined.</span></span> <span data-ttu-id="424a8-169">Si se desactiva la casilla, los atributos de dimensión variable lenta se eliminan de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="424a8-169">If you clear the check box, the slowly changing dimension attributes are removed from the dimension.</span></span>  
  
 <span data-ttu-id="424a8-170">Puede usar el Diseñador de dimensiones para configurar las propiedades de una dimensión variable lenta.</span><span class="sxs-lookup"><span data-stu-id="424a8-170">You can use Dimension Designer to configure properties for a slowly changing dimension.</span></span>  
  
## <a name="completing-the-dimension-wizard"></a><span data-ttu-id="424a8-171">Completar el Asistente para dimensiones</span><span class="sxs-lookup"><span data-stu-id="424a8-171">Completing the Dimension Wizard</span></span>  
 <span data-ttu-id="424a8-172">En la página **Finalización del asistente** , escriba un nombre para la nueva dimensión y consulte la estructura de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="424a8-172">On the **Completing the Wizard** page, type a name for the new dimension and view the dimension structure.</span></span> <span data-ttu-id="424a8-173">Active la casilla **Generar el esquema ahora** para iniciar el Asistente para generar esquemas después de hacer clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="424a8-173">Select the **Generate schema now** check box to start the Schema Generation Wizard after you click **Finish**.</span></span> <span data-ttu-id="424a8-174">En la mayoría de los casos, no se debe activar esta casilla si piensa crear objetos adicionales.</span><span class="sxs-lookup"><span data-stu-id="424a8-174">In most cases, you should not select this check box if you plan to create additional objects.</span></span> <span data-ttu-id="424a8-175">Si no activa esta casilla, se puede usar el Diseñador de dimensiones para generar el esquema más adelante.</span><span class="sxs-lookup"><span data-stu-id="424a8-175">If you do not select this check box, you can use Dimension Designer to generate the schema later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="424a8-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="424a8-176">See Also</span></span>  
 <span data-ttu-id="424a8-177">[Crear una dimensión de tiempo generando una tabla de tiempos](create-a-time-dimension-by-generating-a-time-table.md) </span><span class="sxs-lookup"><span data-stu-id="424a8-177">[Create a Time Dimension by Generating a Time Table](create-a-time-dimension-by-generating-a-time-table.md) </span></span>  
 [<span data-ttu-id="424a8-178">Crear una dimensión de tiempo generando una tabla de tiempos</span><span class="sxs-lookup"><span data-stu-id="424a8-178">Create a Time Dimension by Generating a Time Table</span></span>](create-a-time-dimension-by-generating-a-time-table.md)  
  
  
