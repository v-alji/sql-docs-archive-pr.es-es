---
title: Página ver, informes (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4874ba29-429b-4dd4-a8cb-d4f087237dc2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4eb5733bf6ddfc8d7ba5a1d3d6f5ebe18ce85c66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748590"
---
# <a name="view-page-reports-report-manager"></a><span data-ttu-id="89570-102">Ver la página, informes (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="89570-102">View Page, Reports (Report Manager)</span></span>
  <span data-ttu-id="89570-103">Use la página Ver para ver un informe.</span><span class="sxs-lookup"><span data-stu-id="89570-103">Use the View page for reports to view a report.</span></span> <span data-ttu-id="89570-104">La primera vez que se abre un informe en el Administrador de informes, tiene formato HTML.</span><span class="sxs-lookup"><span data-stu-id="89570-104">When you first open a report in Report Manager, it is formatted in HTML.</span></span> <span data-ttu-id="89570-105">Los informes HTML incluyen una barra de herramientas que aparece en la parte superior del informe, de modo que pueda navegar por las páginas del informe, realizar búsquedas en el informe, o bien exportar el informe a otro formato.</span><span class="sxs-lookup"><span data-stu-id="89570-105">HTML reports include a report toolbar that appears at the top of the report so that you can navigate through report pages, search within a report, or export the report to a different format.</span></span> <span data-ttu-id="89570-106">El diagrama siguiente muestra la barra de herramientas de informe.</span><span class="sxs-lookup"><span data-stu-id="89570-106">The following diagram shows the report toolbar.</span></span>  
  
 <span data-ttu-id="89570-107">![Barra de herramientas de informe](media/htmlviewer-toolbar.gif "Barra de herramientas de informe")</span><span class="sxs-lookup"><span data-stu-id="89570-107">![Report toolbar](media/htmlviewer-toolbar.gif "Report toolbar")</span></span>  
<span data-ttu-id="89570-108">Barra de herramientas de informe</span><span class="sxs-lookup"><span data-stu-id="89570-108">Report toolbar</span></span>  
  
 <span data-ttu-id="89570-109">En [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], los informes se pueden configurar para ejecutarse a petición o desde una instantánea de ejecución de informes.</span><span class="sxs-lookup"><span data-stu-id="89570-109">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], reports can be configured to run on demand or from a report execution snapshot.</span></span> <span data-ttu-id="89570-110">Si un informe se ejecuta a petición, todo el procesamiento de datos y de informes se produce cada vez que abra el informe.</span><span class="sxs-lookup"><span data-stu-id="89570-110">If a report is run on demand, all data processing and report processing occur each time you open the report.</span></span> <span data-ttu-id="89570-111">Si ve un informe que está configurado para ejecutarse como instantánea de ejecución de informes. el procesamiento de datos se produjo cuando se creó la instantánea.</span><span class="sxs-lookup"><span data-stu-id="89570-111">If you view a report that is configured to run as a report execution snapshot, data processing occurred when the snapshot was created.</span></span>  
  
## <a name="exporting-reports"></a><span data-ttu-id="89570-112">Exportar informes</span><span class="sxs-lookup"><span data-stu-id="89570-112">Exporting Reports</span></span>  
 <span data-ttu-id="89570-113">No todas las características de informe está disponibles en todos los formatos de exportación.</span><span class="sxs-lookup"><span data-stu-id="89570-113">Not all report features are available in all of the export formats.</span></span> <span data-ttu-id="89570-114">Si exporta un informe HTML a otro formato, tenga en cuenta que quizás aprecie algunas diferencias de apariencia.</span><span class="sxs-lookup"><span data-stu-id="89570-114">If you export an HTML report to another format, you can expect to see some differences in how the report appears.</span></span> <span data-ttu-id="89570-115">Asimismo, si el informe incluye características interactivas, como hipervínculos, marcadores o mapas de documento, puede que esas características no estén disponibles o no funcionen igual en el nuevo formato.</span><span class="sxs-lookup"><span data-stu-id="89570-115">Also, if the report includes interactive features (such as hyperlinks, bookmarks, or document maps) those features might not be available or work the same way in the new format.</span></span>  
  
## <a name="generating-data-feeds-from-report-data"></a><span data-ttu-id="89570-116">Generar fuentes de distribución de datos a partir de datos de informe</span><span class="sxs-lookup"><span data-stu-id="89570-116">Generating Data Feeds from Report Data</span></span>  
 <span data-ttu-id="89570-117">Puede generar las fuentes de los datos a partir de informes.</span><span class="sxs-lookup"><span data-stu-id="89570-117">You can generate data feeds from reports.</span></span> <span data-ttu-id="89570-118">La extensión de representación de Atom de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] genera dos documentos compatibles con Atom: un documento de servicio de Atom que enumera las fuentes de distribución de datos que proporciona el informe y las fuentes de distribución de datos que contienen los datos del informe.</span><span class="sxs-lookup"><span data-stu-id="89570-118">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Atom rendering extension generates two Atom-compliant documents: an Atom service document that lists the data feeds the report provides and the data feeds that contains the report data.</span></span> <span data-ttu-id="89570-119">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] genera fuentes de distribución de datos en un formato normalizado compatible con Atom 1.0 que lo pueden leer y compartir aplicaciones que consumen fuentes de distribución de datos compatibles con Atom.</span><span class="sxs-lookup"><span data-stu-id="89570-119">The data feeds are generated by [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in a standardized Atom 1.0 compliant format that it readable and exchangeable with applications that consume Atom compliant data feeds.</span></span> <span data-ttu-id="89570-120">Por ejemplo, el cliente de [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] puede consumir fuentes de distribución de datos que se generan a partir de informes.</span><span class="sxs-lookup"><span data-stu-id="89570-120">For example the [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] client can consume data feeds that are generated from reports.</span></span>  
  
## <a name="running-parameterized-reports"></a><span data-ttu-id="89570-121">Ejecutar informes parametrizados</span><span class="sxs-lookup"><span data-stu-id="89570-121">Running Parameterized Reports</span></span>  
 <span data-ttu-id="89570-122">Un informe con parámetros es un informe que contiene campos de entrada y un botón **Ver informe** .</span><span class="sxs-lookup"><span data-stu-id="89570-122">A report that contains input fields and a **View Report** button is a parameterized report.</span></span> <span data-ttu-id="89570-123">Para ver un informe con parámetros, es posible que deba suministrar los valores que se utilizan para ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="89570-123">To view a parameterized report, you may need to provide values that are used to run the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89570-124">Las instantáneas de ejecución de informes y algunos formatos de exportación no están disponibles en todas las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89570-124">Report execution snapshots and some export formats are not available in all editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="89570-125">Para obtener más información, vea [características compatibles con las ediciones de SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="89570-125">For more information, see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89570-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89570-126">See Also</span></span>  
 <span data-ttu-id="89570-127">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="89570-127">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="89570-128">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="89570-128">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  