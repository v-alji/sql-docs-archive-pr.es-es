---
title: Establecer la opción de configuración del servidor Factor de relleno | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fill factor option [SQL Server]
ms.assetid: b920ec34-ba8b-4bb8-af53-a3ffd06bafa6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02258c92b4a09277d371e605fd4729ba9fda3461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673898"
---
# <a name="configure-the-fill-factor-server-configuration-option"></a><span data-ttu-id="01ee3-102">Establecer la opción de configuración del servidor Factor de relleno</span><span class="sxs-lookup"><span data-stu-id="01ee3-102">Configure the fill factor Server Configuration Option</span></span>
  <span data-ttu-id="01ee3-103">En este tema se describe cómo establecer la opción de configuración del servidor **factor de relleno** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01ee3-103">This topic describes how to configure the **fill factor** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="01ee3-104">El factor de relleno permite optimizar el almacenamiento y rendimiento de los datos de índice.</span><span class="sxs-lookup"><span data-stu-id="01ee3-104">Fill factor is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="01ee3-105">Cuando se crea o se vuelve a generar un índice, el valor de factor de relleno determina el porcentaje de espacio en cada página de nivel de hoja que se tiene que rellenar con datos, reservándose el resto como espacio disponible para seguir creciendo.</span><span class="sxs-lookup"><span data-stu-id="01ee3-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the rest as free space for future growth.</span></span> <span data-ttu-id="01ee3-106">Para obtener más información, vea [Especificar el factor de relleno para un índice](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="01ee3-106">For more information, see [Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span></span>  
  
 <span data-ttu-id="01ee3-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="01ee3-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="01ee3-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="01ee3-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="01ee3-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="01ee3-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="01ee3-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="01ee3-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="01ee3-111">**Para configurar la opción de factor de relleno, use:**</span><span class="sxs-lookup"><span data-stu-id="01ee3-111">**To configure the fill factor option, using:**</span></span>  
  
     [<span data-ttu-id="01ee3-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="01ee3-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="01ee3-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="01ee3-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="01ee3-114">**Seguimiento:**  [Después de configurar la opción de factor de relleno](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="01ee3-114">**Follow Up:**  [After you configure the fill factor option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="01ee3-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="01ee3-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="01ee3-116">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="01ee3-116">Recommendations</span></span>  
  
-   <span data-ttu-id="01ee3-117">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="01ee3-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="01ee3-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="01ee3-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="01ee3-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="01ee3-119">Permissions</span></span>  
 <span data-ttu-id="01ee3-120">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="01ee3-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="01ee3-121">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="01ee3-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="01ee3-122">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="01ee3-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="01ee3-123">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="01ee3-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="01ee3-124">Para configurar la opción de factor de relleno</span><span class="sxs-lookup"><span data-stu-id="01ee3-124">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="01ee3-125">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="01ee3-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="01ee3-126">Haga clic en el nodo **Configuración de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="01ee3-126">Click the **Database Settings** node.</span></span>  
  
3.  <span data-ttu-id="01ee3-127">En el cuadro **Factor predeterminado de relleno de índices** , escriba o seleccione el factor de relleno de índices que desee.</span><span class="sxs-lookup"><span data-stu-id="01ee3-127">In the **Default index fill factor** box, type or select the index fill factor that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="01ee3-128">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="01ee3-128">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="01ee3-129">Para configurar la opción de factor de relleno</span><span class="sxs-lookup"><span data-stu-id="01ee3-129">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="01ee3-130">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01ee3-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="01ee3-131">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="01ee3-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="01ee3-132">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="01ee3-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="01ee3-133">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `fill factor` en `100`.</span><span class="sxs-lookup"><span data-stu-id="01ee3-133">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `fill factor` option to `100`.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="01ee3-134">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="01ee3-134">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-fill-factor-option"></a><a name="FollowUp"></a> <span data-ttu-id="01ee3-135">Seguimiento: Después de configurar la opción de factor de relleno</span><span class="sxs-lookup"><span data-stu-id="01ee3-135">Follow Up: After you configure the fill factor option</span></span>  
 <span data-ttu-id="01ee3-136">El servidor debe reiniciarse para que el valor surta efecto.</span><span class="sxs-lookup"><span data-stu-id="01ee3-136">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ee3-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01ee3-137">See Also</span></span>  
 <span data-ttu-id="01ee3-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01ee3-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="01ee3-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01ee3-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="01ee3-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01ee3-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="01ee3-141">[Especificar el factor de relleno para un índice](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="01ee3-141">[Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span></span>  
 <span data-ttu-id="01ee3-142">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="01ee3-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="01ee3-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01ee3-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="01ee3-144">sys.indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="01ee3-144">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
