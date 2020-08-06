---
title: Crear una sesión de eventos extendidos con el asistente (Explorador de objetos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- Sql12.ssms.XeWizard.Summary.f1
- Sql12.ssms.XeWizard.SetSessionProperties.f1
- Sql12.ssms.XeWizard.CaptureAddFields.f1
- Sql12.ssms.XeWizard.SelectEvents.f1
- Sql12.ssms.XeWizard.SpecifySessionTargets.f1
- Sql12.ssms.XeWizard.Welcome.f1
- sql12.ssms.XeWizard.Welcome.f1
- Sql12.ssms.XeWizard.ChooseTemplate.f1
- Sql12.ssms.XeWizard.SetSessionEventFilters.f1
- Sql12.ssms.XeWizard.Results.f1
helpviewer_keywords:
- Sql11.ssms.XeWizard.CaptureAddFields.f1
- Sql11.ssms.XeWizard.SetSessionEventFilters.f1
- Sql11.ssms.XeWizard.SpecifySessionTargets.f1
- Sql11.ssms.XeWizard.Results.f1
- Sql11.ssms.XeWizard.ChooseTemplate.f1
- Sql11.ssms.XeWizard.SetSessionProperties.f1
- Sql11.ssms.XeWizard.Welcome.f1
- Sql11.ssms.XeWizard.Summary.f1
- Sql11.ssms.XeWizard.SelectEvents.f1
ms.assetid: 80c0456f-17c0-41d8-b2aa-502a2f3bb6de
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfc9141b0b99d5b06fc73044b8f4fae623922b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673249"
---
# <a name="create-an-extended-events-session-using-the-wizard-object-explorer"></a><span data-ttu-id="cded2-102">Crear una sesión de Extended Events utilizando el asistente (Explorador de objetos)</span><span class="sxs-lookup"><span data-stu-id="cded2-102">Create an Extended Events Session Using the Wizard (Object Explorer)</span></span>
  <span data-ttu-id="cded2-103">Para ayudarle a seleccionar y capturar eventos en el servidor, los eventos extendidos incluyen un Asistente para nueva sesión que le guía a través de los pasos necesarios para crear una sesión de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="cded2-103">To help you select and capture events on your server, Extended Events includes a New Session Wizard that guides you through the steps to create an Extended Events session.</span></span> <span data-ttu-id="cded2-104">El Asistente para nueva sesión expone la mayor parte de la funcionalidad de Extended Events.</span><span class="sxs-lookup"><span data-stu-id="cded2-104">The New Session Wizard exposes most of the Extended Events functionality.</span></span> <span data-ttu-id="cded2-105">El [cuadro de diálogo Nueva sesión](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) también permite definir una sesión de Eventos extendidos que capture, presente y analice los datos.</span><span class="sxs-lookup"><span data-stu-id="cded2-105">The [New Session dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) also lets you define an Extended Events session that captures, displays, and analyzes your data.</span></span> <span data-ttu-id="cded2-106">El cuadro de diálogo Nueva sesión expone toda la funcionalidad de Extended Events.</span><span class="sxs-lookup"><span data-stu-id="cded2-106">The New Session dialog exposes all Extended Events functionality.</span></span>  
  
### <a name="to-open-the-new-session-wizard"></a><span data-ttu-id="cded2-107">Para abrir el Asistente para nueva sesión</span><span class="sxs-lookup"><span data-stu-id="cded2-107">To open the New Session Wizard</span></span>  
  
1.  <span data-ttu-id="cded2-108">En el Explorador de objetos, expanda el nodo **Administración** y, a continuación, expanda **Eventos extendidos**.</span><span class="sxs-lookup"><span data-stu-id="cded2-108">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="cded2-109">Haga clic con el botón derecho en **Sesiones** y, después, haga clic en **Asistente para nueva sesión**.</span><span class="sxs-lookup"><span data-stu-id="cded2-109">Right-click **Sessions**, and then click **New Session Wizard**.</span></span>  
  
### <a name="use-the-following-new-session-wizard-pages-to-create-an-event-session"></a><span data-ttu-id="cded2-110">Utilizar las páginas siguientes del Asistente para nueva sesión para crear una sesión de eventos</span><span class="sxs-lookup"><span data-stu-id="cded2-110">Use the following New Session Wizard pages to create an event session</span></span>  
  
-   [<span data-ttu-id="cded2-111">Introducción</span><span class="sxs-lookup"><span data-stu-id="cded2-111">Introduction</span></span>](#BKMK_Welcome)  
  
-   [<span data-ttu-id="cded2-112">Establecer propiedades de la sesión</span><span class="sxs-lookup"><span data-stu-id="cded2-112">Set Session Properties</span></span>](#BKMK_SetSessionProperties)  
  
-   [<span data-ttu-id="cded2-113">Elegir plantilla</span><span class="sxs-lookup"><span data-stu-id="cded2-113">Choose Template</span></span>](#BKMK_ChooseTemplate)  
  
-   [<span data-ttu-id="cded2-114">Seleccionar eventos para capturar</span><span class="sxs-lookup"><span data-stu-id="cded2-114">Select Events to Capture</span></span>](#BKMK_SelectEventsToCapture)  
  
-   [<span data-ttu-id="cded2-115">Capturar campos globales</span><span class="sxs-lookup"><span data-stu-id="cded2-115">Capture Global Fields</span></span>](#BKMK_CaptureGlobalFields)  
  
-   [<span data-ttu-id="cded2-116">Establecer filtros de eventos de la sesión</span><span class="sxs-lookup"><span data-stu-id="cded2-116">Set Session Event Filters</span></span>](#BKMK_SetSessionEventFilters)  
  
-   [<span data-ttu-id="cded2-117">Especificar almacenamiento de datos de la sesión</span><span class="sxs-lookup"><span data-stu-id="cded2-117">Specify Session Data Storage</span></span>](#BKMK_SpecifySessionDataOutput)  
  
-   [<span data-ttu-id="cded2-118">Resumen</span><span class="sxs-lookup"><span data-stu-id="cded2-118">Summary</span></span>](#BKMK_Summary)  
  
-   [<span data-ttu-id="cded2-119">Crear sesión de eventos</span><span class="sxs-lookup"><span data-stu-id="cded2-119">Create Event Session</span></span>](#BKMK_CreateEventSession)  
  
##  <a name="introduction"></a><a name="BKMK_Welcome"></a><span data-ttu-id="cded2-120">Aparición</span><span class="sxs-lookup"><span data-stu-id="cded2-120">Introduction</span></span>  
 <span data-ttu-id="cded2-121">En la página **Introducción** realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cded2-121">On the **Introduction** page, do the following:</span></span>  
  
-   <span data-ttu-id="cded2-122">En la página **Introducción** del Asistente para nueva sesión, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cded2-122">On the **Introduction** page of the New Session Wizard, click **Next**.</span></span>  
  
     <span data-ttu-id="cded2-123">Active la casilla **No volver a mostrar esta página** si va a usar el asistente más de una vez y no quiere leer la introducción cada vez que se inicie el asistente.</span><span class="sxs-lookup"><span data-stu-id="cded2-123">Select the **Do not show this page again** check box if you will be using the wizard more than once and do not want to read the introduction each time the wizard is launched.</span></span>  
  
##  <a name="set-session-properties"></a><a name="BKMK_SetSessionProperties"></a><span data-ttu-id="cded2-124">Establecer propiedades de sesión</span><span class="sxs-lookup"><span data-stu-id="cded2-124">Set Session Properties</span></span>  
 <span data-ttu-id="cded2-125">En la página **Establecer propiedades de la sesión** realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cded2-125">On the **Set Session Properties** page, do the following:</span></span>  
  
-   <span data-ttu-id="cded2-126">En el cuadro **Nombre de sesión** , escriba un nombre descriptivo para la sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="cded2-126">In the **Session name** box, type a meaningful name for the event session.</span></span>  
  
     <span data-ttu-id="cded2-127">Si desea que la sesión se inicie al iniciarse el servidor, active la casilla **Iniciar la sesión de eventos al iniciar el servidor** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cded2-127">If you want to start the session when you start the server, select the **Start the event session at server startup** check box, and then click **Next**.</span></span>  
  
##  <a name="choose-template"></a><a name="BKMK_ChooseTemplate"></a><span data-ttu-id="cded2-128">Elegir plantilla</span><span class="sxs-lookup"><span data-stu-id="cded2-128">Choose Template</span></span>  
 <span data-ttu-id="cded2-129">En la página **Elegir plantilla** realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cded2-129">On the **Choose Template** page, do the following:</span></span>  
  
-   <span data-ttu-id="cded2-130">Seleccione la opción **Usar esta plantilla de sesión de eventos** para seleccionar entre un conjunto de plantillas preconfiguradas diseñadas para solucionar problemas comunes.</span><span class="sxs-lookup"><span data-stu-id="cded2-130">Select the **Use this event session template** option to select from a set of pre-configured templates designed for common problems.</span></span> <span data-ttu-id="cded2-131">Seleccione la plantilla que quiera usar en la lista desplegable y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cded2-131">Select the template you want to use from the drop-down list, and then click **Next**.</span></span>  
  
     <span data-ttu-id="cded2-132">O</span><span class="sxs-lookup"><span data-stu-id="cded2-132">-OR-</span></span>  
  
-   <span data-ttu-id="cded2-133">Seleccione la opción **No usar una plantilla** si no quiere usar una plantilla preconfigurada y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cded2-133">Select the **Do not use a template** option if you do not want to use any pre-configured template, and then click **Next**.</span></span>  
  
##  <a name="select-events-to-capture"></a><a name="BKMK_SelectEventsToCapture"></a><span data-ttu-id="cded2-134">Seleccionar eventos para capturar</span><span class="sxs-lookup"><span data-stu-id="cded2-134">Select Events to Capture</span></span>  
 <span data-ttu-id="cded2-135">En la página **Seleccionar eventos para capturar** realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cded2-135">On the **Select Events to Capture** page, do the following:</span></span>  
  
1.  <span data-ttu-id="cded2-136">Seleccione los eventos que desee capturar de la **Biblioteca de eventos**y, a continuación, haga clic en la flecha derecha.</span><span class="sxs-lookup"><span data-stu-id="cded2-136">Select the events you want to capture from the **Event library**, and then click the right arrow.</span></span> <span data-ttu-id="cded2-137">Puede seleccionar varios eventos en la biblioteca de eventos con Mayúsculas+Clic o Ctrl+Clic.</span><span class="sxs-lookup"><span data-stu-id="cded2-137">You can select multiple events in the Event Library by using either Shift+Click or Ctrl+Click.</span></span>  
  
     <span data-ttu-id="cded2-138">Puede seleccionar cómo desea que se busquen los eventos que desea capturar del cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="cded2-138">You can select how you want to search for the events you want to capture from the drop-down list box.</span></span> <span data-ttu-id="cded2-139">Por ejemplo, puede buscar nombres de evento o nombres de evento con sus descripciones.</span><span class="sxs-lookup"><span data-stu-id="cded2-139">For example, you can search for event names or event names and their descriptions.</span></span> <span data-ttu-id="cded2-140">Puede buscar cualquier palabra en la tabla especificando el texto que desea buscar en el cuadro **Biblioteca de eventos** .</span><span class="sxs-lookup"><span data-stu-id="cded2-140">You can search for any word in the table by entering the text you want to search for in the **Event library** box.</span></span> <span data-ttu-id="cded2-141">Por ejemplo, si desea buscar el evento **lock_acquired** , puede especificar **Lock**o **Lock acquire**.</span><span class="sxs-lookup"><span data-stu-id="cded2-141">For example, if you want to find the **lock_acquired** event, you can enter **lock**, or **lock acquire**.</span></span>  
  
     <span data-ttu-id="cded2-142">Los eventos que seleccione aparecerán en el cuadro **Eventos seleccionados** .</span><span class="sxs-lookup"><span data-stu-id="cded2-142">The events you select appear in the **Selected events** box.</span></span> <span data-ttu-id="cded2-143">Para quitar eventos del cuadro **Eventos seleccionados** , haga clic en la flecha izquierda.</span><span class="sxs-lookup"><span data-stu-id="cded2-143">To remove events from the **Selected events** box, click the left arrow.</span></span>  
  
2.  <span data-ttu-id="cded2-144">Después de seleccionar los eventos que desee capturar, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cded2-144">After you select the events you want to capture, click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cded2-145">Los eventos del canal **Depurar** permanecen ocultos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cded2-145">Events from the **Debug** channel are hidden by default.</span></span> <span data-ttu-id="cded2-146">Para mostrar eventos de depuración, seleccione **Depurar** en la lista desplegable **Canal** .</span><span class="sxs-lookup"><span data-stu-id="cded2-146">To display debug events, select **Debug** from the **Channel** drop-down list.</span></span>  
  
##  <a name="capture-global-fields"></a><a name="BKMK_CaptureGlobalFields"></a><span data-ttu-id="cded2-147">Capturar campos globales</span><span class="sxs-lookup"><span data-stu-id="cded2-147">Capture Global Fields</span></span>  
 <span data-ttu-id="cded2-148">Los campos globales (también denominados acciones) se utilizan para asociar una o varias acciones para los eventos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="cded2-148">You use global fields (also referred to as actions) to associate single or multiple actions for your selected events.</span></span> <span data-ttu-id="cded2-149">Si se selecciona una plantilla en la página **Elegir plantilla** , todos los campos que están definidas en la plantilla se muestran en esta página.</span><span class="sxs-lookup"><span data-stu-id="cded2-149">If you selected a template on the **Choose Template** page, all of the global fields that are defined in the template are displayed on this page.</span></span>  
  
 <span data-ttu-id="cded2-150">En la página **Capturar campos globales** realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cded2-150">On the **Capture Global Fields** page, do the following:</span></span>  
  
-   <span data-ttu-id="cded2-151">Seleccione los campos que desee capturar para la sesión de eventos y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cded2-151">Select the global fields that you want to capture for the event session, and then click **Next**.</span></span>  
  
     <span data-ttu-id="cded2-152">Puede quitar o agregar campos globales activando o desactivando la casilla situada junto al campo global.</span><span class="sxs-lookup"><span data-stu-id="cded2-152">You can remove or add global fields by selecting or clearing the check box next to the global field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cded2-153">Las acciones seleccionadas se ordenan por **Nombre** permitiéndole ver las acciones asociadas en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="cded2-153">The selected actions are sorted by **Name** enabling you to view the associated actions in alphabetical order.</span></span> <span data-ttu-id="cded2-154">Puede ordenar por descripción o por estado habilitado/deshabilitado haciendo clic en el encabezado de columna situado junto al nombre de campo.</span><span class="sxs-lookup"><span data-stu-id="cded2-154">You can sort by description or by the enable/disable status by clicking the column heading next to the field name.</span></span>  
  
##  <a name="set-session-event-filters"></a><a name="BKMK_SetSessionEventFilters"></a><span data-ttu-id="cded2-155">Establecer filtros de eventos de sesión</span><span class="sxs-lookup"><span data-stu-id="cded2-155">Set Session Event Filters</span></span>  
 <span data-ttu-id="cded2-156">Puede aplicar filtros (también denominados predicados) para limitar los eventos que desee capturar.</span><span class="sxs-lookup"><span data-stu-id="cded2-156">You can apply filters (also called predicates) to limit the events that you want to capture.</span></span> <span data-ttu-id="cded2-157">En la página **Establecer filtros de eventos de la sesión** realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cded2-157">On the **Set Session Event Filters** page, do the following:</span></span>  
  
1.  <span data-ttu-id="cded2-158">Si no usa una plantilla preconfigurada, cree los criterios de filtro y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cded2-158">If you are not using a pre-configured template, create your filter criteria, and then click **Next**.</span></span>  
  
     <span data-ttu-id="cded2-159">Si usa una plantilla preconfigurada, en la sección **Filtros de plantilla (de solo lectura)** , el Asistente para nueva sesión enumera los filtros ya creados de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="cded2-159">If you are using a pre-configured template, in the **Filters from template (read-only)** section, the New Session Wizard lists filters already created from the template.</span></span>  
  
2.  <span data-ttu-id="cded2-160">En la sección **Filtros adicionales** puede configurar filtros adicionales para la sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="cded2-160">In the **Additional filters** section, you can configure additional filters for the event session.</span></span>  
  
     <span data-ttu-id="cded2-161">Los filtros que configure se aplican a todos los eventos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="cded2-161">The filters you configure apply to all selected events.</span></span> <span data-ttu-id="cded2-162">El Asistente para nueva sesión no admite la configuración de filtros para cada evento.</span><span class="sxs-lookup"><span data-stu-id="cded2-162">The New Session Wizard does not support configuring filters for each event.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cded2-163">Cuando configure una cláusula de grupo para el filtro, se quitarán los paréntesis redundantes del filtro después de guardar el resultado.</span><span class="sxs-lookup"><span data-stu-id="cded2-163">When you configure a group clause for your filter, redundant parentheses are removed from the filter after the result is saved.</span></span> <span data-ttu-id="cded2-164">Por ejemplo, si crea un filtro que agrupe **Cláusula 1** y **Cláusula 2**, aparecerán paréntesis alrededor de las cláusulas.</span><span class="sxs-lookup"><span data-stu-id="cded2-164">For example, if you create a filter grouping **Clause 1** and **Clause 2**, parentheses will appear around the clauses.</span></span> <span data-ttu-id="cded2-165">Después de guardar el filtro, se quitan los paréntesis redundantes.</span><span class="sxs-lookup"><span data-stu-id="cded2-165">After you save the filter, the redundant parentheses are removed.</span></span> <span data-ttu-id="cded2-166">La eliminación de los paréntesis no afecta a la lógica del filtro.</span><span class="sxs-lookup"><span data-stu-id="cded2-166">The removal of the parentheses does not affect the filter logic.</span></span>  
  
##  <a name="specify-session-data-storage"></a><a name="BKMK_SpecifySessionDataOutput"></a><span data-ttu-id="cded2-167">Especificar el almacenamiento de datos de sesión</span><span class="sxs-lookup"><span data-stu-id="cded2-167">Specify Session Data Storage</span></span>  
 <span data-ttu-id="cded2-168">Utilice la página **Especificar almacenamiento de datos de la sesión** para especificar cómo desea recopilar los datos para el análisis.</span><span class="sxs-lookup"><span data-stu-id="cded2-168">You use the **Specify Session Data Storage** page to specify how you want to collect your data for analysis.</span></span> <span data-ttu-id="cded2-169">SQL Server Extended Events utiliza destinos para la salida de datos.</span><span class="sxs-lookup"><span data-stu-id="cded2-169">SQL Server Extended Events uses targets for data output.</span></span> <span data-ttu-id="cded2-170">Los destinos almacenan los datos de evento y pueden realizar acciones como escribir en un archivo y agregar datos de evento.</span><span class="sxs-lookup"><span data-stu-id="cded2-170">Targets store event data and can perform actions such as writing to a file and aggregating event data.</span></span> <span data-ttu-id="cded2-171">Decida cómo desea recopilar los datos para el análisis y, en la página **Especificar almacenamiento de datos de la sesión**, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cded2-171">Decide how you want to collect your data for analysis, and on the **Specify Session Data Storage** page, do the following:</span></span>  
  
1.  <span data-ttu-id="cded2-172">Para los conjuntos de datos grandes y para la creación de registros históricos, active la casilla **Guardar los datos en un archivo para su posterior análisis** y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cded2-172">For large data sets and creating historical records, select the **Save data to a file for later analysis** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="cded2-173">En el cuadro **Nombre de archivo en el servidor** , escriba la ruta de acceso y el nombre de archivo o haga clic en **Examinar** para especificar el directorio de archivos del servidor donde desea guardar los datos.</span><span class="sxs-lookup"><span data-stu-id="cded2-173">In the **File name on server** box, enter the path and file name, or click **Browse** to specify the file directory on the server where you want to save the data.</span></span>  
  
    2.  <span data-ttu-id="cded2-174">En el cuadro **Tamaño máximo del archivo** , especifique el tamaño máximo de archivo que se ha de utilizar para el destino de archivos.</span><span class="sxs-lookup"><span data-stu-id="cded2-174">In the **Maximum file size** box, specify the maximum file size to be used for the file target.</span></span> <span data-ttu-id="cded2-175">Si no especifica el tamaño máximo de archivo, el archivo crecerá hasta llenar el disco.</span><span class="sxs-lookup"><span data-stu-id="cded2-175">If you do not specify the maximum file size, the file will grow until the disk is full.</span></span> <span data-ttu-id="cded2-176">El tamaño de archivo predeterminado es 1 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="cded2-176">The default file size is 1 gigabyte (GB).</span></span>  
  
    3.  <span data-ttu-id="cded2-177">Active la casilla **Habilitar sustitución incremental de archivos** para habilitar la sustitución incremental de archivos para el destino de archivos.</span><span class="sxs-lookup"><span data-stu-id="cded2-177">Select the **Enable file rollover** check box to enable file rollover for the file target.</span></span>  
  
    4.  <span data-ttu-id="cded2-178">En el cuadro **Número máximo de archivos** , especifique el número máximo de archivos que desea conservar en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="cded2-178">In the **Maximum number of files** box, specify the maximum number of files you want to retain in the file system.</span></span>  
  
2.  <span data-ttu-id="cded2-179">Para recopilar datos recientes, active la casilla **Trabajar solo con los datos más recientes (destino ring_buffer)** y, después, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cded2-179">For collecting recent data, select the **Work with only the most recent data (ring buffer target)** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="cded2-180">En el cuadro **Número de eventos para mantener** , escriba o seleccione el número de eventos que desea mantener utilizando las flechas arriba y abajo.</span><span class="sxs-lookup"><span data-stu-id="cded2-180">In the **Number of events to keep** box, enter or select the number of events you want to keep by using the up and down arrows.</span></span>  
  
    2.  <span data-ttu-id="cded2-181">En el cuadro **Tamaño máximo del búfer de memoria** , especifique la cantidad máxima de memoria de búfer que desea usar.</span><span class="sxs-lookup"><span data-stu-id="cded2-181">In the **Maximum buffer memory size** box, specify the maximum amount of buffer memory to use.</span></span> <span data-ttu-id="cded2-182">Los eventos existentes se quitan al alcanzar este valor.</span><span class="sxs-lookup"><span data-stu-id="cded2-182">The existing events are dropped when this value is reached.</span></span>  
  
    3.  <span data-ttu-id="cded2-183">Si quiere conservar un número específico de eventos de cada tipo en el búfer, active la casilla **Mantener un número especificado de eventos (por tipo) cuando el búfer esté lleno** .</span><span class="sxs-lookup"><span data-stu-id="cded2-183">If you want to keep a specific number of events of each type in the buffer, select the **Keep a specified number of events (per type) when the buffer is full** check box.</span></span>  
  
    4.  <span data-ttu-id="cded2-184">En el cuadro **Número de eventos para mantener (por tipo)** , escriba o seleccione el número de eventos (por tipo) que quiere mantener al usar las flechas arriba y abajo.</span><span class="sxs-lookup"><span data-stu-id="cded2-184">In the **Number of events to keep (per type)** box, enter or select the number of events (per type) that you want to keep by using the up and down arrows.</span></span>  
  
##  <a name="summary"></a><a name="BKMK_Summary"></a> <span data-ttu-id="cded2-185">Resumen</span><span class="sxs-lookup"><span data-stu-id="cded2-185">Summary</span></span>  
 <span data-ttu-id="cded2-186">En la página **Resumen** realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cded2-186">On the **Summary** page, do the following:</span></span>  
  
1.  <span data-ttu-id="cded2-187">Asegúrese de que las selecciones sean correctas.</span><span class="sxs-lookup"><span data-stu-id="cded2-187">Make sure that your selections are correct.</span></span> <span data-ttu-id="cded2-188">Expanda los nodos de la sesión de eventos para comprobar que todas las selecciones se incluirán en la sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="cded2-188">Expand the event session nodes to verify that all of your selections will be included in the event session.</span></span>  
  
2.  <span data-ttu-id="cded2-189">Haga clic en **Script** para exportar el script de creación de la sesión a una nueva ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="cded2-189">Click **Script** to export the session creation script to a new Query Editor window.</span></span>  
  
3.  <span data-ttu-id="cded2-190">Haga clic en **Finalizar** para crear la sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="cded2-190">Click **Finish** to create the event session.</span></span>  
  
##  <a name="create-event-session"></a><a name="BKMK_CreateEventSession"></a><span data-ttu-id="cded2-191">Crear sesión de eventos</span><span class="sxs-lookup"><span data-stu-id="cded2-191">Create Event Session</span></span>  
 <span data-ttu-id="cded2-192">En la página **Crear sesión de eventos** , una vez creada correctamente la sesión de eventos, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cded2-192">On the **Create Event Session** page, after your event session has been successfully created, do the following:</span></span>  
  
1.  <span data-ttu-id="cded2-193">Haga clic en **Iniciar la sesión de eventos inmediatamente después de crear la sesión** para iniciar la sesión después de cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="cded2-193">Click **Start the event session immediately after session creation** to start the session after you close the wizard.</span></span> <span data-ttu-id="cded2-194">Debe iniciar la sesión de eventos inmediatamente después de crear la sesión para poder observar datos en directo.</span><span class="sxs-lookup"><span data-stu-id="cded2-194">You must start the event session immediately after you create the session to be able to watch live data.</span></span>  
  
2.  <span data-ttu-id="cded2-195">Haga clic en **Observar datos en directo en la pantalla mientras se capturan** para ver los datos en directo de la sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="cded2-195">Click **Watch live data on screen as it is captured** to view live data for your event session.</span></span> <span data-ttu-id="cded2-196">Los datos en directo iniciarán la presentación del seguimiento inmediatamente después de crearse la sesión.</span><span class="sxs-lookup"><span data-stu-id="cded2-196">The live data will start displaying tracing immediately after the session is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cded2-197">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cded2-197">See Also</span></span>  
 [<span data-ttu-id="cded2-198">Crear una sesión de eventos extendidos utilizando el cuadro de diálogo Nueva sesión</span><span class="sxs-lookup"><span data-stu-id="cded2-198">Create an Extended Events Session Using the New Session Dialog</span></span>](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md)  
  
  
