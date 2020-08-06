---
title: Configuración de errores (cuadro de diálogo estructura de minería de datos) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.miningstructuredialog.general.f1
ms.assetid: d9aa028b-bad9-49c7-a81c-c2150e4dd481
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5eb41da36400271a9b058ecf275d26bd22d3ee53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677921"
---
# <a name="error-configuration-mining-structure-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="ba7c7-102">Configuración de errores (cuadro de diálogo Propiedades de la estructura de minería de datos) (Analysis Services: datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="ba7c7-102">Error Configuration (Mining Structure Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ba7c7-103">Use la página **Configuración de errores** del cuadro de diálogo **Propiedades de la estructura de minería de datos** de **SQL Server Management Studio** para definir las propiedades de configuración de errores de una estructura de minería de datos en una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba7c7-103">Use the **Error Configuration** page of the **Mining Structure Properties** dialog box in **SQL Server Management Studio** to set the error configuration properties of a mining structure in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ba7c7-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="ba7c7-104">Options</span></span>  
 <span data-ttu-id="ba7c7-105">**Usar configuración de error predeterminada**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-105">**Use default error configuration**</span></span>  
 <span data-ttu-id="ba7c7-106">Seleccione esta opción para utilizar la configuración de errores predeterminada para los objetos en la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-106">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="ba7c7-107">**Acción del error de clave**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-107">**Key error action**</span></span>  
 <span data-ttu-id="ba7c7-108">Elija una de las siguientes acciones que tienen lugar cuando se encuentra una nueva clave que no se puede buscar durante el procesamiento:</span><span class="sxs-lookup"><span data-stu-id="ba7c7-108">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="ba7c7-109">**Convertir en desconocido** agrega la información del registro en el miembro desconocido.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-109">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="ba7c7-110">**Descartar registro** excluye la información del registro del procesamiento del objeto.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-110">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="ba7c7-111">**Omitir recuento de errores**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-111">**Ignore errors count**</span></span>  
 <span data-ttu-id="ba7c7-112">Haga en esta opción clic para omitir los errores que se producen durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-112">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="ba7c7-113">**Detenerse ante errores**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-113">**Stop on error**</span></span>  
 <span data-ttu-id="ba7c7-114">Haga clic en esta opción para detener el procesamiento cuando se producen errores.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-114">Click to stop processing when errors occur.</span></span> <span data-ttu-id="ba7c7-115">Esta opción habilita las opciones **Número de errores** y **Acción ante el error** .</span><span class="sxs-lookup"><span data-stu-id="ba7c7-115">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="ba7c7-116">**Número de errores**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-116">**Number of errors**</span></span>  
 <span data-ttu-id="ba7c7-117">Escriba el número de errores que se ignorarán antes de que el proceso se detenga.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-117">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="ba7c7-118">**Acción ante el error**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-118">**On error action**</span></span>  
 <span data-ttu-id="ba7c7-119">Elija una de las siguientes acciones para que se realice cuando el número de errores supere el valor de **Número de errores**:</span><span class="sxs-lookup"><span data-stu-id="ba7c7-119">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="ba7c7-120">**Detener el procesamiento** finaliza la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-120">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="ba7c7-121">**Detener el registro** detiene el registro de errores, pero continúa la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-121">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="ba7c7-122">**Clave no encontrada**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-122">**Key not found**</span></span>  
 <span data-ttu-id="ba7c7-123">Especifique una de las siguientes acciones para que se lleve a cabo cuando no se encuentre una clave al procesar un objeto:</span><span class="sxs-lookup"><span data-stu-id="ba7c7-123">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="ba7c7-124">**Omitir error** omite el error.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-124">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="ba7c7-125">**Informar y continuar** informa del error y continúa la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-125">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="ba7c7-126">**Informar y detenerse** informa del error y detiene la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-126">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="ba7c7-127">**Clave duplicada**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-127">**Duplicate key**</span></span>  
 <span data-ttu-id="ba7c7-128">Especifique una de las siguientes acciones para que se lleve a cabo si se encuentra una clave duplicada al procesar un objeto:</span><span class="sxs-lookup"><span data-stu-id="ba7c7-128">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="ba7c7-129">**Omitir error** omite el error.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-129">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="ba7c7-130">**Informar y continuar** informa del error y continúa la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-130">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="ba7c7-131">**Informar y detenerse** informa del error y detiene la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-131">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="ba7c7-132">**Clave null convertida en Unknown**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-132">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="ba7c7-133">Especifique una de las siguientes acciones para que se lleve a cabo cuando se agregue una clave de miembro NULL al procesar un objeto:</span><span class="sxs-lookup"><span data-stu-id="ba7c7-133">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed.</span></span>  
  
-   <span data-ttu-id="ba7c7-134">**Omitir error** omite el error.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-134">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="ba7c7-135">**Informar y continuar** informa del error y continúa la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-135">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="ba7c7-136">**Informar y detenerse** informa del error y detiene la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-136">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="ba7c7-137">**Clave null no permitida**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-137">**Null key not allowed**</span></span>  
 <span data-ttu-id="ba7c7-138">Especifique una de las siguientes acciones para que se lleve a cabo cuando se encuentre una clave NULL al procesar un objeto:</span><span class="sxs-lookup"><span data-stu-id="ba7c7-138">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed.</span></span>  
  
-   <span data-ttu-id="ba7c7-139">**Omitir error** omite el error.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-139">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="ba7c7-140">**Informar y continuar** informa del error y continúa la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-140">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="ba7c7-141">**Informar y detenerse** informa del error y detiene la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-141">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="ba7c7-142">**Ruta de acceso del registro de errores**</span><span class="sxs-lookup"><span data-stu-id="ba7c7-142">**Error log path**</span></span>  
 <span data-ttu-id="ba7c7-143">Escriba la ruta de acceso completa y un nombre para el archivo de registro de errores.</span><span class="sxs-lookup"><span data-stu-id="ba7c7-143">Type the full path and file name for the error log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba7c7-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba7c7-144">See Also</span></span>  
 <span data-ttu-id="ba7c7-145">[Cuadro de diálogo Propiedades de la estructura de minería de datos &#40;Analysis Services-minería de datos&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ba7c7-145">[Mining Structure Properties Dialog &#40;Analysis Services - Data Mining&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="ba7c7-146">General &#40;cuadro de diálogo estructura de minería de datos&#41; &#40;Analysis Services-minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="ba7c7-146">General &#40;Mining Structure Dialog Box&#41; &#40;Analysis Services - Data Mining&#41;</span></span>](general-mining-structure-dialog-box-analysis-services-data-mining.md)  
  
  
