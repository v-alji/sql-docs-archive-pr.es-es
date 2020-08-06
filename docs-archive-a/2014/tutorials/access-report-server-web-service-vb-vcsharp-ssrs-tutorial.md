---
title: Obtener acceso al servicio Web del servidor de informes mediante Visual Basic o Visual C# (tutorial de SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- walkthroughs [Reporting Services]
- Reporting Services, Web service
- Web service [Reporting Services], tutorials
ms.assetid: cf688163-4ac0-475b-b6dd-6f2f05b553c6
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 3dc2599b4fafe682d74089d637918e04db9ed219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747800"
---
# <a name="accessing-the-report-server-web-service-using-visual-basic-or-visual-c-ssrs-tutorial"></a><span data-ttu-id="2c2f6-102">Obtener acceso al servicio web del servidor de informes mediante Visual Basic o Visual C# (Tutorial de SSRS)</span><span class="sxs-lookup"><span data-stu-id="2c2f6-102">Accessing the Report Server Web Service Using Visual Basic or Visual C# (SSRS Tutorial)</span></span>
  <span data-ttu-id="2c2f6-103">En el siguiente tutorial se muestra cómo obtener acceso al servicio Web del servidor de informes desde una aplicación creada con [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c2f6-103">The following tutorial shows you how to access the Report Server Web service from an application created with [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] or [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="2c2f6-104">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="2c2f6-104">What You Will Learn</span></span>  
 <span data-ttu-id="2c2f6-105">En el transcurso de este tutorial, realizará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c2f6-105">During the course of this tutorial, you will complete the following:</span></span>  
  
-   <span data-ttu-id="2c2f6-106">Cree una aplicación cliente mediante la [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] plantilla de proyecto aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-106">Create a client application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="2c2f6-107">Agregar una referencia web del servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-107">Add a Web reference for the Report Server Web service.</span></span>  
  
-   <span data-ttu-id="2c2f6-108">Escribir código para tener acceso al servicio web.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-108">Write code to access the Web service.</span></span>  
  
-   <span data-ttu-id="2c2f6-109">Ejecutar la aplicación de consola en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-109">Run the console application in debug mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c2f6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c2f6-110">Requirements</span></span>  
 <span data-ttu-id="2c2f6-111">Para poder completar el tutorial en su totalidad, debe disponer de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c2f6-111">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="2c2f6-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c2f6-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="2c2f6-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)]o similar [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] herramienta de desarrollo compatible con.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] or a similar [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]-compatible development tool.</span></span>  
  
-   <span data-ttu-id="2c2f6-114">Permisos suficientes para tener acceso al servicio web del servidor de informes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en el equipo en que se encuentre el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-114">Sufficient permissions to be able to access the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="2c2f6-115">Un informe instalado en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-115">A report installed on your report server.</span></span> <span data-ttu-id="2c2f6-116">En este tutorial se utiliza el informe de muestra Company Sales.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-116">This tutorial uses the sample report, Company Sales.</span></span> <span data-ttu-id="2c2f6-117">Para obtener más información sobre los informes de ejemplo, vea [SQL Server Reporting Services ejemplos de productos](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="2c2f6-117">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c2f6-118">Los ejemplos no se instalan automáticamente durante la ejecución del programa de instalación, pero puede instalarlos en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-118">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="2c2f6-119">Para obtener información acerca de los ejemplos, vea [SQL Server ejemplos de productos](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="2c2f6-119">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="2c2f6-120">**Tiempo estimado para completar el tutorial:** 60 minutos</span><span class="sxs-lookup"><span data-stu-id="2c2f6-120">**Estimated time to complete the tutorial:** 60 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="2c2f6-121">Tareas</span><span class="sxs-lookup"><span data-stu-id="2c2f6-121">Tasks</span></span>  
 [<span data-ttu-id="2c2f6-122">Lección 1: Creación del proyecto cliente del servicio web</span><span class="sxs-lookup"><span data-stu-id="2c2f6-122">Lesson 1: Creating the Web Service Client Project</span></span>](../../2014/tutorials/lesson-1-creating-the-web-service-client-project.md)  
  
 [<span data-ttu-id="2c2f6-123">Lección 2: Adición de una referencia web</span><span class="sxs-lookup"><span data-stu-id="2c2f6-123">Lesson 2: Adding a Web Reference</span></span>](../../2014/tutorials/lesson-2-adding-a-web-reference.md)  
  
 [<span data-ttu-id="2c2f6-124">Lección 3: Acceso al servicio web</span><span class="sxs-lookup"><span data-stu-id="2c2f6-124">Lesson 3: Accessing the Web Service</span></span>](../../2014/tutorials/lesson-3-accessing-the-web-service.md)  
  
 [<span data-ttu-id="2c2f6-125">Lección 4: ejecutar la aplicación &#40;VB-VC&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="2c2f6-125">Lesson 4: Running the Application &#40;VB-VC&#35;&#41;</span></span>](../../2014/tutorials/lesson-4-running-the-application-vb-vcsharp.md)  
  
  
