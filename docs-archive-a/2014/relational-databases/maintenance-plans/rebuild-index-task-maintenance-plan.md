---
title: Tarea Volver a generar índice (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reindex.f1
- reindex
helpviewer_keywords:
- Rebuild Index Task dialog box
ms.assetid: 33e2940b-139f-4563-b0cb-5683f08bd879
author: rothja
ms.author: jroth
ms.openlocfilehash: bc9d7c85a72c34cee1ef7af8cb4b4f25f918a3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671513"
---
# <a name="rebuild-index-task-maintenance-plan"></a><span data-ttu-id="14511-102">Tarea Volver a generar índice (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="14511-102">Rebuild Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="14511-103">Use el cuadro de diálogo **Tarea Volver a generar índice** para volver a crear los índices de las tablas de la base de datos con un nuevo factor de relleno.</span><span class="sxs-lookup"><span data-stu-id="14511-103">Use the **Rebuild Index Task** dialog to re-create the indexes on the tables in the database with a new fill factor.</span></span> <span data-ttu-id="14511-104">El factor de relleno determina la cantidad de espacio vacío de cada una de las páginas del índice, para adaptarse a una futura expansión.</span><span class="sxs-lookup"><span data-stu-id="14511-104">The fill factor determines the amount of empty space on each page in the index, to accommodate future expansion.</span></span> <span data-ttu-id="14511-105">Al agregar datos a la tabla, el espacio disponible se llena, ya que no se conserva el factor de relleno.</span><span class="sxs-lookup"><span data-stu-id="14511-105">As data is added to the table, the free space fills because the fill factor is not maintained.</span></span> <span data-ttu-id="14511-106">Al reorganizar las páginas de datos y de índices, puede restablecer el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="14511-106">Reorganizing data and index pages can re-establish the free space.</span></span>  
  
 <span data-ttu-id="14511-107">La **tarea Volver a generar índice** usa la instrucción ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="14511-107">The **Rebuild Index Task** uses the ALTER INDEX statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="14511-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="14511-108">Options</span></span>  
 <span data-ttu-id="14511-109">**Connection**</span><span class="sxs-lookup"><span data-stu-id="14511-109">**Connection**</span></span>  
 <span data-ttu-id="14511-110">Seleccione la conexión al servidor que va a utilizar para la realización de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="14511-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="14511-111">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="14511-111">**New**</span></span>  
 <span data-ttu-id="14511-112">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="14511-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="14511-113">El cuadro de diálogo **Nueva conexión** se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="14511-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="14511-114">**Bases de datos**</span><span class="sxs-lookup"><span data-stu-id="14511-114">**Databases**</span></span>  
 <span data-ttu-id="14511-115">Especifique las bases de datos a las que afecta esta tarea.</span><span class="sxs-lookup"><span data-stu-id="14511-115">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="14511-116">**Todas las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="14511-116">**All databases**</span></span>  
  
     <span data-ttu-id="14511-117">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a excepción de tempdb.</span><span class="sxs-lookup"><span data-stu-id="14511-117">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="14511-118">**Todas las bases de datos del sistema**</span><span class="sxs-lookup"><span data-stu-id="14511-118">**All system databases**</span></span>  
  
     <span data-ttu-id="14511-119">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a excepción de tempdb.</span><span class="sxs-lookup"><span data-stu-id="14511-119">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="14511-120">No se ejecutarán tareas de mantenimiento en las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="14511-120">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="14511-121">**Todas las bases de datos de usuario**</span><span class="sxs-lookup"><span data-stu-id="14511-121">**All user databases**</span></span>  
  
     <span data-ttu-id="14511-122">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="14511-122">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="14511-123">No se ejecutarán tareas de mantenimiento en las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14511-123">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="14511-124">**Las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="14511-124">**These specific databases**</span></span>  
  
     <span data-ttu-id="14511-125">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento únicamente en las bases de datos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="14511-125">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="14511-126">Si elige esta opción, deberá seleccionar al menos una base de datos de la lista.</span><span class="sxs-lookup"><span data-stu-id="14511-126">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="14511-127">Los planes de mantenimiento solo se ejecutan en bases de datos con un nivel de compatibilidad de 80 o superior.</span><span class="sxs-lookup"><span data-stu-id="14511-127">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="14511-128">Las bases de datos con un nivel de compatibilidad de 70 o inferior no se muestran.</span><span class="sxs-lookup"><span data-stu-id="14511-128">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="14511-129">**Object**</span><span class="sxs-lookup"><span data-stu-id="14511-129">**Object**</span></span>  
 <span data-ttu-id="14511-130">Limite la cuadrícula **Selección** para mostrar tablas, vistas o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="14511-130">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="14511-131">**Selección**</span><span class="sxs-lookup"><span data-stu-id="14511-131">**Selection**</span></span>  
 <span data-ttu-id="14511-132">Especifique las tablas o índices que se ven afectados por esta tarea.</span><span class="sxs-lookup"><span data-stu-id="14511-132">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="14511-133">No estará disponible cuando se seleccione **Tablas y vistas** en el cuadro Objeto.</span><span class="sxs-lookup"><span data-stu-id="14511-133">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="14511-134">**Reorganizar páginas con la cantidad predeterminada de espacio disponible**</span><span class="sxs-lookup"><span data-stu-id="14511-134">**Reorganize pages with the default amount of free space**</span></span>  
 <span data-ttu-id="14511-135">Quita los índices de las tablas de la base de datos y vuelve a crearlos con el factor de relleno que se especificó al crear los índices.</span><span class="sxs-lookup"><span data-stu-id="14511-135">Drop the indexes on the tables in the database and re-create them with the fill factor that was specified when the indexes were created.</span></span>  
  
 <span data-ttu-id="14511-136">**Cambiar el porcentaje de espacio disponible por página a**</span><span class="sxs-lookup"><span data-stu-id="14511-136">**Change free space per page percentage to**</span></span>  
 <span data-ttu-id="14511-137">Quita los índices de las tablas de la base de datos y vuelve a crearlos con un nuevo factor de relleno calculado automáticamente, de forma que reserva la cantidad de espacio disponible especificada en las páginas de índice.</span><span class="sxs-lookup"><span data-stu-id="14511-137">Drop the indexes on the tables in the database and re-create them with a new, automatically calculated fill factor, thereby reserving the specified amount of free space on the index pages.</span></span> <span data-ttu-id="14511-138">Cuanto mayor sea el porcentaje, más espacio disponible se reservará en las páginas de índice y mayor tamaño tendrá el índice.</span><span class="sxs-lookup"><span data-stu-id="14511-138">The higher the percentage, the more free space is reserved on the index pages, and the larger the index grows.</span></span> <span data-ttu-id="14511-139">Los valores válidos son de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="14511-139">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="14511-140">**Ordenar resultados de tempdb**</span><span class="sxs-lookup"><span data-stu-id="14511-140">**Sort results in tempdb**</span></span>  
 <span data-ttu-id="14511-141">Use la `SORT_IN_TEMPDB` opción, que determina dónde se almacenan temporalmente los resultados de ordenación intermedios generados durante la creación del índice.</span><span class="sxs-lookup"><span data-stu-id="14511-141">Use the `SORT_IN_TEMPDB`option, which determines where the intermediate sort results, generated during index creation, are temporarily stored.</span></span> <span data-ttu-id="14511-142">En caso de que sea necesario realizar una operación de ordenación o de que esta pueda realizarse en la memoria, se omitirá la opción `SORT_IN_TEMPDB`.</span><span class="sxs-lookup"><span data-stu-id="14511-142">If a sort operation is not required, or if the sort can be performed in memory, the `SORT_IN_TEMPDB`option is ignored.</span></span>  
  
 <span data-ttu-id="14511-143">**Mantener el índice en línea al volver a indizar**</span><span class="sxs-lookup"><span data-stu-id="14511-143">**Keep index online while reindexing**</span></span>  
 <span data-ttu-id="14511-144">Utilice la opción `ONLINE` para permitir a los usuarios obtener acceso a los datos de la tabla subyacente o del índice clúster y a todos los índices no clúster asociados durante las operaciones de índice.</span><span class="sxs-lookup"><span data-stu-id="14511-144">Use the `ONLINE` option which allows users to access the underlying table or clustered index data and any associated nonclustered indexes during index operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14511-145">Las operaciones de índices en línea no están disponibles en todas las ediciones de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14511-145">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="14511-146">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="14511-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="14511-147">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="14511-147">**View T-SQL**</span></span>  
 <span data-ttu-id="14511-148">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="14511-148">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14511-149">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="14511-149">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="14511-150">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="14511-150">New Connection Dialog Box</span></span>  
 <span data-ttu-id="14511-151">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="14511-151">**Connection name**</span></span>  
 <span data-ttu-id="14511-152">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="14511-152">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="14511-153">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="14511-153">**Select or enter a server name**</span></span>  
 <span data-ttu-id="14511-154">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="14511-154">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="14511-155">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="14511-155">**Refresh**</span></span>  
 <span data-ttu-id="14511-156">Actualiza la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="14511-156">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="14511-157">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="14511-157">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="14511-158">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="14511-158">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="14511-159">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="14511-159">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="14511-160">Se conecta a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="14511-160">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="14511-161">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="14511-161">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="14511-162">Se conecta a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14511-162">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="14511-163">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="14511-163">This option is not available.</span></span>  
  
 <span data-ttu-id="14511-164">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="14511-164">**User name**</span></span>  
 <span data-ttu-id="14511-165">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="14511-165">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="14511-166">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="14511-166">This option is not available.</span></span>  
  
 <span data-ttu-id="14511-167">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="14511-167">**Password**</span></span>  
 <span data-ttu-id="14511-168">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="14511-168">Provide a password to use when authenticating.</span></span> <span data-ttu-id="14511-169">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="14511-169">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14511-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14511-170">See Also</span></span>  
 <span data-ttu-id="14511-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14511-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="14511-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14511-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span></span>  
 <span data-ttu-id="14511-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14511-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="14511-174">[Opción SORT_IN_TEMPDB para índices](../indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="14511-174">[SORT_IN_TEMPDB Option For Indexes](../indexes/indexes.md) </span></span>  
 <span data-ttu-id="14511-175">[Directrices para operaciones de índices en línea](../indexes/guidelines-for-online-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="14511-175">[Guidelines for Online Index Operations](../indexes/guidelines-for-online-index-operations.md) </span></span>  
 <span data-ttu-id="14511-176">[Cómo funcionan las operaciones de índice en línea](../indexes/how-online-index-operations-work.md) </span><span class="sxs-lookup"><span data-stu-id="14511-176">[How Online Index Operations Work](../indexes/how-online-index-operations-work.md) </span></span>  
 [<span data-ttu-id="14511-177">Realizar operaciones de índice en línea</span><span class="sxs-lookup"><span data-stu-id="14511-177">Perform Index Operations Online</span></span>](../indexes/perform-index-operations-online.md)  
  
  
