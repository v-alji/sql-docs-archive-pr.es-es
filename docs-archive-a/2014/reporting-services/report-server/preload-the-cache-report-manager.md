---
title: Cargar previamente la memoria caché (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- cache [Reporting Services]
- preloading cache
ms.assetid: 152a1051-8aa5-4c01-bc85-f8be8971b0cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b60b74f7ab5c0c843b848c09ee574fd59a99c682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746161"
---
# <a name="preload-the-cache-report-manager"></a><span data-ttu-id="c0ac1-102">Cargar previamente la memoria caché (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="c0ac1-102">Preload the Cache (Report Manager)</span></span>
  <span data-ttu-id="c0ac1-103">Puede cargar previamente la memoria caché para un conjunto de datos compartido creando un plan de actualización de caché para él.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-103">You can preload the cache for a shared dataset by creating a cache refresh plan for the shared dataset.</span></span>  
  
 <span data-ttu-id="c0ac1-104">Puede cargar previamente la memoria caché para un informe de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="c0ac1-104">You can preload the cache for a report in two ways:</span></span>  
  
1.  <span data-ttu-id="c0ac1-105">Cree un plan de actualización de caché para el informe.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-105">Create a cache refresh plan for the report.</span></span> <span data-ttu-id="c0ac1-106">Este es el método preferido.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-106">This is the preferred method.</span></span>  
  
2.  <span data-ttu-id="c0ac1-107">Utilice una suscripción controlada por datos para cargar previamente la memoria caché con instancias de informes con parámetros.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-107">Use a data-driven subscription to preload the cache with instances of parameterized reports.</span></span> <span data-ttu-id="c0ac1-108">Esa era la única manera de cargar previamente la memoria caché en las versiones de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] anteriores a [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0ac1-108">This was the only way to preload the cache in versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] earlier than [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="c0ac1-109">Para más información, vea [Informes almacenados en caché &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c0ac1-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
 <span data-ttu-id="c0ac1-110">Se deben cumplir las siguientes condiciones para poder almacenar en memoria caché un informe o un conjunto de datos compartido:</span><span class="sxs-lookup"><span data-stu-id="c0ac1-110">The following conditions must be met before you can cache a report or a shared dataset:</span></span>  
  
-   <span data-ttu-id="c0ac1-111">El conjunto de datos compartido o el informe deben tener habilitado el almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-111">The shared dataset or the report must have caching enabled.</span></span>  
  
-   <span data-ttu-id="c0ac1-112">Los orígenes de datos compartidos para el conjunto de datos compartidos o el informe se deben configurar para utilizar las credenciales almacenadas o para no usar ninguna credencial.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-112">The shared data sources for the shared dataset or the report must be configured to use stored credentials or no credentials.</span></span>  
  
-   <span data-ttu-id="c0ac1-113">Se debe ejecutar el servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0ac1-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service must be running.</span></span>  
  
### <a name="to-preload-the-cache-by-creating-a-cache-refresh-plan"></a><span data-ttu-id="c0ac1-114">Para cargar previamente la memoria caché creando un plan de actualización de caché</span><span class="sxs-lookup"><span data-stu-id="c0ac1-114">To preload the cache by creating a cache refresh plan</span></span>  
  
1.  <span data-ttu-id="c0ac1-115">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c0ac1-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="c0ac1-116">En el Administrador de informes, navegue a la página **Contenido** y después navegue al elemento que desee almacenar en caché.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-116">In Report Manager, navigate to the **Contents** page, and then navigate to the item that you want to cache.</span></span>  
  
3.  <span data-ttu-id="c0ac1-117">Mantenga el mouse sobre el elemento, haga clic en la lista desplegable y, después, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-117">Hover over the item, click the drop-down list, and then click **Manage**.</span></span>  
  
4.  <span data-ttu-id="c0ac1-118">Haga clic en la pestaña **Opciones de actualización de caché** .</span><span class="sxs-lookup"><span data-stu-id="c0ac1-118">Click the **Cache Refresh Options** tab.</span></span>  
  
5.  <span data-ttu-id="c0ac1-119">En la barra de herramientas, haga clic en **Nuevo plan de actualización de caché**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-119">On the toolbar, click **New Cache Refresh Plan**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0ac1-120">Si el elemento no tiene habilitado el almacenamiento en caché, se solicitará que lo habilite.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-120">If the item does not have caching enabled, you will be prompted to enable caching.</span></span> <span data-ttu-id="c0ac1-121">Para habilitar el almacenamiento en caché, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-121">To enable caching, click **OK**.</span></span>  
  
     <span data-ttu-id="c0ac1-122">Se abre la página de Plan de actualización de caché.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-122">The Cache Refresh Plan page opens.</span></span>  
  
6.  <span data-ttu-id="c0ac1-123">Escriba una descripción para el plan de actualización.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-123">Optionally type a description for the refresh plan.</span></span>  
  
7.  <span data-ttu-id="c0ac1-124">En una programación compartida, haga clic en **Programación compartida**y seleccione el nombre de la programación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-124">For a shared schedule, click **Shared schedule**, and then select the name of the schedule to use.</span></span>  
  
     <span data-ttu-id="c0ac1-125">En una programación personalizada, haga clic en **Programación específica del elemento**y, después, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-125">For a custom schedule, click **Item-specific schedule**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="c0ac1-126">Configuración de la programación</span><span class="sxs-lookup"><span data-stu-id="c0ac1-126">Configure the schedule</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-preload-the-cache-with-a-user-specific-report-by-using-a-data-driven-subscription"></a><span data-ttu-id="c0ac1-127">Para cargar previamente la memoria caché con un informe específico del usuario utilizando una suscripción controlada por datos</span><span class="sxs-lookup"><span data-stu-id="c0ac1-127">To preload the cache with a user-specific report by using a data-driven subscription</span></span>  
  
1.  <span data-ttu-id="c0ac1-128">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c0ac1-128">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="c0ac1-129">En el Administrador de informes, navegue a la página **Contenido** y después, al informe para el que desea crear una suscripción.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-129">In Report Manager, navigate to the **Contents** page, and then navigate to the report you want to create a subscription for.</span></span>  
  
3.  <span data-ttu-id="c0ac1-130">Haga clic en el informe, en la pestaña **Suscripciones** y, después, en **Nueva suscripción controlada por datos**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-130">Click the report, click the **Subscriptions** tab, and then click **New Data-Driven Subscription**.</span></span>  
  
4.  <span data-ttu-id="c0ac1-131">Escriba una descripción de la suscripción (opcional).</span><span class="sxs-lookup"><span data-stu-id="c0ac1-131">Optionally type a description for the subscription.</span></span>  
  
5.  <span data-ttu-id="c0ac1-132">En la lista **Especifique cómo se notifica a los destinatarios** , seleccione **Proveedor de entrega NULL**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-132">From the **Specify how recipients are notified** list, select **Null Delivery Provider**.</span></span>  
  
6.  <span data-ttu-id="c0ac1-133">Especifique un tipo de origen de datos y haga clic en **Siguiente** para configurar el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-133">Specify a data source type and then click **Next** to configure the data source.</span></span>  
  
7.  <span data-ttu-id="c0ac1-134">Especifique el tipo de conexión, la cadena de conexión y las credenciales para obtener acceso al origen de datos que contiene la información sobre los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-134">Specify the connection type, connection string, and credentials for accessing the data source that contains subscriber data.</span></span> <span data-ttu-id="c0ac1-135">En el siguiente ejemplo, se muestra la cadena de conexión utilizada para conectarse a una base de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] llamada Subscribers:</span><span class="sxs-lookup"><span data-stu-id="c0ac1-135">The following example illustrates a connection string used to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database called Subscribers:</span></span>  
  
    ```  
    data source=<servername>; initial catalog=Subscribers  
    ```  
  
8.  <span data-ttu-id="c0ac1-136">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-136">Click **Next**.</span></span>  
  
9. <span data-ttu-id="c0ac1-137">Especifique la consulta o el comando que recupera los datos de los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-137">Specify the query or command that retrieves subscriber data.</span></span> <span data-ttu-id="c0ac1-138">Si lo desea, puede incrementar el período de tiempo de espera en el caso de consultas que tarden bastante tiempo en procesarse.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-138">Optionally increase the time-out period for queries that take a long time to process.</span></span> <span data-ttu-id="c0ac1-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c0ac1-139">For example:</span></span>  
  
    ```  
    Select * from UserInfo  
    ```  
  
10. <span data-ttu-id="c0ac1-140">Haga clic en **Validar**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-140">Click **Validate**.</span></span> <span data-ttu-id="c0ac1-141">Antes de continuar, la consulta debe validarse.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-141">The query must be validated before you continue.</span></span> <span data-ttu-id="c0ac1-142">Cuando aparezca el mensaje **Consulta validada correctamente** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-142">When the **Query validated successfully** message appears, click **Next**.</span></span>  
  
11. <span data-ttu-id="c0ac1-143">Dado que no puede configurar extensiones de entrega para el proveedor de entrega NULL, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-143">Because you cannot configure delivery extension settings for the null delivery provider, click **Next**.</span></span>  
  
12. <span data-ttu-id="c0ac1-144">Especifique valores de parámetro de informe para la suscripción y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-144">Specify report parameter values for the subscription, and click **Next**.</span></span>  
  
13. <span data-ttu-id="c0ac1-145">Especifique cuándo se procesa la suscripción.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-145">Specify when the subscription is processed.</span></span> <span data-ttu-id="c0ac1-146">No elija **Cuando los datos del informe se actualizan en el servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-146">Do not choose **When the report data is updated on the report server**.</span></span> <span data-ttu-id="c0ac1-147">Este valor solo es para instantáneas.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-147">That setting is for snapshots only.</span></span> <span data-ttu-id="c0ac1-148">Si quiere usar una programación existente, seleccione **Según una programación compartida**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-148">If want to use a pre-existing schedule, select **On a shared schedule**.</span></span>  
  
     <span data-ttu-id="c0ac1-149">O bien, para crear una programación personalizada, haga clic en **Según una programación creada para esta suscripción** y, a continuación, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-149">Or, to create a custom schedule, click **On a schedule created for this subscription** and then click **Next**.</span></span> <span data-ttu-id="c0ac1-150">Configure la programación y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-150">Configure the schedule and then click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0ac1-151">Para que los suscriptores reciban el informe más reciente, el programa que configure debe ser coherente con la programación de entrega del informe que haya definido para los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-151">In order for the subscribers to receive the newest report, the schedule that you configure should be consistent with the report delivery schedule that you have defined for the subscribers.</span></span> <span data-ttu-id="c0ac1-152">Para más información, vea [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c0ac1-152">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
14. <span data-ttu-id="c0ac1-153">Configure las opciones de Ejecución correspondientes al informe de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0ac1-153">Configure the Execution options for the report as follows.</span></span> <span data-ttu-id="c0ac1-154">En la página del informe, haga clic en la pestaña **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="c0ac1-154">On the report page, click the **Properties** tab.</span></span>  
  
15. <span data-ttu-id="c0ac1-155">En el marco de la izquierda, haga clic en la pestaña **Ejecución** .</span><span class="sxs-lookup"><span data-stu-id="c0ac1-155">In the left frame, click the **Execution** tab.</span></span>  
  
16. <span data-ttu-id="c0ac1-156">En la página, seleccione **Representar este informe con los datos más recientes**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-156">On the page, select **Render this report with the most recent data**.</span></span>  
  
17. <span data-ttu-id="c0ac1-157">Elija una de las dos opciones de caché siguientes y configure la expiración como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c0ac1-157">Choose one of the following two cache options and configure the expiration as follows:</span></span>  
  
    -   <span data-ttu-id="c0ac1-158">Para lograr que la copia en caché expire después de un período de tiempo concreto, haga clic en **Almacenar en caché una copia temporal del informe. La copia del informe expira después de un número determinado de minutos.**</span><span class="sxs-lookup"><span data-stu-id="c0ac1-158">To make the cached copy expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes.**</span></span> <span data-ttu-id="c0ac1-159">Escriba el número de minutos para la expiración del informe.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-159">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="c0ac1-160">Para lograr que la copia en caché expire siguiendo una programación, haga clic en **Guardar en caché una copia temporal del informe. La copia del informe debe caducar según la siguiente programación.**</span><span class="sxs-lookup"><span data-stu-id="c0ac1-160">To make the cached copy expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="c0ac1-161">Haga clic en **Configurar**o seleccione una programación compartida para establecer una programación para la expiración del informe.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-161">Click **Configure**, or select a shared schedule to set a schedule for report expiration.</span></span>  
  
18. <span data-ttu-id="c0ac1-162">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-162">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ac1-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0ac1-163">See Also</span></span>  
 <span data-ttu-id="c0ac1-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="c0ac1-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="c0ac1-165">[Crear una suscripción controlada por datos &#40;Tutorial de SSRS&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="c0ac1-165">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="c0ac1-166">[Rendimiento, instantáneas, almacenamiento en caché &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="c0ac1-166">[Performance, Snapshots, Caching &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span></span>  
 <span data-ttu-id="c0ac1-167">[Establecer propiedades de procesamiento de informes](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c0ac1-167">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="c0ac1-168">Informes almacenados en caché &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c0ac1-168">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
