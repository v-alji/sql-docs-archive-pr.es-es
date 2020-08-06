---
title: Definir la inteligencia de cuentas (Asistente para dimensiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.accountintelligencetypemapping.f1
ms.assetid: cbcff072-3a7e-4e98-858f-1b4265461561
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90871e2299d1531db1b678b1f4b16ddd7f1db767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675047"
---
# <a name="define-account-intelligence-dimension-wizard"></a><span data-ttu-id="b319f-102">Definir la inteligencia de cuentas (Asistente para dimensiones)</span><span class="sxs-lookup"><span data-stu-id="b319f-102">Define Account Intelligence (Dimension Wizard)</span></span>
  <span data-ttu-id="b319f-103">Use la página **Definir la inteligencia de cuentas** para asignar tipos de cuenta definidos en la instancia de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a los tipos de cuenta definidos en el atributo de la dimensión asociado al tipo de atributo **Tipo de cuenta** de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="b319f-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined in the dimension attribute associated with the **Account Type** attribute type in the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b319f-104"> Esta página solo se muestra si ha seleccionado **Dimensión estándar** en la página **Seleccionar el tipo de dimensión** y si ha asignado un atributo de dimensión al tipo de atributo **Tipo de cuenta** en la página **Especificar tipo de dimensión** .</span><span class="sxs-lookup"><span data-stu-id="b319f-104">This page is displayed only if you selected **Standard dimension** on the **Select the Dimension Type** page and if you mapped a dimension attribute to the **Account Type** attribute type on the **Specify Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b319f-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="b319f-105">Options</span></span>  
 <span data-ttu-id="b319f-106">**Tipos de cuenta de tabla de origen**</span><span class="sxs-lookup"><span data-stu-id="b319f-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="b319f-107">Muestra los valores incluidos en el atributo de dimensión asignado al tipo de atributo **Tipo de cuenta** en la página **Especificar clave y tipo de dimensión** .</span><span class="sxs-lookup"><span data-stu-id="b319f-107">Displays the values contained in the dimension attribute assigned to the **Account Type** attribute type in the **Specify Dimension Key and Type** page.</span></span>  
  
 <span data-ttu-id="b319f-108">**Tipos de cuenta integrados**</span><span class="sxs-lookup"><span data-stu-id="b319f-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="b319f-109">Seleccione el tipo de cuenta definido en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que está asignado a los tipos de cuenta de la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="b319f-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="b319f-110">En la tabla siguiente se enumeran los tipos de cuenta definidos en una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b319f-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="b319f-111">Value</span><span class="sxs-lookup"><span data-stu-id="b319f-111">Value</span></span>|<span data-ttu-id="b319f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b319f-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b319f-113">**Recurso**</span><span class="sxs-lookup"><span data-stu-id="b319f-113">**Asset**</span></span>|<span data-ttu-id="b319f-114">Valor de cosas en propiedad en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="b319f-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="b319f-115">**Saldo**</span><span class="sxs-lookup"><span data-stu-id="b319f-115">**Balance**</span></span>|<span data-ttu-id="b319f-116">Cuenta de algo en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="b319f-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="b319f-117">**Expense**</span><span class="sxs-lookup"><span data-stu-id="b319f-117">**Expense**</span></span>|<span data-ttu-id="b319f-118">Valor de cosas consumidas.</span><span class="sxs-lookup"><span data-stu-id="b319f-118">Value of things spent.</span></span>|  
|<span data-ttu-id="b319f-119">**Flujo**</span><span class="sxs-lookup"><span data-stu-id="b319f-119">**Flow**</span></span>|<span data-ttu-id="b319f-120">Cuenta incremental de cosas.</span><span class="sxs-lookup"><span data-stu-id="b319f-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="b319f-121">**Income**</span><span class="sxs-lookup"><span data-stu-id="b319f-121">**Income**</span></span>|<span data-ttu-id="b319f-122">Valor de las cosas recibidas.</span><span class="sxs-lookup"><span data-stu-id="b319f-122">Value of things received.</span></span>|  
|<span data-ttu-id="b319f-123">**Liability**</span><span class="sxs-lookup"><span data-stu-id="b319f-123">**Liability**</span></span>|<span data-ttu-id="b319f-124">Valor de cosas debidas en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="b319f-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="b319f-125">**Estadística**</span><span class="sxs-lookup"><span data-stu-id="b319f-125">**Statistical**</span></span>|<span data-ttu-id="b319f-126">Proporción calculada de algo o cuenta de algo que no se agrega.</span><span class="sxs-lookup"><span data-stu-id="b319f-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b319f-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b319f-127">See Also</span></span>  
 <span data-ttu-id="b319f-128">[Asistente para dimensiones (ayuda F1)](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="b319f-128">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="b319f-129">[Dimensiones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b319f-129">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="b319f-130">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="b319f-130">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
