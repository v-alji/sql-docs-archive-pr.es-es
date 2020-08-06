---
title: Especificar la dirección URL del extremo al agregar o modificar una réplica de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- endpoints [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], endpoint
- Endpoint URLs (HADR)
ms.assetid: d7520c13-a8ee-4ddc-9e9a-54cd3d27ef1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da1eb2bacd4d5a2f7d0b2a623343f62b5e89597d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750197"
---
# <a name="specify-the-endpoint-url-when-adding-or-modifying-an-availability-replica-sql-server"></a><span data-ttu-id="13849-102">Especificar la dirección URL del extremo al agregar o modificar una réplica de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="13849-102">Specify the Endpoint URL When Adding or Modifying an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="13849-103">Para hospedar una réplica de disponibilidad de un grupo de disponibilidad, una instancia de servidor debe poseer un extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="13849-103">To host an availability replica for an availability group, a server instance must possess a database mirroring endpoint.</span></span> <span data-ttu-id="13849-104">La instancia de servidor utiliza este extremo para escuchar los mensajes de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] procedentes de las réplicas de disponibilidad hospedadas por otras instancias del servidor.</span><span class="sxs-lookup"><span data-stu-id="13849-104">The server instance uses this endpoint to listen for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] messages from availability replicas hosted by other server instances.</span></span> <span data-ttu-id="13849-105">Para definir una réplica de disponibilidad para un grupo de disponibilidad, debe especificar la dirección URL del extremo de la instancia del servidor que hospedará la réplica.</span><span class="sxs-lookup"><span data-stu-id="13849-105">To define an availability replica for an availability group, you must specify the endpoint URL of the server instance that will host the replica.</span></span> <span data-ttu-id="13849-106">La *dirección URL del punto de conexión* identifica el protocolo de transporte del TCP del punto de conexión de creación de reflejo de la base de datos, la dirección del sistema de la instancia del servidor y el número de puerto asociado con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="13849-106">The *endpoint URL* identifies the transport protocol of the database mirroring endpoint-TCP, the system address of the server instance, and the port number associated with the endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13849-107">El término “dirección URL del extremo” es sinónimo del término “dirección de red del servidor” que usa la interfaz de usuario y la documentación de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="13849-107">The term "endpoint URL" is synonymous with the term "server network address" used by the database mirroring user interface and documentation.</span></span>  
  
-   [<span data-ttu-id="13849-108">Sintaxis para una dirección URL de extremo</span><span class="sxs-lookup"><span data-stu-id="13849-108">Syntax for an Endpoint URL</span></span>](#SyntaxOfURL)  
  
-   [<span data-ttu-id="13849-109">Buscar el nombre de dominio completo de un sistema</span><span class="sxs-lookup"><span data-stu-id="13849-109">Finding the Fully Qualified Domain Name of A System</span></span>](#Finding_FQDN)  
  
-   [<span data-ttu-id="13849-110">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="13849-110">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="13849-111">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="13849-111">Related Content</span></span>](#RelatedContent)  
  
##  <a name="syntax-for-an-endpoint-url"></a><a name="SyntaxOfURL"></a> <span data-ttu-id="13849-112">Sintaxis de una dirección URL del extremo</span><span class="sxs-lookup"><span data-stu-id="13849-112">Syntax for an Endpoint URL</span></span>  
 <span data-ttu-id="13849-113">La sintaxis de una dirección URL del extremo tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="13849-113">The syntax for an endpoint URL is of the form:</span></span>  
  
 <span data-ttu-id="13849-114">TCP<strong>://</strong> *\<system-address>* <strong>:</strong> *\<port>*</span><span class="sxs-lookup"><span data-stu-id="13849-114">TCP<strong>://</strong>*\<system-address>*<strong>:</strong>*\<port>*</span></span>  
  
 <span data-ttu-id="13849-115">, donde</span><span class="sxs-lookup"><span data-stu-id="13849-115">where</span></span>  
  
-   <span data-ttu-id="13849-116">*\<system-address>* es una cadena que identifica de forma inequívoca el sistema del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="13849-116">*\<system-address>* is a string that unambiguously identifies the target computer system.</span></span> <span data-ttu-id="13849-117">Generalmente, la dirección del servidor es un nombre del sistema (si los sistemas están en el mismo dominio), un nombre de dominio completo o una dirección IP:</span><span class="sxs-lookup"><span data-stu-id="13849-117">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="13849-118">Dado que todos los nodos del clúster de conmutación por error de Windows Server (WSFC) están en el mismo dominio, puede usar el nombre del equipo; por ejemplo, `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="13849-118">Because the nodes of Windows Server Failover Clustering (WSFC) cluster are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="13849-119">Para utilizar una dirección IP, ésta debe ser única en el entorno.</span><span class="sxs-lookup"><span data-stu-id="13849-119">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="13849-120">Recomendamos que utilice una dirección IP solo si es estática.</span><span class="sxs-lookup"><span data-stu-id="13849-120">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="13849-121">La dirección IP puede ser IP Versión 4 (IPv4) o IP Versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="13849-121">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="13849-122">Las direcciones IPv6 se deben incluir entre corchetes, por ejemplo: **[** _<dirección_IPv6>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="13849-122">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="13849-123">Para conocer la dirección IP de un sistema, en el símbolo del sistema de Windows, escriba el comando **ipconfig** .</span><span class="sxs-lookup"><span data-stu-id="13849-123">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="13849-124">El nombre de dominio completo siempre funciona.</span><span class="sxs-lookup"><span data-stu-id="13849-124">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="13849-125">Esta es una cadena de dirección definida localmente que adopta diferentes formatos en distintos lugares.</span><span class="sxs-lookup"><span data-stu-id="13849-125">This is a locally defined address string that takes different forms in different places.</span></span> <span data-ttu-id="13849-126">Con frecuencia, aunque no siempre, el nombre de dominio completo es un nombre compuesto que incluye el nombre del equipo y una serie de segmentos de dominio separados por puntos con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="13849-126">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="13849-127">_nombre_equipo_ **.**</span><span class="sxs-lookup"><span data-stu-id="13849-127">_computer_name_ **.**</span></span> <span data-ttu-id="13849-128">_segmento_dominio_[... **.** _segmento_dominio_]</span><span class="sxs-lookup"><span data-stu-id="13849-128">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="13849-129">donde *nombre_equipo*es el nombre de red del equipo que ejecuta la instancia de servidor y *segmento_dominio*[... **.** _segmento_dominio_] es la información restante de dominio del servidor; por ejemplo: `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="13849-129">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="13849-130">El contenido y el número de segmentos de dominio se determinan en la empresa u organización.</span><span class="sxs-lookup"><span data-stu-id="13849-130">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="13849-131">Para obtener más información, vea [Buscar el nombre de dominio completo](#Finding_FQDN), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="13849-131">For more information, see [Finding the Fully Qualified Domain Name](#Finding_FQDN), later in this topic.</span></span>  
  
-   <span data-ttu-id="13849-132">*\<port>* es el número de puerto que usa el punto de conexión de creación de reflejo de la instancia de servidor asociada.</span><span class="sxs-lookup"><span data-stu-id="13849-132">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span>  
  
     <span data-ttu-id="13849-133">Un extremo de creación de reflejo de la base de datos puede utilizar cualquier puerto disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="13849-133">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="13849-134">Cada número de puerto debe estar asociado con un único extremo y cada extremo está asociado con una sola instancia de servidor; en consecuencia, diferentes instancias del mismo servidor escuchan en diferentes extremos con distintos puertos.</span><span class="sxs-lookup"><span data-stu-id="13849-134">Each port number must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="13849-135">Por consiguiente, el puerto que especifique en la dirección URL del extremo al especificar una réplica de disponibilidad siempre dirigirá los mensajes entrantes a la instancia de servidor cuyo extremo esté asociado con dicho puerto.</span><span class="sxs-lookup"><span data-stu-id="13849-135">Therefore, the port you specify in the endpoint URL when you specify an availability replica will always direct incoming messages to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="13849-136">En la dirección URL del extremo, solo el número de puerto identifica la instancia del servidor que está asociada con el extremo de creación de reflejo en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="13849-136">IIn the endpoint URL, only the number of the port identifies the server instance that is associated with the mirroring endpoint on the target computer.</span></span> <span data-ttu-id="13849-137">En la siguiente ilustración se muestran las direcciones de extremo de dos instancias de servidor en un solo equipo.</span><span class="sxs-lookup"><span data-stu-id="13849-137">The following figure illustrates the endpoint URLs of two server instances on a single computer.</span></span> <span data-ttu-id="13849-138">La instancia predeterminada usa el puerto `7022` y la instancia con nombre usa el puerto `7033`.</span><span class="sxs-lookup"><span data-stu-id="13849-138">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="13849-139">Las direcciones URL del extremo para estas dos instancias de servidor son, respectivamente, `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` y `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="13849-139">The endpoint URL for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="13849-140">Observe que la dirección no contiene el nombre de la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="13849-140">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="13849-141">![Direcciones de red del servidor de una instancia predeterminada](../../media/dbm-2-instances-ports-1-system.gif "Direcciones de red del servidor de una instancia predeterminada")</span><span class="sxs-lookup"><span data-stu-id="13849-141">![Server network addresses of a default instance](../../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="13849-142">Para identificar el puerto asociado actualmente al extremo de creación de reflejo de la base de datos de una instancia de servidor, utilice la siguiente instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="13849-142">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql
    SELECT type_desc, port FROM sys.TCP_endpoints  
    ```  
  
     <span data-ttu-id="13849-143">Busque la fila cuyo valor **type_desc** sea "DATABASE_MIRRORING" y use el número de puerto correspondiente.</span><span class="sxs-lookup"><span data-stu-id="13849-143">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="13849-144">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="13849-144">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="13849-145">A.</span><span class="sxs-lookup"><span data-stu-id="13849-145">A.</span></span> <span data-ttu-id="13849-146">Usar un nombre de sistema</span><span class="sxs-lookup"><span data-stu-id="13849-146">Using a system name</span></span>  
 <span data-ttu-id="13849-147">La siguiente dirección URL del extremo especifica un nombre de sistema, `SYSTEM46`, y el puerto `7022`.</span><span class="sxs-lookup"><span data-stu-id="13849-147">The following endpoint URL specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
 `TCP://SYSTEM46:7022`  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="13849-148">B.</span><span class="sxs-lookup"><span data-stu-id="13849-148">B.</span></span> <span data-ttu-id="13849-149">Usar un nombre de dominio completo</span><span class="sxs-lookup"><span data-stu-id="13849-149">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="13849-150">La siguiente dirección URL del extremo especifica un nombre de dominio completo, `DBSERVER8.manufacturing.Adventure-Works.com`, y el puerto `7024`.</span><span class="sxs-lookup"><span data-stu-id="13849-150">The following endpoint URL specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
 `TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024`  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="13849-151">C.</span><span class="sxs-lookup"><span data-stu-id="13849-151">C.</span></span> <span data-ttu-id="13849-152">Usar IPv4</span><span class="sxs-lookup"><span data-stu-id="13849-152">Using IPv4</span></span>  
 <span data-ttu-id="13849-153">La siguiente dirección URL del extremo especifica una dirección IPv4, `10.193.9.134`, y el puerto `7023`.</span><span class="sxs-lookup"><span data-stu-id="13849-153">The following endpoint URL specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
 `TCP://10.193.9.134:7023`  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="13849-154">D.</span><span class="sxs-lookup"><span data-stu-id="13849-154">D.</span></span> <span data-ttu-id="13849-155">Usar IPv6</span><span class="sxs-lookup"><span data-stu-id="13849-155">Using IPv6</span></span>  
 <span data-ttu-id="13849-156">La siguiente dirección URL del extremo contiene una dirección IPv6, `2001:4898:23:1002:20f:1fff:feff:b3a3`, y el puerto `7022`.</span><span class="sxs-lookup"><span data-stu-id="13849-156">The following endpoint URL contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
 `TCP://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022`  
  
##  <a name="finding-the-fully-qualified-domain-name-of-a-system"></a><a name="Finding_FQDN"></a> <span data-ttu-id="13849-157">Buscar el nombre de dominio completo de un sistema</span><span class="sxs-lookup"><span data-stu-id="13849-157">Finding the Fully Qualified Domain Name of A System</span></span>  
 <span data-ttu-id="13849-158">Para buscar el nombre de dominio completo de un sistema, en el símbolo del sistema de Windows de ese sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="13849-158">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="13849-159">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="13849-159">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="13849-160">Para formar el nombre de dominio completo, concatene los valores de *<host_name>* y *<Primary_Dns_Suffix>* de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="13849-160">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="13849-161">_<host_name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="13849-161">_<host_name>_ **.**</span></span> <span data-ttu-id="13849-162">_<sufijo_DNS_primario>_</span><span class="sxs-lookup"><span data-stu-id="13849-162">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="13849-163">Por ejemplo, la configuración IP</span><span class="sxs-lookup"><span data-stu-id="13849-163">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="13849-164">equivale al siguiente nombre de dominio completo:</span><span class="sxs-lookup"><span data-stu-id="13849-164">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
> [!NOTE]  
>  <span data-ttu-id="13849-165">Si necesita más información acerca de un nombre de dominio completo, póngase en contacto con el administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="13849-165">If you need more information about a fully qualified domain name, see your system administrator.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="13849-166">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="13849-166">Related Tasks</span></span>  
 <span data-ttu-id="13849-167">**Para configurar un extremo de creación del reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="13849-167">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="13849-168">Cree un extremo de creación de reflejo de la base de datos para Grupos de disponibilidad AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="13849-168">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="13849-169">Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="13849-169">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="13849-170">Usar certificados para un punto de conexión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="13849-170">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="13849-171">Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="13849-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="13849-172">Permitir que un punto de conexión de creación de reflejo de la base de datos use certificados para las conexiones entrantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="13849-172">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="13849-173">Especificar una dirección de red de servidor &#40;creación de reflejo de la base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13849-173">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="13849-174">Solucionar problemas de Grupos de disponibilidad AlwaysOn &#40;de configuración de SQL Server&#41;eliminado</span><span class="sxs-lookup"><span data-stu-id="13849-174">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
 <span data-ttu-id="13849-175">**Para ver información acerca del extremo de creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="13849-175">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="13849-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="13849-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="13849-177">**Para agregar una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="13849-177">**To add an availability replica**</span></span>  
  
-   [<span data-ttu-id="13849-178">Agregar una réplica secundaria a un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="13849-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="13849-179">Combinar una réplica secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="13849-179">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="13849-180">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="13849-180">Related Content</span></span>  
  
-   [<span data-ttu-id="13849-181">Guía de soluciones AlwaysOn de Microsoft SQL Server para lograr alta disponibilidad y recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="13849-181">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
## <a name="see-also"></a><span data-ttu-id="13849-182">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13849-182">See Also</span></span>  
 <span data-ttu-id="13849-183">[Creación y configuración de grupos de disponibilidad &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="13849-183">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="13849-184">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="13849-184">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="13849-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="13849-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
