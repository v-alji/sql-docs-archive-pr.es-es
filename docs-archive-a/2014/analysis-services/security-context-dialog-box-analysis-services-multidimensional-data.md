---
title: Cuadro de diálogo contexto de seguridad (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.securitycontext.f1
ms.assetid: 238a4a4b-84bd-4b3d-9f02-f3adf57fa3af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58d5f71172ac16087ecc342342e70ade234226a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669900"
---
# <a name="security-context-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="88088-102">Cuadro de diálogo Contexto de seguridad (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="88088-102">Security Context Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="88088-103">Use el cuadro de diálogo **Contexto de seguridad** en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para cambiar el usuario y el rol usados para examinar datos o metadatos de un objeto de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88088-103">Use the **Security Context** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to change the user and role used to examine data or metadata for a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="88088-104">Para mostrar el cuadro de diálogo **Contexto de seguridad** , haga clic en **Contexto de seguridad** en el panel **Barra de herramientas** de la pestaña **Cálculos** o **Explorador** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="88088-104">You can display the **Security Context** dialog box by clicking **Security Context** in the **Toolbar** pane on either the **Calculations** tab or the **Browser** tab in Cube Designer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="88088-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="88088-105">Options</span></span>  
 <span data-ttu-id="88088-106">**Usuario actual**</span><span class="sxs-lookup"><span data-stu-id="88088-106">**Current user**</span></span>  
 <span data-ttu-id="88088-107">Seleccione esta opción para utilizar el dominio y el nombre del usuario actual al visualizar los datos y metadatos del objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88088-107">Select to use the domain and user name of the current user while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="88088-108">**Otro usuario**</span><span class="sxs-lookup"><span data-stu-id="88088-108">**Other user**</span></span>  
 <span data-ttu-id="88088-109">Escriba el dominio y el nombre de usuario de otro usuario o grupo que se usará al visualizar los datos y metadatos del objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88088-109">Type the domain and user name of another user or group to use while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="88088-110">El dominio y el nombre de usuario o grupo utiliza el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="88088-110">The domain and name of the user or group uses the following format:</span></span>  
  
 <span data-ttu-id="88088-111">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="88088-111">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="88088-112">**Roles**</span><span class="sxs-lookup"><span data-stu-id="88088-112">**Roles**</span></span>  
 <span data-ttu-id="88088-113">Seleccione esta opción para utilizar uno o varios roles especificados al ver los datos y metadatos del objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88088-113">Select to use one or more specified roles when viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="88088-114">Puede seleccionar los roles que se van a utilizar si se definen varios roles en la base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88088-114">You can select the roles to use if multiple roles are defined in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88088-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88088-115">See Also</span></span>  
 <span data-ttu-id="88088-116">[KPI &#40;diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="88088-116">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="88088-117">[Explorador de cubos &#40;&#41; &#40;Analysis Services de datos multidimensionales&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="88088-117">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="88088-118">Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="88088-118">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
