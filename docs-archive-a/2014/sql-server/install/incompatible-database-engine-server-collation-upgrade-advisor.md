---
title: Intercalación de servidor Motor de base de datos incompatible (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f499d6-2c90-49eb-a5b3-0bb5b7faaa3b
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b6ce0555bdf5a878e56d87a8bd55b5ce6c4b2649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676824"
---
# <a name="incompatible-database-engine-server-collation-upgrade-advisor"></a><span data-ttu-id="ad14c-102">Intercalación del servidor de motor de base de datos incompatible (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="ad14c-102">Incompatible Database Engine Server Collation (Upgrade Advisor)</span></span>
  <span data-ttu-id="ad14c-103">El asesor de actualizaciones ha detectado [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que usa una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que está configurada para utilizar una intercalación de servidor incompatible.</span><span class="sxs-lookup"><span data-stu-id="ad14c-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
||  
|-|  
|<span data-ttu-id="ad14c-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ad14c-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="ad14c-105">Componente</span><span class="sxs-lookup"><span data-stu-id="ad14c-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="ad14c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad14c-106">Description</span></span>  
 <span data-ttu-id="ad14c-107">El asesor de actualizaciones ha detectado [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que usa una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que está configurada para utilizar una intercalación de servidor incompatible.</span><span class="sxs-lookup"><span data-stu-id="ad14c-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="ad14c-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]El modo de SharePoint de emplea la arquitectura de servicios compartidos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ad14c-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode utilizes the SharePoint shared services architecture.</span></span> <span data-ttu-id="ad14c-109">SharePoint no admite [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configurado para las intercalaciones de servidor o que distinguen entre mayúsculas y minúsculas o las intercalaciones de servidor binarias.</span><span class="sxs-lookup"><span data-stu-id="ad14c-109">SharePoint does not support [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configured for case sensitive or server collations or binary server collations.</span></span> <span data-ttu-id="ad14c-110">Entre las intercalaciones incompatibles se incluyen las que son binarias o distinguen entre mayúsculas y minúsculas de forma predeterminada, y las intercalaciones base que son compatibles de forma predeterminada, pero se han configurado con alguno de los designadores de intercalación siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad14c-110">Incompatible collations include collations that are by default case sensitive or binary and a base collation that by default is compatible but has been configured with any of the following collation designators:</span></span>  
  
-   <span data-ttu-id="ad14c-111">**Binario**</span><span class="sxs-lookup"><span data-stu-id="ad14c-111">**Binary**</span></span>  
  
-   <span data-ttu-id="ad14c-112">**Distinguir mayúsculas de minúsculas**</span><span class="sxs-lookup"><span data-stu-id="ad14c-112">**Case-sensitive**</span></span>  
  
-   <span data-ttu-id="ad14c-113">**Punto de código binario**</span><span class="sxs-lookup"><span data-stu-id="ad14c-113">**Binary-codepoint**</span></span>  
  
 <span data-ttu-id="ad14c-114">Debido a que la intercalación de servidor actual de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] es incompatible, la actualización se bloquea.</span><span class="sxs-lookup"><span data-stu-id="ad14c-114">Because the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation is incompatible, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="ad14c-115">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="ad14c-115">Corrective Action</span></span>  
 <span data-ttu-id="ad14c-116">La propiedad de intercalación del servidor de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="ad14c-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation property cannot be changed.</span></span> <span data-ttu-id="ad14c-117">No podrá completar una actualización de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad14c-117">You will not be able to complete an upgrade of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="ad14c-118">Deberá migrar la instalación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a un servidor nuevo que use una intercalación del servidor compatible.</span><span class="sxs-lookup"><span data-stu-id="ad14c-118">You will need to migrate your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation to a new server which is using a compatible server collation.</span></span> <span data-ttu-id="ad14c-119">Para obtener más información, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad14c-119">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="ad14c-120">Actualizar y migrar Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ad14c-120">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=233227)  
  
-   [<span data-ttu-id="ad14c-121">Seleccionar una intercalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad14c-121">Selecting a SQL Server Collation</span></span>](https://go.microsoft.com/fwlink/?LinkId=233226)  
  
  
