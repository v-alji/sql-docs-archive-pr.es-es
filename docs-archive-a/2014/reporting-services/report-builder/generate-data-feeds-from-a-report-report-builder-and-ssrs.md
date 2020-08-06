---
title: Generar fuentes de distribución de datos a partir de un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e68baae2-9f2a-4f13-9179-9ac7f29111c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 340191396aaaa92fe14fe8c3c6b42539a713eb45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662626"
---
# <a name="generate-data-feeds-from-a-report-report-builder-and-ssrs"></a><span data-ttu-id="857d1-102">Generar fuentes de distribución de datos a partir de un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="857d1-102">Generate Data Feeds from a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="857d1-103">Puede generar fuentes de datos compatibles con Atom a partir de informes y, a continuación, utilizar las fuentes de datos en aplicaciones, como el [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cliente, que pueden consumir fuentes de datos.</span><span class="sxs-lookup"><span data-stu-id="857d1-103">You can generate Atom-compliant data feeds from reports, and then use the data feeds in applications, such as the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] client, that can consume data feeds.</span></span>  
  
 <span data-ttu-id="857d1-104">La extensión de representación de Atom de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] genera un documento de servicio de Atom que enumera las fuentes de distribución de datos disponibles en un informe.</span><span class="sxs-lookup"><span data-stu-id="857d1-104">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Atom rendering extension generates an Atom service document that lists the data feeds available from a report.</span></span> <span data-ttu-id="857d1-105">El documento enumera al menos una fuente de distribución de datos para cada región de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="857d1-105">The document lists at least one data feed for each data region in the report.</span></span> <span data-ttu-id="857d1-106">Según el tipo de región de datos y los datos que esta muestra, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] podría generar varias fuentes de distribución de datos a partir de una región de datos.</span><span class="sxs-lookup"><span data-stu-id="857d1-106">Depending on the type of data region and the data that the data region displays, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might generate multiple data feeds from a data region.</span></span>  
  
 <span data-ttu-id="857d1-107">El documento de servicio de Atom contiene un identificador único para cada una de las fuentes de distribución de datos que se usa en una dirección URL para ver el contenido de la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="857d1-107">Atom service document contains a unique identifier for each the data feed and you use the identifier in a URL to view the content of the data feed.</span></span>  
  
 <span data-ttu-id="857d1-108">Para obtener más información, vea [generar fuentes de datos a partir de informes &#40;generador de informes y SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="857d1-108">For more information, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-generate-an-atom-service-document"></a><span data-ttu-id="857d1-109">Generar un documento de servicio de Atom</span><span class="sxs-lookup"><span data-stu-id="857d1-109">To generate an Atom service document</span></span>  
  
1.  <span data-ttu-id="857d1-110">En la página **Inicio** del Administrador de informes, navegue hasta el informe con el que desea generar las fuentes de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="857d1-110">From the Report Manager **Home** page, navigate to the report from which you want to generate data feeds.</span></span>  
  
2.  <span data-ttu-id="857d1-111">Haga clic en el informe.</span><span class="sxs-lookup"><span data-stu-id="857d1-111">Click the report.</span></span>  
  
     <span data-ttu-id="857d1-112">El informe se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="857d1-112">The report is run.</span></span>  
  
3.  <span data-ttu-id="857d1-113">En la barra de herramientas, haga clic en el icono Exportar a fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="857d1-113">On the toolbar, click the Export to Data Feed icon.</span></span>  
  
     <span data-ttu-id="857d1-114">Aparece un mensaje en el que se pregunta si desea guardar o abrir el documento de Atom que contiene la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="857d1-114">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
4.  <span data-ttu-id="857d1-115">Haga clic en **Guardar** para guardar el documento en el sistema de archivos o en **Abrir** para ver el contenido del documento antes de guardarlo.</span><span class="sxs-lookup"><span data-stu-id="857d1-115">Click **Save** to save the document to the file system, or click **Open** to view the document content before saving.</span></span> <span data-ttu-id="857d1-116">**De forma predeterminada, el documento se abre en un explorador.**</span><span class="sxs-lookup"><span data-stu-id="857d1-116">**By default, the document opens in a browser.**</span></span>  
  
5.  <span data-ttu-id="857d1-117">Busque la ubicación para guardar el documento.</span><span class="sxs-lookup"><span data-stu-id="857d1-117">Browse to the location to save the document.</span></span>  
  
6.  <span data-ttu-id="857d1-118">Si lo desea, cambie el nombre del documento.</span><span class="sxs-lookup"><span data-stu-id="857d1-118">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="857d1-119">De manera predeterminada, el nombre del documento es el del informe.</span><span class="sxs-lookup"><span data-stu-id="857d1-119">By default, the document name is the report name.</span></span>  
  
7.  <span data-ttu-id="857d1-120">Compruebe que el tipo de documento es **Archivo ATOMSVC**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="857d1-120">Verify the document type is **ATOMSVC File**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="857d1-121">Si lo desea, abra el archivo .atomsvc en un explorador o un editor de texto o XML.</span><span class="sxs-lookup"><span data-stu-id="857d1-121">Optionally, open the .atomsvc file in a browser or text or XML editor.</span></span>  
  
### <a name="to-view-an-atom-compliant-data-feed"></a><span data-ttu-id="857d1-122">Ver una fuente de distribución de datos conforme a Atom</span><span class="sxs-lookup"><span data-stu-id="857d1-122">To view an Atom-compliant data feed</span></span>  
  
1.  <span data-ttu-id="857d1-123">Si el documento de servicio de Atom no está abierto aún, búsquelo y ábralo en un explorador como Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="857d1-123">If the Atom service document is not already open, locate it and open it in a browser such as Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="857d1-124">Copie la dirección URL de la fuente de distribución de datos que desea ver del documento de servicio de Atom al explorador.</span><span class="sxs-lookup"><span data-stu-id="857d1-124">Copy the URL of the data feed that you want to view from the Atom service document to the browser.</span></span>  
  
     <span data-ttu-id="857d1-125">El formato de la dirección URL es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="857d1-125">The format of the URL is the following:</span></span>  
  
 `http://<server name>/ReportServer?%2f<ReportName>rs%3aCommand=Render&rs%3aFormat=ATOM&rc%3aDataFeed=<Identifier>`  
  
1.  <span data-ttu-id="857d1-126">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="857d1-126">Press ENTER.</span></span>  
  
     <span data-ttu-id="857d1-127">Aparece un mensaje en el que se pregunta si desea guardar o abrir el documento de Atom que contiene la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="857d1-127">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
2.  <span data-ttu-id="857d1-128">Haga clic en **Guardar** para guardar el documento en el sistema de archivos, o en **Abrir** para ver la fuente de distribución de datos antes de guardar.</span><span class="sxs-lookup"><span data-stu-id="857d1-128">Click **Save** to save the document to the file system, or click **Open** to view the data feed before saving.</span></span>  
  
3.  <span data-ttu-id="857d1-129">Busque la ubicación para guardar el documento.</span><span class="sxs-lookup"><span data-stu-id="857d1-129">Browse to the location to save the document.</span></span>  
  
4.  <span data-ttu-id="857d1-130">Si lo desea, cambie el nombre del documento.</span><span class="sxs-lookup"><span data-stu-id="857d1-130">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="857d1-131">De forma predeterminada, el nombre del documento es el del informe.</span><span class="sxs-lookup"><span data-stu-id="857d1-131">By default the document name is the report name.</span></span> <span data-ttu-id="857d1-132">Si el documento de servicio de Atom tiene varias fuentes, de forma predeterminada todas usas el mismo nombre, el del informe.</span><span class="sxs-lookup"><span data-stu-id="857d1-132">If the Atom service document has multiple feeds, by default all use the same name, the report name.</span></span> <span data-ttu-id="857d1-133">Para diferenciarlas, cambie su nombre por otro descriptivo.</span><span class="sxs-lookup"><span data-stu-id="857d1-133">To differentiate them, rename them to use meaningful names.</span></span>  
  
5.  <span data-ttu-id="857d1-134">Compruebe que el tipo de documento es **Archivo ATOM**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="857d1-134">Verify the document type is **ATOM File**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="857d1-135">Si lo desea, abra el archivo .atom en un explorador o editor de texto o XML.</span><span class="sxs-lookup"><span data-stu-id="857d1-135">Optionally, open the .atom file in a browser or text editor or XML editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="857d1-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="857d1-136">See Also</span></span>  
 [<span data-ttu-id="857d1-137">Exportar informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="857d1-137">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](export-reports-report-builder-and-ssrs.md)  
  
  
