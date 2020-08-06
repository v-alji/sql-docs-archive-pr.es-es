---
title: Editor de destino de procesamiento de particiones (página avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.advanced.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 2039ee0f-069d-479d-90b2-2a12481b1162
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 12845ecd644eabd949ea37fbb18ba6cc9cf342f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663563"
---
# <a name="partition-processing-destination-editor-advanced-page"></a><span data-ttu-id="a6dc3-102">Editor de destino de procesamiento de particiones (página Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="a6dc3-102">Partition Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="a6dc3-103">Utilice la página **Avanzadas** del cuadro de diálogo **Editor de destino de procesamiento de particiones** para configurar el control de errores.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-103">Use the **Advanced** page of the **Partition Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="a6dc3-104">Para obtener más información acerca del destino de procesamiento de particiones, vea [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a6dc3-104">To learn more about the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6dc3-105">Las tareas aquí descritas no se aplican a los modelos tabulares de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="a6dc3-106">No se pueden asignar las columnas de entrada a las de partición para los modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="a6dc3-107">En su lugar puede usar la tarea Ejecutar DDL de Analysis Services [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) para procesar la partición.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a6dc3-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="a6dc3-108">Options</span></span>  
 <span data-ttu-id="a6dc3-109">**Utilizar la configuración de error predeterminada**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-109">**Use default error configuration.**</span></span>  
 <span data-ttu-id="a6dc3-110">Especifica si debe utilizarse el control de errores predeterminado de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6dc3-110">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="a6dc3-111">De manera predeterminada, este valor es `True`.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-111">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="a6dc3-112">**Acción del error de clave**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-112">**Key error action**</span></span>  
 <span data-ttu-id="a6dc3-113">Permite especificar la forma de controlar registros que tienen valores de clave no aceptables.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-113">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="a6dc3-114">Value</span><span class="sxs-lookup"><span data-stu-id="a6dc3-114">Value</span></span>|<span data-ttu-id="a6dc3-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6dc3-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6dc3-116">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-116">**ConvertToUnknown**</span></span>|<span data-ttu-id="a6dc3-117">Convierte el valor de clave no aceptable en el valor Unknown.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-117">Convert the unacceptable key value to the Unknown value.</span></span>|  
|<span data-ttu-id="a6dc3-118">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-118">**DiscardRecord**</span></span>|<span data-ttu-id="a6dc3-119">Descarta el registro.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-119">Discard the record.</span></span>|  
  
 <span data-ttu-id="a6dc3-120">**Omitir errores**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-120">**Ignore errors**</span></span>  
 <span data-ttu-id="a6dc3-121">Especifica que deben omitirse los errores.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-121">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="a6dc3-122">**Detenerse ante errores**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-122">**Stop on error**</span></span>  
 <span data-ttu-id="a6dc3-123">Especifica que el procesamiento debe detenerse cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-123">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="a6dc3-124">**Número de errores**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-124">**Number of errors**</span></span>  
 <span data-ttu-id="a6dc3-125">Especifica el umbral de error donde debe detenerse el procesamiento, en caso de que se haya seleccionado **Detenerse ante errores**.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-125">Specify the error threshold at which processing should stop, if you have selected **Stop on error**.</span></span>  
  
 <span data-ttu-id="a6dc3-126">**Acción ante el error**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-126">**On error action**</span></span>  
 <span data-ttu-id="a6dc3-127">Especifica la acción que debe llevarse a cabo cuando se alcanza el umbral de error, en caso de que se haya seleccionado **Detenerse ante errores**.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-127">Specify the action to take when the error threshold is reached, if you have selected **Stop on error**.</span></span>  
  
|<span data-ttu-id="a6dc3-128">Value</span><span class="sxs-lookup"><span data-stu-id="a6dc3-128">Value</span></span>|<span data-ttu-id="a6dc3-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6dc3-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6dc3-130">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-130">**StopProcessing**</span></span>|<span data-ttu-id="a6dc3-131">Detiene el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-131">Stop processing.</span></span>|  
|<span data-ttu-id="a6dc3-132">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-132">**StopLogging**</span></span>|<span data-ttu-id="a6dc3-133">Detiene el registro de errores.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-133">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="a6dc3-134">**Clave no encontrada**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-134">**Key not found**</span></span>  
 <span data-ttu-id="a6dc3-135">Especifica la acción que debe llevarse a cabo en caso de que se produzca un error de clave no encontrada.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-135">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="a6dc3-136">Este valor es **ReportAndContinue**de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-136">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="a6dc3-137">Value</span><span class="sxs-lookup"><span data-stu-id="a6dc3-137">Value</span></span>|<span data-ttu-id="a6dc3-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6dc3-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6dc3-139">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-139">**IgnoreError**</span></span>|<span data-ttu-id="a6dc3-140">Omite el error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-140">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="a6dc3-141">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-141">**ReportAndContinue**</span></span>|<span data-ttu-id="a6dc3-142">Informa del error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-142">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="a6dc3-143">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-143">**ReportAndStop**</span></span>|<span data-ttu-id="a6dc3-144">Informa del error y detiene el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-144">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="a6dc3-145">**Clave duplicada**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-145">**Duplicate key**</span></span>  
 <span data-ttu-id="a6dc3-146">Especifica la acción que debe llevarse a cabo en caso de que se produzca un error de clave duplicada.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-146">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="a6dc3-147">Este valor es **IgnoreError**de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-147">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="a6dc3-148">Value</span><span class="sxs-lookup"><span data-stu-id="a6dc3-148">Value</span></span>|<span data-ttu-id="a6dc3-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6dc3-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6dc3-150">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-150">**IgnoreError**</span></span>|<span data-ttu-id="a6dc3-151">Omite el error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-151">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="a6dc3-152">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-152">**ReportAndContinue**</span></span>|<span data-ttu-id="a6dc3-153">Informa del error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-153">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="a6dc3-154">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-154">**ReportAndStop**</span></span>|<span data-ttu-id="a6dc3-155">Informa del error y detiene el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-155">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="a6dc3-156">**Clave null convertida en Unknown**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-156">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="a6dc3-157">Especifica la acción que debe llevarse a cabo cuando una clave NULL se ha convertido al valor Unknown.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-157">Specify the action to take when a null key has been converted to the Unknown value.</span></span> <span data-ttu-id="a6dc3-158">Este valor es **IgnoreError**de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-158">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="a6dc3-159">Value</span><span class="sxs-lookup"><span data-stu-id="a6dc3-159">Value</span></span>|<span data-ttu-id="a6dc3-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6dc3-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6dc3-161">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-161">**IgnoreError**</span></span>|<span data-ttu-id="a6dc3-162">Omite el error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-162">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="a6dc3-163">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-163">**ReportAndContinue**</span></span>|<span data-ttu-id="a6dc3-164">Informa del error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-164">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="a6dc3-165">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-165">**ReportAndStop**</span></span>|<span data-ttu-id="a6dc3-166">Informa del error y detiene el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-166">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="a6dc3-167">**Clave null no permitida**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="a6dc3-168">Especifica la acción que debe llevarse a cabo cuando no se permiten claves NULL y se encuentra una clave NULL.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-168">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="a6dc3-169">Este valor es **ReportAndContinue**de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-169">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="a6dc3-170">Value</span><span class="sxs-lookup"><span data-stu-id="a6dc3-170">Value</span></span>|<span data-ttu-id="a6dc3-171">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6dc3-171">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6dc3-172">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-172">**IgnoreError**</span></span>|<span data-ttu-id="a6dc3-173">Omite el error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-173">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="a6dc3-174">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-174">**ReportAndContinue**</span></span>|<span data-ttu-id="a6dc3-175">Informa del error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-175">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="a6dc3-176">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-176">**ReportAndStop**</span></span>|<span data-ttu-id="a6dc3-177">Informa del error y detiene el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-177">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="a6dc3-178">**Ruta de acceso del registro de errores**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-178">**Error log path**</span></span>  
 <span data-ttu-id="a6dc3-179">Escriba la ruta de acceso al registro de errores o seleccione un destino mediante el botón para examinar **(…)** .</span><span class="sxs-lookup"><span data-stu-id="a6dc3-179">Type the path for the error log, or select a destination by using the browse **(...)** button.</span></span>  
  
 <span data-ttu-id="a6dc3-180">**Examinar (...)**</span><span class="sxs-lookup"><span data-stu-id="a6dc3-180">**Browse (...)**</span></span>  
 <span data-ttu-id="a6dc3-181">Seleccione una ruta de acceso para el registro de errores.</span><span class="sxs-lookup"><span data-stu-id="a6dc3-181">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6dc3-182">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6dc3-182">See Also</span></span>  
 <span data-ttu-id="a6dc3-183">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a6dc3-183">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="a6dc3-184">Editor de destino de procesamiento de particiones &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="a6dc3-184">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md)  
  
  
