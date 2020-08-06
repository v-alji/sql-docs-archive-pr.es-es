---
title: Establecer la opción de configuración del servidor Espera de consulta | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], timing out
- time [SQL Server], query wait time
- query wait option [SQL Server]
ms.assetid: 0fc4aa01-65a3-4a33-9ef4-caca41add238
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 638afff2aa05a9fc4e61bc71e8610dba1dda8cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674329"
---
# <a name="configure-the-query-wait-server-configuration-option"></a><span data-ttu-id="ef1a1-102">Establecer la opción de configuración del servidor Espera de consulta</span><span class="sxs-lookup"><span data-stu-id="ef1a1-102">Configure the query wait Server Configuration Option</span></span>
  <span data-ttu-id="ef1a1-103">En este tema se describe cómo establecer la opción de configuración del servidor **Espera de consulta** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef1a1-103">This topic describes how to configure the **query wait** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ef1a1-104">Las consultas que utilizan mucha memoria (como las relativas a operaciones de ordenación y aplicación del algoritmo de hash) se colocan en cola cuando la memoria disponible para ejecutarlas es insuficiente.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-104">Memory-intensive queries (such as those involving sorting and hashing) are queued when there is not enough memory available to run the query.</span></span> <span data-ttu-id="ef1a1-105">La opción **Espera de consulta** especifica el tiempo en segundos (de 0 a 2147483647) que una consulta espera para usar los recursos antes de que se agote el tiempo de espera. El valor predeterminado para esta opción es -1.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-105">The **query wait** option specifies the time, in seconds (from 0 through 2147483647), that a query waits for resources before it times out. The default value for this option is -1.</span></span> <span data-ttu-id="ef1a1-106">Esto significa que el tiempo de espera se calcula como 25 veces el costo estimado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-106">This means the time-out is calculated as 25 times the estimated query cost.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ef1a1-107">Una transacción que contiene la consulta en espera puede retener bloqueos mientras la consulta espera para utilizar la memoria.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-107">A transaction that contains the waiting query might hold locks while the query waits for memory.</span></span> <span data-ttu-id="ef1a1-108">En situaciones poco habituales, es posible que se produzca un interbloqueo no detectable.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-108">In rare situations, it is possible for an undetectable deadlock to occur.</span></span> <span data-ttu-id="ef1a1-109">Al disminuir el tiempo de espera de la consulta, disminuye la probabilidad de que se produzcan estos interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-109">Decreasing the query wait time lowers the probability of such deadlocks.</span></span> <span data-ttu-id="ef1a1-110">Finalmente, se terminará una consulta en espera y se liberarán los bloqueos de la transacción.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-110">Eventually, a waiting query will be terminated and the transaction locks released.</span></span> <span data-ttu-id="ef1a1-111">No obstante, el aumento del tiempo de espera máximo puede aumentar el tiempo para que la consulta se termine.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-111">However, increasing the maximum wait time may increase the amount of time for the query to be terminated.</span></span> <span data-ttu-id="ef1a1-112">Se recomienda no realizar cambios en esta opción.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-112">Changes to this option are not recommended.</span></span>  
  
 <span data-ttu-id="ef1a1-113">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="ef1a1-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ef1a1-114">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="ef1a1-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ef1a1-115">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="ef1a1-115">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="ef1a1-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ef1a1-116">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ef1a1-117">**Para configurar la opción Espera de consulta, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="ef1a1-117">**To configure the query wait option, using:**</span></span>  
  
     [<span data-ttu-id="ef1a1-118">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef1a1-118">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ef1a1-119">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef1a1-119">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="ef1a1-120">**Seguimiento:**  [Después de configurar la opción Espera de consulta](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="ef1a1-120">**Follow Up:**  [After you configure the query wait option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ef1a1-121">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ef1a1-121">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ef1a1-122">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="ef1a1-122">Recommendations</span></span>  
  
-   <span data-ttu-id="ef1a1-123">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ef1a1-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ef1a1-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ef1a1-125">Permisos</span><span class="sxs-lookup"><span data-stu-id="ef1a1-125">Permissions</span></span>  
 <span data-ttu-id="ef1a1-126">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="ef1a1-127">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="ef1a1-128">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ef1a1-129">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef1a1-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="ef1a1-130">Para configurar la opción query wait</span><span class="sxs-lookup"><span data-stu-id="ef1a1-130">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="ef1a1-131">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="ef1a1-132">Haga clic en el nodo **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="ef1a1-132">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="ef1a1-133">En **Paralelismo**, escriba el valor que desee para la opción **Espera de consulta** .</span><span class="sxs-lookup"><span data-stu-id="ef1a1-133">Under **Parallelism**, type the desired value for the **query wait** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ef1a1-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef1a1-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="ef1a1-135">Para configurar la opción query wait</span><span class="sxs-lookup"><span data-stu-id="ef1a1-135">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="ef1a1-136">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef1a1-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ef1a1-137">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ef1a1-138">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ef1a1-139">Este ejemplo muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción `query wait` en `7500` segundos.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query wait` option to `7500` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query wait', 7500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="ef1a1-140">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ef1a1-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-wait-option"></a><a name="FollowUp"></a> <span data-ttu-id="ef1a1-141">Seguimiento: Después de configurar la opción Espera de consulta</span><span class="sxs-lookup"><span data-stu-id="ef1a1-141">Follow Up: After you configure the query wait option</span></span>  
 <span data-ttu-id="ef1a1-142">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef1a1-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef1a1-143">See Also</span></span>  
 <span data-ttu-id="ef1a1-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ef1a1-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="ef1a1-145">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ef1a1-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="ef1a1-146">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef1a1-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
