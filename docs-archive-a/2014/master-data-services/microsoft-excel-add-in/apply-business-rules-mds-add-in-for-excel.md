---
title: Aplicar reglas de negocios (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: cd106345-f561-4966-88d3-a69139b2bd78
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aad5ce6bcebb635fa4659c32654d67406d4ba0dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745360"
---
# <a name="apply-business-rules-mds-add-in-for-excel"></a><span data-ttu-id="379c6-102">Aplicar reglas de negocios (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="379c6-102">Apply Business Rules (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="379c6-103">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] , puede aplicar reglas de negocios cuando desee validar datos y confirmar que son válidos.</span><span class="sxs-lookup"><span data-stu-id="379c6-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] apply business rules when you want to validate data and confirm that it is valid.</span></span> <span data-ttu-id="379c6-104">Puede corregir validaciones y volver a publicar los datos.</span><span class="sxs-lookup"><span data-stu-id="379c6-104">You can correct validations and re-publish the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="379c6-105">La validación de datos aparece automáticamente al publicar datos.</span><span class="sxs-lookup"><span data-stu-id="379c6-105">Data validation occurs automatically when you publish data.</span></span> <span data-ttu-id="379c6-106">Para obtener más información, consulte [Procedimiento almacenado de validación &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="379c6-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="379c6-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="379c6-107">Prerequisites</span></span>  
 <span data-ttu-id="379c6-108">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="379c6-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="379c6-109">Debe tener acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="379c6-109">You must have access to the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="379c6-110">Debe tener una hoja de cálculo activa que contenga datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="379c6-110">You must have an active worksheet that contains MDS-managed data.</span></span>  
  
### <a name="to-apply-business-rules"></a><span data-ttu-id="379c6-111">Para aplicar reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="379c6-111">To apply business rules</span></span>  
  
1.  <span data-ttu-id="379c6-112">En el grupo **Publicar y validar** , haga clic **Aplicar las reglas**.</span><span class="sxs-lookup"><span data-stu-id="379c6-112">In the **Publish and Validate** group, click **Apply Rules**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="379c6-113">El número de miembros (filas) que se validan al mismo tiempo depende de un valor de [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="379c6-113">The number of members (rows) that are validated at one time depends on a setting in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="379c6-114">Para más información, consulte [Business Rule Settings](../system-settings-master-data-services.md#BusinessRules).</span><span class="sxs-lookup"><span data-stu-id="379c6-114">For more information, see [Business Rule Settings](../system-settings-master-data-services.md#BusinessRules).</span></span>  
  
2.  <span data-ttu-id="379c6-115">Los datos se validan comparándolos con las reglas de negocios y se muestran dos columnas de estado.</span><span class="sxs-lookup"><span data-stu-id="379c6-115">The data is validated against business rules and two status columns are displayed.</span></span> <span data-ttu-id="379c6-116">Si estas columnas no se muestran automáticamente, en el grupo **Publicar y validar** , haga clic en **Mostrar estado** para verlas.</span><span class="sxs-lookup"><span data-stu-id="379c6-116">If these columns are not displayed automatically, in the **Publish and Validate** group, click **Show Status** to view them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="379c6-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="379c6-117">See Also</span></span>  
 [<span data-ttu-id="379c6-118">Complemento MDS para Excel de &#40;de datos de publicación&#41;</span><span class="sxs-lookup"><span data-stu-id="379c6-118">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
