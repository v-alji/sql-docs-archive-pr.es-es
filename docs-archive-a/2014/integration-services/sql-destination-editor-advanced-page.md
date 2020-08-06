---
title: Editor de destino de SQL (página avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.advanced.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 9b46bcf8-ddaf-4d7d-90a6-80bc19517e9b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ccf25ad888c93f694678a152417affe5c0e16091
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669746"
---
# <a name="sql-destination-editor-advanced-page"></a><span data-ttu-id="bb349-102">Editor de destino de SQL (página Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="bb349-102">SQL Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="bb349-103">Utilice la página **Avanzadas** del cuadro de diálogo **Editor de destino de SQL** para especificar opciones avanzadas de inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="bb349-103">Use the **Advanced** page of the **SQL Destination Editor** dialog box to specify advanced bulk insert options.</span></span>  
  
 <span data-ttu-id="bb349-104">Para obtener más información acerca del destino de SQL Server, vea [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="bb349-104">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bb349-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="bb349-105">Options</span></span>  
 <span data-ttu-id="bb349-106">**Mantener valores de identidad**</span><span class="sxs-lookup"><span data-stu-id="bb349-106">**Keep identity**</span></span>  
 <span data-ttu-id="bb349-107">Especifique si la tarea debe insertar valores en columnas de identidad.</span><span class="sxs-lookup"><span data-stu-id="bb349-107">Specify whether the task should insert values into identity columns.</span></span> <span data-ttu-id="bb349-108">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="bb349-108">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="bb349-109">**Mantener valores NULL**</span><span class="sxs-lookup"><span data-stu-id="bb349-109">**Keep nulls**</span></span>  
 <span data-ttu-id="bb349-110">Especifique si la tarea debe mantener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="bb349-110">Specify whether the task should keep null values.</span></span> <span data-ttu-id="bb349-111">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="bb349-111">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="bb349-112">**Bloqueo de tabla**</span><span class="sxs-lookup"><span data-stu-id="bb349-112">**Table lock**</span></span>  
 <span data-ttu-id="bb349-113">Especifique si la tabla está bloqueada cuando se cargan los datos.</span><span class="sxs-lookup"><span data-stu-id="bb349-113">Specify whether the table is locked when the data is loaded.</span></span> <span data-ttu-id="bb349-114">El valor predeterminado de esta propiedad es `True`.</span><span class="sxs-lookup"><span data-stu-id="bb349-114">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="bb349-115">**Restricciones CHECK**</span><span class="sxs-lookup"><span data-stu-id="bb349-115">**Check constraints**</span></span>  
 <span data-ttu-id="bb349-116">Especifique si la tarea debe comprobar restricciones.</span><span class="sxs-lookup"><span data-stu-id="bb349-116">Specify whether the task should check constraints.</span></span> <span data-ttu-id="bb349-117">El valor predeterminado de esta propiedad es `True`.</span><span class="sxs-lookup"><span data-stu-id="bb349-117">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="bb349-118">**Activar desencadenadores**</span><span class="sxs-lookup"><span data-stu-id="bb349-118">**Fire triggers**</span></span>  
 <span data-ttu-id="bb349-119">Especifique si la inserción masiva debe activar desencadenadores en tablas.</span><span class="sxs-lookup"><span data-stu-id="bb349-119">Specify whether the bulk insert should fire triggers on tables.</span></span> <span data-ttu-id="bb349-120">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="bb349-120">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="bb349-121">**Primera fila**</span><span class="sxs-lookup"><span data-stu-id="bb349-121">**First Row**</span></span>  
 <span data-ttu-id="bb349-122">Especifique la primera fila donde se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="bb349-122">Specify the first row to insert.</span></span> <span data-ttu-id="bb349-123">El valor predeterminado de esta propiedad es **-1**, que indica que no se ha asignado ningún valor.</span><span class="sxs-lookup"><span data-stu-id="bb349-123">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb349-124">Borre el cuadro de texto del **Editor de destino de SQL** para indicar que no desea asignar un valor a esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="bb349-124">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="bb349-125">Use -1 en la ventana **Propiedades** , el **Editor avanzado**y el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="bb349-125">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="bb349-126">**Última fila**</span><span class="sxs-lookup"><span data-stu-id="bb349-126">**Last Row**</span></span>  
 <span data-ttu-id="bb349-127">Especifique la última fila donde se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="bb349-127">Specify the last row to insert.</span></span> <span data-ttu-id="bb349-128">El valor predeterminado de esta propiedad es **-1**, que indica que no se ha asignado ningún valor.</span><span class="sxs-lookup"><span data-stu-id="bb349-128">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb349-129">Borre el cuadro de texto del **Editor de destino de SQL** para indicar que no desea asignar un valor a esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="bb349-129">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="bb349-130">Use -1 en la ventana **Propiedades** , el **Editor avanzado**y el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="bb349-130">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="bb349-131">**Número máximo de errores**</span><span class="sxs-lookup"><span data-stu-id="bb349-131">**Maximum number of errors**</span></span>  
 <span data-ttu-id="bb349-132">Especifique el número de errores que se pueden producir antes de que se detenga la inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="bb349-132">Specify the number of errors that can occur before the bulk insert stops.</span></span> <span data-ttu-id="bb349-133">El valor predeterminado de esta propiedad es **-1**, que indica que no se ha asignado ningún valor.</span><span class="sxs-lookup"><span data-stu-id="bb349-133">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb349-134">Borre el cuadro de texto del **Editor de destino de SQL** para indicar que no desea asignar un valor a esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="bb349-134">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="bb349-135">Use -1 en la ventana **Propiedades** , el **Editor avanzado**y el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="bb349-135">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="bb349-136">**Tiempo de espera**</span><span class="sxs-lookup"><span data-stu-id="bb349-136">**Timeout**</span></span>  
 <span data-ttu-id="bb349-137">Especifique el número de segundos que se debe esperar antes de que la inserción masiva se detenga debido a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="bb349-137">Specify the number of seconds to wait before the bulk insert stops because of a time-out.</span></span>  
  
 <span data-ttu-id="bb349-138">**Columnas de orden**</span><span class="sxs-lookup"><span data-stu-id="bb349-138">**Order columns**</span></span>  
 <span data-ttu-id="bb349-139">Escriba los nombres de las columnas de orden.</span><span class="sxs-lookup"><span data-stu-id="bb349-139">Type the names of the sort columns.</span></span> <span data-ttu-id="bb349-140">Las columnas se pueden ordenar en sentido ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="bb349-140">Each column can be sorted in ascending or descending order.</span></span> <span data-ttu-id="bb349-141">Si utiliza varias columnas de orden, delimite la lista con comas.</span><span class="sxs-lookup"><span data-stu-id="bb349-141">If you use multiple sort columns, delimit the list with commas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb349-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb349-142">See Also</span></span>  
 <span data-ttu-id="bb349-143">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bb349-143">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="bb349-144">[Editor de destino de SQL &#40;página Administrador de conexiones&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="bb349-144">[SQL Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="bb349-145">[&#40;página asignaciones del editor de destino de SQL&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="bb349-145">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="bb349-146">Realizar una carga masiva de datos mediante el destino de SQL Server</span><span class="sxs-lookup"><span data-stu-id="bb349-146">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
