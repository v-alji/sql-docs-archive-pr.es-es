---
title: Principales cambios en las características de las herramientas de administración en SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 11/27/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 3ff3fad8-b569-4516-bd58-5a3efeb537e2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0487b6ab0958e0b83d4e8e34be507b5b3211ac87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674374"
---
# <a name="breaking-changes-to-management-tools-features-in-sql-server-2014"></a><span data-ttu-id="8eb64-102">Últimos cambios en las características de las herramientas de administración de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8eb64-102">Breaking Changes to Management Tools Features in SQL Server 2014</span></span>
  <span data-ttu-id="8eb64-103">En este tema se describen los últimos cambios realizados en las características de las herramientas de administración.</span><span class="sxs-lookup"><span data-stu-id="8eb64-103">This topic describes breaking changes to management tools features.</span></span> <span data-ttu-id="8eb64-104">Estos cambios pueden provocar errores en las aplicaciones, en los scripts o en las funcionalidades basados en versiones anteriores de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8eb64-104">These changes might break applications, scripts, or functionalities that are based on earlier versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8eb64-105">Podría encontrar estos problemas al actualizar.</span><span class="sxs-lookup"><span data-stu-id="8eb64-105">You might encounter these issues when you upgrade.</span></span> <span data-ttu-id="8eb64-106">Para obtener más información, vea [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="8eb64-106">For more information, see [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span></span>  
  
## <a name="breaking-changes-in-sssql14"></a><span data-ttu-id="8eb64-107">Principales cambios en [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eb64-107">Breaking Changes in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
 <span data-ttu-id="8eb64-108">La información se proporcionará posteriormente.</span><span class="sxs-lookup"><span data-stu-id="8eb64-108">Information to come later.</span></span>  
  
## <a name="breaking-changes-in-sssql11"></a><span data-ttu-id="8eb64-109">Principales cambios en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eb64-109">Breaking Changes in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
  
### <a name="you-cannot-use-sssql11-management-tools-to-create-a-utility-control-point-on-a-sskilimanjaro-instance-of-sql-server"></a><span data-ttu-id="8eb64-110">No puede utilizar las Herramientas de administración de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] para crear un punto de control de la utilidad en una instancia de [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8eb64-110">You cannot use [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Management Tools to create a utility control point on a [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] instance of SQL Server</span></span>  
 <span data-ttu-id="8eb64-111">Para crear un punto de control de la utilidad en una instancia de [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], utilice las herramientas de administración de [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8eb64-111">To create a utility control point on an instance of [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], use [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] Management Tools.</span></span>  
  
### <a name="smo-has-been-reversioned-in-sssql11"></a><span data-ttu-id="8eb64-112">Se ha creado una nueva versión de SMO en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eb64-112">SMO has been reversioned in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
 <span data-ttu-id="8eb64-113">El código desarrollado con SMO de [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] o versiones anteriores podría no crearse en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] sin tener que hacer modificaciones.</span><span class="sxs-lookup"><span data-stu-id="8eb64-113">Code developed with SMO from [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] or earlier versions might not build against [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] without minor modifications.</span></span> <span data-ttu-id="8eb64-114">Para más información, consulte [Backward Compatibility in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span><span class="sxs-lookup"><span data-stu-id="8eb64-114">For more information, see [Backward Compatibility in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span></span>  

## <a name="breaking-changes-in-sql-server-2005"></a><a name="previous-versions"></a><span data-ttu-id="8eb64-115">Cambios importantes en SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="8eb64-115">Breaking Changes in SQL Server 2005</span></span>  

[!INCLUDE[Archived documentation for very old versions of SQL Server](../includes/paragraph-content/previous-versions-archive-documentation-sql-server.md)]

## <a name="see-also"></a><span data-ttu-id="8eb64-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8eb64-116">See Also</span></span>  
 [<span data-ttu-id="8eb64-117">Compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="8eb64-117">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
 [<span data-ttu-id="8eb64-118">Más información acerca de los cambios importantes en las características de las herramientas de administración en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8eb64-118">More about Breaking Changes to Management Tools Features in SQL Server 2014</span></span>](breaking-changes-to-database-engine-features-in-sql-server-2016.md?view=sql-server-2014)  
  
  
