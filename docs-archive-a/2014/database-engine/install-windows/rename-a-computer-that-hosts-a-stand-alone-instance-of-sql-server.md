---
title: Cambiar el nombre de un equipo que hospeda una instancia independiente de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- remote login errors [SQL Server]
- standalone computer names [SQL Server]
- names [SQL Server], standalone instances of SQL Server
- renaming standalone instances of SQL Server
- sysservers system table
- removing remote logins
- deleting remote logins
- dropping remote logins
ms.assetid: bbaf1445-b8a2-4ebf-babe-17d8cf20b037
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 079348921900a7cbf880027433280253df1a9e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749425"
---
# <a name="rename-a-computer-that-hosts-a-stand-alone-instance-of-sql-server"></a><span data-ttu-id="ef914-102">Cambiar el nombre de un equipo que hospeda una instancia independiente de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ef914-102">Rename a Computer that Hosts a Stand-Alone Instance of SQL Server</span></span>
  <span data-ttu-id="ef914-103">Cuando se cambia el nombre del equipo que ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el nombre nuevo se reconoce durante el inicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef914-103">When you change the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the new name is recognized during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span> <span data-ttu-id="ef914-104">No es necesario que vuelva a ejecutar el programa de instalación para restablecer el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="ef914-104">You do not have to run Setup again to reset the computer name.</span></span> <span data-ttu-id="ef914-105">En su lugar, realice los siguientes pasos para actualizar los metadatos del sistema que están almacenados en sys.servers y que son notificados por la función de sistema @@SERVERNAME.</span><span class="sxs-lookup"><span data-stu-id="ef914-105">Instead, use the following steps to update system metadata that is stored in sys.servers and reported by the system function @@SERVERNAME.</span></span> <span data-ttu-id="ef914-106">Actualice los metadatos del sistema para reflejar los cambios de nombre de equipo de las conexiones remotas y las aplicaciones que usan @@SERVERNAME, o que consultan el nombre del servidor desde sys.servers.</span><span class="sxs-lookup"><span data-stu-id="ef914-106">Update system metadata to reflect computer name changes for remote connections and applications that use @@SERVERNAME, or that query the server name from sys.servers.</span></span>  
  
 <span data-ttu-id="ef914-107">Los siguientes pasos no se pueden utilizar para cambiar el nombre de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef914-107">The following steps cannot be used to rename an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ef914-108">Estos pasos solo se pueden usar para cambiar la parte del nombre de la instancia que corresponde al nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="ef914-108">They can be used only to rename the part of the instance name that corresponds to the computer name.</span></span> <span data-ttu-id="ef914-109">Por ejemplo, puede cambiar el nombre de un equipo denominado MB1 que hospeda una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] denominada Instance1 por otro nombre, por ejemplo MB2.</span><span class="sxs-lookup"><span data-stu-id="ef914-109">For example, you can change a computer named MB1 that hosts an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] named Instance1 to another name, such as MB2.</span></span> <span data-ttu-id="ef914-110">Sin embargo, la parte del nombre que corresponde a la instancia, Instance1, permanecerá intacta.</span><span class="sxs-lookup"><span data-stu-id="ef914-110">However, the instance part of the name, Instance1, will remain unchanged.</span></span> <span data-ttu-id="ef914-111">En este ejemplo, \\\\*nombreDeEquipo*\\*nombreDeInstancia* cambiará de \\\MB1\Instance1 a \\\MB2\Instance1.</span><span class="sxs-lookup"><span data-stu-id="ef914-111">In this example, the \\\\*ComputerName*\\*InstanceName* would be changed from \\\MB1\Instance1 to \\\MB2\Instance1.</span></span>  
  
 <span data-ttu-id="ef914-112">**Antes de empezar**</span><span class="sxs-lookup"><span data-stu-id="ef914-112">**Before you begin**</span></span>  
  
 <span data-ttu-id="ef914-113">Antes de comenzar el proceso de cambio de nombre, lea la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="ef914-113">Before you begin the renaming process, review the following information:</span></span>  
  
-   <span data-ttu-id="ef914-114">Cuando una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] forma parte de un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el proceso para cambiar el nombre del equipo difiere del que se usa en el equipo que hospeda una instancia independiente.</span><span class="sxs-lookup"><span data-stu-id="ef914-114">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the computer renaming process differs from a computer that hosts a stand-alone instance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ef914-115">no permite cambiar el nombre de los equipos implicados en un proceso de replicación, excepto cuando se utiliza el trasvase de registros con la replicación.</span><span class="sxs-lookup"><span data-stu-id="ef914-115">does not support renaming computers that are involved in replication, except when you use log shipping with replication.</span></span> <span data-ttu-id="ef914-116">Se puede cambiar el nombre del equipo secundario del trasvase de registros si el equipo primario se pierde de manera permanente.</span><span class="sxs-lookup"><span data-stu-id="ef914-116">The secondary computer in log shipping can be renamed if the primary computer is permanently lost.</span></span> <span data-ttu-id="ef914-117">Para obtener más información, vea [Trasvase de registros y replicación &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ef914-117">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
-   <span data-ttu-id="ef914-118">Al cambiar el nombre de un equipo que está configurado para utilizar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] podría no estar disponible después del cambio del nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="ef914-118">When you rename a computer that is configured to use [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might not be available after the computer name change.</span></span> <span data-ttu-id="ef914-119">Para obtener más información, vea [Cambiar el nombre de un equipo que ejecuta un servidor de informes](../../reporting-services/report-server/rename-a-report-server-computer.md).</span><span class="sxs-lookup"><span data-stu-id="ef914-119">For more information, see [Rename a Report Server Computer](../../reporting-services/report-server/rename-a-report-server-computer.md).</span></span>  
  
-   <span data-ttu-id="ef914-120">Cuando cambia el nombre de un equipo que está configurado para utilizar la creación de reflejo de la base de datos, ésta debe desactivarse antes de realizar la operación de cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="ef914-120">When you rename a computer that is configured to use database mirroring, you must turn off database mirroring before the renaming operation.</span></span> <span data-ttu-id="ef914-121">A continuación, vuelva a establecer la creación de reflejo de la base de datos con el nuevo nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="ef914-121">Then, re-establish database mirroring with the new computer name.</span></span> <span data-ttu-id="ef914-122">Los metadatos para la creación de reflejo de la base de datos no se actualizan automáticamente para reflejar el nuevo nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="ef914-122">Metadata for database mirroring will not be updated automatically to reflect the new computer name.</span></span> <span data-ttu-id="ef914-123">Utilice los pasos siguientes para actualizar los metadatos del sistema.</span><span class="sxs-lookup"><span data-stu-id="ef914-123">Use the following steps to update system metadata.</span></span>  
  
-   <span data-ttu-id="ef914-124">Es posible que los usuarios que se conectan a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a través de un grupo de Windows que utilice una referencia codificada de forma rígida al nombre del equipo no se puedan conectar a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef914-124">Users who connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through a Windows group that uses a hard-coded reference to the computer name might not be able to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ef914-125">Esto puede ocurrir después de cambiar el nombre si el grupo de Windows especifica el nombre de equipo anterior.</span><span class="sxs-lookup"><span data-stu-id="ef914-125">This can occur after the rename if the Windows group specifies the old computer name.</span></span> <span data-ttu-id="ef914-126">Para asegurarse de que estos grupos de Windows tienen conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] después de la operación de cambio de nombre, actualice el grupo de Windows para especificar el nuevo nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="ef914-126">To ensure that such Windows groups have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connectivity following the renaming operation, update the Windows group to specify the new computer name.</span></span>  
  
 <span data-ttu-id="ef914-127">Puede conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el nuevo nombre del equipo después de haber reiniciado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef914-127">You can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the new computer name after you have restarted [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ef914-128">Para asegurarse de que @@SERVERNAME devuelve el nombre actualizado de la instancia del servidor local, conviene ejecutar manualmente el procedimiento correspondiente a su situación de entre los siguientes.</span><span class="sxs-lookup"><span data-stu-id="ef914-128">To ensure that @@SERVERNAME returns the updated name of the local server instance, you should manually run the following procedure that applies to your scenario.</span></span> <span data-ttu-id="ef914-129">El procedimiento que use dependerá de si está actualizando un equipo que hospeda o una instancia predeterminada o con nombre de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef914-129">The procedure you use depends on whether you are updating a computer that hosts a default or named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-rename-a-computer-that-hosts-a-stand-alone-instance-of-ssnoversion"></a><span data-ttu-id="ef914-130">Para cambiar el nombre de un equipo que hospeda una instancia independiente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef914-130">To rename a computer that hosts a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="ef914-131">En un equipo con el nombre cambiado que hospeda una instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ejecute los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef914-131">For a renamed computer that hosts a default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name>;  
    GO  
    sp_addserver <new_name>, local;  
    GO  
    ```  
  
     <span data-ttu-id="ef914-132">Reinicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef914-132">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="ef914-133">En un equipo con el nombre cambiado que hospeda una instancia con nombre de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ejecute los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef914-133">For a renamed computer that hosts a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name\instancename>;  
    GO  
    sp_addserver <new_name\instancename>, local;  
    GO  
    ```  
  
     <span data-ttu-id="ef914-134">Reinicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef914-134">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="after-the-renaming-operation"></a><span data-ttu-id="ef914-135">Después de la operación de cambio de nombre</span><span class="sxs-lookup"><span data-stu-id="ef914-135">After the Renaming Operation</span></span>  
 <span data-ttu-id="ef914-136">Después de cambiar el nombre del equipo, las conexiones que utilizaban el nombre anterior deben realizarse con el nombre nuevo.</span><span class="sxs-lookup"><span data-stu-id="ef914-136">After a computer has been renamed, any connections that used the old computer name must connect by using the new name.</span></span>  
  
#### <a name="to-verify-that-the-renaming-operation-has-completed-successfully"></a><span data-ttu-id="ef914-137">Para comprobar que la operación de cambio de nombre se ha realizado correctamente</span><span class="sxs-lookup"><span data-stu-id="ef914-137">To verify that the renaming operation has completed successfully</span></span>  
  
-   <span data-ttu-id="ef914-138">Seleccione la información de @@SERVERNAME o de sys.servers.</span><span class="sxs-lookup"><span data-stu-id="ef914-138">Select information from either @@SERVERNAME or sys.servers.</span></span> <span data-ttu-id="ef914-139">La función @@SERVERNAME devolverá el nombre nuevo y la tabla sys.servers lo mostrará.</span><span class="sxs-lookup"><span data-stu-id="ef914-139">The @@SERVERNAME function will return the new name, and the sys.servers table will show the new name.</span></span> <span data-ttu-id="ef914-140">En el siguiente ejemplo se muestra el uso de @@SERVERNAME.</span><span class="sxs-lookup"><span data-stu-id="ef914-140">The following example shows the use of @@SERVERNAME.</span></span>  
  
    ```  
    SELECT @@SERVERNAME AS 'Server Name';  
    ```  
  
## <a name="additional-considerations"></a><span data-ttu-id="ef914-141">Consideraciones adicionales</span><span class="sxs-lookup"><span data-stu-id="ef914-141">Additional Considerations</span></span>  
 <span data-ttu-id="ef914-142">**Remote Logins:** si el equipo dispone de algún inicio de sesión remoto, al ejecutar sesión remoto, al ejecutar **sp_dropserver** podría generarse un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef914-142">**Remote Logins** - If the computer has any remote logins, running **sp_dropserver** might generate an error similar to the following:</span></span>  
  
 `Server: Msg 15190, Level 16, State 1, Procedure sp_dropserver, Line 44 There are still remote logins for the server 'SERVER1'.`  
  
 <span data-ttu-id="ef914-143">Para solucionar el error, debe quitar los inicios de sesión remotos de este servidor.</span><span class="sxs-lookup"><span data-stu-id="ef914-143">To resolve the error, you must drop remote logins for this server.</span></span>  
  
#### <a name="to-drop-remote-logins"></a><span data-ttu-id="ef914-144">Para quitar inicios de sesión remotos</span><span class="sxs-lookup"><span data-stu-id="ef914-144">To drop remote logins</span></span>  
  
-   <span data-ttu-id="ef914-145">Para una instancia predeterminada, ejecute el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="ef914-145">For a default instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name;  
    GO  
    ```  
  
-   <span data-ttu-id="ef914-146">Para una instancia con nombre, ejecute el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="ef914-146">For a named instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name\instancename;  
    GO  
    ```  
  
 <span data-ttu-id="ef914-147">**Configuraciones de servidores vinculados:** el equipo que realiza la operación de cambio de nombre afectará a las configuraciones de los servidores vinculados.</span><span class="sxs-lookup"><span data-stu-id="ef914-147">**Linked Server Configurations** - Linked server configurations will be affected by the computer renaming operation.</span></span> <span data-ttu-id="ef914-148">Utilice `sp_addlinkedserver` o `sp_setnetname` para actualizar las referencias de nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="ef914-148">Use `sp_addlinkedserver` or `sp_setnetname` to update computer name references.</span></span> <span data-ttu-id="ef914-149">Para obtener más información, vea [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) o [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ef914-149">For more information, see the [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) or [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span></span>  
  
 <span data-ttu-id="ef914-150">**Nombres de alias de cliente:** la operación de cambio de nombre de equipo afectará a los alias de cliente que usen canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="ef914-150">**Client Alias Names** - Client aliases that use named pipes will be affected by the computer renaming operation.</span></span> <span data-ttu-id="ef914-151">Por ejemplo, si se creó un alias "PROD_SRVR" para señalar a SRVR1 y usa el protocolo de canalizaciones con nombre, el nombre de la canalización será similar a `\\SRVR1\pipe\sql\query`.</span><span class="sxs-lookup"><span data-stu-id="ef914-151">For example, if an alias "PROD_SRVR" was created to point to SRVR1 and uses the named pipes protocol, the pipe name will look like `\\SRVR1\pipe\sql\query`.</span></span> <span data-ttu-id="ef914-152">Una vez cambiado el nombre del equipo, la ruta de acceso de la canalización con nombre ya no será válida.</span><span class="sxs-lookup"><span data-stu-id="ef914-152">After the computer is renamed, the path of the named pipe will no longer be valid and.</span></span> <span data-ttu-id="ef914-153">Para obtener más información sobre las canalizaciones con nombre, vea el tema sobre cómo [crear una cadena de conexión válida con canalizaciones con nombre](https://go.microsoft.com/fwlink/?LinkId=111063).</span><span class="sxs-lookup"><span data-stu-id="ef914-153">For more information about named pipes, see the [Creating a Valid Connection String Using Named Pipes](https://go.microsoft.com/fwlink/?LinkId=111063).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef914-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef914-154">See Also</span></span>  
 [<span data-ttu-id="ef914-155">Instalar SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ef914-155">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
