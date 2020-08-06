---
title: Tipos de suscriptor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.subscribertypes.f1
ms.assetid: a70656cb-21c9-4489-be77-ccd396747e3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d356377dec1f5307fa136c94ea682c0824479a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677030"
---
# <a name="subscriber-types"></a><span data-ttu-id="ab7a4-102">Tipos de suscriptor</span><span class="sxs-lookup"><span data-stu-id="ab7a4-102">Subscriber Types</span></span>
  <span data-ttu-id="ab7a4-103">La replicación de mezcla le permite especificar los tipos de suscriptor compatibles con una publicación.</span><span class="sxs-lookup"><span data-stu-id="ab7a4-103">Merge replication allows you to specify the types of Subscribers that a publication must support.</span></span> <span data-ttu-id="ab7a4-104">Si selecciona Tipos de suscriptor, podrá establecer el *nivel de compatibilidad de la publicación*, que determina las características que puede usar una publicación.</span><span class="sxs-lookup"><span data-stu-id="ab7a4-104">Selecting Subscriber types sets the *publication compatibility level*, which determines which features can be used by a publication.</span></span>  
  
 <span data-ttu-id="ab7a4-105">Una vez creada una instantánea de publicación, se puede aumentar (restringir) el nivel de compatibilidad de la publicación en la página **General** del cuadro de diálogo **Propiedades de la publicación** ; no se puede reducir el nivel de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="ab7a4-105">After a publication snapshot is created, the publication compatibility level can be increased (made more restrictive) on the **General** page of the **Publication Properties** dialog box; the compatibility level cannot be decreased.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ab7a4-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="ab7a4-106">Options</span></span>  
 <span data-ttu-id="ab7a4-107">Seleccione los tipos de suscriptor compatibles con la publicación.</span><span class="sxs-lookup"><span data-stu-id="ab7a4-107">Select each Subscriber type that this publication must support.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 <span data-ttu-id="ab7a4-108">La publicación podrá usar todas las características.</span><span class="sxs-lookup"><span data-stu-id="ab7a4-108">The publication can use all features.</span></span>  
  
 [!INCLUDE[ssEW](../../includes/ssew-md.md)]  
 <span data-ttu-id="ab7a4-109">La publicación necesita que los archivos de instantáneas tengan un formato de caracteres (el agente de instantáneas lo controlará automáticamente).</span><span class="sxs-lookup"><span data-stu-id="ab7a4-109">The publication requires snapshot files to be in character format (this is handled automatically by the Snapshot Agent).</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="ab7a4-110">también presenta varias restricciones no relacionadas con el nivel de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="ab7a4-110">also has a number of restrictions not related to compatibility level.</span></span>  
  
 <span data-ttu-id="ab7a4-111">Si selecciona esta opción, se habilitará la opción de sincronización web para la publicación.</span><span class="sxs-lookup"><span data-stu-id="ab7a4-111">If this option is selected, the Web synchronization option is enabled for the publication.</span></span> <span data-ttu-id="ab7a4-112">Para obtener más información acerca de la sincronización web, vea [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ab7a4-112">For more information about Web synchronization, see [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab7a4-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab7a4-113">See Also</span></span>  
 <span data-ttu-id="ab7a4-114">[Publicar datos y objetos de base de datos](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="ab7a4-114">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="ab7a4-115">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="ab7a4-115">[Create a Publication](publish/create-a-publication.md) </span></span>  
 [<span data-ttu-id="ab7a4-116">Ver y modificar las propiedades del distribuidor y del publicador</span><span class="sxs-lookup"><span data-stu-id="ab7a4-116">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
