---
title: 'Lección 3: Definir una suscripción controlada por datos | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 89197b9b-7502-4fe2-bea3-ed7943eebf3b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d1bbc25bdd08b369180e31378a6d25a595badbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751798"
---
# <a name="lesson-3-defining-a-data-driven-subscription"></a><span data-ttu-id="13463-102">Lesson 3: Defining a Data-Driven Subscription</span><span class="sxs-lookup"><span data-stu-id="13463-102">Lesson 3: Defining a Data-Driven Subscription</span></span>
  <span data-ttu-id="13463-103">En esta lección, utilizará las páginas de suscripción controladas por datos para conectar a un origen de datos de suscripción, crear una consulta que recupera datos de suscripción y asignar el conjunto de resultados a las opciones de informe y entrega.</span><span class="sxs-lookup"><span data-stu-id="13463-103">In this lesson, you use the data-driven subscription pages to connect to a subscription data source, build a query that retrieves subscription data, and map the result set to report and delivery options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13463-104">Antes de empezar, compruebe que el servicio del Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] esté en ejecución.</span><span class="sxs-lookup"><span data-stu-id="13463-104">Before you start, verify that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service is running.</span></span> <span data-ttu-id="13463-105">Si no es así, no podrá guardar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="13463-105">If it is not running, you cannot save the subscription.</span></span>  
  
 <span data-ttu-id="13463-106">En esta lección se supone que completó la lección 1 y la lección 2, y que el origen de datos del informe usa credenciales almacenadas.</span><span class="sxs-lookup"><span data-stu-id="13463-106">This lesson assumes you completed Lesson 1 and Lesson 2 and that the report data source uses stored credentials.</span></span>  <span data-ttu-id="13463-107">Para obtener más información, consulte [Lección 2: Modificar las propiedades del origen de datos de informe](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)</span><span class="sxs-lookup"><span data-stu-id="13463-107">For more information, see [Lesson 2: Modifying the Report Data Source Properties](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)</span></span>  
  
 <span data-ttu-id="13463-108">En este tema:</span><span class="sxs-lookup"><span data-stu-id="13463-108">In this topic:</span></span>  
  
-   [<span data-ttu-id="13463-109">Iniciar el Asistente para suscripciones controladas por datos</span><span class="sxs-lookup"><span data-stu-id="13463-109">Start the Data-Driven Subscription Wizard</span></span>](#bkmk_startwizard)  
  
-   [<span data-ttu-id="13463-110">Paso 1: definir una descripción</span><span class="sxs-lookup"><span data-stu-id="13463-110">Step 1 - Define a description</span></span>](#bkmk_definesubscription)  
  
-   [<span data-ttu-id="13463-111">Paso 2: definir una conexión al origen de datos del suscriptor</span><span class="sxs-lookup"><span data-stu-id="13463-111">Step 2 - Define a Connection to the Subscriber Data Source</span></span>](#bkmk_defineconnectiontosubscriber)  
  
-   [<span data-ttu-id="13463-112">Paso 3: definir una consulta para recuperar datos del suscriptor</span><span class="sxs-lookup"><span data-stu-id="13463-112">Step 3 - Define a Query to Retrieve Subscriber data</span></span>](#bkmk_definequery)  
  
-   [<span data-ttu-id="13463-113">Paso 4: establecer las opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="13463-113">Step 4 - Set Delivery Options</span></span>](#bkmk_set_deliveryoptions)  
  
-   [<span data-ttu-id="13463-114">Paso 5: configurar un valor de parámetro para cambiar los resultados del informe</span><span class="sxs-lookup"><span data-stu-id="13463-114">Step 5 - Configure a Parameter Value to Very Report Output</span></span>](#bkmk_configure_parameter)  
  
-   [<span data-ttu-id="13463-115">Paso 6: programar una suscripción</span><span class="sxs-lookup"><span data-stu-id="13463-115">Step 6 - To Schedule a Subscription</span></span>](#bkmk_schedule_subscription)  
  
##  <a name="start-the-data-driven-subscription-wizard"></a><a name="bkmk_startwizard"></a><span data-ttu-id="13463-116">Iniciar el Asistente para suscripciones controladas por datos</span><span class="sxs-lookup"><span data-stu-id="13463-116">Start the Data-Driven Subscription Wizard</span></span>  
  
1.  <span data-ttu-id="13463-117">En el Administrador de informes, haga clic en **Inicio**y navegue hasta la carpeta que contiene el informe **Sales Orders** .</span><span class="sxs-lookup"><span data-stu-id="13463-117">In Report Manager, click **Home**, and navigate to the folder containing the **Sales Orders** report.</span></span>  
  
2.  <span data-ttu-id="13463-118">En el menú contextual del informe, haga clic en **Administrar**y, a continuación, haga clic en la pestaña **Suscripciones** .</span><span class="sxs-lookup"><span data-stu-id="13463-118">In the context menu of the report, click **Manage**, and then click the **Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="13463-119">Haga clic en **Nueva suscripción controlada por datos**.</span><span class="sxs-lookup"><span data-stu-id="13463-119">Click **New Data-driven Subscription**.</span></span> <span data-ttu-id="13463-120">Si no ve este botón, no dispone de permisos para el Administrador de contenido.</span><span class="sxs-lookup"><span data-stu-id="13463-120">If you do not see this button, you do not have Content Manager permissions.</span></span>  
  
##  <a name="step-1---define-a-description"></a><a name="bkmk_definesubscription"></a><span data-ttu-id="13463-121">Paso 1: definir una descripción</span><span class="sxs-lookup"><span data-stu-id="13463-121">Step 1 - Define a description</span></span>  
  
1.  <span data-ttu-id="13463-122">Escriba **Entrega de pedido de ventas** en la descripción.</span><span class="sxs-lookup"><span data-stu-id="13463-122">Type **Sales Order delivery** in description.</span></span>  
  
2.  <span data-ttu-id="13463-123">Seleccione **Windows FileShare** para **Especifique cómo se notifica a los destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="13463-123">Select **Windows FileShare** for **Specify how recipients are notified**.</span></span>  
  
3.  <span data-ttu-id="13463-124">Seleccione **Especifique solo esta suscripción**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="13463-124">Select **Specify for this subscription only**, and then click **Next**.</span></span>  
  
##  <a name="step-2---define-a-connection-to-the-subscriber-data-source"></a><a name="bkmk_defineconnectiontosubscriber"></a><span data-ttu-id="13463-125">Paso 2: definir una conexión con el origen de datos del suscriptor</span><span class="sxs-lookup"><span data-stu-id="13463-125">Step 2 - Define a Connection to the Subscriber Data Source</span></span>  
  
1.  <span data-ttu-id="13463-126">Seleccione **Microsoft SQL Server** como tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="13463-126">Select **Microsoft SQL Server** as the data source type.</span></span>  
  
2.  <span data-ttu-id="13463-127">En Cadena de conexión, escriba la siguiente cadena de conexión:</span><span class="sxs-lookup"><span data-stu-id="13463-127">In Connection string, type the following connection string:</span></span>  
  
    ```  
    data source=localhost; initial catalog=Subscribers  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="13463-128">La base de datos de suscriptores se creó en la lección 1.</span><span class="sxs-lookup"><span data-stu-id="13463-128">Subscribers is the database you created in lesson 1.</span></span>  
  
3.  <span data-ttu-id="13463-129">Haga clic en **Credenciales almacenadas de forma segura en el servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="13463-129">Click **Credentials stored securely in the report server**.</span></span>  
  
4.  <span data-ttu-id="13463-130">En **Nombre de usuario** y **Contraseña**, escriba el nombre de usuario y la contraseña del dominio.</span><span class="sxs-lookup"><span data-stu-id="13463-130">In **User Name** and **Password**, type your domain user name and password.</span></span> <span data-ttu-id="13463-131">Incluya tanto el dominio como la cuenta de usuario al especificar **Nombre de usuario**.</span><span class="sxs-lookup"><span data-stu-id="13463-131">Include both the domain and user account when specifying **User Name**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="13463-132">Las credenciales usadas para conectarse a un origen de datos de suscriptor no se devuelven a [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13463-132">Credentials used to connect to a subscriber data source are not passed back to [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="13463-133">Si modifica la suscripción más adelante, deberá volver a escribir la contraseña utilizada para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="13463-133">If you modify the subscription later, you must retype the password used to connect to the data source.</span></span>  
  
5.  <span data-ttu-id="13463-134">Seleccione **Utilizar como credenciales de Windows para la conexión al origen de datos**y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="13463-134">Select **Use as windows credentials when connecting to the data source**, and then click **Next**.</span></span>  
  
##  <a name="step-3---define-a-query-to-retrieve-subscriber-data"></a><a name="bkmk_definequery"></a><span data-ttu-id="13463-135">Paso 3: definir una consulta para recuperar los datos del suscriptor</span><span class="sxs-lookup"><span data-stu-id="13463-135">Step 3 - Define a Query to Retrieve Subscriber data</span></span>  
  
1.  <span data-ttu-id="13463-136">En el cuadro de consultas, escriba la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="13463-136">In the query box, type the following query:</span></span>  
  
    ```  
    Select * from OrderInfo  
    ```  
  
2.  <span data-ttu-id="13463-137">Especifique un tiempo de espera de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="13463-137">Specify a time-out of 30 seconds.</span></span>  
  
3.  <span data-ttu-id="13463-138">Haga clic en **Validar**y, a continuación, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="13463-138">Click **Validate**, and then click **Next**.</span></span>  
  
##  <a name="step-4---set-delivery-options"></a><a name="bkmk_set_deliveryoptions"></a><span data-ttu-id="13463-139">Paso 4: establecer las opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="13463-139">Step 4 - Set Delivery Options</span></span>  
  
1.  <span data-ttu-id="13463-140">Como **Nombre de archivo**, seleccione **Obtener el valor de la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="13463-140">For **File name**, select **Get the value from the database**.</span></span> <span data-ttu-id="13463-141">Seleccione el campo **Order**.</span><span class="sxs-lookup"><span data-stu-id="13463-141">Select the field **Order**.</span></span>  
  
2.  <span data-ttu-id="13463-142">En **Ruta de acceso**, seleccione **Especificar un valor estático**.</span><span class="sxs-lookup"><span data-stu-id="13463-142">For **Path**, select **Specify a static value**.</span></span> <span data-ttu-id="13463-143">En Valor de configuración, escriba el nombre de un recurso compartido de archivos público para el que disponga de permisos de escritura; por ejemplo, ( `\\mycomputer\public\myreports`).</span><span class="sxs-lookup"><span data-stu-id="13463-143">In Setting Value, type the name of a public file share for which you have write permissions (for example, `\\mycomputer\public\myreports`).</span></span>  
  
3.  <span data-ttu-id="13463-144">En **Formato de representación**, seleccione **Obtener el valor de la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="13463-144">For **Render Format**, select **Get the value from the database**.</span></span> <span data-ttu-id="13463-145">Seleccione **formato**.</span><span class="sxs-lookup"><span data-stu-id="13463-145">Select **Format**.</span></span>  
  
4.  <span data-ttu-id="13463-146">Para el **Modo de escritura**, seleccione **Especificar un valor estático** y seleccione **Incrementar automáticamente**.</span><span class="sxs-lookup"><span data-stu-id="13463-146">For **Write mode**, select **Specify a static value** and select **AutoIncrement**.</span></span>  
  
5.  <span data-ttu-id="13463-147">En **Extensión de archivo**, seleccione **Especificar un valor estático** y seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="13463-147">For **File Extension**, select **Specify a static value** and select **True**.</span></span>  
  
6.  <span data-ttu-id="13463-148">En **Nombre de usuario**, seleccione **Especificar un valor estático**.</span><span class="sxs-lookup"><span data-stu-id="13463-148">For **User name**, select **Specify a static value**.</span></span> <span data-ttu-id="13463-149">Escriba su cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="13463-149">Type your domain user account.</span></span> <span data-ttu-id="13463-150">Escríbalo en este formato: `<domain>\<account>`.</span><span class="sxs-lookup"><span data-stu-id="13463-150">Enter it in this format: `<domain>\<account>`.</span></span> <span data-ttu-id="13463-151">La cuenta de usuario tiene que disponer de permisos en la ruta de acceso que configuró en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="13463-151">The user account needs to have permissions to the path you configured in the previous steps.</span></span>  
  
7.  <span data-ttu-id="13463-152">En **Contraseña**, seleccione **Especificar un valor estático**.</span><span class="sxs-lookup"><span data-stu-id="13463-152">For **Password**, select **Specify a static value**.</span></span> <span data-ttu-id="13463-153">Escriba su contraseña.</span><span class="sxs-lookup"><span data-stu-id="13463-153">Type your password.</span></span> <span data-ttu-id="13463-154">Escríbala con cuidado.</span><span class="sxs-lookup"><span data-stu-id="13463-154">Be sure that you type the password carefully.</span></span> <span data-ttu-id="13463-155">El asistente no valida la contraseña.</span><span class="sxs-lookup"><span data-stu-id="13463-155">The wizard does not validate the password.</span></span>  
  
8.  <span data-ttu-id="13463-156">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="13463-156">Click **Next.**</span></span>  
  
##  <a name="step-5---configure-a-parameter-value-to-very-report-output"></a><a name="bkmk_configure_parameter"></a><span data-ttu-id="13463-157">Paso 5: configurar un valor de parámetro para obtener una salida de informe</span><span class="sxs-lookup"><span data-stu-id="13463-157">Step 5 - Configure a Parameter Value to Very Report Output</span></span>  
  
1.  <span data-ttu-id="13463-158">En **OrderNumber**, seleccione **Obtener el valor de la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="13463-158">For **OrderNumber**, select **Get the value from the database**.</span></span> <span data-ttu-id="13463-159">En Valor, seleccione **Order**.</span><span class="sxs-lookup"><span data-stu-id="13463-159">In Value, select **Order**.</span></span> <span data-ttu-id="13463-160">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="13463-160">Click **Next.**</span></span>  
  
##  <a name="step-6---to-schedule-a-subscription"></a><a name="bkmk_schedule_subscription"></a><span data-ttu-id="13463-161">Paso 6: programar una suscripción</span><span class="sxs-lookup"><span data-stu-id="13463-161">Step 6 - To Schedule a Subscription</span></span>  
  
1.  <span data-ttu-id="13463-162">Haga clic en **Según una programación creada para esta suscripción**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="13463-162">Click **On a schedule created for this subscription**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="13463-163">En **Detalles de programación**, haga clic en **Una vez**.</span><span class="sxs-lookup"><span data-stu-id="13463-163">In **Schedule Details**, click **Once**.</span></span>  
  
3.  <span data-ttu-id="13463-164">Especifique una hora de inicio que sea unos cuantos minutos después de la hora actual.</span><span class="sxs-lookup"><span data-stu-id="13463-164">Specify a start time that is a few minutes ahead of the current time.</span></span>  
  
4.  <span data-ttu-id="13463-165">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="13463-165">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="13463-166">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="13463-166">Next Steps</span></span>  
 <span data-ttu-id="13463-167">Cuando se ejecute la suscripción, se entregarán cuatro archivos de informe al recurso compartido de archivos que ha especificado, uno por cada pedido del origen de datos *Subscribers* .</span><span class="sxs-lookup"><span data-stu-id="13463-167">When the subscription runs, four report files will be delivered to the file share you specified, one for each order in the *Subscribers* data source.</span></span> <span data-ttu-id="13463-168">Cada entrega debe ser única en cuanto a datos (los datos deben ser específicos de cada pedido), formato de representación y formato de archivo.</span><span class="sxs-lookup"><span data-stu-id="13463-168">Each delivery should be unique in terms of data (the data should be order-specific), rendering format, and file format.</span></span> <span data-ttu-id="13463-169">Puede abrir cada informe desde la carpeta compartida para comprobar que todas las versiones se hayan personalizado en función de las opciones de suscripción que haya definido.</span><span class="sxs-lookup"><span data-stu-id="13463-169">You can open each report from the shared folder to verify that each version is customized based on the subscription options you defined.</span></span>  
  
 <span data-ttu-id="13463-170">![Lista de archivos creados por la suscripción](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "Lista de archivos creados por la suscripción")</span><span class="sxs-lookup"><span data-stu-id="13463-170">![List of files created by the subscription](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "List of files created by the subscription")</span></span>  
  
 <span data-ttu-id="13463-171">La página de suscripción del Administrador de informes contendrá la fecha de **Última ejecución** y el **Estado** de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="13463-171">The subscription page in Report Manager will contain the **Last Run** date and **Status** of the subscription.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13463-172">Actualice la página cuando la suscripción se ejecute para ver la información actualizada.</span><span class="sxs-lookup"><span data-stu-id="13463-172">Refresh the page after the subscription runs to see the updated information.</span></span>  
  
 <span data-ttu-id="13463-173">![Resultados de suscripción en el administrador de informes](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Resultados de suscripción en el administrador de informes")</span><span class="sxs-lookup"><span data-stu-id="13463-173">![Subscription results in Report Manager](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Subscription results in Report Manager")</span></span>  
  
 <span data-ttu-id="13463-174">Con este paso finaliza el tutorial "Definir una suscripción controlada por datos".</span><span class="sxs-lookup"><span data-stu-id="13463-174">This step concludes the tutorial "Defining a Data-Driven Subscription".</span></span> <span data-ttu-id="13463-175">Para obtener más información sobre otros [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] tutoriales, vea [Reporting Services tutoriales &#40;SSRS&#41;](../reporting-services/reporting-services-tutorials-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="13463-175">To learn more about other [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] tutorials, see [Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services/reporting-services-tutorials-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13463-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13463-176">See Also</span></span>  
 <span data-ttu-id="13463-177">[Crear una suscripción controlada por datos &#40;Tutorial de SSRS&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="13463-177">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="13463-178">[Suscripciones y entrega &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="13463-178">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 <span data-ttu-id="13463-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="13463-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="13463-180">[Crear, modificar y eliminar una suscripción controlada por datos](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="13463-180">[Create, Modify, and Delete a Data-Driven Subscription](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span></span>  
 [<span data-ttu-id="13463-181">Usar un origen de datos externo para obtener información de los suscriptores &#40;suscripción controlada por datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13463-181">Use an External Data Source for Subscriber Data &#40;Data-Driven Subscription&#41;</span></span>](subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md)  
  
  
