---
title: Configurar la opción de configuración del servidor Memoria mínima por consulta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- memory [SQL Server], queries
- minimum query memory
- queries [SQL Server], memory
- min memory per query option
ms.assetid: ecd3fb79-b4a6-432f-9ef5-530e0d42d5a6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 56d85f36840f0900c8b5e986334a99ba610d3930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674332"
---
# <a name="configure-the-min-memory-per-query-server-configuration-option"></a><span data-ttu-id="25b08-102">Configurar la opción de configuración del servidor Memoria mínima por consulta</span><span class="sxs-lookup"><span data-stu-id="25b08-102">Configure the min memory per query Server Configuration Option</span></span>
  <span data-ttu-id="25b08-103">En este tema se describe cómo configurar la `min memory per query` opción de configuración del servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25b08-103">This topic describes how to configure the `min memory per query` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="25b08-104">La `min memory per query` opción especifica la cantidad mínima de memoria (en kilobytes) que se asignará para la ejecución de una consulta.</span><span class="sxs-lookup"><span data-stu-id="25b08-104">The `min memory per query` option specifies the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span> <span data-ttu-id="25b08-105">Por ejemplo, si `min memory per query` se establece en 2.048 KB, se garantiza que la consulta obtiene al menos esa cantidad total de memoria.</span><span class="sxs-lookup"><span data-stu-id="25b08-105">For example, if `min memory per query` is set to 2,048 KB, the query is guaranteed to get at least that much total memory.</span></span> <span data-ttu-id="25b08-106">El valor predeterminado es 1.024 KB.</span><span class="sxs-lookup"><span data-stu-id="25b08-106">The default value is 1,024 KB.</span></span> <span data-ttu-id="25b08-107">El valor mínimo es 512 KB y el valor máximo es 2 147 483 647 KB (2 GB).</span><span class="sxs-lookup"><span data-stu-id="25b08-107">The minimum value 512 KB, and the maximum is 2,147,483,647 KB (2 GB).</span></span>  
  
 <span data-ttu-id="25b08-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="25b08-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="25b08-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="25b08-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="25b08-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="25b08-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="25b08-111">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="25b08-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="25b08-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="25b08-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="25b08-113">**Para configurar la opción de memoria mínima por consulta, use:**</span><span class="sxs-lookup"><span data-stu-id="25b08-113">**To configure the min memory per query option, using:**</span></span>  
  
     [<span data-ttu-id="25b08-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25b08-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="25b08-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="25b08-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="25b08-116">**Seguimiento:**  [Después de configurar la opción de memoria mínima por consulta](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="25b08-116">**Follow Up:**  [After you configure the min memory per query option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="25b08-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="25b08-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="25b08-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="25b08-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="25b08-119">La cantidad de memoria mínima por consulta tiene prioridad sobre la [opción de memoria para creación de índices](configure-the-index-create-memory-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="25b08-119">The amount of min memory per query has precedence over the [index create memory Option](configure-the-index-create-memory-server-configuration-option.md).</span></span> <span data-ttu-id="25b08-120">Si cambia ambas opciones y el valor de index create memory es inferior al de min memory per query, aparecerá un mensaje de advertencia, pero se establecerá el valor.</span><span class="sxs-lookup"><span data-stu-id="25b08-120">If you modify both options and the index create memory is less than min memory per query, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="25b08-121">Durante la ejecución de la consulta recibirá otra advertencia similar.</span><span class="sxs-lookup"><span data-stu-id="25b08-121">During query execution you receive another similar warning.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="25b08-122">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="25b08-122">Recommendations</span></span>  
  
-   <span data-ttu-id="25b08-123">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="25b08-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="25b08-124">El procesador de consultas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] intenta determinar la cantidad óptima de memoria para asignar a una consulta.</span><span class="sxs-lookup"><span data-stu-id="25b08-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query processor tries to determine the optimal amount of memory to allocate to a query.</span></span> <span data-ttu-id="25b08-125">La opción min memory per query permite al administrador especificar la cantidad mínima de memoria que recibirá cada consulta.</span><span class="sxs-lookup"><span data-stu-id="25b08-125">The min memory per query option lets the administrator specify the minimum amount of memory any single query receives.</span></span> <span data-ttu-id="25b08-126">Generalmente, las consultas reciben una cantidad mayor de memoria si tienen operaciones de orden y hash en un gran volumen de datos.</span><span class="sxs-lookup"><span data-stu-id="25b08-126">Queries generally receive more memory than this if they have hash and sort operations on a large volume of data.</span></span> <span data-ttu-id="25b08-127">Aumentar el valor de la opción min memory per query puede mejorar el rendimiento para algunas consultas de pequeño o mediano tamaño, pero podría aumentar la competición por los recursos de la memoria.</span><span class="sxs-lookup"><span data-stu-id="25b08-127">Increasing the value of min memory per query may improve performance for some small to medium-sized queries, but doing so could lead to increased competition for memory resources.</span></span> <span data-ttu-id="25b08-128">La opción de min memory per query incluye memoria asignada para ordenar.</span><span class="sxs-lookup"><span data-stu-id="25b08-128">The min memory per query option includes memory allocated for sorting.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="25b08-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="25b08-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="25b08-130">Permisos</span><span class="sxs-lookup"><span data-stu-id="25b08-130">Permissions</span></span>  
 <span data-ttu-id="25b08-131">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="25b08-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="25b08-132">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="25b08-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="25b08-133">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="25b08-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="25b08-134">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25b08-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="25b08-135">Para configurar la opción de memoria mínima por consulta</span><span class="sxs-lookup"><span data-stu-id="25b08-135">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="25b08-136">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="25b08-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="25b08-137">Haga clic en el nodo **Memoria** .</span><span class="sxs-lookup"><span data-stu-id="25b08-137">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="25b08-138">En el cuadro **Cantidad mínima de memoria por consulta** , especifique la cantidad mínima de memoria (en kilobytes) que se va a asignar para la ejecución de una consulta.</span><span class="sxs-lookup"><span data-stu-id="25b08-138">In the **Minimum memory per query** box, enter the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="25b08-139">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="25b08-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="25b08-140">Para configurar la opción de memoria mínima por consulta</span><span class="sxs-lookup"><span data-stu-id="25b08-140">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="25b08-141">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25b08-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="25b08-142">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="25b08-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="25b08-143">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="25b08-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="25b08-144">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `min memory per query` en `3500` kB.</span><span class="sxs-lookup"><span data-stu-id="25b08-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `min memory per query` option to `3500` KB.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'min memory per query', 3500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-min-memory-per-query-option"></a><a name="FollowUp"></a> <span data-ttu-id="25b08-145">Seguimiento: Después de configurar la opción de memoria mínima por consulta</span><span class="sxs-lookup"><span data-stu-id="25b08-145">Follow Up: After you configure the min memory per query option</span></span>  
 <span data-ttu-id="25b08-146">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="25b08-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b08-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25b08-147">See Also</span></span>  
 <span data-ttu-id="25b08-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="25b08-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="25b08-149">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="25b08-149">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="25b08-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="25b08-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="25b08-151">Establecer la opción de configuración del servidor Memoria para creación de índices</span><span class="sxs-lookup"><span data-stu-id="25b08-151">Configure the index create memory Server Configuration Option</span></span>](configure-the-index-create-memory-server-configuration-option.md)  
  
  
