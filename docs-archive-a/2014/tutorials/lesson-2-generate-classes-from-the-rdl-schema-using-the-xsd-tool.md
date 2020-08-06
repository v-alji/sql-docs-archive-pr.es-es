---
title: 'Lección 2: generar clases a partir del esquema RDL con la herramienta XSD | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a81c87f1-7977-4b30-b6ac-b38b3e2b6398
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 2c5db118ad8f94afc72cea44b9a2489f2b4fd7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747309"
---
# <a name="lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool"></a><span data-ttu-id="92144-102">Lección 2: Generación de clases a partir del esquema RDL con la herramienta xsd</span><span class="sxs-lookup"><span data-stu-id="92144-102">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>
  <span data-ttu-id="92144-103">Una vez creado el proyecto de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], el siguiente paso es recuperar una copia local del esquema de definición de informe y ejecutar la herramienta de definición de esquemas XML (Xsd.exe).</span><span class="sxs-lookup"><span data-stu-id="92144-103">After you have created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project, the next step is to retrieve a local copy of the report definition schema and run the XML Schema Definition Tool (Xsd.exe).</span></span>  
  
### <a name="to-generate-the-rdl-classes"></a><span data-ttu-id="92144-104">Para generar clases RDL</span><span class="sxs-lookup"><span data-stu-id="92144-104">To generate the RDL classes</span></span>  
  
1.  <span data-ttu-id="92144-105">Abra una instancia de [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (o un explorador Web equivalente) y vaya a la dirección URL siguiente:</span><span class="sxs-lookup"><span data-stu-id="92144-105">Open an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (or equivalent Web browser) and navigate to the following URL:</span></span>  
  
    ```  
    https://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition/ReportDefinition.xsd  
    ```  
  
2.  <span data-ttu-id="92144-106">Una vez abierto el esquema RDL en el explorador, vaya al menú **archivo** y seleccione **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="92144-106">Once the RDL schema has been opened in the browser, browse to the **File** menu, and select **Save As**.</span></span>  
  
3.  <span data-ttu-id="92144-107">Vaya a la ubicación en la que creó el proyecto de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] y guarde el esquema con el nombre de archivo ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="92144-107">Browse to the location where you created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project and save the schema with the file name ReportDefinition.xsd.</span></span>  
  
4.  <span data-ttu-id="92144-108">Una vez guardado el archivo, abra una instancia del símbolo del [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] sistema.</span><span class="sxs-lookup"><span data-stu-id="92144-108">After the file has been saved, open an instance of the [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] command prompt.</span></span> <span data-ttu-id="92144-109">Para abrir una instancia del símbolo del sistema, haga clic en el menú Inicio, seleccione **todos los programas**, **Microsoft Visual Studio 2010**, seleccione **Visual Studio Tools** y haga clic en **símbolo del sistema de Visual Studio (2010)**.</span><span class="sxs-lookup"><span data-stu-id="92144-109">To open an instance of the command prompt, click the Start menu, point to **All Programs**, point to **Microsoft Visual Studio 2010**, point to **Visual Studio Tools** and click **Visual Studio Command Prompt (2010)**.</span></span>  
  
5.  <span data-ttu-id="92144-110">Cambie la ruta actual por la ubicación en la que guardó el archivo ReportDefinition.xsd:</span><span class="sxs-lookup"><span data-stu-id="92144-110">Change the current path to the location where you saved the ReportDefinition.xsd file:</span></span>  
  
     `CD\<ReportDefinition.xsd Path>`  
  
6.  <span data-ttu-id="92144-111">Genere el archivo ReportDefinition.cs que contiene las clases para el esquema RDL con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="92144-111">Generate the ReportDefinition.cs file that contains the classes for the RDL schema with the following command:</span></span>  
  
     `xsd /c /n:SampleRDLSchema ReportDefinition.xsd`  
  
     <span data-ttu-id="92144-112">Para generar un archivo ReportDefinition.vb, utilice este comando:</span><span class="sxs-lookup"><span data-stu-id="92144-112">To generate a ReportDefinition.vb file use this command:</span></span>  
  
     `xsd /c /l:VB /n:SampleRDLSchema ReportDefinition.xsd`  
  
7.  <span data-ttu-id="92144-113">Agregue ReportDefinition.xsd al proyecto.</span><span class="sxs-lookup"><span data-stu-id="92144-113">Add ReportDefinition.xsd your project.</span></span> <span data-ttu-id="92144-114">En el menú **proyecto** , haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="92144-114">From the **Project** menu, click **Add Existing Item**.</span></span> <span data-ttu-id="92144-115">Busque la ubicación del archivo ReportDefinition. xsd, seleccione ReportDefinition. xsd y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="92144-115">Browse to the location of the ReportDefinition.xsd file, select ReportDefinition.xsd, and click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="92144-116">Después de agregar el archivo ReportDefinition. xsd al proyecto, observará en **Explorador de soluciones** que el archivo ReportDefinition.CS (. VB) no está allí.</span><span class="sxs-lookup"><span data-stu-id="92144-116">After you have added the ReportDefinition.xsd file to the project you will notice in **Solution Explorer** that the ReportDefinition.cs (.vb) file is not there.</span></span> <span data-ttu-id="92144-117">Para mostrar el archivo, haga clic el botón de expandir o contraer situado junto al archivo ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="92144-117">To display the file, click the expand/collapse button next to the ReportDefinition.xsd file.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="92144-118">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="92144-118">Next Lesson</span></span>  
 <span data-ttu-id="92144-119">En la siguiente lección, escribirá código para cargar una definición de informe desde un servidor de informes usando las clases generadas con el esquema RDL.</span><span class="sxs-lookup"><span data-stu-id="92144-119">In the next lesson, you will write code to load a report definition from a report server using the classes you generated from the RDL schema.</span></span> <span data-ttu-id="92144-120">Vea [Lección 3: cargar una definición de informe desde el servidor de informes](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="92144-120">See [Lesson 3: Load a Report Definition from the Report Server](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92144-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92144-121">See Also</span></span>  
 <span data-ttu-id="92144-122">[Actualizar informes con clases generadas a partir del esquema RDL &#40;tutorial de SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="92144-122">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="92144-123">Lenguaje RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="92144-123">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
