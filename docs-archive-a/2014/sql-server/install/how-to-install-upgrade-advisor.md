---
title: Cómo instalar el asesor de actualizaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, installing
- Upgrade Advisor [SQL Server], installing
ms.assetid: 481b0704-ce79-4543-b141-67306128aa2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3ed5b66522126bfabc94bfa8036ec6c31ac04500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676840"
---
# <a name="how-to-install-upgrade-advisor"></a><span data-ttu-id="0e090-102">Procedimientos: Instalar el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="0e090-102">How to: Install Upgrade Advisor</span></span>
  <span data-ttu-id="0e090-103">El Asesor de actualizaciones admite el análisis remoto de todos los componentes admitidos excepto [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e090-103">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="0e090-104">Si no está analizando instancias de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], puede instalar el Asesor de actualizaciones en cualquier equipo que pueda conectarse a sus instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e090-104">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0e090-105">El equipo también debe cumplir los requisitos previos del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0e090-105">The computer must also meet Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="0e090-106">Si está examinando instancias de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], debe instalar el Asesor de actualizaciones en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="0e090-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="0e090-107">Para obtener más información, vea [instalar el asesor de actualizaciones](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="0e090-107">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
### <a name="to-install-upgrade-advisor"></a><span data-ttu-id="0e090-108">Para instalar el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="0e090-108">To install Upgrade Advisor</span></span>  
  
1.  <span data-ttu-id="0e090-109">Inicie la instalación mediante uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="0e090-109">Start the installation using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="0e090-110">Si va a instalar desde el [!INCLUDE[msCoName](../../includes/msconame-md.md)] sitio web de, haga clic en el vínculo **Descargar** y, a continuación, haga clic en el botón **Ejecutar** para iniciar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0e090-110">If you are installing from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Web site, click the **Download** link and then click the **Run** button to start the installation.</span></span>  
  
    -   <span data-ttu-id="0e090-111">Si va a instalar desde el medio del producto, abra la carpeta **Redist** , abra la carpeta **Asesor de actualizaciones** y, a continuación, haga doble clic en **SQLUA.msi**.</span><span class="sxs-lookup"><span data-stu-id="0e090-111">If you are installing from the product media, open the **redist** folder, open the **Upgrade Advisor** folder, and then double-click **SQLUA.msi**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e090-112">El Asesor de actualizaciones necesita [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0e090-112">Upgrade Advisor requires the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span></span> <span data-ttu-id="0e090-113">Si no está instalado o si tiene una versión preliminar, aparecerá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="0e090-113">If it is not installed, or if you have a pre-release version, an error message will appear.</span></span> <span data-ttu-id="0e090-114">Desinstale cualquier versión anterior de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] y, a continuación, instale la versión más reciente de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0e090-114">Uninstall any earlier version of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] and then install the latest version of .NET Framework 4.</span></span>  
    >   
    >  <span data-ttu-id="0e090-115">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom es un requisito previo para instalar el [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Asesor de actualizaciones y el programa de instalación del Asesor de actualizaciones no lo instala.</span><span class="sxs-lookup"><span data-stu-id="0e090-115">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="0e090-116">El programa de instalación requiere que descargue e instale [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom desde el [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="0e090-116">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
2.  <span data-ttu-id="0e090-117">En la página **Bienvenido a la [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instalación del Asesor de actualizaciones** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0e090-117">On the **Welcome to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor Setup** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="0e090-118">En la página **contrato de licencia** , lea el contrato de licencia.</span><span class="sxs-lookup"><span data-stu-id="0e090-118">On the **License Agreement** page, read the license agreement.</span></span> <span data-ttu-id="0e090-119">Si está de acuerdo, seleccione Acepto **el contrato de licencia** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0e090-119">If you agree, select **I accept the license agreement** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="0e090-120">En la página **información de registro** , escriba su nombre y su compañía.</span><span class="sxs-lookup"><span data-stu-id="0e090-120">On the **Registration Information** page, enter your name and company.</span></span>  
  
5.  <span data-ttu-id="0e090-121">En la página **selección de características** , revise el valor de la ruta de **instalación** .</span><span class="sxs-lookup"><span data-stu-id="0e090-121">On the **Feature Selection** page, review the **Installation path** value.</span></span> <span data-ttu-id="0e090-122">Si es necesario, use el botón **examinar** para cambiar la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e090-122">If necessary, use the **Browse** button to change the location.</span></span> <span data-ttu-id="0e090-123">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="0e090-123">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="0e090-124">En la página **listo para instalar el programa** , haga clic en **instalar** para instalar el asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0e090-124">On the **Ready to Install the Program** page, click **Install** to install Upgrade Advisor.</span></span>  
  
7.  <span data-ttu-id="0e090-125">Haga clic en **Finalizar** para salir del asistente.</span><span class="sxs-lookup"><span data-stu-id="0e090-125">Click **Finish** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e090-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e090-126">See Also</span></span>  
 [<span data-ttu-id="0e090-127">Requisitos previos del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="0e090-127">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
