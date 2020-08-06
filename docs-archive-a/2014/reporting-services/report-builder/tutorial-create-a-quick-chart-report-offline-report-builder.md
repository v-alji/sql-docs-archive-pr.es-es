---
title: 'Tutorial: Creación de un informe de gráfico rápido sin conexión (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports, creating
- tutorials, getting started
- creating reports
ms.assetid: 6b1db67a-cf75-494c-b70c-09f1e6a8d414
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51a9e648550a0108f47e3d93d75267ab0c1c24f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670816"
---
# <a name="tutorial-create-a-quick-chart-report-offline-report-builder"></a><span data-ttu-id="3c98a-102">Tutorial: Crear un informe de gráfico rápido sin conexión (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="3c98a-102">Tutorial: Create a Quick Chart Report Offline (Report Builder)</span></span>
  <span data-ttu-id="3c98a-103">En este tutorial, creará un gráfico circular usando un asistente y, a continuación, lo modificará un poco, solo para hacerse una idea de las posibilidades.</span><span class="sxs-lookup"><span data-stu-id="3c98a-103">In this tutorial, you'll create a pie chart by using a wizard, and then you'll modify it a little, just to get an idea of what's possible.</span></span> <span data-ttu-id="3c98a-104">Puede hacerlo de dos maneras diferentes:</span><span class="sxs-lookup"><span data-stu-id="3c98a-104">You can do this tutorial two different ways.</span></span> <span data-ttu-id="3c98a-105">Ambos métodos tienen el mismo resultado: un gráfico circular como el de la siguiente ilustración:</span><span class="sxs-lookup"><span data-stu-id="3c98a-105">Both methods have the same outcome-a pie chart like the one in the following illustration:</span></span>

 <span data-ttu-id="3c98a-106">!["Mi primer gráfico circular" en la vista Ejecutar](../media/rs-my1stpierunview.gif "Mi primer gráfico circular en la vista ejecutar")</span><span class="sxs-lookup"><span data-stu-id="3c98a-106">!["My First Pie Chart" in Run view](../media/rs-my1stpierunview.gif "My First Pie Chart in Run view")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c98a-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3c98a-107">Prerequisites</span></span>
 <span data-ttu-id="3c98a-108">Si usa datos XML o una consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)], necesita tener acceso al Generador de informes [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c98a-108">Whether you use XML data or a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, you need to have access to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder.</span></span> <span data-ttu-id="3c98a-109">Puede ejecutar la versión independiente o la versión de ClickOnce disponible en el Administrador de informes o en un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c98a-109">You can run the stand-alone version or the ClickOnce version available from Report Manager or a SharePoint site.</span></span> <span data-ttu-id="3c98a-110">Solo el primer paso, cómo abrir Generador de informes, es diferente para las versiones de ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="3c98a-110">Only the first step, how to open Report Builder, is different for ClickOnce versions.</span></span> <span data-ttu-id="3c98a-111">Para obtener más información, vea [instalar, desinstalar y generador de informes soporte técnico](../install-uninstall-and-report-builder-support.md).</span><span class="sxs-lookup"><span data-stu-id="3c98a-111">For more information, see [Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md).</span></span>

##  <a name="two-ways-to-do-this-tutorial"></a><a name="TwoWays"></a> <span data-ttu-id="3c98a-112">Dos maneras de hacer este tutorial</span><span class="sxs-lookup"><span data-stu-id="3c98a-112">Two Ways To Do This Tutorial</span></span>

-   [<span data-ttu-id="3c98a-113">Crear el gráfico circular con datos XML</span><span class="sxs-lookup"><span data-stu-id="3c98a-113">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

-   [<span data-ttu-id="3c98a-114">Crear el gráfico circular con una consulta de Transact-SQL que contenga datos</span><span class="sxs-lookup"><span data-stu-id="3c98a-114">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

### <a name="using-xml-data-for-this-tutorial"></a><span data-ttu-id="3c98a-115">Usar datos XML para este tutorial</span><span class="sxs-lookup"><span data-stu-id="3c98a-115">Using XML data for this tutorial</span></span>
 <span data-ttu-id="3c98a-116">Puede utilizar los datos XML que copia de este tema y pegarlos en el asistente.</span><span class="sxs-lookup"><span data-stu-id="3c98a-116">You can use XML data that you copy from this topic and paste into the wizard.</span></span> <span data-ttu-id="3c98a-117">No necesita estar conectado a un servidor de informes o a un servidor de informes en modo integrado de SharePoint, y no necesita acceso a una instancia de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c98a-117">You don't need to be connected to a report server or a report server in SharePoint integrated mode, and you don't need access to an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>

 [<span data-ttu-id="3c98a-118">Crear el gráfico circular con datos XML</span><span class="sxs-lookup"><span data-stu-id="3c98a-118">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

### <a name="using-a-transact-sql-query-that-contains-data-for-this-tutorial"></a><span data-ttu-id="3c98a-119">Usar una consulta Transact SQL que contenga los datos de este tutorial</span><span class="sxs-lookup"><span data-stu-id="3c98a-119">Using a Transact-SQL query that contains data for this tutorial</span></span>
 <span data-ttu-id="3c98a-120">Puede copiar desde este tema una consulta con datos incluidos en él y pegarlos en el asistente.</span><span class="sxs-lookup"><span data-stu-id="3c98a-120">You can copy a query with data included in it from this topic and paste it into the wizard.</span></span> <span data-ttu-id="3c98a-121">Necesitará el nombre de una instancia de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] y credenciales suficiente para el acceso de solo lectura a cualquier base de datos.</span><span class="sxs-lookup"><span data-stu-id="3c98a-121">You will need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="3c98a-122">La consulta del conjunto de datos en el tutorial usa datos literales, pero la consulta debe ser procesada por una instancia de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] para que devuelva los metadatos requeridos por un conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="3c98a-122">The dataset query in the tutorial uses literal data, but the query must be processed by an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to return the metadata that is required for a report dataset.</span></span>

 <span data-ttu-id="3c98a-123">La ventaja de usar la consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)] es que todos los demás tutoriales del Generador de informes usan el mismo método, de modo que cuando realice los otros tutoriales ya sabrá lo que debe hacer.</span><span class="sxs-lookup"><span data-stu-id="3c98a-123">The advantage of using the [!INCLUDE[tsql](../../../includes/tsql-md.md)] query is that all the other Report Builder tutorials use the same method, so when you do the other tutorials, you will already know what to do.</span></span>

 <span data-ttu-id="3c98a-124">La consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)] TSQL requiere otros requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="3c98a-124">The [!INCLUDE[tsql](../../../includes/tsql-md.md)] query does require a few other prerequisites.</span></span> <span data-ttu-id="3c98a-125">Para obtener más información, consulte [Requisitos previos para los tutoriales&#40;Generador de informes&#41;](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="3c98a-125">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

 [<span data-ttu-id="3c98a-126">Crear el gráfico circular con una consulta de Transact-SQL que contenga datos</span><span class="sxs-lookup"><span data-stu-id="3c98a-126">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

## <a name="also-in-this-article"></a><span data-ttu-id="3c98a-127">También en este artículo</span><span class="sxs-lookup"><span data-stu-id="3c98a-127">Also in This Article</span></span>
 [<span data-ttu-id="3c98a-128">Después de ejecutar el asistente</span><span class="sxs-lookup"><span data-stu-id="3c98a-128">After You Run the Wizard</span></span>](#AfterWizard)

 [<span data-ttu-id="3c98a-129">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3c98a-129">What's Next</span></span>](#WhatsNext)

##  <a name="creating-the-pie-chart-with-xml-data"></a><a name="CreatePieChartXML"></a><span data-ttu-id="3c98a-130">Crear el gráfico circular con datos XML</span><span class="sxs-lookup"><span data-stu-id="3c98a-130">Creating the pie chart with XML data</span></span>

#### <a name="to-create-the-pie-chart-with-xml-data"></a><span data-ttu-id="3c98a-131">Para crear el gráfico circular con datos XML</span><span class="sxs-lookup"><span data-stu-id="3c98a-131">To create the pie chart with XML data</span></span>

1.  <span data-ttu-id="3c98a-132">Haga clic en **Inicio**, seleccione **Programas**, **Generador de informes de Microsoft SQL Server 2012**y, a continuación, haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

     <span data-ttu-id="3c98a-133">Aparece el cuadro de diálogo **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="3c98a-133">The **Getting Started** dialog box appears.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="3c98a-134">Si el cuadro de diálogo **Introducción** no aparece, en el botón **generador de informes** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-134">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>

2.  <span data-ttu-id="3c98a-135">En el panel de la izquierda, compruebe que está seleccionada la opción **Informe** .</span><span class="sxs-lookup"><span data-stu-id="3c98a-135">In the left pane, verify that **Report** is selected.</span></span>

3.  <span data-ttu-id="3c98a-136">En el panel derecho, haga clic en **Asistente para gráfico**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-136">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="3c98a-137">En la página **Elegir un conjunto de datos** , haga clic en **Crear un conjunto de datos**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-137">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="3c98a-138">En la página **Elegir una conexión a un origen de datos** , haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-138">In the **Choose a connection to a data source** page, click **New**.</span></span>

     <span data-ttu-id="3c98a-139">Se abre el cuadro de diálogo **Propiedades del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="3c98a-139">The **Data Source Properties** dialog box opens.</span></span>

6.  <span data-ttu-id="3c98a-140">Puede dar el nombre que desee a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3c98a-140">You can name a data source anything you want.</span></span> <span data-ttu-id="3c98a-141">En el cuadro **Nombre** , escriba: **MiGráficoCircular**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-141">In the **Name** box, type **MyPieChart**.</span></span>

7.  <span data-ttu-id="3c98a-142">En el cuadro **Seleccionar tipo de conexión** , haga clic en **xml.**</span><span class="sxs-lookup"><span data-stu-id="3c98a-142">In the **Select connection type** box, click **XML.**</span></span>

8.  <span data-ttu-id="3c98a-143">Haga clic en la pestaña **credenciales** y seleccione **usar usuario de Windows actual. Es posible que se requiera la delegación Kerberos**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-143">Click the **Credentials** tab, select **Use current Windows user. Kerberos delegation may be required**, and then click **OK**.</span></span>

9. <span data-ttu-id="3c98a-144">En la página **Elegir una conexión a un origen de datos** , haga clic en **miGráficoCircular**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-144">In the **Choose a connection to a data source** page, click **MyPieChart**, and then click **Next**.</span></span>

10. <span data-ttu-id="3c98a-145">Copie el texto siguiente y péguelo en el cuadro grande del centro de la página **diseñar una consulta** .</span><span class="sxs-lookup"><span data-stu-id="3c98a-145">Copy the following text and paste it in the large box in the center of the **Design a query** page.</span></span>

    ```
    <Query>
    <ElementPath>Root /S  {@Sales (Integer)} /C {@FullName} </ElementPath>
    <XmlData>
    <Root>
    <S Sales="150">
      <C FullName="Jae Pak" />
    </S>
    <S Sales="350">
      <C FullName="Jillian  Carson" />
    </S>
    <S Sales="250">
      <C FullName="Linda C Mitchell" />
    </S>
    <S Sales="500">
      <C FullName="Michael Blythe" />
    </S>
    <S Sales="450">
      <C FullName="Ranjit Varkey" />
    </S>
    </Root>
    </XmlData>
    </Query>
    ```

11. <span data-ttu-id="3c98a-146">(Opcional) Haga clic en el botón Ejecutar (**!**) para ver los datos en los que se basará su gráfico.</span><span class="sxs-lookup"><span data-stu-id="3c98a-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

12. <span data-ttu-id="3c98a-147">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-147">Click **Next**.</span></span>

13. <span data-ttu-id="3c98a-148">En la página **Elegir un tipo de gráfico** , haga clic en **Circular**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-148">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

14. <span data-ttu-id="3c98a-149">En la página **Organizar campos del gráfico**, haga doble clic en el campo **Ventas** en el cuadro **Campos disponibles**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-149">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="3c98a-150">Observe que se desplaza automáticamente al cuadro de diálogo **Valores** , porque es un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="3c98a-150">Note that it automatically moves to the **Values** box, because it is a numerical value.</span></span>

15. <span data-ttu-id="3c98a-151">Arrastre el campo **FullName** desde el cuadro **Campos disponibles** hasta **Categorías** (o haga doble clic en él; se desplazará al cuadro **Categorías**) y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-151">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

16. <span data-ttu-id="3c98a-152">En la página **elegir un estilo** , **océano** está seleccionado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3c98a-152">In the **Choose a style** page, **Ocean** is selected by default.</span></span> <span data-ttu-id="3c98a-153">Haga clic en otros estilos para ver su apariencia.</span><span class="sxs-lookup"><span data-stu-id="3c98a-153">Click the other styles to see what they look like.</span></span>

17. <span data-ttu-id="3c98a-154">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="3c98a-154">Click **Finish**.</span></span>

     <span data-ttu-id="3c98a-155">Se ve ahora el nuevo informe de gráfico circular en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="3c98a-155">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="3c98a-156">Lo que ve es figurativo.</span><span class="sxs-lookup"><span data-stu-id="3c98a-156">What you see is representational.</span></span> <span data-ttu-id="3c98a-157">La leyenda dice Full Name 1, Full Name 2, etc., en lugar de los nombres de los vendedores, y el tamaño de los sectores del gráfico circular no es preciso.</span><span class="sxs-lookup"><span data-stu-id="3c98a-157">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="3c98a-158">Únicamente es para que se haga una idea de cómo será el informe.</span><span class="sxs-lookup"><span data-stu-id="3c98a-158">This is just to give you an idea of what your report will look like.</span></span>

18. <span data-ttu-id="3c98a-159">Para ver el gráfico circular real, haga clic en **Ejecutar** en la pestaña **Inicio** de la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="3c98a-159">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="3c98a-160">![Icono de flecha usado con el vínculo volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [volver al principio](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="3c98a-160">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="creating-the-pie-chart-with-a-tsql-query"></a><a name="CreatePieQueryData"></a> <span data-ttu-id="3c98a-161">Crear el gráfico circular con una consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c98a-161">Creating the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query</span></span>

#### <a name="to-create-the-pie-chart-with-a-tsql-query-that-contains-data"></a><span data-ttu-id="3c98a-162">Para crear el gráfico circular con una consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)] que contenga los datos</span><span class="sxs-lookup"><span data-stu-id="3c98a-162">To create the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query that contains data</span></span>

1.  <span data-ttu-id="3c98a-163">Haga clic en **Inicio**, seleccione **Programas**, **Generador de informes de Microsoft SQL Server 2012**y, a continuación, haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-163">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

2.  <span data-ttu-id="3c98a-164">En el cuadro de diálogo **nuevo informe o conjunto** de propiedades, compruebe que **Informe** está seleccionado en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="3c98a-164">In the **New report or dataset** dialog box, verify that **Report** is selected in the left pane.</span></span>

3.  <span data-ttu-id="3c98a-165">En el panel derecho, haga clic en **Asistente para gráfico**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-165">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="3c98a-166">En la página **Elegir un conjunto de datos** , haga clic en **Crear un conjunto de datos**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-166">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="3c98a-167">En la página **Elegir una conexión a un origen de datos** , seleccione un origen de datos existente o vaya al servidor de informes y seleccione un origen de datos y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-167">In the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="3c98a-168">Puede que necesite escribir un nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="3c98a-168">You may need to enter a user name and password.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="3c98a-169">El origen de datos que elija no importa, con tal de que tenga los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="3c98a-169">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="3c98a-170">No está recibiendo datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3c98a-170">You will not be getting data from the data source.</span></span> <span data-ttu-id="3c98a-171">Para obtener más información, consulte [Requisitos previos para los tutoriales&#40;Generador de informes&#41;](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="3c98a-171">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

6.  <span data-ttu-id="3c98a-172">En la página **diseñar una consulta** , haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-172">On the **Design a Query** page, click **Edit as Text**.</span></span>

7.  <span data-ttu-id="3c98a-173">Pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="3c98a-173">Paste the following query into the query pane:</span></span>

    ```
    SELECT 150 AS Sales, 'Jae Pak' AS FullName 
    UNION SELECT 350 AS Sales, 'Jillian Carson' AS FullName 
    UNION SELECT 250 AS Sales, 'Linda C Mitchell' AS FullName 
    UNION SELECT 500 AS Sales, 'Michael Blythe' AS FullName 
    UNION SELECT 450 AS Sales, 'Ranjit Varkey' AS FullName 
    ```

8.  <span data-ttu-id="3c98a-174">(Opcional) Haga clic en el botón Ejecutar (**!**) para ver los datos en los que se basará su gráfico.</span><span class="sxs-lookup"><span data-stu-id="3c98a-174">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

9. <span data-ttu-id="3c98a-175">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-175">Click **Next**.</span></span>

10. <span data-ttu-id="3c98a-176">En la página **Elegir un tipo de gráfico** , haga clic en **Circular**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-176">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

11. <span data-ttu-id="3c98a-177">En la página **Organizar campos del gráfico**, haga doble clic en el campo **Ventas** en el cuadro **Campos disponibles**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-177">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="3c98a-178">Observe que se desplaza automáticamente al cuadro **Valores** , porque es un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="3c98a-178">Note that it automatically moves to the **Values** box, because it's a numerical value.</span></span>

12. <span data-ttu-id="3c98a-179">Arrastre el campo **FullName** desde el cuadro **Campos disponibles** hasta **Categorías** (o haga doble clic en él; se desplazará al cuadro **Categorías**) y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-179">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

13. <span data-ttu-id="3c98a-180">En la página **Elegir un estilo** , Océano está seleccionado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3c98a-180">In the **Choose a style** page, Ocean is selected by default.</span></span> <span data-ttu-id="3c98a-181">Haga clic en otros estilos para ver su apariencia.</span><span class="sxs-lookup"><span data-stu-id="3c98a-181">Click the other styles to see what they look like.</span></span>

14. <span data-ttu-id="3c98a-182">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="3c98a-182">Click **Finish**.</span></span>

     <span data-ttu-id="3c98a-183">Se ve ahora el nuevo informe de gráfico circular en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="3c98a-183">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="3c98a-184">Lo que ve es figurativo.</span><span class="sxs-lookup"><span data-stu-id="3c98a-184">What you see is representational.</span></span> <span data-ttu-id="3c98a-185">La leyenda dice Full Name 1, Full Name 2, etc., en lugar de los nombres de los vendedores, y el tamaño de los sectores del gráfico circular no es preciso.</span><span class="sxs-lookup"><span data-stu-id="3c98a-185">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="3c98a-186">Únicamente es para que se haga una idea de cómo será el informe.</span><span class="sxs-lookup"><span data-stu-id="3c98a-186">This is just to give you an idea of what your report will look like.</span></span>

15. <span data-ttu-id="3c98a-187">Para ver el gráfico circular real, haga clic en **Ejecutar** en la pestaña **Inicio** de la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="3c98a-187">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="3c98a-188">![Icono de flecha usado con el vínculo volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [volver al principio](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="3c98a-188">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="after-you-run-the-wizard"></a><a name="AfterWizard"></a><span data-ttu-id="3c98a-189">Después de ejecutar el asistente</span><span class="sxs-lookup"><span data-stu-id="3c98a-189">After You Run the Wizard</span></span>
 <span data-ttu-id="3c98a-190">Ahora que tiene el informe del gráfico circular, puede trabajar con él.</span><span class="sxs-lookup"><span data-stu-id="3c98a-190">Now that you have your pie chart report, you can play with it.</span></span> <span data-ttu-id="3c98a-191">En la pestaña **Ejecutar** de la cinta de opciones, haga clic en **Diseño**, de modo que pueda seguir modificándolo.</span><span class="sxs-lookup"><span data-stu-id="3c98a-191">On the **Run** tab of the Ribbon, click **Design**, so you can continue modifying it.</span></span>

### <a name="make-the-chart-bigger"></a><span data-ttu-id="3c98a-192">Agrandar el gráfico</span><span class="sxs-lookup"><span data-stu-id="3c98a-192">Make the chart bigger</span></span>
 <span data-ttu-id="3c98a-193">Quizá quiera que el gráfico circular sea más grande.</span><span class="sxs-lookup"><span data-stu-id="3c98a-193">You may want the pie chart to be bigger.</span></span> <span data-ttu-id="3c98a-194">Haga clic en el gráfico, pero no en ningún elemento del gráfico, para seleccionarlo y arrastre la esquina inferior derecha para cambiar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="3c98a-194">Click the chart, but not on any element in the chart, to select it and drag the lower-right corner to resize it.</span></span>

### <a name="add-a-report-title"></a><span data-ttu-id="3c98a-195">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="3c98a-195">Add a report title</span></span>
 <span data-ttu-id="3c98a-196">Seleccione las palabras **Título de gráfico** en la parte superior del gráfico y, a continuación, escriba un título, como **Gráfico circular de ventas**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-196">Select the words **Chart title** at the top of the chart, and then type a title, such as **Sales Pie Chart**.</span></span>

### <a name="add-percentages"></a><span data-ttu-id="3c98a-197">Agregar porcentajes</span><span class="sxs-lookup"><span data-stu-id="3c98a-197">Add percentages</span></span>

##### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="3c98a-198">Para mostrar los valores de porcentaje como etiquetas en un gráfico circular</span><span class="sxs-lookup"><span data-stu-id="3c98a-198">To display percentage values as labels on a pie chart</span></span>

1.  <span data-ttu-id="3c98a-199">Haga clic con el botón secundario en el gráfico circular y seleccione **Mostrar etiquetas de datos**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-199">Right-click on the pie chart and select **Show Data Labels**.</span></span> <span data-ttu-id="3c98a-200">Las etiquetas de datos aparecerán dentro de cada sector del gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="3c98a-200">The data labels should appear within each slice on the pie chart.</span></span>

2.  <span data-ttu-id="3c98a-201">Haga clic con el botón derecho en las etiquetas y seleccione Propiedades de la etiqueta de la **serie**.</span><span class="sxs-lookup"><span data-stu-id="3c98a-201">Right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="3c98a-202">Aparece el cuadro de diálogo **Propiedades de la etiqueta de la serie** .</span><span class="sxs-lookup"><span data-stu-id="3c98a-202">The **Series Label Properties** dialog box appears.</span></span>

3.  <span data-ttu-id="3c98a-203">Escriba `#PERCENT{P0}` para la opción **datos de etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="3c98a-203">Type `#PERCENT{P0}` for the **Label data** option.</span></span>

     <span data-ttu-id="3c98a-204">`{P0}` le da el porcentaje sin decimales.</span><span class="sxs-lookup"><span data-stu-id="3c98a-204">The `{P0}` gives you the percentage without decimal places.</span></span> <span data-ttu-id="3c98a-205">Si simplemente escribe `#PERCENT`, los números tendrán dos posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="3c98a-205">If you type just `#PERCENT`, your numbers will have two decimal places.</span></span> <span data-ttu-id="3c98a-206">`#PERCENT` es una palabra clave que realiza un cálculo o función automáticamente; hay muchas otras.</span><span class="sxs-lookup"><span data-stu-id="3c98a-206">`#PERCENT` is a keyword that performs a calculation or function for you; there are many others.</span></span>

 <span data-ttu-id="3c98a-207">Para obtener más información acerca de cómo personalizar las etiquetas del gráfico y las leyendas, consulte [Mostrar valores de porcentaje en un gráfico circular &#40;Generador de informes y SSRS&#41;](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) y [Cambiar el texto de un elemento de leyenda&#40;Generador de informes y SSRS&#41;](../report-design/chart-legend-change-item-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3c98a-207">For more information about customizing chart labels and legends, see [Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) and [Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](../report-design/chart-legend-change-item-text-report-builder.md).</span></span>

 <span data-ttu-id="3c98a-208">![Icono de flecha usado con el vínculo volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [volver al principio](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="3c98a-208">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="whats-next"></a><a name="WhatsNext"></a><span data-ttu-id="3c98a-209">¿Qué es lo próximo?</span><span class="sxs-lookup"><span data-stu-id="3c98a-209">What's Next?</span></span>
 <span data-ttu-id="3c98a-210">Ahora que ha creado su primer informe en el Generador de informes, está listo para leer los demás tutoriales y empezar a crear informes a partir de sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="3c98a-210">Now that you have created your first report in Report Builder, you are ready to try the other tutorials and to start creating reports from your own data.</span></span> <span data-ttu-id="3c98a-211">Para ejecutar Generador de informes, necesita permiso para obtener acceso a los orígenes de datos, como bases de datos, con una *cadena de conexión*, que realmente le conecta al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3c98a-211">To run Report Builder, you need permission to access your data sources, such as databases, with a *connection string*, which actually connects you to the data source.</span></span> <span data-ttu-id="3c98a-212">El administrador del sistema tiene esta información y puede facilitársela.</span><span class="sxs-lookup"><span data-stu-id="3c98a-212">Your system administrator will have this information and can set you up.</span></span>

 <span data-ttu-id="3c98a-213">Para trabajar con otros tutoriales, necesita el nombre de una instancia de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] y credenciales suficientes para el acceso de solo lectura a cualquier base de datos.</span><span class="sxs-lookup"><span data-stu-id="3c98a-213">To work through the other tutorials, you need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="3c98a-214">El administrador del sistema puede facilitárselo también.</span><span class="sxs-lookup"><span data-stu-id="3c98a-214">Your system administrator can also set that up for you.</span></span>

 <span data-ttu-id="3c98a-215">Finalmente, para guardar los informes en un servidor de informes o en un sitio de SharePoint integrado con un servidor de informes, necesitará la dirección URL y los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="3c98a-215">Finally, to save your reports to a report server or a SharePoint site that is integrated with a report server, you need the URL and permissions.</span></span> <span data-ttu-id="3c98a-216">Puede ejecutar cualquier informe que cree directamente desde su equipo, pero los informes tienen más funcionalidad cuando se ejecutan desde el servidor de informes o desde el sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c98a-216">You can run any report you create directly from your computer, but reports have more functionality when run from the report server or SharePoint site.</span></span> <span data-ttu-id="3c98a-217">Necesita permisos para ejecutar sus informes u otros desde el servidor de informes o desde el sitio de SharePoint donde estén publicados.</span><span class="sxs-lookup"><span data-stu-id="3c98a-217">You need permissions to run your reports or others from the report server or SharePoint site where they are published.</span></span> <span data-ttu-id="3c98a-218">Hable con el administrador del sistema para obtener acceso.</span><span class="sxs-lookup"><span data-stu-id="3c98a-218">Talk to your system administrator to obtain access.</span></span>

 <span data-ttu-id="3c98a-219">Podría resultarle de ayuda leer sobre algunos conceptos y términos antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="3c98a-219">It may help to read about some of the concepts and terms before you get started.</span></span> <span data-ttu-id="3c98a-220">Para obtener más información, vea [conceptos de creación de informes &#40;generador de informes y SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3c98a-220">For more information, see [Report Authoring Concepts &#40;Report Builder and SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="3c98a-221">Además, dedique algún tiempo al planeamiento antes de crear su primer informe.</span><span class="sxs-lookup"><span data-stu-id="3c98a-221">Also, spend some time planning, before you create your first report.</span></span> <span data-ttu-id="3c98a-222">Será tiempo bien invertido.</span><span class="sxs-lookup"><span data-stu-id="3c98a-222">It will be time well spent.</span></span> <span data-ttu-id="3c98a-223">Para obtener más información, vea [planear un informe &#40;Generador de informes&#41;](../report-design/planning-a-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3c98a-223">For more information, see [Planning a Report &#40;Report Builder&#41;](../report-design/planning-a-report-report-builder.md).</span></span>

 <span data-ttu-id="3c98a-224">![Icono de flecha usado con el vínculo volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [volver al principio](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="3c98a-224">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

## <a name="see-also"></a><span data-ttu-id="3c98a-225">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c98a-225">See Also</span></span>
 <span data-ttu-id="3c98a-226">[Tutoriales &#40;Generador de informes&#41;](../report-builder-tutorials.md) [Generador de informes en SQL Server 2014](report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="3c98a-226">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder-in-sql-server-2016.md)</span></span>


