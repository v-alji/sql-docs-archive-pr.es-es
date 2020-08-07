---
title: Ver los errores que se producen durante el proceso de almacenamiento provisional (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], viewing errors
ms.assetid: 6d2bff84-624b-47fc-a4a5-d9ea01d13412
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3b39d039b29090f3021c764126ebb782ce25cbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745854"
---
# <a name="view-errors-that-occur-during-the-staging-process-master-data-services"></a><span data-ttu-id="88aea-102">Ver los errores que se producen durante el proceso de almacenamiento provisional (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="88aea-102">View Errors that Occur During the Staging Process (Master Data Services)</span></span>
  <span data-ttu-id="88aea-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], puede ver los errores que se producen durante el proceso de almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="88aea-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can view errors that occur during the staging process.</span></span> <span data-ttu-id="88aea-104">En la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , hay dos vistas que muestran errores:</span><span class="sxs-lookup"><span data-stu-id="88aea-104">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, there are two views that show errors:</span></span>  
  
-   <span data-ttu-id="88aea-105">stg.viw_name_MemberErrorDetails para las actualizaciones de miembros hoja o consolidados.</span><span class="sxs-lookup"><span data-stu-id="88aea-105">stg.viw_name_MemberErrorDetails for leaf or consolidated member updates.</span></span>  
  
-   <span data-ttu-id="88aea-106">stg.viw_name_RelationshipErrorDetails para las actualizaciones de la relación de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="88aea-106">stg.viw_name_RelationshipErrorDetails for hierarchy relationship updates.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="88aea-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="88aea-107">Prerequisites</span></span>  
 <span data-ttu-id="88aea-108">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="88aea-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="88aea-109">En la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , debe tener permisos SELECT en las vistas stg.viw_name_MemberErrorDetails o stg.viw_name_RelationshipErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="88aea-109">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, you must have SELECT permissions to either the stg.viw_name_MemberErrorDetails or stg.viw_name_RelationshipErrorDetails view.</span></span>  
  
-   <span data-ttu-id="88aea-110">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="88aea-110">You must be a model administrator.</span></span> <span data-ttu-id="88aea-111">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="88aea-111">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-view-staging-errors"></a><span data-ttu-id="88aea-112">Para ver errores de almacenamiento provisional</span><span class="sxs-lookup"><span data-stu-id="88aea-112">To view staging errors</span></span>  
  
1.  <span data-ttu-id="88aea-113">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] y conéctese a la instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)] para la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88aea-113">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="88aea-114">Abra una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="88aea-114">Open a new query.</span></span>  
  
3.  <span data-ttu-id="88aea-115">Escriba el texto siguiente, reemplazando el nombre con el nombre de su tabla de ensayo; por ejemplo, viw_Product_MemberErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="88aea-115">Type the following text, replacing name with the name of your staging table, for example, viw_Product_MemberErrorDetails.</span></span>  
  
     `SELECT * FROM stg.viw_name_MemberErrorDetails`  
  
4.  <span data-ttu-id="88aea-116">Ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="88aea-116">Excecute the query.</span></span> <span data-ttu-id="88aea-117">Los detalles del error se muestran en el campo **ErrorDescription** .</span><span class="sxs-lookup"><span data-stu-id="88aea-117">Error details are displayed in the **ErrorDescription** field.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="88aea-118">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="88aea-118">Next Steps</span></span>  
 <span data-ttu-id="88aea-119">Para obtener más información sobre mensajes de error, consulte [Errores del proceso de almacenamiento provisional &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="88aea-119">For more details on error messages, see [Staging Process Errors &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88aea-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88aea-120">See Also</span></span>  
 <span data-ttu-id="88aea-121">[Master Data Services de &#40;de importación de datos&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="88aea-121">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="88aea-122">Solucionar problemas del proceso de almacenamiento provisional (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="88aea-122">Troubleshooting the Staging Process (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-the-staging-process-master-data-services.aspx)  
  
  
