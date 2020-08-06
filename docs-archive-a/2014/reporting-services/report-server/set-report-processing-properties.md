---
title: Establecer las propiedades del procesamiento de informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- on-demand reports
- report processing [Reporting Services], execution properties
- snapshots [Reporting Services], running reports from
- cached reports [Reporting Services]
- report snapshots [Reporting Services], running reports from
- report execution snapshots [Reporting Services]
ms.assetid: b5cbc453-5986-423e-af44-1f243ef3edb1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f47c70a4bfd7aa5fe0c711532542baa7a51ccbbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672628"
---
# <a name="set-report-processing-properties"></a><span data-ttu-id="ed697-102">Establecer las propiedades del procesamiento de informes</span><span class="sxs-lookup"><span data-stu-id="ed697-102">Set Report Processing Properties</span></span>
  <span data-ttu-id="ed697-103">Las propiedades de ejecución del informe controlan el modo en que se procesa un informe.</span><span class="sxs-lookup"><span data-stu-id="ed697-103">Report execution properties control how a report is processed.</span></span> <span data-ttu-id="ed697-104">Estas propiedades deben establecerse de forma individual para cada uno de los informes.</span><span class="sxs-lookup"><span data-stu-id="ed697-104">Execution properties must be set for each report individually.</span></span>  
  
 <span data-ttu-id="ed697-105">Para establecer las propiedades de ejecución, abra el informe en el Administrador de informes y navegue a la página de propiedades Ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed697-105">To set report execution properties, open the report in Report Manager, and then navigate to the Execution properties page.</span></span> <span data-ttu-id="ed697-106">También puede establecer las propiedades mediante [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed697-106">You can also set properties using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="ed697-107">Para más información, vea [Página de propiedades Opciones de procesamiento &#40;Administrador de informes&#41;](../processing-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ed697-107">For more information, see [Processing Options Properties Page &#40;Report Manager&#41;](../processing-options-properties-page-report-manager.md).</span></span>  
  
## <a name="report-execution-modes"></a><span data-ttu-id="ed697-108">Modos de ejecución del informe</span><span class="sxs-lookup"><span data-stu-id="ed697-108">Report Execution Modes</span></span>  
 <span data-ttu-id="ed697-109">Los informes pueden ejecutarse a petición o como una instantánea.</span><span class="sxs-lookup"><span data-stu-id="ed697-109">You can run a report either on demand or as a snapshot.</span></span> <span data-ttu-id="ed697-110">La siguiente sección describe cada una de estas opciones.</span><span class="sxs-lookup"><span data-stu-id="ed697-110">The following section describes each approach.</span></span>  
  
### <a name="running-reports-on-demand"></a><span data-ttu-id="ed697-111">Ejecutar informes a petición</span><span class="sxs-lookup"><span data-stu-id="ed697-111">Running Reports On Demand</span></span>  
 <span data-ttu-id="ed697-112">Puede especificar que un informe consulte un origen de datos cada vez que un usuario ejecute el informe, lo cual da lugar a informes a petición que contienen los datos más actualizados.</span><span class="sxs-lookup"><span data-stu-id="ed697-112">You can specify that a report query a data source each time a user runs the report, resulting in on-demand reports that contain the most up-to-date data.</span></span> <span data-ttu-id="ed697-113">Por cada usuario que abre o solicita el informe se crea una instancia del informe; cada nueva instancia contiene los resultados de una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="ed697-113">A new instance of the report is created for each user who opens or requests the report; each new instance contains the results of a new query.</span></span> <span data-ttu-id="ed697-114">Cuando se usa esta opción, si diez usuarios abren el informe a la vez, se enviarán diez consultas para procesar al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ed697-114">With this approach, if ten users open the report at the same time, ten queries are sent to the data source for processing.</span></span>  
  
### <a name="running-reports-on-demand-from-cache"></a><span data-ttu-id="ed697-115">Ejecutar informes a petición desde la caché</span><span class="sxs-lookup"><span data-stu-id="ed697-115">Running Reports On Demand From Cache</span></span>  
 <span data-ttu-id="ed697-116">Para mejorar el rendimiento puede especificar que un informe (y sus datos) se almacene temporalmente en caché mientras un usuario lo esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="ed697-116">To enhance performance, you can specify a report (and data) to be cached temporarily when a user runs the report.</span></span> <span data-ttu-id="ed697-117">La copia en caché estará disponible posteriormente para otros usuarios que tengan acceso al mismo informe.</span><span class="sxs-lookup"><span data-stu-id="ed697-117">The cached copy is subsequently available to other users who access the same report.</span></span> <span data-ttu-id="ed697-118">Con esta opción, si diez usuarios abren el informe, solamente la primera solicitud dará lugar al procesamiento del informe.</span><span class="sxs-lookup"><span data-stu-id="ed697-118">With this approach, if ten users open the report, only the first request results in report processing.</span></span> <span data-ttu-id="ed697-119">El informe se almacena posteriormente en caché y los nueve usuarios restantes ven el informe almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="ed697-119">The report is subsequently cached, and the remaining nine users view the cached report.</span></span>  
  
 <span data-ttu-id="ed697-120">Los informes en caché se eliminan a intervalos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ed697-120">Cached reports are removed from the cache at intervals that you define.</span></span> <span data-ttu-id="ed697-121">Estos intervalos pueden especificarse en minutos o se puede programar una fecha y hora específicas para vaciar la caché.</span><span class="sxs-lookup"><span data-stu-id="ed697-121">You can specify intervals in minutes, or you can schedule a specific date and time to empty the cache.</span></span> <span data-ttu-id="ed697-122">Para más información, vea [Informes almacenados en caché &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ed697-122">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="running-reports-from-snapshots"></a><span data-ttu-id="ed697-123">Ejecutar informes desde instantáneas</span><span class="sxs-lookup"><span data-stu-id="ed697-123">Running Reports From Snapshots</span></span>  
 <span data-ttu-id="ed697-124">Una instantánea de informe es un informe que contiene información de diseño y datos que se recuperan en un momento concreto.</span><span class="sxs-lookup"><span data-stu-id="ed697-124">A report snapshot is a report that contains layout information and data that is retrieved at a specific point in time.</span></span> <span data-ttu-id="ed697-125">Los informes pueden ejecutarse como una instantánea de informe si se desea evitar que el informe se ejecute de forma arbitraria (durante una copia de seguridad programada, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="ed697-125">You can run a report as a report snapshot to prevent the report from being run at arbitrary times (for example, during a scheduled backup).</span></span> <span data-ttu-id="ed697-126">Una instantánea de informe suele crearse y actualizarse posteriormente según una programación, lo que permite controlar con exactitud el momento en que se producirá el procesamiento del informe y los datos.</span><span class="sxs-lookup"><span data-stu-id="ed697-126">A report snapshot is usually created and subsequently refreshed on a schedule, allowing you to time exactly when report and data processing will occur.</span></span> <span data-ttu-id="ed697-127">Si un informe se basa en consultas que tardan demasiado en ejecutarse o en consultas que usan datos desde un origen de datos al que prefiere que nadie tenga acceso durante determinadas horas, debe ejecutar el informe como instantánea.</span><span class="sxs-lookup"><span data-stu-id="ed697-127">If a report is based on queries that take a long time to run, or on queries that use data from a data source that you prefer no one access during certain hours, you should run the report as a snapshot.</span></span>  
  
 <span data-ttu-id="ed697-128">Las instantáneas de informe se almacenan en una base de datos del servidor de informes, de donde se recuperan posteriormente cada vez que un usuario o un proceso (como una suscripción) solicita el informe.</span><span class="sxs-lookup"><span data-stu-id="ed697-128">A report snapshot is stored in a report server database, where it is subsequently retrieved when a user or process (such as a subscription) requests the report.</span></span> <span data-ttu-id="ed697-129">Las instantáneas de informe se sobrescriben con una nueva instancia cada vez que se actualizan.</span><span class="sxs-lookup"><span data-stu-id="ed697-129">When a report snapshot is updated, it is overwritten with a new instance.</span></span> <span data-ttu-id="ed697-130">El servidor de informes no guarda las versiones anteriores de una instantánea de informe salvo que se establezcan específicamente opciones para agregarla al historial del informe.</span><span class="sxs-lookup"><span data-stu-id="ed697-130">The report server does not save earlier versions of a report snapshot unless you specifically set options to add it to report history.</span></span> <span data-ttu-id="ed697-131">Para obtener más información, vea [Crear, modificar y eliminar instantáneas del historial de informes](create-modify-and-delete-snapshots-in-report-history.md).</span><span class="sxs-lookup"><span data-stu-id="ed697-131">For more information, see [Create, Modify, and Delete Snapshots in Report History](create-modify-and-delete-snapshots-in-report-history.md).</span></span>  
  
 <span data-ttu-id="ed697-132">No todos los informes pueden configurarse para ejecutarse como una instantánea.</span><span class="sxs-lookup"><span data-stu-id="ed697-132">Not all reports can be configured to run as a snapshot.</span></span> <span data-ttu-id="ed697-133">No puede crear una instantánea para un informe que solicita credenciales a los usuarios o usa seguridad integrada de Windows para obtener datos para el informe.</span><span class="sxs-lookup"><span data-stu-id="ed697-133">You cannot create a snapshot for a report that prompts users for credentials or uses Windows integrated security to get data for the report.</span></span> <span data-ttu-id="ed697-134">Si desea ejecutar un informe con parámetros como instantánea, debe especificar un parámetro predeterminado que se use al crear la instantánea.</span><span class="sxs-lookup"><span data-stu-id="ed697-134">If you want to run a parameterized report as a snapshot, you must specify a default parameter to use when creating the snapshot.</span></span> <span data-ttu-id="ed697-135">A diferencia de los informes que se ejecutan a petición, no es posible especificar un valor de parámetro diferente para una instantánea de informe cuando se abre el informe.</span><span class="sxs-lookup"><span data-stu-id="ed697-135">In contrast with reports that run on demand, it is not possible to specify a different parameter value for a report snapshot when the report is open.</span></span> <span data-ttu-id="ed697-136">La elección de un valor de parámetro diferente dará como resultado una nueva solicitud de procesamiento de informe, lo cual no está permitido.</span><span class="sxs-lookup"><span data-stu-id="ed697-136">Choosing a different parameter value would result in a new report processing request, which is not allowed.</span></span>  
  
 <span data-ttu-id="ed697-137">En algunos casos, la configuración de un informe a petición para ejecutar una instantánea puede desactivar suscripciones.</span><span class="sxs-lookup"><span data-stu-id="ed697-137">In some cases, configuring an on-demand report to run as a snapshot can deactivate subscriptions.</span></span> <span data-ttu-id="ed697-138">La siguiente condición hará que un servidor de informes desactive suscripciones existentes que se definieron cuando se configuró el informe para que se ejecute a petición:</span><span class="sxs-lookup"><span data-stu-id="ed697-138">The following condition will cause a report server to deactivate existing subscriptions that were defined when the report was configured to run on demand:</span></span>  
  
-   <span data-ttu-id="ed697-139">El informe usa parámetros de consulta y se selecciona un valor específico como parámetro predeterminado a fin de cumplir con los requisitos para ejecutar el informe como instantánea.</span><span class="sxs-lookup"><span data-stu-id="ed697-139">The report uses query parameters, and you select a specific value as the default parameter to meet the requirements for running the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="ed697-140">Las suscripciones existentes se configuran para usar valores de parámetro distintos del valor de parámetro predeterminado que se especificó para la instantánea.</span><span class="sxs-lookup"><span data-stu-id="ed697-140">Existing subscriptions are configured to use parameter values that differ from the default parameter value that you specified for the snapshot.</span></span>  
  
 <span data-ttu-id="ed697-141">Cuando se cumpla esta condición, el servidor de informes deshabilitará la suscripción la próxima vez que esté programada su ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed697-141">When this condition exists, the report server will disable the subscription the next time the subscription is scheduled to run.</span></span> <span data-ttu-id="ed697-142">Para volver a activarla, abra y guarde la suscripción.</span><span class="sxs-lookup"><span data-stu-id="ed697-142">To reactivate the subscription, open and then save the subscription.</span></span> <span data-ttu-id="ed697-143">Al abrir la suscripción, el servidor de informes actualiza los valores de parámetro de la suscripción con los valores especificados para la instantánea.</span><span class="sxs-lookup"><span data-stu-id="ed697-143">When you open the subscription, the report server updates the subscription parameter values to those specified for the snapshot.</span></span> <span data-ttu-id="ed697-144">Para más información sobre las suscripciones, vea [Suscripciones y entrega &#40;Reporting Services&#41;](../subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ed697-144">For more information about subscriptions, see [Subscriptions and Delivery &#40;Reporting Services&#41;](../subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed697-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed697-145">See Also</span></span>  
 <span data-ttu-id="ed697-146">[Establecer opciones de procesamiento &#40;Reporting Services en el modo integrado de SharePoint&#41;](../set-processing-options-reporting-services-in-sharepoint-integrated-mode.md) </span><span class="sxs-lookup"><span data-stu-id="ed697-146">[Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;](../set-processing-options-reporting-services-in-sharepoint-integrated-mode.md) </span></span>  
 <span data-ttu-id="ed697-147">[Configurar las propiedades de ejecución de un informe &#40;Administrador de informes&#41;](../reports/configure-execution-properties-for-a-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ed697-147">[Configure Execution Properties for a Report  &#40;Report Manager&#41;](../reports/configure-execution-properties-for-a-report-report-manager.md) </span></span>  
 <span data-ttu-id="ed697-148">[Conceptos de Reporting Services &#40;SSRS&#41;](../reporting-services-concepts-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ed697-148">[Reporting Services Concepts &#40;SSRS&#41;](../reporting-services-concepts-ssrs.md) </span></span>  
 <span data-ttu-id="ed697-149">[Cómo: agregar una instantánea al historial de informes](add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ed697-149">[How to: Add a Snapshot to Report History](add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 [<span data-ttu-id="ed697-150">Especificación de información de credenciales y conexión para los orígenes de datos de informes</span><span class="sxs-lookup"><span data-stu-id="ed697-150">Specify Credential and Connection Information for Report Data Sources</span></span>](../report-data/specify-credential-and-connection-information-for-report-data-sources.md)  
  
  