---
title: Crear un informe de tabla básico (Tutorial de SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- walkthroughs [Reporting Services]
- tutorials [Reporting Services]
- reports [Reporting Services], creating
ms.assetid: 3b539b4b-26f2-4c0b-b506-80f175679a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02e0f42869a3bfa88e0c6646fd447968c8ba3a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661811"
---
# <a name="create-a-basic-table-report-ssrs-tutorial"></a><span data-ttu-id="c53d1-102">Crear un informe de tabla básico (Tutorial de SSRS)</span><span class="sxs-lookup"><span data-stu-id="c53d1-102">Create a Basic Table Report (SSRS Tutorial)</span></span>
  <span data-ttu-id="c53d1-103">Con este tutorial, aprenderá a usar el Diseñador de informes para crear un informe de tabla básico basado en la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c53d1-103">This tutorial is designed to help you create a basic table report based on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database using Report Designer.</span></span> <span data-ttu-id="c53d1-104">También puede crear informes con el Generador de informes o con el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="c53d1-104">You can also use Report Builder or the Report Wizard to create reports.</span></span> <span data-ttu-id="c53d1-105">En este tutorial, creará un proyecto de informes, configurará la información de conexión, definirá una consulta, agregará una región de datos de tabla, agrupará y calculará los totales de varios campos, y obtendrá una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="c53d1-105">In this tutorial, you will create a report project, set up connection information, define a query, add a Table data region, group and total some fields, and preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c53d1-106">Para completar este tutorial, [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] debe ejecutarse en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="c53d1-106">To complete this tutorial, you must be running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode.</span></span> <span data-ttu-id="c53d1-107">Si [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] se ejecuta en el modo integrado de SharePoint, los pasos en que se usan las direcciones URL del servidor de informes no funcionan.</span><span class="sxs-lookup"><span data-stu-id="c53d1-107">If you are running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint integrated mode, the steps that use report server URLs do not work.</span></span> <span data-ttu-id="c53d1-108">Para obtener más información sobre los [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modos, vea [Reporting Services servidor de informes](reporting-services-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="c53d1-108">For more information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modes, see [Reporting Services Report Server](reporting-services-report-server.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c53d1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c53d1-109">Requirements</span></span>  
 <span data-ttu-id="c53d1-110">Para usar este tutorial, debe tener el software siguiente instalado en el sistema:</span><span class="sxs-lookup"><span data-stu-id="c53d1-110">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="c53d1-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c53d1-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database engine.</span></span>  
  
-   <span data-ttu-id="c53d1-112">Las base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c53d1-112">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  <span data-ttu-id="c53d1-113">Para obtener más información, vea [Adventure Works para SQL Server 2012 (Adventure Works para SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) ( https://go.microsoft.com/fwlink/?LinkId=245471). .</span><span class="sxs-lookup"><span data-stu-id="c53d1-113">For more information, see [Adventure Works for SQL Server 2012 (Adventure Works for SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) (https://go.microsoft.com/fwlink/?LinkId=245471)..</span></span> <span data-ttu-id="c53d1-114">Para obtener más información sobre la compatibilidad con las bases de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ejemplo y el código de ejemplo de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] , vea [información general sobre bases de datos y ejemplos](https://go.microsoft.com/fwlink/?LinkId=110391) en el sitio web de codeplex.</span><span class="sxs-lookup"><span data-stu-id="c53d1-114">For more information about support for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sample databases and sample code for [!INCLUDE[ssExpress](../includes/ssexpress-md.md)], see [Databases and Samples Overview](https://go.microsoft.com/fwlink/?LinkId=110391) on the CodePlex Web site.</span></span>  
  
-   [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)]<span data-ttu-id="c53d1-115">.</span><span class="sxs-lookup"><span data-stu-id="c53d1-115">.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="c53d1-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c53d1-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNote64Samp](../includes/ssnote64samp-md.md)]  
  
 <span data-ttu-id="c53d1-117">También debe disponer de permisos de solo lectura para recuperar datos de la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c53d1-117">You must also have read-only permissions to retrieve data from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="c53d1-118">Tareas</span><span class="sxs-lookup"><span data-stu-id="c53d1-118">Tasks</span></span>  
 [<span data-ttu-id="c53d1-119">Lección 1: Crear un proyecto de servidor de informes &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c53d1-119">Lesson 1: Creating a Report Server Project &#40;Reporting Services&#41;</span></span>](lesson-1-creating-a-report-server-project-reporting-services.md)  
  
 [<span data-ttu-id="c53d1-120">Lección 2: Especificar información de conexión &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c53d1-120">Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;</span></span>](lesson-2-specifying-connection-information-reporting-services.md)  
  
 [<span data-ttu-id="c53d1-121">Lección 3: Definir un conjunto de datos para el informe de tabla &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c53d1-121">Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;</span></span>](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md)  
  
 [<span data-ttu-id="c53d1-122">Lección 4: Agregar una tabla al informe &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c53d1-122">Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;</span></span>](lesson-4-adding-a-table-to-the-report-reporting-services.md)  
  
 [<span data-ttu-id="c53d1-123">Lección 5: Aplicar formato a un informe &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c53d1-123">Lesson 5: Formatting a Report &#40;Reporting Services&#41;</span></span>](lesson-5-formatting-a-report-reporting-services.md)  
  
 [<span data-ttu-id="c53d1-124">Lección 6: Agregar grupos y totales &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c53d1-124">Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;</span></span>](lesson-6-adding-grouping-and-totals-reporting-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="c53d1-125">Al revisar los tutoriales, se recomienda agregar los botones **siguiente** y **anterior** a la barra de herramientas del visor de documentos.</span><span class="sxs-lookup"><span data-stu-id="c53d1-125">When reviewing tutorials, we recommend that you add **Next** and **Previous** buttons to the document viewer toolbar.</span></span> <span data-ttu-id="c53d1-126">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="c53d1-126">For more information, see.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c53d1-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c53d1-127">See Also</span></span>  
 [<span data-ttu-id="c53d1-128">Tutoriales de Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c53d1-128">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](reporting-services-tutorials-ssrs.md)  
  
  
