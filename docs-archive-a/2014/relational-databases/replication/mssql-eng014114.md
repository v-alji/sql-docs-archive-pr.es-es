---
title: MSSQL_ENG014114 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014114 error
ms.assetid: f5f04590-e1c6-40d8-ab2b-98c791a0fc44
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ba2a1fde59f55eecbfeeec46555567cde964f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661943"
---
# <a name="mssql_eng014114"></a><span data-ttu-id="99e07-102">MSSQL_ENG014114</span><span class="sxs-lookup"><span data-stu-id="99e07-102">MSSQL_ENG014114</span></span>
    
## <a name="message-details"></a><span data-ttu-id="99e07-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="99e07-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99e07-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="99e07-104">Product Name</span></span>|<span data-ttu-id="99e07-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="99e07-105">SQL Server</span></span>|  
|<span data-ttu-id="99e07-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="99e07-106">Event ID</span></span>|<span data-ttu-id="99e07-107">14114</span><span class="sxs-lookup"><span data-stu-id="99e07-107">14114</span></span>|  
|<span data-ttu-id="99e07-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="99e07-108">Event Source</span></span>|<span data-ttu-id="99e07-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="99e07-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="99e07-110">Componente</span><span class="sxs-lookup"><span data-stu-id="99e07-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="99e07-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="99e07-111">Symbolic Name</span></span>||  
|<span data-ttu-id="99e07-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="99e07-112">Message Text</span></span>|<span data-ttu-id="99e07-113">%1!' no está configurado como distribuidor.</span><span class="sxs-lookup"><span data-stu-id="99e07-113">'%s' is not configured as a Distributor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="99e07-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="99e07-114">Explanation</span></span>  
 <span data-ttu-id="99e07-115">Si el mensaje de error especifica una instancia concreta, en vez de 'null', la instancia especificada no se ha configurado correctamente para que sea reconocida como distribuidor.</span><span class="sxs-lookup"><span data-stu-id="99e07-115">If the error message specifies a particular instance, rather than 'null', the instance specified has not been properly configured to be recognized as a Distributor.</span></span>  
  
 <span data-ttu-id="99e07-116">Si el mensaje especifica 'null' como distribuidor, no hay ninguna entrada para el servidor local en la base de datos **maestra** , o la entrada es incorrecta (quizás porque el equipo ha cambiado de nombre).</span><span class="sxs-lookup"><span data-stu-id="99e07-116">If the message specifies 'null' as a Distributor, there is no entry for the local server in **master** database, or the entry is incorrect (perhaps because the computer was renamed).</span></span> <span data-ttu-id="99e07-117">La replicación espera que todos los servidores de una topología se registren utilizando el nombre del equipo con un nombre de instancia opcional (en el caso de una instancia en clúster, el servidor virtual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el nombre de instancia opcional).</span><span class="sxs-lookup"><span data-stu-id="99e07-117">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="99e07-118">Para que la replicación funcione correctamente, el valor que devuelve `SELECT @@SERVERNAME` por cada servidor de la topología debe coincidir con el nombre del equipo o con el nombre del servidor virtual con el nombre de la instancia opcional.</span><span class="sxs-lookup"><span data-stu-id="99e07-118">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="99e07-119">La replicación no se admite si ha registrado alguna de las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por dirección IP o por nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="99e07-119">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="99e07-120">Es posible que aparezca este error si registró alguna de las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante dirección IP o FQDN en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] cuando configuró la replicación.</span><span class="sxs-lookup"><span data-stu-id="99e07-120">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="99e07-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="99e07-121">User Action</span></span>  
 <span data-ttu-id="99e07-122">Si el mensaje especifica una instancia concreta, configure el servidor como distribuidor.</span><span class="sxs-lookup"><span data-stu-id="99e07-122">If the error message specifies a particular instance, configure the server as a Distributor.</span></span> <span data-ttu-id="99e07-123">Para más información, consulte [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="99e07-123">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
 <span data-ttu-id="99e07-124">Si el mensaje no especifica una instancia concreta ('null'), compruebe que la instancia del distribuidor está correctamente registrada.</span><span class="sxs-lookup"><span data-stu-id="99e07-124">If the message does not specify a particular instance ('null'), verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="99e07-125">Si el nombre de red del equipo y el nombre de la instancia de SQL Server son diferentes, lleve a cabo una de estas acciones.</span><span class="sxs-lookup"><span data-stu-id="99e07-125">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="99e07-126">Agregue el nombre de la instancia de SQL Server como nombre de red válido.</span><span class="sxs-lookup"><span data-stu-id="99e07-126">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="99e07-127">Un método para establecer un nombre de red alternativo es agregarlo al archivo de hosts local.</span><span class="sxs-lookup"><span data-stu-id="99e07-127">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="99e07-128">De manera predeterminada, el archivo de hosts local se encuentra en WINDOWS\system32\drivers\etc o WINNT\system32\drivers\etc. Para obtener más información, vea la documentación de Windows.</span><span class="sxs-lookup"><span data-stu-id="99e07-128">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="99e07-129">Por ejemplo, si el nombre de equipo es comp1 y el equipo tiene la dirección IP 10.193.17.129, y el nombre de la instancia es inst1/instname, agregue la siguiente entrada en el archivo de hosts:</span><span class="sxs-lookup"><span data-stu-id="99e07-129">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="99e07-130">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="99e07-130">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="99e07-131">Deshabilite la distribución, registre la instancia y, a continuación, vuelva establecer la distribución.</span><span class="sxs-lookup"><span data-stu-id="99e07-131">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="99e07-132">Si el valor de @@SERVERNAME no es correcto en una instancia no agrupada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="99e07-132">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="99e07-133">Después de ejecutar el procedimiento almacenado [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), debe reiniciar el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que el cambio en @@SERVERNAME surta efecto.</span><span class="sxs-lookup"><span data-stu-id="99e07-133">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="99e07-134">Si el valor de @@SERVERNAME no es correcto en una instancia en clúster, debe cambiarle el nombre usando el Administrador de clústeres.</span><span class="sxs-lookup"><span data-stu-id="99e07-134">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="99e07-135">Para obtener más información, vea [Always On Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) (Instancias de clúster de conmutación por error de Always On [SQL Server]).</span><span class="sxs-lookup"><span data-stu-id="99e07-135">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e07-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99e07-136">See Also</span></span>  
 [<span data-ttu-id="99e07-137">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="99e07-137">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
