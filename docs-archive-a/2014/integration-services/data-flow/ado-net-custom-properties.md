---
title: Propiedades personalizadas de ADO NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e062a9ab-1e6b-4061-845a-4f8a0552b09d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bada6f512770d0f9f07ddc3693070c8aad309cb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744247"
---
# <a name="ado-net-custom-properties"></a><span data-ttu-id="82a6c-102">Propiedades personalizadas de ADO NET</span><span class="sxs-lookup"><span data-stu-id="82a6c-102">ADO NET Custom Properties</span></span>
  <span data-ttu-id="82a6c-103">**Propiedades personalizadas de origen**</span><span class="sxs-lookup"><span data-stu-id="82a6c-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="82a6c-104">El origen de ADO NET tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="82a6c-104">The ADO NET source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="82a6c-105">En la tabla siguiente se describen las propiedades personalizadas del origen de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="82a6c-105">The following table describes the custom properties of the ADO NET source.</span></span> <span data-ttu-id="82a6c-106">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="82a6c-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="82a6c-107">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="82a6c-107">Property name</span></span>|<span data-ttu-id="82a6c-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="82a6c-108">Data Type</span></span>|<span data-ttu-id="82a6c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="82a6c-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="82a6c-110">CommandTimeout</span><span class="sxs-lookup"><span data-stu-id="82a6c-110">CommandTimeout</span></span>|<span data-ttu-id="82a6c-111">String</span><span class="sxs-lookup"><span data-stu-id="82a6c-111">String</span></span>|<span data-ttu-id="82a6c-112">Valor que especifica el número de segundos que transcurren antes de agotarse el tiempo de espera del comando SQL. El valor 0 indica que el comando no agota nunca el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="82a6c-112">A value that specifies the number of seconds before the SQL command times out. A value of 0 indicates that the command never times out.</span></span>|  
|<span data-ttu-id="82a6c-113">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="82a6c-113">SqlCommand</span></span>|<span data-ttu-id="82a6c-114">String</span><span class="sxs-lookup"><span data-stu-id="82a6c-114">String</span></span>|<span data-ttu-id="82a6c-115">Instrucción SQL que el origen de ADO NET usa para extraer datos.</span><span class="sxs-lookup"><span data-stu-id="82a6c-115">The SQL statement that the ADO NET source uses to extract data.</span></span><br /><br /> <span data-ttu-id="82a6c-116">Cuando el paquete se carga, puede actualizar dinámicamente esta propiedad con la instrucción SQL que el origen de ADO NET utilizará.</span><span class="sxs-lookup"><span data-stu-id="82a6c-116">When the package loads, you can dynamically update this property with the SQL statement that the ADO NET source will use.</span></span> <span data-ttu-id="82a6c-117">Para más información, vea [Expresiones de Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md) y [Usar expresiones de propiedad en paquetes](../expressions/use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="82a6c-117">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md) and [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md).</span></span>|  
|<span data-ttu-id="82a6c-118">AllowImplicitStringConversion</span><span class="sxs-lookup"><span data-stu-id="82a6c-118">AllowImplicitStringConversion</span></span>|<span data-ttu-id="82a6c-119">Boolean</span><span class="sxs-lookup"><span data-stu-id="82a6c-119">Boolean</span></span>|<span data-ttu-id="82a6c-120">Valor que indica si ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82a6c-120">A value that indicates whether the following occurs:</span></span><br /><br /> <span data-ttu-id="82a6c-121">No se genera un error de validación si hay una desigualdad entre los tipos de los metadatos externos y los tipos de las columnas de salida que son cadenas (DT_WSTR o DT_NTEXT).</span><span class="sxs-lookup"><span data-stu-id="82a6c-121">No generation of a validation error if there is a mismatch between external metadata types and output column types that are strings (DT_WSTR or DT_NTEXT).</span></span><br /><br /> <span data-ttu-id="82a6c-122">La conversión implícita de los tipos de los metadatos externos al tipo de datos de cadena que la columna de resultados utiliza.</span><span class="sxs-lookup"><span data-stu-id="82a6c-122">Implicit conversion of external metadata types to the string data type that the output column uses.</span></span><br /><br /> <br /><br /> <span data-ttu-id="82a6c-123">El valor predeterminado es TRUE.</span><span class="sxs-lookup"><span data-stu-id="82a6c-123">The default value is TRUE.</span></span><br /><br /> <span data-ttu-id="82a6c-124">Para más información, consulte [ADO NET Source](ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="82a6c-124">For more information, see [ADO NET Source](ado-net-source.md).</span></span>|  
  
 <span data-ttu-id="82a6c-125">La salida y las columnas de salida del origen de ADO NET no tienen ninguna propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="82a6c-125">The output and the output columns of the ADO NET source have no custom properties.</span></span>  
  
 <span data-ttu-id="82a6c-126">Para más información, consulte [ADO NET Source](ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="82a6c-126">For more information, see [ADO NET Source](ado-net-source.md).</span></span>  
  
 <span data-ttu-id="82a6c-127">**Propiedades personalizadas de los destinos**</span><span class="sxs-lookup"><span data-stu-id="82a6c-127">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="82a6c-128">El destino de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="82a6c-128">The [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="82a6c-129">En la tabla siguiente se describen las propiedades personalizadas del destino [!INCLUDE[vstecado](../../includes/vstecado-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82a6c-129">The following table describes the custom properties of the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination.</span></span> <span data-ttu-id="82a6c-130">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="82a6c-130">All properties are read/write.</span></span> <span data-ttu-id="82a6c-131">Estas propiedades no están disponibles en el **Editor de destinos ADO NET**, pero se pueden establecer con el **Editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="82a6c-131">These properties are not available in the **ADO NET Destination Editor**, but can be set by using the **Advanced Editor**.</span></span>  
  
|<span data-ttu-id="82a6c-132">Propiedad</span><span class="sxs-lookup"><span data-stu-id="82a6c-132">Property</span></span>|<span data-ttu-id="82a6c-133">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="82a6c-133">Data Type</span></span>|<span data-ttu-id="82a6c-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="82a6c-134">Description</span></span>|  
|--------------|---------------|-----------------|  
|<span data-ttu-id="82a6c-135">BatchSize</span><span class="sxs-lookup"><span data-stu-id="82a6c-135">BatchSize</span></span>|<span data-ttu-id="82a6c-136">Entero</span><span class="sxs-lookup"><span data-stu-id="82a6c-136">Integer</span></span>|<span data-ttu-id="82a6c-137">Número de filas de un lote que se envía al servidor.</span><span class="sxs-lookup"><span data-stu-id="82a6c-137">The number of rows in a batch that is sent to the server.</span></span> <span data-ttu-id="82a6c-138">El valor **0** indica que el tamaño del lote coincide con el tamaño del búfer interno.</span><span class="sxs-lookup"><span data-stu-id="82a6c-138">A value of **0** indicates that the batch size matches the internal buffer size.</span></span> <span data-ttu-id="82a6c-139">El valor predeterminado de esta propiedad es **0**.</span><span class="sxs-lookup"><span data-stu-id="82a6c-139">The default value of this property is **0**.</span></span>|  
|<span data-ttu-id="82a6c-140">CommandTimeOut</span><span class="sxs-lookup"><span data-stu-id="82a6c-140">CommandTimeOut</span></span>|<span data-ttu-id="82a6c-141">Entero</span><span class="sxs-lookup"><span data-stu-id="82a6c-141">Integer</span></span>|<span data-ttu-id="82a6c-142">Número máximo de segundos que el comando SQL se puede ejecutar antes de superar el tiempo de espera. Si el valor es **0** , indica un tiempo infinito.</span><span class="sxs-lookup"><span data-stu-id="82a6c-142">The maximum number of seconds that the SQL command can run before timing out. A value of **0** indicates an infinite time.</span></span> <span data-ttu-id="82a6c-143">El valor predeterminado de esta propiedad es **0**.</span><span class="sxs-lookup"><span data-stu-id="82a6c-143">The default value of this property is **0**.</span></span>|  
|<span data-ttu-id="82a6c-144">TableOrViewName</span><span class="sxs-lookup"><span data-stu-id="82a6c-144">TableOrViewName</span></span>|<span data-ttu-id="82a6c-145">String</span><span class="sxs-lookup"><span data-stu-id="82a6c-145">String</span></span>|<span data-ttu-id="82a6c-146">Nombre de la tabla o vista de destino.</span><span class="sxs-lookup"><span data-stu-id="82a6c-146">The name of the destination table or view.</span></span>|  
  
 <span data-ttu-id="82a6c-147">Para más información, consulte [ADO NET Destination](ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="82a6c-147">For more information, see [ADO NET Destination](ado-net-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a6c-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82a6c-148">See Also</span></span>  
 [<span data-ttu-id="82a6c-149">Common Properties</span><span class="sxs-lookup"><span data-stu-id="82a6c-149">Common Properties</span></span>](../common-properties.md)  
  
  