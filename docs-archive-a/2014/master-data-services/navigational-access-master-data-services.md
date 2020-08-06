---
title: Acceso por navegación (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- navigational access [Master Data Services]
- security [Master Data Services], navigational access
ms.assetid: 3403b7b0-44e2-48c3-a1b7-9c4612b874b8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7af3c16d98320b6fea3d4611e9e4c6d37c6015bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662123"
---
# <a name="navigational-access-master-data-services"></a><span data-ttu-id="65639-102">Acceso por navegación (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="65639-102">Navigational Access (Master Data Services)</span></span>
  <span data-ttu-id="65639-103">El acceso por navegación se aplica a la seguridad de los objetos de modelos, que se asigna en la pestaña **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="65639-103">Navigational access applies to model object security, which is assigned on the **Models** tab.</span></span>  
  
 <span data-ttu-id="65639-104">El acceso por navegación es el que se obtiene para niveles superiores a los que su seguridad le haya asignado.</span><span class="sxs-lookup"><span data-stu-id="65639-104">Navigational access is the access you get to levels higher than where you've assigned security.</span></span>  
  
 <span data-ttu-id="65639-105">En este ejemplo, los permisos se asignan a una entidad y el acceso por navegación se concede en el nivel de modelo.</span><span class="sxs-lookup"><span data-stu-id="65639-105">In this example, permissions are assigned to an entity, and so navigational access is granted at the model level.</span></span>  
  
 <span data-ttu-id="65639-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="65639-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>  
  
 <span data-ttu-id="65639-107">**Entidades**</span><span class="sxs-lookup"><span data-stu-id="65639-107">**Entities**</span></span>  
  
 <span data-ttu-id="65639-108">Cuando se asigna permiso a una entidad, a sus miembros hoja o a sus miembros consolidados, el acceso por navegación significa que se pueden leer o actualizar el nombre y el código de todos los miembros.</span><span class="sxs-lookup"><span data-stu-id="65639-108">When you assign permission to an entity, its leaf members, or its consolidated members, navigational access means you can read or update the name and code for all members.</span></span> <span data-ttu-id="65639-109">También se puede leer el nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="65639-109">You can also read the model name.</span></span>  
  
 <span data-ttu-id="65639-110">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="65639-110">**Attributes**</span></span>  
  
 <span data-ttu-id="65639-111">Cuando se asigna permiso a un atributo, el acceso por navegación significa que se pueden leer o actualizar el nombre y el código de todos los miembros de la entidad.</span><span class="sxs-lookup"><span data-stu-id="65639-111">When you assign permission to an attribute, navigational access means you can read or update the name and code for all members in the entity.</span></span> <span data-ttu-id="65639-112">También se puede leer el nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="65639-112">You can also read the model name.</span></span>  
  
 <span data-ttu-id="65639-113">**Colecciones**</span><span class="sxs-lookup"><span data-stu-id="65639-113">**Collections**</span></span>  
  
 <span data-ttu-id="65639-114">Cuando se asignan permisos a las colecciones, se pueden leer o actualizar el nombre, el código, la descripción y el identificador del propietario.</span><span class="sxs-lookup"><span data-stu-id="65639-114">When you assign permissions to collections, you can read or update the name, code, description and owner ID.</span></span> <span data-ttu-id="65639-115">También se puede leer el nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="65639-115">You can also read the model name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65639-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65639-116">See Also</span></span>  
 [<span data-ttu-id="65639-117">Cómo se determinan los permisos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="65639-117">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](how-permissions-are-determined-master-data-services.md)  
  
  
