---
title: Requisitos previos del Asesor de actualizaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- requirements [Upgrade Advisor]
- software [Upgrade Advisor]
- system requirements [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, prerequisites
- prerequisites [Upgrade Advisor]
- Upgrade Advisor [SQL Server], prerequisites
ms.assetid: d21a39e5-5f81-4096-a7dd-f244e4779992
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 41c97cf585d1768c7aebeec2613ee8744cb220da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672408"
---
# <a name="upgrade-advisor-prerequisites"></a><span data-ttu-id="1878f-102">Requisitos previos del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="1878f-102">Upgrade Advisor Prerequisites</span></span>
  <span data-ttu-id="1878f-103">En este tema se describen los requisitos de software para el Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="1878f-103">This topic describes the software requirements for Upgrade Advisor.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1878f-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1878f-104">Prerequisites</span></span>  
 <span data-ttu-id="1878f-105">Los requisitos previos para instalar y ejecutar el Asesor de actualizaciones son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1878f-105">The prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[wiprlhext](../../includes/wiprlhext-md.md)] <span data-ttu-id="1878f-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] a partir de SP2, Windows 7 o [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span><span class="sxs-lookup"><span data-stu-id="1878f-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] beginning with SP2, Windows 7, or [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span></span>  
  
-   <span data-ttu-id="1878f-107">Windows Installer 4.5.</span><span class="sxs-lookup"><span data-stu-id="1878f-107">Windows Installer 4.5.</span></span> <span data-ttu-id="1878f-108">Puede instalar Windows Installer desde el [sitio web de Windows Installer](https://www.microsoft.com/download/details.aspx?id=8483).</span><span class="sxs-lookup"><span data-stu-id="1878f-108">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="1878f-109">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], a partir de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1878f-109">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], beginning with .NET Framework 4.</span></span> <span data-ttu-id="1878f-110">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]Está disponible en los [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] medios del producto y en el [SDK, el redistribuible y Service Pack sitio web de descarga](https://go.microsoft.com/fwlink/?LinkId=48882).</span><span class="sxs-lookup"><span data-stu-id="1878f-110">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [SDK, redistributable, and service pack download Web site](https://go.microsoft.com/fwlink/?LinkId=48882).</span></span>  
  
    -   <span data-ttu-id="1878f-111">Para instalar .NET Framework 4 desde el disco de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], busque la raíz de la unidad de disco.</span><span class="sxs-lookup"><span data-stu-id="1878f-111">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="1878f-112">A continuación, haga doble clic en la carpeta \redist, haga doble clic en la carpeta DotNetFrameworks y ejecute dotNetFx40_Full_x86_x64.exe (para sistemas operativos de 32 bits y 64 bits).</span><span class="sxs-lookup"><span data-stu-id="1878f-112">Then double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for both 32-bit and 64-bit operating systems).</span></span>  
  
-   <span data-ttu-id="1878f-113">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom es un requisito previo para instalar el [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Asesor de actualizaciones y el programa de instalación del Asesor de actualizaciones no lo instala.</span><span class="sxs-lookup"><span data-stu-id="1878f-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="1878f-114">El programa de instalación requiere que descargue e instale [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom desde el [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="1878f-114">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1878f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1878f-115">See Also</span></span>  
 [<span data-ttu-id="1878f-116">Procedimientos: Instalar el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="1878f-116">How to: Install Upgrade Advisor</span></span>](../../../2014/sql-server/install/how-to-install-upgrade-advisor.md)  
  
  
