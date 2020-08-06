---
title: MSSQL_ENG014010 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014010 error
ms.assetid: 6ea84f2f-e7a2-4028-9ea9-af0d2eba660e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c3d989eb7ae78562fb77d9896545539ba4ca3c7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662827"
---
# <a name="mssql_eng014010"></a><span data-ttu-id="06c1a-102">MSSQL_ENG014010</span><span class="sxs-lookup"><span data-stu-id="06c1a-102">MSSQL_ENG014010</span></span>
    
## <a name="message-details"></a><span data-ttu-id="06c1a-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="06c1a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="06c1a-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="06c1a-104">Product Name</span></span>|<span data-ttu-id="06c1a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="06c1a-105">SQL Server</span></span>|  
|<span data-ttu-id="06c1a-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="06c1a-106">Event ID</span></span>|<span data-ttu-id="06c1a-107">14010</span><span class="sxs-lookup"><span data-stu-id="06c1a-107">14010</span></span>|  
|<span data-ttu-id="06c1a-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="06c1a-108">Event Source</span></span>|<span data-ttu-id="06c1a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="06c1a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="06c1a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="06c1a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="06c1a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="06c1a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="06c1a-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="06c1a-112">Message Text</span></span>|<span data-ttu-id="06c1a-113">El servidor '%s' no está definido como servidor de suscripción.</span><span class="sxs-lookup"><span data-stu-id="06c1a-113">The server '%s' is not defined as a subscription server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="06c1a-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="06c1a-114">Explanation</span></span>  
 <span data-ttu-id="06c1a-115">La replicación espera que todos los servidores de una topología se registren utilizando el nombre del equipo con un nombre de instancia opcional (en el caso de una instancia en clúster, el servidor virtual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el nombre de instancia opcional).</span><span class="sxs-lookup"><span data-stu-id="06c1a-115">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="06c1a-116">Para que la replicación funcione correctamente, el valor que devuelve `SELECT @@SERVERNAME` por cada servidor de la topología debe coincidir con el nombre del equipo o con el nombre del servidor virtual con el nombre de la instancia opcional.</span><span class="sxs-lookup"><span data-stu-id="06c1a-116">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="06c1a-117">La replicación no se admite si ha registrado alguna de las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por dirección IP o por nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="06c1a-117">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="06c1a-118">Este error puede producirse si ha registrado alguna de las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por dirección IP o FQDN en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] al configurar la replicación.</span><span class="sxs-lookup"><span data-stu-id="06c1a-118">If you have any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="06c1a-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="06c1a-119">User Action</span></span>  
 <span data-ttu-id="06c1a-120">Compruebe que todas las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la topología están registradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="06c1a-120">Verify that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances in the topology are registered properly.</span></span> <span data-ttu-id="06c1a-121">Si el nombre de red del equipo y el nombre de la instancia de SQL Server son diferentes, lleve a cabo una de estas acciones.</span><span class="sxs-lookup"><span data-stu-id="06c1a-121">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="06c1a-122">Agregue el nombre de la instancia de SQL Server como nombre de red válido.</span><span class="sxs-lookup"><span data-stu-id="06c1a-122">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="06c1a-123">Un método para establecer un nombre de red alternativo es agregarlo al archivo de hosts local.</span><span class="sxs-lookup"><span data-stu-id="06c1a-123">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="06c1a-124">De manera predeterminada, el archivo de hosts local se encuentra en WINDOWS\system32\drivers\etc o WINNT\system32\drivers\etc. Para obtener más información, vea la documentación de Windows.</span><span class="sxs-lookup"><span data-stu-id="06c1a-124">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="06c1a-125">Por ejemplo, si el nombre de equipo es comp1 y el equipo tiene la dirección IP 10.193.17.129, y el nombre de la instancia es inst1/instname, agregue la siguiente entrada en el archivo de hosts:</span><span class="sxs-lookup"><span data-stu-id="06c1a-125">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="06c1a-126">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="06c1a-126">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="06c1a-127">Quite la replicación, registre cada instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y, a continuación, vuelva a restablecer la replicación.</span><span class="sxs-lookup"><span data-stu-id="06c1a-127">Remove replication, register each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then reestablish replication.</span></span> <span data-ttu-id="06c1a-128">Si el valor de @@SERVERNAME no es correcto en una instancia no agrupada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="06c1a-128">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="06c1a-129">Después de ejecutar el procedimiento almacenado [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), debe reiniciar el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que el cambio en @@SERVERNAME surta efecto.</span><span class="sxs-lookup"><span data-stu-id="06c1a-129">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="06c1a-130">Si el valor de @@SERVERNAME no es correcto en una instancia en clúster, debe cambiarle el nombre usando el Administrador de clústeres.</span><span class="sxs-lookup"><span data-stu-id="06c1a-130">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="06c1a-131">Para obtener más información,vea [Instancias de clúster de conmutación por error de AlwaysOn &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="06c1a-131">For more information, see [AlwaysOn Failover Cluster Instances &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c1a-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06c1a-132">See Also</span></span>  
 <span data-ttu-id="06c1a-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="06c1a-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span></span>  
 [<span data-ttu-id="06c1a-134">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="06c1a-134">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
