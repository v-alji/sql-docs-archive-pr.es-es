---
title: Vincular un informe a un modelo como informe click-through | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- customizing clickthrough reports
- clickthrough reports, customizing
- clickthrough reports, templates
ms.assetid: 3af42de3-67ef-41c2-bc8a-7045baec6f63
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cb84f8036dbe5a1694628144f0b948452261ca75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669496"
---
# <a name="link-a-report-to-a-model-as-a-clickthrough-report"></a><span data-ttu-id="70986-102">Vincular un informe a un modelo como informe click-through</span><span class="sxs-lookup"><span data-stu-id="70986-102">Link a Report to a Model as a Clickthrough Report</span></span>
  <span data-ttu-id="70986-103">En lugar de utilizar las plantillas del informe click-through predeterminadas, puede crear un informe del Generador de informes y, a continuación, hacer clic en una entidad específica en el modelo de informe.</span><span class="sxs-lookup"><span data-stu-id="70986-103">Instead of using the default clickthrough report templates, you can create a Report Builder report and then link it to a specific entity in the report model.</span></span> <span data-ttu-id="70986-104">Cuando la persona que ve el informe hace clic en los datos interactivos del informe principal, éste se muestra como un informe click-through.</span><span class="sxs-lookup"><span data-stu-id="70986-104">When the person viewing the report clicks the interactive data in the main report, this report is displayed as a clickthrough report.</span></span> <span data-ttu-id="70986-105">Para vincular un informe a una entidad, utilice el Administrador de informes de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70986-105">To link a report to an entity, use [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="70986-106">La entidad principal o base que se utiliza en el informe debe ser la misma a la que está vinculado el informe.</span><span class="sxs-lookup"><span data-stu-id="70986-106">The primary, or base, entity that is used in the report must to be the same entity to which the report is linked.</span></span>  
  
### <a name="to-start-report-manager-from-a-browser"></a><span data-ttu-id="70986-107">Para iniciar el Administrador de informes desde un explorador</span><span class="sxs-lookup"><span data-stu-id="70986-107">To start Report Manager from a browser</span></span>  
  
1.  <span data-ttu-id="70986-108">Abra [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="70986-108">Open [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 or later.</span></span>  
  
2.  <span data-ttu-id="70986-109">En la barra de direcciones del explorador web, escriba la dirección URL del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="70986-109">In the address bar of the Web browser, type the Report Manager URL.</span></span> <span data-ttu-id="70986-110">De forma predeterminada, la dirección URL es http:// \<*ComputerName*> /Reports.</span><span class="sxs-lookup"><span data-stu-id="70986-110">By default, the URL is http://\<*ComputerName*>/reports.</span></span>  
  
### <a name="to-create-a-customized-clickthrough-report"></a><span data-ttu-id="70986-111">Para crear un informe click-through personalizado</span><span class="sxs-lookup"><span data-stu-id="70986-111">To create a customized clickthrough report</span></span>  
  
1.  <span data-ttu-id="70986-112">Navegue al modelo de informe al que desea agregar el informe click-through personalizado.</span><span class="sxs-lookup"><span data-stu-id="70986-112">Navigate to the report model to which you want to add the customized clickthrough report.</span></span>  
  
2.  <span data-ttu-id="70986-113">Haga doble clic en el modelo de informe.</span><span class="sxs-lookup"><span data-stu-id="70986-113">Double-click the report model.</span></span>  
  
3.  <span data-ttu-id="70986-114">Haga clic en **Click-through**.</span><span class="sxs-lookup"><span data-stu-id="70986-114">Click **Clickthrough**.</span></span>  
  
4.  <span data-ttu-id="70986-115">Seleccione la entidad a la que desea adjuntar el informe click-through personalizado.</span><span class="sxs-lookup"><span data-stu-id="70986-115">Select the entity to which you want to attach the customized clickthrough report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70986-116">Esta entidad debe ser igual que la entidad base del informe click-through personalizado.</span><span class="sxs-lookup"><span data-stu-id="70986-116">This entity must be the same as the base entity of the customized clickthrough report.</span></span>  
  
5.  <span data-ttu-id="70986-117">Para mostrar el informe personalizado cuando se hace clic en una sola instancia de la entidad seleccionada, haga clic en el botón **Examinar** del informe de una sola instancia.</span><span class="sxs-lookup"><span data-stu-id="70986-117">To display the customized report when a single instance of the selected entity is clicked, click the Single instance report **Browse** button.</span></span>  
  
     <span data-ttu-id="70986-118">O bien</span><span class="sxs-lookup"><span data-stu-id="70986-118">-or-</span></span>  
  
     <span data-ttu-id="70986-119">Para mostrar el informe personalizado cuando se hace clic en varias instancias de la entidad seleccionada, haga clic en el botón **Examinar** del informe de varias instancias.</span><span class="sxs-lookup"><span data-stu-id="70986-119">To display the customized report when a multiple instance of the selected entity is clicked, click the Multiple instance report **Browse** button.</span></span>  
  
6.  <span data-ttu-id="70986-120">Seleccione el informe y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="70986-120">Select the report and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="70986-121">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="70986-121">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70986-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70986-122">See Also</span></span>  
 [<span data-ttu-id="70986-123">Informes click-through &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="70986-123">Clickthrough Reports &#40;SSRS&#41;</span></span>](reports/clickthrough-reports-ssrs.md)  
  
  
