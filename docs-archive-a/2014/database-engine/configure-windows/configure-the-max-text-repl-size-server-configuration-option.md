---
title: Establecer la opción de configuración del servidor Tamaño de replicación de texto máximo | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- max text repl size option
ms.assetid: 3056cf64-621d-4996-9162-3913f6bc6d5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af0cf426583ee328f0a484de1c3539836c0d8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674337"
---
# <a name="configure-the-max-text-repl-size-server-configuration-option"></a><span data-ttu-id="406f3-102">Establecer la opción de configuración del servidor Tamaño de replicación de texto máximo</span><span class="sxs-lookup"><span data-stu-id="406f3-102">Configure the max text repl size Server Configuration Option</span></span>
  <span data-ttu-id="406f3-103">En este tema se describe cómo establecer la opción de configuración del servidor **tamaño de replicación de texto máximo** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="406f3-103">This topic describes how to configure the **max text repl size** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="406f3-104">La opción de **tamaño de replicación de texto máximo** especifica el tamaño máximo (en bytes) de los `text` datos de, `ntext` ,,, `varchar(max)` `nvarchar(max)` `varbinary(max)` , `xml` y `image` que se pueden agregar a una columna replicada o a una columna capturada en una sola instrucción INSERT, Update, WRITETEXT o UPDATETEXT.</span><span class="sxs-lookup"><span data-stu-id="406f3-104">The **max text repl size** option specifies the maximum size (in bytes) of `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, `xml`, and `image` data that can be added to a replicated column or captured column in a single INSERT, UPDATE, WRITETEXT, or UPDATETEXT statement.</span></span> <span data-ttu-id="406f3-105">El valor predeterminado es 65 536 bytes.</span><span class="sxs-lookup"><span data-stu-id="406f3-105">The default value is 65536 bytes.</span></span> <span data-ttu-id="406f3-106">Un valor predeterminado de -1 indica que no hay límite de tamaño, excepto el impuesto por el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="406f3-106">A value of -1 indicates that there is no size limit, other than the limit imposed by the data type.</span></span>  
  
 <span data-ttu-id="406f3-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="406f3-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="406f3-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="406f3-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="406f3-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="406f3-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="406f3-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="406f3-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="406f3-111">**Para configurar la opción de tamaño de replicación de texto máximo, use:**</span><span class="sxs-lookup"><span data-stu-id="406f3-111">**To configure the max text repl size option, using:**</span></span>  
  
     [<span data-ttu-id="406f3-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="406f3-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="406f3-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="406f3-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="406f3-114">**Seguimiento:**  [después de configurar la opción de tamaño de replicación de texto máximo](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="406f3-114">**Follow Up:**  [After you configure the max text repl size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="406f3-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="406f3-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="406f3-116">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="406f3-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="406f3-117">Esta opción se aplica a la replicación transaccional y a la captura de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="406f3-117">This option applies to transactional replication and Change Data Capture.</span></span> <span data-ttu-id="406f3-118">Cuando un servidor se configura para la replicación transaccional y la captura de datos modificados, el valor especificado se aplica a ambas características.</span><span class="sxs-lookup"><span data-stu-id="406f3-118">When a server is configured for both transactional replication and Change Data Capture, the specified value applies to both features.</span></span> <span data-ttu-id="406f3-119">La replicación de instantáneas y la replicación de mezcla hacen caso omiso de esta opción.</span><span class="sxs-lookup"><span data-stu-id="406f3-119">This option is ignored by snapshot replication and merge replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="406f3-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="406f3-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="406f3-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="406f3-121">Permissions</span></span>  
 <span data-ttu-id="406f3-122">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="406f3-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="406f3-123">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="406f3-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="406f3-124">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="406f3-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="406f3-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="406f3-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="406f3-126">Para configurar la opción de tamaño de replicación de texto máximo</span><span class="sxs-lookup"><span data-stu-id="406f3-126">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="406f3-127">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="406f3-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="406f3-128">Haga clic en el nodo **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="406f3-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="406f3-129">En **Varios**, cambie la opción **Tamaño de replicación de texto máximo** al valor que desee.</span><span class="sxs-lookup"><span data-stu-id="406f3-129">Under **Miscellaneous**, change the **Max Text Replication Size** option to the desired value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="406f3-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="406f3-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="406f3-131">Para configurar la opción de tamaño de replicación de texto máximo</span><span class="sxs-lookup"><span data-stu-id="406f3-131">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="406f3-132">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="406f3-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="406f3-133">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="406f3-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="406f3-134">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="406f3-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="406f3-135">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar la opción `max text repl size` en `-1`.</span><span class="sxs-lookup"><span data-stu-id="406f3-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max text repl size` option to `-1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;   
RECONFIGURE ;   
GO  
EXEC sp_configure 'max text repl size', -1 ;   
GO  
RECONFIGURE;   
GO  
  
```  
  
 <span data-ttu-id="406f3-136">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="406f3-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-text-repl-size-option"></a><a name="FollowUp"></a> <span data-ttu-id="406f3-137">Seguimiento: después de configurar la opción de tamaño de replicación de texto máximo</span><span class="sxs-lookup"><span data-stu-id="406f3-137">Follow Up: After you configure the max text repl size option</span></span>  
 <span data-ttu-id="406f3-138">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="406f3-138">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="406f3-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="406f3-139">See Also</span></span>  
 <span data-ttu-id="406f3-140">[Replicación de SQL Server](../../relational-databases/replication/sql-server-replication.md) </span><span class="sxs-lookup"><span data-stu-id="406f3-140">[SQL Server Replication](../../relational-databases/replication/sql-server-replication.md) </span></span>  
 <span data-ttu-id="406f3-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="406f3-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="406f3-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="406f3-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="406f3-143">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="406f3-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="406f3-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="406f3-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="406f3-145">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="406f3-145">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 <span data-ttu-id="406f3-146">[UPDATETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/updatetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="406f3-146">[UPDATETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/updatetext-transact-sql) </span></span>  
 [<span data-ttu-id="406f3-147">WRITETEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="406f3-147">WRITETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/writetext-transact-sql)  
  
  
