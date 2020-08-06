---
title: Configurar atributos de dimensión (Asistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.selectattributes.f1
ms.assetid: 3d046e63-bcb1-4ab1-9c37-652463fa68c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1d2e9bc83b7a6d83b6d2808b472d67169266ff07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670039"
---
# <a name="configure-dimension-attributes-business-intelligence-wizard"></a><span data-ttu-id="3c359-102">Configurar los atributos de dimensión (Asistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="3c359-102">Configure Dimension Attributes (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="3c359-103">Use la página **Configurar los atributos de dimensión** para asignar atributos de dimensión a los tipos de atributo que [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usa para identificar atributos para dimensiones de cuentas.</span><span class="sxs-lookup"><span data-stu-id="3c359-103">Use the **Configure Dimension Attributes** page to map the dimension attributes to the attribute types that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to identify attributes for account dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3c359-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="3c359-104">Options</span></span>  
 <span data-ttu-id="3c359-105">**Tipo de dimensión**</span><span class="sxs-lookup"><span data-stu-id="3c359-105">**Dimension type**</span></span>  
 <span data-ttu-id="3c359-106">Muestra el tipo de dimensión seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3c359-106">Displays the selected dimension type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c359-107">Esta opción no está disponible porque la `Type` propiedad de la dimensión no se puede cambiar a un valor distinto de *cuenta* para las dimensiones de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="3c359-107">This option is not available because the `Type` property of the dimension cannot be changed to a value other than *Account* for account dimensions.</span></span>  
  
 <span data-ttu-id="3c359-108">**Atributos de dimensión**</span><span class="sxs-lookup"><span data-stu-id="3c359-108">**Dimension attributes**</span></span>  
 <span data-ttu-id="3c359-109">Muestra los tipos de atributo válidos que se pueden asignar a los atributos de dimensión existentes en la dimensión.</span><span class="sxs-lookup"><span data-stu-id="3c359-109">Displays the valid attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="3c359-110">**Inclui**</span><span class="sxs-lookup"><span data-stu-id="3c359-110">**Include**</span></span>  
 <span data-ttu-id="3c359-111">Active una casilla para incluir el tipo de atributo correspondiente en la dimensión.</span><span class="sxs-lookup"><span data-stu-id="3c359-111">Select a check box to include the corresponding attribute type in the dimension.</span></span>  
  
 <span data-ttu-id="3c359-112">**Tipo de atributo**</span><span class="sxs-lookup"><span data-stu-id="3c359-112">**Attribute Type**</span></span>  
 <span data-ttu-id="3c359-113">Enumera los tipos de atributo que se pueden asignar a los atributos de dimensión existentes en la dimensión.</span><span class="sxs-lookup"><span data-stu-id="3c359-113">Lists the attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="3c359-114">**Atributo de dimensión**</span><span class="sxs-lookup"><span data-stu-id="3c359-114">**Dimension Attribute**</span></span>  
 <span data-ttu-id="3c359-115">Active el atributo de dimensión que debe asignarse al tipo de atributo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3c359-115">Select the dimension attribute that should be mapped to the corresponding attribute type.</span></span>  
  
 <span data-ttu-id="3c359-116">**Establecer medidas en suma parcial en función del tipo de cuenta**</span><span class="sxs-lookup"><span data-stu-id="3c359-116">**Set measures to be semiadditive based on account type**</span></span>  
 <span data-ttu-id="3c359-117">Seleccione esta opción para cambiar cada medida asociada con esta dimensión para que se agregue con el tipo de cuenta.</span><span class="sxs-lookup"><span data-stu-id="3c359-117">Select to change every measure associated with this dimension to be aggregated by account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c359-118">Esta opción no aparece si se ha iniciado el Asistente de Business Intelligence desde el Diseñador de dimensiones o haciendo clic con el botón secundario en una dimensión del Explorador de soluciones de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c359-118">This option does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c359-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c359-119">See Also</span></span>  
 <span data-ttu-id="3c359-120">[Asistente de Business Intelligence (ayuda F1)](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="3c359-120">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="3c359-121">[Diseñador de cubos &#40;Analysis Services de datos multidimensionales&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3c359-121">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3c359-122">Diseñador de dimensiones &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="3c359-122">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
