---
title: Validar miembros específicos con las reglas de negocios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- applying business rules [Master Data Services]
- business rules [Master Data Services], applying to select members
ms.assetid: 2288ef43-5392-47ea-b651-ec25e5692a14
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 18af83146679eb77638dfbc98b31f198dc8e07b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672152"
---
# <a name="validate-specific-members-against-business-rules-master-data-services"></a><span data-ttu-id="a8623-102">Validar miembros específicos con las reglas de negocios (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a8623-102">Validate Specific Members against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="a8623-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], aplique las reglas de negocios selectivamente si desea actualizar o validar subconjuntos de miembros con las reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="a8623-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], apply business rules selectively when you want to update or validate subsets of members against business rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8623-104">Si quiere aplicar reglas de negocios a todos los miembros en una versión de un modelo, consulte [Validar una versión con las reglas de negocios &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a8623-104">If you want to apply business rules to all members in a version of a model, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8623-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a8623-105">Prerequisites</span></span>  
 <span data-ttu-id="a8623-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="a8623-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a8623-107">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="a8623-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="a8623-108">Como mínimo, debe tener el permiso **Actualizar** para el objeto de modelo al que vaya a aplicar reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="a8623-108">You must have a minimum of **Update** permission to the model object you are applying business rules to.</span></span>  
  
### <a name="to-apply-business-rules-selectively"></a><span data-ttu-id="a8623-109">Aplicar reglas de negocios selectivamente</span><span class="sxs-lookup"><span data-stu-id="a8623-109">To apply business rules selectively</span></span>  
  
1.  <span data-ttu-id="a8623-110">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="a8623-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="a8623-111">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="a8623-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="a8623-112">Haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="a8623-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="a8623-113">En la barra de menús, seleccione **Entidades** y haga clic en el nombre de la entidad que contenga los miembros a los que desea aplicar reglas.</span><span class="sxs-lookup"><span data-stu-id="a8623-113">From the menu bar, point to **Entities** and click the name of the entity that contains members you want to apply rules to.</span></span>  
  
5.  <span data-ttu-id="a8623-114">Haga clic en **Aplicar reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="a8623-114">Click **Apply business rules**.</span></span> <span data-ttu-id="a8623-115">Las reglas de negocios solo se aplican a los miembros que aparecen en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a8623-115">Business rules are applied only to the members displayed in the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8623-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8623-116">See Also</span></span>  
 <span data-ttu-id="a8623-117">[Validar una versión con las reglas de negocios &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a8623-117">[Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="a8623-118">Reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a8623-118">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
