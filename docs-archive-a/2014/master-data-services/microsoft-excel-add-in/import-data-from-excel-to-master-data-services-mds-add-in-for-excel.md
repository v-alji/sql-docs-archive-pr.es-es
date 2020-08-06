---
title: Publicar datos de Excel en MDS (Complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 89fce454-a816-4b33-a26a-d1b9741d269b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 597a954760816d8938628974998fe8f6daad1af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676029"
---
# <a name="publish-data-from-excel-to-mds-mds-add-in-for-excel"></a><span data-ttu-id="12a1c-102">Publicar datos de Excel en MDS (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="12a1c-102">Publish Data from Excel to MDS (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="12a1c-103">En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], puede publicar los datos en el repositorio MDS cuando termine de trabajar en Excel y desee guardar los cambios para que otros usuarios tengan acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="12a1c-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you are finished working in Excel and want to save your changes so other users have access to them.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="12a1c-104">Al publicar los cambios, se eliminan los comentarios de las celdas administradas por MDS.</span><span class="sxs-lookup"><span data-stu-id="12a1c-104">When you publish changes, comments on MDS-managed cells are deleted.</span></span>  
> -   <span data-ttu-id="12a1c-105">Una fórmula no se admite en una celda administrada por MDS.</span><span class="sxs-lookup"><span data-stu-id="12a1c-105">A formula is not supported in an MDS-managed cell.</span></span> <span data-ttu-id="12a1c-106">Una fórmula en una celda administrada por MDS se trata como un valor de texto.</span><span class="sxs-lookup"><span data-stu-id="12a1c-106">A formula in an MDS-managed cell is handled as a text value.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="12a1c-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="12a1c-107">Prerequisites</span></span>  
 <span data-ttu-id="12a1c-108">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="12a1c-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="12a1c-109">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="12a1c-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="12a1c-110">La hoja de cálculo activa debe contener datos administrados por MDS y debe haber realizado cambios o adiciones a los datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="12a1c-110">The active worksheet must contain MDS-managed data and you must have made changes or additions to the MDS-managed data.</span></span>  
  
-   <span data-ttu-id="12a1c-111">Si agrega miembros, no tiene que especificar un valor de **Código** si los códigos para la entidad se generan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="12a1c-111">If you are adding members, you do not have to specify a **Code** value if codes for the entity are being automatically generated.</span></span> <span data-ttu-id="12a1c-112">Para obtener más información, consulte [creación automática de código &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="12a1c-112">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span></span>  
  
### <a name="to-publish-data-to-the-mds-repository"></a><span data-ttu-id="12a1c-113">Publicar datos en el repositorio MDS</span><span class="sxs-lookup"><span data-stu-id="12a1c-113">To publish data to the MDS repository</span></span>  
  
1.  <span data-ttu-id="12a1c-114">En el grupo **Publicar y validar** , haga clic en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="12a1c-114">In the **Publish and Validate** group, click **Publish**.</span></span>  
  
2.  <span data-ttu-id="12a1c-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="12a1c-115">Optional.</span></span> <span data-ttu-id="12a1c-116">Si aparece el cuadro de diálogo **Publicar y anotar** , elija compartir la misma anotación (comentario) para todas las actualizaciones o anotar cada cambio de forma individual.</span><span class="sxs-lookup"><span data-stu-id="12a1c-116">If the **Publish and Annotate** dialog box is displayed, choose to share the same annotation (comment) for all updates, or to annotate each change individually.</span></span>  
  
3.  <span data-ttu-id="12a1c-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="12a1c-117">Optional.</span></span> <span data-ttu-id="12a1c-118">Active la casilla **No volver a mostrar este cuadro de diálogo** .</span><span class="sxs-lookup"><span data-stu-id="12a1c-118">Select the **Do not show this dialog box again** check box.</span></span> <span data-ttu-id="12a1c-119">Puede mostrar siempre el cuadro de diálogo en el futuro si elije **Configuración** y activa la casilla **Mostrar el cuadro de diálogo Publicar y anotar al publicar** .</span><span class="sxs-lookup"><span data-stu-id="12a1c-119">You can always show the dialog box in the future by choosing **Settings** and selecting the **Show Publish and Annotate dialog box when publishing** check box.</span></span>  
  
4.  <span data-ttu-id="12a1c-120">Haga clic en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="12a1c-120">Click **Publish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12a1c-121">Si agrega nuevos miembros (filas) en la hoja de cálculo y no puede publicarlos correctamente en el repositorio MDS, es posible que no tenga el permiso **Actualizar** para todos los atributos de la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="12a1c-121">If you are adding new members (rows) to your worksheet and you cannot successfully publish them to the MDS repository, you may not have **Update** permission to all of the attributes in the worksheet.</span></span> <span data-ttu-id="12a1c-122">En la pestaña **Revisar** , en el grupo **Cambios** , haga clic en **Desproteger hoja** e intente publicarla de nuevo.</span><span class="sxs-lookup"><span data-stu-id="12a1c-122">On the **Review** tab, in the **Changes** group, click **Unprotect Sheet** and try to publish again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="12a1c-123">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="12a1c-123">Next Steps</span></span>  
 [<span data-ttu-id="12a1c-124">Aplicar reglas de negocios &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="12a1c-124">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="12a1c-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12a1c-125">See Also</span></span>  
 <span data-ttu-id="12a1c-126">[Complemento MDS para Excel de &#40;de datos de publicación&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="12a1c-126">[Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="12a1c-127">Validar datos &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="12a1c-127">Validating Data &#40;MDS Add-in for Excel&#41;</span></span>](validating-data-mds-add-in-for-excel.md)  
  
  
