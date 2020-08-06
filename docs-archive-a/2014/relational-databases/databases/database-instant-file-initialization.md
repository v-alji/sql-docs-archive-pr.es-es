---
title: Inicialización instantánea de archivos de la base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- initializing files [SQL Server]
- instant file initializations [SQL Server]
- fast file initialization (SQL Server)
- file initialization [SQL Server]
ms.assetid: 1ad468f5-4f75-480b-aac6-0b01b048bd67
author: stevestein
ms.author: sstein
ms.openlocfilehash: dedd2c5b8d075dee8aeeb438904137558c664d95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672099"
---
# <a name="database-instant-file-initialization"></a><span data-ttu-id="f0877-102">Inicialización instantánea de archivos de la base de datos</span><span class="sxs-lookup"><span data-stu-id="f0877-102">Database Instant File Initialization</span></span>
  <span data-ttu-id="f0877-103">Los archivos de datos y registro se inicializan para sobrescribir los datos existentes que los archivos eliminados anteriormente hayan dejado en el disco.</span><span class="sxs-lookup"><span data-stu-id="f0877-103">Data and log files are initialized to overwrite any existing data left on the disk from previously deleted files.</span></span> <span data-ttu-id="f0877-104">Los archivos de datos y registro se inicializan por primera vez rellenando los archivos con ceros al realizar una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="f0877-104">Data and log files are first initialized by filling the files with zeros when you perform one of the following operations:</span></span>  
  
-   <span data-ttu-id="f0877-105">Crear una base de datos.</span><span class="sxs-lookup"><span data-stu-id="f0877-105">Create a database.</span></span>  
  
-   <span data-ttu-id="f0877-106">Añadir archivos, registros o datos a una base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="f0877-106">Add files, log or data, to an existing database.</span></span>  
  
-   <span data-ttu-id="f0877-107">Aumentar el tamaño de un archivo existente (incluidas las operaciones de crecimiento automático).</span><span class="sxs-lookup"><span data-stu-id="f0877-107">Increase the size of an existing file (including autogrow operations).</span></span>  
  
-   <span data-ttu-id="f0877-108">Restaurar una base de datos o un grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="f0877-108">Restore a database or filegroup.</span></span>  
  
 <span data-ttu-id="f0877-109">Inicializar los archivos hace que estas operaciones tarden más.</span><span class="sxs-lookup"><span data-stu-id="f0877-109">File initialization causes these operations to take longer.</span></span> <span data-ttu-id="f0877-110">Sin embargo, cuando los datos se escriben en los archivos por primera vez, el sistema operativo no tiene que rellenar los archivos con ceros.</span><span class="sxs-lookup"><span data-stu-id="f0877-110">However, when data is written to the files for the first time, the operating system does not have to fill the files with zeros.</span></span>  
  
## <a name="instant-file-initialization"></a><span data-ttu-id="f0877-111">Inicialización instantánea de archivos</span><span class="sxs-lookup"><span data-stu-id="f0877-111">Instant File Initialization</span></span>  
 <span data-ttu-id="f0877-112">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], los archivos de datos se pueden inicializar de forma instantánea.</span><span class="sxs-lookup"><span data-stu-id="f0877-112">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data files can be initialized instantaneously.</span></span> <span data-ttu-id="f0877-113">Esto permite ejecutar rápidamente las operaciones con archivos anteriormente mencionadas.</span><span class="sxs-lookup"><span data-stu-id="f0877-113">This allows for fast execution of the previously mentioned file operations.</span></span> <span data-ttu-id="f0877-114">La inicialización instantánea de archivos recupera espacio en disco utilizado sin rellenarlo con ceros.</span><span class="sxs-lookup"><span data-stu-id="f0877-114">Instant file initialization reclaims used disk space without filling that space with zeros.</span></span> <span data-ttu-id="f0877-115">En lugar de eso, el contenido del disco se sobrescribe al escribir nuevos datos en los archivos.</span><span class="sxs-lookup"><span data-stu-id="f0877-115">Instead, disk content is overwritten as new data is written to the files.</span></span> <span data-ttu-id="f0877-116">Los archivos de registro no se pueden inicializar de forma instantánea.</span><span class="sxs-lookup"><span data-stu-id="f0877-116">Log files cannot be initialized instantaneously.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0877-117">La inicialización instantánea de archivos solo está disponible en [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] , [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] o en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f0877-117">Instant file initialization is available only on [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] or [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="f0877-118">La inicialización instantánea de archivos solo está disponible si a la cuenta de servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) se le ha concedido SE_MANAGE_VOLUME_NAME.</span><span class="sxs-lookup"><span data-stu-id="f0877-118">Instant file initialization is only available if the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) service account has been granted SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="f0877-119">Los miembros del grupo de administradores de Windows tienen este derecho y pueden concederlo a otros usuarios añadiéndolos a la directiva de seguridad **Realizar tareas de mantenimiento del volumen** .</span><span class="sxs-lookup"><span data-stu-id="f0877-119">Members of the Windows Administrator group have this right and can grant it to other users by adding them to the **Perform Volume Maintenance Tasks** security policy.</span></span> <span data-ttu-id="f0877-120">Para obtener más información sobre la asignación de derechos de usuario, consulte la documentación de Windows.</span><span class="sxs-lookup"><span data-stu-id="f0877-120">For more information about assigning user rights, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="f0877-121">La inicialización instantánea de archivos no está disponible cuando el TDE está habilitado.</span><span class="sxs-lookup"><span data-stu-id="f0877-121">Instant file initialization is not available when TDE is enabled.</span></span>  
  
 <span data-ttu-id="f0877-122">Para conceder a una cuenta el permiso `Perform volume maintenance tasks` :</span><span class="sxs-lookup"><span data-stu-id="f0877-122">To grant an account the `Perform volume maintenance tasks` permission:</span></span>  
  
1.  <span data-ttu-id="f0877-123">En el ordenador en el que se creará el archivo de copia de seguridad, abra la aplicación `Local Security Policy` (`secpol.msc`).</span><span class="sxs-lookup"><span data-stu-id="f0877-123">On the computer where the backup file will be created, open the `Local Security Policy` application (`secpol.msc`).</span></span>  
  
2.  <span data-ttu-id="f0877-124">En el panel izquierdo, expanda **Directivas locales**y, a continuación, haga clic en **Asignación de derechos de usuario**.</span><span class="sxs-lookup"><span data-stu-id="f0877-124">In the left pane, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
3.  <span data-ttu-id="f0877-125">En el panel derecho, haga doble clic en **Realizar tareas de mantenimiento del volumen**.</span><span class="sxs-lookup"><span data-stu-id="f0877-125">In the right pane, double-click **Perform volume maintenance tasks**.</span></span>  
  
4.  <span data-ttu-id="f0877-126">Haga clic en **Agregar usuario o grupo** y añada las cuentas de usuario que se utilicen para las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f0877-126">Click **Add User or Group** and add any user accounts that are used for backups.</span></span>  
  
5.  <span data-ttu-id="f0877-127">Haga clic en **aplicar**y, a continuación, cierre todos los `Local Security Policy` cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f0877-127">Click **Apply**, and then close all `Local Security Policy` dialog boxes.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="f0877-128">Consideraciones sobre la seguridad</span><span class="sxs-lookup"><span data-stu-id="f0877-128">Security Considerations</span></span>  
 <span data-ttu-id="f0877-129">Como el contenido del disco eliminado solo se sobrescribe cuando se escriben nuevos datos a los archivos, una entidad de seguridad no autorizada puede acceder al contenido eliminado.</span><span class="sxs-lookup"><span data-stu-id="f0877-129">Because the deleted disk content is overwritten only as new data is written to the files, the deleted content might be accessed by an unauthorized principal.</span></span> <span data-ttu-id="f0877-130">Mientras el archivo de la base de datos se adjunte a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], esta amenaza de divulgación de la información se reduce mediante la lista de control de acceso discrecional (DACL) del archivo.</span><span class="sxs-lookup"><span data-stu-id="f0877-130">While the database file is attached to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this information disclosure threat is reduced by the discretionary access control list (DACL) on the file.</span></span> <span data-ttu-id="f0877-131">Esta DACL permite acceder al archivo solo a la cuenta de servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y al administrador local.</span><span class="sxs-lookup"><span data-stu-id="f0877-131">This DACL allows file access only to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the local administrator.</span></span> <span data-ttu-id="f0877-132">Sin embargo, cuando el archivo está separado, un usuario o servicio que no tenga SE_MANAGE_VOLUME_NAME puede acceder a él.</span><span class="sxs-lookup"><span data-stu-id="f0877-132">However, when the file is detached, it may be accessed by a user or service that does not have SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="f0877-133">Existe una amenaza parecida al crear una copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f0877-133">A similar threat exists when the database is backed up.</span></span> <span data-ttu-id="f0877-134">El contenido eliminado puede estar disponible para un usuario servicio no autorizado si el archivo de copia de seguridad no está protegido con una DACL apropiada.</span><span class="sxs-lookup"><span data-stu-id="f0877-134">The deleted content can become available to an unauthorized user or service if the backup file is not protected with an appropriate DACL.</span></span>  
  
 <span data-ttu-id="f0877-135">Si le preocupa la posibilidad de que se divulgue contenido eliminado, debe realizar una o ambas de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f0877-135">If the potential for disclosing deleted content is a concern, you should do one or both of the following:</span></span>  
  
-   <span data-ttu-id="f0877-136">Asegúrese siempre de que los archivos separados y los archivos de copia de seguridad tienen DACL restrictivas.</span><span class="sxs-lookup"><span data-stu-id="f0877-136">Always make sure that any detached data files and backup files have restrictive DACLs.</span></span>  
  
-   <span data-ttu-id="f0877-137">Deshabilite la inicialización instantánea de archivos para la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revocando SE_MANAGE_VOLUME_NAME de la cuenta de servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0877-137">Disable instant file initialization for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by revoking SE_MANAGE_VOLUME_NAME from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0877-138">Deshabilitar la inicialización instantánea de archivos solo afecta a los archivos que se han creado o se ha aumentado su tamaño después de que el derecho del usuario se revocara.</span><span class="sxs-lookup"><span data-stu-id="f0877-138">Disabling instant file initialization only affects files that are created or increased in size after the user right is revoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0877-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0877-139">See Also</span></span>  
 [<span data-ttu-id="f0877-140">CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0877-140">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
