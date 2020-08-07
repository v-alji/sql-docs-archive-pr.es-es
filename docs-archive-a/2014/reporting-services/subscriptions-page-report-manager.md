---
title: Página suscripciones (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cf3a6bd0-e0b2-4875-a532-63ef34cfa860
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c67895babe99c92b7c09afd8cb75ca88d5cd7553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747422"
---
# <a name="subscriptions-page-report-manager"></a><span data-ttu-id="3e192-102">Suscripciones (página del Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="3e192-102">Subscriptions Page (Report Manager)</span></span>
  <span data-ttu-id="3e192-103">Use la página Suscripciones para mostrar todas las suscripciones del informe u origen de datos compartido actual.</span><span class="sxs-lookup"><span data-stu-id="3e192-103">Use the Subscriptions page to list all of the subscriptions for the current report or shared data source.</span></span> <span data-ttu-id="3e192-104">Si tiene permisos suficientes, concedidos por la tarea "Administrar todas las suscripciones", puede ver las suscripciones de todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3e192-104">If you have sufficient permission (as conveyed by the "Manage all subscriptions" task), you can view the subscriptions of all users.</span></span> <span data-ttu-id="3e192-105">En caso contrario, esta página solo muestra las suscripciones que le pertenecen.</span><span class="sxs-lookup"><span data-stu-id="3e192-105">Otherwise, this page shows only the subscriptions that you own.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e192-106">Otras páginas contienen también información acerca de las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="3e192-106">Other pages also contain subscription information.</span></span> <span data-ttu-id="3e192-107">Para obtener más información, consulte la [página Mis suscripciones &#40;Administrador de informes&#41;](../../2014/reporting-services/my-subscriptions-page-report-manager.md) para tener acceso a todas las suscripciones en un solo lugar o la [página nueva suscripción o editar suscripción &#40;administrador de informes&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md) para crear o editar una suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-107">For more information, see [My Subscriptions Page &#40;Report Manager&#41;](../../2014/reporting-services/my-subscriptions-page-report-manager.md) to access all your subscriptions in one place or the [New Subscription or Edit Subscription Page &#40;Report Manager&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md) to create or edit a subscription.</span></span>  
  
 <span data-ttu-id="3e192-108">Algunas opciones solo se mostrarán si hay suscripciones con las que trabajar.</span><span class="sxs-lookup"><span data-stu-id="3e192-108">Some options are visible only if there are existing subscriptions to work with.</span></span> <span data-ttu-id="3e192-109">Si no se han definido suscripciones y ha obtenido acceso a esta página desde un informe, las únicas opciones de la página serán **Nueva suscripción** y **Nueva suscripción controlada por datos** .</span><span class="sxs-lookup"><span data-stu-id="3e192-109">If no subscriptions are defined and you are accessing this page from a report, the **New Subscription** and **New Data-Driven Subscription** are the only options on the page.</span></span>  
  
 <span data-ttu-id="3e192-110">Para poder crear una suscripción nueva, debe comprobar primero si el origen de datos de informe usa credenciales almacenadas.</span><span class="sxs-lookup"><span data-stu-id="3e192-110">Before you can create a new subscription, you must verify that the report data source uses stored credentials.</span></span> <span data-ttu-id="3e192-111">Use la página de propiedades Orígenes de datos para almacenar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="3e192-111">Use the Data Sources properties page to store credentials.</span></span> <span data-ttu-id="3e192-112">Para obtener más información, vea [Página de propiedades orígenes de datos &#40;Administrador de informes&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="3e192-112">For more information, see [Data Sources Properties Page &#40;Report Manager&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e192-113">Esta característica no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e192-113">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3e192-114">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="3e192-114">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="3e192-115">Navegación</span><span class="sxs-lookup"><span data-stu-id="3e192-115">Navigation</span></span>  
 <span data-ttu-id="3e192-116">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="3e192-116">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-subscriptions-page-for-report"></a><span data-ttu-id="3e192-117">Para abrir la página Suscripciones para el informe</span><span class="sxs-lookup"><span data-stu-id="3e192-117">To open the Subscriptions page for report</span></span>  
  
1.  <span data-ttu-id="3e192-118">Abra el Administrador de informes y busque el informe del que desea ver o configurar una suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-118">Open Report Manager, and locate the report for which you want to view or configure a subscription.</span></span>  
  
2.  <span data-ttu-id="3e192-119">Mantenga el mouse sobre el informe y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3e192-119">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="3e192-120">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="3e192-120">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="3e192-121">Se abrirá la página de propiedades General correspondiente al informe.</span><span class="sxs-lookup"><span data-stu-id="3e192-121">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="3e192-122">Seleccione la pestaña **Suscripciones** .</span><span class="sxs-lookup"><span data-stu-id="3e192-122">Select the **Subscriptions** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3e192-123">Opciones</span><span class="sxs-lookup"><span data-stu-id="3e192-123">Options</span></span>  
 <span data-ttu-id="3e192-124">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="3e192-124">**Delete**</span></span>  
 <span data-ttu-id="3e192-125">Haga clic para eliminar una suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-125">Click to delete a subscription.</span></span> <span data-ttu-id="3e192-126">Para poder eliminar suscripciones, debe activar la casilla situada junto a cada suscripción que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="3e192-126">Before you can delete a subscription, select the check box next to each subscription that you want to delete.</span></span>  
  
 <span data-ttu-id="3e192-127">**Nueva suscripción**</span><span class="sxs-lookup"><span data-stu-id="3e192-127">**New Subscription**</span></span>  
 <span data-ttu-id="3e192-128">Haga clic para crear una nueva suscripción al informe actual.</span><span class="sxs-lookup"><span data-stu-id="3e192-128">Click to create a new subscription to the current report.</span></span> <span data-ttu-id="3e192-129">Este botón se habilita si el informe no usa credenciales o usa credenciales almacenadas.</span><span class="sxs-lookup"><span data-stu-id="3e192-129">This button is enabled when the report uses stored credentials or no credentials.</span></span> <span data-ttu-id="3e192-130">No está disponible si abre la página Suscripciones para un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="3e192-130">This button is not available when you open the Subscriptions page for a shared data source.</span></span>  
  
 <span data-ttu-id="3e192-131">**Nueva suscripción controlada por datos**</span><span class="sxs-lookup"><span data-stu-id="3e192-131">**New Data-Driven Subscription**</span></span>  
 <span data-ttu-id="3e192-132">Haga clic para generar una lista de suscriptores y opciones de entrega ejecutando un comando o una consulta en un almacén de datos que contenga esa información.</span><span class="sxs-lookup"><span data-stu-id="3e192-132">Click to generate a subscriber list and delivery options from a command or query against a data store that contains this information.</span></span> <span data-ttu-id="3e192-133">Este botón se habilita si el informe no usa credenciales o usa credenciales almacenadas.</span><span class="sxs-lookup"><span data-stu-id="3e192-133">This button is enabled when the report uses stored credentials or no credentials.</span></span> <span data-ttu-id="3e192-134">No está disponible si abre la página Suscripciones para un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="3e192-134">This button is not available when you open the Subscriptions page for a shared data source.</span></span>  
  
 <span data-ttu-id="3e192-135">**Edición**</span><span class="sxs-lookup"><span data-stu-id="3e192-135">**Edit**</span></span>  
 <span data-ttu-id="3e192-136">Haga clic para ver o editar la descripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-136">Click to view or edit the description.</span></span>  
  
 <span data-ttu-id="3e192-137">**Report**</span><span class="sxs-lookup"><span data-stu-id="3e192-137">**Report**</span></span>  
 <span data-ttu-id="3e192-138">Cuando se abre esta página desde un origen de datos compartido, esta columna identifica el informe para el que se ha definido la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-138">When you open this page from a shared data source, this column identifies the report for which the subscription is defined.</span></span> <span data-ttu-id="3e192-139">La columna **Carpeta** identifica la ubicación del informe.</span><span class="sxs-lookup"><span data-stu-id="3e192-139">The **Folder** column identifies the location of the report.</span></span>  
  
 <span data-ttu-id="3e192-140">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3e192-140">**Description**</span></span>  
 <span data-ttu-id="3e192-141">Muestra una descripción de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-141">Shows a description of the subscription.</span></span>  
  
 <span data-ttu-id="3e192-142">**Desencadenador**</span><span class="sxs-lookup"><span data-stu-id="3e192-142">**Trigger**</span></span>  
 <span data-ttu-id="3e192-143">Identifica los criterios que hacen que se ejecute la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-143">Identifies criteria that cause the subscription to run.</span></span> <span data-ttu-id="3e192-144">El desencadenador **TimedSubscription** se basa en una programación que define cuándo se ejecuta la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-144">A **TimedSubscription** trigger is based on a schedule that defines when the subscription runs.</span></span> <span data-ttu-id="3e192-145">El desencadenador **SnapshotUpdated** se basa en la actualización de una instantánea de informe.</span><span class="sxs-lookup"><span data-stu-id="3e192-145">A **SnapshotUpdated** trigger is based on an update to a report snapshot.</span></span>  
  
 <span data-ttu-id="3e192-146">**Propietario**</span><span class="sxs-lookup"><span data-stu-id="3e192-146">**Owner**</span></span>  
 <span data-ttu-id="3e192-147">Muestra el nombre del usuario que creó la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-147">Shows the name of the user who created the subscription.</span></span>  
  
 <span data-ttu-id="3e192-148">**Última ejecución**</span><span class="sxs-lookup"><span data-stu-id="3e192-148">**Last Run**</span></span>  
 <span data-ttu-id="3e192-149">Muestra la última vez que se procesó la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-149">Shows the last time that the subscription was processed.</span></span>  
  
 <span data-ttu-id="3e192-150">**Estado**</span><span class="sxs-lookup"><span data-stu-id="3e192-150">**Status**</span></span>  
 <span data-ttu-id="3e192-151">Muestra el estado de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-151">Shows the status of the subscription.</span></span> <span data-ttu-id="3e192-152">Por lo general, el valor de estado es Nuevo o la fecha y hora en la que se ejecutó por última vez la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e192-152">Usually, the status value is either New or the date and time at which the subscription last ran.</span></span>  
  
 <span data-ttu-id="3e192-153">El valor de estado "Datos no válidos" se produce cuando la suscripción incluye un puntero para valores cifrados que ya no son válidos (es decir, a las credenciales almacenadas utilizadas para ejecutar el informe).</span><span class="sxs-lookup"><span data-stu-id="3e192-153">A status value of "Bad Data" occurs when the subscription includes a pointer to encrypted values that are no longer valid (that is, to the stored credentials used to run the report).</span></span> <span data-ttu-id="3e192-154">Los valores cifrados existentes se convierten en inutilizables cuando se vuelven a crear las claves simétricas utilizadas para cifrar y descifrar datos en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="3e192-154">Existing encrypted values become unusable when the symmetric keys used to encrypt and decrypt data are recreated on the report server.</span></span>  
  
 <span data-ttu-id="3e192-155">No se puede procesar una suscripción si se ha desactivado.</span><span class="sxs-lookup"><span data-stu-id="3e192-155">A subscription cannot be processed if it has been deactivated.</span></span> <span data-ttu-id="3e192-156">Para actualizar la suscripción y hacer que sea operativa, ábrala y guárdela.</span><span class="sxs-lookup"><span data-stu-id="3e192-156">To update the subscription and make it operational, open and then save the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e192-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e192-157">See Also</span></span>  
 <span data-ttu-id="3e192-158">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="3e192-158">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="3e192-159">[Crear, modificar y eliminar suscripciones estándar &#40;Reporting Services en modo nativo&#41;](subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md) </span><span class="sxs-lookup"><span data-stu-id="3e192-159">[Create, Modify, and Delete Standard Subscriptions &#40;Reporting Services in Native Mode&#41;](subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md) </span></span>  
 <span data-ttu-id="3e192-160">[Crear, modificar y eliminar programaciones](subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="3e192-160">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="3e192-161">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="3e192-161">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
