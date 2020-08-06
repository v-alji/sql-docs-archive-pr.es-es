---
title: Establecer la opción de configuración del servidor Umbral de cursor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cursor threshold option
ms.assetid: 189f2067-c6c4-48bd-9bd9-65f6b2021c12
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0d7fd9ecafda270a02f1fba9f5dd74adc9e299d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677884"
---
# <a name="configure-the-cursor-threshold-server-configuration-option"></a><span data-ttu-id="7e434-102">Establecer la opción de configuración del servidor Umbral de cursor</span><span class="sxs-lookup"><span data-stu-id="7e434-102">Configure the cursor threshold Server Configuration Option</span></span>
  <span data-ttu-id="7e434-103">En este tema se describe cómo establecer la opción de configuración del servidor **umbral de cursor** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e434-103">This topic describes how to configure the **cursor threshold** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7e434-104">La opción de **umbral de cursor** especifica el número de filas del conjunto de cursores donde se generan de manera asincrónica los conjuntos de claves del cursor.</span><span class="sxs-lookup"><span data-stu-id="7e434-104">The **cursor threshold** option specifies the number of rows in the cursor set at which cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="7e434-105">Cuando los cursores generan un conjunto de claves para un conjunto de resultados, el optimizador de consultas calcula el número de filas que se va a devolver para ese conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="7e434-105">When cursors generate a keyset for a result set, the query optimizer estimates the number of rows that will be returned for that result set.</span></span> <span data-ttu-id="7e434-106">Si el optimizador de consultas calcula que el número de filas devuelto es superior a este umbral, el cursor se genera de manera asincrónica, lo que permite al usuario capturar las filas del cursor mientras sigue llenándose.</span><span class="sxs-lookup"><span data-stu-id="7e434-106">If the query optimizer estimates that the number of returned rows is greater than this threshold, the cursor is generated asynchronously, allowing the user to fetch rows from the cursor while the cursor continues to be populated.</span></span> <span data-ttu-id="7e434-107">De lo contrario, el cursor se genera de manera sincrónica y la consulta espera a que se devuelvan todas las filas.</span><span class="sxs-lookup"><span data-stu-id="7e434-107">Otherwise, the cursor is generated synchronously, and the query waits until all rows are returned.</span></span>  
  
 <span data-ttu-id="7e434-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="7e434-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7e434-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="7e434-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7e434-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7e434-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7e434-111">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="7e434-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="7e434-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7e434-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7e434-113">**Para configurar la opción de umbral de cursor, use:**</span><span class="sxs-lookup"><span data-stu-id="7e434-113">**To configure the cursor threshold option, using:**</span></span>  
  
     [<span data-ttu-id="7e434-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e434-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7e434-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e434-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="7e434-116">**Seguimiento:**  [Después de configurar la opción de umbral de cursor](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="7e434-116">**Follow Up:**  [After you configure the cursor threshold option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7e434-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7e434-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7e434-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7e434-118">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7e434-119">no es compatible con la generación asincrónica de cursores de [!INCLUDE[tsql](../../includes/tsql-md.md)] estáticos o controlados por conjuntos de claves.</span><span class="sxs-lookup"><span data-stu-id="7e434-119">does not support generating keyset-driven or static [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors asynchronously.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="7e434-120">como OPEN o FETCH se procesan por lotes, por lo que la generación asincrónica de cursores de [!INCLUDE[tsql](../../includes/tsql-md.md)] no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="7e434-120">cursor operations such as OPEN or FETCH are batched, so there is no need for the asynchronous generation of [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7e434-121">sigue admitiendo los cursores de servidor de la interfaz de programación de aplicaciones (API) estáticos o controlados por conjuntos de claves asincrónicos en los que OPEN de baja latencia es un problema, debido a los recorridos de ida y vuelta al cliente para cada operación del cursor.</span><span class="sxs-lookup"><span data-stu-id="7e434-121">continues to support asynchronous keyset-driven or static application programming interface (API) server cursors where low latency OPEN is a concern, due to client round trips for each cursor operation.</span></span>  
  
-   <span data-ttu-id="7e434-122">La precisión del optimizador de consultas para determinar una estimación del número de filas de un conjunto de claves depende del grado de actualización de las estadísticas de cada una de las tablas del cursor.</span><span class="sxs-lookup"><span data-stu-id="7e434-122">The accuracy of the query optimizer to determine an estimate for the number of rows in a keyset depends on the currency of the statistics for each of the tables in the cursor.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="7e434-123">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="7e434-123">Recommendations</span></span>  
  
-   <span data-ttu-id="7e434-124">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="7e434-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="7e434-125">Si establece el valor -1 para el **umbral de cursor** , todos los conjuntos de claves se generan de manera sincrónica, lo que beneficia a los conjuntos de cursores pequeños.</span><span class="sxs-lookup"><span data-stu-id="7e434-125">If you set **cursor threshold** to -1, all keysets are generated synchronously, which benefits small cursor sets.</span></span> <span data-ttu-id="7e434-126">Si establece el valor 0 para **cursor threshold** , todos los conjuntos de claves del cursor se generan de manera asincrónica.</span><span class="sxs-lookup"><span data-stu-id="7e434-126">If you set **cursor threshold** to 0, all cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="7e434-127">Con otros valores, el optimizador de consultas compara el número de filas esperadas del conjunto de cursores y genera asincrónicamente el conjunto de claves si supera el número establecido en **cursor threshold**.</span><span class="sxs-lookup"><span data-stu-id="7e434-127">With other values, the query optimizer compares the number of expected rows in the cursor set and builds the keyset asynchronously if it exceeds the number set in **cursor threshold**.</span></span> <span data-ttu-id="7e434-128">No establezca un valor demasiado bajo para el **umbral de cursor** , ya que los conjuntos de resultados pequeños se generan mejor de manera sincrónica.</span><span class="sxs-lookup"><span data-stu-id="7e434-128">Do not set **cursor threshold** too low, because small result sets are better built synchronously.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7e434-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7e434-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7e434-130">Permisos</span><span class="sxs-lookup"><span data-stu-id="7e434-130">Permissions</span></span>  
 <span data-ttu-id="7e434-131">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="7e434-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="7e434-132">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="7e434-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="7e434-133">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="7e434-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7e434-134">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e434-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="7e434-135">Para configurar la opción cursor threshold</span><span class="sxs-lookup"><span data-stu-id="7e434-135">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="7e434-136">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7e434-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="7e434-137">Haga clic en el nodo **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="7e434-137">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="7e434-138">En **Varios**, cambie la opción **Umbral de cursor** al valor que desee.</span><span class="sxs-lookup"><span data-stu-id="7e434-138">Under **Miscellaneous**, change the **Cursor Threshold** option to the value you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7e434-139">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e434-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="7e434-140">Para configurar la opción cursor threshold</span><span class="sxs-lookup"><span data-stu-id="7e434-140">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="7e434-141">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e434-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7e434-142">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="7e434-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7e434-143">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7e434-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7e434-144">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer la opción de `cursor threshold` en `0` con el fin de generar conjuntos de claves del cursor de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="7e434-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the `cursor threshold` option to `0` so that cursor keysets are generated asynchronously.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cursor threshold', 0 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="7e434-145">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7e434-145">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cursor-threshold-option"></a><a name="FollowUp"></a> <span data-ttu-id="7e434-146">Seguimiento: Después de configurar la opción de umbral de cursor</span><span class="sxs-lookup"><span data-stu-id="7e434-146">Follow Up: After you configure the cursor threshold option</span></span>  
 <span data-ttu-id="7e434-147">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="7e434-147">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e434-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e434-148">See Also</span></span>  
 <span data-ttu-id="7e434-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e434-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span></span>  
 <span data-ttu-id="7e434-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e434-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="7e434-151">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7e434-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="7e434-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e434-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="7e434-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7e434-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
