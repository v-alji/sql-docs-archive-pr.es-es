---
title: Editor de la tarea control CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdccontroltask.config.f1
ms.assetid: 4f09d040-9ec8-4aaa-b684-f632d571f0a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6b60f2a9126dbbda934124b39f36ccd90b4e6cc6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676626"
---
# <a name="cdc-control-task-editor"></a><span data-ttu-id="5a20a-102">Editor de la tarea Control de CDC</span><span class="sxs-lookup"><span data-stu-id="5a20a-102">CDC Control Task Editor</span></span>
  <span data-ttu-id="5a20a-103">Use el cuadro de diálogo **Editor de la tarea Control CDC** para configurar la tarea Control CDC.</span><span class="sxs-lookup"><span data-stu-id="5a20a-103">Use the **CDC Control Task Editor** dialog box to configure the CDC Control task.</span></span> <span data-ttu-id="5a20a-104">La configuración de la tarea Control CDC incluye la definición de una conexión a la base de datos CDC, la operación de tarea CDC y la información sobre la administración de estados.</span><span class="sxs-lookup"><span data-stu-id="5a20a-104">The CDC Control task configuration includes defining a connection to the CDC database, the CDC task operation and the state management information.</span></span>  
  
 <span data-ttu-id="5a20a-105">Para obtener más información acerca de la tarea Control CDC, vea [CDC Control Task](control-flow/cdc-control-task.md).</span><span class="sxs-lookup"><span data-stu-id="5a20a-105">To learn more about the CDC Control task, see [CDC Control Task](control-flow/cdc-control-task.md).</span></span>  
  
 <span data-ttu-id="5a20a-106">**Para abrir el Editor de la tarea Control CDC**</span><span class="sxs-lookup"><span data-stu-id="5a20a-106">**To open the CDC Control Task Editor**</span></span>  
  
1.  <span data-ttu-id="5a20a-107">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el paquete de [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tiene la tarea Control CDC.</span><span class="sxs-lookup"><span data-stu-id="5a20a-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC Control task.</span></span>  
  
2.  <span data-ttu-id="5a20a-108">En la pestaña **Flujo de control** , haga doble clic en la tarea Control CDC.</span><span class="sxs-lookup"><span data-stu-id="5a20a-108">On the **Control Flow** tab, double-click the CDC Control task.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5a20a-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="5a20a-109">Options</span></span>  
 <span data-ttu-id="5a20a-110">**Administrador de conexiones de ADO.NET para la base de datos CDC de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5a20a-110">**SQL Server CDC database ADO.NET connection manager**</span></span>  
 <span data-ttu-id="5a20a-111">Seleccione un administrador de conexiones existente de la lista o haga clic en **Nueva** para crear una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="5a20a-111">Select an existing connection manager from the list, or click **New** to create a new connection.</span></span> <span data-ttu-id="5a20a-112">Es preciso realizar la conexión a una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] habilitada para CDC y donde se encuentre la tabla de cambios seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5a20a-112">The connection must be to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database that is enabled for CDC and where the selected change table is located.</span></span>  
  
 <span data-ttu-id="5a20a-113">**Operación de Control CDC**</span><span class="sxs-lookup"><span data-stu-id="5a20a-113">**CDC Control Operation**</span></span>  
 <span data-ttu-id="5a20a-114">Seleccione la operación que vaya a ejecutar para esta tarea.</span><span class="sxs-lookup"><span data-stu-id="5a20a-114">Select the operation to run for this task.</span></span> <span data-ttu-id="5a20a-115">Todas las operaciones usan la variable de estado que se almacena en una variable de paquete SSIS donde se almacena el estado y lo pasa entre los distintos componentes del paquete.</span><span class="sxs-lookup"><span data-stu-id="5a20a-115">All operations use the state variable that is stored in an SSIS package variable that stores the state and passes it between the different components in the package.</span></span>  
  
-   <span data-ttu-id="5a20a-116">**Marcar comienzo de carga inicial**: esta operación se usa cuando se ejecuta una carga inicial desde una base de datos activa sin una instantánea.</span><span class="sxs-lookup"><span data-stu-id="5a20a-116">**Mark initial load start**: This operation is used when executing an initial load from an active database without a snapshot.</span></span> <span data-ttu-id="5a20a-117">Se invoca al comienzo de un paquete de carga inicial para registrar el LSN actual en la base de datos de origen antes de que el paquete de carga inicial comience a leer las tablas de origen.</span><span class="sxs-lookup"><span data-stu-id="5a20a-117">It is invoked at the beginning of an initial-load package to record the current LSN in the source database before the initial-load package starts reading the source tables.</span></span> <span data-ttu-id="5a20a-118">Esto requiere una conexión a la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="5a20a-118">This requires a connection to the source database.</span></span>  
  
     <span data-ttu-id="5a20a-119">Si selecciona **Mark Initial Load Start** (Marcar comienzo de carga inicial) cuando trabaja en CDC de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] (es decir, no en Oracle), el usuario especificado en el administrador de conexiones debe ser  **db_owner** o **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="5a20a-119">If you select **Mark Initial Load Start** when working on [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] CDC (that is, not Oracle) the user specified in the connection manager must be either  **db_owner** or **sysadmin**.</span></span>  
  
-   <span data-ttu-id="5a20a-120">**Marcar final de carga inicial**: esta operación se usa al ejecutar una carga inicial desde una base de datos activa sin una instantánea.</span><span class="sxs-lookup"><span data-stu-id="5a20a-120">**Mark initial load end**: This operation is used when executing an initial load from an active database without a snapshot.</span></span> <span data-ttu-id="5a20a-121">Se invoca al final de un paquete de carga inicial para registrar el LSN actual en la base de datos de origen después de que el paquete de carga inicial termine de leer las tablas de origen.</span><span class="sxs-lookup"><span data-stu-id="5a20a-121">It is invoked at the end of an initial-load package to record the current LSN in the source database after the initial-load package finished reading the source tables.</span></span> <span data-ttu-id="5a20a-122">Este LSN se determina mediante el registro de la hora en el momento en que se produjo esta operación y, posteriormente, mediante consulta a la tabla de asignación de `cdc.lsn_time_`de la base de datos CDC en busca de un cambio que hubiera tenido lugar después de dicha hora.</span><span class="sxs-lookup"><span data-stu-id="5a20a-122">This LSN is determined by recording nthe current time when this operation occurred and then querying the `cdc.lsn_time_`mapping table in the CDC database looking for a change that occurred after that time</span></span>  
  
     <span data-ttu-id="5a20a-123">Si selecciona **Mark Initial Load End** (Marcar final de carga inicial) cuando trabaja en CDC de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] (es decir, no en Oracle), el usuario especificado en el administrador de conexiones debe ser  **db_owner** o **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="5a20a-123">If you select **Mark Initial Load End** when working on [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] CDC (that is, not Oracle) the user specified in the connection manager must be either  **db_owner** or **sysadmin**.</span></span>  
  
-   <span data-ttu-id="5a20a-124">**Marcar comienzo de CDC**: esta operación se utiliza cuando la carga inicial se realiza desde una base de datos de base de datos de instantánea o desde una base de datos de inactividad.</span><span class="sxs-lookup"><span data-stu-id="5a20a-124">**Mark CDC start**: This operation is used when then the initial load is made from a snapshot database or from a quiescence database.</span></span> <span data-ttu-id="5a20a-125">Se invoca en cualquier punto del paquete de carga inicial.</span><span class="sxs-lookup"><span data-stu-id="5a20a-125">It is invoked at any point within the initial load package.</span></span> <span data-ttu-id="5a20a-126">La operación acepta un parámetro que puede ser un LSN de instantánea, un nombre de una base de datos de instantánea (desde la que el LSN de instantánea se deriva automáticamente) o se puede dejar vacío, en cuyo caso el LSN de la base de datos actual se usa como el LSN de inicio para el paquete de procesamiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="5a20a-126">The operation accepts a parameter that can be a snapshot LSN, a name of a snapshot database (from which the snapshot LSN will be derived automatically) or it can be left empty, in which case the current database LSN is used as the start LSN for the change processing package.</span></span>  
  
     <span data-ttu-id="5a20a-127">Esta operación se usa en lugar de las operaciones Marcar comienzo/final de carga inicial.</span><span class="sxs-lookup"><span data-stu-id="5a20a-127">This operation is used instead of the Mark Initial Load Start/End operations.</span></span>  
  
     <span data-ttu-id="5a20a-128">Si selecciona **Mark CDC Start** (Marcar comienzo de CDC) cuando trabaja en CDC de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] (es decir, no en Oracle), el usuario especificado en el administrador de conexiones debe ser  **db_owner** o **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="5a20a-128">If you select **Mark CDC Start** when working on [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] CDC (that is, not Oracle) the user specified in the connection manager must be either  **db_owner** or **sysadmin**.</span></span>  
  
-   <span data-ttu-id="5a20a-129">**Obtener intervalo de procesamiento**: esta operación se usa en un paquete de procesamiento de cambios antes de invocar el flujo de datos que usa el flujo de datos de origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="5a20a-129">**Get processing range**: This operation is used in a change processing package before invoking the data flow that uses the CDC Source data flow.</span></span> <span data-ttu-id="5a20a-130">Establece un intervalo de LSN que lee el flujo de datos de origen de CDC cuando se invoca.</span><span class="sxs-lookup"><span data-stu-id="5a20a-130">It establishes a range of LSNs that the CDC Source data flow reads when invoked.</span></span> <span data-ttu-id="5a20a-131">El intervalo se almacena en una variable de paquete SSIS que usa el origen de CDC durante el procesamiento del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="5a20a-131">The range is stored in an SSIS package variable that is used by the CDC Source during data-flow processing.</span></span>  
  
     <span data-ttu-id="5a20a-132">Para obtener más información sobre los posibles estados CDC que se almacenan, vea [Definir una variable de estado](data-flow/define-a-state-variable.md).</span><span class="sxs-lookup"><span data-stu-id="5a20a-132">For more information about the possible CDC states that are stored, see [Define a State Variable](data-flow/define-a-state-variable.md).</span></span>  
  
-   <span data-ttu-id="5a20a-133">**Marcar intervalo procesado**: esta operación se usa en un paquete de procesamiento de cambios al final de una ejecución CDC (después de que el flujo de datos CDC se complete correctamente) para registrar el último LSN que se haya procesado totalmente en la ejecución CDC.</span><span class="sxs-lookup"><span data-stu-id="5a20a-133">**Mark processed range**: This operation is used in a change processing package at the end of a  CDC run (after the CDC data flow is completed successfully) to record the last LSN that was fully processed in the CDC run.</span></span> <span data-ttu-id="5a20a-134">La próxima vez que se ejecute `GetProcessingRange` , esta posición determinará el inicio del siguiente intervalo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5a20a-134">The next time `GetProcessingRange` is executed, this position determines the start of the next processing range.</span></span>  
  
-   <span data-ttu-id="5a20a-135">**Restablecer estado CDC**: esta operación se usa para restablecer el estado CDC persistente asociado al contexto CDC actual.</span><span class="sxs-lookup"><span data-stu-id="5a20a-135">**Reset CDC state**: This operation is used to reset the persistent CDC state associated with the current CDC context.</span></span> <span data-ttu-id="5a20a-136">Después de ejecutar esta operación, el LSN máximo actual de la tabla de `sys.fn_cdc_get_max_lsn` de la marca de tiempo de LSN se convierte en el inicio del intervalo para el siguiente intervalo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5a20a-136">After this operation is run, the current maximum LSN from the LSN-timestamp `sys.fn_cdc_get_max_lsn` table becomes the start of the range for the next processing range.</span></span> <span data-ttu-id="5a20a-137">Esta operación requiere una conexión a la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="5a20a-137">This operation requires a connection to the source database.</span></span>  
  
     <span data-ttu-id="5a20a-138">Un ejemplo de uso de esta operación es cuando se desea procesar solo los registros de cambios creados recientemente y omitir todos los registros de cambios anteriores.</span><span class="sxs-lookup"><span data-stu-id="5a20a-138">An example of when this operation is used is when you want to process only the newly created change records and ignore all old change records.</span></span>  
  
 <span data-ttu-id="5a20a-139">**Variable que contiene el estado CDC**</span><span class="sxs-lookup"><span data-stu-id="5a20a-139">**Variable containing the CDC state**</span></span>  
 <span data-ttu-id="5a20a-140">Seleccione la variable del paquete SSIS que almacena la información sobre el estado de la operación de la tarea.</span><span class="sxs-lookup"><span data-stu-id="5a20a-140">Select the SSIS package variable that stores the state information for the task operation.</span></span> <span data-ttu-id="5a20a-141">Debe definir una variable antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="5a20a-141">You should define a variable before you begin.</span></span> <span data-ttu-id="5a20a-142">Si selecciona **Persistencia de estado automática**, la variable de estado se carga y guarda automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5a20a-142">If you select **Automatic state persistence**, the state variable is loaded and saved automatically.</span></span>  
  
 <span data-ttu-id="5a20a-143">Para obtener más información sobre cómo se define la variable de estado, vea [Definir una variable de estado](data-flow/define-a-state-variable.md).</span><span class="sxs-lookup"><span data-stu-id="5a20a-143">For more information about defining the state variable, see [Define a State Variable](data-flow/define-a-state-variable.md).</span></span>  
  
 <span data-ttu-id="5a20a-144">**LSN de SQL Server para iniciar el nombre de CDC/instantánea:**</span><span class="sxs-lookup"><span data-stu-id="5a20a-144">**SQL Server LSN to start the CDC/Snapshot name:**</span></span>  
 <span data-ttu-id="5a20a-145">Especifique el LSN de la base de datos de origen actual o el nombre de la base de datos de instantánea de la carga inicial desde donde se realizará la carga inicial con el fin de determinar dónde se inicia CDC.</span><span class="sxs-lookup"><span data-stu-id="5a20a-145">Type the current source database LSN or the name of the snapshot database from which the initial load is performed to determine where the CDC starts.</span></span> <span data-ttu-id="5a20a-146">Esto solo está disponible si se establece **Operación de Control CDC** en **Marcar comienzo de CDC**.</span><span class="sxs-lookup"><span data-stu-id="5a20a-146">This is available only if the **CDC Control Operation** is set to **Mark CDC Start**.</span></span>  
  
 <span data-ttu-id="5a20a-147">Para obtener más información acerca de estas operaciones, vea [CDC Control Task](control-flow/cdc-control-task.md).</span><span class="sxs-lookup"><span data-stu-id="5a20a-147">For more information about these operations, see [CDC Control Task](control-flow/cdc-control-task.md)</span></span>  
  
 <span data-ttu-id="5a20a-148">**Almacenar automáticamente el estado en una tabla de base de datos**</span><span class="sxs-lookup"><span data-stu-id="5a20a-148">**Automatically store state in a database table**</span></span>  
 <span data-ttu-id="5a20a-149">Active esta casilla para que la tarea Control CDC controle automáticamente la carga y el almacenamiento del estado de CDC en una tabla de estado que se encuentre en una base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="5a20a-149">Select this check box for the CDC Control task to automatically handle loading and storing the CDC state in a state table contained in the specified database.</span></span> <span data-ttu-id="5a20a-150">Si no se ha activado, el desarrollador debe cargar el estado de CDC cuando el paquete se inicie y guardarlo cada vez que cambie el estado de CDC.</span><span class="sxs-lookup"><span data-stu-id="5a20a-150">When not selected, the developer must load the CDC State when the package starts and save it whenever the CDC State changes.</span></span>  
  
 <span data-ttu-id="5a20a-151">**Administrador de conexiones para la base de datos donde se almacena el estado**</span><span class="sxs-lookup"><span data-stu-id="5a20a-151">**Connection manager for the database where the state is stored**</span></span>  
 <span data-ttu-id="5a20a-152">Seleccione un administrador de conexiones de ADO.NET existente de la lista o haga clic en Nueva para crear una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="5a20a-152">Select an existing ADO.NET connection manager from the list, or click New to create a new connection.</span></span> <span data-ttu-id="5a20a-153">Esta conexión es a una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que contenga la tabla de estado.</span><span class="sxs-lookup"><span data-stu-id="5a20a-153">This connection is to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database that contains the State table.</span></span> <span data-ttu-id="5a20a-154">La tabla de estado contiene la información sobre el estado.</span><span class="sxs-lookup"><span data-stu-id="5a20a-154">The State table contains the State information.</span></span>  
  
 <span data-ttu-id="5a20a-155">Esto solo está disponible si se ha seleccionado **Persistencia de estado automática** y es un parámetro obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5a20a-155">This is available only if **Automatic state persistence** is selected and it is a required parameter.</span></span>  
  
 <span data-ttu-id="5a20a-156">**Tabla que se va a usar para almacenar el estado**</span><span class="sxs-lookup"><span data-stu-id="5a20a-156">**Table to use for storing state**</span></span>  
 <span data-ttu-id="5a20a-157">Escriba el nombre de la tabla de estado que se va a usar para almacenar el estado de CDC.</span><span class="sxs-lookup"><span data-stu-id="5a20a-157">Type the name of the state table to be used for storing the CDC state.</span></span> <span data-ttu-id="5a20a-158">La tabla especificada debe tener dos columnas denominadas **nombre** y **estado** y ambas columnas deben ser del tipo de datos **varchar (256)**.</span><span class="sxs-lookup"><span data-stu-id="5a20a-158">The table specified must have two columns called **name** and **state** and both columns must be of the data type **varchar (256)**.</span></span>  
  
 <span data-ttu-id="5a20a-159">Opcionalmente, puede seleccionar **Nueva** para obtener un script SQL que cree una nueva tabla de estado con las columnas necesarias.</span><span class="sxs-lookup"><span data-stu-id="5a20a-159">You can optionally select **New** to get an SQL script that builds a new State table with the required columns.</span></span> <span data-ttu-id="5a20a-160">Cuando se selecciona **Persistencia de estado automática** , el desarrollador debe crear una tabla de estado según los requisitos descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5a20a-160">When **Automatic state persistence** is selected, the developer must create a state table according to the requirements listed above.</span></span>  
  
 <span data-ttu-id="5a20a-161">Esto solo está disponible si se ha seleccionado **Persistencia de estado automática** y es un parámetro obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5a20a-161">This is available only if **Automatic state persistence** is selected and it is a required parameter.</span></span>  
  
 <span data-ttu-id="5a20a-162">**Nombre del estado**</span><span class="sxs-lookup"><span data-stu-id="5a20a-162">**State name**</span></span>  
 <span data-ttu-id="5a20a-163">Escriba un nombre para asociar al estado CDC persistente.</span><span class="sxs-lookup"><span data-stu-id="5a20a-163">Type a name to associate with the persistent CDC state.</span></span> <span data-ttu-id="5a20a-164">Los paquetes de carga completa y CDC que funcionan con el mismo contexto CDC especificarán un nombre común para el estado.</span><span class="sxs-lookup"><span data-stu-id="5a20a-164">The full load and CDC packages that work with the same CDC context will specify a common state name.</span></span> <span data-ttu-id="5a20a-165">Este nombre se usa para buscar la fila de estado en la tabla de estado.</span><span class="sxs-lookup"><span data-stu-id="5a20a-165">This name is used for looking up the state row in the state table</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a20a-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a20a-166">See Also</span></span>  
 [<span data-ttu-id="5a20a-167">Propiedades personalizadas de la tarea de control CDC</span><span class="sxs-lookup"><span data-stu-id="5a20a-167">CDC Control Task Custom Properties</span></span>](control-flow/cdc-control-task-custom-properties.md)  
  
  