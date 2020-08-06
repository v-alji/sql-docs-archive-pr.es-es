---
title: Establecer la opción de configuración del servidor Bloqueos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- locks option [SQL Server]
ms.assetid: b0cf0f86-7652-4574-a9fb-908e10d03973
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e45f4cc539be585966eb0beb30d4938b504c3419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750146"
---
# <a name="configure-the-locks-server-configuration-option"></a><span data-ttu-id="4b8ba-102">Establecer la opción de configuración del servidor Bloqueos</span><span class="sxs-lookup"><span data-stu-id="4b8ba-102">Configure the locks Server Configuration Option</span></span>
  <span data-ttu-id="4b8ba-103">En este tema se describe cómo establecer la opción de configuración del servidor **bloqueos** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b8ba-103">This topic describes how to configure the **locks** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4b8ba-104">La opción de **bloqueos** establece el número máximo de bloqueos disponibles, limitando de este modo la cantidad de memoria que el [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usa para ellos.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-104">The **locks** option sets the maximum number of available locks, thereby limiting the amount of memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for them.</span></span> <span data-ttu-id="4b8ba-105">El valor predeterminado es 0, lo que permite al [!INCLUDE[ssDE](../../includes/ssde-md.md)] asignar y cancelar la asignación de estructuras de bloqueo de manera dinámica a partir de los requisitos variables del sistema.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-105">The default setting is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically, based on changing system requirements.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="4b8ba-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4b8ba-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4b8ba-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4b8ba-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4b8ba-108">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="4b8ba-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4b8ba-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4b8ba-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4b8ba-110">**Para configurar la opción de bloqueos, use:**</span><span class="sxs-lookup"><span data-stu-id="4b8ba-110">**To configure the locks option, using:**</span></span>  
  
     [<span data-ttu-id="4b8ba-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b8ba-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4b8ba-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b8ba-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="4b8ba-113">**Seguimiento:**  [Después de configurar la opción de bloqueos](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="4b8ba-113">**Follow Up:**  [After you configure the locks option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4b8ba-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4b8ba-114">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4b8ba-115">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="4b8ba-115">Recommendations</span></span>  
  
-   <span data-ttu-id="4b8ba-116">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-116">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="4b8ba-117">Cuando se inicia el servidor con un valor de 0 para **bloqueos** , el administrador de bloqueos obtendrá suficiente memoria del [!INCLUDE[ssDE](../../includes/ssde-md.md)] para un grupo inicial de 2.500 estructuras de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-117">When the server is started with **locks** set to 0, the lock manager acquires sufficient memory from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for an initial pool of 2,500 lock structures.</span></span> <span data-ttu-id="4b8ba-118">A medida que se agota el grupo de bloqueos, se adquiere más memoria para el grupo.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-118">As the lock pool is exhausted, additional memory is acquired for the pool.</span></span>  
  
     <span data-ttu-id="4b8ba-119">Generalmente, si se necesita más memoria para el grupo de bloqueos que la disponible en el bloque de memoria del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , y hay más memoria en el equipo (no se ha alcanzado el umbral especificado en la opción **Memoria de servidor máxima** ), el [!INCLUDE[ssDE](../../includes/ssde-md.md)] asignará memoria de manera dinámica para satisfacer la solicitud de bloqueos.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-119">Generally, if more memory is required for the lock pool than is available in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool, and more computer memory is available (the **max server memory** threshold has not been reached), the [!INCLUDE[ssDE](../../includes/ssde-md.md)] allocates memory dynamically to satisfy the request for locks.</span></span> <span data-ttu-id="4b8ba-120">No obstante, si la asignación de esa memoria puede causar la paginación en el sistema operativo (por ejemplo, si se está ejecutando otra aplicación en el mismo equipo que una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y está utilizando esa memoria), no se asignará más espacio para bloqueos.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-120">However, if allocating that memory would cause paging at the operating system level (for example, if another application is running on the same computer as an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and using that memory), more lock space is not allocated.</span></span> <span data-ttu-id="4b8ba-121">El grupo de bloqueos dinámicos no obtendrá más del 60% de la memoria asignada para el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b8ba-121">The dynamic lock pool does not acquire more than 60 percent of the memory allocated to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="4b8ba-122">Cuando el grupo de bloqueos alcanza el 60% de la memoria obtenida por una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)], o cuando ya no queda más memoria disponible en el equipo, se generará un error si se producen más solicitudes de bloqueos.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-122">After the lock pool has reached 60 percent of the memory acquired by an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or no more memory is available on the computer, further requests for locks generate an error.</span></span>  
  
     <span data-ttu-id="4b8ba-123">La configuración recomendada es permitir que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilice los bloqueos de manera dinámica.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-123">Allowing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use locks dynamically is the recommended configuration.</span></span> <span data-ttu-id="4b8ba-124">No obstante, puede establecer la opción **locks** e invalidar la capacidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para asignar recursos de bloqueo de manera dinámica.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-124">However, you can set **locks** and override the ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to allocate lock resources dynamically.</span></span> <span data-ttu-id="4b8ba-125">Cuando se selecciona un valor para **locks** distinto de 0, el [!INCLUDE[ssDE](../../includes/ssde-md.md)] no puede asignar más bloqueos que el número especificado en el valor **locks**.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-125">When **locks** is set to a value other than 0, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] cannot allocate more locks than the value specified in **locks**.</span></span> <span data-ttu-id="4b8ba-126">Aumente este valor si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muestra un mensaje en el que se indica que se ha superado el número de bloqueos disponibles.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-126">Increase this value if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a message that you have exceeded the number of available locks.</span></span> <span data-ttu-id="4b8ba-127">Como cada bloqueo consume memoria (96 bytes por bloqueo), el aumento de este valor puede requerir el aumento de la cantidad de memoria dedicada al servidor.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-127">Because each lock consumes memory (96 bytes per lock), increasing this value can require increasing the amount of memory dedicated to the server.</span></span>  
  
-   <span data-ttu-id="4b8ba-128">La opción **locks** también afecta al momento en el que se produce la ampliación de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-128">The **locks** option also affects when lock escalation occurs.</span></span> <span data-ttu-id="4b8ba-129">Cuando se selecciona el valor 0 para **locks** , la ampliación de bloqueo se produce cuando la memoria utilizada por las estructuras de bloqueo actuales alcanza el 40% del bloque de memoria del [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b8ba-129">When **locks** is set to 0, lock escalation occurs when the memory used by the current lock structures reaches 40 percent of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool.</span></span> <span data-ttu-id="4b8ba-130">Cuando se selecciona un valor distinto de 0 para **bloqueos** , la ampliación de bloqueo se produce cuando el número de bloqueos alcanza el 40% del valor especificado para **bloqueos**.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-130">When **locks** is not set to 0, lock escalation occurs when the number of locks reaches 40 percent of the value specified for **locks**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4b8ba-131">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4b8ba-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4b8ba-132">Permisos</span><span class="sxs-lookup"><span data-stu-id="4b8ba-132">Permissions</span></span>  
 <span data-ttu-id="4b8ba-133">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="4b8ba-134">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="4b8ba-135">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4b8ba-136">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b8ba-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="4b8ba-137">Para configurar la opción locks</span><span class="sxs-lookup"><span data-stu-id="4b8ba-137">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="4b8ba-138">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="4b8ba-139">Haga clic en el nodo **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="4b8ba-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="4b8ba-140">En **Paralelismo**, escriba el valor deseado para la opción **locks** .</span><span class="sxs-lookup"><span data-stu-id="4b8ba-140">Under **Parallelism**, type the desired value for the **locks** option.</span></span>  
  
     <span data-ttu-id="4b8ba-141">Use la opción **locks** para establecer el número máximo de bloqueos disponibles y limitar así la cantidad de memoria que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliza para los mismos.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-141">Use the **locks** option to set the maximum number of available locks, thereby limiting the amount of memory [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses for them.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4b8ba-142">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b8ba-142">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="4b8ba-143">Para configurar la opción locks</span><span class="sxs-lookup"><span data-stu-id="4b8ba-143">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="4b8ba-144">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b8ba-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4b8ba-145">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4b8ba-146">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4b8ba-147">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `locks` para establecer el número de bloqueos disponibles para todos los usuarios en `20000`.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `locks` option to set the number of locks available for all users to `20000`.</span></span>  
  
```sql  
Use AdventureWorks2012 ;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'locks', 20000;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="4b8ba-148">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4b8ba-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-locks-option"></a><a name="FollowUp"></a> <span data-ttu-id="4b8ba-149">Seguimiento: Después de configurar la opción de bloqueos</span><span class="sxs-lookup"><span data-stu-id="4b8ba-149">Follow Up: After you configure the locks option</span></span>  
 <span data-ttu-id="4b8ba-150">El servidor debe reiniciarse para que el valor surta efecto.</span><span class="sxs-lookup"><span data-stu-id="4b8ba-150">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b8ba-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b8ba-151">See Also</span></span>  
 <span data-ttu-id="4b8ba-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4b8ba-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="4b8ba-153">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4b8ba-153">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="4b8ba-154">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b8ba-154">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
