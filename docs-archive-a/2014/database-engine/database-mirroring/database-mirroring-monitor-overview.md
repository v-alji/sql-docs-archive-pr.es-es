---
title: Información general del Monitor de creación de reflejo de la base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.main.f1
helpviewer_keywords:
- Database Mirroring Monitor [SQL Server], interface
ms.assetid: 8ebbdcd6-565a-498f-b674-289c84b985eb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d19f9a2aa66aaee30bcf623e254d6f24aa690277
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746518"
---
# <a name="database-mirroring-monitor-overview"></a><span data-ttu-id="a2176-102">Información general del Monitor de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="a2176-102">Database Mirroring Monitor Overview</span></span>
  <span data-ttu-id="a2176-103">Si dispone de los permisos correctos, puede utilizar el Monitor de creación de reflejo de la base de datos para supervisar cualquier subconjunto de las bases de datos reflejadas de una instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="a2176-103">If you have the correct permissions, you can use Database Mirroring Monitor to monitor any subset of the mirrored databases on a server instance.</span></span> <span data-ttu-id="a2176-104">La supervisión le permite comprobar si los datos fluyen en la sesión de creación de reflejo de la base de datos. Si hay flujo de datos, supervisa la calidad del mismo.</span><span class="sxs-lookup"><span data-stu-id="a2176-104">Monitoring enables you to verify whether and how well data is flowing in the database mirroring session.</span></span> <span data-ttu-id="a2176-105">Asimismo, el Monitor de creación de reflejo de la base de datos resulta útil para solucionar la causa de un flujo de datos reducido.</span><span class="sxs-lookup"><span data-stu-id="a2176-105">Database Mirroring Monitor is also useful for troubleshooting the cause of reduced data flow.</span></span>  
  
 <span data-ttu-id="a2176-106">Puede registrar cualquiera de las bases de datos reflejadas para supervisar cada uno de los asociados de conmutación por error manualmente.</span><span class="sxs-lookup"><span data-stu-id="a2176-106">You can register any of your mirrored databases for monitoring on each of the failover partners individually.</span></span> <span data-ttu-id="a2176-107">Al registrar una base de datos, el Monitor de creación de reflejo de la base de datos almacena en caché la siguiente información acerca de dicha base de datos:</span><span class="sxs-lookup"><span data-stu-id="a2176-107">When you register a database, Database Mirroring Monitor caches the following information about the database:</span></span>  
  
-   <span data-ttu-id="a2176-108">Nombre de la base de datos</span><span class="sxs-lookup"><span data-stu-id="a2176-108">Database name</span></span>  
  
-   <span data-ttu-id="a2176-109">Nombres de las dos instancias de servidor asociado</span><span class="sxs-lookup"><span data-stu-id="a2176-109">The names of the two partner server instances</span></span>  
  
-   <span data-ttu-id="a2176-110">Últimos roles conocidos de cada asociado (entidad de seguridad o reflejado)</span><span class="sxs-lookup"><span data-stu-id="a2176-110">The last known roles of each partner (principal or mirror)</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="a2176-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="a2176-111">Permissions</span></span>  
 <span data-ttu-id="a2176-112">Para supervisar la creación de reflejo de la base de datos, debe ser miembro del rol fijo de servidor **sysadmin** o del rol fijo de base de datos **dbm_monitor** en la base de datos **msdb** de la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="a2176-112">To monitor database mirroring, you must be a member of either the **sysadmin** fixed server role or the **dbm_monitor** fixed database role in the **msdb** database on the server instance.</span></span> <span data-ttu-id="a2176-113">Si solo es miembro de **sysadmin** o **dbm_monitor** en una de las instancias del servidor asociado, el monitor únicamente puede conectarse a dicho asociado; no puede recuperar información del otro asociado.</span><span class="sxs-lookup"><span data-stu-id="a2176-113">If you are a member of **sysadmin** or **dbm_monitor** on only one of the partner server instances, the monitor can connect only to that partner; the monitor cannot retrieve information from the other partner.</span></span>  
  
 <span data-ttu-id="a2176-114">Si solo es miembro de **dbm_monitor** en una instancia del servidor, tendrá permisos limitados en esa instancia.</span><span class="sxs-lookup"><span data-stu-id="a2176-114">If you are a member of just **dbm_monitor** on a server instance, you will have limited permissions on that server instance.</span></span> <span data-ttu-id="a2176-115">Únicamente podrá ver la fila de estado más reciente.</span><span class="sxs-lookup"><span data-stu-id="a2176-115">You will only be able to view the most recent status row.</span></span> <span data-ttu-id="a2176-116">Si se conecta a una instancia del servidor mediante los permisos **dbm_monitor** , el Monitor de creación de reflejo de la base de datos le informa de que tiene permisos limitados.</span><span class="sxs-lookup"><span data-stu-id="a2176-116">If you connect to a server instance using **dbm_monitor** permissions, Database Mirroring Monitor informs you that you have limited permissions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a2176-117">El rol fijo de base de datos **dbm_monitor** se crea en la base de datos **msdb** cuando se registra la primera base de datos en el Monitor de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a2176-117">The **dbm_monitor** fixed database role is created in the **msdb** database when the first database is registered in Database Mirroring Monitor.</span></span> <span data-ttu-id="a2176-118">El nuevo rol **dbm_monitor** no tiene miembros hasta que un administrador del sistema asigne usuarios al rol.</span><span class="sxs-lookup"><span data-stu-id="a2176-118">The new **dbm_monitor** role has no members until a system administrator assigns users to the role.</span></span>  
  
## <a name="navigation-tree"></a><span data-ttu-id="a2176-119">Árbol de navegación</span><span class="sxs-lookup"><span data-stu-id="a2176-119">Navigation Tree</span></span>  
 <span data-ttu-id="a2176-120">Si las bases de datos se han registrado para supervisión con el Monitor de creación de reflejo de la base de datos, se mostrará una lista de bases de datos registradas en el árbol de navegación.</span><span class="sxs-lookup"><span data-stu-id="a2176-120">If any databases have been registered for monitoring by the Database Mirroring Monitor, a list of registered databases is displayed in the navigation tree.</span></span> <span data-ttu-id="a2176-121">El árbol se actualiza automáticamente cada 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="a2176-121">The tree automatically refreshes every 30 seconds.</span></span> <span data-ttu-id="a2176-122">Para ver el estado de una base de datos registrada, selecciónela.</span><span class="sxs-lookup"><span data-stu-id="a2176-122">To see the status of a registered database, select it.</span></span> <span data-ttu-id="a2176-123">Para obtener más información, vea "Panel de detalles" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="a2176-123">For more information, see "Detail Pane," later in this topic.</span></span>  
  
 <span data-ttu-id="a2176-124">En cada base de datos registrada, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a2176-124">For each registered database, the following information is displayed:</span></span>  
  
 <span data-ttu-id="a2176-125">_<Database_name>_ **(** _\<Status>_ **,** _<PRINCIPAL_SERVER>_ **->** _<MIRROR_SERVER>_ **)**</span><span class="sxs-lookup"><span data-stu-id="a2176-125">_<Database_name>_ **(** _\<Status>_ **,** _<PRINCIPAL_SERVER>_ **->** _<MIRROR_SERVER>_ **)**</span></span>  
  
 <span data-ttu-id="a2176-126">*<Database_name>*</span><span class="sxs-lookup"><span data-stu-id="a2176-126">*<Database_name>*</span></span>  
 <span data-ttu-id="a2176-127">Nombre de una base de datos reflejada que se registra con el Monitor de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a2176-127">The name of a mirrored database that is registered with the Database Mirroring Monitor.</span></span>  
  
 *\<Status>*  
 <span data-ttu-id="a2176-128">Los estados posibles y sus iconos asociados son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2176-128">The possible statuses and their associated icons are as follows:</span></span>  
  
|<span data-ttu-id="a2176-129">Icono</span><span class="sxs-lookup"><span data-stu-id="a2176-129">Icon</span></span>|<span data-ttu-id="a2176-130">Estado</span><span class="sxs-lookup"><span data-stu-id="a2176-130">Status</span></span>|<span data-ttu-id="a2176-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2176-131">Description</span></span>|  
|----------|------------|-----------------|  
|<span data-ttu-id="a2176-132">Icono de advertencia</span><span class="sxs-lookup"><span data-stu-id="a2176-132">Warning icon</span></span>|<span data-ttu-id="a2176-133">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="a2176-133">**Unknown**</span></span>|<span data-ttu-id="a2176-134">El monitor no está conectado a ningún asociado.</span><span class="sxs-lookup"><span data-stu-id="a2176-134">The monitor is not connected to either partner.</span></span> <span data-ttu-id="a2176-135">La única información disponible es lo que el monitor almacena en caché.</span><span class="sxs-lookup"><span data-stu-id="a2176-135">The only available information is what has been cached by the monitor.</span></span>|  
|<span data-ttu-id="a2176-136">Icono de advertencia</span><span class="sxs-lookup"><span data-stu-id="a2176-136">Warning icon</span></span>|<span data-ttu-id="a2176-137">**Sincronizando**</span><span class="sxs-lookup"><span data-stu-id="a2176-137">**Synchronizing**</span></span>|<span data-ttu-id="a2176-138">El contenido de la base de datos reflejada está atrasado con respecto al contenido de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a2176-138">The contents of the mirror database are lagging behind the contents of the principal database.</span></span> <span data-ttu-id="a2176-139">La instancia de servidor principal envía las entradas de registro a la instancia del servidor reflejado, que aplica los cambios en la base de datos reflejada para confirmarla.</span><span class="sxs-lookup"><span data-stu-id="a2176-139">The principal server instance is sending log records to the mirror server instance, which is applying the changes to the mirror database to roll it forward.</span></span><br /><br /> <span data-ttu-id="a2176-140">Al inicio de una sesión de creación de reflejo de la base de datos, las bases de datos principal y reflejada se encuentran en este estado.</span><span class="sxs-lookup"><span data-stu-id="a2176-140">At the start of a database mirroring session, the mirror and principal databases are in this state.</span></span>|  
|<span data-ttu-id="a2176-141">Cilindro de base de datos estándar</span><span class="sxs-lookup"><span data-stu-id="a2176-141">Standard database cylinder</span></span>|<span data-ttu-id="a2176-142">**Sincronizada**</span><span class="sxs-lookup"><span data-stu-id="a2176-142">**Synchronized**</span></span>|<span data-ttu-id="a2176-143">El estado de la base de datos cambia a **Sincronizado**cuando el servidor reflejado está suficientemente al día con respecto al servidor principal.</span><span class="sxs-lookup"><span data-stu-id="a2176-143">When the mirror server becomes sufficiently caught up to the principal server, the database state changes to **Synchronized**.</span></span> <span data-ttu-id="a2176-144">La base de datos permanece en este estado mientras el servidor principal continúa con el envío de cambios al servidor reflejado, y el servidor reflejado continúa con la aplicación de los cambios en la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="a2176-144">The database remains in this state as long as the principal server continues to send changes to the mirror server and the mirror server continues to apply changes to the mirror database.</span></span><br /><br /> <span data-ttu-id="a2176-145">En el modo de seguridad alta, son posibles las conmutaciones manual y automática por error sin pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="a2176-145">For high-safety mode, automatic failover and manual failover are both possible, without any data loss.</span></span><br /><br /> <span data-ttu-id="a2176-146">En el modo de rendimiento alto, siempre es posible que se pierdan datos, incluso en el estado **Sincronizado** .</span><span class="sxs-lookup"><span data-stu-id="a2176-146">For high-performance mode, some data loss is always possible, even in the **Synchronized** state.</span></span>|  
|<span data-ttu-id="a2176-147">Icono de advertencia</span><span class="sxs-lookup"><span data-stu-id="a2176-147">Warning icon</span></span>|<span data-ttu-id="a2176-148">**Suspendido**</span><span class="sxs-lookup"><span data-stu-id="a2176-148">**Suspended**</span></span>|<span data-ttu-id="a2176-149">La base de datos principal está disponible, pero no envía ningún registro al servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="a2176-149">The principal database is available but is not sending any logs to the mirror server.</span></span>|  
|<span data-ttu-id="a2176-150">Icono de error</span><span class="sxs-lookup"><span data-stu-id="a2176-150">Error icon</span></span>|<span data-ttu-id="a2176-151">**Desconectada**</span><span class="sxs-lookup"><span data-stu-id="a2176-151">**Disconnected**</span></span>|<span data-ttu-id="a2176-152">La instancia del servidor no se puede conectar a su asociado.</span><span class="sxs-lookup"><span data-stu-id="a2176-152">The server instance cannot connect to its partner.</span></span>|  
  
 <span data-ttu-id="a2176-153">*<PRINCIPAL_SERVER>*</span><span class="sxs-lookup"><span data-stu-id="a2176-153">*<PRINCIPAL_SERVER>*</span></span>  
 <span data-ttu-id="a2176-154">Nombre del asociado que es actualmente la instancia del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="a2176-154">The name of the partner that is currently the principal server instance.</span></span> <span data-ttu-id="a2176-155">El nombre adopta el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="a2176-155">The name is in the following format:</span></span>  
  
 <span data-ttu-id="a2176-156">*<SYSTEM_NAME>* [ **\\** _<instance_name>_ ]</span><span class="sxs-lookup"><span data-stu-id="a2176-156">*<SYSTEM_NAME>*[**\\**_<instance_name>_]</span></span>  
  
 <span data-ttu-id="a2176-157">donde *<SYSTEM_NAME>* es el nombre del sistema en el que se encuentra la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="a2176-157">where *<SYSTEM_NAME>* is the name of the system on which the server instance resides.</span></span> <span data-ttu-id="a2176-158">En una instancia del servidor no predeterminada, también se muestra el nombre de la instancia: _<SYSTEM_NAME>_ **\\** _<nombre_instancia>_ .</span><span class="sxs-lookup"><span data-stu-id="a2176-158">For a non-default server instance, the instance name is also displayed: _<SYSTEM_NAME>_**\\**_<instance_name>_.</span></span>  
  
 <span data-ttu-id="a2176-159">*<MIRROR_SERVER>*</span><span class="sxs-lookup"><span data-stu-id="a2176-159">*<MIRROR_SERVER>*</span></span>  
 <span data-ttu-id="a2176-160">Nombre del asociado que es actualmente la instancia del servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="a2176-160">The name of the partner that is currently the mirror server instance.</span></span> <span data-ttu-id="a2176-161">El formato es el mismo que el del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="a2176-161">The format is the same as for the principal server.</span></span>  
  
## <a name="detail-pane"></a><span data-ttu-id="a2176-162">Panel de detalles</span><span class="sxs-lookup"><span data-stu-id="a2176-162">Detail Pane</span></span>  
 <span data-ttu-id="a2176-163">El aspecto del monitor depende de si está seleccionada una base de datos.</span><span class="sxs-lookup"><span data-stu-id="a2176-163">The appearance of the monitor depends on whether a database is selected.</span></span> <span data-ttu-id="a2176-164">Al abrir el monitor, el panel de detalles muestra un vínculo **Registrar base de datos reflejada** .</span><span class="sxs-lookup"><span data-stu-id="a2176-164">When you open the monitor, the detail pane displays a **Register mirrored database** link.</span></span> <span data-ttu-id="a2176-165">Haga clic en el vínculo para registrar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="a2176-165">Click this to register a database.</span></span> <span data-ttu-id="a2176-166">Las bases de datos registradas aparecen debajo del nodo **Monitor de creación de reflejo de la base de datos** del árbol de navegación.</span><span class="sxs-lookup"><span data-stu-id="a2176-166">Registered databases are listed below the **Database Mirroring Monitor** node in the navigation tree.</span></span> <span data-ttu-id="a2176-167">El Monitor de creación de reflejo de la base de datos intenta conectarse a todas las instancias de servidor para las que haya almacenado credenciales.</span><span class="sxs-lookup"><span data-stu-id="a2176-167">Database Mirroring Monitor always tries to connect to every server instance for which it has stored credentials.</span></span>  
  
 <span data-ttu-id="a2176-168">Cuando seleccione una base de datos, su estado se mostrará en la página con pestañas **Estado** del panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="a2176-168">When you select a database, its status is displayed on the **Status** tabbed page in the detail pane.</span></span> <span data-ttu-id="a2176-169">El contenido de esta página procede de las instancias de servidor principal y reflejado.</span><span class="sxs-lookup"><span data-stu-id="a2176-169">The content of this page comes from both the principal and mirror server instances.</span></span> <span data-ttu-id="a2176-170">La página se actualiza de forma asincrónica, a medida que se recopila la información del estado a través de conexiones independientes en las instancias de servidor principal y reflejado.</span><span class="sxs-lookup"><span data-stu-id="a2176-170">The page is filled asynchronously as status is gathered through separate connections to the principal and mirror server instances.</span></span> <span data-ttu-id="a2176-171">El estado se actualiza automáticamente a intervalos de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="a2176-171">The status automatically refreshes at 30-second intervals.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2176-172">No puede cambiar la frecuencia de actualización del monitor, pero sí puede actualizar la tabla de estado del cuadro de diálogo **Historial de creación de reflejo de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="a2176-172">You cannot change the monitor's refresh rate, but you can refresh the status table from the **Database Mirroring History** dialog box.</span></span>  
  
 <span data-ttu-id="a2176-173">Un administrador del sistema puede ver la configuración actual de las advertencias para la base de datos; para ello, debe seleccionar la página con pestañas **Advertencias** .</span><span class="sxs-lookup"><span data-stu-id="a2176-173">A system administrator can view the current configuration of warnings for the database by selecting the **Warnings** tabbed page.</span></span> <span data-ttu-id="a2176-174">Desde dicha página, el administrador puede iniciar el cuadro de diálogo **Establecer umbrales de advertencia** para habilitar y configurar uno o varios umbrales de advertencia.</span><span class="sxs-lookup"><span data-stu-id="a2176-174">From there, the administrator can launch the **Set Warning Thresholds** dialog box to enable and configure one or more warning thresholds.</span></span>  
  
 <span data-ttu-id="a2176-175">En el titular situado encima de las pestañas, el panel de detalles muestra la última hora a la que el monitor actualizó la información de estado, como **última actualización:** _\<date>_ *\<time>* .</span><span class="sxs-lookup"><span data-stu-id="a2176-175">In the banner above the tabs, the detail pane displays the last time the monitor refreshed the status information as, **Last refresh:**_\<date>_*\<time>*.</span></span> <span data-ttu-id="a2176-176">Normalmente, el Monitor de creación de reflejo de la base de datos recupera información de estado de las instancias del servidor principal y reflejado a horas diferentes.</span><span class="sxs-lookup"><span data-stu-id="a2176-176">Usually, the Database Mirroring Monitor retrieves status information from the principal and mirror server instances at different times.</span></span> <span data-ttu-id="a2176-177">Se muestran las dos horas de actualización más antiguas.</span><span class="sxs-lookup"><span data-stu-id="a2176-177">The older of these two refresh times is displayed.</span></span>  
  
## <a name="action-menu"></a><span data-ttu-id="a2176-178">Menú Acción</span><span class="sxs-lookup"><span data-stu-id="a2176-178">Action Menu</span></span>  
 <span data-ttu-id="a2176-179">El menú **Acción** siempre contiene los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="a2176-179">The **Action** menu always contains the following commands:</span></span>  
  
|<span data-ttu-id="a2176-180">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a2176-180">Command</span></span>|<span data-ttu-id="a2176-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2176-181">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2176-182">**Registrar base de datos reflejada...**</span><span class="sxs-lookup"><span data-stu-id="a2176-182">**Register Mirrored Database...**</span></span>|<span data-ttu-id="a2176-183">Abre el cuadro de diálogo **Registrar base de datos reflejada** .</span><span class="sxs-lookup"><span data-stu-id="a2176-183">Opens the **Register Mirrored Database** dialog box.</span></span> <span data-ttu-id="a2176-184">Utilice este cuadro de diálogo para registrar una o varias bases de datos reflejadas en una instancia del servidor determinada, mediante la adición de las bases de datos al Monitor de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a2176-184">Use this dialog box to register one or more mirrored databases on a given server instance by adding the database or databases to the Database Mirroring Monitor.</span></span> <span data-ttu-id="a2176-185">Cuando se agrega una base de datos, el Monitor de creación de reflejo de la base de datos almacena localmente en caché información acerca de la base de datos, sus asociados y el método de conexión a éstos.</span><span class="sxs-lookup"><span data-stu-id="a2176-185">When a database is added, Database Mirroring Monitor locally caches information about the database, its partners, and how to connect to the partners.</span></span>|  
|<span data-ttu-id="a2176-186">**Administrar conexiones de instancia del servidor...**</span><span class="sxs-lookup"><span data-stu-id="a2176-186">**Manage Server Instance Connections...**</span></span>|<span data-ttu-id="a2176-187">Si selecciona este comando, se abre el cuadro de diálogo **Administrar conexiones de instancia del servidor** .</span><span class="sxs-lookup"><span data-stu-id="a2176-187">When you select this command, the **Manage Server Connections** dialog box opens.</span></span> <span data-ttu-id="a2176-188">En dicho diálogo, puede elegir una instancia del servidor para la que desee especificar credenciales del monitor, que usará al conectarse a un asociado determinado.</span><span class="sxs-lookup"><span data-stu-id="a2176-188">There, you can choose a server instance for which you want to specify credentials for the monitor to use when connecting to a given partner.</span></span><br /><br /> <span data-ttu-id="a2176-189">Para editar credenciales para un asociado, localice su entrada en la cuadrícula **Instancias del servidor** y haga clic en **Editar** en la fila.</span><span class="sxs-lookup"><span data-stu-id="a2176-189">To edit the credentials for a partner, locate its entry in the **Server instances** grid, and click **Edit** on that row.</span></span> <span data-ttu-id="a2176-190">Se abrirá el cuadro de diálogo **Conectar al servidor** para ese nombre de instancia del servidor, con los controles de credencial inicializados en el valor actual almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="a2176-190">The **Connect to Server** dialog box appears with the server instance name fixed and the credential controls initialized to the current cached value.</span></span> <span data-ttu-id="a2176-191">Cambie la información de autenticación según corresponda y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="a2176-191">Change the authentication information as necessary and click **Connect**.</span></span> <span data-ttu-id="a2176-192">Si las credenciales tienen privilegios suficientes, la columna **Conectar utilizando** se actualizará con las nuevas credenciales.</span><span class="sxs-lookup"><span data-stu-id="a2176-192">If the credentials have sufficient privileges, the **Connect Using** column is updated with the new credentials.</span></span>|  
  
 <span data-ttu-id="a2176-193">Si selecciona una base de datos, el menú **Acción** también contiene los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="a2176-193">If you select a database, the **Action** menu also contains the following commands.</span></span>  
  
|<span data-ttu-id="a2176-194">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a2176-194">Command</span></span>|<span data-ttu-id="a2176-195">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2176-195">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2176-196">**Eliminar esta base de datos del Registro**</span><span class="sxs-lookup"><span data-stu-id="a2176-196">**Unregister This Database**</span></span>|<span data-ttu-id="a2176-197">Quita la base de datos seleccionada del Monitor de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a2176-197">Removes the selected database from Database Mirroring Monitor.</span></span>|  
|<span data-ttu-id="a2176-198">**Establecer umbrales de advertencia...**</span><span class="sxs-lookup"><span data-stu-id="a2176-198">**Set Warning Thresholds...**</span></span>|<span data-ttu-id="a2176-199">Abre el cuadro de diálogo **Establecer umbrales de advertencia** .</span><span class="sxs-lookup"><span data-stu-id="a2176-199">Opens the **Set Warning Thresholds** dialog box.</span></span> <span data-ttu-id="a2176-200">En dicho diálogo, un administrador del sistema puede habilitar o deshabilitar las advertencias para la base de datos en cada uno de los asociados y cambiar el umbral de las advertencias.</span><span class="sxs-lookup"><span data-stu-id="a2176-200">There a system administrator can enable or disable warnings for the database on each of the partners and change the threshold of each warning.</span></span> <span data-ttu-id="a2176-201">Es recomendable establecer un umbral para una advertencia específica en los dos asociados, con lo que se puede garantizar que la advertencia persiste si se produce una conmutación por error en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a2176-201">We recommend setting a threshold for a given warning on both partners to ensure that the warning persists if the database fails over.</span></span> <span data-ttu-id="a2176-202">El umbral adecuado para cada asociado depende de la capacidad de rendimiento del sistema de dicho asociado.</span><span class="sxs-lookup"><span data-stu-id="a2176-202">The appropriate threshold for each partner depends on the performance capabilities of that partner's system.</span></span><br /><br /> <span data-ttu-id="a2176-203">Un evento solo se escribe en el registro de eventos para un rendimiento si su valor se encuentra en el umbral, o por encima de éste, cuando se actualiza la tabla de estado.</span><span class="sxs-lookup"><span data-stu-id="a2176-203">An event is written to the event log for a performance only if its value is at or above its threshold when the status table is being updated.</span></span> <span data-ttu-id="a2176-204">Si un valor máximo alcanza el umbral momentáneamente entre las actualizaciones de estado, se pierde dicho máximo.</span><span class="sxs-lookup"><span data-stu-id="a2176-204">If a peak value reaches the threshold momentarily between status updates that peak is missed.</span></span>|  
  
 <span data-ttu-id="a2176-205">**Para supervisar la creación de reflejo de la base de datos mediante SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="a2176-205">**To monitor database mirroring by using SQL Server Management Studio to**</span></span>  
  
-   [<span data-ttu-id="a2176-206">Iniciar el Monitor de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a2176-206">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="a2176-207">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a2176-207">See Also</span></span>  
 <span data-ttu-id="a2176-208">[Supervisar la creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a2176-208">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="a2176-209">Iniciar el Asistente para la configuración de seguridad de la creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a2176-209">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  