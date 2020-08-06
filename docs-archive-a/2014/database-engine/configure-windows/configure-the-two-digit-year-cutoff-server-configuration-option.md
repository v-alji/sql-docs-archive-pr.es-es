---
title: Establecer la opción de configuración del servidor Fecha límite de año de dos dígitos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- two digit year cutoff option
- four-digit years [SQL Server]
ms.assetid: d94e81b6-f2e6-47ef-b497-ec3d827a1646
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c31c1d87c8b743132dd90d495f73ef711dc1f813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671160"
---
# <a name="configure-the-two-digit-year-cutoff-server-configuration-option"></a><span data-ttu-id="5e456-102">Establecer la opción de configuración del servidor Fecha límite de año de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="5e456-102">Configure the two digit year cutoff Server Configuration Option</span></span>
  <span data-ttu-id="5e456-103">En este tema se describe cómo configurar la opción de configuración de servidor **fecha límite de año de dos dígitos** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e456-103">This topic describes how to configure the **two digit year cutoff** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5e456-104">La opción de **fecha límite de año de dos dígitos** especifica un número entero entre 1753 y 9999 que representa el año límite para interpretar años de dos dígitos como años de cuatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="5e456-104">The **two digit year cutoff** option specifies an integer from 1753 to 9999 that represents the cutoff year for interpreting two-digit years as four-digit years.</span></span> <span data-ttu-id="5e456-105">El marco temporal predeterminado para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es de 1950 a 2049, que indica el año límite 2049.</span><span class="sxs-lookup"><span data-stu-id="5e456-105">The default time span for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 1950-2049, which represents a cutoff year of 2049.</span></span> <span data-ttu-id="5e456-106">Esto significa que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interpreta un año con dos dígitos igual a 49 como 2049, un año con dos dígitos igual a 50 como 1950 y un año con dos dígitos igual a 99 como 1999.</span><span class="sxs-lookup"><span data-stu-id="5e456-106">This means that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interprets a two-digit year of 49 as 2049, a two-digit year of 50 as 1950, and a two-digit year of 99 as 1999.</span></span> <span data-ttu-id="5e456-107">Para mantener la compatibilidad con las versiones anteriores, utilice el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5e456-107">To maintain backward compatibility, leave the setting at the default value.</span></span>  
  
 <span data-ttu-id="5e456-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5e456-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5e456-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5e456-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5e456-110">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="5e456-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5e456-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5e456-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5e456-112">**Para configurar la opción de fecha límite de año de dos dígitos, use:**</span><span class="sxs-lookup"><span data-stu-id="5e456-112">**To configure the two digit year cutoff option, using:**</span></span>  
  
     [<span data-ttu-id="5e456-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e456-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5e456-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e456-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="5e456-115">**Seguimiento:**  [Después de configurar la opción de fecha límite de año de dos dígitos](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5e456-115">**Follow Up:**  [After you configure the two digit year cutoff option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5e456-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5e456-116">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5e456-117">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="5e456-117">Recommendations</span></span>  
  
-   <span data-ttu-id="5e456-118">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="5e456-118">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="5e456-119">Los objetos de automatización OLE utilizan 2030 como el año límite de dos dígitos.</span><span class="sxs-lookup"><span data-stu-id="5e456-119">OLE Automation objects use 2030 as the two-digit cutoff year.</span></span> <span data-ttu-id="5e456-120">Puede utilizar la opción de **fecha límite de año de dos dígitos** para que los valores de fecha de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y las aplicaciones cliente sean coherentes.</span><span class="sxs-lookup"><span data-stu-id="5e456-120">You can use the **two digit year cutoff** option to provide consistency in date values between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and client applications.</span></span> <span data-ttu-id="5e456-121">No obstante, para evitar ambigüedades con las fechas, utilice años con cuatro dígitos en los datos.</span><span class="sxs-lookup"><span data-stu-id="5e456-121">However, to avoid ambiguity with dates, use four-digit years in your data.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5e456-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5e456-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5e456-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="5e456-123">Permissions</span></span>  
 <span data-ttu-id="5e456-124">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="5e456-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="5e456-125">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5e456-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="5e456-126">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="5e456-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5e456-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e456-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="5e456-128">Para configurar la opción de fecha límite de año de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="5e456-128">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="5e456-129">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5e456-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5e456-130">Haga clic en el nodo **Configuración adicional del servidor** .</span><span class="sxs-lookup"><span data-stu-id="5e456-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="5e456-131">En **Compatibilidad con años de dos dígitos**, en el cuadro **Cuando se escriba un año con dos dígitos**, **debe interpretarse como un año entre** , escriba o seleccione un valor que represente el último año del intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="5e456-131">Under **Two digit year support**, in the **When a two digit year is entered**, **interpret it as a year between** box, type or select a value that is the ending year of the time span.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5e456-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e456-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="5e456-133">Para configurar la opción de fecha límite de año de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="5e456-133">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="5e456-134">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e456-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e456-135">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5e456-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5e456-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5e456-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5e456-137">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `two digit year cutoff` en `2030`.</span><span class="sxs-lookup"><span data-stu-id="5e456-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `two digit year cutoff` option to `2030`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'two digit year cutoff', 2030 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="5e456-138">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5e456-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-two-digit-year-cutoff-option"></a><a name="FollowUp"></a> <span data-ttu-id="5e456-139">Seguimiento: Después de configurar la opción de fecha límite de año de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="5e456-139">Follow Up: After you configure the two digit year cutoff option</span></span>  
 <span data-ttu-id="5e456-140">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="5e456-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e456-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e456-141">See Also</span></span>  
 <span data-ttu-id="5e456-142">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5e456-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="5e456-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5e456-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="5e456-144">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5e456-144">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
