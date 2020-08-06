---
title: MSSQL_ENG014117 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014117 error
ms.assetid: e5906a76-9511-4c47-8826-8c765b58a39d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4694aacc7d1f5ee31f4ff54d8cdd4256b48f713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661944"
---
# <a name="mssql_eng014117"></a><span data-ttu-id="bd92e-102">MSSQL_ENG014117</span><span class="sxs-lookup"><span data-stu-id="bd92e-102">MSSQL_ENG014117</span></span>
    
## <a name="message-details"></a><span data-ttu-id="bd92e-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="bd92e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd92e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="bd92e-104">Product Name</span></span>|<span data-ttu-id="bd92e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd92e-105">SQL Server</span></span>|  
|<span data-ttu-id="bd92e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="bd92e-106">Event ID</span></span>|<span data-ttu-id="bd92e-107">14117</span><span class="sxs-lookup"><span data-stu-id="bd92e-107">14117</span></span>|  
|<span data-ttu-id="bd92e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="bd92e-108">Event Source</span></span>|<span data-ttu-id="bd92e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bd92e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bd92e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bd92e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="bd92e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bd92e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="bd92e-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bd92e-112">Message Text</span></span>|<span data-ttu-id="bd92e-113">%1!' no está configurado como base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="bd92e-113">'%s' is not configured as a distribution database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd92e-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="bd92e-114">Explanation</span></span>  
 <span data-ttu-id="bd92e-115">Este problema puede ocurrir si se cumple uno de los siguientes supuestos o ambos:</span><span class="sxs-lookup"><span data-stu-id="bd92e-115">This error can occur if one or both of the following are true:</span></span>  
  
-   <span data-ttu-id="bd92e-116">Falta la entrada de la base de datos de distribución especificada en **msdb..MSdistributiondbs**.</span><span class="sxs-lookup"><span data-stu-id="bd92e-116">The entry for the specified distribution database is missing from **msdb..MSdistributiondbs**.</span></span>  
  
-   <span data-ttu-id="bd92e-117">No hay una entrada para el servidor local en la base de datos **maestra** o la entrada que hay es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="bd92e-117">There is not an entry for the local server in the **master** database, or the entry that is there is incorrect.</span></span>  
  
     <span data-ttu-id="bd92e-118">La replicación espera que todos los servidores de una topología se registren utilizando el nombre del equipo con un nombre de instancia opcional (en el caso de una instancia en clúster, el servidor virtual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el nombre de instancia opcional).</span><span class="sxs-lookup"><span data-stu-id="bd92e-118">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="bd92e-119">Para que la replicación funcione correctamente, el valor que devuelve `SELECT @@SERVERNAME` por cada servidor de la topología debe coincidir con el nombre del equipo o con el nombre del servidor virtual con el nombre de la instancia opcional.</span><span class="sxs-lookup"><span data-stu-id="bd92e-119">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
     <span data-ttu-id="bd92e-120">La replicación no se admite si ha registrado alguna de las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por dirección IP o por nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="bd92e-120">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="bd92e-121">Es posible que aparezca este error si registró alguna de las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante dirección IP o FQDN en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] cuando configuró la replicación.</span><span class="sxs-lookup"><span data-stu-id="bd92e-121">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd92e-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bd92e-122">User Action</span></span>  
 <span data-ttu-id="bd92e-123">Compruebe que la instancia del distribuidor esté correctamente registrada.</span><span class="sxs-lookup"><span data-stu-id="bd92e-123">Verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="bd92e-124">Si el nombre de red del equipo y el nombre de la instancia de SQL Server son diferentes, lleve a cabo una de estas acciones.</span><span class="sxs-lookup"><span data-stu-id="bd92e-124">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="bd92e-125">Agregue el nombre de la instancia de SQL Server como nombre de red válido.</span><span class="sxs-lookup"><span data-stu-id="bd92e-125">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="bd92e-126">Un método para establecer un nombre de red alternativo es agregarlo al archivo de hosts local.</span><span class="sxs-lookup"><span data-stu-id="bd92e-126">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="bd92e-127">De manera predeterminada, el archivo de hosts local se encuentra en WINDOWS\system32\drivers\etc o WINNT\system32\drivers\etc. Para obtener más información, vea la documentación de Windows.</span><span class="sxs-lookup"><span data-stu-id="bd92e-127">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="bd92e-128">Por ejemplo, si el nombre de equipo es comp1 y el equipo tiene la dirección IP 10.193.17.129, y el nombre de la instancia es inst1/instname, agregue la siguiente entrada en el archivo de hosts:</span><span class="sxs-lookup"><span data-stu-id="bd92e-128">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="bd92e-129">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="bd92e-129">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="bd92e-130">Deshabilite la distribución, registre la instancia y, a continuación, vuelva establecer la distribución.</span><span class="sxs-lookup"><span data-stu-id="bd92e-130">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="bd92e-131">Si el valor de @@SERVERNAME no es correcto en una instancia no agrupada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bd92e-131">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="bd92e-132">Después de ejecutar el procedimiento almacenado [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), debe reiniciar el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que el cambio en @@SERVERNAME surta efecto.</span><span class="sxs-lookup"><span data-stu-id="bd92e-132">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="bd92e-133">Si el valor de @@SERVERNAME no es correcto en una instancia en clúster, debe cambiarle el nombre usando el Administrador de clústeres.</span><span class="sxs-lookup"><span data-stu-id="bd92e-133">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="bd92e-134">Para obtener más información, vea [Always On Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) (Instancias de clúster de conmutación por error de Always On [SQL Server]).</span><span class="sxs-lookup"><span data-stu-id="bd92e-134">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
 <span data-ttu-id="bd92e-135">Después de comprobar que la instancia del distribuidor está correctamente registrada, asegúrese de que la base de datos de distribución aparece en **msdb..MSdistributiondbs**.</span><span class="sxs-lookup"><span data-stu-id="bd92e-135">After verifying that the Distributor instance is registered properly, verify that the distribution database is listed in **msdb..MSdistributiondbs**.</span></span> <span data-ttu-id="bd92e-136">Si no es así:</span><span class="sxs-lookup"><span data-stu-id="bd92e-136">If it is not listed:</span></span>  
  
1.  <span data-ttu-id="bd92e-137">Genere un script para la configuración de la distribución.</span><span class="sxs-lookup"><span data-stu-id="bd92e-137">Script out the distribution configuration.</span></span> <span data-ttu-id="bd92e-138">Para más información, consulte [Scripting Replication](scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="bd92e-138">For more information, see [Scripting Replication](scripting-replication.md).</span></span>  
  
2.  <span data-ttu-id="bd92e-139">Deshabilite la distribución y, a continuación, vuelva a habilitarla.</span><span class="sxs-lookup"><span data-stu-id="bd92e-139">Disable distribution and then re-enable it.</span></span> <span data-ttu-id="bd92e-140">Para más información, consulte [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="bd92e-140">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd92e-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd92e-141">See Also</span></span>  
 [<span data-ttu-id="bd92e-142">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="bd92e-142">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
