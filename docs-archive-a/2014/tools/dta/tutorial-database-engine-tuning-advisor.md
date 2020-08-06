---
title: 'Tutorial: Asistente para la optimización de motor de base de datos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], tutorials
- tutorials [Database Engine Tuning Advisor]
ms.assetid: 3b54cbbe-d8c6-424d-92f1-aa58179f4da8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 68e026cb28b875b834f20c906232285ede8e217b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663256"
---
# <a name="tutorial-database-engine-tuning-advisor"></a><span data-ttu-id="2f579-102">Tutorial: Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="2f579-102">Tutorial: Database Engine Tuning Advisor</span></span>
  <span data-ttu-id="2f579-103">Bienvenido al tutorial del Asistente para la optimización de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f579-103">Welcome to the Database Engine Tuning Advisor tutorial.</span></span> <span data-ttu-id="2f579-104">El Asistente para la optimización de motor de base de datos analiza la forma en que se procesan las consultas en las bases de datos especificadas por el usuario y, a continuación, recomienda la forma en que se puede mejorar el rendimiento del procesamiento modificando las estructuras de base de datos tales como índices, vistas indizadas y particiones.</span><span class="sxs-lookup"><span data-stu-id="2f579-104">Database Engine Tuning Advisor examines how queries are processed in the databases you specify, and then recommends how you can improve query processing performance by modifying database structures such as indexes, indexed views, and partitioning.</span></span>  
  
 <span data-ttu-id="2f579-105">El Asistente para la optimización de motor de base de datos proporciona dos interfaces de usuario: una interfaz gráfica de usuario (GUI) y la utilidad del símbolo del sistema **dta** .</span><span class="sxs-lookup"><span data-stu-id="2f579-105">Database Engine Tuning Advisor provides two user interfaces: a graphical user interface (GUI) and the **dta** command prompt utility.</span></span> <span data-ttu-id="2f579-106">La GUI facilita y agiliza la obtención de resultados a partir de las sesiones de optimización y la utilidad **dta** facilita la incorporación de la funcionalidad del Asistente para la optimización de motor de base de datos a los scripts con el fin de automatizar la optimización.</span><span class="sxs-lookup"><span data-stu-id="2f579-106">The GUI makes it easy to quickly view the results of tuning sessions, and the **dta** utility makes it easy to incorporate Database Engine Tuning Advisor functionality into scripts for automated tuning.</span></span> <span data-ttu-id="2f579-107">Además, este asistente admite datos de entrada XML, lo que ofrece un mayor control sobre el proceso de optimización.</span><span class="sxs-lookup"><span data-stu-id="2f579-107">In addition, Database Engine Tuning Advisor can take XML input, which offers more control over the tuning process.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="2f579-108">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="2f579-108">What You Will Learn</span></span>  
 <span data-ttu-id="2f579-109">Este tutorial le mostrará cómo navegar por la GUI del Asistente para la optimización de motor de base de datos y cómo realizar algunas tareas básicas tanto con la GUI como con la utilidad **dta** .</span><span class="sxs-lookup"><span data-stu-id="2f579-109">This tutorial will teach you how to navigate the Database Engine Tuning Advisor GUI, and how to perform some basic tasks with both the GUI and the **dta** utility.</span></span> <span data-ttu-id="2f579-110">Incluye las lecciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f579-110">It contains the following lessons:</span></span>  
  
 [<span data-ttu-id="2f579-111">Lección 1: Navegación básica en el Asistente para la optimización de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f579-111">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
 <span data-ttu-id="2f579-112">En esta lección, se familiarizará con la GUI del Asistente para la optimización de motor de base de datos y aprenderá a configurar las opciones de visualización y el diseño.</span><span class="sxs-lookup"><span data-stu-id="2f579-112">In this lesson, you will familiarize yourself with the new Database Engine Tuning Advisor GUI and learn how to set display options and layout.</span></span>  
  
 [<span data-ttu-id="2f579-113">Lección 2: Usar el Asistente para la optimización de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f579-113">Lesson 2: Using Database Engine Tuning Advisor</span></span>](lesson-2-using-database-engine-tuning-advisor.md)  
 <span data-ttu-id="2f579-114">En esta lección, aprenderá a realizar tareas básicas de optimización con la GUI del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f579-114">In this lesson, you will learn how to perform basic tuning tasks with the Database Engine Tuning Advisor GUI.</span></span>  
  
 [<span data-ttu-id="2f579-115">Lección 3: Uso de la utilidad del símbolo del sistema DTA</span><span class="sxs-lookup"><span data-stu-id="2f579-115">Lesson 3: Using the dta Command Prompt Utility</span></span>](lesson-3-using-the-dta-command-prompt-utility.md)  
 <span data-ttu-id="2f579-116">En esta lección, aprenderá a iniciar la utilidad del símbolo del sistema **dta** y a ejecutar algunos comandos de optimización sencillos.</span><span class="sxs-lookup"><span data-stu-id="2f579-116">In this lesson, you learn how to start the **dta** command prompt utility and how to run some simple tuning commands.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f579-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f579-117">Requirements</span></span>  
 <span data-ttu-id="2f579-118">Este tutorial está destinado a los administradores de bases de datos que no están familiarizados con la GUI del Asistente para la optimización de motor de base de datos o la utilidad del símbolo del sistema **dta** , pero que tienen experiencia con las estructuras y los conceptos de bases de datos, como los índices y las vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="2f579-118">This tutorial is intended for database administrators who are not familiar with the Database Engine Tuning Advisor GUI or the **dta** command prompt utility, but who are experienced with database concepts and structures, such as indexes and indexed views.</span></span>  
  
 <span data-ttu-id="2f579-119">Debe instalar [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (o una versión posterior) con la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f579-119">You must install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (or a later version) with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="2f579-120">Con el objeto de mejorar la seguridad, las bases de datos de ejemplo no se instalan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2f579-120">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="2f579-121">Para instalarlas, consulte [Instalar ejemplos de SQL Server y bases de datos de ejemplo](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="2f579-121">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="after-you-finish-this-tutorial"></a><span data-ttu-id="2f579-122">Al finalizar este tutorial</span><span class="sxs-lookup"><span data-stu-id="2f579-122">After You Finish This Tutorial</span></span>  
 <span data-ttu-id="2f579-123">Cuando haya finalizado las lecciones de este tutorial, consulte los temas siguientes para obtener más información acerca del Asistente para la optimización de motor de base de datos:</span><span class="sxs-lookup"><span data-stu-id="2f579-123">After you finish the lessons in this tutorial, refer to the following topics for more information about Database Engine Tuning Advisor:</span></span>  
  
-   <span data-ttu-id="2f579-124">[Asistente para la optimización de motor de base de datos](../../relational-databases/performance/database-engine-tuning-advisor.md) para obtener descripciones sobre cómo realizar tareas con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="2f579-124">[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) for descriptions of how to perform tasks with this tool.</span></span>  
  
-   <span data-ttu-id="2f579-125">[dta (utilidad)](dta-utility.md) para obtener material de referencia sobre la utilidad de símbolo del sistema y el archivo XML opcional que puede usar para controlar el funcionamiento de la utilidad.</span><span class="sxs-lookup"><span data-stu-id="2f579-125">[dta Utility](dta-utility.md) for reference material on the command prompt utility and the optional XML file you can use to control the operation of the utility.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="2f579-126">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="2f579-126">Next Lesson</span></span>  
 [<span data-ttu-id="2f579-127">Lección 1: Navegación básica en el Asistente para la optimización de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f579-127">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
