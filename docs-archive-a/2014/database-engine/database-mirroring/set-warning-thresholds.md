---
title: Establecer umbrales de advertencia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.setwarningthreshold.f1
ms.assetid: 17f93147-e7d9-4092-b4c2-c11b38051171
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2d5fd9c0213d74f3a6b5d0d4cb2f11d3531d336d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746476"
---
# <a name="set-warning-thresholds"></a><span data-ttu-id="1c2bc-102">Establecer umbrales de advertencia</span><span class="sxs-lookup"><span data-stu-id="1c2bc-102">Set Warning Thresholds</span></span>
  <span data-ttu-id="1c2bc-103">Utilice este cuadro de diálogo para habilitar y configurar uno o varios umbrales de advertencia para la base de datos seleccionada en el árbol de navegación del cuadro de diálogo **Monitor de creación de reflejo de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="1c2bc-103">Use this dialog box to enable and configure one or more warning thresholds for the database selected in the navigation tree of the **Database Mirroring Monitor** dialog box.</span></span>  
  
 <span data-ttu-id="1c2bc-104">El cuadro de diálogo intenta conectarse a las dos instancias del servidor.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-104">The dialog box tries to connect to both server instances.</span></span> <span data-ttu-id="1c2bc-105">Estas conexiones se establecen de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-105">These connections are established asynchronously.</span></span> <span data-ttu-id="1c2bc-106">En el cuadro de diálogo se muestra el estado de conexión de cada asociado.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-106">The dialog shows the connection status of each partner.</span></span> <span data-ttu-id="1c2bc-107">Si el asociado no está conectado, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-107">If the partner is not connected, you can click **Connect**.</span></span>  
  
 <span data-ttu-id="1c2bc-108">**Para utilizar SQL Server Management Studio a fin de supervisar la creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-108">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="1c2bc-109">Iniciar el Monitor de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1c2bc-109">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="options"></a><span data-ttu-id="1c2bc-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="1c2bc-110">Options</span></span>  
 <span data-ttu-id="1c2bc-111">*Instancia del servidor y su estado de conexión*</span><span class="sxs-lookup"><span data-stu-id="1c2bc-111">*Server instance and its connection status*</span></span>  
 <span data-ttu-id="1c2bc-112">Nombre de una instancia del servidor asociado con el formato _sistema_ **\\** _INSTANCE_NAME_.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-112">Name of a partner server instance in the form _SYSTEM_**\\**_INSTANCE_NAME_.</span></span> <span data-ttu-id="1c2bc-113">En el caso de una instancia de servidor predeterminada, solo se muestra el nombre del sistema.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-113">For a default server instance, only the system name is displayed.</span></span>  
  
 <span data-ttu-id="1c2bc-114">Este campo también indica si el monitor está conectado actualmente a esta instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-114">This field also indicates whether the monitor is currently connected to this server instance.</span></span> <span data-ttu-id="1c2bc-115">Los estados de conexión posibles son:</span><span class="sxs-lookup"><span data-stu-id="1c2bc-115">The possible connection statuses are:</span></span>  
  
-   <span data-ttu-id="1c2bc-116">**No conectado a** *nombre de instancia de servidor*</span><span class="sxs-lookup"><span data-stu-id="1c2bc-116">**Not connected to**  *server_instance_name*</span></span>  
  
-   <span data-ttu-id="1c2bc-117">**Intentando conectar a** *nombre de instancia de servidor*</span><span class="sxs-lookup"><span data-stu-id="1c2bc-117">**Trying to connect to**  *server_instance_name*</span></span>  
  
-   <span data-ttu-id="1c2bc-118">**Conectado a** *nombre de instancia de servidor*</span><span class="sxs-lookup"><span data-stu-id="1c2bc-118">**Connected to**  *server_instance_name*</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1c2bc-119">Si no es miembro del rol fijo de servidor **sysadmin**, este estado es **Conectado a** *nombre de instancia de servidor*  **(permisos limitados)** .</span><span class="sxs-lookup"><span data-stu-id="1c2bc-119">If you do are not a member of the **sysadmin** fixed server role, this status is **Connected to** *server_instance_name* **(Limited permissions)**.</span></span>  
  
 <span data-ttu-id="1c2bc-120">El nombre de cada una de las instancias del servidor asociado se muestra en otro campo de *instancia del servidor y su estado de conexión* .</span><span class="sxs-lookup"><span data-stu-id="1c2bc-120">The name of each of the partner server instances is displayed in a separate *Server instance and its connection status* field.</span></span> <span data-ttu-id="1c2bc-121">En el campo superior se muestra el servidor principal cuando el monitor inició su ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-121">The top field lists the principal server when the monitor started running.</span></span>  
  
 <span data-ttu-id="1c2bc-122">**Conectar**/**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-122">**Connect**/**Cancel**</span></span>  
 <span data-ttu-id="1c2bc-123">Un botón **Conectar**/**Cancelar** está asociado a cada campo de la *instancia del servidor y su estado de conexión* .</span><span class="sxs-lookup"><span data-stu-id="1c2bc-123">A **Connect**/**Cancel** button is associated with each *Server instance and its connection status* fields.</span></span> <span data-ttu-id="1c2bc-124">El estado del botón depende del estado de la conexión:</span><span class="sxs-lookup"><span data-stu-id="1c2bc-124">The state of the button depends on the connection status:</span></span>  
  
-   <span data-ttu-id="1c2bc-125">Si no hay conexión con la instancia del servidor, el texto del botón es **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-125">If there is no connection to the server instance, the button text is **Connect**.</span></span> <span data-ttu-id="1c2bc-126">Haga clic en el botón para conectarse a la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-126">Click to connect to the server instance.</span></span>  
  
-   <span data-ttu-id="1c2bc-127">Cuando hay un intento de conexión en curso, el texto del botón es **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-127">When a connection attempt is in progress, the button text is **Cancel**.</span></span> <span data-ttu-id="1c2bc-128">Haga clic en el botón para cancelar el intento de conexión.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-128">Click to cancel the connection attempt.</span></span>  
  
-   <span data-ttu-id="1c2bc-129">Si el servidor está conectado, el texto del botón es **Conectado**y éste aparece atenuado.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-129">If the server is connected, the button text is **Connected**, and the button is dimmed.</span></span>  
  
 <span data-ttu-id="1c2bc-130">**Umbrales**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-130">**Thresholds**</span></span>  
 <span data-ttu-id="1c2bc-131">En la cuadrícula **Umbrales** se muestra la configuración de advertencias para las dos instancias del servidor.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-131">The **Thresholds** grid displays the warnings settings for the two server instances.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c2bc-132">Si una instancia del servidor no está conectada, sus columnas se muestran con celdas vacías y un fondo gris.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-132">If a server instance is not connected, its columns are displayed with empty cells and a gray background.</span></span> <span data-ttu-id="1c2bc-133">Cuando la conexión se abre, la cuadrícula muestra automáticamente el contenido de la instancia.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-133">When the connection opens, the grid automatically displays the content from the instance.</span></span>  
  
 <span data-ttu-id="1c2bc-134">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c2bc-134">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="1c2bc-135">**Advertencias**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-135">**Warnings**</span></span>  
 <span data-ttu-id="1c2bc-136">Muestra las advertencias admitidas:</span><span class="sxs-lookup"><span data-stu-id="1c2bc-136">Lists the supported warnings:</span></span>  
  
|<span data-ttu-id="1c2bc-137">Advertencia</span><span class="sxs-lookup"><span data-stu-id="1c2bc-137">Warning</span></span>|<span data-ttu-id="1c2bc-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c2bc-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c2bc-139">**Advierte si el registro sin enviar supera el valor de umbral**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-139">**Warn if the unsent log exceeds the threshold**</span></span>|<span data-ttu-id="1c2bc-140">El umbral indica el número de kilobytes (KB) del registro sin enviar en la cola de envío del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-140">The threshold indicates the number of kilobytes (KB) of the unsent log in the send queue on the principal.</span></span>|  
|<span data-ttu-id="1c2bc-141">**Advertir si el registro sin restaurar sobrepasa el umbral**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-141">**Warn if the unrestored log exceeds the threshold**</span></span>|<span data-ttu-id="1c2bc-142">El umbral indica el número de KB de la cola rehecha en la instancia del servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-142">The threshold indicates the number of KB of the redo queue on the mirror server instance.</span></span>|  
|<span data-ttu-id="1c2bc-143">**Advertir si la transacción sin enviar más antigua sobrepasa el umbral**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-143">**Warn if the age of the oldest unsent transaction exceeds the threshold**</span></span>|<span data-ttu-id="1c2bc-144">El umbral indica el número de minutos de transacciones que no se han enviado desde la cola de envío a la instancia del servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-144">The threshold indicates the number of minutes of transactions that have not yet been sent from the send queue to the mirror server instance.</span></span> <span data-ttu-id="1c2bc-145">Este valor ayuda a medir la posibilidad de pérdida de datos con respecto a la hora.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-145">This value helps measure the potential for data loss in terms of time.</span></span>|  
|<span data-ttu-id="1c2bc-146">**Advertir si la sobrecarga de confirmación del servidor reflejado sobrepasa el umbral**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-146">**Warn if the mirror commit overhead exceeds the threshold**</span></span>|<span data-ttu-id="1c2bc-147">El umbral indica el número de milisegundos de retraso por transacción (solo relevante en el modo de seguridad alta).</span><span class="sxs-lookup"><span data-stu-id="1c2bc-147">The threshold indicates the number of milliseconds of delay per transaction (relevant only in high-safety mode).</span></span> <span data-ttu-id="1c2bc-148">Este retardo es la cantidad de sobrecarga en la que se incurre mientras la instancia del servidor principal espera a la instancia del servidor reflejado para escribir la entrada de registro de la transacción en la cola de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-148">This delay is the amount of overhead incurred while the principal server instance waits for the mirror server instance to write the transaction's log record into the redo queue.</span></span>|  
  
 <span data-ttu-id="1c2bc-149">**Habilitado en "** *\<server instance>* **"**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-149">**Enabled at '** *\<server instance>* **'**</span></span>  
 <span data-ttu-id="1c2bc-150">Una casilla en blanco indica que la advertencia está deshabilitada actualmente en la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-150">A blank check box indicates that the warning is currently disabled on the server instance.</span></span> <span data-ttu-id="1c2bc-151">Para habilitar una advertencia, haga clic en su casilla.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-151">To enable a warning, click its check box.</span></span>  
  
 <span data-ttu-id="1c2bc-152">**Umbral en "** *\<server instance>* **"**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-152">**Threshold at '** *\<server instance>* **'**</span></span>  
 <span data-ttu-id="1c2bc-153">Al habilitar una advertencia, establezca el umbral en la parte izquierda de esta columna.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-153">When a warning is enabled, set the threshold on the left side of this column.</span></span> <span data-ttu-id="1c2bc-154">Se produce un evento si se ha alcanzado el umbral especificado al actualizarse la tabla de estado.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-154">An event occurs if the specified threshold has been reached when the status table is updated.</span></span> <span data-ttu-id="1c2bc-155">Si deshabilita un umbral tras la configuración de un valor, su valor permanece en este campo y se usará si vuelve a habilitar la advertencia.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-155">If you disable a threshold after configuring a value, your value remains in this field and will be used if you re-enable the warning.</span></span>  
  
 <span data-ttu-id="1c2bc-156">Cuando no se habilita una advertencia, este campo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-156">When a warning is not enabled, this field is inactive.</span></span>  
  
 <span data-ttu-id="1c2bc-157">**OK (CORRECTO)**</span><span class="sxs-lookup"><span data-stu-id="1c2bc-157">**OK**</span></span>  
 <span data-ttu-id="1c2bc-158">Al hacer clic en **Aceptar** , se cierra este cuadro de diálogo y se muestran los valores especificados actualmente de los umbrales de advertencia de la cuadrícula **Umbrales** en la página con pestañas **Advertencias**.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-158">Clicking **OK** closes this dialog box and displays the currently specified values of warning thresholds in the **Thresholds** grid on the **Warnings**tabbed page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c2bc-159">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1c2bc-159">Remarks</span></span>  
 <span data-ttu-id="1c2bc-160">Un umbral solo se puede aplicar a un asociado a la vez, aunque es recomendable que establezca un umbral para un evento específico en los dos asociados, con lo que podrá asegurarse de que la advertencia persiste si se produce una conmutación por error en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-160">A threshold is only applicable at one partner at a time, but we recommend that you set a threshold for a given event on both partners to ensure that the warning persists if the database fails over.</span></span> <span data-ttu-id="1c2bc-161">El umbral adecuado para cada asociado depende de la capacidad de rendimiento del sistema de dicho asociado.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-161">The appropriate threshold for each partner depends on the performance capabilities of that partner's system.</span></span>  
  
 <span data-ttu-id="1c2bc-162">Un evento solo se escribe en el registro de eventos para un rendimiento si su valor se encuentra en el umbral, o por encima de éste, cuando se actualiza la tabla de estado.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-162">An event is written to the event log for a performance only if its value is at or above its threshold when the status table is being updated.</span></span> <span data-ttu-id="1c2bc-163">Si un valor máximo alcanza el umbral momentáneamente entre las actualizaciones de estado, se pierde dicho máximo.</span><span class="sxs-lookup"><span data-stu-id="1c2bc-163">If a peak value reaches the threshold momentarily between status updates that peak is missed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c2bc-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c2bc-164">See Also</span></span>  
 <span data-ttu-id="1c2bc-165">[Iniciar el Monitor de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1c2bc-165">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="1c2bc-166">[Supervisar la creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1c2bc-166">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="1c2bc-167">Iniciar el Asistente para la configuración de seguridad de la creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1c2bc-167">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  
