---
title: Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 143c68a5-589f-4e7f-be59-02707e1a430a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3088333fbfd4babd209df07f8880c838ce626d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663694"
---
# <a name="establish-a-database-mirroring-session-using-windows-authentication-transact-sql"></a><span data-ttu-id="30bdd-102">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="30bdd-102">Establish a Database Mirroring Session Using Windows Authentication (Transact-SQL)</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="30bdd-103">Se usa [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] en su lugar.</span><span class="sxs-lookup"><span data-stu-id="30bdd-103">Use [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] instead.</span></span>  
  
 <span data-ttu-id="30bdd-104">Una vez preparada la base de datos reflejada (vea [Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)), puede establecer una sesión de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="30bdd-104">After the mirror database is prepared (see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)), you can establish a database mirroring session.</span></span> <span data-ttu-id="30bdd-105">Las instancias de servidor principal, reflejado y testigo deben ser instancias de servidor independientes y se deben encontrar en sistemas host distintos.</span><span class="sxs-lookup"><span data-stu-id="30bdd-105">The principal, mirror, and witness server instances must be separate server instances, which should be on separate host systems.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="30bdd-106">Es recomendable que configure la creación de reflejo de la base de datos durante las horas de menor actividad, ya que puede afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="30bdd-106">We recommend that you configure database mirroring during off-peak hours because configuring mirroring can impact performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30bdd-107">Una determinada instancia de servidor puede participar en varias sesiones simultáneas de creación de reflejo de la base de datos con el mismo asociado o con asociados distintos.</span><span class="sxs-lookup"><span data-stu-id="30bdd-107">A given server instance can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="30bdd-108">Una instancia de servidor puede ser asociado en algunas sesiones y testigo en otras.</span><span class="sxs-lookup"><span data-stu-id="30bdd-108">A server instance can be a partner in some sessions and a witness in other sessions.</span></span> <span data-ttu-id="30bdd-109">La instancia del servidor reflejado debe ejecutar la misma edición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que la instancia del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="30bdd-109">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the principal server instance.</span></span> <span data-ttu-id="30bdd-110">La creación de reflejo de la base de datos no está disponible en todas las ediciones de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30bdd-110">Database mirroring is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="30bdd-111">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="30bdd-112">Asimismo, se recomienda encarecidamente que se ejecuten en sistemas comparables que puedan administrar cargas de trabajo idénticas.</span><span class="sxs-lookup"><span data-stu-id="30bdd-112">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
### <a name="to-establish-a-database-mirroring-session"></a><span data-ttu-id="30bdd-113">Para establecer una sesión de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="30bdd-113">To establish a database mirroring session</span></span>  
  
1.  <span data-ttu-id="30bdd-114">Cree la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="30bdd-114">Create the mirror database.</span></span> <span data-ttu-id="30bdd-115">Para obtener más información, vea [Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-115">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="30bdd-116">Configure la seguridad en cada instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="30bdd-116">Set up security on each server instance.</span></span>  
  
     <span data-ttu-id="30bdd-117">Cada instancia de servidor de una sesión de creación de reflejo de la base de datos requiere un extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="30bdd-117">Each server instance in a database mirroring session requires a database mirroring endpoint.</span></span> <span data-ttu-id="30bdd-118">Si el extremo no existe, deberá crearlo.</span><span class="sxs-lookup"><span data-stu-id="30bdd-118">If the endpoint does not exist, you must create it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30bdd-119">El tipo de autenticación que utilice la instancia de servidor para la creación de reflejo de la base de datos es una propiedad del extremo de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="30bdd-119">The form of authentication used for database mirroring by a server instance is a property of its database mirroring endpoint.</span></span> <span data-ttu-id="30bdd-120">Existen dos tipos de seguridad de transporte para la creación de reflejo de la base de datos: autenticación de Windows o autenticación basada en certificados.</span><span class="sxs-lookup"><span data-stu-id="30bdd-120">Two types of transport security are available for database mirroring: Windows Authentication or certificate-based authentication.</span></span> <span data-ttu-id="30bdd-121">Para obtener más información, vea [seguridad de transporte para la creación de reflejo de la base de datos y Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-121">For more information, see [Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span></span>  
  
     <span data-ttu-id="30bdd-122">Asegúrese de que exista un extremo para el reflejo de bases de datos en cada servidor asociado.</span><span class="sxs-lookup"><span data-stu-id="30bdd-122">On each partner server, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="30bdd-123">La instancia de servidor solo puede tener un extremo de reflejo de la base de datos, independientemente del número de sesiones de creación de reflejo que se admitirán.</span><span class="sxs-lookup"><span data-stu-id="30bdd-123">Regardless of the number of mirroring sessions to be supported, the server instance can have only one database mirroring endpoint.</span></span> <span data-ttu-id="30bdd-124">Si tiene pensado usar esta instancia de servidor exclusivamente para los asociados en las sesiones de creación de reflejo de la base de datos, puede asignar el rol de asociado al punto de conexión (ROLE **=** PARTNER).</span><span class="sxs-lookup"><span data-stu-id="30bdd-124">If you intend to use this server instance exclusively for partners in database mirroring sessions, you can assign the role of partner to the endpoint (ROLE**=** PARTNER).</span></span> <span data-ttu-id="30bdd-125">Si también tiene pensado usar este servidor para el testigo en otras sesiones de creación de reflejo de la base de datos, asigne el rol del extremo como ALL.</span><span class="sxs-lookup"><span data-stu-id="30bdd-125">If you intend also to use this server for the witness in other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="30bdd-126">Para ejecutar una instrucción SET PARTNER, el valor de STATE de los extremos de ambos asociados debe ser STARTED.</span><span class="sxs-lookup"><span data-stu-id="30bdd-126">To execute a SET PARTNER statement, the STATE of the endpoints of both partners must be set to STARTED.</span></span>  
  
     <span data-ttu-id="30bdd-127">Para saber si una instancia de servidor tiene un extremo de creación de reflejo de la base de datos y cuáles son su rol y su estado, use en esa instancia la siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="30bdd-127">To learn whether a server instance has a database mirroring endpoint and to learn its role and state, on that instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="30bdd-128">No reconfigure un extremo de creación de reflejo de la base de datos en uso.</span><span class="sxs-lookup"><span data-stu-id="30bdd-128">Do not reconfigure an in-use database mirroring endpoint.</span></span> <span data-ttu-id="30bdd-129">Si existe un extremo para la creación de reflejo de la base de datos y ya se está utilizando, se recomienda utilizar ese extremo para cada sesión en la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="30bdd-129">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="30bdd-130">Quitar un extremo en uso puede dar lugar a que el extremo se reinicie y conllevar la interrupción de las conexiones de las sesiones existentes, que pueden aparecer como un error en las otras instancias de servidor.</span><span class="sxs-lookup"><span data-stu-id="30bdd-130">Dropping an in-use endpoint can cause the endpoint to restart, disrupting the connections of the existing sessions, which can appear to be an error to the other server instances.</span></span> <span data-ttu-id="30bdd-131">Esto es especialmente importante en el modo de alta seguridad con conmutación automática por error, en el que reconfigurar el extremo en un asociado podría dar lugar a una conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="30bdd-131">This is particularly important in high-safety mode with automatic failover, in which reconfiguring the endpoint on a partner could cause a failover to occur.</span></span> <span data-ttu-id="30bdd-132">Asimismo, si se ha establecido un testigo para una sesión, la eliminación del extremo de creación de reflejo de la base de datos puede hacer que el servidor principal de esa sesión pierda quórum; si sucede esto, la base de datos se queda sin conexión y se desconecta a sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="30bdd-132">Also, if a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="30bdd-133">Para más información, vea [Cuórum: cómo un testigo afecta a la disponibilidad de la base de datos &#40;creación de reflejo de la base de datos&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-133">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="30bdd-134">Si alguno de los asociados no tiene un punto de conexión, vea [Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-134">If either partner lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
3.  <span data-ttu-id="30bdd-135">Si las instancias de servidor se ejecutan con distintas cuentas de usuario de dominio, cada una requiere un inicio de sesión en la base de datos **master** de las demás.</span><span class="sxs-lookup"><span data-stu-id="30bdd-135">If server instances are running under different domain user accounts, each requires a login in the **master** database of the others.</span></span> <span data-ttu-id="30bdd-136">Si el inicio de sesión no existe, deberá crearlo.</span><span class="sxs-lookup"><span data-stu-id="30bdd-136">If the login does not exist, you must create it.</span></span> <span data-ttu-id="30bdd-137">Para obtener más información, vea [Permitir el acceso de red a un punto de conexión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-137">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
4.  <span data-ttu-id="30bdd-138">Para establecer el servidor principal como asociado en la base de datos reflejada, conéctese al servidor reflejado y emita la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="30bdd-138">To set the principal server as partner on the mirror database, connect to the mirror server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="30bdd-139">ALTER DATABASE *<database_name>* conjunto de asociados **=** _<server_network_address>_</span><span class="sxs-lookup"><span data-stu-id="30bdd-139">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="30bdd-140">donde *<database_name>* es el nombre de la base de datos de la que se va a crear el reflejo (este nombre es el mismo en ambos asociados) y *<server_network_address>* es la dirección de red del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="30bdd-140">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the principal server.</span></span>  
  
     <span data-ttu-id="30bdd-141">La sintaxis para una dirección de red de servidor es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="30bdd-141">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="30bdd-142">TCP<strong>://</strong> \<*system-address> \*<strong>:</strong> \<*port> \*</span><span class="sxs-lookup"><span data-stu-id="30bdd-142">TCP<strong>://</strong>\<*system-address>*<strong>:</strong>\<*port>*</span></span>  
  
     <span data-ttu-id="30bdd-143">donde \<*system-address>\* es una cadena que identifica de forma inequívoca el sistema del equipo de destino y \<*port>\* es el número de puerto que usa el punto de conexión de la creación de reflejo de la instancia de servidor asociado.</span><span class="sxs-lookup"><span data-stu-id="30bdd-143">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="30bdd-144">Para obtener más información, vea [Especificar una dirección de red de servidor &#40;creación de reflejo de la base de datos&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-144">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="30bdd-145">Por ejemplo, en la instancia del servidor reflejado, el siguiente parámetro ALTER DATABASE establece el asociado como la instancia de servidor principal original.</span><span class="sxs-lookup"><span data-stu-id="30bdd-145">For example, on the mirror server instance, the following ALTER DATABASE statement sets the partner as the original principal server instance.</span></span> <span data-ttu-id="30bdd-146">El nombre de la base de datos es **AdventureWorks**, la dirección del sistema es DBSERVER1 (el nombre del sistema del asociado) y el puerto usado por el punto de conexión de reflejo de la base de datos del asociado es 7022:</span><span class="sxs-lookup"><span data-stu-id="30bdd-146">The database name is **AdventureWorks**, the system address is DBSERVER1-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7022:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
       SET PARTNER = 'TCP://DBSERVER1:7022'  
    ```  
  
     <span data-ttu-id="30bdd-147">Esta instrucción prepara el servidor reflejado para que cree una sesión cuando el servidor principal se ponga en contacto con él.</span><span class="sxs-lookup"><span data-stu-id="30bdd-147">This statement prepares the mirror server to form a session when it is contacted by the principal server.</span></span>  
  
5.  <span data-ttu-id="30bdd-148">Para establecer el servidor reflejado como asociado en la base de datos principal, conéctese al servidor principal y emita la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="30bdd-148">To set the mirror server as partner on the principal database, connect to the principal server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="30bdd-149">ALTER DATABASE *<database_name>* conjunto de asociados **=** _<server_network_address>_</span><span class="sxs-lookup"><span data-stu-id="30bdd-149">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="30bdd-150">Para obtener más información, vea el paso 4.</span><span class="sxs-lookup"><span data-stu-id="30bdd-150">For more information, see step 4.</span></span>  
  
     <span data-ttu-id="30bdd-151">Por ejemplo, en la instancia de servidor principal, la siguiente instrucción ALTER DATABASE establece el asociado como la instancia del servidor reflejado original.</span><span class="sxs-lookup"><span data-stu-id="30bdd-151">For example, on the principal server instance, the following ALTER DATABASE statement sets the partner as the original mirror server instance.</span></span> <span data-ttu-id="30bdd-152">El nombre de la base de datos es **AdventureWorks**, la dirección del sistema es DBSERVER2 (el nombre del sistema del asociado) y el puerto usado por el punto de conexión de reflejo de la base de datos del asociado es 7025:</span><span class="sxs-lookup"><span data-stu-id="30bdd-152">The database name is **AdventureWorks**, the system address is DBSERVER2-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7025:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks SET PARTNER = 'TCP://DBSERVER2:7022'  
    ```  
  
     <span data-ttu-id="30bdd-153">Si escribe esta instrucción en el servidor principal, comenzará la sesión de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="30bdd-153">Entering this statement on the principal server begins the database mirroring session.</span></span>  
  
6.  <span data-ttu-id="30bdd-154">De forma predeterminada, una sesión se configura con la seguridad de las transacciones completa (SAFETY se establece en FULL), lo que inicia la sesión en modo sincrónico de alta seguridad sin conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="30bdd-154">By default a session is set to full transaction safety (SAFETY is set to FULL), which starts the session in synchronous, high-safety mode without automatic failover.</span></span> <span data-ttu-id="30bdd-155">Puede volver a configurar la sesión para ejecutarla en modo de alta seguridad con conmutación automática por error o en modo asincrónico de alto rendimiento, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="30bdd-155">You can reconfigure the session to run in high-safety mode with automatic failover or in asynchronous, high-performance mode, as follows:</span></span>  
  
    -   <span data-ttu-id="30bdd-156">**Modo de seguridad alta con conmutación automática por error**</span><span class="sxs-lookup"><span data-stu-id="30bdd-156">**High-safety mode with automatic failover**</span></span>  
  
         <span data-ttu-id="30bdd-157">Si desea que una sesión en modo de alta seguridad admita la conmutación automática por error, agregue una instancia de servidor testigo.</span><span class="sxs-lookup"><span data-stu-id="30bdd-157">If you want a high-safety mode session to support automatic failover, add a witness server instance.</span></span> <span data-ttu-id="30bdd-158">Para obtener más información, vea [Agregar un testigo de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-158">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
    -   <span data-ttu-id="30bdd-159">**Modo de alto rendimiento**</span><span class="sxs-lookup"><span data-stu-id="30bdd-159">**High-performance mode**</span></span>  
  
         <span data-ttu-id="30bdd-160">Otra opción, si no desea la conmutación automática por error y prefiere poner más énfasis en el rendimiento en lugar de la disponibilidad, es desactivar la seguridad de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="30bdd-160">Alternatively, if you do not want automatic failover and you prefer to emphasize performance over availability, turn off transaction safety.</span></span> <span data-ttu-id="30bdd-161">Para obtener más información, vea [Cambiar la seguridad de las transacciones en una sesión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-161">For more information, see [Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="30bdd-162">En el modo de alto rendimiento, WITNESS debe establecerse en OFF.</span><span class="sxs-lookup"><span data-stu-id="30bdd-162">In high-performance mode, WITNESS should be set to OFF.</span></span> <span data-ttu-id="30bdd-163">Para más información, vea [Cuórum: cómo un testigo afecta a la disponibilidad de la base de datos &#40;creación de reflejo de la base de datos&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-163">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30bdd-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30bdd-164">Example</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30bdd-165">En el siguiente ejemplo se establece una sesión de creación de reflejo de la base de datos entre asociados de una base de datos reflejada existente.</span><span class="sxs-lookup"><span data-stu-id="30bdd-165">The following example establishes a database mirroring session between partners for an existing mirror database.</span></span> <span data-ttu-id="30bdd-166">Para obtener información sobre la creación de una base de datos reflejada, vea [Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-166">For information on creating a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)=.</span></span>  
  
 <span data-ttu-id="30bdd-167">En el ejemplo se muestran los pasos básicos para crear una sesión de creación de reflejo de la base de datos sin un testigo.</span><span class="sxs-lookup"><span data-stu-id="30bdd-167">The example shows the basic steps for creating a database mirroring session without a witness.</span></span> <span data-ttu-id="30bdd-168">Los dos asociados son las instancias de servidor predeterminadas en dos equipos (PARTNERHOST1 y PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="30bdd-168">The two partners are the default server instances on two computer systems (PARTNERHOST1 and PARTNERHOST5).</span></span> <span data-ttu-id="30bdd-169">Las dos instancias de asociado se ejecutan con la misma cuenta de usuario de dominio de Windows (MYDOMAIN\dbousername).</span><span class="sxs-lookup"><span data-stu-id="30bdd-169">The two partner instances run the same Windows domain user account (MYDOMAIN\dbousername).</span></span>  
  
1.  <span data-ttu-id="30bdd-170">En la instancia de servidor principal (instancia predeterminada en PARTNERHOST1), cree un extremo que admita todos los roles y que utilice el puerto 7022:</span><span class="sxs-lookup"><span data-stu-id="30bdd-170">On the principal server instance (default instance on PARTNERHOST1), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="30bdd-171">Para obtener un ejemplo de cómo configurar un inicio de sesión, vea [Permitir el acceso de red a un punto de conexión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-171">For an example of how to setup a login, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
2.  <span data-ttu-id="30bdd-172">En la instancia del servidor reflejado (instancia predeterminada en PARTNERHOST5), cree un extremo que admita todos los roles y que utilice el puerto 7022:</span><span class="sxs-lookup"><span data-stu-id="30bdd-172">On the mirror server instance (default instance on PARTNERHOST5), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
3.  <span data-ttu-id="30bdd-173">En la instancia de servidor principal (en PARTNERHOST1), cree una copia de seguridad de la base de datos:</span><span class="sxs-lookup"><span data-stu-id="30bdd-173">On the principal server instance (on PARTNERHOST1), back up the database:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdvWorks_dbmirror.bak'   
        WITH FORMAT  
    GO  
    ```  
  
4.  <span data-ttu-id="30bdd-174">En la instancia del servidor reflejado (en `PARTNERHOST5`), restaure la base de datos:</span><span class="sxs-lookup"><span data-stu-id="30bdd-174">On the mirror server instance (on `PARTNERHOST5`), restore the database:</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks   
        FROM DISK = 'Z:\AdvWorks_dbmirror.bak'   
        WITH NORECOVERY  
    GO  
    ```  
  
5.  <span data-ttu-id="30bdd-175">Tras crear la copia de seguridad completa de base de datos, debe crear una copia de seguridad de registros en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="30bdd-175">After you create the full database backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="30bdd-176">Por ejemplo, las siguientes instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] hacen una copia de seguridad del registro en el mismo archivo que ha utilizado la copia de seguridad de base de datos anterior:</span><span class="sxs-lookup"><span data-stu-id="30bdd-176">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding database backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="30bdd-177">Para poder iniciar la creación de reflejo, se debe aplicar la copia de seguridad de registros obligatoria (y las copias de seguridad de registros subsiguientes).</span><span class="sxs-lookup"><span data-stu-id="30bdd-177">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="30bdd-178">Por ejemplo, la siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] restaura el primer registro desde C:\AdventureWorks.bak:</span><span class="sxs-lookup"><span data-stu-id="30bdd-178">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from C:\AdventureWorks.bak:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\ AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="30bdd-179">En la instancia del servidor reflejado, establezca la instancia de servidor en PARTNERHOST1 como asociado (para convertirla en el servidor principal inicial):</span><span class="sxs-lookup"><span data-stu-id="30bdd-179">On the mirror server instance, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1:7022'  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="30bdd-180">De forma predeterminada, una sesión de creación de reflejo de la base de datos se ejecuta en modo sincrónico. Esto exige tener la seguridad de las transacciones completa (SAFETY establecido en FULL).</span><span class="sxs-lookup"><span data-stu-id="30bdd-180">default, a database mirroring session runs in synchronous mode, which depends on having full transaction safety (SAFETY is set to FULL).</span></span> <span data-ttu-id="30bdd-181">Para que una sesión se ejecute en modo asincrónico de alto rendimiento, establezca SAFETY en OFF.</span><span class="sxs-lookup"><span data-stu-id="30bdd-181">To cause a session to run in asynchronous, high-performance mode, set SAFETY to OFF.</span></span> <span data-ttu-id="30bdd-182">Para más información, consulte [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-182">For more information, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
8.  <span data-ttu-id="30bdd-183">En la instancia de servidor principal, establezca la instancia de servidor en `PARTNERHOST5` como asociado (para convertirla en el servidor reflejado inicial):</span><span class="sxs-lookup"><span data-stu-id="30bdd-183">On the principal server instance, set the server instance on `PARTNERHOST5` as the partner (making it the initial mirror server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5:7022'  
    GO  
    ```  
  
9. <span data-ttu-id="30bdd-184">Opcionalmente, si va a usar el modo de alta seguridad con conmutación automática por error, configure la instancia de servidor testigo.</span><span class="sxs-lookup"><span data-stu-id="30bdd-184">Optionally, if you intend to use high-safety mode with automatic failover, set up the witness server instance.</span></span> <span data-ttu-id="30bdd-185">Para obtener más información, vea [Agregar un testigo de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-185">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30bdd-186">Para ver un ejemplo completo en el que se muestra la configuración de seguridad, se prepara la base de datos reflejada, se configuran los asociados y se agrega un testigo, vea [Configurar la creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30bdd-186">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30bdd-187">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30bdd-187">See Also</span></span>  
 <span data-ttu-id="30bdd-188">[Configurar la creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="30bdd-188">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="30bdd-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="30bdd-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="30bdd-190">[Permitir el acceso de red a un punto de conexión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="30bdd-190">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="30bdd-191">[Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="30bdd-191">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="30bdd-192">[Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="30bdd-192">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="30bdd-193">[Creación de reflejo de la base de datos y trasvase de registros &#40;SQL Server&#41;](database-mirroring-and-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="30bdd-193">[Database Mirroring and Log Shipping &#40;SQL Server&#41;](database-mirroring-and-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="30bdd-194">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="30bdd-194">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="30bdd-195">[Replicación y creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="30bdd-195">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="30bdd-196">[Configurar la creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="30bdd-196">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="30bdd-197">[Especificar una dirección de red de servidor &#40;creación de reflejo de la base de datos&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="30bdd-197">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 [<span data-ttu-id="30bdd-198">Database Mirroring Operating Modes</span><span class="sxs-lookup"><span data-stu-id="30bdd-198">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
