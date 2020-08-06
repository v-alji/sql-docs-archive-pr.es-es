---
title: Compatibilidad con versiones anteriores en SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 2f986436-aaf2-4eaf-9809-df849d97d4fb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73b6f4eebccf23850ccf08ec95ccb59dbc5c6293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672911"
---
# <a name="backward-compatibility-in-smo"></a><span data-ttu-id="ff3b2-102">Compatibilidad con versiones anteriores en SMO</span><span class="sxs-lookup"><span data-stu-id="ff3b2-102">Backward Compatibility in SMO</span></span>
  <span data-ttu-id="ff3b2-103">Las aplicaciones de SMO que se escribieron utilizando versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se pueden volver a compilar utilizando SMO en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff3b2-103">SMO applications that were written using previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be recompiled by using SMO in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="migrating-smo-applications"></a><span data-ttu-id="ff3b2-104">Migrar aplicaciones de SMO</span><span class="sxs-lookup"><span data-stu-id="ff3b2-104">Migrating SMO Applications</span></span>  
 <span data-ttu-id="ff3b2-105">Se deben quitar las referencias a archivos dll de SMO en las versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y se deben incluir las referencias a los nuevos archivos dll de SMO proporcionados con [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff3b2-105">References to SMO dlls in older versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed, and references to the new SMO dlls that are provided with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be included.</span></span>  
  
 <span data-ttu-id="ff3b2-106">Como mínimo, debe hacer referencia a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff3b2-106">Minimally, you would reference the following:</span></span>  
  
-   <span data-ttu-id="ff3b2-107">Microsoft.SqlServer.ConnectionInfo</span><span class="sxs-lookup"><span data-stu-id="ff3b2-107">Microsoft.SqlServer.ConnectionInfo</span></span>  
  
-   <span data-ttu-id="ff3b2-108">Microsoft.SqlServer.Smo</span><span class="sxs-lookup"><span data-stu-id="ff3b2-108">Microsoft.SqlServer.Smo</span></span>  
  
-   <span data-ttu-id="ff3b2-109">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="ff3b2-109">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
 <span data-ttu-id="ff3b2-110">Estos archivos son necesarios para las clases de conexión, las clases de utilidad SMO y las clases de fundación.</span><span class="sxs-lookup"><span data-stu-id="ff3b2-110">These files are required for connection classes, SMO utility classes, and foundation classes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff3b2-111">Se ha eliminado SmoEnum.dll por lo que deben eliminarse las referencias a esta dll del proyecto [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] de SMO.</span><span class="sxs-lookup"><span data-stu-id="ff3b2-111">SmoEnum.dll has been removed so references to it must be removed from the SMO [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] project.</span></span>  
  
 <span data-ttu-id="ff3b2-112">Los espacios de nombres también han cambiado; puede usar los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff3b2-112">The namespaces have also changed, so you can use the following:</span></span>  
  
##### <a name="for-visual-c"></a><span data-ttu-id="ff3b2-113">Para Visual C#</span><span class="sxs-lookup"><span data-stu-id="ff3b2-113">For Visual C#</span></span>  
  
```  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
```  
  
##### <a name="for-visual-basic"></a><span data-ttu-id="ff3b2-114">Para Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff3b2-114">For Visual Basic</span></span>  
  
```  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
```  
  
 <span data-ttu-id="ff3b2-115">Si el código usa la funcionalidad Urn como `Server.GetSqlSmoObject(Urn)`, debe efectuar un vínculo al espacio de nombres Microsoft.SqlServer.Management.Sdk.Sfc.</span><span class="sxs-lookup"><span data-stu-id="ff3b2-115">If your code uses Urn functionality, such as `Server.GetSqlSmoObject(Urn)`, you must link to the Microsoft.SqlServer.Management.Sdk.Sfc namespace.</span></span>  
  
 <span data-ttu-id="ff3b2-116">Si el código usa el objeto Transfer directamente, tendrá que efectuar un vínculo al espacio de nombres Microsoft.SqlServer.Management.SmoExtended.</span><span class="sxs-lookup"><span data-stu-id="ff3b2-116">If your code uses the Transfer object directly, you will have to link to the Microsoft.SqlServer.Management.SmoExtended namespace.</span></span>  
  
 <span data-ttu-id="ff3b2-117">Al migrar código, es posible que tenga que modificarlo.</span><span class="sxs-lookup"><span data-stu-id="ff3b2-117">When you migrate code, you might have to modify the code.</span></span> <span data-ttu-id="ff3b2-118">Esto ocurre porque varias características de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] se han quedado en desuso en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff3b2-118">This is because several [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] features have been deprecated in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="ff3b2-119">Para obtener más información acerca de las características en desuso, vea [características Desusadas motor de base de datos en SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) en los [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] libros en pantalla de.</span><span class="sxs-lookup"><span data-stu-id="ff3b2-119">For more information about deprecated features, see [Deprecated Database Engine Features in SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
