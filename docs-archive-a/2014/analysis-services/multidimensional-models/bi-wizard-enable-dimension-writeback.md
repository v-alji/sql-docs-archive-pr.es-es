---
title: Habilitar reescritura en la dimensión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying dimensions
- writeback [Analysis Services], setting up
- dimensions [Analysis Services], Business Intelligence enhancements
- Business Intelligence enhancements [Analysis Services], writeback
- dimensions [Analysis Services], writeback
- writeback [Analysis Services]
- dimensions [Analysis Services], modifying
- manual dimension structure modifications
ms.assetid: a4b5eb5a-366d-4fc8-ad0d-5bdb8e7b4163
author: minewiskan
ms.author: owend
ms.openlocfilehash: cba4a54e8a51d022c6f84a4c81d32f359a95692a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670654"
---
# <a name="enable-dimension-writeback"></a><span data-ttu-id="c925f-102">Habilitar reescritura en la dimensión</span><span class="sxs-lookup"><span data-stu-id="c925f-102">Enable Dimension Writeback</span></span>
  <span data-ttu-id="c925f-103">Agregar la mejora de reescritura de dimensiones a un cubo o dimensión para permitir que los usuarios modifiquen manualmente la estructura y los miembros de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="c925f-103">Add the dimension writeback enhancement to a cube or dimension to allow users to manually modify the dimension structure and members.</span></span> <span data-ttu-id="c925f-104">Las actualizaciones de una dimensión habilitada para escritura se registran directamente en la tabla de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="c925f-104">Updates to a write-enabled dimension are recorded directly in the dimension table.</span></span> <span data-ttu-id="c925f-105">Esta mejora cambia la configuración de la propiedad `WriteEnabled` para una dimensión.</span><span class="sxs-lookup"><span data-stu-id="c925f-105">This enhancement changes the `WriteEnabled` property setting for a dimension.</span></span>  
  
 <span data-ttu-id="c925f-106">Para agregar la reescritura de dimensiones, se usa el Asistente de Business Intelligence y se selecciona la opción **Habilitar reescritura en la dimensión** en la página **Elegir mejora** .</span><span class="sxs-lookup"><span data-stu-id="c925f-106">To add dimension writeback, you use the Business Intelligence Wizard, and select the **Enable dimension writeback** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="c925f-107">Este asistente le guía por los pasos para seleccionar la dimensión a la que desee aplicar la reescritura de dimensiones y establecer esta opción para la dimensión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c925f-107">This wizard then guides you through the steps of selecting a dimension to which you want to apply dimension writeback and setting this option for the selected dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c925f-108">La reescritura solo es compatible para bases de datos relacionales de SQL Server y data marts.</span><span class="sxs-lookup"><span data-stu-id="c925f-108">Writeback is supported for SQL Server relational databases and data marts only.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="c925f-109">Seleccionar una dimensión</span><span class="sxs-lookup"><span data-stu-id="c925f-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="c925f-110">En la primera página **Habilitar reescritura en la dimensión** del asistente, se especifica la dimensión a la que se desea aplicar la reescritura.</span><span class="sxs-lookup"><span data-stu-id="c925f-110">On the first **Enable Dimension Writeback** page of the wizard, you specify the dimension to which you want to apply dimension writeback.</span></span> <span data-ttu-id="c925f-111">La mejora de reescritura de dimensiones agregada a esta dimensión seleccionada produce cambios en la dimensión.</span><span class="sxs-lookup"><span data-stu-id="c925f-111">The dimension writeback enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="c925f-112">Estos cambios son heredados por todos los cubos que incluyan la dimensión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c925f-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="setting-dimension-writeback-capability"></a><span data-ttu-id="c925f-113">Establecer la capacidad de reescritura de dimensiones</span><span class="sxs-lookup"><span data-stu-id="c925f-113">Setting Dimension Writeback Capability</span></span>  
 <span data-ttu-id="c925f-114">En la segunda página **Habilitar reescritura en la dimensión** del asistente se establece la opción **Habilitar reescritura en la dimensión** .</span><span class="sxs-lookup"><span data-stu-id="c925f-114">On the second **Enable Dimension Writeback** page of the wizard, you actually set the **Enable writeback in the dimension** option.</span></span> <span data-ttu-id="c925f-115">Al seleccionar esta opción se establece automáticamente la propiedad `WriteEnabled` de la dimensión como `True`.</span><span class="sxs-lookup"><span data-stu-id="c925f-115">Selecting this option automatically sets the `WriteEnabled` property of the dimension to `True`.</span></span> <span data-ttu-id="c925f-116">Al eliminar la selección de esta opción, se establece automáticamente la propiedad como `False`.</span><span class="sxs-lookup"><span data-stu-id="c925f-116">Clearing this option automatically sets the property to `False`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c925f-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c925f-117">Remarks</span></span>  
 <span data-ttu-id="c925f-118">Al crear un nuevo miembro, debe incluir todos los atributos en una dimensión.</span><span class="sxs-lookup"><span data-stu-id="c925f-118">When you create a new member, you must include every attribute in a dimension.</span></span> <span data-ttu-id="c925f-119">No puede insertar un miembro sin especificar un valor para el atributo clave de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="c925f-119">You cannot insert a member without specifying a value for the key attribute of the dimension.</span></span> <span data-ttu-id="c925f-120">Por lo tanto, la creación de miembros está sujeta a las restricciones (como los valores de clave no nulos) definidas en la tabla de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="c925f-120">Therefore, creating members is subject to any constraints (such as non-null key values) that are defined on the dimension table.</span></span> <span data-ttu-id="c925f-121">También debe tener en cuenta las columnas especificadas opcionalmente por las propiedades de la dimensión, como las columnas especificadas en las propiedades de la dimensión `CustomRollupColumn`, `CustomRollupPropertiesColumn` o `UnaryOperatorColumn`.</span><span class="sxs-lookup"><span data-stu-id="c925f-121">You should also consider columns optionally specified by dimension properties, such as columns specified in the `CustomRollupColumn`, `CustomRollupPropertiesColumn` or the `UnaryOperatorColumn` dimension properties.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="c925f-122">Si usa SQL Azure como origen de datos para realizar la reescritura en una base de datos de Analysis Services, se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="c925f-122">If you use SQL Azure as a data source to perform writeback into an Analysis Services database, the operation fails.</span></span> <span data-ttu-id="c925f-123">Esto es así por cuestiones de diseño, porque la opción del proveedor que permite que haya varios conjuntos de resultados (MARS) activos no está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c925f-123">This is by design, because the provider option that enables multiple active result sets (MARS) is not turned on by default.</span></span>  
>   
>  <span data-ttu-id="c925f-124">La solución es agregar el valor siguiente en la cadena de conexión, para admitir MARS y habilitar la reescritura:</span><span class="sxs-lookup"><span data-stu-id="c925f-124">The workaround is to add the following setting in the connection string, to support MARS and to enable writeback:</span></span>  
>   
>  `"MultipleActiveResultSets=True"`  
>   
>  <span data-ttu-id="c925f-125">Para más información, vea [Utilizar conjuntos de resultados activos múltiples &#40;MARS&#41;](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span><span class="sxs-lookup"><span data-stu-id="c925f-125">For more information see [Using Multiple Active Result Sets &#40;MARS&#41;](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c925f-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c925f-126">See Also</span></span>  
 [<span data-ttu-id="c925f-127">Dimensiones habilitadas para escritura</span><span class="sxs-lookup"><span data-stu-id="c925f-127">Write-Enabled Dimensions</span></span>](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  
