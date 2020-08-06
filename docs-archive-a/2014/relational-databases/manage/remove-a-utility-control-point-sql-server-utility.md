---
title: Eliminación de un punto de control de la utilidad de SQL Server (utilidad de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c048a416-900e-4c77-8243-e0f0d8b94068
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fe4ebb9de3f7644b4cff5c7dbfb34e50be7e8993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677626"
---
# <a name="remove-a-utility-control-point-sql-server-utility"></a><span data-ttu-id="ff735-102">Quitar un punto de control de la utilidad de SQL Server (utilidad de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ff735-102">Remove a Utility Control Point (SQL Server Utility)</span></span>
  <span data-ttu-id="ff735-103">En este tema se describe cómo quitar un punto de control de la utilidad (UCP) de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff735-103">This topic describes how to remove a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utility control point (UCP) from the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ff735-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="ff735-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ff735-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="ff735-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ff735-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ff735-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ff735-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ff735-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ff735-108">**Para quitar un punto de control de la utilidad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="ff735-108">**To remove a Utility Control Point, using:**</span></span>  
  
     [<span data-ttu-id="ff735-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ff735-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ff735-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ff735-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ff735-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ff735-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ff735-112">Antes de utilizar este procedimiento para quitar el UCP de la Utilidad [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , tenga en cuenta los siguientes requisitos.</span><span class="sxs-lookup"><span data-stu-id="ff735-112">Before you use this procedure to remove the UCP from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, note the following requirements.</span></span> <span data-ttu-id="ff735-113">El procedimiento almacenado ejecutará las comprobaciones de los requisitos previos como parte de la operación.</span><span class="sxs-lookup"><span data-stu-id="ff735-113">The stored procedure will run prerequisite checks as part of the operation.</span></span>  
  
-   <span data-ttu-id="ff735-114">Antes de ejecutar este procedimiento, todas las instancias administradas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se deben quitar del UCP.</span><span class="sxs-lookup"><span data-stu-id="ff735-114">Before you run this procedure, all managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed from the UCP.</span></span> <span data-ttu-id="ff735-115">Tenga en cuenta que el UCP es una instancia administrada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff735-115">Note that the UCP is a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ff735-116">Para obtener más información, vea [Quitar una instancia de SQL Server de la Utilidad de SQL Server](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ff735-116">From more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
-   <span data-ttu-id="ff735-117">Este procedimiento se tiene que ejecutar en un equipo que sea un UCP.</span><span class="sxs-lookup"><span data-stu-id="ff735-117">This procedure must be run on a computer that is a UCP.</span></span>  
  
-   <span data-ttu-id="ff735-118">Si la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la que se quitó el UCP tiene un conjunto de recopilación de datos que no es de utilidad, el procedimiento no quitará la base de datos UMDW (sysutility_mdw).</span><span class="sxs-lookup"><span data-stu-id="ff735-118">If the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the UCP was removed has a non-Utility data collection set, the UMDW database (sysutility_mdw) will not be dropped by the procedure.</span></span> <span data-ttu-id="ff735-119">Si es así, la base de datos UMDW (sysutility_mdw) se debe quitar de modo manual para poder volver a crear el UCP.</span><span class="sxs-lookup"><span data-stu-id="ff735-119">If this is the case, the UMDW database (sysutility_mdw) must be dropped manually before the UCP can be created again.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ff735-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ff735-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ff735-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="ff735-121">Permissions</span></span>  
 <span data-ttu-id="ff735-122">Para ejecutar este procedimiento, el usuario debe tener permisos `sysadmin`, los mismos que se necesitan para crear un UCP.</span><span class="sxs-lookup"><span data-stu-id="ff735-122">This procedure must be run by a user with `sysadmin` permissions; the same permissions required to create a UCP.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ff735-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ff735-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-utility-control-point"></a><span data-ttu-id="ff735-124">Para quitar un punto de control de la utilidad</span><span class="sxs-lookup"><span data-stu-id="ff735-124">To remove a Utility Control Point</span></span>  
  
1.  <span data-ttu-id="ff735-125">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff735-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ff735-126">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="ff735-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ff735-127">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ff735-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```  
EXEC msdb.dbo.sp_sysutility_ucp_remove;  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff735-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff735-128">See Also</span></span>  
 <span data-ttu-id="ff735-129">[Características y tareas de la utilidad de SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="ff735-129">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="ff735-130">[Utilizar el explorador de Utilidad para administrar la utilidad de SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ff735-130">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="ff735-131">Solucionar problemas de la Utilidad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff735-131">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
