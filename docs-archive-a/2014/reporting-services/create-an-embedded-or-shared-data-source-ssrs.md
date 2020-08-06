---
title: Crear un origen de datos incrustado o compartido (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], creating
ms.assetid: b111a8d0-a60d-4c8b-b00a-51644b19c34b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52c5263859ad16ed725065bce4998d08bddaf5f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747508"
---
# <a name="create-an-embedded-or-shared-data-source-ssrs"></a><span data-ttu-id="ca657-102">Crear un origen de datos incrustado o compartido (SSRS)</span><span class="sxs-lookup"><span data-stu-id="ca657-102">Create an Embedded or Shared Data Source (SSRS)</span></span>
  <span data-ttu-id="ca657-103">Un origen de datos de informe especifica la información de nombre y cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="ca657-103">A report data source specifies a name and connection information.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="ca657-104">admite dos tipos de orígenes de datos: incrustados y compartidos.</span><span class="sxs-lookup"><span data-stu-id="ca657-104">supports two types of data sources: embedded and shared.</span></span> <span data-ttu-id="ca657-105">Un origen de datos incrustado se define en una definición de informe y se usa solamente en ese informe.</span><span class="sxs-lookup"><span data-stu-id="ca657-105">An embedded data source is defined in a report definition and used only by that report.</span></span> <span data-ttu-id="ca657-106">Un origen de datos compartido se define como un elemento independiente y se puede usar en varios informes.</span><span class="sxs-lookup"><span data-stu-id="ca657-106">A shared data source is defined as a separate item and can be used by multiple reports.</span></span> <span data-ttu-id="ca657-107">Para obtener más información, vea [conexiones de datos y orígenes de datos incrustados y Compartidos &#40;generador de informes y SSRS&#41;](../../2014/reporting-services/embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ca657-107">For more information, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="ca657-108">En el Generador de informes, puede desplazarse al servidor de informes o al sitio de SharePoint y seleccionar orígenes de datos o crear orígenes de datos incrustados.</span><span class="sxs-lookup"><span data-stu-id="ca657-108">In Report Builder, you browse to the report server or SharePoint site and select data sources or create embedded data sources.</span></span> <span data-ttu-id="ca657-109">No puede crear orígenes de datos compartidos en el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="ca657-109">You cannot create shared data sources in Report Builder.</span></span>  
  
 <span data-ttu-id="ca657-110">En el Diseñador de informes, puede crear orígenes de datos compartidos o incrustados.</span><span class="sxs-lookup"><span data-stu-id="ca657-110">In Report Designer, you can create shared or embedded data sources.</span></span> <span data-ttu-id="ca657-111">En el panel datos de informe, empiece a crear una referencia de origen de datos y, a continuación, seleccione la opción **nuevo** .</span><span class="sxs-lookup"><span data-stu-id="ca657-111">From the Report Data pane, begin to create a data source reference, and then select the **New** option.</span></span> <span data-ttu-id="ca657-112">Después de crear la referencia de origen de datos, se agregará automáticamente un nuevo origen de datos compartido al Explorador de soluciones en la carpeta de orígenes de datos compartidos.</span><span class="sxs-lookup"><span data-stu-id="ca657-112">After you create the data source reference, a new shared data source will automatically be added to Solution Explorer under the Shared Data Sources folder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="ca657-113">También puede crear orígenes de datos compartidos directamente en un servidor de informes o un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ca657-113">You can also create shared data sources directly on a report server or SharePoint site.</span></span> <span data-ttu-id="ca657-114">Para obtener más información, vea [crear, eliminar o modificar un origen de datos compartido &#40;Administrador de informes&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md) o [crear y administrar orígenes de datos compartidos &#40;Reporting Services en el modo integrado de SharePoint&#41;](../../2014/reporting-services/create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="ca657-114">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md) or [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../../2014/reporting-services/create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span>  
  
### <a name="to-create-an-embedded-or-shared-data-source"></a><span data-ttu-id="ca657-115">Para crear un origen de datos incrustado o compartido</span><span class="sxs-lookup"><span data-stu-id="ca657-115">To create an embedded or shared data source</span></span>  
  
1.  <span data-ttu-id="ca657-116">En la barra de herramientas del panel datos de informe, haga clic en **nuevo** y, a continuación, haga clic en **origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="ca657-116">On the toolbar in the Report Data pane, click **New** and then click **Data Source**.</span></span> <span data-ttu-id="ca657-117">Se abre el cuadro de diálogo **Propiedades del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="ca657-117">The **Data Source Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca657-118"> Si el panel Datos de informe no está visible, haga clic en **Datos de informe** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="ca657-118">If the Report Data pane is not visible, click **Report Data** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="ca657-119">En el cuadro de texto **Nombre** , escriba un nombre para el origen de datos o acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ca657-119">In the **Name** text box, type a name for the data source or accept the default.</span></span> <span data-ttu-id="ca657-120">El nombre del origen de datos se utiliza internamente en el informe.</span><span class="sxs-lookup"><span data-stu-id="ca657-120">The data source name is used internally within the report.</span></span> <span data-ttu-id="ca657-121">Para evitar confusiones, se recomienda que el nombre del origen de datos contenga el nombre de la base de datos especificada en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="ca657-121">For clarity, we recommend that the name of the data source contain the name of the database specified in the connection string.</span></span>  
  
3.  <span data-ttu-id="ca657-122">Para un origen de datos incrustado, compruebe que está seleccionada la opción **conexión incrustada** .</span><span class="sxs-lookup"><span data-stu-id="ca657-122">For an embedded data source, verify that **Embedded connection** is selected.</span></span>  
  
    1.  <span data-ttu-id="ca657-123">En la lista desplegable **Tipo** , seleccione un tipo de origen de datos (por ejemplo, **Microsoft SQL Server** u **OLE DB**).</span><span class="sxs-lookup"><span data-stu-id="ca657-123">From the **Type** drop-down list, select a data source type; for example, **Microsoft SQL Server** or **OLE DB**.</span></span>  
  
    2.  <span data-ttu-id="ca657-124">Especifique una cadena de conexión usando una de las alternativas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ca657-124">Specify a connection string using one of the following alternatives:</span></span>  
  
    -   <span data-ttu-id="ca657-125">Escriba la cadena de conexión directamente en el cuadro de texto **Cadena de conexión** .</span><span class="sxs-lookup"><span data-stu-id="ca657-125">Type the connection string directly in the **Connection string** text box.</span></span> <span data-ttu-id="ca657-126">Para obtener una lista de cadenas de conexión de ejemplo, vea [conexiones de datos, orígenes de datos y cadenas de conexión en generador de informes](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-report-builder.md) o [conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ca657-126">For a list of example connection strings, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-report-builder.md) or [Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span></span>  
  
    -   <span data-ttu-id="ca657-127">Haga clic en el botón de expresión (**fx** ) para crear una expresión que dé como resultado una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="ca657-127">Click the expression (**fx)** button to create an expression that evaluates to a connection string.</span></span> <span data-ttu-id="ca657-128">En el cuadro de diálogo **Expresión** , escriba la expresión en el panel Expresión.</span><span class="sxs-lookup"><span data-stu-id="ca657-128">In the **Expression** dialog box, type the expression in the Expression pane.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
    -   <span data-ttu-id="ca657-129">Haga clic en **Editar** para abrir el cuadro de diálogo **Propiedades de conexión** para el tipo de origen de datos que eligió en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="ca657-129">Click **Edit** to open the **Connection Properties** dialog box for the data source type you chose in step 2.</span></span>  
  
         <span data-ttu-id="ca657-130">Rellene los campos del cuadro de diálogo **Propiedades de conexión** según corresponda para el tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ca657-130">Fill in the fields in the **Connection Properties** dialog box as appropriate for the data source type.</span></span> <span data-ttu-id="ca657-131">Las propiedades de conexión incluyen el tipo de origen de datos, el nombre del origen de datos, y las credenciales que se deben usar.</span><span class="sxs-lookup"><span data-stu-id="ca657-131">Connection properties include the type of data source, the name of the data source, and the credentials to use.</span></span> <span data-ttu-id="ca657-132">Después de especificar los valores en este cuadro de diálogo, haga clic en **Probar conexión** para comprobar que el origen de datos está disponible y que las credenciales que especificó son correctas.</span><span class="sxs-lookup"><span data-stu-id="ca657-132">After you specify values in this dialog box, click **Test Connection** to verify that the data source is available and that the credentials you specified are correct.</span></span> <span data-ttu-id="ca657-133">Para más información sobre tipos de orígenes de datos específicos, vea los temas en [Agregar datos de orígenes de datos externos &#40;SSRS&#41;](report-data/add-data-from-external-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ca657-133">For more information about specific data source types, see topics in [Add Data from External Data Sources &#40;SSRS&#41;](report-data/add-data-from-external-data-sources-ssrs.md).</span></span>  
  
4.  <span data-ttu-id="ca657-134">Para un origen de datos compartido, compruebe que está seleccionada la opción **usar referencia de origen de datos compartido** .</span><span class="sxs-lookup"><span data-stu-id="ca657-134">For a shared data source, verify that **Use shared data source reference** is selected.</span></span>  
  
    1.  <span data-ttu-id="ca657-135">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="ca657-135">Click **New**.</span></span> <span data-ttu-id="ca657-136">En el cuadro de diálogo de propiedades **Origen de datos compartido** , siga los pasos 2 y 3 para crear un nuevo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ca657-136">In the **Shared Data Source** properties dialog box, follow steps 2 and 3 to create a new data source.</span></span>  
  
    2.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
         <span data-ttu-id="ca657-137">El nuevo origen de datos compartido aparece en la carpeta Orígenes de datos compartidos del Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="ca657-137">The new shared data source appears in the Shared Data Sources folder in Solution Explorer.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="ca657-138">El origen de datos aparece en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="ca657-138">The data source appears in the Report Data pane.</span></span> <span data-ttu-id="ca657-139">En el panel Datos de informe, un origen de datos compartido señala la definición del origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="ca657-139">In the Report Data pane, a shared data source points to the data source definition.</span></span> <span data-ttu-id="ca657-140">En el Generador de informes, la definición del origen de datos está en un servidor de informes o en un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ca657-140">In Report Builder, the data source definition is on a report server or SharePoint site.</span></span> <span data-ttu-id="ca657-141">En el Diseñador de informes, la definición del origen de datos es un archivo del Explorador de soluciones en la carpeta de orígenes de datos compartidos.</span><span class="sxs-lookup"><span data-stu-id="ca657-141">In Report Designer, the data source definition is a file in Solution Explorer under the Shared Data Sources folder.</span></span>  
  
### <a name="to-import-an-existing-data-source-in-report-designer"></a><span data-ttu-id="ca657-142">Para importar un origen de datos existente en el Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="ca657-142">To import an existing data source in Report Designer</span></span>  
  
1.  <span data-ttu-id="ca657-143">En el Explorador de soluciones, haga clic con el botón derecho en la carpeta **Orígenes de datos compartidos** del proyecto de servidor de informes y, después, haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="ca657-143">In Solution Explorer, right-click the **Shared Data Sources** folder in the report server project, and then click **Add Existing Item**.</span></span> <span data-ttu-id="ca657-144">Se abrirá el cuadro de diálogo **Agregar elemento existente** .</span><span class="sxs-lookup"><span data-stu-id="ca657-144">The **Add Existing Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="ca657-145">Navegue a un archivo existente de origen de datos compartido de definición de informe (rds) y, después, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="ca657-145">Navigate to an existing Report Definition Shared data source (rds) file and then click **Open**.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-convert-an-embedded-data-source-to-a-shared-data-source-in-report-designer"></a><span data-ttu-id="ca657-146">Para convertir un origen de datos incrustado en un origen de datos compartido en el Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="ca657-146">To convert an embedded data source to a shared data source in Report Designer</span></span>  
  
-   <span data-ttu-id="ca657-147">En el panel datos de informe, haga clic con el botón secundario en el origen de datos y, a continuación, haga clic en **convertir en origen de datos compartido**.</span><span class="sxs-lookup"><span data-stu-id="ca657-147">In the Report Data pane, right-click the data source and then click **Convert to Shared Data Source**.</span></span>  
  
### <a name="to-convert-a-shared-data-source-to-an-embedded-data-source-in-report-builder"></a><span data-ttu-id="ca657-148">Para convertir un origen de datos compartido en un origen de datos incrustado en el Generador de informes</span><span class="sxs-lookup"><span data-stu-id="ca657-148">To convert a shared data source to an embedded data source in Report Builder</span></span>  
  
-   <span data-ttu-id="ca657-149">En el panel datos de informe, haga clic con el botón secundario en el origen de datos y Abra **propiedades del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="ca657-149">In the Report Data pane, right-click the data source and open **Data Source Properties**.</span></span>  
  
-   <span data-ttu-id="ca657-150">Haga clic en **conexión incrustada** y termine de crear el origen de datos incrustado como se describe en un procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="ca657-150">Click **Embedded Connection** and finish creating the embedded data source as described in an earlier procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca657-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca657-151">See Also</span></span>  
 <span data-ttu-id="ca657-152">[Almacenar credenciales en un origen de datos de Reporting Services](report-data/store-credentials-in-a-reporting-services-data-source.md) </span><span class="sxs-lookup"><span data-stu-id="ca657-152">[Store Credentials in a Reporting Services Data Source](report-data/store-credentials-in-a-reporting-services-data-source.md) </span></span>  
 <span data-ttu-id="ca657-153">[Conexiones de datos u orígenes de datos incrustados y compartidos &#40;Generador de informes y SSRS&#41;](../../2014/reporting-services/embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ca657-153">[Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ca657-154">[Convertir un origen de datos de incrustado en &#40;compartidos Generador de informes y SSRS&#41;](report-data/convert-data-sources-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ca657-154">[Convert a Data Source from Embedded to Shared &#40;Report Builder and SSRS&#41;](report-data/convert-data-sources-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ca657-155">[Enlazar un informe o un modelo a un origen de datos compartido &#40;SSRS&#41;](report-data/bind-a-report-or-model-to-a-shared-data-source-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ca657-155">[Bind a Report or Model to a Shared Data Source &#40;SSRS&#41;](report-data/bind-a-report-or-model-to-a-shared-data-source-ssrs.md) </span></span>  
 <span data-ttu-id="ca657-156">[Configurar propiedades de origen de datos para un informe &#40;Administrador de informes&#41;](report-data/configure-data-source-properties-for-a-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ca657-156">[Configure Data Source Properties for a Report  &#40;Report Manager&#41;](report-data/configure-data-source-properties-for-a-report-report-manager.md) </span></span>  
 [<span data-ttu-id="ca657-157">Orígenes de datos admitidos por Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ca657-157">Data Sources Supported by Reporting Services &#40;SSRS&#41;</span></span>](create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  