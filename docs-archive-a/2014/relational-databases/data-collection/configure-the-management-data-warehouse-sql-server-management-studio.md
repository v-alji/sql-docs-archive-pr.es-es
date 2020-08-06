---
title: Configuración del almacén de administración de datos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollection.wizard_finish.f1
- sql12.swb.dc.datacollection.wizard_maploginuser.f1
- sql12.swb.dc.datacollection.wizard_welcome.f1
- sql12.swb.dc.datacollection.wizard_choosemdw.f1
- sql12.swb.dc.datacollection.wizard_completecfg.f1
- sql12.swb.dc.datacollection.wizard_config.f1
- sql12.swb.dc.datacollection.wizard_createmdw.f1
helpviewer_keywords:
- data warehouse [SQL Server], multiple instances
- data warehouse [SQL Server], configuring
- Configure Management Data Warehouse Wizard
- management data warehouse, configuring
ms.assetid: 23a584f3-c5e1-414c-9afe-73cd7efbda4b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1ef4ddd518343a3076c72ecc41f9b15ddf092dc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678205"
---
# <a name="configure-the-management-data-warehouse-sql-server-management-studio"></a><span data-ttu-id="902b7-102">Configurar el almacén de administración de datos (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="902b7-102">Configure the Management Data Warehouse (SQL Server Management Studio)</span></span>
  <span data-ttu-id="902b7-103">En este tema se describe cómo configurar el almacén de administración de datos para admitir el almacenamiento de datos en una o varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que utilizan el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-103">This topic describes how to configure the management data warehouse to support data storage on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the data collector.</span></span> <span data-ttu-id="902b7-104">Estas instancias pueden estar en el mismo servidor o en servidores diferentes.</span><span class="sxs-lookup"><span data-stu-id="902b7-104">These instances can be on the same server or on different servers.</span></span> <span data-ttu-id="902b7-105">También se proporcionan descripciones de la interfaz de usuario del cuadro de diálogo [Asistente para configurar el almacén de administración de datos](#Wizard) .</span><span class="sxs-lookup"><span data-stu-id="902b7-105">This topic also provides descriptions of the user interface for the [Configure Data Management Warehouse Wizard](#Wizard) dialog box.</span></span> <span data-ttu-id="902b7-106">Para obtener información acerca de cómo configurar un recopilador de datos, vea [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span><span class="sxs-lookup"><span data-stu-id="902b7-106">For information about configuring a data collector, see [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="902b7-107">Si se configura el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que se ejecute mediante una de las cuentas de servicio del sistema (sistema local, servicio de red o servicio local) y el almacén de administración de datos se crea en una instancia diferente del recopilador de datos, debe configurar los conjuntos de recopilación para que utilicen un proxy para cargar los datos en el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is configured to run using one of the System service accounts (Local System, Network Service, or Local Service), and the management data warehouse is created on a different instance from the data collector, you must configure collection sets to use a proxy for uploading data to the management data warehouse.</span></span>  
  
### <a name="configure-the-management-data-warehouse-on-a-single-instance-or-multiple-instances-of-ssnoversion"></a><span data-ttu-id="902b7-108">Configurar el almacén de administración de datos en una o varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="902b7-108">Configure the management data warehouse on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="902b7-109">Asegúrese de que el Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="902b7-109">Ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running.</span></span>  
  
2.  <span data-ttu-id="902b7-110">En el Explorador de objetos, expanda el nodo **Administración** .</span><span class="sxs-lookup"><span data-stu-id="902b7-110">In Object Explorer, expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="902b7-111">Haga clic con el botón derecho en **Recopilación de datos**, expanda **Tareas**y haga clic en **Configurar almacén de administración de datos**.</span><span class="sxs-lookup"><span data-stu-id="902b7-111">Right-click **Data Collection**, expand **Tasks**, and then click **Configure Management Data Warehouse**.</span></span>  
  
4.  <span data-ttu-id="902b7-112">Use el [Asistente para configurar el almacén de administración de datos](#Wizard) para crear un almacén de administración de datos, configurar inicios de sesión, habilitar la recopilación de datos e iniciar **Conjuntos de recopilación de datos del sistema**.</span><span class="sxs-lookup"><span data-stu-id="902b7-112">Use the [Configure Management Data Warehouse Wizard](#Wizard) to create a management data warehouse, configure logins, enable data collection, and start the **System Data Collection Sets**.</span></span>  
  
     <span data-ttu-id="902b7-113">Para configurar varias instancias, continúe con el paso 5.</span><span class="sxs-lookup"><span data-stu-id="902b7-113">To configure multiple instances, continue with step 5.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="902b7-114">Se recomienda utilizar servidores proxy en las implementaciones en que el recopilador de datos está instalado en varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que utilizan el mismo almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-114">It is considered best practice to use proxies in deployments where the data collector is installed on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the same management data warehouse.</span></span>  
  
5.  <span data-ttu-id="902b7-115">Abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] en otra instancia y realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="902b7-115">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] on another instance and do either of the following:</span></span>  
  
    -   <span data-ttu-id="902b7-116">Use el Asistente para configurar el almacén de administración de datos a fin de configurar la recopilación de datos para el almacén de administración de datos existente.</span><span class="sxs-lookup"><span data-stu-id="902b7-116">Use the Configure Management Data Warehouse wizard to configure data collection for the existing management data warehouse.</span></span>  
  
    -   <span data-ttu-id="902b7-117">Haga clic con el botón derecho en **Recopilación de datos**y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="902b7-117">Right-click **Data Collection**, and then click **Properties**.</span></span> <span data-ttu-id="902b7-118">En la pestaña **General** , especifique el almacén de administración de datos existente y el servidor en que está instalado.</span><span class="sxs-lookup"><span data-stu-id="902b7-118">On the **General** tab, specify the existing management data warehouse and the server that it is installed on.</span></span>  
  
6.  <span data-ttu-id="902b7-119">Repita el paso 5 hasta que todas las instancias de base de datos que utilizan el recopilador de datos estén configuradas para cargar datos en el almacén de administración de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="902b7-119">Repeat step 5 until all the database instances that use the data collector are configured to upload data to the shared management data warehouse.</span></span>  
  
####  <a name="configure-management-data-warehouse-wizard"></a><a name="Wizard"></a> <span data-ttu-id="902b7-120">Asistente para configurar el almacén de administración de datos</span><span class="sxs-lookup"><span data-stu-id="902b7-120">Configure Management Data Warehouse Wizard</span></span>  
 <span data-ttu-id="902b7-121">**Página Asistente**</span><span class="sxs-lookup"><span data-stu-id="902b7-121">**Welcome Page**</span></span>  
  
 <span data-ttu-id="902b7-122">La página de bienvenida es la página de inicio del Asistente para configurar la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-122">The Welcome page is the starting page of the Configure Data Collection Wizard.</span></span> <span data-ttu-id="902b7-123">El usuario decide si desea que se muestre.</span><span class="sxs-lookup"><span data-stu-id="902b7-123">Displaying this page is optional.</span></span>  
  
 <span data-ttu-id="902b7-124">**No volver a mostrar esta página.**</span><span class="sxs-lookup"><span data-stu-id="902b7-124">**Do not show this starting page again.**</span></span>  
 <span data-ttu-id="902b7-125">Seleccione esta opción para suprimir esta página la próxima vez que ejecute el Asistente para configurar la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-125">Select to suppress this page the next time you launch the Configure Data Collection Wizard.</span></span>  
  
 <span data-ttu-id="902b7-126">**Página Configurar almacenamiento del almacén de administración de datos**</span><span class="sxs-lookup"><span data-stu-id="902b7-126">**Configure Management Data Warehouse Storage Page**</span></span>  
  
 <span data-ttu-id="902b7-127">Utilice esta página para seleccionar un servidor de bases de datos y un almacén de administración de datos para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="902b7-127">Use this page to select a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and management data warehouse.</span></span> <span data-ttu-id="902b7-128">El almacén de administración de datos es una base de datos relacional que almacenará los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="902b7-128">The management data warehouse is a relational database that will store collected data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="902b7-129">Debe tener el nivel de permisos adecuado para crear el almacén de administración de datos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="902b7-129">You must have the appropriate level of permissions in order to create the management data warehouse on the server.</span></span> <span data-ttu-id="902b7-130">Para obtener más información, vea [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="902b7-130">For more information, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span> <span data-ttu-id="902b7-131">También debe tener el nivel de permisos adecuado para crear inicios de sesión para los roles del almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-131">You also must have the appropriate level of permissions to create logins for management data warehouse roles.</span></span>  
  
 <span data-ttu-id="902b7-132">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="902b7-132">**Server name**</span></span>  
 <span data-ttu-id="902b7-133">Especifica el nombre del servidor que hospedará el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-133">Specifies the name of the server that will host the management data warehouse.</span></span>  
  
 <span data-ttu-id="902b7-134">Al configurar un almacén de administración de datos, **Nombre del servidor** es siempre el nombre del servidor local y no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="902b7-134">When configuring a management data warehouse, **Server name** is always the name of the local server and cannot be modified.</span></span>  
  
 <span data-ttu-id="902b7-135">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="902b7-135">**Database name**</span></span>  
 <span data-ttu-id="902b7-136">Especifica la base de datos relacional que almacenará los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="902b7-136">Specifies the relational database that will store collected data.</span></span> <span data-ttu-id="902b7-137">Utilice la lista para seleccionar una base de datos existente o haga clic en **Nueva** para crear una nueva base de datos mediante el cuadro de diálogo **Nueva base de datos** .</span><span class="sxs-lookup"><span data-stu-id="902b7-137">Use the list to select an existing database or click **New** to create a new database using the **New Database** dialog.</span></span>  
  
 <span data-ttu-id="902b7-138">La opción **Nueva** solo está disponible al configurar un conjunto de recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-138">The **New** option is available only when configuring a data collection set</span></span>  
  
 <span data-ttu-id="902b7-139">**Página Asignar inicios de sesión y usuarios**</span><span class="sxs-lookup"><span data-stu-id="902b7-139">**Map Logins and Users Page**</span></span>  
  
 <span data-ttu-id="902b7-140">Utilice esta página para asignar inicios de sesión a roles de usuario de base de datos para el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-140">Use this page to map logins to database user roles for the management data warehouse.</span></span>  
  
 <span data-ttu-id="902b7-141">**Usuarios asignados a este inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="902b7-141">**Users mapped to this login**</span></span>  
 <span data-ttu-id="902b7-142">Muestra los inicios de sesión existentes en el servidor que hospedará el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-142">Displays the existing logins on the server that will host the management data warehouse.</span></span> <span data-ttu-id="902b7-143">Cada fila contiene una casilla **Asignar** modificable, un nombre de **Inicio de sesión** y un **Tipo** de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="902b7-143">Each row contains an editable **Map** check box, a **Login** name, and a **Type** of login.</span></span>  
  
 <span data-ttu-id="902b7-144">Especifique un inicio de sesión activando la casilla **Asignar** para el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="902b7-144">Specify a login by selecting the **Map** checkbox for the login.</span></span>  
  
 <span data-ttu-id="902b7-145">**Pertenencia del rol de base de datos para:** *\<data warehouse name>*</span><span class="sxs-lookup"><span data-stu-id="902b7-145">**Database role membership for:**  *\<data warehouse name>*</span></span>  
 <span data-ttu-id="902b7-146">Seleccione el rol del almacén de administración de datos al que se ha asignado el inicio de sesión haciendo clic en la casilla correspondiente a una o varias de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="902b7-146">Select the management data warehouse role that the login is mapped to by clicking the checkbox by one or more of the following options:</span></span>  
  
-   <span data-ttu-id="902b7-147">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="902b7-147">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="902b7-148">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="902b7-148">**mdw_reader**</span></span>  
  
-   <span data-ttu-id="902b7-149">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="902b7-149">**mdw_writer**</span></span>  
  
 <span data-ttu-id="902b7-150">**Nuevo inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="902b7-150">**New Login**</span></span>  
 <span data-ttu-id="902b7-151">Abra el cuadro de diálogo **Inicio de sesión - Nuevo** y cree un nuevo inicio de sesión para el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-151">Open the **Login - New** dialog box and create a new login for the management data warehouse.</span></span>  
  
 <span data-ttu-id="902b7-152">**Página Finalización del asistente**</span><span class="sxs-lookup"><span data-stu-id="902b7-152">**Complete the Wizard Page**</span></span>  
  
 <span data-ttu-id="902b7-153">Utilice esta página para comprobar y completar la configuración de la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-153">Use this page to verify and complete data collection configuration.</span></span> <span data-ttu-id="902b7-154">El árbol mostrado en la ventana de vista muestra las configuraciones que se aplicarán, así como las acciones que tendrán lugar al hacer clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="902b7-154">The tree displayed in the viewing window shows what configurations will applied as well as what actions will take place when you click **Finish**.</span></span>  
  
 <span data-ttu-id="902b7-155">**Página Progreso del Asistente para configurar la recopilación de datos**</span><span class="sxs-lookup"><span data-stu-id="902b7-155">**Configure Data Collection Wizard Progress Page**</span></span>  
  
 <span data-ttu-id="902b7-156">Utilice esta página para ver los resultados de cada paso de configuración.</span><span class="sxs-lookup"><span data-stu-id="902b7-156">Use this page to view the results of each configuration step.</span></span>  
  
 <span data-ttu-id="902b7-157">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="902b7-157">**Details**</span></span>  
 <span data-ttu-id="902b7-158">Muestra cada paso de configuración como una fila en la cuadrícula **Detalles** .</span><span class="sxs-lookup"><span data-stu-id="902b7-158">Displays each configuration step as a row in the **Details** grid.</span></span> <span data-ttu-id="902b7-159">Cada fila contiene una columna **Acción** que describe el paso y una columna **Estado** que indica si el paso se ha realizado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="902b7-159">Each row contains an **Action** column that describes the step, and a **Status** column that indicates the success or failure of the step.</span></span> <span data-ttu-id="902b7-160">Si hay un error, aparece un mensaje en la columna **Mensaje** .</span><span class="sxs-lookup"><span data-stu-id="902b7-160">If there is an error, a message appears in the **Message** column.</span></span>  
  
 <span data-ttu-id="902b7-161">**Detención**</span><span class="sxs-lookup"><span data-stu-id="902b7-161">**Stop**</span></span>  
 <span data-ttu-id="902b7-162">Detiene el procesamiento del asistente.</span><span class="sxs-lookup"><span data-stu-id="902b7-162">Stop wizard processing.</span></span>  
  
 <span data-ttu-id="902b7-163">**Report**</span><span class="sxs-lookup"><span data-stu-id="902b7-163">**Report**</span></span>  
 <span data-ttu-id="902b7-164">Muestra un informe de la configuración de la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="902b7-164">View a report of the data collection configuration.</span></span> <span data-ttu-id="902b7-165">Se proporcionan las opciones de informe siguientes:</span><span class="sxs-lookup"><span data-stu-id="902b7-165">The following report options are provided:</span></span>  
  
-   <span data-ttu-id="902b7-166">Ver informe</span><span class="sxs-lookup"><span data-stu-id="902b7-166">View Report</span></span>  
  
-   <span data-ttu-id="902b7-167">Guardar informe en archivo</span><span class="sxs-lookup"><span data-stu-id="902b7-167">Save Report to File</span></span>  
  
-   <span data-ttu-id="902b7-168">Copiar informe al Portapapeles</span><span class="sxs-lookup"><span data-stu-id="902b7-168">Copy Report to Clipboard</span></span>  
  
-   <span data-ttu-id="902b7-169">Enviar informe como correo electrónico</span><span class="sxs-lookup"><span data-stu-id="902b7-169">Send Report as E-mail</span></span>  
  
 <span data-ttu-id="902b7-170">**Close**</span><span class="sxs-lookup"><span data-stu-id="902b7-170">**Close**</span></span>  
 <span data-ttu-id="902b7-171">Cierra el asistente.</span><span class="sxs-lookup"><span data-stu-id="902b7-171">Close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="902b7-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="902b7-172">See Also</span></span>  
 <span data-ttu-id="902b7-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="902b7-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span></span>  
 <span data-ttu-id="902b7-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="902b7-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span></span>  
 <span data-ttu-id="902b7-175">[Recopilación de datos](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="902b7-175">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="902b7-176">Administrar la recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="902b7-176">Manage Data Collection</span></span>](manage-data-collection.md)  
  
  
