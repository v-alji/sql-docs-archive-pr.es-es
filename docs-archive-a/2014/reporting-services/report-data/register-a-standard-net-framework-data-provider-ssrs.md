---
title: Registrar un proveedor de datos estándar de .NET Framework (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], data
- .NET Framework data providers for Reporting Services
- data processing extensions [Reporting Services]
- data providers [Reporting Services]
- data retrieval [Reporting Services]
- Reporting Services, data sources
ms.assetid: d92add64-e93c-4598-8508-55d1bc46acf6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fd26f9c7fa163d9e6005d42e24c7b1483987f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744504"
---
# <a name="register-a-standard-net-framework-data-provider-ssrs"></a><span data-ttu-id="24e90-102">Registrar un proveedor de datos estándar de .NET Framework (SSRS)</span><span class="sxs-lookup"><span data-stu-id="24e90-102">Register a Standard .NET Framework Data Provider (SSRS)</span></span>
  <span data-ttu-id="24e90-103">Para usar un proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] de terceros para recuperar datos de un conjunto de datos de informe de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , es necesario implementar y registrar el ensamblado del proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] en dos ubicaciones: en el cliente de creación de informes y en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="24e90-103">To use a third-party [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider to retrieve data for a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report dataset, you need to deploy and register the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly in two locations: on the report authoring client and on the report server.</span></span> <span data-ttu-id="24e90-104">En el cliente de creación de informes, debe registrar el proveedor de datos como un tipo de origen de datos y asociarlo a un diseñador de consultas.</span><span class="sxs-lookup"><span data-stu-id="24e90-104">On the report authoring client, you must register the data provider as a data source type and associate it with a query designer.</span></span> <span data-ttu-id="24e90-105">A continuación, puede seleccionar este proveedor de datos como un tipo de origen de datos al crear un conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="24e90-105">You can then select this data provider as a type of data source when you create a report dataset.</span></span> <span data-ttu-id="24e90-106">El diseñador de consultas asociado se abre para ayudarle a crear consultas para este tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="24e90-106">The associated query designer opens to help you create queries for this data source type.</span></span> <span data-ttu-id="24e90-107">En el servidor de informes, debe registrar el proveedor de datos como un tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="24e90-107">On the report server, you must register the data provider as a data source type.</span></span> <span data-ttu-id="24e90-108">A continuación, puede procesar los informes publicados que recuperan datos de un origen de datos con este proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="24e90-108">You can then process published reports that retrieve data from a data source using this data provider.</span></span>  
  
 <span data-ttu-id="24e90-109">Los proveedores de datos de terceros no proporcionan necesariamente todas las funciones disponibles con las extensiones de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24e90-109">Third-party data providers do not necessarily provide all the functionality available with the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] data processing extensions.</span></span> <span data-ttu-id="24e90-110">Para más información, vea [Orígenes de datos admitidos por Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="24e90-110">For more information, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span> <span data-ttu-id="24e90-111">Para obtener más información acerca de cómo ampliar la funcionalidad de un proveedor de datos de .[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24e90-111">To learn about extending the functionality of a .[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]</span></span> <span data-ttu-id="24e90-112">, vea [Implementación de una extensión de procesamiento de datos](../extensions/data-processing/implementing-a-data-processing-extension.md).</span><span class="sxs-lookup"><span data-stu-id="24e90-112">data provider, see [Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md).</span></span>  
  
 <span data-ttu-id="24e90-113">Necesita credenciales de administrador para instalar y registrar proveedores de datos.</span><span class="sxs-lookup"><span data-stu-id="24e90-113">You need administrator credentials to install and register data providers.</span></span>  
  
## <a name="registering-a-net-framework-data-provider-on-the-report-server"></a><span data-ttu-id="24e90-114">Registrar un proveedor de datos de .NET Framework en el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="24e90-114">Registering a .NET Framework Data Provider on the Report Server</span></span>  
 <span data-ttu-id="24e90-115">Para procesar los informes publicados que usan este proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] en el servidor de informes, debe instalar el ensamblado en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="24e90-115">In order to process published reports that use this [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider on the report server, you need to install the assembly on the report server.</span></span> <span data-ttu-id="24e90-116">Debe modificar dos archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="24e90-116">You must modify two configuration files.</span></span> <span data-ttu-id="24e90-117">Modifique rsreportserver.config para registrar el proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="24e90-117">Modify rsreportserver.config to register the data provider.</span></span> <span data-ttu-id="24e90-118">Modifique rssrvpolicy.config para conceder permisos de seguridad de acceso del código para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="24e90-118">Modify rssrvpolicy.config to grant code access security permissions for the assembly.</span></span>  
  
#### <a name="to-install-a-data-provider-assembly-on-the-report-server"></a><span data-ttu-id="24e90-119">Para instalar un ensamblado del proveedor de datos en el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="24e90-119">To install a data provider assembly on the report server</span></span>  
  
1.  <span data-ttu-id="24e90-120">Navegue hasta la ubicación predeterminada del directorio bin del servidor de informes donde desea usar el proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24e90-120">Navigate to the default location of the bin directory on the report server on which you want to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="24e90-121">La ubicación predeterminada del directorio bin del servidor de informes es *\<drive>* : \Archivos de programa\microsoft SQL Server \ MSRS10_50. MSSQLSERVER\Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="24e90-121">The default location of the report server bin directory is *\<drive>*:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin.</span></span>  
  
2.  <span data-ttu-id="24e90-122">Copie el ensamblado desde la ubicación de almacenamiento provisional en el directorio bin del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="24e90-122">Copy your assembly from your staging location to the bin directory of the report server.</span></span> <span data-ttu-id="24e90-123">Otra opción es cargar el ensamblado en la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="24e90-123">Alternatively, you can load your assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="24e90-124">Para obtener más información, vea [Trabajar con ensamblados y la Caché de ensamblados global](https://go.microsoft.com/fwlink/?linkid=63912) en la documentación del SDK de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] en MSDN.</span><span class="sxs-lookup"><span data-stu-id="24e90-124">For more information, see [Working with Assemblies and the Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation on MSDN.</span></span>  
  
#### <a name="to-register-a-net-data-provider-on-the-report-server"></a><span data-ttu-id="24e90-125">Para registrar un proveedor de datos de .NET en el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="24e90-125">To register a .NET data provider on the report server</span></span>  
  
1.  <span data-ttu-id="24e90-126">Haga una copia de seguridad del archivo RSReportServer.config en el directorio principal ReportServer para bin.</span><span class="sxs-lookup"><span data-stu-id="24e90-126">Make a backup of the RSReportServer.config file in the ReportServer parent directory for bin.</span></span>  
  
2.  <span data-ttu-id="24e90-127">Abra RSReportServer.config. Puede abrir el archivo de configuración con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un editor de texto simple como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="24e90-127">Open RSReportServer.config. You can open the configuration file with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="24e90-128">Busque el elemento `Data` en el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="24e90-128">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="24e90-129">Se debe crear una entrada para el proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="24e90-129">An entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Extension Your data provider configuration information goes here />  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="24e90-130">Agregue una entrada para el proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24e90-130">Add an entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span>  
  
    |<span data-ttu-id="24e90-131">Atributo</span><span class="sxs-lookup"><span data-stu-id="24e90-131">Attribute</span></span>|<span data-ttu-id="24e90-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="24e90-132">Description</span></span>|  
    |---------------|-----------------|  
    |`Name`|<span data-ttu-id="24e90-133">Proporcione un nombre único para el proveedor de datos (por ejemplo, **miProveedorDeDatosDeNET**).</span><span class="sxs-lookup"><span data-stu-id="24e90-133">Provide a unique name for the data provider, for example, **MyNETDataProvider**.</span></span> <span data-ttu-id="24e90-134">La longitud máxima para el atributo `Name` es de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="24e90-134">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="24e90-135">El nombre debe ser único entre todas las entradas en el elemento `Extension` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="24e90-135">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="24e90-136">El valor incluido aquí aparece en la lista desplegable de tipos de orígenes de datos al crear un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="24e90-136">The value you include here appears in the drop-down list of data source types when you create a new data source.</span></span>|  
    |`Type`|<span data-ttu-id="24e90-137">Escriba una lista separada por comas donde se incluya el espacio de nombres completo de la clase que implementa la interfaz <xref:System.Data.IDbConnection> , seguido del nombre del ensamblado del proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] (sin incluir la extensión de nombre de archivo .dll).</span><span class="sxs-lookup"><span data-stu-id="24e90-137">Enter a comma-separated list that includes the fully qualified namespace of the class that implements the <xref:System.Data.IDbConnection> interface, followed by the name of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly (not including the .dll file name extension).</span></span>|  
  
     <span data-ttu-id="24e90-138">Por ejemplo, la entrada puede ser similar a la siguiente para una DLL implementada en el directorio bin del servidor de informes:</span><span class="sxs-lookup"><span data-stu-id="24e90-138">For example, the entry might resemble the following for a DLL deployed to the report server bin directory:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly" />   
    ```  
  
     <span data-ttu-id="24e90-139">Si carga el ensamblado en la caché de ensamblados global (GAC), debe proporcionar las propiedades de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="24e90-139">If you load your assembly into the global assembly cache (GAC), you must provide the strong name properties.</span></span> <span data-ttu-id="24e90-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="24e90-140">For example:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly,Version=1.0.0.0, Culture=neutral, PublicKeyToken=MyPublicToken"/>  
    ```  
  
#### <a name="to-set-the-code-group-policy-for-a-net-data-provider"></a><span data-ttu-id="24e90-141">Para establecer la directiva de grupo de código para un proveedor de datos de .NET</span><span class="sxs-lookup"><span data-stu-id="24e90-141">To set the code group policy for a .NET data provider</span></span>  
  
1.  <span data-ttu-id="24e90-142">Haga una copia de seguridad del archivo rssrvpolicy.config en el directorio principal ReportServer para bin.</span><span class="sxs-lookup"><span data-stu-id="24e90-142">Make a backup copy of the rssrvpolicy.config file in the ReportServer parent directory for bin.</span></span>  
  
2.  <span data-ttu-id="24e90-143">Abra rssrvpolicy.config. Puede abrir el archivo de configuración con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un editor de texto simple como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="24e90-143">Open rssrvpolicy.config. You can open the configuration file with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor such as Notepad.</span></span>  
  
3.  <span data-ttu-id="24e90-144">Busque el elemento `CodeGroup` en el archivo rssrvpolicy.config.</span><span class="sxs-lookup"><span data-stu-id="24e90-144">Locate the `CodeGroup` element in the rssrvpolicy.config file.</span></span>  
  
4.  <span data-ttu-id="24e90-145">Agregue un grupo de códigos para el ensamblado del proveedor de datos que concede el permiso `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="24e90-145">Add a code group for the data provider assembly that grants `FullTrust` permission.</span></span> <span data-ttu-id="24e90-146">El grupo de códigos puede ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="24e90-146">Your code group might resemble the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="ThisDataProviderCodeGroup"  
       Description="Code group for the .NET data provider">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url=  
    "C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\DataProviderAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="24e90-147">La pertenencia de dirección URL es solo una de las muchas condiciones de pertenencia que puede seleccionar para el proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="24e90-147">URL membership is only one of many membership conditions you might select for the data provider.</span></span>  
  
### <a name="verifying-the-deployment-and-registration"></a><span data-ttu-id="24e90-148">Comprobar la implementación y el registro</span><span class="sxs-lookup"><span data-stu-id="24e90-148">Verifying the Deployment and Registration</span></span>  
 <span data-ttu-id="24e90-149">Puede comprobar si el proveedor de datos se implementó correctamente para el servidor de informes si abre el Administrador de informes y comprueba si el proveedor de datos está incluido en la lista de orígenes de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="24e90-149">You can verify whether the data provider was deployed successfully to the report server by opening Report Manager and verifying that the data provider is included in the list of available data sources.</span></span> <span data-ttu-id="24e90-150">Para más información sobre el Administrador de informes y los orígenes de datos, vea [Crear, modificar y eliminar orígenes de datos compartidos &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="24e90-150">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="registering-a-net-framework-data-provider-on-the-report-designer-client"></a><span data-ttu-id="24e90-151">Registrar un proveedor de datos de .NET Framework en el cliente del Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="24e90-151">Registering a .NET Framework Data Provider on the Report Designer Client</span></span>  
 <span data-ttu-id="24e90-152">Para crear informes que usen este proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para un origen de datos, debe instalar el ensamblado en el equipo cliente que ejecuta el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="24e90-152">In order to author reports that use this [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider for a data source, you must install the assembly on your client computer that runs Report Designer.</span></span> <span data-ttu-id="24e90-153">Debe modificar dos archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="24e90-153">You must modify two configuration files.</span></span> <span data-ttu-id="24e90-154">Modifique RSReportDesigner.config para registrar el proveedor de datos como un origen de datos y para usar el diseñador de consultas genérico.</span><span class="sxs-lookup"><span data-stu-id="24e90-154">Modify RSReportDesigner.config to register the data provider as a data source and to use the generic query designer.</span></span> <span data-ttu-id="24e90-155">Modifique RSPreviewPolicy.config para conceder permisos de seguridad de acceso del código para el ensamblado del proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="24e90-155">Modify RSPreviewPolicy.config to grant code access security permissions for the data provider assembly.</span></span>  
  
#### <a name="to-install-a-data-provider-assembly-on-the-report-designer-client"></a><span data-ttu-id="24e90-156">Para instalar un ensamblado del proveedor de datos en el cliente del Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="24e90-156">To install a data provider assembly on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="24e90-157">Navegue hasta la ubicación predeterminada del directorio PrivateAssemblies del cliente del Diseñador de informes donde desea usar el proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24e90-157">Navigate to the default location of the PrivateAssemblies directory on the Report Designer client on which you want to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="24e90-158">La ubicación predeterminada del directorio PrivateAssemblies es *\<drive>* : \Archivos de Programa\microsoft Visual Studio 9.0 \ Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="24e90-158">The default location of the PrivateAssemblies directory is *\<drive>*:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="24e90-159">Copie el ensamblado desde la ubicación de almacenamiento provisional en el directorio PrivateAssemblies del cliente del Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="24e90-159">Copy your assembly from your staging location to the PrivateAssemblies directory of the Report Designer client.</span></span> <span data-ttu-id="24e90-160">Otra opción es cargar el ensamblado en la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="24e90-160">Alternatively, you can load your assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="24e90-161">Para obtener más información, vea [Trabajar con ensamblados y la Caché de ensamblados global](https://go.microsoft.com/fwlink/?linkid=63912) en la documentación del SDK de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] en MSDN.</span><span class="sxs-lookup"><span data-stu-id="24e90-161">For more information, see [Working with Assemblies and the Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation on MSDN.</span></span>  
  
#### <a name="to-register-a-net-data-provider-on-the-report-designer-client"></a><span data-ttu-id="24e90-162">Para registrar un proveedor de datos de .NET en el cliente del Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="24e90-162">To register a .NET data provider on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="24e90-163">Haga una copia de seguridad del archivo RSReportDesigner.config en el directorio PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="24e90-163">Make a backup copy of the RSReportDesigner.config file in the PrivateAssemblies directory.</span></span>  
  
2.  <span data-ttu-id="24e90-164">Abra RSReportDesigner.config con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un editor de texto simple como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="24e90-164">Open RSReportDesigner.config with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor such as Notepad.</span></span>  
  
3.  <span data-ttu-id="24e90-165">Busque el elemento `Data` en el archivo RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="24e90-165">Locate the `Data` element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="24e90-166">Se debe crear una entrada para el proveedor de datos en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="24e90-166">An entry for the data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Extension Your data provider configuration information goes here />  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="24e90-167">Agregue una entrada para el proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="24e90-167">Add an entry for the data provider.</span></span>  
  
    |<span data-ttu-id="24e90-168">Atributo</span><span class="sxs-lookup"><span data-stu-id="24e90-168">Attribute</span></span>|<span data-ttu-id="24e90-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="24e90-169">Description</span></span>|  
    |---------------|-----------------|  
    |`Name`|<span data-ttu-id="24e90-170">Proporcione un nombre único para el proveedor de datos (por ejemplo, **miProveedorDeDatosDeNET**).</span><span class="sxs-lookup"><span data-stu-id="24e90-170">Provide a unique name for the data provider, for example, **MyNETDataProvider**.</span></span> <span data-ttu-id="24e90-171">La longitud máxima para el atributo `Name` es de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="24e90-171">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="24e90-172">El nombre debe ser único entre todas las entradas en el elemento `Extension` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="24e90-172">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="24e90-173">El valor incluido aquí aparece en la lista desplegable de tipos de orígenes de datos al crear un origen de datos nuevo.</span><span class="sxs-lookup"><span data-stu-id="24e90-173">The value that you include here appears in the drop-down list of data source types when you create a new data source.</span></span>|  
    |`Type`|<span data-ttu-id="24e90-174">Escriba una lista separada por comas donde se incluya el espacio de nombres completo de la clase que implementa la interfaz <xref:System.Data.IDbConnection> , seguido del nombre del ensamblado del proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] (sin incluir la extensión de nombre de archivo .dll).</span><span class="sxs-lookup"><span data-stu-id="24e90-174">Enter a comma-separated list that includes the fully qualified namespace of the class that implements the <xref:System.Data.IDbConnection> interface, followed by the name of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly (not including the .dll file name extension).</span></span>|  
  
     <span data-ttu-id="24e90-175">Por ejemplo, la entrada puede ser similar a la siguiente para una DLL implementada en el directorio PrivateAssemblies de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="24e90-175">For example, the entry might resemble the following for a DLL deployed to the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] PrivateAssemblies directory:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly" />   
    ```  
  
     <span data-ttu-id="24e90-176">Si carga el ensamblado en la GAC, debe proporcionar las propiedades de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="24e90-176">If you load your assembly into the GAC, you must provide the strong name properties.</span></span> <span data-ttu-id="24e90-177">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="24e90-177">For example:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=MyPublicToken"/>  
    ```  
  
5.  <span data-ttu-id="24e90-178">Busque el elemento `Designer` en el archivo RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="24e90-178">Locate the `Designer` element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="24e90-179">Se debe crear una entrada para el proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="24e90-179">An entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Designer>  
          <Your data provider configuration information goes here>  
       </Designer>  
    </Extensions>  
    ```  
  
6.  <span data-ttu-id="24e90-180">Agregue la siguiente entrada al archivo RSReportDesigner.config en el elemento `Designer`.</span><span class="sxs-lookup"><span data-stu-id="24e90-180">Add the following entry to the RSReportDesigner.config file under the `Designer` element.</span></span> <span data-ttu-id="24e90-181">Debe reemplazar solamente el atributo `Name` por el nombre proporcionado en las entradas anteriores.</span><span class="sxs-lookup"><span data-stu-id="24e90-181">You need to replace only the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
#### <a name="to-set-the-code-group-policy-for-a-net-data-provider-on-the-report-designer-client"></a><span data-ttu-id="24e90-182">Para establecer la directiva de grupo de código para un proveedor de datos de .NET en el cliente del Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="24e90-182">To set the code group policy for a .NET data provider on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="24e90-183">Haga una copia de seguridad del archivo RSPreviewPolicy.config en el directorio PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="24e90-183">Make a backup copy of the RSPreviewPolicy.config file in the PrivateAssemblies directory.</span></span>  
  
2.  <span data-ttu-id="24e90-184">Abra RSPreviewPolicy.config con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o un editor de texto simple como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="24e90-184">Open RSPreviewPolicy.config with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="24e90-185">Busque el elemento `CodeGroup` en el archivo RSPreviewPolicy.config.</span><span class="sxs-lookup"><span data-stu-id="24e90-185">Locate the `CodeGroup` element in the RSPreviewPolicy.config file.</span></span>  
  
4.  <span data-ttu-id="24e90-186">Agregue un grupo de códigos para el ensamblado del proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que concede el permiso `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="24e90-186">Add a code group for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly that grants `FullTrust` permission.</span></span> <span data-ttu-id="24e90-187">El grupo de códigos puede ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="24e90-187">Your code group might resemble the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="ThisDataProviderCodeGroup"  
       Description="Code group for the .NET data provider">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url=  
    " C:\Program Files\Microsoft Visual Studio 9\Common7\IDE\PrivateAssemblies\DataProviderAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="24e90-188">La pertenencia de dirección URL es solo una de las muchas condiciones de pertenencia que puede seleccionar para el proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="24e90-188">URL membership is only one of many membership conditions you might select for the data provider.</span></span>  
  
### <a name="verifying-the-deployment-and-registration-on-the-report-designer-client"></a><span data-ttu-id="24e90-189">Comprobar la implementación y el registro en el cliente del Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="24e90-189">Verifying the Deployment and Registration on the Report Designer Client</span></span>  
 <span data-ttu-id="24e90-190">Para poder comprobar la implementación, debe cerrar todas las instancias de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="24e90-190">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="24e90-191">Una vez que haya finalizado todas las sesiones actuales, puede comprobar si el proveedor de datos se implementó correctamente para el Diseñador de informes si crea un proyecto de informe nuevo en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24e90-191">After you have ended all current sessions, you can verify whether your data provider was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="24e90-192">El proveedor de datos se debe incluir en la lista de tipos de orígenes de datos disponibles al crear un conjunto de datos nuevo para el informe.</span><span class="sxs-lookup"><span data-stu-id="24e90-192">The data provider should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="platform-considerations"></a><span data-ttu-id="24e90-193">Consideraciones sobre las plataformas</span><span class="sxs-lookup"><span data-stu-id="24e90-193">Platform Considerations</span></span>  
 <span data-ttu-id="24e90-194">En una plataforma de 64 bits (x64), [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] se ejecuta en el modo WOW de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="24e90-194">On a 64-bit (x64) platform, [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] runs in 32-bit WOW mode.</span></span> <span data-ttu-id="24e90-195">Si crea informes en una plataforma x64, necesita tener proveedores de datos de 32 bits instalados en el cliente de creación de informes para obtener vistas previas de los informes.</span><span class="sxs-lookup"><span data-stu-id="24e90-195">When you author reports on an x64 platform, you need 32-bit data providers installed on the report authoring client in order to preview your reports.</span></span> <span data-ttu-id="24e90-196">Si publica el informe en el mismo sistema, necesita proveedores de datos x64 para ver el informe con el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="24e90-196">If you publish the report on the same system, you need x64 data providers to view the report with Report Manager.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="24e90-197">no se admite para las plataformas basadas en [!INCLUDE[vcpritanium](../../includes/vcpritanium-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24e90-197">is not supported for [!INCLUDE[vcpritanium](../../includes/vcpritanium-md.md)]-based platforms.</span></span>  
  
 <span data-ttu-id="24e90-198">Las extensiones de procesamiento de datos instaladas con [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] se deben compilar de forma nativa para cada plataforma e instalar en las ubicaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="24e90-198">The data processing extensions that are installed with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] must be compiled natively for each platform and installed in the correct locations.</span></span> <span data-ttu-id="24e90-199">Si registra un proveedor de datos personalizado o un proveedor de datos estándar de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , se debe compilar de forma nativa para la plataforma adecuada e instalar en las ubicaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="24e90-199">If you register a custom data provider or a standard [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider, it needs to be compiled natively for the appropriate platform and installed the appropriate locations.</span></span> <span data-ttu-id="24e90-200">Si usa una plataforma de 32 bits, el proveedor de datos se debe compilar para una plataforma de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="24e90-200">If you are running on a 32-bit platform, the data provider must be compiled for a 32-bit platform.</span></span> <span data-ttu-id="24e90-201">Si usa una plataforma de 64 bits, el proveedor de datos se debe compilar para una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="24e90-201">If you are running on a 64-bit platform, the data provider must be compiled for the 64-bit platform.</span></span> <span data-ttu-id="24e90-202">No puede usar un proveedor de datos de 32 bits incluido con interfaces de 64 bits en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="24e90-202">You cannot use a 32-bit data provider wrapped with 64-bit interfaces on a 64 bit platform.</span></span> <span data-ttu-id="24e90-203">Compruebe el software de terceros para obtener información acerca de si el proveedor de datos funcionará en la plataforma instalada.</span><span class="sxs-lookup"><span data-stu-id="24e90-203">Check your third-party software for information about whether the data provider will work on the installed platform.</span></span> <span data-ttu-id="24e90-204">Para más información sobre proveedores de datos y la compatibilidad con plataformas, vea [Orígenes de datos admitidos por Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="24e90-204">For more information about data providers and platform support, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e90-205">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24e90-205">See Also</span></span>  
 <span data-ttu-id="24e90-206">[Configurar y administrar un servidor de informes &#40;modo nativo de SSRS&#41;](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="24e90-206">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="24e90-207">[Implementar una extensión de procesamiento de datos](../extensions/data-processing/implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="24e90-207">[Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="24e90-208">[Archivos de configuración de Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="24e90-208">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="24e90-209">Seguridad de acceso del código en Reporting Services</span><span class="sxs-lookup"><span data-stu-id="24e90-209">Code Access Security in Reporting Services</span></span>](../extensions/secure-development/code-access-security-in-reporting-services.md)  
  
  
