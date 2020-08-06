---
title: Crear una alerta de datos en el Diseñador de alertas de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8464ab9d-afe1-4490-955f-9f3319bcbf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19c3001d4663848c009a353baa068f237d4a0b5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747519"
---
# <a name="create-a-data-alert-in-data-alert-designer"></a><span data-ttu-id="f7c73-102">Crear una alerta de datos en el Diseñador de alertas de datos</span><span class="sxs-lookup"><span data-stu-id="f7c73-102">Create a Data Alert in Data Alert Designer</span></span>
  <span data-ttu-id="f7c73-103">Las definiciones de alertas de datos se crean en el Diseñador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="f7c73-103">You create data alert definitions in Data Alert Designer.</span></span> <span data-ttu-id="f7c73-104">Una vez guardadas las definiciones de alertas, es posible volver a abrirlas, modificarlas y volver a guardarlas en el Diseñador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="f7c73-104">After you save the alert definitions, you can reopen, edit, and then resave them in Data Alert Designer.</span></span> <span data-ttu-id="f7c73-105">Para más información sobre cómo editar definiciones de alertas, vea [Administrar mis alertas de datos en el Administrador de alertas de datos](manage-my-data-alerts-in-data-alert-manager.md) y [Editar una alerta de datos en el Diseñador de alertas](edit-a-data-alert-in-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="f7c73-105">For information about editing alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md) and [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md).</span></span>

### <a name="to-create-a-data-alert-definition"></a><span data-ttu-id="f7c73-106">Para crear una definición de alertas de datos</span><span class="sxs-lookup"><span data-stu-id="f7c73-106">To create a data alert definition</span></span>

1.  <span data-ttu-id="f7c73-107">Busque la biblioteca de SharePoint que contiene el informe para el que desea crear una definición de alerta de datos.</span><span class="sxs-lookup"><span data-stu-id="f7c73-107">Locate the SharePoint library that contains the report that you want to create a data alert definition for.</span></span>

2.  <span data-ttu-id="f7c73-108">Haga clic en el informe.</span><span class="sxs-lookup"><span data-stu-id="f7c73-108">Click the report.</span></span>

     <span data-ttu-id="f7c73-109">El informe se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="f7c73-109">The report runs.</span></span> <span data-ttu-id="f7c73-110">Si el informe tiene parámetros, compruebe que el informe muestra los datos para los que desea recibir mensajes de alerta.</span><span class="sxs-lookup"><span data-stu-id="f7c73-110">If the report is parameterized, verify that the report shows the data that you want to receive alert messages about.</span></span> <span data-ttu-id="f7c73-111">Si no ve las columnas o los valores que le interesan, puede que desee volver a ejecutar el informe con valores de parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="f7c73-111">If you do not see the columns or values you are interested in, you might want to rerun the report, using different parameter values.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f7c73-112">Los valores de parámetro que eligió para ejecutar el informe se guardan en la definición de alerta y se usarán cuando se vuelva a ejecutar el informe durante el procesamiento de la definición de alerta.</span><span class="sxs-lookup"><span data-stu-id="f7c73-112">The parameter values you chose to run the report are saved in the alert definition and will be used when report is rerun as a step in processing the alert definition.</span></span> <span data-ttu-id="f7c73-113">Para utilizar valores de parámetro diferentes, debe crear una nueva definición de alerta.</span><span class="sxs-lookup"><span data-stu-id="f7c73-113">To use different parameter values, you must create a new alert definition.</span></span>

3.  <span data-ttu-id="f7c73-114">En el menú **Acciones** , haga clic en **Nueva alerta de datos**.</span><span class="sxs-lookup"><span data-stu-id="f7c73-114">On the **Actions** menu, click **New Data Alert**.</span></span>

     <span data-ttu-id="f7c73-115">La imagen siguiente muestra el menú **Acciones** .</span><span class="sxs-lookup"><span data-stu-id="f7c73-115">The following picture shows the **Actions** menu.</span></span>

     <span data-ttu-id="f7c73-116">![Abrir el Diseñador de alertas desde la biblioteca de SharePoint](media/rs-openalertdesigneriw.gif "Abrir el Diseñador de alertas desde la biblioteca de SharePoint")</span><span class="sxs-lookup"><span data-stu-id="f7c73-116">![Open Alert Designer from SharePoint library](media/rs-openalertdesigneriw.gif "Open Alert Designer from SharePoint library")</span></span>

     <span data-ttu-id="f7c73-117">Se abre el Diseñador de alertas de datos y en él se muestra una tabla con las 100 primeras filas de la primera fuente de distribución de datos generada por el informe.</span><span class="sxs-lookup"><span data-stu-id="f7c73-117">The Data Alert Designer opens, showing the first 100 rows of the first data feed that the report generates in a table.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f7c73-118">Si no ve la opción **Nueva alerta de datos** , el servicio de alertas no está configurado en el sitio de SharePoint o la edición de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no incluye alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="f7c73-118">If you do not see the **New Data Alert** option, the alerting service is not configured on the SharePoint site or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] edition does not include data alerts.</span></span> <span data-ttu-id="f7c73-119">Para obtener más información, vea [Aplicaciones de servicio y servicio de SharePoint de Reporting Services](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span><span class="sxs-lookup"><span data-stu-id="f7c73-119">For more information, see [Reporting Services SharePoint Service and Service Applications](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span></span>
    > 
    >  <span data-ttu-id="f7c73-120">Si la opción **Nueva alerta de datos** aparece atenuada, el origen de datos del informe está configurado para utilizar las credenciales de seguridad integradas o para solicitar credenciales.</span><span class="sxs-lookup"><span data-stu-id="f7c73-120">If the **New Data Alert** option is grayed, the report data source is configured to use integrated security credentials or prompt for credentials.</span></span> <span data-ttu-id="f7c73-121">Para que la opción **Nueva alerta de datos** esté disponible, debe actualizar el origen de datos de modo que use las credenciales almacenadas o no use credenciales.</span><span class="sxs-lookup"><span data-stu-id="f7c73-121">To make the **New Data Alert** option available, you must update the data source to use stored credentials or no credentials.</span></span>

     <span data-ttu-id="f7c73-122">El nombre de la fuente de distribución de datos aparece en la lista desplegable **Nombre de los datos de informe** .</span><span class="sxs-lookup"><span data-stu-id="f7c73-122">The name of the data feed appears in **Report data name** drop-down list.</span></span>

4.  <span data-ttu-id="f7c73-123">De manera opcional, seleccione otra fuente de distribución de datos en la lista desplegable **Nombre de los datos de informe** .</span><span class="sxs-lookup"><span data-stu-id="f7c73-123">Optionally, select a different data feed in the **Report data name** drop-down list.</span></span>

     <span data-ttu-id="f7c73-124">Si no se genera ninguna fuente de distribución de datos a partir del informe, no puede crear una definición de alerta para el informe.</span><span class="sxs-lookup"><span data-stu-id="f7c73-124">If no data feed is generated from the report, you cannot create an alert definition for the report.</span></span> <span data-ttu-id="f7c73-125">El diseño del informe determina el contenido de cada fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="f7c73-125">The layout of the report determines the content of each data feed.</span></span> <span data-ttu-id="f7c73-126">Para más información, vea [Generar fuentes de distribución de datos a partir de informes &#40;Generador de informes y SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f7c73-126">For more information see, [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

5.  <span data-ttu-id="f7c73-127">Si lo desea, en el cuadro de texto **Nombre de alerta** , cambie el nombre predeterminado por otro más significativo.</span><span class="sxs-lookup"><span data-stu-id="f7c73-127">Optionally, in the **Alert name** text box, update the default name to be more meaningful.</span></span>

     <span data-ttu-id="f7c73-128">El nombre predeterminado de la definición de alerta es el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="f7c73-128">The default name of the alert definition is the name of the report.</span></span> <span data-ttu-id="f7c73-129">Los nombres de definición de alertas no tienen que ser únicos, lo que puede dificultar distinguirlos al ver la lista de alertas posteriormente en el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="f7c73-129">Alert definition names do not have to be unique, which can make it difficult to tell them apart when you later view the list of your alerts in Data Alert Manager.</span></span> <span data-ttu-id="f7c73-130">Se recomienda que utilice nombres significativos y únicos para sus definiciones de alerta.</span><span class="sxs-lookup"><span data-stu-id="f7c73-130">It is recommended that you use meaningful and unique names for your alert definitions.</span></span>

6.  <span data-ttu-id="f7c73-131">Si lo desea, cambie la opción de datos predeterminada de **algún dato de la fuente de distribución de datos tiene** a **ningún dato de la fuente de distribución de datos tiene**.</span><span class="sxs-lookup"><span data-stu-id="f7c73-131">Optionally, change the default data option from **any data in the data feed has** to **no data in the data feed has**.</span></span>

7.  <span data-ttu-id="f7c73-132">Haga clic en **Agregar regla**.</span><span class="sxs-lookup"><span data-stu-id="f7c73-132">Click **Add rule**.</span></span>

     <span data-ttu-id="f7c73-133">Aparece una lista de columnas en la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="f7c73-133">A list of the columns in the data feed appears.</span></span>

8.  <span data-ttu-id="f7c73-134">En la lista, seleccione la columna que desee utilizar en la regla y, a continuación, seleccione un operador de comparación y escriba el valor del umbral.</span><span class="sxs-lookup"><span data-stu-id="f7c73-134">In the list, select the column that you want to use in the rule, and then select a comparison operator and enter the threshold value.</span></span>

     <span data-ttu-id="f7c73-135">Se muestran distintos operadores de comparación en función del tipo de datos de la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f7c73-135">Depending on the data type of the selected column, different comparison operators are listed.</span></span> <span data-ttu-id="f7c73-136">Si la columna tiene un tipo de datos de fecha, se muestra un icono de calendario junto al valor del umbral de la regla.</span><span class="sxs-lookup"><span data-stu-id="f7c73-136">If the column has a date data type, a calendar icon displays next to threshold value for the rule.</span></span> <span data-ttu-id="f7c73-137">Puede especificar una fecha haciendo clic en una fecha en el calendario o escribiendo la fecha.</span><span class="sxs-lookup"><span data-stu-id="f7c73-137">You can enter a data by clicking a date in the calendar or typing the date.</span></span>

     <span data-ttu-id="f7c73-138">El Diseñador de alertas de datos proporciona dos modos de comparación: **Modo de entrada de valores** y **Modo de selección de campos**.</span><span class="sxs-lookup"><span data-stu-id="f7c73-138">Data Alert Designer provides two comparison modes: **Value Entry Mode** and **Field Selection Mode**.</span></span> <span data-ttu-id="f7c73-139">El modo predeterminado es **Modo de entrada de valores**.</span><span class="sxs-lookup"><span data-stu-id="f7c73-139">The default mode is **Value Entry Mode**.</span></span> <span data-ttu-id="f7c73-140">Solo puede agregar cláusulas OR cuando se encuentre en el **Modo de entrada de valores** y utilice la comparación **is** .</span><span class="sxs-lookup"><span data-stu-id="f7c73-140">You can add OR clauses only when you are in **Value Entry Mode** and are using the **is** comparison.</span></span>

9. <span data-ttu-id="f7c73-141">Para agregar una cláusula OR, haga clic en la flecha abajo y, después, haga clic en **Modo de entrada de valores**.</span><span class="sxs-lookup"><span data-stu-id="f7c73-141">To add an OR clause, click the down-arrow, and then click **Value Entry Mode**.</span></span>

10. <span data-ttu-id="f7c73-142">Escriba el valor de comparación.</span><span class="sxs-lookup"><span data-stu-id="f7c73-142">Type the comparison value.</span></span>

11. <span data-ttu-id="f7c73-143">De manera opcional, vuelva a hacer clic en los puntos suspensivos **(...)**.</span><span class="sxs-lookup"><span data-stu-id="f7c73-143">Optionally, click the ellipsis **(...)** again.</span></span>

     <span data-ttu-id="f7c73-144">Los puntos suspensivos **(...)** aparecen en la línea que contiene la primera cláusula.</span><span class="sxs-lookup"><span data-stu-id="f7c73-144">The ellipsis **(...)** appears on the line that contains the first clause.</span></span>

     <span data-ttu-id="f7c73-145">La cláusula OR se agrega debajo y dentro de la regla AND.</span><span class="sxs-lookup"><span data-stu-id="f7c73-145">An OR clause is added below and within the AND rule.</span></span>

12. <span data-ttu-id="f7c73-146">De manera opcional, haga clic en la flecha abajo, seleccione **Modo de selección de campos**y, después, seleccione una columna de la lista.</span><span class="sxs-lookup"><span data-stu-id="f7c73-146">Optionally, click the down-arrow, select **Field Selection Mode**, and then select a column in the list.</span></span>

     <span data-ttu-id="f7c73-147">Observará que el signo de puntos suspensivos **(...)** en los que se hace clic para agregar cláusulas OR ha desaparecido.</span><span class="sxs-lookup"><span data-stu-id="f7c73-147">You will notice that the ellipsis **(...)** that you click to add OR clauses has disappeared.</span></span>

13. <span data-ttu-id="f7c73-148">Si lo desea, haga clic en **Agregar regla** de nuevo para agregar más reglas.</span><span class="sxs-lookup"><span data-stu-id="f7c73-148">Optionally, click **Add rule** again to add additional rules.</span></span>

     <span data-ttu-id="f7c73-149">Las reglas se combinan mediante el operador lógico AND.</span><span class="sxs-lookup"><span data-stu-id="f7c73-149">The rules are combined by using the AND logical operator.</span></span>

14. <span data-ttu-id="f7c73-150">Seleccione una opción en la lista de periodicidad.</span><span class="sxs-lookup"><span data-stu-id="f7c73-150">Select an option in the recurrence list.</span></span> <span data-ttu-id="f7c73-151">Dependiendo del tipo de periodicidad, especifique un intervalo.</span><span class="sxs-lookup"><span data-stu-id="f7c73-151">Depending on the type of recurrence, enter an interval.</span></span>

15. <span data-ttu-id="f7c73-152">Si lo desea, haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="f7c73-152">Optionally, click **Advanced**.</span></span>

16. <span data-ttu-id="f7c73-153">Si lo desea, cambie la fecha en que se inicia el mensaje de alerta escribiendo otra fecha o abriendo el calendario y haciendo clic en una fecha en el mismo.</span><span class="sxs-lookup"><span data-stu-id="f7c73-153">Optionally, change the date that the alert message starts on by typing a different date or opening the calendar, and then clicking a date in the calendar.</span></span>

     <span data-ttu-id="f7c73-154">La fecha de inicio predeterminada es la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="f7c73-154">The default start date is the current date.</span></span>

17. <span data-ttu-id="f7c73-155">Si lo desea, active la casilla situada junto a **Detener alerta el**y después elija una fecha para detener el mensaje de alerta.</span><span class="sxs-lookup"><span data-stu-id="f7c73-155">Optionally, select the checkbox located next to **Stop alert on**, and then choose a date to stop the alert message.</span></span>

     <span data-ttu-id="f7c73-156">De forma predeterminada, un mensaje de alerta no tiene ninguna fecha de detención.</span><span class="sxs-lookup"><span data-stu-id="f7c73-156">By default, an alert message has no stop date.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f7c73-157">La detención de un mensaje de alerta no elimina la definición de alerta.</span><span class="sxs-lookup"><span data-stu-id="f7c73-157">Stopping an alert message does not delete the alert definition.</span></span> <span data-ttu-id="f7c73-158">Después de detener un mensaje de alerta, puede reiniciarlo actualizando las fechas de inicio y detención.</span><span class="sxs-lookup"><span data-stu-id="f7c73-158">After you stop an alert message, you can restart it by updating the start and stop dates.</span></span> <span data-ttu-id="f7c73-159">Para más información sobre cómo eliminar definiciones de alertas, vea [Administrar mis alertas de datos en el Administrador de alertas de datos](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f7c73-159">For information about deleting alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

18. <span data-ttu-id="f7c73-160">Si lo desea, desactive la casilla **Enviar mensaje solo si cambian los resultados** .</span><span class="sxs-lookup"><span data-stu-id="f7c73-160">Optionally, clear the **Send message only if results change** checkbox.</span></span>

     <span data-ttu-id="f7c73-161">Si envía mensajes de alerta con frecuencia, la información redundante puede que no sea del agrado de todos y debería desactivar esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f7c73-161">If you send alert messages frequently, redundant information might not be welcome and you should not clear this checkbox.</span></span>

19. <span data-ttu-id="f7c73-162">Escriba las direcciones de correo electrónico de los destinatarios del mensaje de alerta.</span><span class="sxs-lookup"><span data-stu-id="f7c73-162">Enter the email addresses of alert message recipients.</span></span> <span data-ttu-id="f7c73-163">Separe las direcciones con signos de punto y coma.</span><span class="sxs-lookup"><span data-stu-id="f7c73-163">Separate addresses with semicolons.</span></span>

     <span data-ttu-id="f7c73-164">Si la dirección de correo electrónico de la persona que ha creado la definición de alerta está disponible, se agrega al cuadro **Destinatarios** .</span><span class="sxs-lookup"><span data-stu-id="f7c73-164">If the email address of the person who created the alert definition is available, it is added to the **Recipient(s)** box.</span></span>

20. <span data-ttu-id="f7c73-165">Si lo desea, en el cuadro de texto **Asunto** , actualice la línea de asunto del mensaje de alerta.</span><span class="sxs-lookup"><span data-stu-id="f7c73-165">Optionally, in the **Subject** text box, update the Subject line of the alert message.</span></span>

     <span data-ttu-id="f7c73-166">El asunto predeterminado es \*\*alerta de datos \<data alert name> para \*\*.</span><span class="sxs-lookup"><span data-stu-id="f7c73-166">The default Subject is **Data alert for \<data alert name>**.</span></span>

21. <span data-ttu-id="f7c73-167">Si lo desea, en el cuadro de texto **Descripción** , escriba una descripción del mensaje de alerta.</span><span class="sxs-lookup"><span data-stu-id="f7c73-167">Optionally, in the **Description** text box, type a description of the alert message.</span></span>

22. <span data-ttu-id="f7c73-168">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="f7c73-168">Click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7c73-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7c73-169">See Also</span></span>
 <span data-ttu-id="f7c73-170">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Administrador de alertas de datos del diseñador de alertas de datos para los administradores de alertas](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services alertas de datos](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f7c73-170">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


