---
title: 'Opciones (editor de texto: pestaña Editor y página barra de estado) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.editorcontextsettings
- VS.ToolsOptionsPages.Text_Editor.EditorTabAndStatusBar
ms.assetid: e4815678-7885-4631-878f-c6a2b857ee05
author: rothja
ms.author: jroth
ms.openlocfilehash: 920b7d48b5f7a2472a521af21c8217b1adba486a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676168"
---
# <a name="options-text-editor-editor-tab-and-status-bar-page"></a><span data-ttu-id="1f661-102">Opciones (Editor de texto: pestaña Editor y página de la barra de estado)</span><span class="sxs-lookup"><span data-stu-id="1f661-102">Options (Text Editor: Editor Tab and Status Bar Page)</span></span>
  <span data-ttu-id="1f661-103">La **página Barra de estado y pestaña de editor** permite personalizar la información mostrada por los editores de consultas de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f661-103">The **Editor Tab and Status Bar Page** lets you customize the information displayed by the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Query Editors.</span></span> <span data-ttu-id="1f661-104">Puede especificar el nivel de información que se muestra en la pestaña y en la barra de estado de la ventana del editor de consultas y si la barra de estado debe aparecer en la parte superior o inferior de la ventana del editor.</span><span class="sxs-lookup"><span data-stu-id="1f661-104">You can specify the level of information displayed in the tab and status bar of the Query Editor window, and whether the status bar appears at the top or bottom of the editor window.</span></span>  
  
## <a name="option-settings-by-editor"></a><span data-ttu-id="1f661-105">Configuración de las opciones de editor</span><span class="sxs-lookup"><span data-stu-id="1f661-105">Option Settings by Editor</span></span>  
 <span data-ttu-id="1f661-106">La pestaña del editor y la barra de estado están disponibles en todos los editores de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , pero tienen distintos niveles de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="1f661-106">The editor tab and the status bar are available in all of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, but have different levels of functionality.</span></span>  
  
 <span data-ttu-id="1f661-107">El editor de consultas del motor de base de datos puede conectarse a un grupo de servidores, en cuyo caso abre las conexiones a todas las instancias del grupo de servidores y puede ejecutar simultáneamente la misma consulta en cada conexión.</span><span class="sxs-lookup"><span data-stu-id="1f661-107">The Database Engine Query Editor can connect to a server group, in which case it opens connections to all the instances in the Server Group and can simultaneously run the same query on each connection.</span></span> <span data-ttu-id="1f661-108">Puede usar este cuadro de diálogo para especificar que la barra de estado tiene diferentes colores cuando se conecta con varias instancias en lugar de una instancia. Para cambiar las opciones de resultados de varios servidores, use la página [Opciones (Resultados de la consulta/SQL Server/Multiservidor)](../../2014/database-engine/options-query-results-sql-server-multi-server.md) .</span><span class="sxs-lookup"><span data-stu-id="1f661-108">You can use this dialog to specify that the status bar has different colors when connected to multiple instances rather than one instance.To change the multi-server results options, use the [Options (Query Results/SQL Server/Multi-Server)](../../2014/database-engine/options-query-results-sql-server-multi-server.md) page.</span></span>  
  
## <a name="status-bar-content"></a><span data-ttu-id="1f661-109">Contenido de la barra de estado</span><span class="sxs-lookup"><span data-stu-id="1f661-109">Status Bar Content</span></span>  
 <span data-ttu-id="1f661-110">Especifica la información que aparece en la barra de estado del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="1f661-110">Specifies the information that appears in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="1f661-111">**Mostrar tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="1f661-111">**Display execution time**</span></span>  
 <span data-ttu-id="1f661-112">Incluye la hora de ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="1f661-112">Includes the script execution time.</span></span> <span data-ttu-id="1f661-113">La configuración es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f661-113">The settings are as follows:</span></span>  
  
 <span data-ttu-id="1f661-114">**None**</span><span class="sxs-lookup"><span data-stu-id="1f661-114">**None**</span></span>  
 <span data-ttu-id="1f661-115">La barra de estado no muestra ninguna información horaria.</span><span class="sxs-lookup"><span data-stu-id="1f661-115">The status bar displays no time information.</span></span>  
  
 <span data-ttu-id="1f661-116">**Fin**</span><span class="sxs-lookup"><span data-stu-id="1f661-116">**End**</span></span>  
 <span data-ttu-id="1f661-117">La barra de estado muestra la hora actual del día mientras se ejecuta el script.</span><span class="sxs-lookup"><span data-stu-id="1f661-117">The status bar displays the current time of day while the script is running.</span></span> <span data-ttu-id="1f661-118">Cuando se completa el script, la pantalla muestra la hora del día a la que se ha completado el script.</span><span class="sxs-lookup"><span data-stu-id="1f661-118">When the script completes, the display shows the time of day that the script completed.</span></span>  
  
 <span data-ttu-id="1f661-119">**Transcurrido**</span><span class="sxs-lookup"><span data-stu-id="1f661-119">**Elapsed**</span></span>  
 <span data-ttu-id="1f661-120">La barra de estado muestra la cantidad de tiempo que el script ha estado en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1f661-120">The status bar displays the length of time that the script has been running.</span></span> <span data-ttu-id="1f661-121">Cuando se completa el script, la pantalla muestra el tiempo que ha llevado ejecutarse el script.</span><span class="sxs-lookup"><span data-stu-id="1f661-121">When the script completes, the display shows how much time was taken to run the script.</span></span>  
  
 <span data-ttu-id="1f661-122">**Incluir nombre de base de datos**</span><span class="sxs-lookup"><span data-stu-id="1f661-122">**Include database name**</span></span>  
 <span data-ttu-id="1f661-123">Incluye el nombre de la base de datos actual para la conexión.</span><span class="sxs-lookup"><span data-stu-id="1f661-123">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="1f661-124">Cuando se abre el editor de consultas por primera vez, esta es la base de datos predeterminada del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="1f661-124">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="1f661-125">El contexto de la base de datos se puede cambiar posteriormente mediante la instrucción USE de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1f661-125">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="1f661-126">**Incluir nombre de inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="1f661-126">**Include login name**</span></span>  
 <span data-ttu-id="1f661-127">Incluye el nombre de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="1f661-127">Includes the login name.</span></span>  
  
 <span data-ttu-id="1f661-128">**Incluir recuento de filas**</span><span class="sxs-lookup"><span data-stu-id="1f661-128">**Include row count**</span></span>  
 <span data-ttu-id="1f661-129">Incluye un recuento de las filas procesadas por el script que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="1f661-129">Includes a count of the rows that have been processed by the script that is currently executing.</span></span>  
  
 <span data-ttu-id="1f661-130">**Incluir nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="1f661-130">**Include server name**</span></span>  
 <span data-ttu-id="1f661-131">Incluye el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="1f661-131">Includes the server name.</span></span> <span data-ttu-id="1f661-132">Para las conexiones locales, es el nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="1f661-132">For local connections, this is the instance name.</span></span> <span data-ttu-id="1f661-133">Para las conexiones remotas, es el nombre del equipo remoto y el nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="1f661-133">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="status-bar-layout-and-colors"></a><span data-ttu-id="1f661-134">Diseño de la barra de estado y colores</span><span class="sxs-lookup"><span data-stu-id="1f661-134">Status Bar Layout and Colors</span></span>  
 <span data-ttu-id="1f661-135">Especifica los colores de los elementos de la barra de estado del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="1f661-135">Specifies the colors for items in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="1f661-136">**Conexiones de grupo**</span><span class="sxs-lookup"><span data-stu-id="1f661-136">**Group connections**</span></span>  
 <span data-ttu-id="1f661-137">Establezca el color de la barra de estado cuando el Editor de consultas tenga más de una conexión.</span><span class="sxs-lookup"><span data-stu-id="1f661-137">Set the color of the status bar when the Query Editor has more than one connection.</span></span>  
  
 <span data-ttu-id="1f661-138">**Conexiones de servidor único**</span><span class="sxs-lookup"><span data-stu-id="1f661-138">**Single server connections**</span></span>  
 <span data-ttu-id="1f661-139">Establezca el color de la barra de estado cuando el Editor de consultas tenga una conexión.</span><span class="sxs-lookup"><span data-stu-id="1f661-139">Set the color of the status bar when the Query Editor has one connection.</span></span>  
  
 <span data-ttu-id="1f661-140">**Ubicación de la barra de estado**</span><span class="sxs-lookup"><span data-stu-id="1f661-140">**Status bar location**</span></span>  
 <span data-ttu-id="1f661-141">Especifica la ubicación de la barra de estado.</span><span class="sxs-lookup"><span data-stu-id="1f661-141">Specifies the location of the status bar.</span></span> <span data-ttu-id="1f661-142">La configuración es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f661-142">The settings are as follows:</span></span>  
  
 <span data-ttu-id="1f661-143">**Top** (Principales)</span><span class="sxs-lookup"><span data-stu-id="1f661-143">**Top**</span></span>  
 <span data-ttu-id="1f661-144">La barra de estado aparece en la parte superior de la ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="1f661-144">The status bar appears at the top of the Query Editor window.</span></span>  
  
 <span data-ttu-id="1f661-145">**Inferior**</span><span class="sxs-lookup"><span data-stu-id="1f661-145">**Bottom**</span></span>  
 <span data-ttu-id="1f661-146">La barra de estado aparece en la parte inferior de la ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="1f661-146">The status bar appears at the bottom of the Query Editor window.</span></span>  
  
## <a name="tab-text"></a><span data-ttu-id="1f661-147">Texto de pestaña</span><span class="sxs-lookup"><span data-stu-id="1f661-147">Tab Text</span></span>  
 <span data-ttu-id="1f661-148">Especifica el texto que aparece en la pestaña en la parte superior de una ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="1f661-148">Specifies the text that appears in the tab at the top of a Query Editor window.</span></span> <span data-ttu-id="1f661-149">Si el texto es demasiado largo para mostrarse, puede ver la cadena completa en una información sobre herramientas que se muestra si mantiene el mouse sobre la pestaña.</span><span class="sxs-lookup"><span data-stu-id="1f661-149">If the text is too long to display, you can view the full string in a tooltip that is displayed if you hover over the tab.</span></span>  
  
 <span data-ttu-id="1f661-150">**Incluir nombre de base de datos**</span><span class="sxs-lookup"><span data-stu-id="1f661-150">**Include database name**</span></span>  
 <span data-ttu-id="1f661-151">Incluye el nombre de la base de datos actual para la conexión.</span><span class="sxs-lookup"><span data-stu-id="1f661-151">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="1f661-152">Cuando se abre el editor de consultas por primera vez, esta es la base de datos predeterminada del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="1f661-152">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="1f661-153">El contexto de la base de datos se puede cambiar posteriormente mediante la instrucción USE de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1f661-153">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="1f661-154">**Incluir nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="1f661-154">**Include file name**</span></span>  
 <span data-ttu-id="1f661-155">Incluye el nombre del archivo donde se almacena el script.</span><span class="sxs-lookup"><span data-stu-id="1f661-155">Includes the name of the file where the script is stored.</span></span>  
  
 <span data-ttu-id="1f661-156">**Incluir carpeta**</span><span class="sxs-lookup"><span data-stu-id="1f661-156">**Include folder name**</span></span>  
 <span data-ttu-id="1f661-157">Incluye la ruta de acceso donde se almacena el archivo de script.</span><span class="sxs-lookup"><span data-stu-id="1f661-157">Includes the path of the folder where the script file is stored.</span></span>  
  
 <span data-ttu-id="1f661-158">**Incluir nombre de inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="1f661-158">**Include login name**</span></span>  
 <span data-ttu-id="1f661-159">Incluye el nombre de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="1f661-159">Includes the login name.</span></span>  
  
 <span data-ttu-id="1f661-160">**Incluir nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="1f661-160">**Include server name**</span></span>  
 <span data-ttu-id="1f661-161">Incluye el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="1f661-161">Includes the server name.</span></span> <span data-ttu-id="1f661-162">Para las conexiones locales, es el nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="1f661-162">For local connections, this is the instance name.</span></span> <span data-ttu-id="1f661-163">Para las conexiones remotas, es el nombre del equipo remoto y el nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="1f661-163">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f661-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f661-164">See Also</span></span>  
 <span data-ttu-id="1f661-165">[Opciones &#40;entorno: página fuentes y colores&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span><span class="sxs-lookup"><span data-stu-id="1f661-165">[Options &#40;Environment: Fonts and Colors Page&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span></span>  
 [<span data-ttu-id="1f661-166">Codificación de colores en el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="1f661-166">Color Coding in Query Editors</span></span>](../relational-databases/scripting/color-coding-in-query-editors.md)  
  
  
