---
title: Especificar una dirección de red de servidor (creación de reflejo de la base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- server network addresses [SQL Server]
ms.assetid: a64d4b6b-9016-4f1e-a310-b1df181dd0c6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c7db7ee6d321229205248059ce09a86f1da101f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673875"
---
# <a name="specify-a-server-network-address-database-mirroring"></a><span data-ttu-id="f5838-102">Especificar una dirección de red de servidor (creación de reflejo de la base de datos)</span><span class="sxs-lookup"><span data-stu-id="f5838-102">Specify a Server Network Address (Database Mirroring)</span></span>
  <span data-ttu-id="f5838-103">La configuración de una sesión de creación de reflejo de la base de datos necesita una dirección de red de servidor para cada una de las instancias de servidor.</span><span class="sxs-lookup"><span data-stu-id="f5838-103">Setting up a database mirroring session requires a server network address for each of the server instances.</span></span> <span data-ttu-id="f5838-104">La dirección de red de servidor de una instancia de servidor debe identificar sin ambigüedades la instancia proporcionando una dirección del sistema y el número del puerto en el que la instancia escucha.</span><span class="sxs-lookup"><span data-stu-id="f5838-104">The server network address of a server instance must unambiguously identify the instance by providing a system address and the number of the port on which the instance is listening.</span></span>  
  
 <span data-ttu-id="f5838-105">Antes de que pueda especificar un puerto en una dirección de red de servidor, debe existir un extremo de creación de reflejo de la base de datos en la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="f5838-105">Before you can specify a port in a server network address, the database mirroring endpoint must exist on the server instance.</span></span> <span data-ttu-id="f5838-106">Para obtener más información, vea [Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f5838-106">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
  
  
##  <a name="syntax-for-a-server-network-address"></a><a name="Syntax"></a> <span data-ttu-id="f5838-107">Sintaxis para una dirección de red de servidor</span><span class="sxs-lookup"><span data-stu-id="f5838-107">Syntax for a Server Network Address</span></span>  
 <span data-ttu-id="f5838-108">La sintaxis para una dirección de red de servidor tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="f5838-108">The syntax for a server network address is of the form:</span></span>  
  
 <span data-ttu-id="f5838-109">TCP<strong>://</strong> *\<system-address>* <strong> :<strong>*\<port>*</span><span class="sxs-lookup"><span data-stu-id="f5838-109">TCP<strong>://</strong>*\<system-address>*<strong>:<strong>*\<port>*</span></span> 
  
 <span data-ttu-id="f5838-110">, donde</span><span class="sxs-lookup"><span data-stu-id="f5838-110">where</span></span>  
  
-   <span data-ttu-id="f5838-111">*\<system-address>* es una cadena que identifica de forma inequívoca el sistema del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="f5838-111">*\<system-address>* is a string that unambiguously identifies the destination computer system.</span></span> <span data-ttu-id="f5838-112">Generalmente, la dirección del servidor es un nombre del sistema (si los sistemas están en el mismo dominio), un nombre de dominio completo o una dirección IP:</span><span class="sxs-lookup"><span data-stu-id="f5838-112">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="f5838-113">Si los sistemas están en el mismo dominio, puede utilizar el nombre del equipo; por ejemplo, `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="f5838-113">If the systems are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="f5838-114">Para utilizar una dirección IP, ésta debe ser única en el entorno.</span><span class="sxs-lookup"><span data-stu-id="f5838-114">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="f5838-115">Recomendamos que utilice una dirección IP solo si es estática.</span><span class="sxs-lookup"><span data-stu-id="f5838-115">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="f5838-116">La dirección IP puede ser IP Versión 4 (IPv4) o IP Versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="f5838-116">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="f5838-117">Las direcciones IPv6 se deben incluir entre corchetes, por ejemplo: **[** _<dirección_IPv6>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="f5838-117">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="f5838-118">Para conocer la dirección IP de un sistema, en el símbolo del sistema de Windows, escriba el comando **ipconfig** .</span><span class="sxs-lookup"><span data-stu-id="f5838-118">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="f5838-119">El nombre de dominio completo siempre funciona.</span><span class="sxs-lookup"><span data-stu-id="f5838-119">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="f5838-120">Éste es una cadena de dirección definida localmente que tiene diferentes formatos en los distintos lugares.</span><span class="sxs-lookup"><span data-stu-id="f5838-120">This is a locally defined address string that different forms in different places.</span></span> <span data-ttu-id="f5838-121">Con frecuencia, aunque no siempre, el nombre de dominio completo es un nombre compuesto que incluye el nombre del equipo y una serie de segmentos de dominio separados por puntos con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="f5838-121">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="f5838-122">_nombre_equipo_ **.**</span><span class="sxs-lookup"><span data-stu-id="f5838-122">_computer_name_ **.**</span></span> <span data-ttu-id="f5838-123">_segmento_dominio_[... **.** _segmento_dominio_]</span><span class="sxs-lookup"><span data-stu-id="f5838-123">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="f5838-124">donde *nombre_equipo*es el nombre de red del equipo que ejecuta la instancia de servidor y *segmento_dominio*[... **.** _segmento_dominio_] es la información restante de dominio del servidor; por ejemplo: `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="f5838-124">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="f5838-125">El contenido y el número de segmentos de dominio se determinan en la empresa u organización.</span><span class="sxs-lookup"><span data-stu-id="f5838-125">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="f5838-126">Si no conoce el nombre de dominio completo del servidor, consulte con el administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="f5838-126">If you do not know the fully qualified domain name for your server, see your system administrator.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="f5838-127">Para obtener información acerca de cómo buscar un nombre de dominio completo, vea "Buscar el nombre de dominio completo" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="f5838-127">For information about how to find a fully qualified domain name, see "Finding the Fully Qualified Domain Name," later in this topic.</span></span>  
  
-   <span data-ttu-id="f5838-128">*\<port>* es el número de puerto que usa el punto de conexión de creación de reflejo de la instancia del servidor asociado.</span><span class="sxs-lookup"><span data-stu-id="f5838-128">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="f5838-129">Para obtener más información sobre cómo especificar un punto de conexión, vea [Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f5838-129">For information about specifying an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
     <span data-ttu-id="f5838-130">Un extremo de creación de reflejo de la base de datos puede utilizar cualquier puerto disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f5838-130">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="f5838-131">Cada número de puerto de un sistema debe estar asociado con un único extremo y cada extremo está asociado con una sola instancia de servidor; en consecuencia, diferentes instancias del mismo servidor escuchan en diferentes extremos con distintos puertos.</span><span class="sxs-lookup"><span data-stu-id="f5838-131">Each port number on a computer system must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="f5838-132">Por lo tanto, el puerto que especifique en la dirección de red de servidor al configurar una sesión de creación de reflejo de la base de datos siempre dirigirá la sesión a la instancia de servidor cuyo extremo esté asociado con dicho puerto.</span><span class="sxs-lookup"><span data-stu-id="f5838-132">Therefore, the port you specify in the server network address when you set up a database mirroring session will always direct the session to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="f5838-133">En la dirección de red de servidor de una instancia de servidor, solo el número del puerto asociado con su extremo de creación de reflejo distingue esa instancia de las demás instancias del equipo.</span><span class="sxs-lookup"><span data-stu-id="f5838-133">In the server network address of a server instance, only the number of the port associated with its mirroring endpoint distinguishes that instance from any other instances on the computer.</span></span> <span data-ttu-id="f5838-134">En la siguiente ilustración se muestran las direcciones de red de servidor de dos instancias de servidor en un solo equipo.</span><span class="sxs-lookup"><span data-stu-id="f5838-134">The following figure illustrates the server network addresses of two server instances on a single computer.</span></span> <span data-ttu-id="f5838-135">La instancia predeterminada usa el puerto `7022` y la instancia con nombre usa el puerto `7033`.</span><span class="sxs-lookup"><span data-stu-id="f5838-135">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="f5838-136">Las direcciones de red de servidor de estas dos instancias de servidor son, respectivamente, `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` y `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="f5838-136">The server network address for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="f5838-137">Observe que la dirección no contiene el nombre de la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="f5838-137">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="f5838-138">![Direcciones de red del servidor de una instancia predeterminada](../media/dbm-2-instances-ports-1-system.gif "Direcciones de red del servidor de una instancia predeterminada")</span><span class="sxs-lookup"><span data-stu-id="f5838-138">![Server network addresses of a default instance](../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="f5838-139">Para identificar el puerto asociado actualmente al extremo de creación de reflejo de la base de datos de una instancia de servidor, utilice la siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="f5838-139">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT type_desc, port FROM sys.tcp_endpoints  
    ```  
  
     <span data-ttu-id="f5838-140">Busque la fila cuyo valor **type_desc** sea "DATABASE_MIRRORING" y use el número de puerto correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f5838-140">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="f5838-141">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f5838-141">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="f5838-142">A.</span><span class="sxs-lookup"><span data-stu-id="f5838-142">A.</span></span> <span data-ttu-id="f5838-143">Usar un nombre de sistema</span><span class="sxs-lookup"><span data-stu-id="f5838-143">Using a system name</span></span>  
 <span data-ttu-id="f5838-144">La siguiente dirección de red de servidor especifica un nombre de sistema, `SYSTEM46`, y el puerto `7022`.</span><span class="sxs-lookup"><span data-stu-id="f5838-144">The following server network address specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://SYSTEM46:7022';  
```  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="f5838-145">B.</span><span class="sxs-lookup"><span data-stu-id="f5838-145">B.</span></span> <span data-ttu-id="f5838-146">Usar un nombre de dominio completo</span><span class="sxs-lookup"><span data-stu-id="f5838-146">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="f5838-147">La siguiente dirección de red de servidor especifica un nombre de dominio completo, `DBSERVER8.manufacturing.Adventure-Works.com`, y el puerto `7024`.</span><span class="sxs-lookup"><span data-stu-id="f5838-147">The following server network address specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://DBSERVER8.manufacturing.Adventure-Works.com:7024';  
```  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="f5838-148">C.</span><span class="sxs-lookup"><span data-stu-id="f5838-148">C.</span></span> <span data-ttu-id="f5838-149">Usar IPv4</span><span class="sxs-lookup"><span data-stu-id="f5838-149">Using IPv4</span></span>  
 <span data-ttu-id="f5838-150">La siguiente dirección de red de servidor especifica una dirección IPv4 `10.193.9.134`, y el puerto `7023`.</span><span class="sxs-lookup"><span data-stu-id="f5838-150">The following server network address specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://10.193.9.134:7023';  
```  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="f5838-151">D.</span><span class="sxs-lookup"><span data-stu-id="f5838-151">D.</span></span> <span data-ttu-id="f5838-152">Usar IPv6</span><span class="sxs-lookup"><span data-stu-id="f5838-152">Using IPv6</span></span>  
 <span data-ttu-id="f5838-153">La siguiente dirección de red de servidor contiene una dirección IPv6, `2001:4898:23:1002:20f:1fff:feff:b3a3`, y el puerto `7022`.</span><span class="sxs-lookup"><span data-stu-id="f5838-153">The following server network address contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022';  
```  
  
## <a name="finding-the-fully-qualified-domain-name"></a><span data-ttu-id="f5838-154">Buscar el nombre de dominio completo</span><span class="sxs-lookup"><span data-stu-id="f5838-154">Finding the Fully Qualified Domain Name</span></span>  
 <span data-ttu-id="f5838-155">Para buscar el nombre de dominio completo de un sistema, en el símbolo del sistema de Windows de ese sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="f5838-155">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="f5838-156">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="f5838-156">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="f5838-157">Para formar el nombre de dominio completo, concatene los valores de *<host_name>* y *<Primary_Dns_Suffix>* de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f5838-157">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="f5838-158">_<host_name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="f5838-158">_<host_name>_ **.**</span></span> <span data-ttu-id="f5838-159">_<sufijo_DNS_primario>_</span><span class="sxs-lookup"><span data-stu-id="f5838-159">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="f5838-160">Por ejemplo, la configuración IP</span><span class="sxs-lookup"><span data-stu-id="f5838-160">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="f5838-161">equivale al siguiente nombre de dominio completo:</span><span class="sxs-lookup"><span data-stu-id="f5838-161">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="f5838-162">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f5838-162">Examples</span></span>  
 <span data-ttu-id="f5838-163">En este ejemplo se muestra la dirección de red de servidor para una instancia de servidor en un equipo denominado `REMOTESYSTEM3` en otro dominio.</span><span class="sxs-lookup"><span data-stu-id="f5838-163">The following example shows the server network address for a server instance on a computer system named `REMOTESYSTEM3` in another domain.</span></span> <span data-ttu-id="f5838-164">La información del dominio es `NORTHWEST.ADVENTURE-WORKS.COM`y el puerto del extremo de creación de reflejo de la base de datos es `7025`.</span><span class="sxs-lookup"><span data-stu-id="f5838-164">The domain information is `NORTHWEST.ADVENTURE-WORKS.COM`, and the port of the database mirroring endpoint is `7025`.</span></span> <span data-ttu-id="f5838-165">Dados los componentes de este ejemplo, la dirección de red de servidor es:</span><span class="sxs-lookup"><span data-stu-id="f5838-165">Given these example components, the server network address is.</span></span>  
  
 `TCP://REMOTESYSTEM3.NORTHWEST.ADVENTURE-WORKS.COM:7025`  
  
 <span data-ttu-id="f5838-166">En este ejemplo se muestra la dirección de red de servidor para una instancia de servidor en un equipo denominado `DBSERVER1`.</span><span class="sxs-lookup"><span data-stu-id="f5838-166">The following example shows the server network address for a server instance on a computer system named `DBSERVER1`.</span></span> <span data-ttu-id="f5838-167">Este sistema se encuentra en el dominio local y su nombre de sistema lo identifica de forma inequívoca.</span><span class="sxs-lookup"><span data-stu-id="f5838-167">This system is in the local domain and is unambiguously identified by its system name.</span></span> <span data-ttu-id="f5838-168">El puerto del extremo de creación de reflejo de la base de datos es `7022`.</span><span class="sxs-lookup"><span data-stu-id="f5838-168">The port of the database mirroring endpoint is `7022`.</span></span>  
  
 `TCP://DBSERVER1:7022`  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f5838-169">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="f5838-169">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f5838-170">Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f5838-170">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="f5838-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5838-171">See Also</span></span>  
 <span data-ttu-id="f5838-172">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f5838-172">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="f5838-173">El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f5838-173">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
