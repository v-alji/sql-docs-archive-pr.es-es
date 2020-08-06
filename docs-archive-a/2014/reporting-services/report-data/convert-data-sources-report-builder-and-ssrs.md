---
title: Convertir un origen de datos incrustado en compartido (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
- data sources [Reporting Services], shared
ms.assetid: 0e099c7e-8c03-43eb-9ea3-76e52d9ebbe3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5827bab564b58e7a2b7922f01a33f550a6f523f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663925"
---
# <a name="convert-a-data-source-from-embedded-to-shared-report-builder-and-ssrs"></a><span data-ttu-id="f648d-102">Convertir un origen de datos incrustado en compartido (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="f648d-102">Convert a Data Source from Embedded to Shared (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f648d-103">Cada origen de datos del panel Datos de informe está incrustado y es específico del informe, o está compartido.</span><span class="sxs-lookup"><span data-stu-id="f648d-103">Each data source in the Report Data pane is embedded and specific to the report or is shared.</span></span> <span data-ttu-id="f648d-104">En el Generador de informes, un origen de datos compartido señala un origen de datos compartido publicado en un servidor de informes o un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f648d-104">In Report Builder, a shared data source points to a published shared data source on a report server or SharePoint site.</span></span> <span data-ttu-id="f648d-105">En el Diseñador de informes, un origen de datos compartido señala un origen de datos compartido de la carpeta **Orígenes de datos compartidos** en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="f648d-105">In Report Designer, a shared data source points to a shared data source in the **Shared Data Sources** folder in Solution Explorer.</span></span>  
  
 <span data-ttu-id="f648d-106">Para más información sobre las diferencias entre orígenes de datos insertados y compartidos, vea [Conexiones de datos u orígenes de datos compartidos e incrustados &#40;Generador de informes y SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f648d-106">For more information about the differences between embedded and shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="f648d-107">Para más información sobre cómo crear un origen de datos compartido, vea [Crear un origen de datos incrustado o compartido &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f648d-107">For more information on how to create a shared data source, see [Create an Embedded or Shared Data Source &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="report-designer"></a><span data-ttu-id="f648d-108">Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="f648d-108">Report Designer</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="f648d-109">Para convertir un origen de datos incrustado en compartido</span><span class="sxs-lookup"><span data-stu-id="f648d-109">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="f648d-110">En el panel Datos de informe, haga clic con el botón derecho en el origen de datos y, después, haga clic en **Convertir a origen de datos compartidos**.</span><span class="sxs-lookup"><span data-stu-id="f648d-110">In the Report Data pane, right-click the data source, and then click **Convert to Shared Data Source**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f648d-111">Si el panel Datos de informe no está visible, haga clic en **Datos de informe** en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="f648d-111">If the Report Data pane is not visible, on the **View** menu, click **Report Data**.</span></span> <span data-ttu-id="f648d-112">Si el panel se abre como una ventana flotante, puede acoplarlo.</span><span class="sxs-lookup"><span data-stu-id="f648d-112">If the pane opens as a floating window, you can dock it.</span></span> <span data-ttu-id="f648d-113">Para más información, vea [Acoplar el panel Datos de informe en el Diseñador de informes &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f648d-113">For more information, see [Dock the Report Data Pane in Report Designer &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span></span>  
  
     <span data-ttu-id="f648d-114">En el panel Datos de informe, el icono de origen de datos cambia al icono de origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="f648d-114">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span> <span data-ttu-id="f648d-115">En el Explorador de soluciones, aparece un origen de datos compartido con el mismo nombre bajo la carpeta **Origen de datos compartido** .</span><span class="sxs-lookup"><span data-stu-id="f648d-115">In Solution Explorer, a shared data source with the same name appears under the **Shared Data Source** folder.</span></span>  
  
### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="f648d-116">Para convertir un origen de datos compartido en incrustado</span><span class="sxs-lookup"><span data-stu-id="f648d-116">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="f648d-117">En el panel Datos de informe, haga clic con el botón derecho en el origen de datos, abra el cuadro de diálogo **Propiedades del origen de datos** y, después, haga clic en **Conexión incrustada**.</span><span class="sxs-lookup"><span data-stu-id="f648d-117">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="f648d-118">Escriba la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="f648d-118">Enter the required information.</span></span>  
  
     <span data-ttu-id="f648d-119">En el panel Datos de informe, el icono de origen de datos cambia al icono de origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="f648d-119">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="report-builder"></a><span data-ttu-id="f648d-120">Generador de informes</span><span class="sxs-lookup"><span data-stu-id="f648d-120">Report Builder</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="f648d-121">Para convertir un origen de datos incrustado en compartido</span><span class="sxs-lookup"><span data-stu-id="f648d-121">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="f648d-122">En el panel Datos de informe, haga clic con el botón derecho en el origen de datos para abrir el cuadro de diálogo **Propiedades del origen de datos** y, después, haga clic en **Conexión incrustada**.</span><span class="sxs-lookup"><span data-stu-id="f648d-122">In the Report Data pane, right-click the data source to open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="f648d-123">Escriba la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="f648d-123">Enter the required information.</span></span>  
  
     <span data-ttu-id="f648d-124">En el panel Datos de informe, el icono de origen de datos cambia al icono de origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="f648d-124">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
#### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="f648d-125">Para convertir un origen de datos compartido en incrustado</span><span class="sxs-lookup"><span data-stu-id="f648d-125">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="f648d-126">En el panel Datos de informe, haga clic con el botón derecho en el origen de datos, abra el cuadro de diálogo **Propiedades del origen de datos** y, después, haga clic en **Conexión incrustada**.</span><span class="sxs-lookup"><span data-stu-id="f648d-126">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="f648d-127">Escriba la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="f648d-127">Enter the required information.</span></span>  
  
     <span data-ttu-id="f648d-128">En el panel Datos de informe, el icono de origen de datos cambia al icono de origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="f648d-128">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f648d-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f648d-129">See Also</span></span>  
 <span data-ttu-id="f648d-130">[Administrar orígenes de datos de informe](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="f648d-130">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="f648d-131">Data Connections, Data Sources, and Connection Strings in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f648d-131">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
