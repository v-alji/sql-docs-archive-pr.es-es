---
title: Administración de sesiones de eventos en el Explorador de objetos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 16849e38-d3fb-414d-8dcb-797b5ffce6ee
author: rothja
ms.author: jroth
ms.openlocfilehash: 1aa33a97137f63348898e6b1fcb7b19b2d218573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662929"
---
# <a name="manage-event-sessions-in-the-object-explorer"></a><span data-ttu-id="66a61-102">Administrar sesiones de eventos en el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="66a61-102">Manage Event Sessions in the Object Explorer</span></span>
  <span data-ttu-id="66a61-103">En este tema se describen las acciones que se pueden llevar a cabo en el **Explorador de objetos** que afectan a una sesión de eventos extendidos:</span><span class="sxs-lookup"><span data-stu-id="66a61-103">This topic discusses the actions you can take in **Object Explorer** that affect Extended Events:</span></span>  
  
-   <span data-ttu-id="66a61-104">Crear una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-104">Create an Extended Events Session</span></span>  
  
-   <span data-ttu-id="66a61-105">Iniciar o detener una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-105">Starting or Stopping an Extended Events Session</span></span>  
  
-   <span data-ttu-id="66a61-106">Exportar una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-106">Export an Extended Events Session</span></span>  
  
-   <span data-ttu-id="66a61-107">Importar una plantilla de sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-107">Import an Extended Events Session Template</span></span>  
  
-   <span data-ttu-id="66a61-108">Editar una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-108">Edit an Extended Events Session</span></span>  
  
-   <span data-ttu-id="66a61-109">Eliminar una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-109">Delete an Extended Events Session</span></span>  
  
## <a name="create-an-extended-events-session"></a><span data-ttu-id="66a61-110">Crear una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-110">Create an Extended Events Session</span></span>  
 <span data-ttu-id="66a61-111">Para obtener más información acerca de cómo crear una sesión de eventos extendidos, vea [Create an Extended Events Session](../../database-engine/create-an-extended-events-session.md).</span><span class="sxs-lookup"><span data-stu-id="66a61-111">For more information about creating an Extended Events session, see [Create an Extended Events Session](../../database-engine/create-an-extended-events-session.md).</span></span>  
  
## <a name="starting-or-stopping-an-extended-events-session"></a><span data-ttu-id="66a61-112">Iniciar o detener una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-112">Starting or Stopping an Extended Events Session</span></span>  
 <span data-ttu-id="66a61-113">Puede iniciar o detener una sesión de eventos extendidos mediante el **Editor de consultas** de mediante la `ALTER EVENT SESSION` instrucción o mediante el nodo **eventos extendidos** de **Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="66a61-113">You can start or stop an Extended Events session through the **Query Editor** using the `ALTER EVENT SESSION` statement, or by using the **Extended Events** node of **Object Explorer**.</span></span>  
  
 <span data-ttu-id="66a61-114">Cuando se detiene una sesión de eventos, la sesión ya no se muestra como una sesión activa en la vista de administración dinámica (DMV) sys.dm_xe_sessions.</span><span class="sxs-lookup"><span data-stu-id="66a61-114">When you stop an event session, the session is no longer listed as an active session in the sys.dm_xe_sessions dynamic management view (DMV).</span></span> <span data-ttu-id="66a61-115">Sin embargo, la definición de la sesión permanece intacta y se puede reiniciar la sesión.</span><span class="sxs-lookup"><span data-stu-id="66a61-115">However, the session definition remains intact, and you can restart the session.</span></span> <span data-ttu-id="66a61-116">Para quitar completamente la definición de una sesión, se debe eliminar la sesión.</span><span class="sxs-lookup"><span data-stu-id="66a61-116">To completely remove a session definition, you must delete the session.</span></span>  
  
 <span data-ttu-id="66a61-117">Para iniciar o detener una sesión de eventos extendidos, debe disponer del permiso ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="66a61-117">To start or stop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="66a61-118">Cuando se detiene una sesión que usa un destino en memoria, como los destinos de búfer en anillo, de creación de depósitos, de emparejamiento de eventos o de contador de eventos sincrónicos, se pierde toda la información almacenada en el búfer de la sesión (la columna target_data de la DMV sys.dm_xe_session_targets).</span><span class="sxs-lookup"><span data-stu-id="66a61-118">When you stop a session that uses an in-memory target, such as the ring buffer, bucketing, event pairing, or synchronous event counter targets, all the information stored in the session's buffer (the target_data column of the sys.dm_xe_session_targets DMV) will be lost.</span></span> <span data-ttu-id="66a61-119">Para obtener acceso a los datos de evento después de detener la sesión, debe guardar los datos antes de detener o configurar la sesión para que se utilice el destino de archivo.</span><span class="sxs-lookup"><span data-stu-id="66a61-119">To access event data after you stop the session, you should either save the data before you stop the session, or configure the session to use the file target.</span></span>  
  
### <a name="start-or-stop-an-extended-events-session-using-query-editor"></a><span data-ttu-id="66a61-120">Iniciar o detener una sesión de eventos extendidos mediante el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="66a61-120">Start or Stop an Extended Events Session Using Query Editor</span></span>  
 <span data-ttu-id="66a61-121">Para iniciar una sesión, emita las instrucciones siguientes, reemplazando *nombre_sesión* por el nombre de la sesión de eventos extendidos:</span><span class="sxs-lookup"><span data-stu-id="66a61-121">To start a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = START  
```  
  
 <span data-ttu-id="66a61-122">Para detener una sesión, emita las instrucciones siguientes, reemplazando *nombre_sesión* por el nombre de la sesión de eventos extendidos:</span><span class="sxs-lookup"><span data-stu-id="66a61-122">To stop a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = STOP  
```  
  
### <a name="start-or-stop-an-extended-events-session-in-object-explorer"></a><span data-ttu-id="66a61-123">Iniciar o detener una sesión de eventos extendidos en el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="66a61-123">Start or Stop an Extended Events Session in Object Explorer</span></span>  
 <span data-ttu-id="66a61-124">Para iniciar o detener una sesión de eventos extendidos en el **Explorador de objetos**, expanda los nodos **Administración**, **Eventos extendidos**y **Sesiones** y, a continuación, haga clic con el botón secundario en una sesión y en **Iniciar sesión** o **Detener sesión**.</span><span class="sxs-lookup"><span data-stu-id="66a61-124">To start or stop an Extended Events session in **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes and right click on a session and then click **Start Session** or **Stop Session**.</span></span>  
  
## <a name="export-an-extended-events-session-template"></a><span data-ttu-id="66a61-125">Exportar una plantilla de sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-125">Export an Extended Events Session Template</span></span>  
 <span data-ttu-id="66a61-126">Puede exportar una sesión de eventos extendidos con el **Explorador de objetos**y guardarlos en un archivo de plantilla .xml.</span><span class="sxs-lookup"><span data-stu-id="66a61-126">You can export an Extended Events session using **Object Explorer**, and save it as an .xml template file.</span></span> <span data-ttu-id="66a61-127">Por ejemplo, puede exportar una sesión y, a continuación, aplicar la plantilla a una nueva sesión de evento mediante el **Asistente para nueva sesión** o el cuadro de diálogo **Nueva sesión** .</span><span class="sxs-lookup"><span data-stu-id="66a61-127">For example, you may want to export a session and then apply the template to a new event session using the **New Session Wizard** or the **New Session** wizard.</span></span>  
  
 <span data-ttu-id="66a61-128">Al exportar una sesión, asegúrese de que guarda el archivo de plantilla en una ubicación que usa el sistema de archivos NTFS y que restringe el acceso a los usuarios que están autorizados para ver la información.</span><span class="sxs-lookup"><span data-stu-id="66a61-128">When you export a session, make sure that you save the template file to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="66a61-129">Para exportar una sesión de eventos extendidos en el **Explorador de objetos**:</span><span class="sxs-lookup"><span data-stu-id="66a61-129">To export an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="66a61-130">Expanda los nodos de **Administración**, **Eventos extendidos**y **Sesiones** .</span><span class="sxs-lookup"><span data-stu-id="66a61-130">Expand the **Management**, **Extended Events**, and then **Sessions** nodes</span></span>  
  
2.  <span data-ttu-id="66a61-131">Haga clic con el botón derecho en la sesión que quiere exportar y seleccione **Exportar sesión**.</span><span class="sxs-lookup"><span data-stu-id="66a61-131">Right-click the session that you want to export, and select **Export Session**.</span></span>  
  
3.  <span data-ttu-id="66a61-132">En el cuadro de diálogo **Guardar como** , seleccione una ubicación para guardar el archivo, escriba el nombre de archivo en el cuadro **Nombre de archivo** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="66a61-132">In the **Save As** dialog box, select a location to save the file, type the file name in the **File name** box, and then click **Save**.</span></span>  
  
     <span data-ttu-id="66a61-133">Si guarda el archivo en la ubicación predeterminada de la plantilla de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , la plantilla aparecerá en la lista desplegable de plantillas predefinidas cuando use el cuadro de diálogo **Asistente para nueva sesión** y **Nueva sesión** .</span><span class="sxs-lookup"><span data-stu-id="66a61-133">If you save the file to the default [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] template location, the template will appear in the dropdown list of predefined templates when you use the **New Session Wizard** and **New Session** dialog.</span></span>  
  
## <a name="import-an-extended-events-session-template"></a><span data-ttu-id="66a61-134">Importar una plantilla de sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-134">Import an Extended Events Session Template</span></span>  
 <span data-ttu-id="66a61-135">Mediante el **Explorador de objetos**, puede importar una plantilla para una sesión de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="66a61-135">Using **Object Explorer**, you can import a template for an Extended Events session.</span></span> <span data-ttu-id="66a61-136">Por ejemplo, puede que desee realizar esta operación para crear una sesión de una plantilla que se exportó desde otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66a61-136">For example, you may want to do this to create a session from a template that was exported from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="66a61-137">Para importar una sesión de eventos extendidos, debe tener los permisos necesarios para `ALTER ANY EVENT SESSION`.</span><span class="sxs-lookup"><span data-stu-id="66a61-137">To import an Extended Events session, you must have the necessary `ALTER ANY EVENT SESSION` permissions.</span></span>  
  
 <span data-ttu-id="66a61-138">Antes de importar un archivo de plantilla, asegúrese de que el archivo procede de un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="66a61-138">Before you import a template file, make sure that the file is from a trusted source.</span></span> <span data-ttu-id="66a61-139">Los archivos de plantilla deben guardarse en una ubicación que use el sistema de archivos NTFS y donde el acceso está restringido a los usuarios que estén autorizados para ver la información.</span><span class="sxs-lookup"><span data-stu-id="66a61-139">Template files should be saved to a location that uses the NTFS file system and where access is restricted to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="66a61-140">Para importar una sesión de eventos extendidos:</span><span class="sxs-lookup"><span data-stu-id="66a61-140">To import an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="66a61-141">En el **Explorador de objetos**, expanda los nodos **Administración**y después **Eventos extendidos** .</span><span class="sxs-lookup"><span data-stu-id="66a61-141">In **Object Explorer**, expand the **Management**, and then **Extended Events** nodes.</span></span>  
  
2.  <span data-ttu-id="66a61-142">Haga clic con el botón derecho en **Sesiones** y seleccione **Nueva sesión**.</span><span class="sxs-lookup"><span data-stu-id="66a61-142">Right-click **Sessions** and select **New Session**.</span></span>  
  
3.  <span data-ttu-id="66a61-143">Especifica un nombre para la sesión.</span><span class="sxs-lookup"><span data-stu-id="66a61-143">Specify a name for the session.</span></span>  
  
4.  <span data-ttu-id="66a61-144">Expanda la lista desplegable **Plantilla** .</span><span class="sxs-lookup"><span data-stu-id="66a61-144">Expand the **Template** drop down box.</span></span>  
  
5.  <span data-ttu-id="66a61-145">Haga clic en **\<File From ...>Abrir** y busque la sesión (archivo XML) que quiera importar.</span><span class="sxs-lookup"><span data-stu-id="66a61-145">Click **\<File From ...>Open** and browse for the session (XML file) you want to import.</span></span>  
  
 <span data-ttu-id="66a61-146">La sesión aparecen bajo el nodo **Sesiones** .</span><span class="sxs-lookup"><span data-stu-id="66a61-146">The session appears under the **Sessions** node.</span></span> <span data-ttu-id="66a61-147">De forma predeterminada, no se inicia la sesión.</span><span class="sxs-lookup"><span data-stu-id="66a61-147">By default, the session is not started.</span></span>  
  
## <a name="edit-an-extended-events-session"></a><span data-ttu-id="66a61-148">Editar una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-148">Edit an Extended Events Session</span></span>  
 <span data-ttu-id="66a61-149">Puede modificar una sesión de eventos extendidos en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="66a61-149">You can edit an Extended Events session in Object Explorer.</span></span>  
  
 <span data-ttu-id="66a61-150">Para editar una sesión de eventos extendidos:</span><span class="sxs-lookup"><span data-stu-id="66a61-150">To edit an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="66a61-151">En el **Explorador de objetos**, expanda los nodos **Administración**, **Eventos extendidos**y **Sesiones** .</span><span class="sxs-lookup"><span data-stu-id="66a61-151">In **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="66a61-152">Haga clic con el botón derecho en una sesión y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="66a61-152">Right-click a session and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="66a61-153">En la sección **Seleccionar una página** , seleccione la página o las páginas que desee editar.</span><span class="sxs-lookup"><span data-stu-id="66a61-153">In the **Select a page** section, select the page or pages you want to edit.</span></span>  
  
4.  <span data-ttu-id="66a61-154">Después de finalizar la revisión de la sesión de evento, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="66a61-154">After you finish revising the event session, click **OK**.</span></span>  
  
## <a name="script-an-event-session-definition-using-tsql"></a><span data-ttu-id="66a61-155">Crear un script para una definición de la sesión de eventos mediante [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66a61-155">Script an Event Session Definition Using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
 <span data-ttu-id="66a61-156">Tanto el Asistente para nueva sesión como el cuadro de diálogo Nueva sesión tienen una opción de script que genera [!INCLUDE[tsql](../../includes/tsql-md.md)] para definir la sesión de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="66a61-156">Both the New Session Wizard and the New Session dialog have a Script option that generates the [!INCLUDE[tsql](../../includes/tsql-md.md)] that defines the Extended Events session.</span></span>  
  
 <span data-ttu-id="66a61-157">Puede tener acceso a [!INCLUDE[tsql](../../includes/tsql-md.md)] para una sesión de eventos extendidos existente haciendo clic con el botón secundario en el nombre de la sesión, seleccionando **Incluir sesión como**y después seleccionando **Crear para**.</span><span class="sxs-lookup"><span data-stu-id="66a61-157">You can access the [!INCLUDE[tsql](../../includes/tsql-md.md)] for an existing Extended Events session by right clicking the session name, selecting **Script Session as**, and then selecting **Create to**.</span></span>  
  
## <a name="delete-an-extended-events-session"></a><span data-ttu-id="66a61-158">Eliminar una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="66a61-158">Delete an Extended Events Session</span></span>  
 <span data-ttu-id="66a61-159">Puede eliminar una sesión de eventos extendidos:</span><span class="sxs-lookup"><span data-stu-id="66a61-159">You can delete an Extended Events session:</span></span>  
  
-   <span data-ttu-id="66a61-160">En el Editor de consultas mediante `DROP EVENT SESSION`.</span><span class="sxs-lookup"><span data-stu-id="66a61-160">In Query Editor using `DROP EVENT SESSION`.</span></span>  
  
-   <span data-ttu-id="66a61-161">En el **Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="66a61-161">In **Object Explorer**.</span></span>  
  
 <span data-ttu-id="66a61-162">Cuando se elimina una sesión de eventos, se quita toda la información de configuración y la definición de la sesión ya no aparece en la vista de catálogo sys.server_event_sessions.</span><span class="sxs-lookup"><span data-stu-id="66a61-162">When you delete an event session, all configuration information is removed and the session definition no longer appears in the sys.server_event_sessions catalog view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66a61-163">system_health y AlwaysOn_health se incluyen con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; no los elimine.</span><span class="sxs-lookup"><span data-stu-id="66a61-163">system_health and AlwaysOn_health are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; do not delete them.</span></span> <span data-ttu-id="66a61-164">system_health está habilitado de forma predeterminada (para obtener más información, vea [Usar la sesión system_health](use-the-ssms-xe-profiler.md)).</span><span class="sxs-lookup"><span data-stu-id="66a61-164">system_health is enabled by default (for more information, see [Use the system_health Session](use-the-ssms-xe-profiler.md)).</span></span> <span data-ttu-id="66a61-165">AlwaysOn_health está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="66a61-165">AlwaysOn_health is off by default.</span></span> <span data-ttu-id="66a61-166">Estas sesiones recopilan los datos que pueden ser útiles para diagnosticar problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="66a61-166">These sessions collect data that can be useful for diagnosing performance issues.</span></span>  
  
 <span data-ttu-id="66a61-167">Para eliminar una sesión de eventos extendidos, debe disponer del permiso ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="66a61-167">To delete an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="66a61-168">Para eliminar una sesión de eventos extendidos en el **Explorador de objetos**:</span><span class="sxs-lookup"><span data-stu-id="66a61-168">To delete an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="66a61-169">Expanda los nodos de **Administración**, **Eventos extendidos**y **Sesiones** .</span><span class="sxs-lookup"><span data-stu-id="66a61-169">Expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="66a61-170">Haga clic con el botón derecho en la sesión y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="66a61-170">Right-click a session and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="66a61-171">En el cuadro de diálogo **Eliminar objeto** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="66a61-171">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="66a61-172">Después de finalizar la revisión de la sesión de evento, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="66a61-172">After you finish revising the event session, click **OK**.</span></span>  
  
 <span data-ttu-id="66a61-173">Para eliminar una sesión de eventos extendidos en el **Editor de consultas**, emita las instrucciones siguientes, reemplazando *nombre_sesión* por el nombre de la sesión de eventos extendidos que quiere eliminar:</span><span class="sxs-lookup"><span data-stu-id="66a61-173">To delete an Extended Events session in the **Query Editor**, Issue the following statements, replacing *session_name* with the name of the Extended Events session that you want to delete:</span></span>  
  
```  
DROP EVENT SESSION [session_name]  
ON SERVER  
```  
  
  
