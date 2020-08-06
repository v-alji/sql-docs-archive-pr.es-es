---
title: Ver o cambiar las programaciones del conjunto de recopilación (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.collectionsetprop.uploads.f1
- sql12.swb.dc.collectionsetprop.general.f1
- sql12.swb.dc.collectionsetprop.description.f1
helpviewer_keywords:
- collection sets [SQL Server], changing schedules
- schedules [SQL Server], changing collection set
- collection sets [SQL Server], viewing schedules
- schedules [SQL Server], viewing collection set
ms.assetid: 26336c98-78c5-414f-8d6a-574fc3af60c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2eb1acf0346b3e16bd1d54829abbc070e1d9d63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676004"
---
# <a name="view-or-change-collection-set-schedules-sql-server-management-studio"></a><span data-ttu-id="86c9a-102">Ver o cambiar las programaciones del conjunto de recopilación (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="86c9a-102">View or Change Collection Set Schedules (SQL Server Management Studio)</span></span>
  <span data-ttu-id="86c9a-103">Puede ver o cambiar las programaciones del conjunto de recopilación mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86c9a-103">You can view or change collection set schedules by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="86c9a-104">El modo de recopilación, con almacenamiento en caché o sin almacenamiento en caché, determina cómo se puede hacer cambios en una programación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-104">The collection mode, cached or non-cached, determines how you can make changes to a schedule.</span></span> <span data-ttu-id="86c9a-105">El modo de almacenamiento en caché utiliza programaciones independientes para la recopilación y para la carga.</span><span class="sxs-lookup"><span data-stu-id="86c9a-105">Cached mode uses separate schedules for collection and upload.</span></span> <span data-ttu-id="86c9a-106">El modo sin almacenamiento en caché utiliza la misma programación para la recopilación y para la carga.</span><span class="sxs-lookup"><span data-stu-id="86c9a-106">Non-cached mode uses the same schedule for collection and upload.</span></span> <span data-ttu-id="86c9a-107">El tipo de modo de recopilación para cada uno de los conjuntos de recopilación de datos del sistema es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="86c9a-107">The type of collection mode for each of the System Datacollection sets is as follows:</span></span>  
  
-   <span data-ttu-id="86c9a-108">**Uso de disco** : usa el modo de recopilación de datos no almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="86c9a-108">**Disk Usage** uses non-cached collection mode.</span></span>  
  
-   <span data-ttu-id="86c9a-109">**Estadísticas de consultas** : utiliza el modo de recopilación de datos almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="86c9a-109">**Query Statistics** uses cached collection mode.</span></span>  
  
-   <span data-ttu-id="86c9a-110">**Actividad del servidor** : utiliza el modo de recopilación de datos almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="86c9a-110">**Server Activity** uses cached collection mode.</span></span>  
  
### <a name="to-view-collection-set-schedules"></a><span data-ttu-id="86c9a-111">Para ver las programaciones del conjunto de recopilación</span><span class="sxs-lookup"><span data-stu-id="86c9a-111">To view collection set schedules</span></span>  
  
1.  <span data-ttu-id="86c9a-112">En el Explorador de objetos, expanda el nodo **Administración** , expanda **Recopilación de datos**y, después, **Conjuntos de recopilación de datos del sistema**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-112">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="86c9a-113">Haga clic con el botón derecho en un nombre de conjunto de recopilación y haga clic en **Propiedades** para abrir el cuadro de diálogo [Propiedades del conjunto de recopilación de datos](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="86c9a-113">Right-click a collection set name, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
### <a name="to-change-the-schedules-for-a-cached-mode-collection-set"></a><span data-ttu-id="86c9a-114">Para cambiar las programaciones de un conjunto de recopilación en modo de datos almacenados en caché</span><span class="sxs-lookup"><span data-stu-id="86c9a-114">To change the schedules for a cached mode collection set</span></span>  
  
1.  <span data-ttu-id="86c9a-115">En el Explorador de objetos, expanda el nodo **Administración** , expanda **Recopilación de datos**y, después, **Conjuntos de recopilación de datos del sistema**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-115">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="86c9a-116">Haga clic con el botón derecho en un conjunto de recopilación que use el modo de almacenamiento en memoria caché, como **Estadísticas de consultas**y haga clic en **Propiedades** para abrir el cuadro de diálogo [Propiedades del conjunto de recopilación de datos](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="86c9a-116">Right-click a collection set that uses cached mode, such as **Query Statistics**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
3.  <span data-ttu-id="86c9a-117">Puede cambiar la frecuencia de recopilación en la página **General** .</span><span class="sxs-lookup"><span data-stu-id="86c9a-117">You can change the collection frequency on the **General** page.</span></span> <span data-ttu-id="86c9a-118">Para ello, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="86c9a-118">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="86c9a-119">En el panel de detalles, haga doble clic en el número que se muestra para la columna **Frecuencia de recopilación (s)** en la tabla **Elementos de recopilación** .</span><span class="sxs-lookup"><span data-stu-id="86c9a-119">In the details pane, double-click the number that is displayed for the **Collection Frequency (sec)** column in the **Collection items** table.</span></span>  
  
    2.  <span data-ttu-id="86c9a-120">Para aumentar o disminuir la frecuencia de recopilación, escriba un número menor o mayor, y presione ENTRAR para almacenar el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="86c9a-120">To increase or decrease the collection frequency, type a lower or higher number, and then press ENTER to store the new value.</span></span>  
  
4.  <span data-ttu-id="86c9a-121">Para cambiar la programación de carga existente del conjunto de recopilación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="86c9a-121">To change the existing upload schedule for the collection set, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="86c9a-122">Haga clic en la página **Cargas** .</span><span class="sxs-lookup"><span data-stu-id="86c9a-122">Click the **Uploads** page.</span></span>  
  
    2.  <span data-ttu-id="86c9a-123">En el panel de detalles, haga clic en **Elegir**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-123">In the details pane, click **Pick**.</span></span>  
  
         <span data-ttu-id="86c9a-124">Se abre el cuadro de diálogo **Elegir programación para trabajo** .</span><span class="sxs-lookup"><span data-stu-id="86c9a-124">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="86c9a-125">Las programaciones disponibles aparecen en forma de tabla.</span><span class="sxs-lookup"><span data-stu-id="86c9a-125">The available schedules appear as a table.</span></span>  
  
    3.  <span data-ttu-id="86c9a-126">Haga clic en la fila con la programación que desee.</span><span class="sxs-lookup"><span data-stu-id="86c9a-126">Click the row with the schedule that you want.</span></span> <span data-ttu-id="86c9a-127">Por ejemplo, para cambiar la programación a cada 5 minutos, haga clic en la fila donde el nombre de programación sea **CollectorSchedule_Every_5min**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-127">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min.**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="86c9a-128">Puede ver y modificar las propiedades de la programación seleccionada haciendo clic en **Propiedades** para abrir el cuadro de diálogo **Propiedades de programación del trabajo** correspondiente a la programación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-128">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="86c9a-129">Puede usar este cuadro de diálogo para cambiar información de la programación, como la frecuencia.</span><span class="sxs-lookup"><span data-stu-id="86c9a-129">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
        >   
        >  <span data-ttu-id="86c9a-130">Como alternativa a modificar una programación existente, puede hacer clic en **Nueva** , en la página **Cargas** , para crear una programación de carga nueva.</span><span class="sxs-lookup"><span data-stu-id="86c9a-130">As an alternative to modifying an existing schedule, you can create a new upload schedule by clicking **New** on the **Uploads** page.</span></span> <span data-ttu-id="86c9a-131">De este modo se abre el cuadro de diálogo **Nueva programación de trabajo** , que puede utilizar para crear una programación personalizada.</span><span class="sxs-lookup"><span data-stu-id="86c9a-131">This action opens the **New Job Schedule** dialog box, which you can use to create a custom schedule.</span></span>  
  
    4.  <span data-ttu-id="86c9a-132">Cuando haya terminado de configurar la programación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-132">When you are finished configuring the schedule, click **OK**.</span></span>  
  
         <span data-ttu-id="86c9a-133">Los cambios que haga se muestran en la página **Cargas** .</span><span class="sxs-lookup"><span data-stu-id="86c9a-133">The changes that you made appear on the **Uploads** page.</span></span>  
  
5.  <span data-ttu-id="86c9a-134">Haga clic en **Aceptar** para guardar los cambios de la frecuencia de recopilación y la programación de carga y para cerrar el cuadro de diálogo **Propiedades del conjunto de recopilación de datos** .</span><span class="sxs-lookup"><span data-stu-id="86c9a-134">Click **OK** to save the changes to the collection frequency and the upload schedule, and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
### <a name="to-change-the-schedule-for-a-non-cached-mode-collection-set"></a><span data-ttu-id="86c9a-135">Para cambiar la programación de un conjunto de recopilación en modo de datos no almacenados en caché</span><span class="sxs-lookup"><span data-stu-id="86c9a-135">To change the schedule for a non-cached mode collection set</span></span>  
  
1.  <span data-ttu-id="86c9a-136">En el Explorador de objetos, expanda el nodo **Administración** , expanda **Recopilación de datos**y, después, **Conjuntos de recopilación de datos del sistema**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-136">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="86c9a-137">Haga clic con el botón derecho en un conjunto de recopilación que use el modo sin almacenamiento en memoria caché, como **Uso de disco**, y haga clic en **Propiedades** para abrir el cuadro de diálogo [Propiedades del conjunto de recopilación de datos](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="86c9a-137">Right-click a collection set that uses non-cached mode, such as **Disk Usage**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
     <span data-ttu-id="86c9a-138">El cuadro de diálogo **Propiedades del conjunto de recopilación de datos** muestra una vista paginada de las propiedades del conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-138">The **Data Collection Set Properties** dialog box displays a paged view of the collection set properties.</span></span>  
  
3.  <span data-ttu-id="86c9a-139">Para cambiar la programación de un conjunto de recopilación, haga clic en **Elegir**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-139">To change the schedule for the collection set, click **Pick**.</span></span>  
  
     <span data-ttu-id="86c9a-140">Se abre el cuadro de diálogo **Elegir programación para trabajo** .</span><span class="sxs-lookup"><span data-stu-id="86c9a-140">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="86c9a-141">Las programaciones disponibles se muestran en forma de tabla.</span><span class="sxs-lookup"><span data-stu-id="86c9a-141">The available schedules are displayed as a table.</span></span>  
  
4.  <span data-ttu-id="86c9a-142">Haga clic en la fila con la programación que desee.</span><span class="sxs-lookup"><span data-stu-id="86c9a-142">Click the row with the schedule that you want.</span></span> <span data-ttu-id="86c9a-143">Por ejemplo, para cambiar la programación a cada 5 minutos, haga clic en la fila donde el nombre de programación sea **CollectorSchedule_Every_5min**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-143">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="86c9a-144">Puede ver y modificar las propiedades de la programación seleccionada haciendo clic en **Propiedades** para abrir el cuadro de diálogo **Propiedades de programación del trabajo** correspondiente a la programación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-144">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="86c9a-145">Puede usar este cuadro de diálogo para cambiar información de la programación, como la frecuencia.</span><span class="sxs-lookup"><span data-stu-id="86c9a-145">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
    >   
    >  <span data-ttu-id="86c9a-146">Como alternativa a modificar una programación existente, puede hacer clic en **Nueva** , en la página **General** , para crear una recopilación y una programación de carga nuevas.</span><span class="sxs-lookup"><span data-stu-id="86c9a-146">As an alternative to modifying an existing schedule, you can create a new collect and upload schedule by clicking **New** on the **General** page.</span></span> <span data-ttu-id="86c9a-147">De este modo se abre el cuadro de diálogo **Nueva programación de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="86c9a-147">This action opens the **New Job Schedule** dialog box.</span></span>  
  
5.  <span data-ttu-id="86c9a-148">Cuando haya terminado de configurar la programación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-148">When you are finished configuring the schedule, click **OK**.</span></span>  
  
6.  <span data-ttu-id="86c9a-149">Haga clic en **Aceptar** para guardar los cambios y cerrar el cuadro de diálogo **Propiedades del conjunto de recopilación de datos** .</span><span class="sxs-lookup"><span data-stu-id="86c9a-149">Click **OK** to save the changes and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
####  <a name="data-collection-set-properties-dialog-box"></a><a name="CollectionSet"></a> <span data-ttu-id="86c9a-150">Cuadro de diálogo Propiedades del conjunto de recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="86c9a-150">Data Collection Set Properties Dialog Box</span></span>  
 <span data-ttu-id="86c9a-151">**Página General**</span><span class="sxs-lookup"><span data-stu-id="86c9a-151">**General Page**</span></span>  
  
 <span data-ttu-id="86c9a-152">Utilice esta página para configurar la recopilación y carga de datos, las programaciones y los períodos de retención de datos en el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="86c9a-152">Use this page to configure how data is collected and uploaded, configure schedules, and configure data retention periods in the management data warehouse.</span></span> <span data-ttu-id="86c9a-153">Esta página también proporciona información sobre los conjuntos de recopilación, como los tipos de recopilador y las frecuencias de recopilación, así como sobre los parámetros de entrada que se utilizan para un conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-153">This page also provides information about collection sets, such as collector types and collection frequencies, as well as the input parameters that are used for a collection set.</span></span>  
  
 <span data-ttu-id="86c9a-154">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="86c9a-154">**Name**</span></span>  
 <span data-ttu-id="86c9a-155">Muestra el nombre del conjunto de recopilación al que hace referencia esta página.</span><span class="sxs-lookup"><span data-stu-id="86c9a-155">Displays the name of the collection set that this page refers to.</span></span>  
  
 <span data-ttu-id="86c9a-156">**Recopilación y carga de datos**</span><span class="sxs-lookup"><span data-stu-id="86c9a-156">**Data collection and upload**</span></span>  
 <span data-ttu-id="86c9a-157">Especifica cómo se recopilan y cargan los datos en el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="86c9a-157">Specifies how data is collected and uploaded to the management data warehouse.</span></span> <span data-ttu-id="86c9a-158">Elija una de las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="86c9a-158">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86c9a-159">**Sin caché. Recopilación y carga de datos en la misma programación.**</span><span class="sxs-lookup"><span data-stu-id="86c9a-159">**Non-cached. Collection and data upload on the same schedule.**</span></span>|<span data-ttu-id="86c9a-160">Si la selecciona, especifique una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="86c9a-160">When selected, specify one of the following:</span></span><br /><br /> <span data-ttu-id="86c9a-161">**A petición**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-161">**On-demand**.</span></span> <span data-ttu-id="86c9a-162">Los datos se recopilan y se cargan a petición.</span><span class="sxs-lookup"><span data-stu-id="86c9a-162">Data is collected and uploaded on demand.</span></span><br /><br /> <span data-ttu-id="86c9a-163">**Programación**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-163">**Schedule**.</span></span> <span data-ttu-id="86c9a-164">Los datos se recopilan y se cargan de acuerdo con una programación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-164">Data is collected and uploaded according to a schedule.</span></span> <span data-ttu-id="86c9a-165">Haga clic en **Seleccionar** para seleccionar entre una lista predefinida de programaciones o en **Nueva** para crear una nueva programación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-165">Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>|  
|<span data-ttu-id="86c9a-166">**En caché. Recopilar y almacenar en caché los datos en un conjunto de frecuencias de recopilación. Cargar los datos en caché según una programación independiente.**</span><span class="sxs-lookup"><span data-stu-id="86c9a-166">**Cached. Collect and cache data at a set of collection frequencies. Upload cached data on a separate schedule.**</span></span>|<span data-ttu-id="86c9a-167">Recopilar y almacenar en caché los datos para una frecuencia de recopilación especificada.</span><span class="sxs-lookup"><span data-stu-id="86c9a-167">Collect and cache data for a specified collection frequency.</span></span> <span data-ttu-id="86c9a-168">Cargar los datos recopilados según una programación independiente.</span><span class="sxs-lookup"><span data-stu-id="86c9a-168">Upload the collected data on a separate schedule.</span></span>|  
  
 <span data-ttu-id="86c9a-169">**Elementos de recopilación**</span><span class="sxs-lookup"><span data-stu-id="86c9a-169">**Collection items**</span></span>  
 <span data-ttu-id="86c9a-170">Muestra los elementos de recopilación del conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-170">Displays the collection items in the collection set.</span></span> <span data-ttu-id="86c9a-171">Se proporciona la información siguiente para cada elemento de recopilación:</span><span class="sxs-lookup"><span data-stu-id="86c9a-171">The following information is provided for each collection item:</span></span>  
  
-   <span data-ttu-id="86c9a-172">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="86c9a-172">**Name**</span></span>  
  
-   <span data-ttu-id="86c9a-173">**Tipo de recopilador**</span><span class="sxs-lookup"><span data-stu-id="86c9a-173">**Collector Type**</span></span>  
  
-   <span data-ttu-id="86c9a-174">**Frecuencia de recopilación** (s).</span><span class="sxs-lookup"><span data-stu-id="86c9a-174">**Collection Frequency** (secs).</span></span> <span data-ttu-id="86c9a-175">Este campo se puede modificar si **Recopilación y carga de datos** se configura como almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="86c9a-175">This field is editable if **Data collection and upload** is configured as cached.</span></span> <span data-ttu-id="86c9a-176">Haga doble clic en esta celda para establecer la frecuencia de recopilación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-176">Double-click this cell to set the collection frequency.</span></span>  
  
 <span data-ttu-id="86c9a-177">**Parámetros de entrada**</span><span class="sxs-lookup"><span data-stu-id="86c9a-177">**Input parameters**</span></span>  
 <span data-ttu-id="86c9a-178">Muestra los parámetros de entrada utilizados para el conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-178">Displays the input parameters used for the collection set.</span></span>  
  
 <span data-ttu-id="86c9a-179">**Ejecutar como**</span><span class="sxs-lookup"><span data-stu-id="86c9a-179">**Run as**</span></span>  
 <span data-ttu-id="86c9a-180">Especifica la cuenta utilizada para ejecutar el conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-180">Specifies the account used to run the collection set.</span></span> <span data-ttu-id="86c9a-181">De forma predeterminada, ésta es la cuenta del servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86c9a-181">By default this is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service Account.</span></span> <span data-ttu-id="86c9a-182">Si se definen cuentas de proxy, esta lista incluye los nombres de las cuentas de proxy disponibles.</span><span class="sxs-lookup"><span data-stu-id="86c9a-182">If proxy accounts are defined, this list includes the names of the available proxy accounts.</span></span>  
  
 <span data-ttu-id="86c9a-183">**Establecer cuánto tiempo se retendrán los datos recopilados en el almacén de administración de datos.**</span><span class="sxs-lookup"><span data-stu-id="86c9a-183">**Set how long collected data will be retained in the management data warehouse.**</span></span>  
 <span data-ttu-id="86c9a-184">Especifica cuánto tiempo se retienen los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="86c9a-184">Specifies how long collected data is retained.</span></span> <span data-ttu-id="86c9a-185">Elija una de las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="86c9a-185">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86c9a-186">**Retener datos para**</span><span class="sxs-lookup"><span data-stu-id="86c9a-186">**Retain data for**</span></span>|<span data-ttu-id="86c9a-187">Esta opción está seleccionada de forma predeterminada y el período de retención predeterminado es de 14 días.</span><span class="sxs-lookup"><span data-stu-id="86c9a-187">This option is selected by default, and the default retention period is 14 days.</span></span>|  
|<span data-ttu-id="86c9a-188">**Retener datos indefinidamente**</span><span class="sxs-lookup"><span data-stu-id="86c9a-188">**Retain data indefinitely**</span></span>|<span data-ttu-id="86c9a-189">No hay ningún límite en la cantidad de tiempo que se retienen los datos.</span><span class="sxs-lookup"><span data-stu-id="86c9a-189">There is no time limit on the length of time that data is retained.</span></span>|  
  
 <span data-ttu-id="86c9a-190">**Página Cargas**</span><span class="sxs-lookup"><span data-stu-id="86c9a-190">**Uploads Page**</span></span>  
  
 <span data-ttu-id="86c9a-191">Utilice esta página para configurar la programación de carga para los datos recogidos por este conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-191">Use this page to configure the upload schedule for data that is collected by this collection set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86c9a-192">Esta pestaña solo está habilitada si se configura la opción **En caché** para **Recopilación y carga de datos**.</span><span class="sxs-lookup"><span data-stu-id="86c9a-192">This tab is only enabled if the **Cached** option is configured for **Data collection and upload**.</span></span>  
  
 <span data-ttu-id="86c9a-193">**Server**</span><span class="sxs-lookup"><span data-stu-id="86c9a-193">**Server**</span></span>  
 <span data-ttu-id="86c9a-194">Muestra el nombre del servidor que hospeda el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="86c9a-194">Displays the name of the server that hosts the management data warehouse.</span></span> <span data-ttu-id="86c9a-195">Para obtener más información, vea [Configurar el almacén de administración de datos &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="86c9a-195">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="86c9a-196">**almacén de administración de datos**</span><span class="sxs-lookup"><span data-stu-id="86c9a-196">**Management data warehouse**</span></span>  
 <span data-ttu-id="86c9a-197">Muestra el nombre del almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="86c9a-197">Displays the name of the management data warehouse.</span></span> <span data-ttu-id="86c9a-198">Para obtener más información, vea [Configurar el almacén de administración de datos &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="86c9a-198">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="86c9a-199">**Última carga**</span><span class="sxs-lookup"><span data-stu-id="86c9a-199">**Last upload**</span></span>  
 <span data-ttu-id="86c9a-200">Muestra la información de fecha y hora para la última carga del conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-200">Displays date and time information for the last upload done for the collection set.</span></span>  
  
 <span data-ttu-id="86c9a-201">**Programación de carga**</span><span class="sxs-lookup"><span data-stu-id="86c9a-201">**Upload schedule**</span></span>  
 <span data-ttu-id="86c9a-202">Especifica la programación de carga para el conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-202">Specifies the upload schedule for the collection set.</span></span> <span data-ttu-id="86c9a-203">Si está habilitada, haga clic en **Seleccionar** para seleccionar entre una lista predefinida de programaciones o en **Nueva** para crear una nueva programación.</span><span class="sxs-lookup"><span data-stu-id="86c9a-203">If enabled, Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>  
  
 <span data-ttu-id="86c9a-204">**Página Descripción**</span><span class="sxs-lookup"><span data-stu-id="86c9a-204">**Description Page**</span></span>  
  
 <span data-ttu-id="86c9a-205">Utilice esta página para ver una descripción del conjunto de recopilación al que hace referencia esta página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="86c9a-205">Use this page to view a description of the collection set that this properties page refers to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c9a-206">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86c9a-206">See Also</span></span>  
 <span data-ttu-id="86c9a-207">[Administrar la recopilación de datos](manage-data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="86c9a-207">[Manage Data Collection](manage-data-collection.md) </span></span>  
 [<span data-ttu-id="86c9a-208">Recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="86c9a-208">Data Collection</span></span>](data-collection.md)  
  
  
