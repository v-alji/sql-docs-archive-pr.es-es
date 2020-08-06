---
title: Cómo implementar una extensión de procesamiento de datos en el Diseñador de informes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: 3614e601-004e-4a16-8388-836ffd67e9dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56bd56e9d8eeeeff1781f22b42cf0eb1ce706fa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750497"
---
# <a name="how-to-deploy-a-data-processing-extension-to-report-designer"></a><span data-ttu-id="a3479-102">Procedimientos: Implementar una extensión de procesamiento de datos en el Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="a3479-102">How to: Deploy a Data Processing Extension to Report Designer</span></span>
  <span data-ttu-id="a3479-103">El Diseñador de informes utiliza las extensiones de procesamiento de datos para recuperar y procesar los datos mientras se diseñan los informes.</span><span class="sxs-lookup"><span data-stu-id="a3479-103">Report Designer uses data processing extensions for retrieving and processing data while you are designing reports.</span></span> <span data-ttu-id="a3479-104">Debería implementar el ensamblado de extensión de procesamiento de datos para el Diseñador de informes como un ensamblado privado.</span><span class="sxs-lookup"><span data-stu-id="a3479-104">You should deploy your data processing extension assembly to Report Designer as a private assembly.</span></span> <span data-ttu-id="a3479-105">También tiene que realizar una entrada en el archivo de configuración del Diseñador de informes, RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="a3479-105">You also need to make an entry in the Report Designer configuration file, RSReportDesigner.config.</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="a3479-106">Para implementar un ensamblado de extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="a3479-106">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="a3479-107">Copie el ensamblado desde la ubicación de almacenamiento provisional en el directorio del Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="a3479-107">Copy your assembly from your staging location to the Report Designer directory.</span></span> <span data-ttu-id="a3479-108">La ubicación predeterminada del directorio del Diseñador de informes es C:\Archivos de programa\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="a3479-108">The default location of the Report Designer directory is C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="a3479-109">Una vez copiado el archivo de ensamblado, abra el archivo RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="a3479-109">After the assembly file is copied, open the RSReportDesigner.config file.</span></span> <span data-ttu-id="a3479-110">El archivo RSReportDesigner.config también se encuentra en el directorio del Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="a3479-110">The RSReportDesigner.config file is also located in the Report Designer directory.</span></span> <span data-ttu-id="a3479-111">Tiene que realizar una entrada en el archivo de configuración para el archivo de ensamblado de extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="a3479-111">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="a3479-112">Puede abrir el archivo de configuración con [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un editor de texto sencillo, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="a3479-112">You can open the configuration file with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or with a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="a3479-113">Busque el elemento **Data** en el archivo RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="a3479-113">Locate the **Data** element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="a3479-114">En la ubicación siguiente se debería realizar una entrada para la extensión de procesamiento de datos creada recientemente:</span><span class="sxs-lookup"><span data-stu-id="a3479-114">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="a3479-115">Agregue una entrada para la extensión de procesamiento de datos que incluya un elemento **Extension** con valores para los `Name` `Type` atributos, y `Visible` .</span><span class="sxs-lookup"><span data-stu-id="a3479-115">Add an entry for your data processing extension which includes an **Extension** element with values for the `Name`, `Type`, and `Visible` attributes.</span></span> <span data-ttu-id="a3479-116">La entrada podría tener la apariencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3479-116">Your entry might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="a3479-117">El valor de `Name` es el nombre único de la extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="a3479-117">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="a3479-118">El valor de `Type` es una lista separada por comas que incluye una entrada para el espacio de nombres completo de la clase que implementa las interfaces <xref:Microsoft.ReportingServices.Interfaces.IExtension> y <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection>, seguido del nombre del ensamblado (sin incluir la extensión de archivo .dll).</span><span class="sxs-lookup"><span data-stu-id="a3479-118">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="a3479-119">De forma predeterminada, las extensiones de procesamiento de datos están visibles.</span><span class="sxs-lookup"><span data-stu-id="a3479-119">By default, data processing extensions are visible.</span></span> <span data-ttu-id="a3479-120">Para ocultar una extensión de las interfaces de usuario, como Diseñador de informes, agregue un `Visible` atributo al elemento **Extension** y establézcalo en `false` .</span><span class="sxs-lookup"><span data-stu-id="a3479-120">To hide an extension from user interfaces, such as Report Designer, add a `Visible` attribute to the **Extension** element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="a3479-121">Finalmente, agregue un grupo de código para el ensamblado personalizado que conceda el permiso **FullTrust** para la extensión.</span><span class="sxs-lookup"><span data-stu-id="a3479-121">Finally, add a code group for your custom assembly that grants **FullTrust** permission for your extension.</span></span> <span data-ttu-id="a3479-122">Para ello, se agrega el grupo de código al archivo rspreviewpolicy.config, que se encuentra de forma predeterminada en la carpeta C:\Archivos de programa\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="a3479-122">You do this by adding the code group to the rspreviewpolicy.config file located by default in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span> <span data-ttu-id="a3479-123">El grupo de código podría tener la apariencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3479-123">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="a3479-124">La pertenencia de dirección URL es solo una de las muchas condiciones de pertenencia que podría elegir para la extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="a3479-124">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="a3479-125">Para más información sobre la seguridad de acceso del código de [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)], vea [Desarrollo seguro &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a3479-125">For more information about code access security in [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="generic-query-designer"></a><span data-ttu-id="a3479-126">Diseñador de consultas genérico</span><span class="sxs-lookup"><span data-stu-id="a3479-126">Generic Query Designer</span></span>  
 <span data-ttu-id="a3479-127">El Diseñador de consultas proporciona un diseñador de consultas genérico que puede utilizar con extensiones de procesamiento de datos personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a3479-127">Report Designer provides a generic query designer that you can use with custom data processing extensions.</span></span> <span data-ttu-id="a3479-128">Este diseñador está compuesto de dos paneles: uno de consulta y otro de resultados.</span><span class="sxs-lookup"><span data-stu-id="a3479-128">This designer consists of two panes: a query pane and a results pane.</span></span> <span data-ttu-id="a3479-129">Puede utilizar el diseñador genérico para escribir las consultas que la interfaz gráfica no admita.</span><span class="sxs-lookup"><span data-stu-id="a3479-129">You can use the generic designer to write queries that are not supported by the graphical interface.</span></span> <span data-ttu-id="a3479-130">A diferencia del diseñador gráfico de consultas, el diseñador genérico no comprueba la sintaxis de la consulta ni procede a reestructurarla.</span><span class="sxs-lookup"><span data-stu-id="a3479-130">Unlike the graphical query designer, the generic query designer does not check query syntax or restructure the query.</span></span>  
  
#### <a name="to-enable-the-generic-query-designer-for-a-custom-extension"></a><span data-ttu-id="a3479-131">Para habilitar el diseñador de consultas genérico para una extensión personalizada</span><span class="sxs-lookup"><span data-stu-id="a3479-131">To enable the generic query designer for a custom extension</span></span>  
  
-   <span data-ttu-id="a3479-132">Agregue la entrada siguiente al archivo RSReportDesigner.config bajo el elemento **Designer** , reemplazando el `Name` atributo por el nombre que proporcionó en las entradas anteriores.</span><span class="sxs-lookup"><span data-stu-id="a3479-132">Add the following entry to the RSReportDesigner.config file under the **Designer** element, replacing the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="a3479-133">Comprobación de la implementación</span><span class="sxs-lookup"><span data-stu-id="a3479-133">Verifying the Deployment</span></span>  
 <span data-ttu-id="a3479-134">Para poder comprobar la implementación, debe cerrar todas las instancias de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a3479-134">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="a3479-135">Una vez que haya finalizado todas las sesiones actuales, puede comprobar si la extensión de procesamiento de datos se implementó correctamente para el Diseñador de informes creando un proyecto de informe nuevo en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3479-135">After you have ended all current sessions, you can verify whether your data processing extension was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="a3479-136">La extensión se debe incluir en la lista de tipos de orígenes de datos disponibles al crear un conjunto de datos nuevo para el informe.</span><span class="sxs-lookup"><span data-stu-id="a3479-136">Your extension should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3479-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3479-137">See Also</span></span>  
 <span data-ttu-id="a3479-138">[Implementación de una extensión de procesamiento de datos](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="a3479-138">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="a3479-139">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="a3479-139">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="a3479-140">[Implementar una extensión de procesamiento de datos](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="a3479-140">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="a3479-141">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a3479-141">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
