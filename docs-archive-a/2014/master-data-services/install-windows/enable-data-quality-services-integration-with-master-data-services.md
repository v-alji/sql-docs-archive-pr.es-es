---
title: Habilitar la integración de Data Quality Services con Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ab32938d-a80e-4106-80d4-94b2de3d67dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8d2fa25254cae2a129b6e08ff657d92af4ff9455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671112"
---
# <a name="enable-data-quality-services-integration-with-master-data-services"></a><span data-ttu-id="aad1c-102">Habilitar la integración de Data Quality Services con Master Data Services</span><span class="sxs-lookup"><span data-stu-id="aad1c-102">Enable Data Quality Services Integration with Master Data Services</span></span>
  <span data-ttu-id="aad1c-103">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], Data Quality Services (DQS) proporciona la funcionalidad de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="aad1c-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], matching functionality is provided by Data Quality Services (DQS).</span></span> <span data-ttu-id="aad1c-104">Esta funcionalidad debe habilitarse para poder usarse.</span><span class="sxs-lookup"><span data-stu-id="aad1c-104">This functionality must be enabled to be used.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aad1c-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aad1c-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="aad1c-106">Una aplicación web y una base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] deben existir.</span><span class="sxs-lookup"><span data-stu-id="aad1c-106">A [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web application and database must exist.</span></span>  
  
-   <span data-ttu-id="aad1c-107">La característica Data Quality Services y Data Quality Client deben estar instalados en la misma instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda la base de datos MDS.</span><span class="sxs-lookup"><span data-stu-id="aad1c-107">The Data Quality Services feature and the Data Quality Client must be installed on the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the MDS database.</span></span> <span data-ttu-id="aad1c-108">Para más información, consulte [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="aad1c-108">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
### <a name="to-enable-data-quality-services-integration"></a><span data-ttu-id="aad1c-109">Para habilitar la integración con Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="aad1c-109">To enable Data Quality Services integration</span></span>  
  
1.  <span data-ttu-id="aad1c-110">Abra [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aad1c-110">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="aad1c-111">En el panel izquierdo, haga clic en **Configuración web**.</span><span class="sxs-lookup"><span data-stu-id="aad1c-111">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="aad1c-112">En la página **Configuración web** , seleccione el sitio web y la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="aad1c-112">On the **Web Configuration** page, select the website and web application.</span></span>  
  
4.  <span data-ttu-id="aad1c-113">En la sección **Habilitar la integración DQS** , haga clic en **Habilitar la integración con Data Quality Services**.</span><span class="sxs-lookup"><span data-stu-id="aad1c-113">In the **Enable DQS Integration** section, click **Enable integration with Data Quality Services**.</span></span>  
  
5.  <span data-ttu-id="aad1c-114">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aad1c-114">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad1c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aad1c-115">See Also</span></span>  
 <span data-ttu-id="aad1c-116">[Coincidencia de calidad de datos en el Complemento MDS para Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="aad1c-116">[Data Quality Matching in the MDS Add-in for Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="aad1c-117">[Complemento Master Data Services para Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span><span class="sxs-lookup"><span data-stu-id="aad1c-117">[Master Data Services Add-in for Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span></span>  
 [<span data-ttu-id="aad1c-118">Instalar Master Data Services</span><span class="sxs-lookup"><span data-stu-id="aad1c-118">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
