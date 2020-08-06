---
title: Definir la inteligencia de cuentas (Asistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.mapaccounttype.f1
ms.assetid: fe4c204b-1031-4ac4-9916-8052ce2301cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17b8136e79097cd502d6b239ba6867c4e678c70f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744438"
---
# <a name="define-account-intelligence-business-intelligence-wizard"></a><span data-ttu-id="01487-102">Definir la inteligencia de cuentas (Asistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="01487-102">Define Account Intelligence (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="01487-103">Use la página **Definir la inteligencia de cuentas** para asignar tipos de cuenta definidos en la instancia de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a tipos de cuenta definidos por una tabla de origen en el origen de datos que proporciona datos para la dimensión de cuenta.</span><span class="sxs-lookup"><span data-stu-id="01487-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined by a source table in the data source that supplies the data for the account dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="01487-104">Esta página aparecerá si se ha asignado un atributo de dimensión al tipo de atributo **Tipo de cuenta** en la página **Configurar los atributos de dimensión** .</span><span class="sxs-lookup"><span data-stu-id="01487-104">This page will appear if a dimension attribute was mapped to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="01487-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="01487-105">Options</span></span>  
 <span data-ttu-id="01487-106">**Tipos de cuenta de tabla de origen**</span><span class="sxs-lookup"><span data-stu-id="01487-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="01487-107">Muestra los valores que contiene el atributo de dimensión asignado al tipo de atributo **Tipo de cuenta** de la página **Configurar los atributos de dimensión** .</span><span class="sxs-lookup"><span data-stu-id="01487-107">Displays the values that are contained in the dimension attribute assigned to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
 <span data-ttu-id="01487-108">**Tipos de cuenta integrados**</span><span class="sxs-lookup"><span data-stu-id="01487-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="01487-109">Seleccione el tipo de cuenta definido en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que está asignado a los tipos de cuenta de la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="01487-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="01487-110">En la tabla siguiente se enumeran los tipos de cuenta definidos en una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01487-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="01487-111">Value</span><span class="sxs-lookup"><span data-stu-id="01487-111">Value</span></span>|<span data-ttu-id="01487-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="01487-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="01487-113">**Recurso**</span><span class="sxs-lookup"><span data-stu-id="01487-113">**Asset**</span></span>|<span data-ttu-id="01487-114">Valor de cosas en propiedad en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="01487-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="01487-115">**Saldo**</span><span class="sxs-lookup"><span data-stu-id="01487-115">**Balance**</span></span>|<span data-ttu-id="01487-116">Cuenta de algo en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="01487-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="01487-117">**Expense**</span><span class="sxs-lookup"><span data-stu-id="01487-117">**Expense**</span></span>|<span data-ttu-id="01487-118">Valor de cosas consumidas.</span><span class="sxs-lookup"><span data-stu-id="01487-118">Value of things spent.</span></span>|  
|<span data-ttu-id="01487-119">**Flujo**</span><span class="sxs-lookup"><span data-stu-id="01487-119">**Flow**</span></span>|<span data-ttu-id="01487-120">Cuenta incremental de cosas.</span><span class="sxs-lookup"><span data-stu-id="01487-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="01487-121">**Income**</span><span class="sxs-lookup"><span data-stu-id="01487-121">**Income**</span></span>|<span data-ttu-id="01487-122">Valor de las cosas recibidas.</span><span class="sxs-lookup"><span data-stu-id="01487-122">Value of things received.</span></span>|  
|<span data-ttu-id="01487-123">**Liability**</span><span class="sxs-lookup"><span data-stu-id="01487-123">**Liability**</span></span>|<span data-ttu-id="01487-124">Valor de cosas debidas en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="01487-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="01487-125">**Estadística**</span><span class="sxs-lookup"><span data-stu-id="01487-125">**Statistical**</span></span>|<span data-ttu-id="01487-126">Proporción calculada de algo o cuenta de algo que no se agrega.</span><span class="sxs-lookup"><span data-stu-id="01487-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01487-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01487-127">See Also</span></span>  
 <span data-ttu-id="01487-128">[Asistente de Business Intelligence (ayuda F1)](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="01487-128">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="01487-129">[Diseñador de cubos &#40;Analysis Services de datos multidimensionales&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="01487-129">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="01487-130">Diseñador de dimensiones &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="01487-130">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
