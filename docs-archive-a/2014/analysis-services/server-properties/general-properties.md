---
title: Propiedades generales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- IdleConnectionTimeout property
- InstanceVisible property
- TempDir property
- AdminTimeout property
- MinIdleSessionTimeout property
- MaxIdleSessionTimeout property
- IdleOrphanSessionTimeout property
- BackupDir property
- CommitTimeout property
- ExternalCommandTimeout property
- Enabled property
- ForceCommitTimeout property
- Port property
- CoordinatorShutdownMode property
- ServerTimeout property
- AllowedBrowsingFolders property
- CoordinatorCancelCount property
- DataDir property
- CoordinatorQueryMaxThreads property
- CoordinatorExecutionMode property
- ExternalConnectionTimeout property
- CollationName property
- EnableFast1033Locale property
- CoordinatorBuildMaxThreads property
- Language property
- StatisticsStoreSize property
- RepositoryConnectionString property
ms.assetid: 88a8117c-396a-469f-a62d-c6f262504021
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca746a1bb57e84cf0f6a8f47622b118c7180eb1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752397"
---
# <a name="general-properties"></a><span data-ttu-id="73605-102">Propiedades generales</span><span class="sxs-lookup"><span data-stu-id="73605-102">General Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="73605-103">admite las propiedades de servidor descritas en las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="73605-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="73605-104">En este tema se documentan las propiedades de servidor en el archivo msmdsrv.ini que no se incluyen de otro modo en una sección concreta, como Seguridad, Red o ThreadPool.</span><span class="sxs-lookup"><span data-stu-id="73605-104">This topic documents those server properties in the msmdsrv.ini file that are not otherwise included in a specific section, such as Security, Network, or ThreadPool.</span></span> <span data-ttu-id="73605-105">Para obtener más información sobre las propiedades de servidor adicionales y cómo establecerlas, vea [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="73605-105">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="73605-106">**Se aplica a:** modo de servidor multidimensional y tabular, a menos que se especifique lo contrario</span><span class="sxs-lookup"><span data-stu-id="73605-106">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="73605-107">Categoría no específica</span><span class="sxs-lookup"><span data-stu-id="73605-107">Non-Specific Category</span></span>  
 `AdminTimeout`  
 <span data-ttu-id="73605-108">Propiedad de entero de 32 bits con signo que define el tiempo de espera del administrador, en segundos.</span><span class="sxs-lookup"><span data-stu-id="73605-108">A signed 32-bit integer property that defines the administrator timeout in seconds.</span></span> <span data-ttu-id="73605-109">Se trata de una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73605-109">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="73605-110">El valor predeterminado de esta propiedad es cero (0), que indica que no hay tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="73605-110">The default value for this property is zero (0), which indicates there is no timeout.</span></span>  
  
 `AllowedBrowsingFolders`  
 <span data-ttu-id="73605-111">Propiedad de cadena que especifica en una lista delimitada las carpetas que se pueden examinar al guardar, abrir y buscar archivos en los cuadros de diálogo de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="73605-111">A string property that specifies in a delimited list the folders that can be browsed when saving, opening, and finding files in Analysis Services dialog boxes.</span></span> <span data-ttu-id="73605-112">La cuenta de servicio de Analysis Services debe tener permisos de lectura y escritura en cualquiera de las carpetas que agregue a la lista.</span><span class="sxs-lookup"><span data-stu-id="73605-112">The Analysis Services service account must have read and write permissions to any folders that you add to the list.</span></span>  
  
 `BackupDir`  
 <span data-ttu-id="73605-113">Propiedad de cadena que identifica el nombre del directorio en el que se almacenan los archivos de copia de seguridad de forma predeterminada, en caso de que no se especifique una ruta de acceso como parte del comando de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="73605-113">A string property that identifies the name of the directory where backup files are stored by default, in the event a path is not specified as part of the Backup command.</span></span>  
  
 `CollationName`  
 <span data-ttu-id="73605-114">Propiedad de cadena que identifica la intercalación del servidor.</span><span class="sxs-lookup"><span data-stu-id="73605-114">A string property that identifies the server collation.</span></span> <span data-ttu-id="73605-115">Para más información, vea [Idiomas e intercalaciones &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="73605-115">For more information, see [Languages and Collations &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span></span>  
  
 `CommitTimeout`  
 <span data-ttu-id="73605-116">Propiedad de entero que especifica cuánto tiempo (en milisegundos) debe esperar el servidor para adquirir un bloqueo de escritura con el fin de confirmar una transacción.</span><span class="sxs-lookup"><span data-stu-id="73605-116">An integer property that specifies how long (in milliseconds) the server will wait to acquire a write lock for the purpose of committing a transaction.</span></span> <span data-ttu-id="73605-117">A menudo, es necesario un período de espera debido a que el servidor tiene que esperar a que se liberen otros bloqueos para poder establecer un bloqueo de escritura que confirme la transacción.</span><span class="sxs-lookup"><span data-stu-id="73605-117">A waiting period is often required because the server must wait for other locks to be released before it can take a write lock that commits the transaction.</span></span>  
  
 <span data-ttu-id="73605-118">El valor predeterminado para esta propiedad es cero (0), lo que indica que el servidor esperará de forma indefinida.</span><span class="sxs-lookup"><span data-stu-id="73605-118">The default value for this property is zero (0), which indicates that the server will wait indefinitely.</span></span> <span data-ttu-id="73605-119">Para más información sobre las propiedades relacionadas con los bloqueos, vea la [Guía de operaciones de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="73605-119">For more information about lock-related properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorBuildMaxThreads`  
 <span data-ttu-id="73605-120">Propiedad de entero de 32 bits con signo que define el máximo de subprocesos asignados para generar índices de partición.</span><span class="sxs-lookup"><span data-stu-id="73605-120">A signed 32-bit integer property that defines the maximum number of threads allocated to building partition indexes.</span></span> <span data-ttu-id="73605-121">Aumente este valor para acelerar la indización de particiones, a costa de usar memoria.</span><span class="sxs-lookup"><span data-stu-id="73605-121">Increase this value in order to speed-up partition indexing, at the cost of memory usage.</span></span> <span data-ttu-id="73605-122">Para obtener más información acerca de esta propiedad, vea la [Guía de operaciones de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="73605-122">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorCancelCount`  
 <span data-ttu-id="73605-123">Una propiedad de entero de 32 bits con signo que define la frecuencia con la que el servidor debería comprobar si se ha producido un evento Cancel (según el recuento interno de iteraciones).</span><span class="sxs-lookup"><span data-stu-id="73605-123">A signed 32-bit integer property that defines how frequently the server should check whether a Cancel event occurred (based on internal iteration count).</span></span> <span data-ttu-id="73605-124">Disminuya este número para comprobar Cancel más frecuentemente, a expensas del rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="73605-124">Decrease this number in order to check for Cancel more frequently, at the expense of general performance.</span></span>  
  
 <span data-ttu-id="73605-125">`CoordinatorCancelCount` se omite en modo de servidor tabular.</span><span class="sxs-lookup"><span data-stu-id="73605-125">`CoordinatorCancelCount` is ignored in tabular server mode.</span></span>  
  
 `CoordinatorExecutionMode`  
 <span data-ttu-id="73605-126">Una propiedad de entero de 32 bits con signo que define el máximo de operaciones paralelas que intentará realizar el servidor, incluidas las operaciones de consulta y procesamiento.</span><span class="sxs-lookup"><span data-stu-id="73605-126">A signed 32-bit integer property that defines the maximum number of parallel operations the server will attempt, including processing and querying operations.</span></span> <span data-ttu-id="73605-127">Cero (0) indica que el servidor decidirá, según un algoritmo interno.</span><span class="sxs-lookup"><span data-stu-id="73605-127">Zero (0) indicates that the server will decide, based on an internal algorithm.</span></span> <span data-ttu-id="73605-128">Un número positivo indica el máximo de operaciones en total.</span><span class="sxs-lookup"><span data-stu-id="73605-128">A positive number indicates the maximum number of operations in total.</span></span> <span data-ttu-id="73605-129">Un número negativo, con el signo invertido, indica el máximo de operaciones por procesador.</span><span class="sxs-lookup"><span data-stu-id="73605-129">A negative number, with the sign reversed, indicates the maximum number of operations per processor.</span></span>  
  
 <span data-ttu-id="73605-130">`CoordinatorExecutionMode` se omite en modo de servidor tabular.</span><span class="sxs-lookup"><span data-stu-id="73605-130">`CoordinatorExecutionMode` is ignored in tabular server mode.</span></span>  
  
 <span data-ttu-id="73605-131">El valor predeterminado para esta propiedad es -4, que indica que el servidor está limitado a 4 operaciones paralelas por procesador.</span><span class="sxs-lookup"><span data-stu-id="73605-131">The default value for this property is -4, which indicates the server is limited to 4 parallel operations per processor.</span></span> <span data-ttu-id="73605-132">Para obtener más información acerca de esta propiedad, vea la [Guía de operaciones de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="73605-132">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorQueryMaxThreads`  
 <span data-ttu-id="73605-133">Una propiedad de entero de 32 bits con signo que define el máximo de subprocesos por segmento de partición durante una resolución de consulta.</span><span class="sxs-lookup"><span data-stu-id="73605-133">A signed 32-bit integer property that defines the maximum number of threads per partition segment during query resolution.</span></span> <span data-ttu-id="73605-134">Cuanto menor sea el número de usuarios simultáneos, mayor podrá ser este valor, a expensas de la memoria.</span><span class="sxs-lookup"><span data-stu-id="73605-134">The fewer the number of concurrent users, the higher this value can be, at the cost of memory.</span></span> <span data-ttu-id="73605-135">Por el contrario, puede ser necesario disminuirlo si hay un gran número de usuarios simultáneos.</span><span class="sxs-lookup"><span data-stu-id="73605-135">Conversely, it may need to be lowered if there are a large number of concurrent users.</span></span>  
  
 `CoordinatorShutdownMode`  
 <span data-ttu-id="73605-136">Una propiedad booleana que define el modo de apagado del coordinador.</span><span class="sxs-lookup"><span data-stu-id="73605-136">A Boolean property that defines coordinator shutdown mode.</span></span> <span data-ttu-id="73605-137">Se trata de una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73605-137">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataDir`  
 <span data-ttu-id="73605-138">Una propiedad de cadena que identifica el nombre del directorio en el que se almacenan los datos.</span><span class="sxs-lookup"><span data-stu-id="73605-138">A string property that identifies the name of the directory where data is stored.</span></span>  
  
 `DeploymentMode`  
 <span data-ttu-id="73605-139">Determina el contexto operativo de una instancia de servidor de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="73605-139">Determines the operational context of an Analysis Services server instance.</span></span> <span data-ttu-id="73605-140">Esta propiedad se denomina ' modo de servidor ' en los cuadros de diálogo, los mensajes y la documentación.</span><span class="sxs-lookup"><span data-stu-id="73605-140">This property is referred to as 'server mode' in dialog boxes, messages, and documentation.</span></span> <span data-ttu-id="73605-141">Esta propiedad la configura el programa de instalación de SQL Server en función del modo de servidor que se seleccione al instalar Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="73605-141">This property is configured by SQL Server Setup based on the server mode you selected when installing Analysis Services.</span></span> <span data-ttu-id="73605-142">Esta propiedad debe considerarse interna únicamente y siempre se usa el valor especificado por el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="73605-142">This property should be considered internal only, always using the value specified by Setup.</span></span>  
  
 <span data-ttu-id="73605-143">Los valores válidos de esta propiedad incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="73605-143">Valid values for this property include the following:</span></span>  
  
|<span data-ttu-id="73605-144">Value</span><span class="sxs-lookup"><span data-stu-id="73605-144">Value</span></span>|<span data-ttu-id="73605-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="73605-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="73605-146">0</span><span class="sxs-lookup"><span data-stu-id="73605-146">0</span></span>|<span data-ttu-id="73605-147">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="73605-147">This is the default value.</span></span> <span data-ttu-id="73605-148">Especifica el modo multidimensional, utilizado para dar servicio a las bases de datos multidimensionales que usan el almacenamiento MOLAP, HOLAP y ROLAP, así como a los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="73605-148">It specifies multidimensional mode, used to service multidimensional databases that use MOLAP, HOLAP, and ROLAP storage, as well as data mining models.</span></span>|  
|<span data-ttu-id="73605-149">1</span><span class="sxs-lookup"><span data-stu-id="73605-149">1</span></span>|<span data-ttu-id="73605-150">Especifica las instancias de Analysis Services que se instalaron como parte de una implementación de PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="73605-150">Specifies Analysis Services instances that were installed as part of a PowerPivot for SharePoint deployment.</span></span> <span data-ttu-id="73605-151">No cambie la propiedad del modo de implementación de la instancia de Analysis Services que forma parte de una instalación de PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="73605-151">Do not change the deployment mode property of Analysis Services instance that is part of a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="73605-152">Los datos PowerPivot dejarán de ejecutarse en el servidor si cambia el modo.</span><span class="sxs-lookup"><span data-stu-id="73605-152">PowerPivot data will no longer run on the server if you change the mode.</span></span>|  
|<span data-ttu-id="73605-153">2</span><span class="sxs-lookup"><span data-stu-id="73605-153">2</span></span>|<span data-ttu-id="73605-154">Especifica el modo tabular empleado para hospedar las bases de datos de modelos tabulares que utilizan el almacenamiento en memoria o el almacenamiento DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="73605-154">Specifies Tabular mode used for hosting tabular model databases that use in-memory storage or DirectQuery storage.</span></span>|  
  
 <span data-ttu-id="73605-155">Cada modo excluye a los demás.</span><span class="sxs-lookup"><span data-stu-id="73605-155">Each mode is exclusive of the other.</span></span> <span data-ttu-id="73605-156">Un servidor configurado para el modo tabular no podrá ejecutar las bases de datos de Analysis Services que contengan cubos y dimensiones.</span><span class="sxs-lookup"><span data-stu-id="73605-156">A server that is configured for tabular mode cannot run Analysis Services databases that contain cubes and dimensions.</span></span> <span data-ttu-id="73605-157">Si el hardware del equipo subyacente puede admitirlo, puede instalar varias instancias de Analysis Services en el mismo equipo y configurar cada instancia para utilizar otro modo.</span><span class="sxs-lookup"><span data-stu-id="73605-157">If the underlying computer hardware can support it, you can install multiple instances of Analysis Services on the same computer and configure each instance to use a different deployment mode.</span></span> <span data-ttu-id="73605-158">Recuerde que Analysis Services es una aplicación que usa muchos recursos.</span><span class="sxs-lookup"><span data-stu-id="73605-158">Remember that Analysis Services is a resource intensive application.</span></span> <span data-ttu-id="73605-159">La implementación de varias instancias en el mismo sistema solo se recomienda para los servidores de tecnología avanzada.</span><span class="sxs-lookup"><span data-stu-id="73605-159">Deploying multiple instances on the same system is recommended only for high-end servers.</span></span>  
  
 `EnableFast1033Locale`  
 <span data-ttu-id="73605-160">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73605-160">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ExternalCommandTimeout`  
 <span data-ttu-id="73605-161">Propiedad de entero que define el tiempo de espera, en segundos, para comandos emitidos a servidores externos, incluidos los orígenes de datos relacionales y los servidores de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] externos.</span><span class="sxs-lookup"><span data-stu-id="73605-161">An integer property that defines the timeout, in seconds, for commands issued to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="73605-162">El valor predeterminado para esta propiedad es 3600 (segundos).</span><span class="sxs-lookup"><span data-stu-id="73605-162">The default value for this property is 3600 (seconds).</span></span>  
  
 `ExternalConnectionTimeout`  
 <span data-ttu-id="73605-163">Propiedad de entero que define el tiempo de espera, en segundos, para crear conexiones con servidores externos, incluidos los orígenes de datos relacionales y los servidores de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] externos.</span><span class="sxs-lookup"><span data-stu-id="73605-163">An integer property that defines the timeout, in seconds, for creating connections to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span> <span data-ttu-id="73605-164">Esta propiedad se omite si se especifica un tiempo de espera de conexión en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="73605-164">This property is ignored if a connection timeout is specified on the connection string.</span></span>  
  
 <span data-ttu-id="73605-165">El valor predeterminado para esta propiedad es 60 (segundos).</span><span class="sxs-lookup"><span data-stu-id="73605-165">The default value for this property is 60 (seconds).</span></span>  
  
 `ForceCommitTimeout`  
 <span data-ttu-id="73605-166">Propiedad de entero que especifica cuánto tiempo, en milisegundos, debe esperar una operación de confirmación de escritura antes de cancelar otros comandos que preceden al comando actual, incluyendo las consultas en curso.</span><span class="sxs-lookup"><span data-stu-id="73605-166">An integer property that specifies how long, in milliseconds, a write commit operation should wait before canceling other commands that preceded the current command, including queries in progress.</span></span> <span data-ttu-id="73605-167">Esto permite que la transacción de confirmación continúe y cancele las operaciones con una prioridad más baja, como las consultas.</span><span class="sxs-lookup"><span data-stu-id="73605-167">This allows the commit transaction to proceed by canceling lower priority operations, such as queries.</span></span>  
  
 <span data-ttu-id="73605-168">El valor predeterminado de esta propiedad es 30 segundos (30000 milisegundos), lo que indica que otros comandos no se verán forzados a agotar su tiempo hasta que la transacción de confirmación haya esperado 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="73605-168">The default value for this property is 30 seconds (30000 milliseconds), which indicates that other commands will not be forced to timeout until the commit transaction has been waiting for 30 seconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73605-169">Las consultas y procesos cancelados por este evento generarán el mensaje de error siguiente: "`Server: The operation has been cancelled`"</span><span class="sxs-lookup"><span data-stu-id="73605-169">Queries and processes cancelled by this event will report the following error message: "`Server: The operation has been cancelled`"</span></span>  
  
 <span data-ttu-id="73605-170">Para obtener más información acerca de esta propiedad, vea la [Guía de operaciones de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="73605-170">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="73605-171">`ForceCommitTimeout` se aplica a los comandos de procesamiento de cubos y a las operaciones de reescritura.</span><span class="sxs-lookup"><span data-stu-id="73605-171">`ForceCommitTimeout` applies to cube processing commands and to writeback operations.</span></span>  
  
 `IdleConnectionTimeout`  
 <span data-ttu-id="73605-172">Propiedad de entero que especifica un tiempo de espera, en segundos, para las conexiones que están inactivas.</span><span class="sxs-lookup"><span data-stu-id="73605-172">An integer property that specifies a timeout, in seconds, for connections that are inactive.</span></span>  
  
 <span data-ttu-id="73605-173">El valor predeterminado para esta propiedad es cero (0), que indica que las conexiones inactivas no agotarán el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="73605-173">The default value for this property is zero (0), which indicates that idle connections will not be timed out.</span></span>  
  
 `IdleOrphanSessionTimeout`  
 <span data-ttu-id="73605-174">Propiedad de entero que define, en segundos, cuánto tiempo se conservarán las sesiones huérfanas en la memoria del servidor.</span><span class="sxs-lookup"><span data-stu-id="73605-174">An integer property that defines how long, in seconds, orphaned sessions will be retained in server memory.</span></span> <span data-ttu-id="73605-175">Una sesión huérfana es aquella que ya no tiene una conexión asociada.</span><span class="sxs-lookup"><span data-stu-id="73605-175">An orphaned session is one that no longer has an associated connection.</span></span> <span data-ttu-id="73605-176">El valor predeterminado es 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="73605-176">The default is 120 seconds.</span></span>  
  
 `InstanceVisible`  
 <span data-ttu-id="73605-177">Propiedad booleana que indica si la instancia del servidor está visible para detectar solicitudes de instancia del servicio SQL Server Browser.</span><span class="sxs-lookup"><span data-stu-id="73605-177">A Boolean property that indicates whether the server instance is visible to discover instance requests from SQL Server Browser service.</span></span> <span data-ttu-id="73605-178">El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="73605-178">The default is True.</span></span> <span data-ttu-id="73605-179">Si lo establece en false, la instancia no está visible para SQL Server Browser.</span><span class="sxs-lookup"><span data-stu-id="73605-179">If you set it to false, the instance is not visible to SQL Server Browser.</span></span>  
  
 `Language`  
 <span data-ttu-id="73605-180">Propiedad de cadena que define el idioma, incluidos los mensajes de error y el formato de números.</span><span class="sxs-lookup"><span data-stu-id="73605-180">A string property that defines the language, including error messages and number formatting.</span></span> <span data-ttu-id="73605-181">Esta propiedad invalida la propiedad CollationName.</span><span class="sxs-lookup"><span data-stu-id="73605-181">This property overrides the CollationName property.</span></span>  
  
 <span data-ttu-id="73605-182">El valor predeterminado para esta propiedad es en blanco, que indica que la propiedad CollationName define el idioma.</span><span class="sxs-lookup"><span data-stu-id="73605-182">The default value for this property is blank, which indicates that the CollationName property defines the language.</span></span>  
  
 `LogDir`  
 <span data-ttu-id="73605-183">Una propiedad de cadena que identifica el nombre del directorio que contiene los registros del servidor.</span><span class="sxs-lookup"><span data-stu-id="73605-183">A string property that identifies the name of the directory that contains server logs.</span></span> <span data-ttu-id="73605-184">Esta propiedad solo se aplica cuando se utilizan archivos de disco para realizar el registro, a diferencia de cuando se utilizan tablas de base de datos (comportamiento predeterminado).</span><span class="sxs-lookup"><span data-stu-id="73605-184">This property only applies when disk files are used for logging, as opposed to database tables (the default behavior).</span></span>  
  
 `MaxIdleSessionTimeout`  
 <span data-ttu-id="73605-185">Propiedad de entero que define el tiempo de espera máximo de una sesión inactiva, en segundos.</span><span class="sxs-lookup"><span data-stu-id="73605-185">An integer property that defines the maximum idle session timeout, in seconds.</span></span> <span data-ttu-id="73605-186">El valor predeterminado es cero (0), lo que indica que nunca se agota el tiempo de espera de las sesiones. Sin embargo, las sesiones inactivas se quitarán si el servidor está bajo restricciones de recursos.</span><span class="sxs-lookup"><span data-stu-id="73605-186">The default is zero (0), indicating that sessions are never timed out. However, idle sessions will still be removed if the server is under resource constraints.</span></span>  
  
 `MinIdleSessionTimeout`  
 <span data-ttu-id="73605-187">Propiedad de entero que define el tiempo mínimo, en segundos, que las sesiones inactivas tardarán en agotar el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="73605-187">An integer property that defines the minimum time, in seconds, that idle sessions will timeout.</span></span> <span data-ttu-id="73605-188">El valor predeterminado es 2700 segundos.</span><span class="sxs-lookup"><span data-stu-id="73605-188">The default is 2700 seconds.</span></span> <span data-ttu-id="73605-189">Después de que expire este tiempo, el servidor puede finalizar la sesión inactiva, pero solo lo hará a medida que se necesite memoria.</span><span class="sxs-lookup"><span data-stu-id="73605-189">After this time expires, the server is permitted to end the idle session, but will only do so as memory is needed.</span></span>  
  
 `Port`  
 <span data-ttu-id="73605-190">Propiedad de entero que define el número de puerto en el que el servidor escuchará las conexiones de los clientes.</span><span class="sxs-lookup"><span data-stu-id="73605-190">An integer property that defines the port number on which server will listen for client connections.</span></span> <span data-ttu-id="73605-191">Si no está establecida, el servidor encontrará de forma dinámica el primer puerto no usado.</span><span class="sxs-lookup"><span data-stu-id="73605-191">If not set, server dynamically finds first unused port.</span></span>  
  
 <span data-ttu-id="73605-192">El valor predeterminado para esta propiedad es cero (0), que a su vez establece el valor predeterminado en el puerto 2383.</span><span class="sxs-lookup"><span data-stu-id="73605-192">The default value for this property is zero (0), which in turn defaults to port 2383.</span></span> <span data-ttu-id="73605-193">Para obtener más información acerca de la configuración de puertos, vea [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span><span class="sxs-lookup"><span data-stu-id="73605-193">For more information about port configuration, see [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span></span>  
  
 `ServerTimeout`  
 <span data-ttu-id="73605-194">Entero que define el tiempo de espera, en segundos, para las consultas.</span><span class="sxs-lookup"><span data-stu-id="73605-194">An integer that defines the timeout, in seconds, for queries.</span></span> <span data-ttu-id="73605-195">El valor predeterminado es de 3600 segundos (o 60 minutos).</span><span class="sxs-lookup"><span data-stu-id="73605-195">The default is 3600 seconds (or 60 minutes).</span></span> <span data-ttu-id="73605-196">El valor cero (0) especifica que no se agotará el tiempo de espera de las consultas.</span><span class="sxs-lookup"><span data-stu-id="73605-196">Zero (0) specifies that no queries will timeout.</span></span>  
  
 `TempDir`  
 <span data-ttu-id="73605-197">Propiedad de cadena que especifica la ubicación de almacenamiento de los archivos temporales utilizados durante las operaciones de procesamiento y restauración, entre otras.</span><span class="sxs-lookup"><span data-stu-id="73605-197">A string property that specifies the location for storing temporary files used during processing, restoring, and other operations.</span></span> <span data-ttu-id="73605-198">El valor predeterminado de esta propiedad viene determinado por la configuración.</span><span class="sxs-lookup"><span data-stu-id="73605-198">The default value for this property is determined by setup.</span></span> <span data-ttu-id="73605-199">Si no se especifica, el valor predeterminado es el directorio Data.</span><span class="sxs-lookup"><span data-stu-id="73605-199">If not specified, the default is the Data directory.</span></span>  
  
## <a name="requestprioritization-category"></a><span data-ttu-id="73605-200">Categoría RequestPrioritization</span><span class="sxs-lookup"><span data-stu-id="73605-200">RequestPrioritization Category</span></span>  
 `Enabled`  
 <span data-ttu-id="73605-201">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73605-201">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `StatisticsStoreSize`  
 <span data-ttu-id="73605-202">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73605-202">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73605-203">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73605-203">See Also</span></span>  
 <span data-ttu-id="73605-204">[Configurar las propiedades del servidor en Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="73605-204">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="73605-205">Determinar el modo de servidor de una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="73605-205">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
