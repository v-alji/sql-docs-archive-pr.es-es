---
title: Palabras reservadas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- reserved words [Master Data Services]
- Master Data Services, reserved words
ms.assetid: 88afd0d0-4362-4394-8357-4e65388fc0fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c54bb371cd8f797cfb36f015387e0e21339c0426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673747"
---
# <a name="reserved-words-master-data-services"></a><span data-ttu-id="67860-102">Palabras reservadas (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="67860-102">Reserved Words (Master Data Services)</span></span>
  <span data-ttu-id="67860-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], al crear objetos del modelo o miembros, algunas palabras no se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="67860-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when you create model objects or members, some words cannot be used.</span></span> <span data-ttu-id="67860-104">Su uso puede producir errores.</span><span class="sxs-lookup"><span data-stu-id="67860-104">Using these words may cause errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67860-105">También debe limitar el uso de caracteres especiales (símbolos, guiones, etc.).</span><span class="sxs-lookup"><span data-stu-id="67860-105">You should also limit your use of special characters (symbols, hyphenation, etc.).</span></span>  
  
-   [<span data-ttu-id="67860-106">Modelos</span><span class="sxs-lookup"><span data-stu-id="67860-106">Models</span></span>](#models)  
  
-   [<span data-ttu-id="67860-107">Entidades</span><span class="sxs-lookup"><span data-stu-id="67860-107">Entities</span></span>](#entities)  
  
-   [<span data-ttu-id="67860-108">Jerarquías explícitas</span><span class="sxs-lookup"><span data-stu-id="67860-108">Explicit Hierarchies</span></span>](#exhierarchies)  
  
-   [<span data-ttu-id="67860-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="67860-109">Attributes</span></span>](#attributes)  
  
-   [<span data-ttu-id="67860-110">Miembros</span><span class="sxs-lookup"><span data-stu-id="67860-110">Members</span></span>](#members)  
  
##  <a name="models"></a><a name="models"></a><span data-ttu-id="67860-111">Modelos</span><span class="sxs-lookup"><span data-stu-id="67860-111">Models</span></span>  
 <span data-ttu-id="67860-112">Si crea un modelo con el nombre establecido en **nombre**, no seleccione **crear entidad con el mismo nombre que el modelo** porque **el nombre no se puede** usar para el nombre de una entidad.</span><span class="sxs-lookup"><span data-stu-id="67860-112">If you create a model with the name set to **Name**, do not select **Create entity with same name as model** because **Name** cannot be used for the name of an entity.</span></span>  
  
##  <a name="entities"></a><a name="entities"></a><span data-ttu-id="67860-113">Jurídica</span><span class="sxs-lookup"><span data-stu-id="67860-113">Entities</span></span>  
 <span data-ttu-id="67860-114">Para los nombres de entidad, no puede usar **Name** o **Code**.</span><span class="sxs-lookup"><span data-stu-id="67860-114">For entity names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="explicit-hierarchies"></a><a name="exhierarchies"></a><span data-ttu-id="67860-115">Jerarquías explícitas</span><span class="sxs-lookup"><span data-stu-id="67860-115">Explicit Hierarchies</span></span>  
 <span data-ttu-id="67860-116">Para los nombres de jerarquía explícita, no puede utilizar **Name** o **Code**.</span><span class="sxs-lookup"><span data-stu-id="67860-116">For explicit hierarchy names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="attributes"></a><a name="attributes"></a><span data-ttu-id="67860-117">Sus</span><span class="sxs-lookup"><span data-stu-id="67860-117">Attributes</span></span>  
  
-   <span data-ttu-id="67860-118">**ID**</span><span class="sxs-lookup"><span data-stu-id="67860-118">**ID**</span></span>  
  
-   <span data-ttu-id="67860-119">**Código**</span><span class="sxs-lookup"><span data-stu-id="67860-119">**Code**</span></span>  
  
-   <span data-ttu-id="67860-120">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="67860-120">**Name**</span></span>  
  
-   <span data-ttu-id="67860-121">**EnterDTM**</span><span class="sxs-lookup"><span data-stu-id="67860-121">**EnterDTM**</span></span>  
  
-   <span data-ttu-id="67860-122">**EnterUserID**</span><span class="sxs-lookup"><span data-stu-id="67860-122">**EnterUserID**</span></span>  
  
-   <span data-ttu-id="67860-123">**EnterUserName**</span><span class="sxs-lookup"><span data-stu-id="67860-123">**EnterUserName**</span></span>  
  
-   <span data-ttu-id="67860-124">**LastChgDTM**</span><span class="sxs-lookup"><span data-stu-id="67860-124">**LastChgDTM**</span></span>  
  
-   <span data-ttu-id="67860-125">**LastChgUserID**</span><span class="sxs-lookup"><span data-stu-id="67860-125">**LastChgUserID**</span></span>  
  
-   <span data-ttu-id="67860-126">**Status_ID**</span><span class="sxs-lookup"><span data-stu-id="67860-126">**Status_ID**</span></span>  
  
-   <span data-ttu-id="67860-127">**ValidationStatus_ID**</span><span class="sxs-lookup"><span data-stu-id="67860-127">**ValidationStatus_ID**</span></span>  
  
-   <span data-ttu-id="67860-128">**Version_ID**</span><span class="sxs-lookup"><span data-stu-id="67860-128">**Version_ID**</span></span>  
  
##  <a name="members"></a><a name="members"></a><span data-ttu-id="67860-129">Registrados</span><span class="sxs-lookup"><span data-stu-id="67860-129">Members</span></span>  
 <span data-ttu-id="67860-130">Para los miembros, no puede usar **MDMMemberStatus** o **root** para el valor del atributo **code** .</span><span class="sxs-lookup"><span data-stu-id="67860-130">For members, you cannot use **MDMMemberStatus** or **ROOT** for the **Code** attribute value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67860-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67860-131">See Also</span></span>  
 [<span data-ttu-id="67860-132">Introducción a Master Data Services</span><span class="sxs-lookup"><span data-stu-id="67860-132">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
  
