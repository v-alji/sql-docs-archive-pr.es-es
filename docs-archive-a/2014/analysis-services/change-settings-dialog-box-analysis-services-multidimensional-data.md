---
title: Cuadro de diálogo Cambiar configuración (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.batchsettingsdialog.f1
ms.assetid: 0041e042-d7ce-48f9-a690-a6dc65471ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2649195e3aff4e17d378e54c4b1d656361dfe3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670701"
---
# <a name="change-settings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="e10aa-102">Cuadro de diálogo Cambiar configuración (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="e10aa-102">Change Settings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e10aa-103">Use el cuadro de diálogo **Cambiar configuración** en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] y [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para cambiar la configuración que controla el procesamiento de los objetos enumerados en el cuadro de diálogo **Procesar** .</span><span class="sxs-lookup"><span data-stu-id="e10aa-103">Use the **Change Settings** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to change the settings that govern the processing of objects listed in the **Process** dialog box.</span></span> <span data-ttu-id="e10aa-104">Para mostrar el cuadro de diálogo **Cambiar configuración** , haga clic en **Cambiar configuración** en el cuadro de diálogo **Proceso** .</span><span class="sxs-lookup"><span data-stu-id="e10aa-104">You can display the **Change Settings** dialog box by clicking **Change Settings** on the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e10aa-105"> La configuración especificada en este cuadro de diálogo invalida la configuración heredada de la base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para los objetos enumerados en el cuadro de diálogo **Proceso** .</span><span class="sxs-lookup"><span data-stu-id="e10aa-105">Settings specified in this dialog box override default settings inherited from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database for the objects listed in the **Process** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e10aa-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="e10aa-106">Options</span></span>  
 <span data-ttu-id="e10aa-107">**Opciones de procesamiento**</span><span class="sxs-lookup"><span data-stu-id="e10aa-107">**Processing options**</span></span>  
 <span data-ttu-id="e10aa-108">Utilice esta pestaña para modificar la configuración relacionada con el orden de procesamiento, la tabla de reescritura y los objetos afectados por la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-108">Use this tab to modify settings related to the processing order, writeback table, and affected objects for the processing operation.</span></span> <span data-ttu-id="e10aa-109">Esta pestaña contiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e10aa-109">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="e10aa-110">**Parallel**</span><span class="sxs-lookup"><span data-stu-id="e10aa-110">**Parallel**</span></span>  
 <span data-ttu-id="e10aa-111">Haga clic en esta opción para procesar los objetos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="e10aa-111">Click to process the objects in parallel.</span></span>  
  
 <span data-ttu-id="e10aa-112">**Tareas paralelas máximas**</span><span class="sxs-lookup"><span data-stu-id="e10aa-112">**Maximum parallel tasks**</span></span>  
 <span data-ttu-id="e10aa-113">Seleccione el número máximo de tareas que quiere que la operación de procesamiento ejecute en paralelo o elija **Dejar que el servidor decida** para que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] seleccione el número óptimo de tareas paralelas.</span><span class="sxs-lookup"><span data-stu-id="e10aa-113">Select the maximum number of tasks to execute in parallel by the processing operation, or choose **Let the server decide** to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to select an optimal number of parallel tasks.</span></span>  
  
 <span data-ttu-id="e10aa-114">**Secuencial**</span><span class="sxs-lookup"><span data-stu-id="e10aa-114">**Sequential**</span></span>  
 <span data-ttu-id="e10aa-115">Haga clic en esta opción procesar los objetos de manera secuencial.</span><span class="sxs-lookup"><span data-stu-id="e10aa-115">Click to process the objects sequentially.</span></span>  
  
 <span data-ttu-id="e10aa-116">**Modo de transacción**</span><span class="sxs-lookup"><span data-stu-id="e10aa-116">**Transaction mode**</span></span>  
 <span data-ttu-id="e10aa-117">Elija el modo de transacción que se utiliza cuando los objetos se procesan en orden secuencial:</span><span class="sxs-lookup"><span data-stu-id="e10aa-117">Choose the transaction mode that is used when objects are processed in sequential order:</span></span>  
  
-   <span data-ttu-id="e10aa-118">**Una transacción** procesa todos los objetos en la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="e10aa-118">**One Transaction** processes all objects in the same transaction.</span></span>  
  
-   <span data-ttu-id="e10aa-119">**Transacciones independientes** procesa todos los objetos, incluidos los objetos dependientes, en transacciones independientes.</span><span class="sxs-lookup"><span data-stu-id="e10aa-119">**Separate Transactions** processes all objects, including dependent objects, in separate transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e10aa-120"> Esta opción solo se habilita si se selecciona **Secuenciales** .</span><span class="sxs-lookup"><span data-stu-id="e10aa-120">This option is enabled only if **Sequential** is selected.</span></span>  
  
 <span data-ttu-id="e10aa-121">**Opción de tabla de reescritura**</span><span class="sxs-lookup"><span data-stu-id="e10aa-121">**Writeback table option**</span></span>  
 <span data-ttu-id="e10aa-122">Elija la opción usada para administrar la tabla de reescritura:</span><span class="sxs-lookup"><span data-stu-id="e10aa-122">Choose the option used to manage a writeback table:</span></span>  
  
-   <span data-ttu-id="e10aa-123">**Crear** crea una tabla de reescritura si no existe una.</span><span class="sxs-lookup"><span data-stu-id="e10aa-123">**Create** creates a writeback table if it does not exist.</span></span> <span data-ttu-id="e10aa-124">Se produce un error si la tabla de reescritura ya existe.</span><span class="sxs-lookup"><span data-stu-id="e10aa-124">An error occurs if a writeback table already exists.</span></span>  
  
-   <span data-ttu-id="e10aa-125">**Crear siempre** crea una tabla de reescritura si no existe una o sobrescribe la tabla de reescritura existente si existiese una.</span><span class="sxs-lookup"><span data-stu-id="e10aa-125">**Create always** creates a writeback table if it does not exist, or overwrites the existing writeback table if it does exist.</span></span>  
  
-   <span data-ttu-id="e10aa-126">**Utilizar existente** utiliza la tabla de reescritura existente si es que existe una.</span><span class="sxs-lookup"><span data-stu-id="e10aa-126">**Use existing** uses the existing writeback table if it exists.</span></span> <span data-ttu-id="e10aa-127">Se produce un error si no existe una tabla de reescritura.</span><span class="sxs-lookup"><span data-stu-id="e10aa-127">An error occurs if a writeback table does not exist.</span></span>  
  
 <span data-ttu-id="e10aa-128">**Procesar objetos afectados**</span><span class="sxs-lookup"><span data-stu-id="e10aa-128">**Process affected objects**</span></span>  
 <span data-ttu-id="e10aa-129">Seleccione esta opción para incluir y procesar objetos que dependan de otros objetos incluidos en la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-129">Select to include and process objects that depend on objects included in the processing operation.</span></span>  
  
 <span data-ttu-id="e10aa-130">**Errores de clave de dimensión**</span><span class="sxs-lookup"><span data-stu-id="e10aa-130">**Dimension key errors**</span></span>  
 <span data-ttu-id="e10aa-131">Utilice esta pestaña para modificar la configuración relacionada con la configuración de errores de la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-131">Use this tab to modify settings related to the error configuration for the processing operation.</span></span> <span data-ttu-id="e10aa-132">Esta pestaña contiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e10aa-132">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="e10aa-133">**Usar configuración de error predeterminada**</span><span class="sxs-lookup"><span data-stu-id="e10aa-133">**Use default error configuration**</span></span>  
 <span data-ttu-id="e10aa-134">Seleccione esta opción para utilizar la configuración de errores predeterminada para los objetos en la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-134">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="e10aa-135">**Utilizar la configuración de error personalizada**</span><span class="sxs-lookup"><span data-stu-id="e10aa-135">**Use custom error configuration**</span></span>  
 <span data-ttu-id="e10aa-136">Seleccione esta opción para definir la configuración de error para los objetos de la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-136">Select to define the error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="e10aa-137">**Acción del error de clave**</span><span class="sxs-lookup"><span data-stu-id="e10aa-137">**Key error action**</span></span>  
 <span data-ttu-id="e10aa-138">Elija una de las siguientes acciones que tienen lugar cuando se encuentra una nueva clave que no se puede buscar durante el procesamiento:</span><span class="sxs-lookup"><span data-stu-id="e10aa-138">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="e10aa-139">**Convertir en desconocido** agrega la información del registro en el miembro desconocido.</span><span class="sxs-lookup"><span data-stu-id="e10aa-139">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="e10aa-140">**Descartar registro** excluye la información del registro del procesamiento del objeto.</span><span class="sxs-lookup"><span data-stu-id="e10aa-140">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="e10aa-141">**Omitir recuento de errores**</span><span class="sxs-lookup"><span data-stu-id="e10aa-141">**Ignore errors count**</span></span>  
 <span data-ttu-id="e10aa-142">Haga en esta opción clic para omitir los errores que se producen durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-142">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="e10aa-143">**Detenerse ante errores**</span><span class="sxs-lookup"><span data-stu-id="e10aa-143">**Stop on error**</span></span>  
 <span data-ttu-id="e10aa-144">Haga clic en esta opción para detener el procesamiento cuando se producen errores.</span><span class="sxs-lookup"><span data-stu-id="e10aa-144">Click to stop processing when errors occur.</span></span> <span data-ttu-id="e10aa-145">Esta opción habilita las opciones **Número de errores** y **Acción ante el error** .</span><span class="sxs-lookup"><span data-stu-id="e10aa-145">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="e10aa-146">**Número de errores**</span><span class="sxs-lookup"><span data-stu-id="e10aa-146">**Number of errors**</span></span>  
 <span data-ttu-id="e10aa-147">Escriba el número de errores que se ignorarán antes de que el proceso se detenga.</span><span class="sxs-lookup"><span data-stu-id="e10aa-147">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="e10aa-148">**Acción ante el error**</span><span class="sxs-lookup"><span data-stu-id="e10aa-148">**On error action**</span></span>  
 <span data-ttu-id="e10aa-149">Elija una de las siguientes acciones para que se realice cuando el número de errores supere el valor de **Número de errores**:</span><span class="sxs-lookup"><span data-stu-id="e10aa-149">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="e10aa-150">**Detener el procesamiento** finaliza la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-150">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="e10aa-151">**Detener el registro** detiene el registro de errores, pero continúa la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-151">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="e10aa-152">**Clave no encontrada**</span><span class="sxs-lookup"><span data-stu-id="e10aa-152">**Key not found**</span></span>  
 <span data-ttu-id="e10aa-153">Especifique una de las siguientes acciones para que se lleve a cabo cuando no se encuentre una clave al procesar un objeto:</span><span class="sxs-lookup"><span data-stu-id="e10aa-153">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="e10aa-154">**Omitir error** omite el error.</span><span class="sxs-lookup"><span data-stu-id="e10aa-154">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="e10aa-155">**Informar y continuar** notifica el error y continúa con la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-155">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="e10aa-156">**Informar y detenerse** informa del error y detiene la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-156">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="e10aa-157">**Clave duplicada**</span><span class="sxs-lookup"><span data-stu-id="e10aa-157">**Duplicate key**</span></span>  
 <span data-ttu-id="e10aa-158">Especifique una de las siguientes acciones para que se lleve a cabo si se encuentra una clave duplicada al procesar un objeto:</span><span class="sxs-lookup"><span data-stu-id="e10aa-158">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="e10aa-159">**Omitir error** omite el error.</span><span class="sxs-lookup"><span data-stu-id="e10aa-159">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="e10aa-160">**Informar y continuar** notifica el error y continúa con la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-160">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="e10aa-161">**Informar y detenerse** informa del error y detiene la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-161">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="e10aa-162">**Clave null convertida en Unknown**</span><span class="sxs-lookup"><span data-stu-id="e10aa-162">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="e10aa-163">Especifique una de las siguientes acciones para que se lleve a cabo cuando se agregue una clave de miembro NULL al miembro desconocido durante el procesamiento de un objeto:</span><span class="sxs-lookup"><span data-stu-id="e10aa-163">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed:</span></span>  
  
-   <span data-ttu-id="e10aa-164">**Omitir error** omite el error.</span><span class="sxs-lookup"><span data-stu-id="e10aa-164">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="e10aa-165">**Informar y continuar** notifica el error y continúa con la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-165">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="e10aa-166">**Informar y detenerse** informa del error y detiene la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-166">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="e10aa-167">**Clave null no permitida**</span><span class="sxs-lookup"><span data-stu-id="e10aa-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="e10aa-168">Especifique una de las siguientes acciones para que se lleve a cabo si se encuentra una clave NULL que no está permitida cuando se procesa un objeto:</span><span class="sxs-lookup"><span data-stu-id="e10aa-168">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed:</span></span>  
  
-   <span data-ttu-id="e10aa-169">**Omitir error** omite el error.</span><span class="sxs-lookup"><span data-stu-id="e10aa-169">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="e10aa-170">**Informar y continuar** notifica el error y continúa con la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-170">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="e10aa-171">**Informar y detenerse** informa del error y detiene la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e10aa-171">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="e10aa-172">**Ruta de acceso del registro de errores**</span><span class="sxs-lookup"><span data-stu-id="e10aa-172">**Error log path**</span></span>  
 <span data-ttu-id="e10aa-173">Escriba la ruta de acceso completa y un nombre para el archivo de registro de errores.</span><span class="sxs-lookup"><span data-stu-id="e10aa-173">Type the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="e10aa-174">**Browse**</span><span class="sxs-lookup"><span data-stu-id="e10aa-174">**Browse**</span></span>  
 <span data-ttu-id="e10aa-175">Haga clic en esta acción para abrir el cuadro de diálogo **Abrir** y seleccionar la ruta de acceso completa y el nombre de archivo correspondiente al archivo del registro de errores.</span><span class="sxs-lookup"><span data-stu-id="e10aa-175">Click to open the **Open** dialog box and select the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="e10aa-176">**Procesar objetos afectados**</span><span class="sxs-lookup"><span data-stu-id="e10aa-176">**Process affected objects**</span></span>  
 <span data-ttu-id="e10aa-177">Haga clic en esta acción para procesar los objetos que dependan de los objetos seleccionados en el cuadro de diálogo **Proceso** .</span><span class="sxs-lookup"><span data-stu-id="e10aa-177">Click to process the objects that have a dependency on the objects selected in the **Process** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e10aa-178">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e10aa-178">See Also</span></span>  
 <span data-ttu-id="e10aa-179">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e10aa-179">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e10aa-180">Cuadro de diálogo procesar &#40;Analysis Services-datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="e10aa-180">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
