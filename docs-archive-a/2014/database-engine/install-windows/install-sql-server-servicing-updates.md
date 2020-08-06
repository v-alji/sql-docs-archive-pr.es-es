---
title: Instalar actualizaciones de servicio de SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 7d6c962b-c8d0-49f7-a2ac-00ad8dca930a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace0fd187386d9a9d96e82f61d1efaa254f08c6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744835"
---
# <a name="install-sql-server-2014-servicing-updates"></a><span data-ttu-id="12cca-102">Instalar actualizaciones de servicio de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="12cca-102">Install SQL Server 2014 Servicing Updates</span></span>
  <span data-ttu-id="12cca-103">Este tema proporciona información acerca de cómo instalar actualizaciones para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12cca-103">This topic provides information about installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="12cca-104">Esta sección proporciona información acerca de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="12cca-104">This section provides information about the following:</span></span>  
  
-   <span data-ttu-id="12cca-105">Instalar actualizaciones para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] durante una nueva instalación</span><span class="sxs-lookup"><span data-stu-id="12cca-105">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] during a new installation</span></span>  
  
-   <span data-ttu-id="12cca-106">Instalar actualizaciones para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] una vez instalado.</span><span class="sxs-lookup"><span data-stu-id="12cca-106">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed.</span></span>  
  
 <span data-ttu-id="12cca-107">Se recomienda que los clientes evalúen e instalen las últimas actualizaciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puntualmente para asegurarse de que los sistemas están al día con las actualizaciones de seguridad más recientes.</span><span class="sxs-lookup"><span data-stu-id="12cca-107">We recommend that customers evaluate and install latest [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates in a timely manner to make sure that systems are up-to-date with the most recent security updates.</span></span>  
  
## <a name="installing-updates-for-sscurrent-during-a-new-installation"></a><span data-ttu-id="12cca-108">Instalar actualizaciones para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] durante una nueva instalación</span><span class="sxs-lookup"><span data-stu-id="12cca-108">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] During a New Installation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="12cca-109">integra las últimas actualizaciones del producto con la instalación del producto principal, de modo que el producto principal y las actualizaciones aplicables se instalen al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="12cca-109">setup integrates the latest product updates with the main product installation so that the main product and its applicable updates are installed at the same time.</span></span> <span data-ttu-id="12cca-110">La actualización del producto puede buscar actualizaciones aplicables en:</span><span class="sxs-lookup"><span data-stu-id="12cca-110">Product Update can search for the applicable updates from:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="12cca-111">Update</span><span class="sxs-lookup"><span data-stu-id="12cca-111">Update</span></span>  
  
-   <span data-ttu-id="12cca-112">Windows Server Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="12cca-112">Windows Server Update Services (WSUS)</span></span>  
  
-   <span data-ttu-id="12cca-113">Una carpeta local</span><span class="sxs-lookup"><span data-stu-id="12cca-113">A local folder</span></span>  
  
-   <span data-ttu-id="12cca-114">Un recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="12cca-114">A network share</span></span>  
  
 <span data-ttu-id="12cca-115">Una vez que el programa de instalación encuentra las versiones más recientes de las actualizaciones aplicables, las descarga y las integra con el proceso de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] actual.</span><span class="sxs-lookup"><span data-stu-id="12cca-115">After Setup finds the latest versions of the applicable updates, it downloads and integrates them with the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup process.</span></span> <span data-ttu-id="12cca-116">La actualización del producto puede incluir una actualización acumulativa, un Service Pack o un Service Pack más la actualización acumulativa.</span><span class="sxs-lookup"><span data-stu-id="12cca-116">Product Update can include a cumulative update, service pack, or service pack plus cumulative update.</span></span> <span data-ttu-id="12cca-117">La funcionalidad de Actualización de producto es una extensión de la [funcionalidad de instalación integrada](https://go.microsoft.com/fwlink/?LinkId=219945) que estaba disponible en [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span><span class="sxs-lookup"><span data-stu-id="12cca-117">Product Update functionality is an extension of the [Slipstream Functionality](https://go.microsoft.com/fwlink/?LinkId=219945) that was available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span></span>  
  
## <a name="installing-updates-for-sscurrent-after-it-has-already-been-installed"></a><span data-ttu-id="12cca-118">Instalar actualizaciones para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] una vez instalado</span><span class="sxs-lookup"><span data-stu-id="12cca-118">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed</span></span>  
 <span data-ttu-id="12cca-119">En una instancia instalada de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , se recomienda aplicar todas las actualizaciones disponibles: las versiones de distribución general (GDR-seguridad/actualizaciones críticas), los Service Pack (SP), así como la última actualización acumulativa (Cu) disponible.</span><span class="sxs-lookup"><span data-stu-id="12cca-119">On an installed instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you apply all available updates: General Distribution Releases (GDR - security/critical updates), Service Packs (SP), as well as the latest available Cumulative Update (CU).</span></span>  
  
 <span data-ttu-id="12cca-120">En función del tipo de servicio de mantenimiento, las actualizaciones de SQL Server están disponibles a través de Microsoft Update (MU), el centro de descarga de Microsoft o el servidor de revisiones de servicios de soporte al cliente.</span><span class="sxs-lookup"><span data-stu-id="12cca-120">Depending on the type of servicing release, SQL Server updates are available via Microsoft Update (MU), the Microsoft Download Center, and/or the Customer Support Services hotfix Server.</span></span> <span data-ttu-id="12cca-121">Las actualizaciones críticas y de seguridad de SQL Server se proporcionan automáticamente en Microsoft Update (para poder ver estas actualizaciones es necesario participar en MU a través de Windows Update en el panel de control).</span><span class="sxs-lookup"><span data-stu-id="12cca-121">Security and Critical updates for SQL Server are automatically provided by Microsoft Update (to be able to see these updates you need to opt-in to MU through Windows Update in Control panel).</span></span> <span data-ttu-id="12cca-122">Los Service Pack están disponibles en MU como descargas opcionales/importantes, así como en el centro de descarga.</span><span class="sxs-lookup"><span data-stu-id="12cca-122">Service Packs are available on MU as Optional/Important downloads as well as the Download Center.</span></span> <span data-ttu-id="12cca-123">Hay actualizaciones acumulativas disponibles en el servidor de descarga de revisiones de Microsoft que se proporciona en los artículos de Knowledge base de CU.</span><span class="sxs-lookup"><span data-stu-id="12cca-123">Cumulative updates are available on the Microsoft hotfix download server provided in CU Knowledge Base articles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cca-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12cca-124">See Also</span></span>  
 <span data-ttu-id="12cca-125">[Instale SQL Server 2014 desde el Asistente para la instalación &#40;el programa de instalación&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span><span class="sxs-lookup"><span data-stu-id="12cca-125">[Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span></span>  
 <span data-ttu-id="12cca-126">Al [instalar actualizaciones desde el símbolo del sistema](installing-updates-from-the-command-prompt.md) , se [agregan características a una instancia de SQL Server 2014 &#40;la instalación&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span><span class="sxs-lookup"><span data-stu-id="12cca-126">[Installing updates from the command prompt](installing-updates-from-the-command-prompt.md) [Add Features to an Instance of SQL Server 2014 &#40;Setup&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span></span>  
 [<span data-ttu-id="12cca-127">Anular una instalación de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="12cca-127">Drop a SQL Server 2014 Installation</span></span>](repair-a-failed-sql-server-installation.md)  
  
  
