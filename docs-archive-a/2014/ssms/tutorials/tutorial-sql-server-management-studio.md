---
title: 'Tutorial: SQL Server Management Studio | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.tutorialstart.ssms.f1
helpviewer_keywords:
- projects [SQL Server Management Studio], tutorials
- templates [SQL Server], SQL Server Management Studio
- source controls [SQL Server Management Studio], tutorials
- Help [SQL Server], SQL Server Management Studio
- tutorials [SQL Server Management Studio]
- Transact-SQL tutorials
- solutions [SQL Server Management Studio], tutorials
- SQL Server Management Studio [SQL Server], tutorials
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d2bade70-07cf-4d94-b5d2-88aecb538ed1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8206fea828d6169975dc1d026a22e18e682f71e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676806"
---
# <a name="tutorial-sql-server-management-studio"></a><span data-ttu-id="00dd9-102">Tutorial: SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="00dd9-102">Tutorial: SQL Server Management Studio</span></span>
  <span data-ttu-id="00dd9-103">El tutorial [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] le muestra el entorno integrado para administrar la infraestructura de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00dd9-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tutorial introduces you to the integrated environment for managing your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] infrastructure.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="00dd9-104">presenta una interfaz gráfica para configurar, supervisar y administrar instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00dd9-104">presents a graphical interface for configuring, monitoring, and administering instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00dd9-105">También permite implementar, supervisar y actualizar los componentes de capa de datos usados por las aplicaciones, como bases de datos y almacenamientos de datos.</span><span class="sxs-lookup"><span data-stu-id="00dd9-105">It also allows you to deploy, monitor, and upgrade the data-tier components used by your applications, such as databases and data warehouses.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="00dd9-106">también proporciona editores de lenguaje de [!INCLUDE[tsql](../../includes/tsql-md.md)], MDX, DMX y XML para editar y depurar scripts.</span><span class="sxs-lookup"><span data-stu-id="00dd9-106">also provides [!INCLUDE[tsql](../../includes/tsql-md.md)], MDX, DMX, and XML language editors for editing and debugging scripts.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="00dd9-107">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="00dd9-107">What You Will Learn</span></span>  
 <span data-ttu-id="00dd9-108">Este tutorial le ayudará a entender cómo se presenta la información en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y cómo aprovechar las ventajas de las características.</span><span class="sxs-lookup"><span data-stu-id="00dd9-108">This tutorial will help you understand the presentation of information in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to take advantage of the features.</span></span> <span data-ttu-id="00dd9-109">Tenga en cuenta que este tutorial se aplica a la instalación completa de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] que se incluye con todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] excepto [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00dd9-109">Note that this tutorial applies to the complete installation of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] that is included with all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="00dd9-110">La funcionalidad para las instalaciones básicas de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y para las instalaciones de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] que se proporcionan con [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] es algo diferente de la que se muestra en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="00dd9-110">Functionality for basic installations of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and for [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] installations that ship with [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] is slightly different than what is presented in this tutorial.</span></span>  
  
 <span data-ttu-id="00dd9-111">La mejor forma de familiarizarse con [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] es practicar.</span><span class="sxs-lookup"><span data-stu-id="00dd9-111">The best way to get acquainted with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is through hands-on practice.</span></span> <span data-ttu-id="00dd9-112">Este tutorial le mostrará cómo administrar los componentes de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y cómo localizar las características que utiliza habitualmente.</span><span class="sxs-lookup"><span data-stu-id="00dd9-112">This tutorial will teach you how to manage the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to find the features that you use regularly.</span></span>  
  
 <span data-ttu-id="00dd9-113">El tutorial está compuesto por tres lecciones:</span><span class="sxs-lookup"><span data-stu-id="00dd9-113">This tutorial is divided into three lessons:</span></span>  
  
 [<span data-ttu-id="00dd9-114">Lección 1: Navegación básica en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="00dd9-114">Lesson 1: Basic Navigation in SQL Server Management Studio</span></span>](lesson-1-basic-navigation-in-sql-server-management-studio.md)  
 <span data-ttu-id="00dd9-115">En esta lección, aprenderá a utilizar los componentes de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], a configurar nuevamente el diseño del entorno y a restaurar el diseño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="00dd9-115">In this lesson you will learn how to use the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], how to reconfigure the environment layout, and how to restore the default layout.</span></span>  
  
 [<span data-ttu-id="00dd9-116">Lección 2: Escribir Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="00dd9-116">Lesson 2: Writing Transact-SQL</span></span>](lesson-2-writing-transact-sql.md)  
 <span data-ttu-id="00dd9-117">En esta lección, aprenderá a abrir el Editor de consultas, a administrar código y a utilizar otras características nuevas del editor.</span><span class="sxs-lookup"><span data-stu-id="00dd9-117">In this lesson, you will learn how to open Query Editor, how to manage code, and how to use the other new features of Query Editor.</span></span>  
  
 [<span data-ttu-id="00dd9-118">Lección 3: Trabajar con plantillas, soluciones, proyectos de script</span><span class="sxs-lookup"><span data-stu-id="00dd9-118">Lesson 3: Working with Templates, Solutions, and Script Projects</span></span>](lesson-3-working-with-templates-solutions-and-script-projects.md)  
 <span data-ttu-id="00dd9-119">En esta lección, aprenderá a usar las plantillas y a organizar los scripts en soluciones y proyectos.</span><span class="sxs-lookup"><span data-stu-id="00dd9-119">In this lesson you will learn how to use templates, and organize scripts into solutions and projects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00dd9-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00dd9-120">Requirements</span></span>  
 <span data-ttu-id="00dd9-121">Este tutorial está destinado a los administradores de bases de datos con experiencia y a los desarrolladores de bases de datos que no están familiarizados con [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], pero que conocen los conceptos relacionados con las bases de datos y el lenguaje [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00dd9-121">This tutorial is intended for experienced database administrators and database developers who are not familiar with [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], but who are who are familiar with database concepts and the [!INCLUDE[tsql](../../includes/tsql-md.md)] language.</span></span>  
  
 <span data-ttu-id="00dd9-122">Para usar este tutorial, debe tener el software siguiente instalado en el sistema:</span><span class="sxs-lookup"><span data-stu-id="00dd9-122">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="00dd9-123">o una versión posterior con las bases de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00dd9-123">or a later version with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample databases.</span></span> <span data-ttu-id="00dd9-124">Con el objeto de mejorar la seguridad, las bases de datos de ejemplo no se instalan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00dd9-124">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="00dd9-125">Para instalarlas, consulte [Instalar ejemplos de SQL Server y bases de datos de ejemplo](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="00dd9-125">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
-   <span data-ttu-id="00dd9-126">Internet Explorer 9.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="00dd9-126">Internet Explorer 9.0 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00dd9-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00dd9-127">See Also</span></span>  
 [<span data-ttu-id="00dd9-128">Tutoriales del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="00dd9-128">Database Engine Tutorials</span></span>](../../relational-databases/database-engine-tutorials.md)  
  
  
