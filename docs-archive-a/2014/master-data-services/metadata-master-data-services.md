---
title: Metadatos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined metadata [Master Data Services], about user-defined metadata
- metadata [Master Data Services], about metadata
- metadata [Master Data Services]
- user-defined metadata [Master Data Services]
ms.assetid: ac1aabe3-d8d4-4d7a-8954-50ee3c185d81
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 39ab95b7925306febb551962495da7ec9751589b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745363"
---
# <a name="metadata-master-data-services"></a><span data-ttu-id="a596a-102">Metadatos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a596a-102">Metadata (Master Data Services)</span></span>
  <span data-ttu-id="a596a-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], los metadatos definidos por el usuario son la información que se usa para describir los objetos del modelo.</span><span class="sxs-lookup"><span data-stu-id="a596a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], user-defined metadata is information that you use to describe model objects.</span></span> <span data-ttu-id="a596a-104">Por ejemplo, puede que desee realizar el seguimiento de los propietarios de un modelo o entidad determinados, o realizar el seguimiento de los sistemas de origen que proporcionan los datos a una entidad.</span><span class="sxs-lookup"><span data-stu-id="a596a-104">For example, you may want to track the owners of a particular model or entity, or track the source systems that supply data to an entity.</span></span>  
  
 <span data-ttu-id="a596a-105">Los metadatos definidos por el usuario se administran mediante un modelo denominado **metadatos**.</span><span class="sxs-lookup"><span data-stu-id="a596a-105">User-defined metadata is managed by a model called **Metadata**.</span></span> <span data-ttu-id="a596a-106">Este modelo se incluye automáticamente cuando [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] se instala y es similar al resto de modelos de MDS, excepto en que no se pueden crear versiones de los mismos.</span><span class="sxs-lookup"><span data-stu-id="a596a-106">This model is automatically included when [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is installed, and it is similar to all other MDS models, except that you cannot create versions of it.</span></span>  
  
 <span data-ttu-id="a596a-107">Después de rellenar el modelo de metadatos con los metadatos definidos por el usuario, puede incluirlo en las vistas de suscripciones, para que lo puedan usar los sistemas suscriptores.</span><span class="sxs-lookup"><span data-stu-id="a596a-107">After you populate the Metadata model with user-defined metadata, you can include it in subscription views, so it can be consumed by subscribing systems.</span></span>  
  
## <a name="metadata-entities"></a><span data-ttu-id="a596a-108">Entidades de metadatos</span><span class="sxs-lookup"><span data-stu-id="a596a-108">Metadata Entities</span></span>  
 <span data-ttu-id="a596a-109">El modelo de metadatos incluye cinco entidades, cada una de las cuales representa un tipo de objeto del modelo de datos maestros que admite los metadatos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a596a-109">The Metadata model includes five entities, each of which represents a type of master data model object that supports user-defined metadata.</span></span> <span data-ttu-id="a596a-110">Por ejemplo, la entidad **definición de metadatos del modelo** contiene miembros que representan modelos y la entidad definición de **metadatos de atributo** tiene miembros que representan todos los atributos de todos los modelos.</span><span class="sxs-lookup"><span data-stu-id="a596a-110">For example, the **Model Metadata Definition** entity contains members that represent models, and the **Attribute Metadata Definition** entity has members that represent all attributes in all models.</span></span>  
  
 <span data-ttu-id="a596a-111">Para definir los metadatos de un objeto del modelo, rellene uno de estos atributos del miembro.</span><span class="sxs-lookup"><span data-stu-id="a596a-111">To define metadata for a model object, you populate one of these member's attributes.</span></span> <span data-ttu-id="a596a-112">Por ejemplo, en la entidad **definición de metadatos de entidad** , puede rellenar el atributo Descripción del miembro del precio con el texto: **el precio del producto cuando se vende a un cliente**.</span><span class="sxs-lookup"><span data-stu-id="a596a-112">For example, in the **Entity Metadata Definition** entity, you can populate the Price member's Description attribute with the text: **The product price when sold to a customer**.</span></span>  
  
 <span data-ttu-id="a596a-113">Los miembros del modelo de metadatos se actualizan automáticamente siempre que se agregan o se eliminan los objetos del modelo compatibles con los metadatos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a596a-113">The members in the Metadata model are automatically updated whenever model objects that support user-defined metadata are added or deleted.</span></span>  
  
 <span data-ttu-id="a596a-114">No se pueden crear versiones del modelo de metadatos, no se pueden agregar ni quitar marcas de versión, ni se puede guardar como un paquete de implementación del modelo.</span><span class="sxs-lookup"><span data-stu-id="a596a-114">The Metadata model cannot be versioned, have version flags added or changed, or be saved as a model deployment package.</span></span> <span data-ttu-id="a596a-115">Sin embargo, todas sus demás funciones son las mismas que las de los otros modelos de datos maestros.</span><span class="sxs-lookup"><span data-stu-id="a596a-115">However, it has all the same other functionality available to other master data models.</span></span> <span data-ttu-id="a596a-116">Por ejemplo, podría implementar un conjunto de reglas de negocios en el modelo Metadatos para aplicar directivas de datos.</span><span class="sxs-lookup"><span data-stu-id="a596a-116">For example, you might implement a set of business rules on the Metadata model to enforce data policies.</span></span>  
  
## <a name="customizing-your-metadata-model"></a><span data-ttu-id="a596a-117">Personalizar un modelo de metadatos</span><span class="sxs-lookup"><span data-stu-id="a596a-117">Customizing Your Metadata Model</span></span>  
 <span data-ttu-id="a596a-118">Cada entidad de definición de metadatos incluye los atributos Nombre, Código y Descripción.</span><span class="sxs-lookup"><span data-stu-id="a596a-118">Each metadata definition entity includes Name, Code, and Description attributes.</span></span> <span data-ttu-id="a596a-119">Puede ser conveniente crear atributos adicionales para describir de forma precisa los objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="a596a-119">You may want to create additional attributes to further describe your model objects.</span></span>  
  
 <span data-ttu-id="a596a-120">Por ejemplo, podría crear:</span><span class="sxs-lookup"><span data-stu-id="a596a-120">For example, you might create:</span></span>  
  
-   <span data-ttu-id="a596a-121">Un atributo basado en dominio denominado Propietario, que se utiliza para realizar el seguimiento del propietario de cada objeto de modelo.</span><span class="sxs-lookup"><span data-stu-id="a596a-121">A domain-based attribute named Owner, which you use to track the owner of each model object.</span></span>  
  
-   <span data-ttu-id="a596a-122">Un atributo de forma libre denominado Fecha de la última revisión, que se utiliza para realizar el seguimiento de la fecha en que el propietario de un objeto lo revisó por última vez.</span><span class="sxs-lookup"><span data-stu-id="a596a-122">A free-form attribute named Last Review Date, which you use to track the date that an object was last reviewed by the owner.</span></span>  
  
-   <span data-ttu-id="a596a-123">Un atributo basado en dominio denominado sources, que se utiliza para realizar un seguimiento de los sistemas de origen que interactúan con la instancia de y administrarlos [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a596a-123">A domain-based attribute named Sources, which you use to track and manage the source systems that interact with the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] instance.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a596a-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a596a-124">Related Tasks</span></span>  
  
|<span data-ttu-id="a596a-125">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="a596a-125">Task Description</span></span>|<span data-ttu-id="a596a-126">Tema</span><span class="sxs-lookup"><span data-stu-id="a596a-126">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="a596a-127">Agregar metadatos a un objeto del modelo.</span><span class="sxs-lookup"><span data-stu-id="a596a-127">Add metadata to a model object.</span></span>|[<span data-ttu-id="a596a-128">Agregar metadatos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a596a-128">Add Metadata &#40;Master Data Services&#41;</span></span>](add-metadata-master-data-services.md)
|&nbsp;|&nbsp;|
  
## <a name="related-content"></a><span data-ttu-id="a596a-129">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="a596a-129">Related Content</span></span>  
  
-   [<span data-ttu-id="a596a-130">Exportar datos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a596a-130">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
