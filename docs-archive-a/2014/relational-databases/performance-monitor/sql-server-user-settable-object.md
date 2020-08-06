---
title: User Settable (objeto de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- User Settable object
- SQLServer:User Settable
ms.assetid: 633de3ef-533c-4f0c-9c7b-c105129d8e94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7243ab4767c8de93dccf4556f136a94b47554d3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744653"
---
# <a name="sql-server-user-settable-object"></a><span data-ttu-id="bd041-102">User Settable (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bd041-102">SQL Server, User Settable Object</span></span>
  <span data-ttu-id="bd041-103">El objeto **User Settable** de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite crear instancias de contadores personalizadas.</span><span class="sxs-lookup"><span data-stu-id="bd041-103">The **User Settable** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to create custom counter instances.</span></span> <span data-ttu-id="bd041-104">Utilice las instancias de contadores personalizadas para supervisar aspectos del servidor que los contadores existentes no supervisan, como los componentes únicos de la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (por ejemplo, para determinar el número de pedidos de clientes registrados o el inventario de productos).</span><span class="sxs-lookup"><span data-stu-id="bd041-104">Use custom counter instances to monitor aspects of the server not monitored by existing counters, such as components unique to your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database (for example, the number of customer orders logged or the product inventory).</span></span>  
  
 <span data-ttu-id="bd041-105">El objeto **User Settable** contiene 10 instancias del contador de consultas: **Contador de usuario 1** hasta **Contador de usuario 10**.</span><span class="sxs-lookup"><span data-stu-id="bd041-105">The **User Settable** object contains 10 instances of the query counter: **User counter 1** through **User counter 10**.</span></span> <span data-ttu-id="bd041-106">Estos contadores tienen asignados los procedimientos almacenados de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que van del **sp_user_counter1** al **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="bd041-106">These counters map to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures **sp_user_counter1** through **sp_user_counter10**.</span></span> <span data-ttu-id="bd041-107">A medida que las aplicaciones del usuario ejecutan estos procedimientos almacenados, los valores que establecen estos procedimientos almacenados se muestran en el Monitor de sistema.</span><span class="sxs-lookup"><span data-stu-id="bd041-107">As these stored procedures are executed by user applications, the values set by the stored procedures are displayed in System Monitor.</span></span> <span data-ttu-id="bd041-108">Un contador puede supervisar cualquier valor entero, por ejemplo, un procedimiento almacenado que cuente el número de pedidos de un producto específico que se han realizado en un día.</span><span class="sxs-lookup"><span data-stu-id="bd041-108">A counter can monitor any single integer value (for example, a stored procedure that counts how many orders for a particular product have occurred in one day).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd041-109">El Monitor del sistema no realiza automáticamente el sondeo de los procedimientos almacenados de contadores del usuario.</span><span class="sxs-lookup"><span data-stu-id="bd041-109">The user counter stored procedures are not polled automatically by System Monitor.</span></span> <span data-ttu-id="bd041-110">Es necesario ejecutarlos explícitamente en una aplicación de usuario para actualizar los valores de estos contadores.</span><span class="sxs-lookup"><span data-stu-id="bd041-110">They must be explicitly executed by a user application for the counter values to be updated.</span></span> <span data-ttu-id="bd041-111">Utilice un desencadenador para actualizar automáticamente el valor del contador.</span><span class="sxs-lookup"><span data-stu-id="bd041-111">Use a trigger to update the value of the counter automatically.</span></span> <span data-ttu-id="bd041-112">Por ejemplo, para crear un contador que supervise el número de filas de una tabla, cree un desencadenador INSERT y DELETE en la tabla que ejecuta la siguiente instrucción: `SELECT COUNT(*) FROM table`.</span><span class="sxs-lookup"><span data-stu-id="bd041-112">For example, to create a counter that monitors the number of rows in a table, create an INSERT and DELETE trigger on the table that executes the following statement: `SELECT COUNT(*) FROM table`.</span></span> <span data-ttu-id="bd041-113">Siempre que se active el desencadenador debido a que se esté realizando una operación INSERT o DELETE en la tabla, el contador del Monitor de sistema se actualizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bd041-113">Whenever the trigger is fired because of an INSERT or DELETE operation occurring on the table, the System Monitor counter is automatically updated.</span></span>  
  
 <span data-ttu-id="bd041-114">En esta tabla se describe el objeto **User Settable** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd041-114">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **User Settable** object.</span></span>  
  
|<span data-ttu-id="bd041-115">Contadores de Establecidas por el usuario de SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd041-115">SQL Server User Settable counters</span></span>|<span data-ttu-id="bd041-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd041-116">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="bd041-117">**Consultar**</span><span class="sxs-lookup"><span data-stu-id="bd041-117">**Query**</span></span>|<span data-ttu-id="bd041-118">El objeto **User Settable** contiene el contador de consultas.</span><span class="sxs-lookup"><span data-stu-id="bd041-118">The **User Settable** object contains the query counter.</span></span> <span data-ttu-id="bd041-119">El usuario configura los **contadores del usuario** del objeto Query.</span><span class="sxs-lookup"><span data-stu-id="bd041-119">Users configure the **User counters** within the query object.</span></span>|  
  
 <span data-ttu-id="bd041-120">En esta tabla se describen las **instancias** del contador **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="bd041-120">This table describes the **instances** of the **Query** counter.</span></span>  
  
|<span data-ttu-id="bd041-121">Instancias del contador de consultas</span><span class="sxs-lookup"><span data-stu-id="bd041-121">Query counter instances</span></span>|<span data-ttu-id="bd041-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd041-122">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="bd041-123">**User counter 1**</span><span class="sxs-lookup"><span data-stu-id="bd041-123">**User counter 1**</span></span>|<span data-ttu-id="bd041-124">Definido mediante **sp_user_counter1**.</span><span class="sxs-lookup"><span data-stu-id="bd041-124">Defined using **sp_user_counter1**.</span></span>|  
|<span data-ttu-id="bd041-125">**User counter 2**</span><span class="sxs-lookup"><span data-stu-id="bd041-125">**User counter 2**</span></span>|<span data-ttu-id="bd041-126">Definido mediante **sp_user_counter2**.</span><span class="sxs-lookup"><span data-stu-id="bd041-126">Defined using **sp_user_counter2**.</span></span>|  
|<span data-ttu-id="bd041-127">**User counter 3**</span><span class="sxs-lookup"><span data-stu-id="bd041-127">**User counter 3**</span></span>|<span data-ttu-id="bd041-128">Definido mediante **sp_user_counter3**.</span><span class="sxs-lookup"><span data-stu-id="bd041-128">Defined using **sp_user_counter3**.</span></span>|  
|<span data-ttu-id="bd041-129">...</span><span class="sxs-lookup"><span data-stu-id="bd041-129">...</span></span>||  
|<span data-ttu-id="bd041-130">**User counter 10**</span><span class="sxs-lookup"><span data-stu-id="bd041-130">**User counter 10**</span></span>|<span data-ttu-id="bd041-131">Definido mediante **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="bd041-131">Defined using **sp_user_counter10**.</span></span>|  
  
 <span data-ttu-id="bd041-132">Para utilizar los procedimientos almacenados de contadores del usuario, ejecútelos desde su propia aplicación con un parámetro de número entero que represente el nuevo valor del contador.</span><span class="sxs-lookup"><span data-stu-id="bd041-132">To make use of the user counter stored procedures, execute them from your own application with a single integer parameter representing the new value for the counter.</span></span> <span data-ttu-id="bd041-133">Por ejemplo, para establecer el valor 10 para **User counter 1** , ejecute esta instrucción Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="bd041-133">For example, to set **User counter 1** to the value 10, execute this Transact-SQL statement:</span></span>  
  
```  
EXECUTE sp_user_counter1 10  
```  
  
 <span data-ttu-id="bd041-134">Los procedimientos almacenados de contadores de usuario se pueden llamar desde los mismos lugares que otros procedimientos almacenados, por ejemplo los propios del usuario.</span><span class="sxs-lookup"><span data-stu-id="bd041-134">The user counter stored procedures can be called from anywhere other stored procedures can be called, such as your own stored procedures.</span></span> <span data-ttu-id="bd041-135">Por ejemplo, puede crear el siguiente procedimiento almacenado para contar el número de conexiones e intentos de conexión realizados desde que se inició una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="bd041-135">For example, you can create the following stored procedure to count the number of connections and attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was started:</span></span>  
  
```  
DROP PROC My_Proc  
GO  
CREATE PROC My_Proc  
AS   
   EXECUTE sp_user_counter1 @@CONNECTIONS  
GO  
```  
  
 <span data-ttu-id="bd041-136">La función @@CONNECTIONS devuelve el número de conexiones o intentos de conexión desde el inicio de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd041-136">The @@CONNECTIONS function returns the number of connections or attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] started.</span></span> <span data-ttu-id="bd041-137">Este valor se pasa al procedimiento almacenado **sp_user_counter1** como el parámetro.</span><span class="sxs-lookup"><span data-stu-id="bd041-137">This value is passed to the **sp_user_counter1** stored procedure as the parameter.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bd041-138">Las consultas definidas en los procedimientos almacenados de contadores de usuario deben ser lo más sencillas posible.</span><span class="sxs-lookup"><span data-stu-id="bd041-138">Make the queries defined in the user counter stored procedures as simple as possible.</span></span> <span data-ttu-id="bd041-139">Las consultas con un gran uso de memoria que realizan un número significativo de operaciones de ordenación o de hash, o las consultas que realizan un gran número de operaciones de E/S tienen un gran costo de ejecución y pueden afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="bd041-139">Memory-intensive queries that perform substantial sort or hash operations or queries that perform large amounts of I/O are expensive to execute and can impact performance.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="bd041-140">Permisos</span><span class="sxs-lookup"><span data-stu-id="bd041-140">Permissions</span></span>  
 <span data-ttu-id="bd041-141">**sp_user_counter** está disponible para todos los usuarios, pero puede estar restringido para cualquier contador de consultas.</span><span class="sxs-lookup"><span data-stu-id="bd041-141">**sp_user_counter** is available for all users but can be restricted for any query counter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd041-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd041-142">See Also</span></span>  
 [<span data-ttu-id="bd041-143">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="bd041-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
