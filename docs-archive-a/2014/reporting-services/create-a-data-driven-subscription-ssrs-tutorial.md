---
title: Crear una suscripción controlada por datos (Tutorial de SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], tutorials
- walkthroughs [Reporting Services]
- data-driven subscriptions
ms.assetid: 79ab0572-43e9-4dc4-9b5a-cd8b627b8274
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 53be7cf793d8fa38d177643c7f366115d4df8b7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747511"
---
# <a name="create-a-data-driven-subscription-ssrs-tutorial"></a><span data-ttu-id="7b35a-102">Crear una suscripción controlada por datos (Tutorial de SSRS)</span><span class="sxs-lookup"><span data-stu-id="7b35a-102">Create a Data-Driven Subscription (SSRS Tutorial)</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="7b35a-103">proporciona suscripciones controladas por datos para que pueda personalizar la distribución de un informe basándose en datos dinámicos de suscriptores.</span><span class="sxs-lookup"><span data-stu-id="7b35a-103">provides data-driven subscriptions so that you can customize the distribution of a report based on dynamic subscriber data.</span></span> <span data-ttu-id="7b35a-104">Las suscripciones controladas por datos están destinadas a los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b35a-104">Data-driven subscriptions are intended for the following kinds of scenarios:</span></span>  
  
-   <span data-ttu-id="7b35a-105">La distribución de informes a un grupo grande de destinatarios cuya pertenencia al grupo puede cambiar de una distribución a otra.</span><span class="sxs-lookup"><span data-stu-id="7b35a-105">Distributing reports to a large recipient pool whose membership may change from one distribution to the next.</span></span> <span data-ttu-id="7b35a-106">Por ejemplo, la distribución de un informe mensual a todos los clientes actuales.</span><span class="sxs-lookup"><span data-stu-id="7b35a-106">For example, distribute a monthly report to all current customers.</span></span>  
  
-   <span data-ttu-id="7b35a-107">La distribución de informes a un grupo específico de destinatarios basado en criterios predefinidos.</span><span class="sxs-lookup"><span data-stu-id="7b35a-107">Distributing reports to a specific group of recipients based on predefined criteria.</span></span> <span data-ttu-id="7b35a-108">Por ejemplo, el envío de un informe de rendimiento de ventas a los diez principales directores de ventas de la organización.</span><span class="sxs-lookup"><span data-stu-id="7b35a-108">For example, send a sales performance report to the top ten sales managers in an organization.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="7b35a-109">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="7b35a-109">What You Will Learn</span></span>  
 <span data-ttu-id="7b35a-110">En este tutorial se muestra cómo utilizar suscripciones controladas por datos mediante un sencillo ejemplo que ilustra los conceptos.</span><span class="sxs-lookup"><span data-stu-id="7b35a-110">This tutorial shows you how to use data-driven subscriptions using a simple example to illustrate the concepts.</span></span>  
  
 <span data-ttu-id="7b35a-111">El tutorial está compuesto por tres lecciones:</span><span class="sxs-lookup"><span data-stu-id="7b35a-111">This tutorial is divided into three lessons:</span></span>  
  
 [<span data-ttu-id="7b35a-112">Lección 1: Creación de una base de datos de suscriptor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b35a-112">Lesson 1: Creating a Sample Subscriber Database</span></span>](lesson-1-creating-a-sample-subscriber-database.md)  
 <span data-ttu-id="7b35a-113">En esta lección aprenderá a crear una base de datos local de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] con información de suscriptores.</span><span class="sxs-lookup"><span data-stu-id="7b35a-113">In this lesson you will learn how to create a local [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database that contains subscriber information.</span></span>  
  
 [<span data-ttu-id="7b35a-114">Lección 2: Modificación de las propiedades del origen de datos de informe</span><span class="sxs-lookup"><span data-stu-id="7b35a-114">Lesson 2: Modifying the Report Data Source Properties</span></span>](lesson-2-modifying-the-report-data-source-properties.md)  
 <span data-ttu-id="7b35a-115">En esta lección aprenderá a modificar propiedades del origen de datos de informe de manera que el informe pueda ejecutarse en modo desatendido.</span><span class="sxs-lookup"><span data-stu-id="7b35a-115">In this lesson, you will learn how to modify report data source properties so that the report can run unattended.</span></span> <span data-ttu-id="7b35a-116">El procesamiento desatendido requiere las credenciales almacenadas.</span><span class="sxs-lookup"><span data-stu-id="7b35a-116">Unattended processing requires stored credentials.</span></span> <span data-ttu-id="7b35a-117">Además, modificará el conjunto de datos de informe para que incluya un parámetro proporcionado por los datos del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="7b35a-117">You will also modify the report dataset to include a parameter that is supplied by the subscriber data.</span></span>  
  
 [<span data-ttu-id="7b35a-118">Lección 3: Definir una suscripción controlada por datos</span><span class="sxs-lookup"><span data-stu-id="7b35a-118">Lesson 3: Defining a Data-Driven Subscription</span></span>](lesson-3-defining-a-data-driven-subscription.md)  
 <span data-ttu-id="7b35a-119">En esta lección aprenderá a definir una suscripción controlada por datos.</span><span class="sxs-lookup"><span data-stu-id="7b35a-119">In this lesson you will learn how to define a data-driven subscription.</span></span> <span data-ttu-id="7b35a-120">Esta lección le guía a través de cada página del Asistente para suscripciones controladas por datos.</span><span class="sxs-lookup"><span data-stu-id="7b35a-120">This lesson guides you through each page in the Data-Driven Subscription Wizard.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b35a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b35a-121">Requirements</span></span>  
 <span data-ttu-id="7b35a-122">Normalmente, los administradores del servidor de informes se ocupan de crear y mantener las suscripciones controladas por datos.</span><span class="sxs-lookup"><span data-stu-id="7b35a-122">Data-driven subscriptions are typically created and maintained by report server administrators.</span></span> <span data-ttu-id="7b35a-123">La posibilidad de crear suscripciones controladas por datos requiere tener conocimientos de creación de consultas, estar familiarizado con los orígenes de datos que contienen datos de suscriptores y tener permisos superiores en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7b35a-123">The ability to create data-driven subscriptions requires expertise in building queries, knowledge of data sources that contain subscriber data, and elevated permissions on a report server.</span></span>  
  
 <span data-ttu-id="7b35a-124">En el tutorial se usará el informe creado en el tutorial [crear un informe de tabla básico &#40;tutorial de SSRS&#41;](create-a-basic-table-report-ssrs-tutorial.md) y datos de[!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b35a-124">The tutorial will use the report created in the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](create-a-basic-table-report-ssrs-tutorial.md) and data from [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]</span></span>  
  
 <span data-ttu-id="7b35a-125">Para usar este tutorial, debe tener el software siguiente instalado en el sistema:</span><span class="sxs-lookup"><span data-stu-id="7b35a-125">Your system must have the following installed to use this tutorial:</span></span>  
  
-   <span data-ttu-id="7b35a-126">Una edición de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que admita suscripciones controladas por datos.</span><span class="sxs-lookup"><span data-stu-id="7b35a-126">An edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that supports data-driven subscriptions.</span></span> <span data-ttu-id="7b35a-127">Para obtener más información, vea [ediciones y componentes de SQL Server 2014](../sql-server/editions-and-components-of-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="7b35a-127">For more information, see [Editions and Components of SQL Server 2014](../sql-server/editions-and-components-of-sql-server-2016.md).</span></span>  
  
-   <span data-ttu-id="7b35a-128">El servidor de informes debe ejecutarse en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="7b35a-128">The report server must be running in native mode.</span></span> <span data-ttu-id="7b35a-129">La interfaz de usuario descrita en este tutorial se basa en un servidor de informes en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="7b35a-129">The user interface described in this tutorial is based on a native mode report server.</span></span> <span data-ttu-id="7b35a-130">Las suscripciones se admiten en los servidores de informes de modo de SharePoint pero la interfaz de usuario será diferente a la que se describe en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="7b35a-130">Subscriptions are supported on SharePoint mode report servers but the user interface will be different than what is described in this tutorial.</span></span>  
  
-   <span data-ttu-id="7b35a-131">Se debe ejecutar el servicio del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7b35a-131">SQL Server Agent service must be running.</span></span>  
  
-   <span data-ttu-id="7b35a-132">Un informe que contenga parámetros.</span><span class="sxs-lookup"><span data-stu-id="7b35a-132">A report that includes parameters.</span></span> <span data-ttu-id="7b35a-133">En este tutorial, se supone que usa el informe de ejemplo `Sales Orders` que creó con el tutorial [Crear un informe de tabla básico &#40;Tutorial de SSRS&#41;](create-a-basic-table-report-ssrs-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="7b35a-133">This tutorial assumes the sample report, `Sales Orders` you create using the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](create-a-basic-table-report-ssrs-tutorial.md).</span></span>  
  
-   <span data-ttu-id="7b35a-134">La base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)], que proporciona datos para el informe de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7b35a-134">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database, which provides data to the sample report.</span></span>  
  
-   <span data-ttu-id="7b35a-135">Una asignación de roles que incluye la tarea Administrar todas las suscripciones en el informe de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7b35a-135">A role assignment that includes the Manage all subscriptions task on the sample report.</span></span> <span data-ttu-id="7b35a-136">Esta tarea es necesaria para definir una suscripción controlada por datos.</span><span class="sxs-lookup"><span data-stu-id="7b35a-136">This task is required for defining a data-driven subscription.</span></span> <span data-ttu-id="7b35a-137">Si es administrador del equipo, la asignación de roles predeterminada para los administradores locales le proporciona los permisos necesarios para crear suscripciones controladas por datos.</span><span class="sxs-lookup"><span data-stu-id="7b35a-137">If you are an administrator on the computer, the default role assignment for local administrators provides the permissions necessary for creating data-driven subscriptions.</span></span> <span data-ttu-id="7b35a-138">Para obtener más información, consulte [Conceder permisos en un servidor de informes en modo nativo](security/granting-permissions-on-a-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="7b35a-138">For more information, see [Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md).</span></span>  
  
-   <span data-ttu-id="7b35a-139">Una carpeta compartida para la que tenga permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="7b35a-139">A shared folder for which you have write permissions.</span></span> <span data-ttu-id="7b35a-140">La carpeta compartida debe estar accesible a través de una conexión de red.</span><span class="sxs-lookup"><span data-stu-id="7b35a-140">The shared folder must be accessible over a network connection.</span></span>  
  
 <span data-ttu-id="7b35a-141">**Tiempo estimado para completar este tutorial:** 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="7b35a-141">**Estimated time to complete the tutorial:** 30 minutes.</span></span> <span data-ttu-id="7b35a-142">Otros 30 minutos si no ha completado el tutorial de informe básico.</span><span class="sxs-lookup"><span data-stu-id="7b35a-142">An additional 30 minutes if you have not completed the basic report tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b35a-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b35a-143">See Also</span></span>  
 <span data-ttu-id="7b35a-144">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="7b35a-144">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span></span>  
 [<span data-ttu-id="7b35a-145">Crear un informe de tabla básico &#40;Tutorial de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7b35a-145">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
