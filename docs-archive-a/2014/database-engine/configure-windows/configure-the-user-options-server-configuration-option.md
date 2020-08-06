---
title: Establecer la opción de configuración del servidor Opciones de usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- global default for all users [SQL Server]
- users [SQL Server], global defaults
- user options option [SQL Server]
ms.assetid: cfed8f86-6bcf-4b90-88eb-9656e22d5dc5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d7ee40d0f6de532b93ce9d8075b609c80f09df7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749471"
---
# <a name="configure-the-user-options-server-configuration-option"></a><span data-ttu-id="223f4-102">Establecer la opción de configuración del servidor Opciones de usuario</span><span class="sxs-lookup"><span data-stu-id="223f4-102">Configure the user options Server Configuration Option</span></span>
  <span data-ttu-id="223f4-103">En este tema se describe cómo establecer la opción de configuración de servidor para **opciones de usuario** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="223f4-103">This topic describes how to configure the **user options** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="223f4-104">La opción para **opciones de usuario** especifica valores predeterminados globales para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="223f4-104">The **user options** option specifies global defaults for all users.</span></span> <span data-ttu-id="223f4-105">Hay establecida una lista de opciones de procesamiento de consultas predeterminadas para la duración de la sesión de trabajo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="223f4-105">A list of default query processing options is established for the duration of a user's work session.</span></span> <span data-ttu-id="223f4-106">La opción **opciones de usuario** permite cambiar los valores predeterminados de las opciones SET si no resultan adecuados los valores predeterminados del servidor.</span><span class="sxs-lookup"><span data-stu-id="223f4-106">The **user options** option allows you to change the default values of the SET options (if the server's default settings are not appropriate).</span></span>  
  
 <span data-ttu-id="223f4-107">El usuario puede suplantar estos valores predeterminados con la instrucción SET.</span><span class="sxs-lookup"><span data-stu-id="223f4-107">A user can override these defaults by using the SET statement.</span></span> <span data-ttu-id="223f4-108">Puede configurar la opción **user options** de manera dinámica para nuevos inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="223f4-108">You can configure **user options** dynamically for new logins.</span></span> <span data-ttu-id="223f4-109">Después de cambiar el valor de la opción para **opciones de usuario**, los nuevos inicios de sesión utilizarán el nuevo valor, pero el cambio no afectará a los inicios de sesión actuales.</span><span class="sxs-lookup"><span data-stu-id="223f4-109">After you change the setting of **user options**, new login sessions use the new setting; current login sessions are not affected.</span></span>  
  
 <span data-ttu-id="223f4-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="223f4-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="223f4-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="223f4-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="223f4-112">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="223f4-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="223f4-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="223f4-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="223f4-114">**Para configurar la opción de configuración para opciones de usuario, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="223f4-114">**To configure the user options configuration option, using:**</span></span>  
  
     [<span data-ttu-id="223f4-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="223f4-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="223f4-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="223f4-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="223f4-117">**Seguimiento:**  [Después de configurar la opción de configuración para opciones de usuario](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="223f4-117">**Follow Up:**  [After you configure the user options configuration option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="223f4-118">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="223f4-118">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="223f4-119">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="223f4-119">Recommendations</span></span>  
  
-   <span data-ttu-id="223f4-120">En la tabla siguiente se muestran y describen los valores de configuración para **opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="223f4-120">The following table lists and describes the configuration values for **user options**.</span></span> <span data-ttu-id="223f4-121">No todos los valores de configuración son compatibles entre sí.</span><span class="sxs-lookup"><span data-stu-id="223f4-121">Not all configuration values are compatible with each other.</span></span> <span data-ttu-id="223f4-122">Por ejemplo, ANSI_NULL_DFLT_ON y ANSI_NULL_DFLT_OFF no se pueden establecer al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="223f4-122">For example, ANSI_NULL_DFLT_ON and ANSI_NULL_DFLT_OFF cannot be set at the same time.</span></span>  
  
    |<span data-ttu-id="223f4-123">Value</span><span class="sxs-lookup"><span data-stu-id="223f4-123">Value</span></span>|<span data-ttu-id="223f4-124">Configuración</span><span class="sxs-lookup"><span data-stu-id="223f4-124">Configuration</span></span>|<span data-ttu-id="223f4-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="223f4-125">Description</span></span>|  
    |-----------|-------------------|-----------------|  
    |<span data-ttu-id="223f4-126">1</span><span class="sxs-lookup"><span data-stu-id="223f4-126">1</span></span>|<span data-ttu-id="223f4-127">DISABLE_DEF_CNST_CHK</span><span class="sxs-lookup"><span data-stu-id="223f4-127">DISABLE_DEF_CNST_CHK</span></span>|<span data-ttu-id="223f4-128">Controla la comprobación de restricciones provisionales o diferidas.</span><span class="sxs-lookup"><span data-stu-id="223f4-128">Controls interim or deferred constraint checking.</span></span>|  
    |<span data-ttu-id="223f4-129">2</span><span class="sxs-lookup"><span data-stu-id="223f4-129">2</span></span>|<span data-ttu-id="223f4-130">IMPLICIT_TRANSACTIONS</span><span class="sxs-lookup"><span data-stu-id="223f4-130">IMPLICIT_TRANSACTIONS</span></span>|<span data-ttu-id="223f4-131">Para las conexiones de biblioteca de red dblib, controla si una transacción se inicia de manera implícita al ejecutar una instrucción.</span><span class="sxs-lookup"><span data-stu-id="223f4-131">For dblib network library connections, controls whether a transaction is started implicitly when a statement is executed.</span></span> <span data-ttu-id="223f4-132">El valor IMPLICIT_TRANSACTIONS no tiene ningún efecto en las conexiones ODBC u OLEDB.</span><span class="sxs-lookup"><span data-stu-id="223f4-132">The IMPLICIT_TRANSACTIONS setting has no effect on ODBC or OLEDB connections.</span></span>|  
    |<span data-ttu-id="223f4-133">4</span><span class="sxs-lookup"><span data-stu-id="223f4-133">4</span></span>|<span data-ttu-id="223f4-134">CURSOR_CLOSE_ON_COMMIT</span><span class="sxs-lookup"><span data-stu-id="223f4-134">CURSOR_CLOSE_ON_COMMIT</span></span>|<span data-ttu-id="223f4-135">Controla el comportamiento de los cursores después de realizarse una operación de confirmación.</span><span class="sxs-lookup"><span data-stu-id="223f4-135">Controls behavior of cursors after a commit operation has been performed.</span></span>|  
    |<span data-ttu-id="223f4-136">8</span><span class="sxs-lookup"><span data-stu-id="223f4-136">8</span></span>|<span data-ttu-id="223f4-137">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="223f4-137">ANSI_WARNINGS</span></span>|<span data-ttu-id="223f4-138">Controla el truncamiento y los valores NULL en las advertencias de agregados.</span><span class="sxs-lookup"><span data-stu-id="223f4-138">Controls truncation and NULL in aggregate warnings.</span></span>|  
    |<span data-ttu-id="223f4-139">16</span><span class="sxs-lookup"><span data-stu-id="223f4-139">16</span></span>|<span data-ttu-id="223f4-140">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="223f4-140">ANSI_PADDING</span></span>|<span data-ttu-id="223f4-141">Controla los valores de relleno de las variables de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="223f4-141">Controls padding of fixed-length variables.</span></span>|  
    |<span data-ttu-id="223f4-142">32</span><span class="sxs-lookup"><span data-stu-id="223f4-142">32</span></span>|<span data-ttu-id="223f4-143">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="223f4-143">ANSI_NULLS</span></span>|<span data-ttu-id="223f4-144">Controla el tratamiento de los valores NULL cuando se utilizan operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="223f4-144">Controls NULL handling when using equality operators.</span></span>|  
    |<span data-ttu-id="223f4-145">64</span><span class="sxs-lookup"><span data-stu-id="223f4-145">64</span></span>|<span data-ttu-id="223f4-146">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="223f4-146">ARITHABORT</span></span>|<span data-ttu-id="223f4-147">Cancela una consulta cuando se produce un error de desbordamiento o división por cero durante su ejecución.</span><span class="sxs-lookup"><span data-stu-id="223f4-147">Terminates a query when an overflow or divide-by-zero error occurs during query execution.</span></span>|  
    |<span data-ttu-id="223f4-148">128</span><span class="sxs-lookup"><span data-stu-id="223f4-148">128</span></span>|<span data-ttu-id="223f4-149">ARITHIGNORE</span><span class="sxs-lookup"><span data-stu-id="223f4-149">ARITHIGNORE</span></span>|<span data-ttu-id="223f4-150">Devuelve un valor NULL cuando se produce un error de desbordamiento o de división por cero durante una consulta.</span><span class="sxs-lookup"><span data-stu-id="223f4-150">Returns NULL when an overflow or divide-by-zero error occurs during a query.</span></span>|  
    |<span data-ttu-id="223f4-151">256</span><span class="sxs-lookup"><span data-stu-id="223f4-151">256</span></span>|<span data-ttu-id="223f4-152">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="223f4-152">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="223f4-153">Diferencia entre las comillas simples o dobles al evaluar una expresión.</span><span class="sxs-lookup"><span data-stu-id="223f4-153">Differentiates between single and double quotation marks when evaluating an expression.</span></span>|  
    |<span data-ttu-id="223f4-154">512</span><span class="sxs-lookup"><span data-stu-id="223f4-154">512</span></span>|<span data-ttu-id="223f4-155">NOCOUNT</span><span class="sxs-lookup"><span data-stu-id="223f4-155">NOCOUNT</span></span>|<span data-ttu-id="223f4-156">Desactiva el mensaje que se devuelve al final de cada instrucción, que indica el número de filas afectadas.</span><span class="sxs-lookup"><span data-stu-id="223f4-156">Turns off the message returned at the end of each statement that states how many rows were affected.</span></span>|  
    |<span data-ttu-id="223f4-157">1024</span><span class="sxs-lookup"><span data-stu-id="223f4-157">1024</span></span>|<span data-ttu-id="223f4-158">ANSI_NULL_DFLT_ON</span><span class="sxs-lookup"><span data-stu-id="223f4-158">ANSI_NULL_DFLT_ON</span></span>|<span data-ttu-id="223f4-159">Altera el comportamiento de la sesión para que utilice la compatibilidad con ANSI para la nulabilidad.</span><span class="sxs-lookup"><span data-stu-id="223f4-159">Alters the session's behavior to use ANSI compatibility for nullability.</span></span> <span data-ttu-id="223f4-160">Se permite la nulabilidad para las nuevas columnas definidas sin la aceptación explícita de estos valores.</span><span class="sxs-lookup"><span data-stu-id="223f4-160">New columns defined without explicit nullability are defined to allow nulls.</span></span>|  
    |<span data-ttu-id="223f4-161">2048</span><span class="sxs-lookup"><span data-stu-id="223f4-161">2048</span></span>|<span data-ttu-id="223f4-162">ANSI_NULL_DFLT_OFF</span><span class="sxs-lookup"><span data-stu-id="223f4-162">ANSI_NULL_DFLT_OFF</span></span>|<span data-ttu-id="223f4-163">Altera el comportamiento de la sesión para que no utilice la compatibilidad con ANSI para la nulabilidad.</span><span class="sxs-lookup"><span data-stu-id="223f4-163">Alters the session's behavior not to use ANSI compatibility for nullability.</span></span> <span data-ttu-id="223f4-164">Las nuevas columnas definidas sin la nulabilidad no aceptan estos valores.</span><span class="sxs-lookup"><span data-stu-id="223f4-164">New columns defined without explicit nullability do not allow nulls.</span></span>|  
    |<span data-ttu-id="223f4-165">4096</span><span class="sxs-lookup"><span data-stu-id="223f4-165">4096</span></span>|<span data-ttu-id="223f4-166">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="223f4-166">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="223f4-167">Devuelve un valor NULL al concatenar un valor NULL con una cadena.</span><span class="sxs-lookup"><span data-stu-id="223f4-167">Returns NULL when concatenating a NULL value with a string.</span></span>|  
    |<span data-ttu-id="223f4-168">8192</span><span class="sxs-lookup"><span data-stu-id="223f4-168">8192</span></span>|<span data-ttu-id="223f4-169">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="223f4-169">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="223f4-170">Genera un error cuando se produce una pérdida de precisión en una expresión.</span><span class="sxs-lookup"><span data-stu-id="223f4-170">Generates an error when a loss of precision occurs in an expression.</span></span>|  
    |<span data-ttu-id="223f4-171">16384</span><span class="sxs-lookup"><span data-stu-id="223f4-171">16384</span></span>|<span data-ttu-id="223f4-172">XACT_ABORT</span><span class="sxs-lookup"><span data-stu-id="223f4-172">XACT_ABORT</span></span>|<span data-ttu-id="223f4-173">Revierte una transacción si una instrucción Transact- SQL produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="223f4-173">Rolls back a transaction if a Transact-SQL statement raises a run-time error.</span></span>|  
  
-   <span data-ttu-id="223f4-174">Las posiciones de bits de **opciones de usuario** son las mismas que las de la función @@OPTIONS.</span><span class="sxs-lookup"><span data-stu-id="223f4-174">The bit positions in **user options** are identical to those in @@OPTIONS.</span></span> <span data-ttu-id="223f4-175">Cada conexión tiene su propia función @@OPTIONS, que representa el entorno de configuración.</span><span class="sxs-lookup"><span data-stu-id="223f4-175">Each connection has its own @@OPTIONS function, which represents the configuration environment.</span></span> <span data-ttu-id="223f4-176">Cuando se inicia una sesión en una instancia de \ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el usuario recibe un entorno de configuración predeterminado que asigna el valor actual para **opciones de usuario** a la función @@OPTIONS.</span><span class="sxs-lookup"><span data-stu-id="223f4-176">When logging in to an instance of \ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a user receives a default environment that assigns the current **user options** value to @@OPTIONS.</span></span> <span data-ttu-id="223f4-177">La ejecución de instrucciones SET para **user options** afecta al valor correspondiente de la función @@OPTIONS de la sesión.</span><span class="sxs-lookup"><span data-stu-id="223f4-177">Executing SET statements for **user options** affects the corresponding value in the session's @@OPTIONS function.</span></span> <span data-ttu-id="223f4-178">Todas las conexiones que se crean después de modificar esta opción recibirán el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="223f4-178">All connections created after this setting is changed receive the new value.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="223f4-179">Seguridad</span><span class="sxs-lookup"><span data-stu-id="223f4-179">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="223f4-180">Permisos</span><span class="sxs-lookup"><span data-stu-id="223f4-180">Permissions</span></span>  
 <span data-ttu-id="223f4-181">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="223f4-181">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="223f4-182">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="223f4-182">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="223f4-183">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="223f4-183">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="223f4-184">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="223f4-184">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-user-options-configuration-option"></a><span data-ttu-id="223f4-185">Para configurar la opción de configuración para opciones de usuario</span><span class="sxs-lookup"><span data-stu-id="223f4-185">To configure the user options configuration option</span></span>  
  
1.  <span data-ttu-id="223f4-186">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="223f4-186">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="223f4-187">Haga clic en el nodo **Conexiones** .</span><span class="sxs-lookup"><span data-stu-id="223f4-187">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="223f4-188">En el cuadro **Opciones predeterminadas de conexión** , seleccione uno o más atributos para configurar las opciones predeterminadas del procesamiento de consultas para todos los usuarios conectados.</span><span class="sxs-lookup"><span data-stu-id="223f4-188">In the **Default connection options** box, select one or more attributes to configure the default query-processing options for all connected users.</span></span>  
  
     <span data-ttu-id="223f4-189">De manera predeterminada, no hay ninguna opción de usuario configurada.</span><span class="sxs-lookup"><span data-stu-id="223f4-189">By default, no user options are configured.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="223f4-190">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="223f4-190">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-user-options-configuration-option"></a><span data-ttu-id="223f4-191">Para configurar la opción de configuración para opciones de usuario</span><span class="sxs-lookup"><span data-stu-id="223f4-191">To configure the user options configuration option</span></span>  
  
1.  <span data-ttu-id="223f4-192">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="223f4-192">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="223f4-193">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="223f4-193">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="223f4-194">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="223f4-194">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="223f4-195">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar `user options` para cambiar el valor de la opción de servidor ANSI_WARNINGS.</span><span class="sxs-lookup"><span data-stu-id="223f4-195">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `user options` to change the setting for the ANSI_WARNINGS server option.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'user options', 8 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-user-options-configuration-option"></a><a name="FollowUp"></a> <span data-ttu-id="223f4-196">Seguimiento: Después de configurar la opción de configuración para opciones de usuario</span><span class="sxs-lookup"><span data-stu-id="223f4-196">Follow Up: After you configure the user options configuration option</span></span>  
 <span data-ttu-id="223f4-197">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="223f4-197">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223f4-198">Consulte también</span><span class="sxs-lookup"><span data-stu-id="223f4-198">See Also</span></span>  
 <span data-ttu-id="223f4-199">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="223f4-199">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="223f4-200">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="223f4-200">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="223f4-201">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="223f4-201">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="223f4-202">Instrucciones SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="223f4-202">SET Statements &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-statements-transact-sql)  
  
  