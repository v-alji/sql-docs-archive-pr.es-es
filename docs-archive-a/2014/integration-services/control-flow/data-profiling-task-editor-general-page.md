---
title: Editor de la tarea de generación de perfiles de datos (página General) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataprofilingtask.general.f1
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: eec15906-d757-4079-b2f6-aca4e52b3b4c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cfcdf472f817d3dd688a5f867ac74d46835ab91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674259"
---
# <a name="data-profiling-task-editor-general-page"></a><span data-ttu-id="d3c31-102">Editor de tareas de generación de perfiles de datos (página General)</span><span class="sxs-lookup"><span data-stu-id="d3c31-102">Data Profiling Task Editor (General Page)</span></span>
  <span data-ttu-id="d3c31-103">Utilice la página **General** del **Editor de tareas de generación de perfiles de datos** para configurar las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3c31-103">Use the **General** page of the **Data Profiling Task Editor** to configure the following options:</span></span>  
  
-   <span data-ttu-id="d3c31-104">Especifique el destino para el perfil generado.</span><span class="sxs-lookup"><span data-stu-id="d3c31-104">Specify the destination for the profile output.</span></span>  
  
-   <span data-ttu-id="d3c31-105">Utilice la configuración predeterminada para simplificar la tarea de generar perfiles de una sola tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="d3c31-105">Use the default settings to simplify the task of profiling a single table or view.</span></span>  
  
 <span data-ttu-id="d3c31-106">Para más información sobre cómo usar la tarea de generación de perfiles de datos, vea [Configuración de la Tarea de generación de perfiles de datos](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="d3c31-106">For more information about how to use the Data Profiling task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="d3c31-107">Para más información sobre cómo usar el Visor de perfil de datos para analizar la salida de la tarea de generación de perfiles de datos, vea [Visor de perfil de datos](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="d3c31-107">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
 <span data-ttu-id="d3c31-108">**Para abrir la página General del Editor de tareas de generación de perfiles de datos**</span><span class="sxs-lookup"><span data-stu-id="d3c31-108">**To open the General page of the Data Profiling Task Editor**</span></span>  
  
1.  <span data-ttu-id="d3c31-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que tiene la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="d3c31-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that has the Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="d3c31-110">En la pestaña **Flujo de control** , haga doble clic en la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="d3c31-110">On the **Control Flow** tab, double-click the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="d3c31-111">En el **Editor de tareas de generación de perfiles de datos**, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="d3c31-111">In the **Data Profiling Task Editor**, click **General**.</span></span>  
  
## <a name="data-profiling-options"></a><span data-ttu-id="d3c31-112">Opciones de la generación de perfiles de datos</span><span class="sxs-lookup"><span data-stu-id="d3c31-112">Data Profiling Options</span></span>  
 <span data-ttu-id="d3c31-113">**Tiempo de espera**</span><span class="sxs-lookup"><span data-stu-id="d3c31-113">**Timeout**</span></span>  
 <span data-ttu-id="d3c31-114">Especifique el número de segundos transcurridos los cuales la tarea de generación de datos debe agotar el tiempo de espera y dejar de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d3c31-114">Specify the number of seconds after which the Data Profiling task should timeout and stop running.</span></span> <span data-ttu-id="d3c31-115">El valor predeterminado es 0, lo que no indica ningún tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d3c31-115">The default value is 0, which indicates no timeout.</span></span>  
  
## <a name="destination-options"></a><span data-ttu-id="d3c31-116">Opciones de destino</span><span class="sxs-lookup"><span data-stu-id="d3c31-116">Destination Options</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3c31-117">El archivo de salida podría contener datos confidenciales acerca de la base de datos y de los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="d3c31-117">The output file might contain sensitive data about your database and the data that database contains.</span></span> <span data-ttu-id="d3c31-118">Para conocer sugerencias sobre cómo hacer que este archivo sea más seguro, vea [Acceso a los archivos usados por los paquetes](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="d3c31-118">For suggestions about how to make this file more secure, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="d3c31-119">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="d3c31-119">**DestinationType**</span></span>  
 <span data-ttu-id="d3c31-120">Especifique si guardar el perfil de los datos generado en un archivo o una variable:</span><span class="sxs-lookup"><span data-stu-id="d3c31-120">Specify whether to save the data profile output to a file or a variable:</span></span>  
  
|<span data-ttu-id="d3c31-121">Value</span><span class="sxs-lookup"><span data-stu-id="d3c31-121">Value</span></span>|<span data-ttu-id="d3c31-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3c31-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d3c31-123">**FileConnection**</span><span class="sxs-lookup"><span data-stu-id="d3c31-123">**FileConnection**</span></span>|<span data-ttu-id="d3c31-124">Guarde el perfil generado en un archivo de la ubicación que se especifica en un administrador de conexiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="d3c31-124">Save the profile output to a file in the location that is specified in a File connection manager.</span></span><br /><br /> <span data-ttu-id="d3c31-125">Nota: Para especificar qué administrador de conexiones de archivos utilizar, use la opción **Destino** .</span><span class="sxs-lookup"><span data-stu-id="d3c31-125">Note: You specify which File connection manager to use in the **Destination** option.</span></span>|  
|<span data-ttu-id="d3c31-126">**Variable**</span><span class="sxs-lookup"><span data-stu-id="d3c31-126">**Variable**</span></span>|<span data-ttu-id="d3c31-127">Guarde el perfil generado en una variable de paquete.</span><span class="sxs-lookup"><span data-stu-id="d3c31-127">Save the profile output to a package variable.</span></span><br /><br /> <span data-ttu-id="d3c31-128">Para especificar qué variable de paquete utilizar, use la opción **Destino** .</span><span class="sxs-lookup"><span data-stu-id="d3c31-128">Note: You specify which package variable to use in the **Destination** option.</span></span>|  
  
 <span data-ttu-id="d3c31-129">**Destino**</span><span class="sxs-lookup"><span data-stu-id="d3c31-129">**Destination**</span></span>  
 <span data-ttu-id="d3c31-130">Especifique qué administrador de conexiones de archivos o variable de paquete contiene el perfil de datos generado:</span><span class="sxs-lookup"><span data-stu-id="d3c31-130">Specify which File connection manager or package variable contains the data profile output:</span></span>  
  
-   <span data-ttu-id="d3c31-131">Si la opción **DestinationType** está establecida en **FileConnection**, la opción **Destination** muestra los administradores de conexión de archivos disponibles.</span><span class="sxs-lookup"><span data-stu-id="d3c31-131">If the **DestinationType** option is set to **FileConnection**, the **Destination** option displays the available File connection managers.</span></span> <span data-ttu-id="d3c31-132">Seleccione uno de estos administradores de conexiones, o bien seleccione \<New File connection> para crear un administrador de conexiones de archivos nuevo.</span><span class="sxs-lookup"><span data-stu-id="d3c31-132">Select one of these connection managers, or select \<New File connection> to create a new File connection manager.</span></span>  
  
-   <span data-ttu-id="d3c31-133">Si la opción **DestinationType** está establecida en **Variable**, la opción **Destination** muestra las variables de paquete disponibles en la lista **Destination** .</span><span class="sxs-lookup"><span data-stu-id="d3c31-133">If the **DestinationType** option is set to **Variable**, the **Destination** option displays the available package variables in the **Destination** list.</span></span> <span data-ttu-id="d3c31-134">Seleccione una de estas variables, o bien seleccione \<New Variable> para crear una variable nueva.</span><span class="sxs-lookup"><span data-stu-id="d3c31-134">Select one of these variables, or select \<New Variable> to create a new variable.</span></span>  
  
 <span data-ttu-id="d3c31-135">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="d3c31-135">**OverwriteDestination**</span></span>  
 <span data-ttu-id="d3c31-136">Especifique si sobrescribir el archivo de salida si ya existe.</span><span class="sxs-lookup"><span data-stu-id="d3c31-136">Specify whether to overwrite the output file if it already exists.</span></span> <span data-ttu-id="d3c31-137">El valor predeterminado es **False**.</span><span class="sxs-lookup"><span data-stu-id="d3c31-137">The default value is **False**.</span></span> <span data-ttu-id="d3c31-138">El valor de esta propiedad se usa cuando la opción DestinationType está establecida en FileConnection.</span><span class="sxs-lookup"><span data-stu-id="d3c31-138">The value of this property is used only when the DestinationType option is set to FileConnection.</span></span> <span data-ttu-id="d3c31-139">Cuando la opción DestinationType está establecida en Variable, la tarea siempre sobrescribe el valor anterior de la variable.</span><span class="sxs-lookup"><span data-stu-id="d3c31-139">When the DestinationType option is set to Variable, the task always overwrites the previous value of the variable.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3c31-140">Si intenta ejecutar la tarea de generación de perfiles de datos más de una vez sin cambiar el nombre del archivo de salida o el valor de la propiedad **OverwriteDestination** a **True**, se produce un error en la tarea con un mensaje que indica que el archivo de salida ya existe.</span><span class="sxs-lookup"><span data-stu-id="d3c31-140">If you try to run the Data Profiling task more than once without changing the output file name or changing the value of the **OverwriteDestination** property to **True**, the task fails with the message that the output file already exists.</span></span>  
  
## <a name="other-options"></a><span data-ttu-id="d3c31-141">Otras opciones</span><span class="sxs-lookup"><span data-stu-id="d3c31-141">Other Options</span></span>  
 <span data-ttu-id="d3c31-142">**Perfil rápido**</span><span class="sxs-lookup"><span data-stu-id="d3c31-142">**Quick Profile**</span></span>  
 <span data-ttu-id="d3c31-143">Muestre el **Formulario de perfil rápido de tabla única**.</span><span class="sxs-lookup"><span data-stu-id="d3c31-143">Display the **Single Table Quick Profile Form**.</span></span> <span data-ttu-id="d3c31-144">Este formulario simplifica la tarea de generar perfiles de una tabla o vista únicas con la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d3c31-144">This form simplifies the task of profiling a single table or view by using default settings.</span></span> <span data-ttu-id="d3c31-145">Para más información, vea [Formulario de perfil rápido de tabla única &#40;tarea de generación de perfiles de datos&#41;](single-table-quick-profile-form-data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="d3c31-145">For more information, see [Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md).</span></span>  
  
 <span data-ttu-id="d3c31-146">**Abrir el visor de perfil**</span><span class="sxs-lookup"><span data-stu-id="d3c31-146">**Open Profile Viewer**</span></span>  
 <span data-ttu-id="d3c31-147">Abre el Visor de perfil de datos.</span><span class="sxs-lookup"><span data-stu-id="d3c31-147">Opens the Data Profile Viewer.</span></span> <span data-ttu-id="d3c31-148">El Visor de perfil de datos independiente muestra el resultado del perfil de datos de la tarea Generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="d3c31-148">The stand-alone Data Profile Viewer displays data profile output from the Data Profiling task.</span></span> <span data-ttu-id="d3c31-149">El resultado del perfil de datos puede verse después de ejecutar la tarea Generación de perfiles de datos dentro del paquete [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] y de calcular los perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="d3c31-149">You can view the data profile output after you have run the Data Profiling task inside the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package and computed the data profiles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3c31-150">También puede abrir el Visor de perfil de datos si ejecuta el archivo DataProfileViewer.exe en la carpeta *\<drive>* :\Archivos de programa (x86) | Archivos de programa\Microsoft SQL Server\110\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="d3c31-150">You can also open the Data Profile Viewer by running the DataProfileViewer.exe in the folder, *\<drive>*:\Program Files (x86) | Program Files\Microsoft SQL Server\110\DTS\Binn.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c31-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3c31-151">See Also</span></span>  
 <span data-ttu-id="d3c31-152">[Formulario de perfil rápido de tabla única &#40;tarea de generación de perfiles de datos&#41;](single-table-quick-profile-form-data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="d3c31-152">[Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md) </span></span>  
 [<span data-ttu-id="d3c31-153">Editor de tareas de generación de perfiles de datos &#40;página Solicitudes de perfil&#41;</span><span class="sxs-lookup"><span data-stu-id="d3c31-153">Data Profiling Task Editor &#40;Profile Requests Page&#41;</span></span>](data-profiling-task-editor-profile-requests-page.md)  
  
  
