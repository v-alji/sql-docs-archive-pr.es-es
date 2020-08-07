---
title: Función clasificadora del regulador de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function
- user-defined functions [SQL Server], classifier function
- classifier function [SQL Server]
- classifier function [SQL Server], overview
ms.assetid: 64c25012-7068-476f-afa2-0b4f3adde9a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69b6fd10ac0adc6f76925e0d41f110b917111466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745691"
---
# <a name="resource-governor-classifier-function"></a><span data-ttu-id="5febd-102">Resource Governor Classifier Function</span><span class="sxs-lookup"><span data-stu-id="5febd-102">Resource Governor Classifier Function</span></span>
  <span data-ttu-id="5febd-103">El proceso de clasificación del regulador de recursos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asigna las sesiones de entrada a un grupo de carga de trabajo según las características de la sesión.</span><span class="sxs-lookup"><span data-stu-id="5febd-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource governor classification process assigns incoming sessions to a workload group based on the characteristics of the session.</span></span> <span data-ttu-id="5febd-104">Puede adaptar la lógica de clasificación escribiendo una función definida por el usuario, denominada función clasificadora.</span><span class="sxs-lookup"><span data-stu-id="5febd-104">You can tailor the classification logic by writing a user-defined function, called a classifier function.</span></span>  
  
## <a name="classification"></a><span data-ttu-id="5febd-105">clasificación</span><span class="sxs-lookup"><span data-stu-id="5febd-105">Classification</span></span>  
 <span data-ttu-id="5febd-106">El regulador de recursos admite la clasificación de sesiones de entrada.</span><span class="sxs-lookup"><span data-stu-id="5febd-106">Resource Governor supports the classification of incoming sessions.</span></span> <span data-ttu-id="5febd-107">La clasificación se basa en un conjunto de criterios escritos por el usuario contenidos en una función.</span><span class="sxs-lookup"><span data-stu-id="5febd-107">Classification is based on a set of user-written criteria contained in a function.</span></span> <span data-ttu-id="5febd-108">Los resultados de la lógica de la función permiten al regulador de recursos clasificar las sesiones en los grupos de cargas de trabajo existentes.</span><span class="sxs-lookup"><span data-stu-id="5febd-108">The results of the function logic enable Resource Governor to classify sessions into existing workload groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5febd-109">El grupo de cargas de trabajo interno se rellena con las solicitudes que solo son para uso interno.</span><span class="sxs-lookup"><span data-stu-id="5febd-109">The internal workload group is populated with requests that are for internal use only.</span></span> <span data-ttu-id="5febd-110">No se pueden cambiar los criterios que se usan para enrutar estas solicitudes y no se pueden clasificar las solicitudes en el grupo de cargas de trabajo interno.</span><span class="sxs-lookup"><span data-stu-id="5febd-110">You cannot change the criteria used for routing these requests and you cannot classify requests into the internal workload group.</span></span>  
  
 <span data-ttu-id="5febd-111">Puede escribir una función escalar que contenga la lógica que se utiliza para asignar las sesiones entrantes a un grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5febd-111">You can write a scalar function that contains the logic that is used to assign incoming sessions to a workload group.</span></span> <span data-ttu-id="5febd-112">Para poder ejecutar esta función, debe completar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5febd-112">Before you can use this function, you must complete the following actions:</span></span>  
  
-   <span data-ttu-id="5febd-113">Crear y registrar la función utilizando la instrucción ALTER RESOURCE GOVERNOR.</span><span class="sxs-lookup"><span data-stu-id="5febd-113">Create and register the function using the ALTER RESOURCE GOVERNOR statement.</span></span> <span data-ttu-id="5febd-114">Para obtener más información, vea [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5febd-114">For more information, see [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span></span>  
  
-   <span data-ttu-id="5febd-115">Actualizar la configuración del regulador de recursos utilizando la instrucción ALTER RESOURCE GOVERNOR con el parámetro RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="5febd-115">Update the Resource Governor configuration using the ALTER RESOURCE GOVERNOR statement with the RECONFIGURE parameter.</span></span>  
  
 <span data-ttu-id="5febd-116">Después de crear la función y aplicar los cambios de configuración, el clasificador del regulador de recursos utilizará el nombre del grupo de cargas de trabajo devuelto por la función para enviar una nueva solicitud al grupo de cargas de trabajo adecuado.</span><span class="sxs-lookup"><span data-stu-id="5febd-116">After you create the function and apply the configuration changes, the Resource Governor classifier will use the workload group name returned by the function to send a new request to the appropriate workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5febd-117">La sesión del cliente puede expirar si la función de clasificación no se completa dentro del tiempo de espera especificado para el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5febd-117">The client session may time out if the classification function does not complete within the specified time-out for the login.</span></span> <span data-ttu-id="5febd-118">El tiempo de espera de inicio de sesión es una propiedad del cliente y como a tal, el servidor no está al tanto de los tiempos de espera. Una función clasificadora que se ejecute durante un tiempo prolongado puede dejar al servidor con conexiones huérfanas durante largos períodos de tiempo.</span><span class="sxs-lookup"><span data-stu-id="5febd-118">Login time-out is a client property and as such, the server is unaware of a time-out. A long-running classifier function can leave the server with orphaned connections for long periods.</span></span> <span data-ttu-id="5febd-119">Es importante que cree funciones clasificadoras que finalicen su ejecución antes de que se acabe el tiempo de espera de la conexión.</span><span class="sxs-lookup"><span data-stu-id="5febd-119">It is important that you create classifier functions that finish executing before a connection time-out.</span></span>  
  
 <span data-ttu-id="5febd-120">La función definida por el usuario tiene las siguientes características y comportamientos:</span><span class="sxs-lookup"><span data-stu-id="5febd-120">The user-defined function has the following characteristics and behaviors:</span></span>  
  
-   <span data-ttu-id="5febd-121">La función definida por el usuario se evalúa para cada nueva sesión, incluso cuando la agrupación de conexiones esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="5febd-121">The user-defined function is evaluated for every new session, even when connection pooling is enabled.</span></span>  
  
-   <span data-ttu-id="5febd-122">La función definida por el usuario proporciona el contexto del grupo de cargas de trabajo para la sesión.</span><span class="sxs-lookup"><span data-stu-id="5febd-122">The user-defined function gives workload group context for the session.</span></span> <span data-ttu-id="5febd-123">Una vez determinada la pertenencia al grupo, la sesión se enlaza al grupo de cargas de trabajo durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="5febd-123">After group membership is determined, the session is bound to the workload group for the lifetime of the session.</span></span>  
  
-   <span data-ttu-id="5febd-124">Si la función definida por el usuario devuelve NULL, predeterminado o el nombre de un grupo que no existe, la sesión recibirá el contexto del grupo de cargas de trabajo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5febd-124">If the user-defined function returns NULL, default, or the name of non-existent group the session is given the default workload group context.</span></span> <span data-ttu-id="5febd-125">La sesión también recibe el contexto predeterminado si se produce un error en la función por cualquier motivo.</span><span class="sxs-lookup"><span data-stu-id="5febd-125">The session is also given the default context if the function fails for any reason.</span></span>  
  
-   <span data-ttu-id="5febd-126">La función se debería definir con ámbito del servidor (base de datos maestra).</span><span class="sxs-lookup"><span data-stu-id="5febd-126">The function should be defined with server scope (master database).</span></span>  
  
-   <span data-ttu-id="5febd-127">La designación de la función clasificadora definida por el usuario solo surte efecto después de ejecutar ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="5febd-127">The classifier user-defined function designation only takes effect after ALTER RESOURCE GOVERNOR RECONFIGURE is executed.</span></span>  
  
-   <span data-ttu-id="5febd-128">Solo se puede definir una función definida por el usuario como clasificador a la vez.</span><span class="sxs-lookup"><span data-stu-id="5febd-128">Only one user-defined function can be designated as a classifier at a time.</span></span>  
  
-   <span data-ttu-id="5febd-129">La función del clasificador definida por el usuario no se puede eliminar o modificar a menos que se quite su estado de clasificador.</span><span class="sxs-lookup"><span data-stu-id="5febd-129">The classifier user-defined function cannot be dropped or altered unless its classifier status is removed.</span></span>  
  
-   <span data-ttu-id="5febd-130">Con la ausencia de una función del clasificador definida por el usuario, todas las sesiones se clasifican en el grupo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5febd-130">In the absence of a classifier user-defined function, all sessions are classified into the default group.</span></span>  
  
-   <span data-ttu-id="5febd-131">El grupo de cargas de trabajo devuelto por la función clasificadora está fuera del ámbito de la restricción del enlace de esquema.</span><span class="sxs-lookup"><span data-stu-id="5febd-131">The workload group returned by the classifier function is outside the scope of the schema-binding restriction.</span></span> <span data-ttu-id="5febd-132">Por ejemplo, no puede quitar una tabla, pero puede quitar un grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5febd-132">For example, you cannot drop a table, but you can drop a workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5febd-133">Se recomienda habilitar la conexión de administrador dedicada (DAC) en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5febd-133">We recommend enabling the Dedicated Administrator Connection (DAC) on the server.</span></span> <span data-ttu-id="5febd-134">La conexión de administrador dedicada no está sujeta a la clasificación del regulador de recursos y se puede utilizar para supervisar y solucionar problemas de una función clasificadora.</span><span class="sxs-lookup"><span data-stu-id="5febd-134">The DAC is not subject to Resource Governor classification and can be used to monitor and troubleshoot a classifier function.</span></span> <span data-ttu-id="5febd-135">Para obtener más información, vea [Conexión de diagnóstico para administradores de bases de datos](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="5febd-135">For more information, see [Diagnostic Connection for Database Administrators](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span></span> <span data-ttu-id="5febd-136">Si no hay disponible una conexión de administrador dedicada para solucionar los problemas, la otra opción es reiniciar el sistema en modo de usuario único.</span><span class="sxs-lookup"><span data-stu-id="5febd-136">If a DAC is not available for troubleshooting, the other option is to restart the system in single user mode.</span></span> <span data-ttu-id="5febd-137">Aunque el modo de usuario único no está sujeto a clasificación, no ofrece la capacidad de diagnosticar la clasificación del regulador de recursos mientras se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="5febd-137">Although single user mode is not subject to classification, it does not give you the ability to diagnose Resource Governor classification while it is running.</span></span>  
  
### <a name="classification-process"></a><span data-ttu-id="5febd-138">Proceso de clasificación</span><span class="sxs-lookup"><span data-stu-id="5febd-138">Classification Process</span></span>  
 <span data-ttu-id="5febd-139">En el contexto del regulador de recursos, el proceso de inicio de sesión para una sesión consta de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5febd-139">In the context of Resource Governor, the login process for a session consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="5febd-140">Autenticación del inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="5febd-140">Login authentication</span></span>  
  
2.  <span data-ttu-id="5febd-141">Ejecución del desencadenador LOGON</span><span class="sxs-lookup"><span data-stu-id="5febd-141">LOGON trigger execution</span></span>  
  
3.  <span data-ttu-id="5febd-142">clasificación</span><span class="sxs-lookup"><span data-stu-id="5febd-142">Classification</span></span>  
  
 <span data-ttu-id="5febd-143">Cuando la clasificación se inicia, el regulador de recursos ejecuta la función clasificadora y utiliza el valor devuelto por la función para enviar solicitudes al grupo de cargas de trabajo adecuado.</span><span class="sxs-lookup"><span data-stu-id="5febd-143">When classification starts, Resource Governor executes the classifier function and uses the value returned by the function to send requests to the appropriate workload group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5febd-144">La información sobre la ejecución de la función clasificadora y sobre los desencadenadores LOGON se expone en [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) y [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5febd-144">Information about the execution of the classifier function and LOGON triggers is exposed in [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span></span>  
  
## <a name="classification-function-tasks"></a><span data-ttu-id="5febd-145">Tareas de función de clasificación</span><span class="sxs-lookup"><span data-stu-id="5febd-145">Classification Function Tasks</span></span>  
  
|<span data-ttu-id="5febd-146">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="5febd-146">Task Description</span></span>|<span data-ttu-id="5febd-147">Tema</span><span class="sxs-lookup"><span data-stu-id="5febd-147">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="5febd-148">Describe cómo crear y probar una función clasificadora definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5febd-148">Describes how to create and test a classifier user-defined function.</span></span>|[<span data-ttu-id="5febd-149">Crear y probar una función clasificadora definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="5febd-149">Create and Test a Classifier User-Defined Function</span></span>](create-and-test-a-classifier-user-defined-function.md)|  
  
## <a name="see-also"></a><span data-ttu-id="5febd-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5febd-150">See Also</span></span>  
 <span data-ttu-id="5febd-151">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="5febd-151">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="5febd-152">[Habilitar el regulador de recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="5febd-152">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="5febd-153">[Grupo de recursos de servidor del regulador de recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="5febd-153">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="5febd-154">[Grupos de cargas de trabajo del regulador de recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="5febd-154">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="5febd-155">[Configurar el regulador de recursos utilizando una plantilla](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="5febd-155">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="5febd-156">Ver las propiedades del regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="5febd-156">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
