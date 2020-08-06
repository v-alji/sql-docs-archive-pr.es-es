---
title: Propiedades del administrador de bloqueos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- lock manager properties [Analysis Services]
- LockWaitGranularityMS property
- DefaultLockTimeoutMS property
- DeadlockDetectionGranularityMS property
ms.assetid: 15fe9ead-825b-4ac3-9191-7a07caa2861b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d10927f1c549f00625b8affb801ec7b0831827c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752389"
---
# <a name="lock-manager-properties"></a><span data-ttu-id="d9e01-102">Propiedades del administrador de bloqueos</span><span class="sxs-lookup"><span data-stu-id="d9e01-102">Lock Manager Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="d9e01-103">admite las propiedades de servidor del administrador de bloqueos que aparecen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="d9e01-103">supports the lock manager server properties listed in the following table.</span></span> <span data-ttu-id="d9e01-104">Para obtener más información sobre las propiedades de servidor adicionales y cómo establecerlas, vea [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d9e01-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="d9e01-105">**Se aplica a:** modo de servidor multidimensional y tabular</span><span class="sxs-lookup"><span data-stu-id="d9e01-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d9e01-106">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d9e01-106">Properties</span></span>  
 `DefaultLockTimeoutMS`  
 <span data-ttu-id="d9e01-107">Propiedad de entero de 32 bits con signo que define el tiempo de espera de bloqueo predeterminado en milisegundos para las solicitudes de bloqueo internas.</span><span class="sxs-lookup"><span data-stu-id="d9e01-107">A signed 32-bit integer property that defines default lock timeout in milliseconds for internal lock requests.</span></span>  
  
 <span data-ttu-id="d9e01-108">El valor predeterminado de esta propiedad es -1, que indica que no hay tiempo de espera para las solicitudes de bloqueo internas.</span><span class="sxs-lookup"><span data-stu-id="d9e01-108">The default value for this property is -1, which indicates there is no timeout for internal lock requests.</span></span>  
  
 `LockWaitGranularityMS`  
 <span data-ttu-id="d9e01-109">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d9e01-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DeadlockDetectionGranularityMS`  
 <span data-ttu-id="d9e01-110">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d9e01-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e01-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9e01-111">See Also</span></span>  
 <span data-ttu-id="d9e01-112">[Configurar las propiedades del servidor en Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="d9e01-112">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="d9e01-113">Determinar el modo de servidor de una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d9e01-113">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
