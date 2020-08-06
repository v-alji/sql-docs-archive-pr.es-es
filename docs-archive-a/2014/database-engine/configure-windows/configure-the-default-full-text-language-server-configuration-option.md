---
title: Establecer la opción de configuración del servidor Idioma de texto completo predeterminado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- languages [full-text search]
- default full-text language option
ms.assetid: 0fa8785b-0830-4a52-aff5-fcf8268b72fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ec0736326a4da0708d125bfc480996d54bb86c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663111"
---
# <a name="configure-the-default-full-text-language-server-configuration-option"></a><span data-ttu-id="8298a-102">Establecer la opción de configuración del servidor Idioma de texto completo predeterminado</span><span class="sxs-lookup"><span data-stu-id="8298a-102">Configure the default full-text language Server Configuration Option</span></span>
  <span data-ttu-id="8298a-103">En este tema se describe cómo configurar la `default full-text language` opción de configuración del servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8298a-103">This topic describes how to configure the `default full-text language` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8298a-104">La `default full-text language` opción especifica un valor de idioma predeterminado para los índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8298a-104">The `default full-text language` option specifies a default language value for full-text indexes.</span></span> <span data-ttu-id="8298a-105">Los análisis lingüísticos se realizan en todos los datos que tienen índices de texto completo y que dependen del idioma de los datos.</span><span class="sxs-lookup"><span data-stu-id="8298a-105">Linguistic analysis is performed on all data that is full-text indexed and is dependent on the language of the data.</span></span> <span data-ttu-id="8298a-106">El valor predeterminado de esta opción es el idioma del servidor.</span><span class="sxs-lookup"><span data-stu-id="8298a-106">The default value of this option is the language of the server.</span></span> <span data-ttu-id="8298a-107">En el caso de una versión localizada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] el programa de instalación de establece la `default full-text language` opción en el idioma del servidor si existe una coincidencia adecuada.</span><span class="sxs-lookup"><span data-stu-id="8298a-107">For a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup sets the `default full-text language` option to the language of the server if an appropriate match exists.</span></span> <span data-ttu-id="8298a-108">En las versiones no traducidas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la opción `default full-text language` es el inglés.</span><span class="sxs-lookup"><span data-stu-id="8298a-108">For a non-localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the `default full-text language` option is English.</span></span>  
  
 <span data-ttu-id="8298a-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="8298a-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8298a-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="8298a-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8298a-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="8298a-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8298a-112">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="8298a-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="8298a-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8298a-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8298a-114">**Para configurar la opción de idioma de texto completo predeterminado, use:**</span><span class="sxs-lookup"><span data-stu-id="8298a-114">**To configure the default full-text language option, using:**</span></span>  
  
     [<span data-ttu-id="8298a-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8298a-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8298a-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8298a-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="8298a-117">**Seguimiento:**  [Después de configurar la opción de idioma de texto completo predeterminado](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="8298a-117">**Follow Up:**  [After you configure the default full-text language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8298a-118">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8298a-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8298a-119">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="8298a-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8298a-120">El valor de la `default full-text language` opción se usa en un índice de texto completo cuando no se especifica ningún idioma para una columna a través de la opción language **language_term** en las instrucciones CREATE FULLTEXT index o ALTER fulltext index.</span><span class="sxs-lookup"><span data-stu-id="8298a-120">The value of the `default full-text language` option is used in a full-text index when no language is specified for a column through the LANGUAGE **language_term** option in the CREATE FULLTEXT INDEX or ALTER FULLTEXT INDEX statements.</span></span> <span data-ttu-id="8298a-121">Si el idioma predeterminado para búsqueda de texto completo no es compatible o el paquete de análisis lingüístico no está disponible, la operación CREATE o ALTER no será satisfactoria y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devolverá un mensaje de error que indica que el idioma especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="8298a-121">If the default full-text language is not supported or the linguistic analysis package is not available, the CREATE or ALTER operation will fail and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will return an error message stating that the language specified is not valid.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="8298a-122">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="8298a-122">Recommendations</span></span>  
  
-   <span data-ttu-id="8298a-123">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="8298a-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="8298a-124">La `default full-text language` opción requiere un valor LCID.</span><span class="sxs-lookup"><span data-stu-id="8298a-124">The `default full-text language` option requires an LCID value.</span></span> <span data-ttu-id="8298a-125">Para obtener una lista de los LCID admitidos y sus respectivos idiomas, vea [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8298a-125">For a list of supported LCIDs and their related languages, see [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span></span> <span data-ttu-id="8298a-126">Por ejemplo, es posible que haya otros idiomas disponibles de fabricantes independientes de software.</span><span class="sxs-lookup"><span data-stu-id="8298a-126">Other languages may also be available from independent software vendors, for example.</span></span> <span data-ttu-id="8298a-127">Si no se detecta ningún dialecto de idioma específico, el motor de texto completo cambiará automáticamente al idioma principal.</span><span class="sxs-lookup"><span data-stu-id="8298a-127">If no specific language dialect is found, the Full-Text Engine will automatically switch to the primary language.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8298a-128">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8298a-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8298a-129">Permisos</span><span class="sxs-lookup"><span data-stu-id="8298a-129">Permissions</span></span>  
 <span data-ttu-id="8298a-130">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="8298a-130">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="8298a-131">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="8298a-131">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="8298a-132">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="8298a-132">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8298a-133">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8298a-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="8298a-134">Para configurar la opción de idioma de texto completo predeterminado</span><span class="sxs-lookup"><span data-stu-id="8298a-134">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="8298a-135">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8298a-135">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="8298a-136">Haga clic en el nodo **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="8298a-136">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="8298a-137">En Varios, use la opción **Idioma de texto completo predeterminado** para especificar un valor de idioma predeterminado para las columnas indexadas de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8298a-137">Under Miscellaneous, use **Default Full Text Language** to specify a default language value for full-text indexed columns.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8298a-138">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8298a-138">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="8298a-139">Para configurar la opción de idioma de texto completo predeterminado</span><span class="sxs-lookup"><span data-stu-id="8298a-139">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="8298a-140">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8298a-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8298a-141">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="8298a-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8298a-142">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8298a-142">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8298a-143">Este ejemplo muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `default full-text` en Neerlandés (`1043`).</span><span class="sxs-lookup"><span data-stu-id="8298a-143">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `default full-text` option to Dutch (`1043`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'default full-text language', 1043 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="8298a-144">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8298a-144">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-full-text-language-option"></a><a name="FollowUp"></a> <span data-ttu-id="8298a-145">Seguimiento: Después de configurar la opción de idioma de texto completo predeterminado</span><span class="sxs-lookup"><span data-stu-id="8298a-145">Follow Up: After you configure the default full-text language option</span></span>  
 <span data-ttu-id="8298a-146">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="8298a-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8298a-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8298a-147">See Also</span></span>  
 <span data-ttu-id="8298a-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8298a-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span></span>  
 <span data-ttu-id="8298a-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8298a-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="8298a-150">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8298a-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="8298a-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8298a-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="8298a-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8298a-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="8298a-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8298a-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  
