---
title: Agregar un testigo de creación de reflejo de la base de datos mediante la autenticación de Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- Windows authentication [SQL Server]
- database mirroring [SQL Server], witness
ms.assetid: bf5e87df-91a4-49f9-ae88-2a6dcf644510
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 88684c3a1ca12ea579859759ed804ca281647fa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670583"
---
# <a name="add-a-database-mirroring-witness-using-windows-authentication-transact-sql"></a><span data-ttu-id="4f93f-102">Agregar un testigo de creación de reflejo de la base de datos mediante la autenticación de Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4f93f-102">Add a Database Mirroring Witness Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="4f93f-103">Para configurar un testigo para la base de datos, el propietario de ésta debe asignar una instancia del Motor de base de datos al rol de servidor testigo.</span><span class="sxs-lookup"><span data-stu-id="4f93f-103">To set up a witness for a database, the database owner assigns a Database Engine instance to the role of witness server.</span></span> <span data-ttu-id="4f93f-104">La instancia de servidor testigo puede ejecutarse en el mismo equipo que la instancia de servidor principal o reflejado, aunque de este modo se reduce la solidez de la conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="4f93f-104">The witness server instance can run on the same computer as the principal or mirror server instance, but this substantially reduces the robustness of automatic failover.</span></span>  
  
 <span data-ttu-id="4f93f-105">Se recomienda que el testigo se aloje en un equipo independiente.</span><span class="sxs-lookup"><span data-stu-id="4f93f-105">We strongly recommend that the witness reside on a separate computer.</span></span> <span data-ttu-id="4f93f-106">Un servidor determinado puede participar en varias sesiones simultáneas de creación de reflejo de la base de datos con el mismo asociado o con asociados distintos.</span><span class="sxs-lookup"><span data-stu-id="4f93f-106">A given server can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="4f93f-107">Un servidor específico puede ser asociado en algunas sesiones y testigo en otras.</span><span class="sxs-lookup"><span data-stu-id="4f93f-107">A given server can be a partner in some sessions and a witness in other sessions.</span></span>  
  
 <span data-ttu-id="4f93f-108">El testigo está pensado exclusivamente para el modo de alta seguridad con conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="4f93f-108">The witness is intended exclusively for high-safety mode with automatic failover.</span></span> <span data-ttu-id="4f93f-109">Antes de definir un testigo, es recomendable que se asegure de que la propiedad SAFETY está definida actualmente como FULL.</span><span class="sxs-lookup"><span data-stu-id="4f93f-109">Before you set a witness, we strongly recommend that you ensure that the SAFETY property is currently set to FULL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4f93f-110">Se recomienda configurar la creación de reflejo de la base de datos durante los periodos de poca actividad, dado que este proceso puede afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4f93f-110">We recommend that you configure database mirroring during off-peak hours because configuration can impact performance.</span></span>  
  
### <a name="to-establish-a-witness"></a><span data-ttu-id="4f93f-111">Para establecer un testigo</span><span class="sxs-lookup"><span data-stu-id="4f93f-111">To establish a witness</span></span>  
  
1.  <span data-ttu-id="4f93f-112">En la instancia de servidor testigo, asegúrese de que existe un extremo para la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4f93f-112">On the witness server instance, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="4f93f-113">Independientemente del número de sesiones de creación de reflejo que deban admitirse, la instancia del servidor solo debe tener un extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4f93f-113">Regardless of the number of mirroring session to be supported, the server instance must have only one database mirroring endpoint.</span></span> <span data-ttu-id="4f93f-114">Si tiene previsto usar esta instancia de servidor exclusivamente como testigo en las sesiones de creación de reflejo de la base de datos, asigne el rol de testigo al extremo (testigo de rol **=** ).</span><span class="sxs-lookup"><span data-stu-id="4f93f-114">If you intend to use this server instance exclusively as a witness in database mirroring sessions, assign the role of witness to the endpoint (ROLE **=** WITNESS).</span></span> <span data-ttu-id="4f93f-115">Si lo que quiere es utilizar la instancia de servidor como asociado en una o más sesiones de creación de reflejo de la base de datos, asigne el rol del extremo a ALL.</span><span class="sxs-lookup"><span data-stu-id="4f93f-115">If you intend to use this server instance as a partner in one or more other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="4f93f-116">Para ejecutar una instrucción SET WITNESS, es preciso haber iniciado previamente la sesión de creación de reflejo de la base de datos (entre los asociados) y el valor STATE del extremo del testigo debe establecerse en STARTED.</span><span class="sxs-lookup"><span data-stu-id="4f93f-116">To execute a SET WITNESS statement, the database mirroring session must already be started (between the partners), and the STATE of the endpoint of the witness must be set to STARTED.</span></span>  
  
     <span data-ttu-id="4f93f-117">Para saber si la instancia del servidor testigo tiene su extremo de creación de reflejo de la base de datos y para conocer su rol y su estado, utilice la siguiente instrucción Transact-SQL en dicha instancia:</span><span class="sxs-lookup"><span data-stu-id="4f93f-117">To learn whether the witness server instance has its database mirroring endpoint and to learn its role and state, on that instance, use the following Transact-SQL statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4f93f-118">Si existe un extremo para la creación de reflejo de la base de datos y ya se está utilizando, se recomienda utilizar ese extremo para cada sesión en la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="4f93f-118">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="4f93f-119">Si quita un extremo en uso, se interrumpirán las conexiones de las sesiones existentes.</span><span class="sxs-lookup"><span data-stu-id="4f93f-119">Dropping an in-use endpoint disrupts the connections of the existing sessions.</span></span> <span data-ttu-id="4f93f-120">Si se ha establecido un testigo para una sesión, la eliminación del extremo de creación de reflejo de la base de datos puede hacer que el servidor principal de esa sesión pierda quórum; si sucede esto, la base de datos se queda sin conexión y sus usuarios quedan desconectados.</span><span class="sxs-lookup"><span data-stu-id="4f93f-120">If a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="4f93f-121">Para más información, vea [Cuórum: cómo un testigo afecta a la disponibilidad de la base de datos &#40;creación de reflejo de la base de datos&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="4f93f-121">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="4f93f-122">Si el asociado carece de un punto de conexión, vea [Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4f93f-122">If the witness lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="4f93f-123">Si las instancias de asociados se ejecutan en cuentas de usuario de distintos dominios, cree un inicio de sesión para las diferentes cuentas de la base de datos maestra de cada instancia.</span><span class="sxs-lookup"><span data-stu-id="4f93f-123">If the partner instances are running under different domain user accounts, create a login for the different accounts in the master database of each instance.</span></span> <span data-ttu-id="4f93f-124">Para obtener más información, vea [Permitir el acceso de red a un punto de conexión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="4f93f-124">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="4f93f-125">Conéctese al servidor principal y emita la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="4f93f-125">Connect to the principal server and issue the following statement:</span></span>  
  
     <span data-ttu-id="4f93f-126">ALTER DATABASE *<database_name>* SET WITNESS **=** _<server_network_address>_</span><span class="sxs-lookup"><span data-stu-id="4f93f-126">ALTER DATABASE *<database_name>* SET WITNESS **=** _<server_network_address>_</span></span>  
  
     <span data-ttu-id="4f93f-127">donde *<nombre_de_base_de_datos>* es el nombre de la base de datos de la que se va a crear el reflejo (este nombre es el mismo para ambos asociados) y *<dirección_de_red_de_servidor>* es la dirección de red de servidor de la instancia del servidor testigo.</span><span class="sxs-lookup"><span data-stu-id="4f93f-127">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the witness server instance.</span></span>  
  
     <span data-ttu-id="4f93f-128">La sintaxis para una dirección de red de servidor es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f93f-128">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="4f93f-129">TCP **://** \<_system-address> _**:**\<*port>\*</span><span class="sxs-lookup"><span data-stu-id="4f93f-129">TCP **://**\<_system-address>_**:**\<*port>\*</span></span>  
  
     <span data-ttu-id="4f93f-130">donde \<*system-address>\* es una cadena que identifica de forma inequívoca el sistema del equipo de destino y \<*port>\* es el número de puerto que usa el punto de conexión de la creación de reflejo de la instancia de servidor asociado.</span><span class="sxs-lookup"><span data-stu-id="4f93f-130">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="4f93f-131">Para obtener más información, vea [Especificar una dirección de red de servidor &#40;creación de reflejo de la base de datos&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="4f93f-131">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="4f93f-132">Por ejemplo, en la instancia del servidor principal, la siguiente instrucción ALTER DATABASE define el testigo.</span><span class="sxs-lookup"><span data-stu-id="4f93f-132">For example, on the principal server instance, the following ALTER DATABASE statement sets the witness.</span></span> <span data-ttu-id="4f93f-133">El nombre de la base de datos es **AdventureWorks**, la dirección del sistema es DBSERVER3 (el nombre del sistema testigo) y el puerto que usa el punto de conexión de creación de reflejo de la base de datos del testigo es `7022`:</span><span class="sxs-lookup"><span data-stu-id="4f93f-133">The database name is **AdventureWorks**, the system address is DBSERVER3-the name of the witness system, and the port used by the database mirroring endpoint of the witness is `7022`:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
      SET WITNESS = 'TCP://DBSERVER3:7022'  
    ```  
  
## <a name="example"></a><span data-ttu-id="4f93f-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f93f-134">Example</span></span>  
 <span data-ttu-id="4f93f-135">En el siguiente ejemplo se establece un testigo de creación de reflejo de datos.</span><span class="sxs-lookup"><span data-stu-id="4f93f-135">The following example establishes a data mirroring witness.</span></span> <span data-ttu-id="4f93f-136">En la instancia del servidor testigo (instancia predeterminada en `WITNESSHOST4`):</span><span class="sxs-lookup"><span data-stu-id="4f93f-136">On the witness server instance (default instance on `WITNESSHOST4`):</span></span>  
  
1.  <span data-ttu-id="4f93f-137">Cree un extremo para esta instancia de servidor solo para el rol WITNESS usando el puerto `7022`.</span><span class="sxs-lookup"><span data-stu-id="4f93f-137">Create an endpoint for this server instance for the WITNESS role only using port `7022`.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    ```  
  
2.  <span data-ttu-id="4f93f-138">Cree un inicio de sesión para la cuenta de usuario de dominio de las instancias de asociados, si son diferentes; por ejemplo, suponga que el testigo se está ejecutando como `SOMEDOMAIN\witnessuser`, pero los asociados se están ejecutando como `MYDOMAIN\dbousername`.</span><span class="sxs-lookup"><span data-stu-id="4f93f-138">Create a login for domain user account of partner instances, if different; for example, assume that the witness is running as `SOMEDOMAIN\witnessuser`, but the partners are running as `MYDOMAIN\dbousername`.</span></span> <span data-ttu-id="4f93f-139">Cree un inicio de sesión para los asociados, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="4f93f-139">Create a login for the partners, as follows:</span></span>  
  
    ```  
    --Create a login for the partner server instances,  
    --which are both running as MYDOMAIN\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [MYDOMAIN\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [MYDOMAIN\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="4f93f-140">En cada instancia del servidor asociado, cree un inicio de sesión para la instancia del servidor testigo:</span><span class="sxs-lookup"><span data-stu-id="4f93f-140">On each of the partner server instances, create a login for the witness server instance:</span></span>  
  
    ```  
    --Create a login for the witness server instance,  
    --which is running as SOMEDOMAIN\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [SOMEDOMAIN\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [SOMEDOMAIN\witnessuser];  
    GO  
    ```  
  
4.  <span data-ttu-id="4f93f-141">En el servidor principal, establezca el testigo (que se encuentra en `WITNESSHOST4`):</span><span class="sxs-lookup"><span data-stu-id="4f93f-141">On the principal server, set the witness (which is on `WITNESSHOST4`):</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4:7022'  
    GO  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="4f93f-142">La dirección de red del servidor indica la instancia del servidor de destino mediante el número de puerto, que se asigna al extremo de creación de reflejo de la instancia.</span><span class="sxs-lookup"><span data-stu-id="4f93f-142">The server network address indicates the target server instance by the port number, which maps to the mirroring endpoint of the instance.</span></span>  
  
 <span data-ttu-id="4f93f-143">Para ver un ejemplo completo en el que se muestra la configuración de seguridad, se prepara la base de datos reflejada, se configuran los asociados y se agrega un testigo, vea [Configurar la creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4f93f-143">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f93f-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f93f-144">See Also</span></span>  
 <span data-ttu-id="4f93f-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f93f-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="4f93f-146">[Permitir el acceso de red a un punto de conexión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="4f93f-146">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="4f93f-147">[Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="4f93f-147">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="4f93f-148">[Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="4f93f-148">[Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md) </span></span>  
 <span data-ttu-id="4f93f-149">[Quitar el testigo de una sesión de creación de reflejo de la base de datos &#40;SQL Server&#41;](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4f93f-149">[Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="4f93f-150">Testigo de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="4f93f-150">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
