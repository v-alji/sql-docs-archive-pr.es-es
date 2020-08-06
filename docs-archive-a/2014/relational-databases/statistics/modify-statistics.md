---
title: Modificación de estadísticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], modifying
- modifying statistics
ms.assetid: b06299ca-ed52-411a-b245-45eac4628c99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6dd44da6d1a80050f37f08e49773f95af0e5a339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676408"
---
# <a name="modify-statistics"></a><span data-ttu-id="264b6-102">Modificar estadísticas</span><span class="sxs-lookup"><span data-stu-id="264b6-102">Modify Statistics</span></span>
  <span data-ttu-id="264b6-103">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , puede modificar las estadísticas existentes mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="264b6-103">You can modify existing statistics in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="264b6-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="264b6-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="264b6-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="264b6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="264b6-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="264b6-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="264b6-107">**Para modificar las estadísticas, use:**</span><span class="sxs-lookup"><span data-stu-id="264b6-107">**To modify statistics, using:**</span></span>  
  
     [<span data-ttu-id="264b6-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="264b6-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="264b6-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="264b6-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="264b6-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="264b6-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="264b6-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="264b6-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="264b6-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="264b6-112">Permissions</span></span>  
 <span data-ttu-id="264b6-113">Requiere que:</span><span class="sxs-lookup"><span data-stu-id="264b6-113">Requires that:</span></span>  
  
-   <span data-ttu-id="264b6-114">El usuario tiene el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="264b6-114">The user has ALTER permission on the table or view.</span></span>  
  
-   <span data-ttu-id="264b6-115">El usuario debe ser el propietario de la tabla o vista indexada o un miembro de uno de los roles siguientes: rol fijo de servidor **sysadmin** , rol fijo de base de datos **db_owner** o rol fijo de base de datos **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="264b6-115">The user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="264b6-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="264b6-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-statistics"></a><span data-ttu-id="264b6-117">Para modificar las estadísticas</span><span class="sxs-lookup"><span data-stu-id="264b6-117">To modify statistics</span></span>  
  
1.  <span data-ttu-id="264b6-118">En el **Explorador de objetos**, haga clic en el signo más para expandir la base de datos en la que desea modificar una estadística.</span><span class="sxs-lookup"><span data-stu-id="264b6-118">In **Object Explorer**, click the plus sign to expand the database in which you want to modify a statistic.</span></span>  
  
2.  <span data-ttu-id="264b6-119">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="264b6-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="264b6-120">Haga clic en el signo más para expandir la tabla en la que desea modificar una estadística.</span><span class="sxs-lookup"><span data-stu-id="264b6-120">Click the plus sign to expand the table in which you want to modify a statistic.</span></span>  
  
4.  <span data-ttu-id="264b6-121">Haga clic en el signo más para expandir la carpeta **Estadísticas** .</span><span class="sxs-lookup"><span data-stu-id="264b6-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="264b6-122">Haga clic con el botón derecho en el objeto de estadísticas que quiera modificar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="264b6-122">Right-click the statistics object that you wish to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="264b6-123">En el cuadro de diálogo **Propiedades de estadísticas:** *nombre de estadísticas*, en la página **General**, haga clic en **Agregar**, **Quitar**, **Subir** o **Bajar**, o cualquier combinación, para alterar las propiedades de las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="264b6-123">In the **Statistics Properties -** *statistics_name* dialog box, on the **General** page, click **Add**, **Remove**, **Move Up**, or **Move Down**, or any combination, to alter the properties of the statistics.</span></span> <span data-ttu-id="264b6-124">Recuerde que la ubicación de una columna dentro de la cuadrícula **Columnas de estadísticas** puede afectar considerablemente a la utilidad de las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="264b6-124">Remember that a column's location within the **Statistics Columns** grid can substantially impact the usefulness of the statistics.</span></span>  
  
7.  <span data-ttu-id="264b6-125">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="264b6-125">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="264b6-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="264b6-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="264b6-127">**Para modificar las estadísticas**</span><span class="sxs-lookup"><span data-stu-id="264b6-127">**To modify statistics**</span></span>  
  
 <span data-ttu-id="264b6-128">Esta tarea no se puede realizar mediante instrucciones Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="264b6-128">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="264b6-129">Para modificar las estadísticas con Transact-SQL, primero debe eliminar la estadística existente y, a continuación, volver a crearla con nuevos atributos.</span><span class="sxs-lookup"><span data-stu-id="264b6-129">To modify statistics using Transact-SQL, you must first delete the existing statistic and then re-create it with new attributes.</span></span>  
  
 <span data-ttu-id="264b6-130">Para obtener más información, vea [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) y [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="264b6-130">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) and [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
