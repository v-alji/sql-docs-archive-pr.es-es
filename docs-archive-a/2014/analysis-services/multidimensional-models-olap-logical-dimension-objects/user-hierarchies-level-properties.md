---
title: Propiedades de nivel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- user hierarchies [Analysis Services]
- hierarchies [Analysis Services], user
ms.assetid: dabb7335-887b-442a-b67c-4901ba1242b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 553503b9d35142bcc998b4ec12ad2e29d4c66318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663771"
---
# <a name="level-properties"></a><span data-ttu-id="a1b82-102">Propiedades del nivel</span><span class="sxs-lookup"><span data-stu-id="a1b82-102">Level Properties</span></span> 
  <span data-ttu-id="a1b82-103">En la siguiente tabla se enumeran y describen las propiedades de un nivel en una jerarquía definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a1b82-103">The following table lists and describes the properties of a level in a user-defined hierarchy.</span></span>  
  
|<span data-ttu-id="a1b82-104">Propiedad</span><span class="sxs-lookup"><span data-stu-id="a1b82-104">Property</span></span>|<span data-ttu-id="a1b82-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1b82-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a1b82-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1b82-106">Description</span></span>|<span data-ttu-id="a1b82-107">Contiene la descripción del nivel.</span><span class="sxs-lookup"><span data-stu-id="a1b82-107">Contains the description of the level.</span></span>|  
|<span data-ttu-id="a1b82-108">HideMemberIf</span><span class="sxs-lookup"><span data-stu-id="a1b82-108">HideMemberIf</span></span>|<span data-ttu-id="a1b82-109">Indica si un miembro en un nivel debe ocultarse de las aplicaciones cliente y cuándo.</span><span class="sxs-lookup"><span data-stu-id="a1b82-109">Indicates whether and when a member in a level should be hidden from client applications.</span></span> <span data-ttu-id="a1b82-110">Esta propiedad puede tener los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1b82-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="a1b82-111">Nunca</span><span class="sxs-lookup"><span data-stu-id="a1b82-111">Never</span></span><br /> <span data-ttu-id="a1b82-112">Los miembros nunca se ocultan.</span><span class="sxs-lookup"><span data-stu-id="a1b82-112">Members are never hidden.</span></span> <span data-ttu-id="a1b82-113">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a1b82-113">This is the default value.</span></span><br /><br /> <span data-ttu-id="a1b82-114">OnlyChildWithNoName</span><span class="sxs-lookup"><span data-stu-id="a1b82-114">OnlyChildWithNoName</span></span><br /> <span data-ttu-id="a1b82-115">Se oculta un miembro cuando el miembro es el único elemento secundario de un elemento primario y el nombre del miembro está vacío.</span><span class="sxs-lookup"><span data-stu-id="a1b82-115">A member is hidden when the member is the only child of its parent and the member's name is empty.</span></span><br /><br /> <span data-ttu-id="a1b82-116">OnlyChildWithParentName</span><span class="sxs-lookup"><span data-stu-id="a1b82-116">OnlyChildWithParentName</span></span><br /> <span data-ttu-id="a1b82-117">Se oculta un miembro cuando el miembro es el único elemento secundario de un elemento primario y el nombre del miembro es idéntico al del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="a1b82-117">A member is hidden when the member is the only child of its parent and the member's name is identical to that of its parent.</span></span><br /><br /> <span data-ttu-id="a1b82-118">NoName</span><span class="sxs-lookup"><span data-stu-id="a1b82-118">NoName</span></span><br /> <span data-ttu-id="a1b82-119">Un miembro se oculta cuando el nombre del miembro está vacío.</span><span class="sxs-lookup"><span data-stu-id="a1b82-119">A member is hidden when the member's name is empty.</span></span><br /><br /> <span data-ttu-id="a1b82-120">ParentName</span><span class="sxs-lookup"><span data-stu-id="a1b82-120">ParentName</span></span><br /> <span data-ttu-id="a1b82-121">Un miembro se oculta cuando el nombre del miembro es idéntico al del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="a1b82-121">A member is hidden when the member's name is identical to that of its parent.</span></span>|  
|<span data-ttu-id="a1b82-122">ID</span><span class="sxs-lookup"><span data-stu-id="a1b82-122">ID</span></span>|<span data-ttu-id="a1b82-123">Contiene el identificador único (Id.) del nivel.</span><span class="sxs-lookup"><span data-stu-id="a1b82-123">Contains the unique identifier (ID) of the level.</span></span>|  
|<span data-ttu-id="a1b82-124">Nombre</span><span class="sxs-lookup"><span data-stu-id="a1b82-124">Name</span></span>|<span data-ttu-id="a1b82-125">Contiene el nombre descriptivo del nivel.</span><span class="sxs-lookup"><span data-stu-id="a1b82-125">Contains the friendly name of the level.</span></span> <span data-ttu-id="a1b82-126">De forma predeterminada, el nombre de un nivel es el mismo que el nombre del atributo de origen.</span><span class="sxs-lookup"><span data-stu-id="a1b82-126">By default, the name of a level is the same as the name of the source attribute.</span></span>|  
|<span data-ttu-id="a1b82-127">SourceAttribute</span><span class="sxs-lookup"><span data-stu-id="a1b82-127">SourceAttribute</span></span>|<span data-ttu-id="a1b82-128">Contiene el nombre del atributo de origen en el que se basa el nivel.</span><span class="sxs-lookup"><span data-stu-id="a1b82-128">Contains the name of the source attribute on which the level is based.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1b82-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1b82-129">See Also</span></span>  
 [<span data-ttu-id="a1b82-130">Propiedades de jerarquía de usuario</span><span class="sxs-lookup"><span data-stu-id="a1b82-130">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
