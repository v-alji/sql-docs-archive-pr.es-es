---
title: Crear un punto de conexión de reflejo de la base de datos para la autenticación de Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: baf1a4b1-6790-4275-b261-490bca33bdb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5558bc5684f2eb9053c935543db0c05d6225daf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670569"
---
# <a name="create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql"></a><span data-ttu-id="cd805-102">Crear un extremo de reflejo de la base de datos para la autenticación de Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cd805-102">Create a Database Mirroring Endpoint for Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="cd805-103">En este tema se describe cómo crear un extremo de creación de reflejo de la base de datos que utilice la autenticación de Windows en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd805-103">This topic describes how to create a database mirroring endpoint that uses Windows Authentication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cd805-104">Para admitir la creación de reflejo de la base de datos o [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] , cada instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requiere un extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cd805-104">To support database mirroring or [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires a database mirroring endpoint.</span></span> <span data-ttu-id="cd805-105">Una instancia de servidor solo puede tener un extremo de creación de reflejo de base de datos, que tiene un puerto único.</span><span class="sxs-lookup"><span data-stu-id="cd805-105">A server instance can have only one database mirroring endpoint, which has a single port.</span></span> <span data-ttu-id="cd805-106">Un extremo de creación de reflejo de base de datos puede utilizar cualquier puerto disponible en el sistema local cuando se crea el extremo.</span><span class="sxs-lookup"><span data-stu-id="cd805-106">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="cd805-107">Todas las sesiones de creación de reflejo de base de datos de una instancia de servidor escuchan en dicho puerto y todas las conexiones entrantes para la creación de reflejo de base de datos utilizan dicho puerto.</span><span class="sxs-lookup"><span data-stu-id="cd805-107">All database mirroring sessions on a server instance listen on that port, and all incoming connections for database mirroring use that port.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd805-108">Si existe un extremo de creación de reflejo de la base de datos y ya está en uso, se recomienda utilizar dicho extremo.</span><span class="sxs-lookup"><span data-stu-id="cd805-108">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint.</span></span> <span data-ttu-id="cd805-109">Quitar un extremo en uso interrumpe las sesiones existentes.</span><span class="sxs-lookup"><span data-stu-id="cd805-109">Dropping an in-use endpoint disrupts existing sessions.</span></span>  
  
 <span data-ttu-id="cd805-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="cd805-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cd805-111">**Antes de empezar:**  [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="cd805-111">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="cd805-112">**Para crear un punto de conexión de creación de reflejo de la base de datos con:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="cd805-112">**To create a database mirroring endpoint, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cd805-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="cd805-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cd805-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="cd805-114">Security</span></span>  
 <span data-ttu-id="cd805-115">El administrador del sistema establece los métodos de autenticación y cifrado de la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="cd805-115">The authentication and encryption methods of the server instance are established by the system administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd805-116">El algoritmo RC4 está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="cd805-116">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="cd805-117">Se recomienda utilizar AES.</span><span class="sxs-lookup"><span data-stu-id="cd805-117">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cd805-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="cd805-118">Permissions</span></span>  
 <span data-ttu-id="cd805-119">Requiere permiso CREATE ENDPOINT o pertenecer al rol fijo de servidor sysadmin.</span><span class="sxs-lookup"><span data-stu-id="cd805-119">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="cd805-120">Para obtener más información, vea [GRANT &#40;permisos de punto de conexión de Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cd805-120">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cd805-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cd805-121">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-mirroring-endpoint-that-uses-windows-authentication"></a><span data-ttu-id="cd805-122">Para crear un extremo de reflejo de la base de datos que use la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="cd805-122">To Create a Database Mirroring Endpoint That Uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="cd805-123">Conéctese a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la que desea crear un extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cd805-123">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to create a database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="cd805-124">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="cd805-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cd805-125">Determine si ya existe un extremo de creación de reflejo de la base de datos utilizando la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="cd805-125">Determine if a database mirroring endpoint already exists by using the following statement:</span></span>  
  
    ```sql
    SELECT name, role_desc, state_desc FROM sys.database_mirroring_endpoints;
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="cd805-126">Si ya existe un extremo de creación de reflejo de la base de datos para la instancia del servidor, utilice ese extremo para todas las otras sesiones que establezca en la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="cd805-126">If a database mirroring endpoint already exists for the server instance, use that endpoint for any other sessions you establish on the server instance.</span></span>  
  
4.  <span data-ttu-id="cd805-127">Para usar Transact-SQL para crear un extremo que se utilice con la autenticación de Windows, utilice la instrucción CREATE ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="cd805-127">To use Transact-SQL to create an endpoint to use with Windows Authentication, use a CREATE ENDPOINT statement.</span></span> <span data-ttu-id="cd805-128">La instrucción toma la siguiente forma general:</span><span class="sxs-lookup"><span data-stu-id="cd805-128">The statement takes the following general form:</span></span>  
  
     <span data-ttu-id="cd805-129">CREATE ENDPOINT *\<endpointName>*</span><span class="sxs-lookup"><span data-stu-id="cd805-129">CREATE ENDPOINT *\<endpointName>*</span></span>  
  
     <span data-ttu-id="cd805-130">STATE=STARTED</span><span class="sxs-lookup"><span data-stu-id="cd805-130">STATE=STARTED</span></span>  
  
     <span data-ttu-id="cd805-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span><span class="sxs-lookup"><span data-stu-id="cd805-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span></span>  
  
     <span data-ttu-id="cd805-132">FOR DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="cd805-132">FOR DATABASE_MIRRORING</span></span>  
  
     <span data-ttu-id="cd805-133">(</span><span class="sxs-lookup"><span data-stu-id="cd805-133">(</span></span>  
  
     <span data-ttu-id="cd805-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span><span class="sxs-lookup"><span data-stu-id="cd805-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span></span>  
  
     <span data-ttu-id="cd805-135">]</span><span class="sxs-lookup"><span data-stu-id="cd805-135">]</span></span>  
  
     <span data-ttu-id="cd805-136">[ [ **,** ] ENCRYPTION = **REQUIRED**</span><span class="sxs-lookup"><span data-stu-id="cd805-136">[ [**,**] ENCRYPTION = **REQUIRED**</span></span>  
  
     <span data-ttu-id="cd805-137">[ ALGORITHM { *\<algorithm>* } ]</span><span class="sxs-lookup"><span data-stu-id="cd805-137">[ ALGORITHM { *\<algorithm>* } ]</span></span>  
  
     <span data-ttu-id="cd805-138">]</span><span class="sxs-lookup"><span data-stu-id="cd805-138">]</span></span>  
  
     <span data-ttu-id="cd805-139">[ **,** ] ROLE = *\<role>*</span><span class="sxs-lookup"><span data-stu-id="cd805-139">[**,**] ROLE = *\<role>*</span></span>  
  
     <span data-ttu-id="cd805-140">)</span><span class="sxs-lookup"><span data-stu-id="cd805-140">)</span></span>  
  
     <span data-ttu-id="cd805-141">, donde</span><span class="sxs-lookup"><span data-stu-id="cd805-141">where</span></span>  
  
    -   <span data-ttu-id="cd805-142">*\<endpointName>* es un nombre único para el punto de conexión de creación de reflejos de las bases de datos de la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="cd805-142">*\<endpointName>* is a unique name for the database mirroring endpoint of the server instance.</span></span>  
  
    -   <span data-ttu-id="cd805-143">STARTED especifica que el extremo debe iniciarse y que debe empezar a escuchar las conexiones.</span><span class="sxs-lookup"><span data-stu-id="cd805-143">STARTED specifies that the endpoint is to be started and to begin listening for connections.</span></span> <span data-ttu-id="cd805-144">Un extremo de creación de reflejo de la base de datos de base de datos normalmente se crea en el estado STARTED.</span><span class="sxs-lookup"><span data-stu-id="cd805-144">A database mirroring endpoint typically is created in the STARTED state.</span></span> <span data-ttu-id="cd805-145">Opcionalmente, puede iniciar una sesión en el estado STOPPED (valor predeterminado) o DISABLED.</span><span class="sxs-lookup"><span data-stu-id="cd805-145">Alternatively, you can start a session in a STOPPED state (the default) or DISABLED state.</span></span>  
  
    -   <span data-ttu-id="cd805-146">*\<listenerPortList>* es un número de puerto único (*nnnn*) en el que quiere que el servidor escuche los mensajes de creación de reflejos de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cd805-146">*\<listenerPortList>* is a single port number (*nnnn*) on which you want the server to listen for database mirroring messages.</span></span> <span data-ttu-id="cd805-147">Solo se permite TCP; si se especifica cualquier otro protocolo se provoca un error.</span><span class="sxs-lookup"><span data-stu-id="cd805-147">Only TCP is allowed; specifying any other protocol causes an error.</span></span>  
  
         <span data-ttu-id="cd805-148">Un número de puerto solo se puede usar una vez por sistema.</span><span class="sxs-lookup"><span data-stu-id="cd805-148">A port number can be used only once per computer system.</span></span> <span data-ttu-id="cd805-149">Un extremo de creación de reflejo de base de datos puede utilizar cualquier puerto disponible en el sistema local cuando se crea el extremo.</span><span class="sxs-lookup"><span data-stu-id="cd805-149">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="cd805-150">Para identificar los puertos que están usando los extremos TCP del sistema, utilice la siguiente instrucción Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="cd805-150">To identify the ports currently being used by TCP endpoints on the system, use the following Transact-SQL statement:</span></span>  
  
        ```  
        SELECT name, port FROM sys.tcp_endpoints;  
        ```  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="cd805-151">Cada instancia del servidor requiere solo un puerto de escucha único.</span><span class="sxs-lookup"><span data-stu-id="cd805-151">Each server instance requires one and only one unique listener port.</span></span>  
  
    -   <span data-ttu-id="cd805-152">Para la Autenticación de Windows, la opción AUTHENTICATION es opcional, salvo que desee que el extremo únicamente Use NTLM o Kerberos para autenticar conexiones.</span><span class="sxs-lookup"><span data-stu-id="cd805-152">For Windows Authentication, the AUTHENTICATION option is optional, unless you want the endpoint to use only NTLM or Kerberos to authenticate connections.</span></span> <span data-ttu-id="cd805-153">*\<authorizationMethod>* especifica el método que se usa para autenticar conexiones como uno de los siguientes: NTLM, KERBEROS o NEGOTIATE.</span><span class="sxs-lookup"><span data-stu-id="cd805-153">*\<authorizationMethod>* specifies the method used to authenticate connections as one of the following: NTLM, KERBEROS, or NEGOTIATE.</span></span> <span data-ttu-id="cd805-154">El valor predeterminado, NEGOTIATE, hace que el extremo utilice el protocolo de negociación de Windows para elegir NTLM o Kerberos.</span><span class="sxs-lookup"><span data-stu-id="cd805-154">The default, NEGOTIATE, causes the endpoint to use the Windows negotiation protocol to choose either NTLM or Kerberos.</span></span> <span data-ttu-id="cd805-155">La negociación habilita conexiones con o sin autenticación, dependiendo del nivel de autenticación del extremo opuesto.</span><span class="sxs-lookup"><span data-stu-id="cd805-155">Negotiation enables connections with or without authentication, depending on the authentication level of the opposite endpoint.</span></span>  
  
    -   <span data-ttu-id="cd805-156">ENCRYPTION se establece en REQUIRED de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cd805-156">ENCRYPTION is set to REQUIRED by default.</span></span> <span data-ttu-id="cd805-157">Esto significa que todas las conexiones con este punto final deben usar cifrado.</span><span class="sxs-lookup"><span data-stu-id="cd805-157">This means that all connections to this endpoint must use encryption.</span></span> <span data-ttu-id="cd805-158">No obstante, puede deshabilitar el cifrado o hacer que sea opcional en un extremo.</span><span class="sxs-lookup"><span data-stu-id="cd805-158">However, you can disable encryption or make it optional on an endpoint.</span></span> <span data-ttu-id="cd805-159">Las alternativas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd805-159">The alternatives are as follows:</span></span>  
  
        |<span data-ttu-id="cd805-160">Value</span><span class="sxs-lookup"><span data-stu-id="cd805-160">Value</span></span>|<span data-ttu-id="cd805-161">Definición</span><span class="sxs-lookup"><span data-stu-id="cd805-161">Definition</span></span>|  
        |-----------|----------------|  
        |<span data-ttu-id="cd805-162">DISABLED</span><span class="sxs-lookup"><span data-stu-id="cd805-162">DISABLED</span></span>|<span data-ttu-id="cd805-163">Especifica que los datos enviados a través de una conexión no están cifrados.</span><span class="sxs-lookup"><span data-stu-id="cd805-163">Specifies that data sent over a connection is not encrypted.</span></span>|  
        |<span data-ttu-id="cd805-164">SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="cd805-164">SUPPORTED</span></span>|<span data-ttu-id="cd805-165">Especifica que los datos están cifrados solo si el extremo opuesto especifica SUPPORTED o REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="cd805-165">Specifies that the data is encrypted only if the opposite endpoint specifies either SUPPORTED or REQUIRED.</span></span>|  
        |<span data-ttu-id="cd805-166">REQUIRED</span><span class="sxs-lookup"><span data-stu-id="cd805-166">REQUIRED</span></span>|<span data-ttu-id="cd805-167">Especifica que los datos enviados en una conexión deben estar cifrados.</span><span class="sxs-lookup"><span data-stu-id="cd805-167">Specifies that data sent over a connection must be encrypted.</span></span>|  
  
         <span data-ttu-id="cd805-168">Si un extremo requiere cifrado, el otro extremo debe tener ENCRYPTION establecido en SUPPORTED o REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="cd805-168">If an endpoint requires encryption, the other endpoint must have ENCRYPTION set to either SUPPORTED or REQUIRED.</span></span>  
  
    -   <span data-ttu-id="cd805-169">*\<algorithm>* proporciona la opción de especificar estándares de cifrado para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="cd805-169">*\<algorithm>* provides the option of specifying the encryption standards for the endpoint.</span></span> <span data-ttu-id="cd805-170">El valor de *\<algorithm>* puede ser uno de los algoritmos o combinaciones de algoritmos siguientes: RC4, AES, AES RC4 o RC4 AES.</span><span class="sxs-lookup"><span data-stu-id="cd805-170">The value of *\<algorithm>* can be one following algorithms or combinations of algorithms: RC4, AES, AES RC4, or RC4 AES.</span></span>  
  
         <span data-ttu-id="cd805-171">AES RC4 especifica que este extremo negociará el algoritmo de cifrado, dando preferencia al algoritmo AES.</span><span class="sxs-lookup"><span data-stu-id="cd805-171">AES RC4 specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the AES algorithm.</span></span> <span data-ttu-id="cd805-172">RC4 AES especifica que este extremo negociará el algoritmo de cifrado, dando preferencia al algoritmo RC4.</span><span class="sxs-lookup"><span data-stu-id="cd805-172">RC4 AES specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the RC4 algorithm.</span></span> <span data-ttu-id="cd805-173">Si ambos extremos especifican estos dos algoritmos en distintas órdenes, el extremo que acepte la conexión gana.</span><span class="sxs-lookup"><span data-stu-id="cd805-173">If both endpoints specify both algorithms but in different orders, the endpoint accepting the connection wins.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="cd805-174">El algoritmo RC4 está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="cd805-174">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="cd805-175">Se recomienda utilizar AES.</span><span class="sxs-lookup"><span data-stu-id="cd805-175">We recommend that you use AES.</span></span>  
  
    -   <span data-ttu-id="cd805-176">*\<role>* define el rol o los roles que el servidor puede llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="cd805-176">*\<role>* defines the role or roles that the server can perform.</span></span> <span data-ttu-id="cd805-177">Se tiene que especificar ROLE.</span><span class="sxs-lookup"><span data-stu-id="cd805-177">Specifying ROLE is required.</span></span> <span data-ttu-id="cd805-178">Sin embargo, el rol del extremo solo es relevante para la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cd805-178">However, the role of the endpoint is relevant only for database mirroring.</span></span> <span data-ttu-id="cd805-179">Para [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], el rol del extremo se omite.</span><span class="sxs-lookup"><span data-stu-id="cd805-179">For [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], the role of the endpoint is ignored.</span></span>  
  
         <span data-ttu-id="cd805-180">Para permitir que una instancia de servidor sirva como un rol para una sesión de reflejo de base de datos y un rol diferente para otra sesión, especifique ROLE=ALL.</span><span class="sxs-lookup"><span data-stu-id="cd805-180">To allow a server instance to serve as one role for one database mirroring session and different role for another session, specify ROLE=ALL.</span></span> <span data-ttu-id="cd805-181">Para hacer que la instancia de un servidor solo sea un asociado o un testigo, especifique ROLE=PARTNER o ROLE=WITNESS, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cd805-181">To restrict a server instance to being either a partner or a witness, specify ROLE=PARTNER or ROLE=WITNESS, respectively.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="cd805-182">Para obtener más información sobre las opciones de creación de reflejo de la base de datos para diferentes ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="cd805-182">For more information about Database Mirroring options for different editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
     <span data-ttu-id="cd805-183">Para obtener una descripción completa de la sintaxis de CREATE ENDPOINT, vea [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cd805-183">For a complete description of the CREATE ENDPOINT syntax, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cd805-184">Para cambiar un punto de conexión existente, use [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cd805-184">To change an existing endpoint, use [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
###  <a name="example-creating-endpoints-to-support-for-database-mirroring-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="cd805-185">Ejemplo: Crear puntos de conexión para admitir para la creación de reflejo de la base de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cd805-185">Example: Creating Endpoints to Support for Database Mirroring (Transact-SQL)</span></span>  
 <span data-ttu-id="cd805-186">En el siguiente ejemplo se crean dos extremos de creación de reflejo de la base de datos para las instancias del servidor predeterminadas en tres sistemas independientes:</span><span class="sxs-lookup"><span data-stu-id="cd805-186">The following example creates database mirroring endpoints for the default server instances on three separate computer systems:</span></span>  
  
|<span data-ttu-id="cd805-187">Rol de la instancia de servidor</span><span class="sxs-lookup"><span data-stu-id="cd805-187">Role of server instance</span></span>|<span data-ttu-id="cd805-188">Nombre del equipo host</span><span class="sxs-lookup"><span data-stu-id="cd805-188">Name of host computer</span></span>|  
|-----------------------------|---------------------------|  
|<span data-ttu-id="cd805-189">Asociado (inicialmente en el rol principal)</span><span class="sxs-lookup"><span data-stu-id="cd805-189">Partner (initially in the principal role)</span></span>|`SQLHOST01\.`|  
|<span data-ttu-id="cd805-190">Asociado (inicialmente en el rol reflejado)</span><span class="sxs-lookup"><span data-stu-id="cd805-190">Partner (initially in the mirror role)</span></span>|`SQLHOST02\.`|  
|<span data-ttu-id="cd805-191">Testigo</span><span class="sxs-lookup"><span data-stu-id="cd805-191">Witness</span></span>|`SQLHOST03\.`|  
  
 <span data-ttu-id="cd805-192">En este ejemplo, los tres extremos utilizan el número de puerto 7022, aunque funcionaría cualquier número de puerto disponible.</span><span class="sxs-lookup"><span data-stu-id="cd805-192">In this example, all three endpoints use port number 7022, though any available port number would work.</span></span> <span data-ttu-id="cd805-193">La opción AUTHENTICATION no es necesaria, porque los extremos utilizan el tipo predeterminado, Autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="cd805-193">The AUTHENTICATION option is unnecessary, because the endpoints use the default type, Windows Authentication.</span></span> <span data-ttu-id="cd805-194">La opción ENCRYPTION tampoco es necesaria, porque se supone que los extremos van a negociar el método de autenticación de una conexión, que es el comportamiento predeterminado para la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="cd805-194">The ENCRYPTION option is also unnecessary, because the endpoints are all intended to negotiate the authentication method for a connection, which is the default behavior for Windows Authentication.</span></span> <span data-ttu-id="cd805-195">Además, todos los extremos requieren cifrado, que es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cd805-195">Also, all of the endpoints require the encryption, which is the default behavior.</span></span>  
  
 <span data-ttu-id="cd805-196">Cada instancia de servidor se limita a actuar como asociado o como testigo, y el extremo de cada servidor especifica expresamente el rol (ROLE=PARTNER o ROLE=WITNESS).</span><span class="sxs-lookup"><span data-stu-id="cd805-196">Each server instance is limited to serving as either a partner or a witness, and the endpoint of each server expressly specifies which role (ROLE=PARTNER or ROLE=WITNESS).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd805-197">Cada instancia de servidor solo puede tener un extremo.</span><span class="sxs-lookup"><span data-stu-id="cd805-197">Each server instance can have only one endpoint.</span></span> <span data-ttu-id="cd805-198">Por lo tanto, si desea que una instancia de servidor actúe como asociado en ciertas sesiones y como testigo en otras, especifique ROLE=ALL.</span><span class="sxs-lookup"><span data-stu-id="cd805-198">Therefore, if you want a server instance to be a partner in some sessions and the witness in others, specify ROLE=ALL.</span></span>  
  
```sql
--Endpoint for initial principal server instance, which  
--is the only server instance running on SQLHOST01.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for initial mirror server instance, which  
--is the only server instance running on SQLHOST02.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for witness server instance, which  
--is the only server instance running on SQLHOST03.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=WITNESS);  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="cd805-199">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="cd805-199">Related Tasks</span></span>  

### <a name="to-configure-a-database-mirroring-endpoint"></a><span data-ttu-id="cd805-200">Para configurar un extremo de creación del reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="cd805-200">To Configure a Database Mirroring Endpoint</span></span>
  
-   [<span data-ttu-id="cd805-201">Cree un extremo de creación de reflejo de la base de datos para Grupos de disponibilidad AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="cd805-201">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](../availability-groups/windows/database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="cd805-202">Usar certificados para un punto de conexión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd805-202">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="cd805-203">Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd805-203">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="cd805-204">Permitir que un punto de conexión de creación de reflejo de la base de datos use certificados para las conexiones entrantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd805-204">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="cd805-205">Especificar una dirección de red de servidor &#40;creación de reflejo de la base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="cd805-205">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="cd805-206">Especificar la dirección URL del punto de conexión al agregar o modificar una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd805-206">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](../availability-groups/windows/specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="cd805-207">**Para ver información acerca del extremo de creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="cd805-207">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="cd805-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd805-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="cd805-209">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd805-209">See Also</span></span>  
 <span data-ttu-id="cd805-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd805-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="cd805-211">[Elegir un algoritmo de cifrado](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="cd805-211">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="cd805-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd805-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="cd805-213">[Especificar una dirección de red de servidor &#40;creación de reflejo de la base de datos&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="cd805-213">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="cd805-214">[Ejemplo: Configurar la creación de reflejo de la base de datos mediante la autenticación de Windows &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="cd805-214">[Example: Setting Up Database Mirroring Using Windows Authentication &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="cd805-215">El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd805-215">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
