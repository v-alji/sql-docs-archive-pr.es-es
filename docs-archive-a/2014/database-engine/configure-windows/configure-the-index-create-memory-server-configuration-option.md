---
title: Establecer la opción de configuración del servidor Memoria para creación de índices | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- index create memory option
ms.assetid: 3d722d9b-bada-4bf5-a9d7-bfc556bb4915
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd0aeb93d3fb68089338335068fdaaae19919fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745967"
---
# <a name="configure-the-index-create-memory-server-configuration-option"></a><span data-ttu-id="5da0e-102">Establecer la opción de configuración del servidor Memoria para creación de índices</span><span class="sxs-lookup"><span data-stu-id="5da0e-102">Configure the index create memory Server Configuration Option</span></span>
  <span data-ttu-id="5da0e-103">En este tema se describe cómo establecer la opción de configuración del servidor **memoria para creación de índices** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5da0e-103">This topic describes how to configure the **index create memory** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5da0e-104">La opción de **memoria para creación de índices** controla la cantidad máxima de memoria asignada inicialmente para la creación de índices.</span><span class="sxs-lookup"><span data-stu-id="5da0e-104">The **index create memory** option controls the maximum amount of memory initially allocated for creating indexes.</span></span> <span data-ttu-id="5da0e-105">El valor predeterminado para esta opción es 0 (configuración automática).</span><span class="sxs-lookup"><span data-stu-id="5da0e-105">The default value for this option is 0 (self-configuring).</span></span> <span data-ttu-id="5da0e-106">Si más adelante se necesita más memoria para la creación de índices y hay memoria disponible, el servidor la utilizará; por lo tanto, se excederá el valor de esta opción.</span><span class="sxs-lookup"><span data-stu-id="5da0e-106">If more memory is later needed for index creation and the memory is available, the server will use it; thereby, exceeding the setting of this option.</span></span> <span data-ttu-id="5da0e-107">Si no hay más memoria disponible, la creación de índices continuará utilizando la asignada.</span><span class="sxs-lookup"><span data-stu-id="5da0e-107">If additional memory is not available, the index creation will continue using the memory already allocated.</span></span>  
  
 <span data-ttu-id="5da0e-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5da0e-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5da0e-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5da0e-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5da0e-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5da0e-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5da0e-111">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="5da0e-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5da0e-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5da0e-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5da0e-113">**Para configurar la opción de memoria para creación de índices, use:**</span><span class="sxs-lookup"><span data-stu-id="5da0e-113">**To configure the index create memory option, using:**</span></span>  
  
     [<span data-ttu-id="5da0e-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5da0e-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5da0e-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5da0e-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="5da0e-116">**Seguimiento:**  [Después de configurar la opción de memoria para creación de índices](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5da0e-116">**Follow Up:**  [After you configure the index create memory option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5da0e-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5da0e-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5da0e-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5da0e-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5da0e-119">El valor de la opción de **memoria mínima por consulta** tiene prioridad sobre la opción **memoria para creación de índices**.</span><span class="sxs-lookup"><span data-stu-id="5da0e-119">The setting of the **min memory per query** option has precedence over the **index create memory** option.</span></span> <span data-ttu-id="5da0e-120">Si cambia ambas opciones y el valor de **memoria para creación de índices** es inferior al de **memoria mínima por consulta**, aparecerá un mensaje de advertencia, pero se establecerá el valor.</span><span class="sxs-lookup"><span data-stu-id="5da0e-120">If you change both options and the **index create memory** is less than **min memory per query**, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="5da0e-121">Durante la ejecución de consultas, recibirá una advertencia similar.</span><span class="sxs-lookup"><span data-stu-id="5da0e-121">During query execution, you receive a similar warning.</span></span>  
  
-   <span data-ttu-id="5da0e-122">Al usar tablas e índices con particiones, los requisitos de memoria mínima para la creación de índices pueden aumentar de forma significativa si hay índices con particiones no alineados con un alto grado de paralelismo.</span><span class="sxs-lookup"><span data-stu-id="5da0e-122">When using partitioned tables and indexes, the minimum memory requirements for index creation may increase significantly if there are non-aligned partitioned indexes and a high degree of parallelism.</span></span> <span data-ttu-id="5da0e-123">Esta opción controla la cantidad inicial total de memoria asignada para todas las particiones de índice en una sola operación de creación de índices.</span><span class="sxs-lookup"><span data-stu-id="5da0e-123">This option controls the total initial amount of memory allocated for all index partitions in a single index creation operation.</span></span> <span data-ttu-id="5da0e-124">La consulta se terminará con un mensaje de error si la cantidad establecida por esta opción es inferior al mínimo necesario para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="5da0e-124">The query will terminate with an error message if the amount set by this option is less than the minimum required to run the query.</span></span>  
  
-   <span data-ttu-id="5da0e-125">El valor de ejecución de esta opción no excederá la cantidad real de memoria que se puede usar para el sistema operativo y la plataforma de hardware en los que se ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5da0e-125">The run value for this option will not exceed the actual amount of memory that can be used for the operating system and hardware platform on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="5da0e-126">En los sistemas operativos de 32 bits, el valor de ejecución será inferior a 3 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="5da0e-126">On 32-bit operating systems, the run value will be less than 3 gigabytes (GB).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5da0e-127">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="5da0e-127">Recommendations</span></span>  
  
-   <span data-ttu-id="5da0e-128">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="5da0e-128">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="5da0e-129">La opción **Memoria para creación de índices** se configura automáticamente y, por lo general, funciona sin necesidad de ajuste alguno.</span><span class="sxs-lookup"><span data-stu-id="5da0e-129">The **index create memory** option is self-configuring and usually works without requiring adjustment.</span></span> <span data-ttu-id="5da0e-130">No obstante, si tiene dificultades para crear índices, puede probar a aumentar el valor de esta opción a partir del valor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5da0e-130">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5da0e-131">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5da0e-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5da0e-132">Permisos</span><span class="sxs-lookup"><span data-stu-id="5da0e-132">Permissions</span></span>  
 <span data-ttu-id="5da0e-133">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="5da0e-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="5da0e-134">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5da0e-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="5da0e-135">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="5da0e-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5da0e-136">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5da0e-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="5da0e-137">Para configurar la opción index create memory</span><span class="sxs-lookup"><span data-stu-id="5da0e-137">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="5da0e-138">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5da0e-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5da0e-139">Haga clic en el nodo **Memoria** .</span><span class="sxs-lookup"><span data-stu-id="5da0e-139">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="5da0e-140">En **Memoria de creación de índice**, escriba o seleccione el valor que desee para la opción index create memory.</span><span class="sxs-lookup"><span data-stu-id="5da0e-140">Under **Index creation memory**, type or select the desired value for the index create memory option.</span></span>  
  
     <span data-ttu-id="5da0e-141">Utilice la opción **index create memory** para controlar la cantidad de memoria que se utiliza para ordenaciones de creación de índices.</span><span class="sxs-lookup"><span data-stu-id="5da0e-141">Use the **index create memory** option to control the amount of memory used by index creation sorts.</span></span> <span data-ttu-id="5da0e-142">La opción **Memoria para creación de índices** se configura automáticamente y, en la mayoría de los casos, debería funcionar sin necesidad de ajuste alguno.</span><span class="sxs-lookup"><span data-stu-id="5da0e-142">The **index create memory** option is self-configuring and should work in most cases without requiring adjustment.</span></span> <span data-ttu-id="5da0e-143">No obstante, si tiene dificultades para crear índices, puede probar a aumentar el valor de esta opción a partir del valor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5da0e-143">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span> <span data-ttu-id="5da0e-144">Las ordenaciones de consultas se controlan mediante la opción de **memoria mínima por consulta** .</span><span class="sxs-lookup"><span data-stu-id="5da0e-144">Query sorts are controlled through the **min memory per query** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5da0e-145">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5da0e-145">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="5da0e-146">Para configurar la opción index create memory</span><span class="sxs-lookup"><span data-stu-id="5da0e-146">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="5da0e-147">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5da0e-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5da0e-148">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5da0e-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5da0e-149">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5da0e-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5da0e-150">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `index create memory` en `4096`.</span><span class="sxs-lookup"><span data-stu-id="5da0e-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `index create memory` option to `4096`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
EXEC sp_configure 'index create memory', 4096  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="5da0e-151">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5da0e-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-index-create-memory-option"></a><a name="FollowUp"></a> <span data-ttu-id="5da0e-152">Seguimiento: Después de configurar la opción de memoria para creación de índices</span><span class="sxs-lookup"><span data-stu-id="5da0e-152">Follow Up: After you configure the index create memory option</span></span>  
 <span data-ttu-id="5da0e-153">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="5da0e-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da0e-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5da0e-154">See Also</span></span>  
 <span data-ttu-id="5da0e-155">[sys.configurations&#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5da0e-155">[sys.configurations &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span></span>  
 <span data-ttu-id="5da0e-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5da0e-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="5da0e-157">[Opciones de configuración de memoria del servidor](server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="5da0e-157">[Server Memory Server Configuration Options](server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="5da0e-158">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5da0e-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="5da0e-159">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5da0e-159">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
