---
title: Actualizar informes con clases generadas a partir del esquema RDL (tutorial de SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RDL [Reporting Services], generating
- RDL [Reporting Services], tutorials
- RDL [Reporting Services], serializing
ms.assetid: 8f81d48f-7ab9-4ef8-bce0-7d16d9a47fbd
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: f3972b8e1af6d50ccc6f5188c8f671fe333ebce8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663829"
---
# <a name="updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial"></a><span data-ttu-id="e3905-102">Actualizar informes con clases generadas a partir del esquema RDL (Tutorial de SSRS)</span><span class="sxs-lookup"><span data-stu-id="e3905-102">Updating Reports Using Classes Generated from the RDL Schema (SSRS Tutorial)</span></span>
  <span data-ttu-id="e3905-103">En este tutorial se muestra cómo utilizar la herramienta de definición de esquemas XML (Xsd.exe) para generar clases que le permitan serializar y deserializar archivos de definición de informe (. RDL y. rdlc) con la [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> clase.</span><span class="sxs-lookup"><span data-stu-id="e3905-103">This tutorial illustrates how to use the XML Schema Definition Tool (Xsd.exe) to generate classes that allow you to serialize and deserialize report definition files (.rdl and .rdlc) with the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="e3905-104">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="e3905-104">What You Will Learn</span></span>  
 <span data-ttu-id="e3905-105">En el transcurso de este tutorial, realizará las actividades siguientes:</span><span class="sxs-lookup"><span data-stu-id="e3905-105">During the course of this tutorial, you will complete the following activities:</span></span>  
  
-   <span data-ttu-id="e3905-106">Cree una aplicación con la [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] plantilla de proyecto aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="e3905-106">Create an application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="e3905-107">Generar clases a partir del esquema del lenguaje RDL (Report Definition Language) mediante la herramienta **xsd** .</span><span class="sxs-lookup"><span data-stu-id="e3905-107">Generate classes from the Report Definition Language (RDL) schema using the **xsd** tool.</span></span>  
  
-   <span data-ttu-id="e3905-108">Conectarse a un servidor de informes y recuperar una definición de informe.</span><span class="sxs-lookup"><span data-stu-id="e3905-108">Connect to a report server and retrieve a report definition.</span></span>  
  
-   <span data-ttu-id="e3905-109">Escribir un código para actualizar el archivo de definición de informe.</span><span class="sxs-lookup"><span data-stu-id="e3905-109">Write code to update the report definition file.</span></span>  
  
-   <span data-ttu-id="e3905-110">Guardar la definición de informe actualizada en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e3905-110">Save the updated report definition back to the report server.</span></span>  
  
-   <span data-ttu-id="e3905-111">Ejecutar la aplicación del esquema RDL (VB/C#).</span><span class="sxs-lookup"><span data-stu-id="e3905-111">Run the RDL Schema Application (VB/C#).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3905-112">Los ejemplos de código proporcionados en este tutorial pueden provocar errores en los informes que no tengan una descripción.</span><span class="sxs-lookup"><span data-stu-id="e3905-112">The code samples provided in this tutorial might fail for reports having no description.</span></span> <span data-ttu-id="e3905-113">El error se debe a que la propiedad de descripción no existe en los informes en los que no se ha especificado una descripción.</span><span class="sxs-lookup"><span data-stu-id="e3905-113">The failure is because the description property does not exist for the reports with description not specified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3905-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3905-114">Requirements</span></span>  
 <span data-ttu-id="e3905-115">Para poder completar el tutorial en su totalidad, debe disponer de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e3905-115">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="e3905-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3905-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="e3905-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3905-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="e3905-118">Permisos suficientes para tener acceso al servicio web del servidor de informes y publicar informes en este servicio en el equipo en que se encuentre el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e3905-118">Sufficient permissions to be able to access and publish reports to the Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="e3905-119">La base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] instalada en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3905-119">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database installed to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e3905-120">Un informe instalado en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e3905-120">A report installed on your report server.</span></span> <span data-ttu-id="e3905-121">En este tutorial se utiliza el informe de muestra Company Sales 2012.</span><span class="sxs-lookup"><span data-stu-id="e3905-121">This tutorial uses the sample report, Company Sales 2012.</span></span> <span data-ttu-id="e3905-122">Para obtener más información sobre los informes de ejemplo, vea [SQL Server Reporting Services ejemplos de productos](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="e3905-122">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3905-123">Los ejemplos no se instalan automáticamente durante la ejecución del programa de instalación, pero puede instalarlos en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="e3905-123">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="e3905-124">Para obtener información acerca de los ejemplos, vea [SQL Server ejemplos de productos](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="e3905-124">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="e3905-125">**Tiempo estimado para completar el tutorial:** 30 minutos</span><span class="sxs-lookup"><span data-stu-id="e3905-125">**Estimated time to complete the tutorial:** 30 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="e3905-126">Tareas</span><span class="sxs-lookup"><span data-stu-id="e3905-126">Tasks</span></span>  
 [<span data-ttu-id="e3905-127">Lección 1: Creación del proyecto de Visual Studio Esquema RDL</span><span class="sxs-lookup"><span data-stu-id="e3905-127">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>](../../2014/tutorials/lesson-1-create-the-rdl-schema-visual-studio-project.md)  
  
 [<span data-ttu-id="e3905-128">Lección 2: Generación de clases a partir del esquema RDL con la herramienta xsd</span><span class="sxs-lookup"><span data-stu-id="e3905-128">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md)  
  
 [<span data-ttu-id="e3905-129">Lección 3: Carga de una definición de informe desde el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="e3905-129">Lesson 3: Load a Report Definition from the Report Server</span></span>](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md)  
  
 [<span data-ttu-id="e3905-130">Lección 4: Actualización de la definición del informe mediante programación</span><span class="sxs-lookup"><span data-stu-id="e3905-130">Lesson 4: Update the Report Definition Programmatically</span></span>](../../2014/tutorials/lesson-4-update-the-report-definition-programmatically.md)  
  
 [<span data-ttu-id="e3905-131">Lección 5: Publicación de la definición de informe en el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="e3905-131">Lesson 5: Publish the Report Definition to the Report Server</span></span>](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md)  
  
 [<span data-ttu-id="e3905-132">Lección 6: ejecutar la aplicación de esquema RDL &#40;VB-C&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="e3905-132">Lesson 6: Run the RDL Schema Application &#40;VB-C&#35;&#41;</span></span>](../../2014/tutorials/lesson-6-run-the-rdl-schema-application-vb-csharp.md)  
  
## <a name="see-also"></a><span data-ttu-id="e3905-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3905-133">See Also</span></span>  
 [<span data-ttu-id="e3905-134">Lenguaje RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e3905-134">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
