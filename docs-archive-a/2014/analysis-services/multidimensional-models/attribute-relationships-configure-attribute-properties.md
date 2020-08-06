---
title: Configurar propiedades de relación de atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- flexible relationships (Analysis Services)
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
- properties [Analysis Services], attribute relationships
- rigid relationships (Analysis Services)
ms.assetid: fce511af-66d7-42fc-bb3a-6c516f16b10e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 241fa2af16377fd2cacf657ec6f99c5ca4bd0c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663178"
---
# <a name="configure-attribute-relationship-properties"></a><span data-ttu-id="f6ef1-102">Configurar propiedades de relación de los atributos</span><span class="sxs-lookup"><span data-stu-id="f6ef1-102">Configure Attribute Relationship Properties</span></span>
  <span data-ttu-id="f6ef1-103">En la siguiente tabla se muestran y describen las propiedades de una relación de atributo.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-103">The following table lists and describes the properties of an attribute relationship.</span></span>  
  
|<span data-ttu-id="f6ef1-104">Propiedad</span><span class="sxs-lookup"><span data-stu-id="f6ef1-104">Property</span></span>|<span data-ttu-id="f6ef1-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6ef1-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f6ef1-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="f6ef1-106">Attribute</span></span>|<span data-ttu-id="f6ef1-107">Contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-107">Contains the name of the attribute.</span></span>|  
|<span data-ttu-id="f6ef1-108">Cardinalidad</span><span class="sxs-lookup"><span data-stu-id="f6ef1-108">Cardinality</span></span>|<span data-ttu-id="f6ef1-109">Indica la cardinalidad de la relación.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-109">Indicates the cardinality of the relationship.</span></span> <span data-ttu-id="f6ef1-110">Los valores son Many, para una relación de varios a uno, y One, para una relación de uno a uno.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-110">Values are Many, for a many to one relationship, or One, for a one to one relationship.</span></span> <span data-ttu-id="f6ef1-111">El valor predeterminado es Many.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-111">Default value is Many.</span></span> <span data-ttu-id="f6ef1-112">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , la propiedad de cardinalidad no tiene ningún efecto: su uso se reserva para una implementación futura.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-112">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the cardinality property has no effect - its use is reserved for a future implementation.</span></span>|  
|<span data-ttu-id="f6ef1-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="f6ef1-113">Name</span></span>|<span data-ttu-id="f6ef1-114">Contiene el nombre descriptivo del atributo.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-114">Contains the friendly name of the attribute.</span></span>|  
|<span data-ttu-id="f6ef1-115">RelationshipType</span><span class="sxs-lookup"><span data-stu-id="f6ef1-115">RelationshipType</span></span>|<span data-ttu-id="f6ef1-116">Indica si las relaciones de los miembros cambian a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-116">Indicates whether member relationships change over time.</span></span> <span data-ttu-id="f6ef1-117">Los valores son Rigid, que significa que las relaciones entre los miembros no cambian a lo largo del tiempo, o Flexible, que significa que las relaciones entre los miembros sí cambian.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-117">Values are Rigid, which means that relationships between members do not change over time, or Flexible, which means that relationships between members change over time.</span></span> <span data-ttu-id="f6ef1-118">El valor predeterminado es Flexible.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-118">Default is Flexible.</span></span> <span data-ttu-id="f6ef1-119">Si define una relación como flexible, las agregaciones se quitan y se vuelven a calcular como parte de una actualización incremental (no se quitarán si solo se agregan miembros nuevos).</span><span class="sxs-lookup"><span data-stu-id="f6ef1-119">If you define a relationship as flexible, aggregations are dropped and recomputed as part of an incremental update (they will not be dropped if only new members are added).</span></span> <span data-ttu-id="f6ef1-120">Si define una relación como rígida, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retiene las agregaciones cuando la dimensión se actualiza de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-120">If you define a relationship as rigid, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retains aggregations when the dimension is incrementally updated.</span></span> <span data-ttu-id="f6ef1-121">Si una relación definida como rígida cambia realmente, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generará un error durante el procesamiento incremental.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-121">If a relationship that is defined as rigid actually changes, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generates an error during incremental processing.</span></span> <span data-ttu-id="f6ef1-122">El rendimiento de la consulta y del procesamiento aumenta si se especifican las relaciones y las propiedades de relación apropiadas.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-122">Specifying the appropriate relationships and relationship properties increases query and processing performance.</span></span>|  
|<span data-ttu-id="f6ef1-123">Visible</span><span class="sxs-lookup"><span data-stu-id="f6ef1-123">Visible</span></span>|<span data-ttu-id="f6ef1-124">Determina la visibilidad de la relación de los atributos.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-124">Determines the visibility of the attribute relationship.</span></span> <span data-ttu-id="f6ef1-125">Los valores son True o False.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-125">Values are True or False.</span></span> <span data-ttu-id="f6ef1-126">El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="f6ef1-126">Default is True.</span></span>|  
  
  
