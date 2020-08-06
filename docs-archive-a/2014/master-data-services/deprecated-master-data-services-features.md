---
title: Características desusadas Master Data Services en SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d8506bda-66dd-45a4-bfc9-3a10fa665acc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce532e9f407ec475f7e59c0d79659265a9e0bf3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744162"
---
# <a name="deprecated-master-data-services-features-in-sql-server-2014"></a><span data-ttu-id="d0947-102">Características desusadas de Master Data Services en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="d0947-102">Deprecated Master Data Services Features in SQL Server 2014</span></span>
  <span data-ttu-id="d0947-103">Este tema describe las características desusadas de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] que siguen estando disponibles en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0947-103">This topic describes the deprecated [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d0947-104">Está previsto quitar estas características en una futura versión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0947-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d0947-105">Las características en desuso no se deben usar en nuevas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d0947-105">Deprecated features should not be used in new applications.</span></span>  
  
## <a name="staging-process"></a><span data-ttu-id="d0947-106">Proceso de almacenamiento provisional</span><span class="sxs-lookup"><span data-stu-id="d0947-106">Staging Process</span></span>  
 <span data-ttu-id="d0947-107">El proceso de almacenamiento provisional que se empleaba en [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] ya no está disponible en la aplicación web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]; sin embargo, todavía está disponible en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0947-107">The staging process that was used in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] is no longer available in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application; however it is still available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="d0947-108">Los errores del proceso de almacenamiento provisional de [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] ya no se muestran en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="d0947-108">Staging errors from the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging process are no longer displayed in the UI.</span></span> <span data-ttu-id="d0947-109">Los códigos de error que se rellenan durante el proceso de almacenamiento provisional siguen estando disponibles en las tablas de almacenamiento provisional y se pueden encontrar aquí: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d0947-109">Error codes that are populated during the staging process are still available in the staging tables, and can be found here: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx).</span></span>  
  
 <span data-ttu-id="d0947-110">Las tablas de ensayo (tblStgMember, tblStgMemberAttribute y tblStgRelationship) siguen estando disponibles en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d0947-110">The staging tables (tblStgMember, tblStgMemberAttribute, and tblStgRelationship) are still available in the database.</span></span> <span data-ttu-id="d0947-111">El procedimiento almacenado usado para iniciar el proceso de almacenamiento provisional (mdm.udpStagingSweep) sigue estando disponible en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d0947-111">The stored procedure used to initiate the staging process (mdm.udpStagingSweep) is still available in the database.</span></span>  
  
 <span data-ttu-id="d0947-112">Los métodos de servicio web que llaman al proceso de almacenamiento provisional siguen estando disponibles.</span><span class="sxs-lookup"><span data-stu-id="d0947-112">The web service methods that call the staging process are still available.</span></span>  
  
 <span data-ttu-id="d0947-113">El intervalo de almacenamiento provisional establecido en [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] se aplica al proceso de almacenamiento provisional tanto en [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] como en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0947-113">The staging interval set in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] applies to the staging process in both [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] and [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="d0947-114">En [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] se ha implementado un proceso de almacenamiento temporal nuevo y de mayor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d0947-114">A new, higher performance staging process has been implemented in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d0947-115">Para más información, vea [Importación de datos &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d0947-115">For more information, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
## <a name="metadata"></a><span data-ttu-id="d0947-116">Metadatos</span><span class="sxs-lookup"><span data-stu-id="d0947-116">Metadata</span></span>  
 <span data-ttu-id="d0947-117">Aunque el modelo metadatos se sigue mostrando en la aplicación web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="d0947-117">Though the Metadata model is still displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, it should not be used.</span></span> <span data-ttu-id="d0947-118">Se eliminará en una próxima versión.</span><span class="sxs-lookup"><span data-stu-id="d0947-118">It will be removed in a future release.</span></span> <span data-ttu-id="d0947-119">Los usuarios también pueden dejar de ver los metadatos en el área funcional del **Explorador** y ya no se pueden crear versiones del modelo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d0947-119">Users can also no longer view metadata in the **Explorer** functional area, and you can no longer create versions of the Metadata model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0947-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d0947-120">See Also</span></span>  
 [<span data-ttu-id="d0947-121">Características descontinuadas de Master Data Services en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="d0947-121">Discontinued Master Data Services Features in SQL Server 2014</span></span>](discontinued-master-data-services-features.md)  
  
  
