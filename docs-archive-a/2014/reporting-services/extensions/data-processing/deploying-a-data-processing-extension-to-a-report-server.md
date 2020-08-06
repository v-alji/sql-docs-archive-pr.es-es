---
title: Cómo implementar una extensión de procesamiento de datos en un servidor de informes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: e00dface-70f8-434b-9763-8ebee18737d2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d606096b9f2060d3cf5b9cea1f95a5345e592383
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750513"
---
# <a name="how-to-deploy-a-data-processing-extension-to-a-report-server"></a><span data-ttu-id="7de85-102">Procedimientos: Implementar una extensión de procesamiento de datos en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="7de85-102">How to: Deploy a Data Processing Extension to a Report Server</span></span>
  <span data-ttu-id="7de85-103">Los servidores de informes utilizan las extensiones de procesamiento de datos para recuperar y procesar los datos en informes representados.</span><span class="sxs-lookup"><span data-stu-id="7de85-103">Report servers use data processing extensions for retrieving and processing data in rendered reports.</span></span> <span data-ttu-id="7de85-104">Debería implementar el ensamblado de extensión de procesamiento de datos en un servidor de informes como un ensamblado privado.</span><span class="sxs-lookup"><span data-stu-id="7de85-104">You should deploy your data processing extension assembly to a report server as a private assembly.</span></span> <span data-ttu-id="7de85-105">También tiene que realizar una entrada en el archivo de configuración del servidor de informes, RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="7de85-105">You also need to make an entry in the report server configuration file, RSReportServer.config.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="7de85-106">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7de85-106">Procedures</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="7de85-107">Para implementar un ensamblado de extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="7de85-107">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="7de85-108">Copie el ensamblado de la ubicación provisional al directorio bin del servidor de informes en el que desea utilizar la extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="7de85-108">Copy your assembly from your staging location to the bin directory of the report server on which you want to use the data processing extension.</span></span> <span data-ttu-id="7de85-109">La ubicación predeterminada del directorio bin del servidor de informes es%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<*Instance Name*> \Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="7de85-109">The default location of the report server bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer\bin.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7de85-110">Este paso evitará una actualización a una instancia más nueva de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7de85-110">This step will prevent an upgrade to a newer instance of SQL Server.</span></span> <span data-ttu-id="7de85-111">Para obtener más información, vea [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="7de85-111">For more information, see [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
2.  <span data-ttu-id="7de85-112">Una vez copiado el archivo de ensamblado, abra el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="7de85-112">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="7de85-113">El archivo RSReportServer.config se encuentra en el directorio ReportServer.</span><span class="sxs-lookup"><span data-stu-id="7de85-113">The RSReportServer.config file is located in the ReportServer directory.</span></span> <span data-ttu-id="7de85-114">Tiene que realizar una entrada en el archivo de configuración para el archivo de ensamblado de extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="7de85-114">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="7de85-115">Puede abrir el archivo de configuración con Visual Studio o con un procesador de texto sencillo como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="7de85-115">You can open the configuration file with Visual Studio or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="7de85-116">Busque el elemento `Data` en el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="7de85-116">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="7de85-117">En la ubicación siguiente se debería realizar una entrada para la extensión de procesamiento de datos creada recientemente:</span><span class="sxs-lookup"><span data-stu-id="7de85-117">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="7de85-118">Agregue una entrada para su extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="7de85-118">Add an entry for your data processing extension.</span></span> <span data-ttu-id="7de85-119">La entrada debe incluir un `Extension` elemento con valores para `Name` y `Type` y podría ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="7de85-119">Your entry should include an `Extension` element with values for `Name` and `Type` and might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, MyExtensionAssembly" />  
    ```  
  
     <span data-ttu-id="7de85-120">El valor de `Name` es el nombre único de la extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="7de85-120">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="7de85-121">El valor de `Type` es una lista separada por comas que incluye una entrada para el espacio de nombres completo de la clase que implementa las interfaces <xref:Microsoft.ReportingServices.Interfaces.IExtension> y <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection>, seguido del nombre del ensamblado (sin incluir la extensión de archivo .dll).</span><span class="sxs-lookup"><span data-stu-id="7de85-121">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="7de85-122">De forma predeterminada, las extensiones de procesamiento de datos están visibles.</span><span class="sxs-lookup"><span data-stu-id="7de85-122">By default, data processing extensions are visible.</span></span> <span data-ttu-id="7de85-123">Para ocultar una extensión de las interfaces de usuario, como el Administrador de informes, agregue un atributo `Visible` al elemento `Extension` y establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="7de85-123">To hide an extension from user interfaces, such as Report Manager, add a `Visible` attribute to the `Extension` element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="7de85-124">Agregue un grupo de código para el ensamblado personalizado que conceda el permiso `FullTrust` para la extensión.</span><span class="sxs-lookup"><span data-stu-id="7de85-124">Add a code group for your custom assembly that grants `FullTrust` permission for your extension.</span></span> <span data-ttu-id="7de85-125">Para ello, agregue el grupo de código al archivo rssrvpolicy.config ubicado de forma predeterminada en%ProgramFiles%\Microsoft SQL Server \\<MSRS10_50. \<*Instance Name*> \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="7de85-125">You do this by adding the code group to the rssrvpolicy.config file located by default in %ProgramFiles%\Microsoft SQL Server\\<MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer.</span></span> <span data-ttu-id="7de85-126">El grupo de código podría tener la apariencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="7de85-126">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<Instance Name>\Reporting Services\ReportServer\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="7de85-127">La pertenencia de dirección URL es solo una de las muchas condiciones de pertenencia que podría elegir para la extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="7de85-127">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="7de85-128">Para más información sobre la seguridad de acceso del código en [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], vea [Desarrollo seguro &#40;Reporting Services&#41](../secure-development/secure-development-reporting-services.md);.</span><span class="sxs-lookup"><span data-stu-id="7de85-128">For more information about code access security in [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span></span>  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="7de85-129">Comprobación de la implementación</span><span class="sxs-lookup"><span data-stu-id="7de85-129">Verifying the Deployment</span></span>  
 <span data-ttu-id="7de85-130">Puede comprobar si la extensión de procesamiento de datos se implementó correctamente en el servidor de informes utilizando el método <xref:ReportService2010.ReportingService2010.ListExtensions%2A> del servicio web.</span><span class="sxs-lookup"><span data-stu-id="7de85-130">You can verify whether your data processing extension was deployed successfully to the report server by using the Web service <xref:ReportService2010.ReportingService2010.ListExtensions%2A> method.</span></span> <span data-ttu-id="7de85-131">Puede abrir también Administrador de informes y comprobar que su extensión está incluida en la lista de orígenes de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="7de85-131">You can also open Report Manager and verify that your extension is included in the list of available data sources.</span></span> <span data-ttu-id="7de85-132">Para más información sobre el Administrador de informes y los orígenes de datos, vea [Crear, modificar y eliminar orígenes de datos compartidos &#40;SSRS&#41;](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7de85-132">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de85-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7de85-133">See Also</span></span>  
 <span data-ttu-id="7de85-134">[Implementación de una extensión de procesamiento de datos](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="7de85-134">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="7de85-135">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="7de85-135">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="7de85-136">[Implementar una extensión de procesamiento de datos](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="7de85-136">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="7de85-137">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7de85-137">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
