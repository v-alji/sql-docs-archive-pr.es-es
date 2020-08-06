---
title: MSSQLSERVER_1418 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1418 (Database Engine error)
ms.assetid: 6e9c7241-0201-44e0-9f8b-b3c4e293f0f6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1fcac03f044aacce5e907824862eb589c97a07d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747014"
---
# <a name="mssqlserver_1418"></a><span data-ttu-id="ceb8d-102">MSSQLSERVER_1418</span><span class="sxs-lookup"><span data-stu-id="ceb8d-102">MSSQLSERVER_1418</span></span>
    
## <a name="details"></a><span data-ttu-id="ceb8d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ceb8d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ceb8d-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="ceb8d-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="ceb8d-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ceb8d-105">Event ID</span></span>|<span data-ttu-id="ceb8d-106">1418</span><span class="sxs-lookup"><span data-stu-id="ceb8d-106">1418</span></span>|  
|<span data-ttu-id="ceb8d-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="ceb8d-107">Event Source</span></span>|<span data-ttu-id="ceb8d-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ceb8d-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ceb8d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ceb8d-109">Component</span></span>|<span data-ttu-id="ceb8d-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ceb8d-110">SQLEngine</span></span>|  
|<span data-ttu-id="ceb8d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ceb8d-111">Symbolic Name</span></span>|<span data-ttu-id="ceb8d-112">DBM_PARTNERNOTFOUND</span><span class="sxs-lookup"><span data-stu-id="ceb8d-112">DBM_PARTNERNOTFOUND</span></span>|  
|<span data-ttu-id="ceb8d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ceb8d-113">Message Text</span></span>|<span data-ttu-id="ceb8d-114">La dirección de red del servidor "%.\*ls" no se puede alcanzar o no existe.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-114">The server network address "%.\*ls" can not be reached or does not exist.</span></span> <span data-ttu-id="ceb8d-115">Compruebe el nombre de la dirección de red y que los puertos de los extremos local y remoto estén operativos.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-115">Check the network address name and that the ports for the local and remote endpoints are operational.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ceb8d-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ceb8d-116">Explanation</span></span>  
 <span data-ttu-id="ceb8d-117">El extremo de la red del servidor no ha respondido porque no existe o no se puede alcanzar o no existe la dirección de red del servidor especificada.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-117">The server network endpoint did not respond because the specified server network address cannot be reached or does not exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ceb8d-118">De forma predeterminada, el sistema operativo de [!INCLUDE[msCoName](../../includes/msconame-md.md)] bloquea todos los puertos.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-118">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] operating system blocks all ports.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ceb8d-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ceb8d-119">User Action</span></span>  
 <span data-ttu-id="ceb8d-120">Compruebe el nombre de la dirección de red y vuelva a emitir el comando.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-120">Verify the network address name and reissue the command.</span></span>  
  
 <span data-ttu-id="ceb8d-121">Es posible que se necesiten acciones correctoras en ambos asociados.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-121">Corrective action might be required on both partners.</span></span> <span data-ttu-id="ceb8d-122">Por ejemplo, si se genera este mensaje cuando se intenta ejecutar SET PARTNER en la instancia del servidor principal, puede que el mensaje implique que solo es necesario realizar una acción correctora en la instancia del servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-122">For example, if this message is raised when you are trying to run SET PARTNER on the principal server instance, the message might imply that you only have to take corrective action on the mirror server instance.</span></span> <span data-ttu-id="ceb8d-123">No obstante, es posible que se necesiten acciones correctoras en ambos asociados.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-123">However, corrective actions might be required on both partners.</span></span>  
  
### <a name="additional-corrective-actions"></a><span data-ttu-id="ceb8d-124">Acciones correctoras adicionales</span><span class="sxs-lookup"><span data-stu-id="ceb8d-124">Additional Corrective Actions</span></span>  
  
-   <span data-ttu-id="ceb8d-125">Asegúrese de que la base de datos reflejada está preparada para la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-125">Make sure that the mirror database is ready for mirroring.</span></span>  
  
-   <span data-ttu-id="ceb8d-126">Asegúrese de que el nombre y el puerto de la instancia del servidor reflejado son correctos.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-126">Make sure that the name and port of the mirror server instance are correct.</span></span>  
  
-   <span data-ttu-id="ceb8d-127">Asegúrese de que la instancia del servidor reflejado de destino no está detrás de un firewall.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-127">Make sure that the destination mirror server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="ceb8d-128">Asegúrese de que la instancia del servidor principal no está detrás de un firewall.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-128">Make sure that the principal server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="ceb8d-129">Compruebe que los extremos se inician en los asociados usando la columna **state** o **state_desc** de la vista de catálogo **sys.database_mirroring_endpoints**.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-129">Verify that the endpoints are started on the partners by using the **state** or **state_desc** column the of the **sys.database_mirroring_endpoints** catalog view.</span></span> <span data-ttu-id="ceb8d-130">Si alguno de los extremos no se ha iniciado, ejecute una instrucción ALTER ENDPOINT para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-130">If either endpoint is not started, execute an ALTER ENDPOINT statement to start it.</span></span>  
  
-   <span data-ttu-id="ceb8d-131">Asegúrese de que la instancia del servidor principal escucha en el puerto asignado a su extremo de creación de reflejo de la base de datos y que la instancia del servidor reflejado escucha en su puerto.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-131">Make sure that the principal server instance is listening on the port assigned to its database mirroring endpoint and that and the mirror server instance is listening on its port.</span></span> <span data-ttu-id="ceb8d-132">Para obtener más información, vea "Comprobar la disponibilidad de los puertos" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-132">For more information, see "Verifying Port Availability," later in this topic.</span></span> <span data-ttu-id="ceb8d-133">Si un asociado no escucha en su puerto asignado, modifique el extremo de creación de reflejo de la base de datos para que escuche en otro puerto.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-133">If a partner is not listening on its assigned port, modify the database mirroring endpoint to listen on a different port.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ceb8d-134">Una seguridad configurada incorrectamente puede provocar un mensaje de error de configuración general.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-134">Improperly configured security can cause a general setup error message.</span></span> <span data-ttu-id="ceb8d-135">Normalmente, la instancia de servidor elimina la solicitud de conexión incorrecta sin responder.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-135">Typically, the server instance drops the bad connection request without responding.</span></span> <span data-ttu-id="ceb8d-136">Para el autor de la llamada, puede parecer que el error de configuración de seguridad se produce por distintos motivos, como que la base de datos reflejada se encuentra en mal estado o no existe, permisos incorrectos, etc.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-136">To the caller, a security-configuration error could appear to have occurred for a variety of other reasons, such as the mirror database in a bad state or does not exist, incorrect permissions, and so on.</span></span>  
  
### <a name="using-the-error-log-file-for-diagnosis"></a><span data-ttu-id="ceb8d-137">Usar el archivo de registro de errores para diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ceb8d-137">Using the Error Log File for Diagnosis</span></span>  
 <span data-ttu-id="ceb8d-138">En ocasiones, solo hay archivos de registro de errores disponibles para la investigación.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-138">In some cases, only error log files are available for investigation.</span></span> <span data-ttu-id="ceb8d-139">En esos casos, determine si el registro de errores contiene el mensaje de error 26023 para el puerto TCP del extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-139">In these cases, determine whether the error log contains error message 26023 for the TCP port of the database mirroring endpoint.</span></span> <span data-ttu-id="ceb8d-140">Este error, cuya gravedad es de 16, podría indicar que no se ha iniciado el extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-140">This error, which is severity 16, might indicate that the database mirroring endpoint is not started.</span></span> <span data-ttu-id="ceb8d-141">Este mensaje se puede generar aunque **sys.database_mirroring_endpoints** muestre el estado del extremo como iniciado.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-141">This message can occur even if **sys.database_mirroring_endpoints** shows the endpoint state as started.</span></span>  
  
 <span data-ttu-id="ceb8d-142">Después de resolver cualquier problema que surja, vuelva a ejecutar la instrucción ALTER DATABASE *nombreDeBaseDeDatos* SET PARTNER en el servidor principal.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-142">After resolving any issues that you encounter, rerun the ALTER DATABASE *database_name* SET PARTNER statement on the principal server.</span></span>  
  
### <a name="verifying-port-availability"></a><span data-ttu-id="ceb8d-143">Comprobar la disponibilidad de los puertos</span><span class="sxs-lookup"><span data-stu-id="ceb8d-143">Verifying Port Availability</span></span>  
 <span data-ttu-id="ceb8d-144">Al configurar la red para una sesión de creación de reflejo de la base de datos, asegúrese de que el extremo de reflejo de la base de datos de cada una de las instancias de servidor solo se usa en el proceso de creación de reflejo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-144">When you are configuring the network for a database mirroring session, make sure the database mirroring endpoint of each server instance is used by only the database mirroring process.</span></span> <span data-ttu-id="ceb8d-145">Si otro proceso escucha en el puerto asignado a un extremo de reflejo de la base de datos, los procesos de creación de reflejo de la base de datos de las demás instancias de servidor no podrán conectarse al extremo.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-145">If another process is listening on the port assigned to a database mirroring endpoint, the database mirroring processes of the other server instances cannot connect to the endpoint.</span></span>  
  
 <span data-ttu-id="ceb8d-146">Para mostrar todos los puertos en los que escucha un servidor basado en Windows, use la utilidad de símbolo del sistema **netstat**.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-146">To display all the ports on which a Windows-based server is listening, use the **netstat** command-prompt utility.</span></span> <span data-ttu-id="ceb8d-147">La sintaxis de **netstat** depende de la versión del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-147">The syntax for **netstat** depends on the version of the Windows operating system.</span></span> <span data-ttu-id="ceb8d-148">Para obtener más información, vea la documentación del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-148">For more information, see the operating system documentation.</span></span>  
  
#### <a name="windows-server-2003-service-pack-1-sp1"></a><span data-ttu-id="ceb8d-149">Service Pack 1 (SP1) de Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="ceb8d-149">Windows Server 2003 Service Pack 1 (SP1)</span></span>  
 <span data-ttu-id="ceb8d-150">Para enumerar los puertos que escuchan y los procesos que los tienen abiertos, especifique el siguiente comando en el símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="ceb8d-150">To list listening ports and the processes that have those ports opened, enter the following command at the Windows command prompt:</span></span>  
  
 <span data-ttu-id="ceb8d-151">**netstat -abn**</span><span class="sxs-lookup"><span data-stu-id="ceb8d-151">**netstat -abn**</span></span>  
  
#### <a name="windows-server-2003-pre-sp1"></a><span data-ttu-id="ceb8d-152">Windows Server 2003 (anterior al SP1)</span><span class="sxs-lookup"><span data-stu-id="ceb8d-152">Windows Server 2003 (pre-SP1)</span></span>  
 <span data-ttu-id="ceb8d-153">Para identificar los puertos que escuchan y los procesos que los tienen abiertos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ceb8d-153">To identify the listening ports and the processes that have those ports opened, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ceb8d-154">Obtenga el Id. del proceso.</span><span class="sxs-lookup"><span data-stu-id="ceb8d-154">Obtain the process ID.</span></span>  
  
     <span data-ttu-id="ceb8d-155">Para obtener más información sobre el Id. de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], conéctese a la instancia y utilice la siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ceb8d-155">To learn the process ID of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connect to that instance and use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT SERVERPROPERTY('ProcessID')   
    ```  
  
     <span data-ttu-id="ceb8d-156">Para obtener más información, vea "SERVERPROPERTY (Transact-SQL)" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ceb8d-156">For more information, see "SERVERPROPERTY (Transact-SQL)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="ceb8d-157">Haga coincidir el id. del proceso con el resultado del siguiente comando **netstat**:</span><span class="sxs-lookup"><span data-stu-id="ceb8d-157">Match the process ID with the output of the following **netstat** command:</span></span>  
  
     <span data-ttu-id="ceb8d-158">**netstat -ano**</span><span class="sxs-lookup"><span data-stu-id="ceb8d-158">**netstat -ano**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb8d-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ceb8d-159">See Also</span></span>  
 <span data-ttu-id="ceb8d-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ceb8d-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="ceb8d-161">[El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ceb8d-161">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="ceb8d-162">[Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ceb8d-162">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="ceb8d-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ceb8d-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="ceb8d-164">[Especificar una dirección de red de servidor &#40;creación de reflejo de la base de datos&#41;](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="ceb8d-164">[Specify a Server Network Address &#40;Database Mirroring&#41;](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="ceb8d-165">[sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ceb8d-165">[sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="ceb8d-166">Solucionar problemas de configuración de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ceb8d-166">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
