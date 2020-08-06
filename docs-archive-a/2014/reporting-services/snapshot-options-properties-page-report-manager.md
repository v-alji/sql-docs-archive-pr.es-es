---
title: Página de propiedades opciones de instantánea (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f6641f59-5267-4f57-8957-63b93d1a9679
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3025b23dfe498a92c2ce1d8535229d8d23dfd429
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744464"
---
# <a name="snapshot-options-properties-page-report-manager"></a><span data-ttu-id="6233b-102">Página de propiedades de opciones de instantánea (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="6233b-102">Snapshot Options Properties Page (Report Manager)</span></span>
  <span data-ttu-id="6233b-103">Use la página de propiedades Opciones de instantánea para programar las instantáneas de informe que se van a agregar al historial del informe, y para establecer los límites del número de ellas que se almacenarán en el historial.</span><span class="sxs-lookup"><span data-stu-id="6233b-103">Use the Snapshot Options properties page to schedule report snapshots to be added to report history, and to set limits on the number of report snapshots that are stored in report history.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6233b-104">Esta característica no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6233b-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6233b-105">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vea [servicios de base de datos adicionales](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md#Add_DBServices).</span><span class="sxs-lookup"><span data-stu-id="6233b-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Additional Database Services](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md#Add_DBServices).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="6233b-106">Navegación</span><span class="sxs-lookup"><span data-stu-id="6233b-106">Navigation</span></span>  
 <span data-ttu-id="6233b-107">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="6233b-107">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-snapshot-options-properties-page-for-a-report"></a><span data-ttu-id="6233b-108">Para abrir la página de propiedades Opciones de instantánea de un informe</span><span class="sxs-lookup"><span data-stu-id="6233b-108">To open the Snapshot Options properties page for a report</span></span>  
  
1.  <span data-ttu-id="6233b-109">Abra el Administrador de informes y busque el informe para el que desea configurar las propiedades de la instantánea de informe.</span><span class="sxs-lookup"><span data-stu-id="6233b-109">Open Report Manager, and locate the report for which you want to configure report snapshot properties.</span></span>  
  
2.  <span data-ttu-id="6233b-110">Mantenga el mouse sobre el informe y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6233b-110">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="6233b-111">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="6233b-111">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="6233b-112">Se abrirá la página de propiedades General correspondiente al informe.</span><span class="sxs-lookup"><span data-stu-id="6233b-112">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="6233b-113">Seleccione la pestaña **Opciones de instantánea** .</span><span class="sxs-lookup"><span data-stu-id="6233b-113">Select the **Snapshot Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6233b-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="6233b-114">Options</span></span>  
 <span data-ttu-id="6233b-115">**Permitir que el historial de informe se cree manualmente**</span><span class="sxs-lookup"><span data-stu-id="6233b-115">**Allow report history to be created manually**</span></span>  
 <span data-ttu-id="6233b-116">Active esta casilla para agregar instantáneas a un historial de informe según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6233b-116">Select this check box to add snapshots to report history as needed.</span></span> <span data-ttu-id="6233b-117">Al activarla, aparece el botón **Nueva instantánea** en la página Historial.</span><span class="sxs-lookup"><span data-stu-id="6233b-117">Selecting this check box causes the **New Snapshot** button to appear on the History page.</span></span>  
  
 <span data-ttu-id="6233b-118">**Almacenar todas las instantáneas de ejecución de informes en el historial**</span><span class="sxs-lookup"><span data-stu-id="6233b-118">**Store all report execution snapshots in report history**</span></span>  
 <span data-ttu-id="6233b-119">Active esta casilla para copiar en el historial de un informe una instantánea del informe generada según las propiedades de ejecución del informe.</span><span class="sxs-lookup"><span data-stu-id="6233b-119">Select this check box to copy a report snapshot that you generate based on report execution properties to report history.</span></span> <span data-ttu-id="6233b-120">Puede establecer las propiedades de ejecución de informes para ejecutar un informe a partir de una instantánea generada.</span><span class="sxs-lookup"><span data-stu-id="6233b-120">You can set report execution properties to run a report from a generated snapshot.</span></span> <span data-ttu-id="6233b-121">Al establecer esta propiedad del historial del informe, se puede mantener un registro de todas las instantáneas del informe generadas con el tiempo, colocando copias de las mismas en el historial.</span><span class="sxs-lookup"><span data-stu-id="6233b-121">By setting this report history property, you can keep a record of all reports snapshots that are generated over time by placing copies of them in report history.</span></span>  
  
 <span data-ttu-id="6233b-122">**Utilizar la siguiente programación para agregar instantáneas al historial de informe**</span><span class="sxs-lookup"><span data-stu-id="6233b-122">**Use the following schedule to add snapshots to report history**</span></span>  
 <span data-ttu-id="6233b-123">Active esta casilla para agregar instantáneas al historial de un informe según una programación.</span><span class="sxs-lookup"><span data-stu-id="6233b-123">Select this check box to add snapshots to report history on a scheduled basis.</span></span> <span data-ttu-id="6233b-124">Puede crear una programación exclusivamente con esta finalidad o seleccionar una programación compartida predefinida, si alguna contiene la información de programación que desea.</span><span class="sxs-lookup"><span data-stu-id="6233b-124">You can create a schedule that is used exclusively for this purpose, or you can select a predefined shared schedule if one contains the schedule information you want.</span></span>  
  
 <span data-ttu-id="6233b-125">**Seleccione el número de instantáneas que desea mantener**</span><span class="sxs-lookup"><span data-stu-id="6233b-125">**Select the number of snapshots to keep**</span></span>  
 <span data-ttu-id="6233b-126">Seleccione alguna de las opciones siguientes para controlar el número de informes que desea guardar en el historial.</span><span class="sxs-lookup"><span data-stu-id="6233b-126">Select from the following options to control the number of reports that are kept in report history.</span></span> <span data-ttu-id="6233b-127">La configuración de historial de informe puede variar para cada informe.</span><span class="sxs-lookup"><span data-stu-id="6233b-127">Report history settings can vary for each report.</span></span>  
  
-   <span data-ttu-id="6233b-128">Seleccione **Usar configuración predeterminada** para conservar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6233b-128">Select **Use default setting** to retain the default setting.</span></span> <span data-ttu-id="6233b-129">El administrador del servidor de informes controla una configuración maestra para el almacenamiento de historial de informe.</span><span class="sxs-lookup"><span data-stu-id="6233b-129">The report server administrator controls a master setting for report history storage.</span></span> <span data-ttu-id="6233b-130">Si elige esta opción, el número de instantáneas guardadas se obtiene de esta configuración maestra.</span><span class="sxs-lookup"><span data-stu-id="6233b-130">If you choose this option, the number of snapshots that are retained is obtained from this master setting.</span></span>  
  
-   <span data-ttu-id="6233b-131">Seleccione **Conservar un número ilimitado de instantáneas en el historial de informe** para guardar todas las instantáneas del historial de informe.</span><span class="sxs-lookup"><span data-stu-id="6233b-131">Select **Keep an unlimited number of snapshots in report history** to retain all report history snapshots.</span></span> <span data-ttu-id="6233b-132">Para reducir el tamaño del historial de informe, debe eliminar las instantáneas manualmente.</span><span class="sxs-lookup"><span data-stu-id="6233b-132">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
-   <span data-ttu-id="6233b-133">Seleccione **Limitar las copias del historial de informe** para guardar un número determinado de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="6233b-133">Select **Limit the copies of report history** to retain a set number of snapshots.</span></span> <span data-ttu-id="6233b-134">Cuando se alcanza el límite, las copias más antiguas se eliminan del historial de informe para dejar sitio para las nuevas.</span><span class="sxs-lookup"><span data-stu-id="6233b-134">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="6233b-135">El historial de informes está almacenado en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6233b-135">Report history is stored in the report server database.</span></span> <span data-ttu-id="6233b-136">Si tiene informes grandes o numerosos informes para los que desea mantener el historial, piense en limitar la cantidad del historial del informe para ayudar a administrar las necesidades de espacio en disco de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6233b-136">If you have large reports or numerous reports for which you want to maintain history, consider limiting the amount of report history to help manage the disk space requirements of the report server database.</span></span>  
  
 <span data-ttu-id="6233b-137">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="6233b-137">**Apply**</span></span>  
 <span data-ttu-id="6233b-138">Haga clic para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="6233b-138">Click to save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6233b-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6233b-139">See Also</span></span>  
 <span data-ttu-id="6233b-140">[Agregar una instantánea al historial de informes &#40;Administrador de informes&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="6233b-140">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="6233b-141">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="6233b-141">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="6233b-142">[Crear, modificar y eliminar instantáneas del historial de informes](report-server/create-modify-and-delete-snapshots-in-report-history.md) </span><span class="sxs-lookup"><span data-stu-id="6233b-142">[Create, Modify, and Delete Snapshots in Report History](report-server/create-modify-and-delete-snapshots-in-report-history.md) </span></span>  
 [<span data-ttu-id="6233b-143">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="6233b-143">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
