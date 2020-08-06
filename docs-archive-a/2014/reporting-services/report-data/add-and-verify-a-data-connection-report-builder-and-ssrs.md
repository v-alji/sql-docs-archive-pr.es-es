---
title: Agregar y comprobar una conexión de datos o un origen de datos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1d3b2573-e29d-480d-9dde-d26379c86618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d86b3e6598c12545f0e24ef1d162eeb1131bd15d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662611"
---
# <a name="add-and-verify-a-data-connection-or-data-source-report-builder-and-ssrs"></a><span data-ttu-id="b3ca0-102">Agregar y comprobar una conexión de datos o un origen de datos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="b3ca0-102">Add and Verify a Data Connection or Data Source (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b3ca0-103">En el Generador de informes, puede agregar un origen de datos compartido del servidor de informes o crear un origen de datos incrustado para el informe.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-103">In Report Builder, you can add a shared data source from the report server or create an embedded data source for your report.</span></span> <span data-ttu-id="b3ca0-104">En el Diseñador de informes, puede crear un origen de datos compartido o un origen de datos incrustado e implementarlo en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-104">In Report Designer, you can create a shared data source or an embedded data source and deploy it to a report server.</span></span>  
  
 <span data-ttu-id="b3ca0-105">Para agregar un origen de datos compartido al informe, busque un servidor de informes y seleccione un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-105">To add a shared data source to your report, browse to a report server and select a shared data source.</span></span> <span data-ttu-id="b3ca0-106">El origen de datos compartido del informe señala a la definición del origen de datos compartido en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-106">The shared data source in your report points to the shared data source definition on the report server.</span></span>  
  
 <span data-ttu-id="b3ca0-107">Para crear un origen de datos incrustado, debe disponer de la información de la conexión al origen de datos externo y saber qué permisos necesita para el acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-107">To create an embedded data source, you must have connection information to the external source of data and you must know which permissions you need to access the data.</span></span> <span data-ttu-id="b3ca0-108">Esta información normalmente procede del propietario del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-108">This information usually comes from the owner of the data source.</span></span> <span data-ttu-id="b3ca0-109">Puede probar la conexión para comprobar que las credenciales que se especifican son suficientes.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-109">You can test the connection to verify that the credentials that are specified are sufficient.</span></span>  
  
 <span data-ttu-id="b3ca0-110">Para obtener más información, vea [Conexiones de datos, orígenes de datos y cadenas de conexión (Generador de informes y SSRS)](../data-connections-data-sources-and-connection-strings-in-report-builder.md) y [Especificar credenciales en el Generador de informes](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b3ca0-110">For more information, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) and [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-reference-to-a-shared-data-source"></a><span data-ttu-id="b3ca0-111">Para crear una referencia a un origen de datos compartido</span><span class="sxs-lookup"><span data-stu-id="b3ca0-111">To create a reference to a shared data source</span></span>  
  
1.  <span data-ttu-id="b3ca0-112">En la barra de herramientas del panel Datos de informe, haga clic en **Nuevo** y, a continuación, haga clic en **Origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-112">On the toolbar in the Report Data pane, click **New,** and then click **Data Source**.</span></span> <span data-ttu-id="b3ca0-113">Se abre el cuadro de diálogo **Propiedades del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="b3ca0-113">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="b3ca0-114">En el cuadro de texto **Nombre** , escriba un nombre para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-114">In the **Name** text box, type a name for the data source.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b3ca0-115">Este nombre se guarda en la definición de informe local.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-115">This name is saved in the local report definition.</span></span> <span data-ttu-id="b3ca0-116">No es el nombre del origen de datos compartido del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-116">This name is not the name of the shared data source on the report server.</span></span>  
  
3.  <span data-ttu-id="b3ca0-117">Seleccione **Usar una conexión compartida en el modelo de informe**.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-117">Select **Use a shared connection or report model**.</span></span> <span data-ttu-id="b3ca0-118">Aparece la lista de modelos de informe y orígenes de datos compartidos usados recientemente.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-118">The list of recently used shared data sources and report models appears.</span></span> <span data-ttu-id="b3ca0-119">Para seleccionar uno de un servidor de informes, haga clic en **Examinar** y busque la carpeta del servidor de informes en la que están disponibles los orígenes de datos compartidos.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-119">To select one from a report server, click **Browse** and browse to the folder on the report server where shared data sources are available.</span></span>  
  
4.  <span data-ttu-id="b3ca0-120">Seleccione el origen de datos compartido y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-120">Select the shared data source and then click **Open**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="b3ca0-121">El origen de datos aparece en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-121">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="b3ca0-122">Para crear un origen de datos incrustado</span><span class="sxs-lookup"><span data-stu-id="b3ca0-122">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="b3ca0-123">En la barra de herramientas del panel datos de informe, haga clic en **nuevo**y, a continuación, haga clic en **origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-123">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span> <span data-ttu-id="b3ca0-124">Se abre el cuadro de diálogo **Propiedades del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="b3ca0-124">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="b3ca0-125">En el cuadro de texto **Nombre** , escriba un nombre para el origen de datos o acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-125">In the **Name** text box, type a name for the data source or accept the default.</span></span>  
  
3.  <span data-ttu-id="b3ca0-126">Compruebe que la casilla **Usar una conexión incrustada en el informe** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-126">Verify that **Use a connection embedded in my report** is selected.</span></span>  
  
    1.  <span data-ttu-id="b3ca0-127">En la lista desplegable **Seleccionar el tipo de conexión** , seleccione un tipo de origen de datos (por ejemplo, **Microsoft SQL Server** o **OLE DB**).</span><span class="sxs-lookup"><span data-stu-id="b3ca0-127">From the **Select connection type** drop-down list, select a data source type; for example, **Microsoft SQL Server** or **OLE DB**.</span></span>  
  
    2.  <span data-ttu-id="b3ca0-128">Especifique una cadena de conexión usando una de las alternativas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3ca0-128">Specify a connection string by using one of the following alternatives:</span></span>  
  
    -   <span data-ttu-id="b3ca0-129">Escriba la cadena de conexión directamente en el cuadro de texto **Cadena de conexión** .</span><span class="sxs-lookup"><span data-stu-id="b3ca0-129">Type the connection string directly in the **Connection string** text box.</span></span> <span data-ttu-id="b3ca0-130">Para obtener ejemplos de cadenas de conexión, vea [Conexiones de datos, orígenes de datos y cadenas de conexión en el Generador de informes](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b3ca0-130">For a list of example connection strings, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
    -   <span data-ttu-id="b3ca0-131">Haga clic en el botón de expresión (**fx** ) para crear una expresión que dé como resultado una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-131">Click the expression (**fx)** button to create an expression that evaluates to a connection string.</span></span> <span data-ttu-id="b3ca0-132">En el cuadro de diálogo **Expresión** , escriba la expresión en el panel Expresión.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-132">In the **Expression** dialog box, type the expression in the Expression pane.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    -   <span data-ttu-id="b3ca0-133">Haga clic en **Generar** para abrir el cuadro de diálogo **Propiedades de conexión** correspondiente al tipo de origen de datos que eligió en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-133">Click **Build** to open the **Connection Properties** dialog box for the data source type that you chose in step 2.</span></span>  
  
         <span data-ttu-id="b3ca0-134">Rellene los campos del cuadro de diálogo **Propiedades de conexión** según corresponda para el tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-134">Fill in the fields in the **Connection Properties** dialog box as appropriate for the data source type.</span></span> <span data-ttu-id="b3ca0-135">Las propiedades de conexión incluyen el tipo de origen de datos, el nombre del origen de datos, y las credenciales que se deben usar.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-135">Connection properties include the type of data source, the name of the data source, and the credentials to use.</span></span> <span data-ttu-id="b3ca0-136">Después de especificar los valores en este cuadro de diálogo, haga clic en **Probar conexión** para comprobar que el origen de datos está disponible y que las credenciales que especificó son correctas.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-136">After you specify values in this dialog box, click **Test Connection** to verify that the data source is available and that the credentials you specified are correct.</span></span>  
  
4.  <span data-ttu-id="b3ca0-137">Haga clic en **Credenciales**.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-137">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="b3ca0-138">Especifique las credenciales que se deben usar para este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-138">Specify the credentials to use for this data source.</span></span> <span data-ttu-id="b3ca0-139">El propietario del origen de datos elige el tipo de credenciales que se admiten.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-139">The owner of the data source chooses the type of credentials that are supported.</span></span> <span data-ttu-id="b3ca0-140">En algunos casos, el propietario del origen de datos mantiene un origen de datos compartido en un servidor de informes y configura el origen de datos con credenciales que puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-140">In some cases, the owner of the data source maintains a shared data source on a report server and configures the data source with credentials that you can use.</span></span> <span data-ttu-id="b3ca0-141">Póngase en contacto con el propietario del origen de datos para obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-141">Contact the data source owner for this information.</span></span> <span data-ttu-id="b3ca0-142">Para más información, vea [Especificar credenciales en el Generador de informes](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b3ca0-142">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="b3ca0-143">El origen de datos aparece en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-143">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-verify-a-data-connection"></a><span data-ttu-id="b3ca0-144">Para comprobar una conexión de datos</span><span class="sxs-lookup"><span data-stu-id="b3ca0-144">To verify a data connection</span></span>  
  
1.  <span data-ttu-id="b3ca0-145">En la barra de herramientas del panel Datos de informe, haga doble clic en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-145">On the toolbar in the Report Data pane, double-click the data source.</span></span> <span data-ttu-id="b3ca0-146">Se abre el cuadro de diálogo **Propiedades del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="b3ca0-146">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="b3ca0-147">Haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-147">Click **Test Connection**.</span></span>  
  
3.  <span data-ttu-id="b3ca0-148">Si la conexión es correcta, aparece el mensaje siguiente: "Conexión creada correctamente".</span><span class="sxs-lookup"><span data-stu-id="b3ca0-148">If the connection is successful, the following message appears: "Connection created successfully".</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="b3ca0-149">Si la conexión no es correcta, aparece un mensaje similar al siguiente: "No se puede establecer conexión con el origen de datos".</span><span class="sxs-lookup"><span data-stu-id="b3ca0-149">If the connection is not successful, the following message appears: "Unable to connect to the data source."</span></span>  
  
5.  <span data-ttu-id="b3ca0-150">Haga clic en **Detalles**y utilice la información para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="b3ca0-150">Click **Details**, and use the information to correct the issue.</span></span>  
  
     <span data-ttu-id="b3ca0-151">Para más información, vea [Especificar credenciales en el Generador de informes](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b3ca0-151">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b3ca0-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3ca0-152">See Also</span></span>  
 <span data-ttu-id="b3ca0-153">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b3ca0-153">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="b3ca0-154">[Conjuntos de valores integrados de informe y conjuntos de recursos compartidos &#40;Generador de informes y SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b3ca0-154">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b3ca0-155">[Buscar, ver y administrar informes &#40;Generador de informes y SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b3ca0-155">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b3ca0-156">Conexiones de datos, orígenes de datos y cadenas de conexión en el Generador de informes</span><span class="sxs-lookup"><span data-stu-id="b3ca0-156">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
