---
title: Acceso al proveedor WMI de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services]
- programming [Reporting Services]
ms.assetid: 22cfbeb8-4ea3-4182-8f54-3341c771e87b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db0848ae8c988229a1804bbd4b19e6c38b68c35f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748639"
---
# <a name="access-the-reporting-services-wmi-provider"></a><span data-ttu-id="d952e-102">Obtener acceso al proveedor WMI de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d952e-102">Access the Reporting Services WMI Provider</span></span>
  <span data-ttu-id="d952e-103">El proveedor WMI de Reporting Services expone dos clases de WMI para administrar instancias del servidor de informes en modo nativo mediante scripts:</span><span class="sxs-lookup"><span data-stu-id="d952e-103">The Reporting Services WMI provider exposes two WMI classes for administration of Native mode report server instances through scripting:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d952e-104">A partir de la versión de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , el proveedor WMI se admite para los servidores de informes en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="d952e-104">Starting with the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, the WMI provider is supported for only native mode report servers.</span></span> <span data-ttu-id="d952e-105">Los servidores de informes en modo de SharePoint pueden administrarse con las páginas de Administración central de SharePoint y scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d952e-105">SharePoint mode report servers can be managed with SharePoint Central Administration pages and PowerShell scripts.</span></span>  
  
|<span data-ttu-id="d952e-106">Clase</span><span class="sxs-lookup"><span data-stu-id="d952e-106">Class</span></span>|<span data-ttu-id="d952e-107">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d952e-107">Namespace</span></span>|<span data-ttu-id="d952e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d952e-108">Description</span></span>|  
|-----------|---------------|-----------------|  
|<span data-ttu-id="d952e-109">MSReportServer_Instance</span><span class="sxs-lookup"><span data-stu-id="d952e-109">MSReportServer_Instance</span></span>|<span data-ttu-id="d952e-110">root\Microsoft\SqlServer\ReportServer\ RS_ *\<EncodedInstanceName>* \v11</span><span class="sxs-lookup"><span data-stu-id="d952e-110">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11</span></span>|<span data-ttu-id="d952e-111">Proporciona la información básica requerida para que un cliente se conecte a un servidor de informes instalado.</span><span class="sxs-lookup"><span data-stu-id="d952e-111">Provides basic information required for a client to connect to an installed report server.</span></span>|  
|<span data-ttu-id="d952e-112">MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d952e-112">MSReportServer_ConfigurationSetting</span></span>|<span data-ttu-id="d952e-113">root\Microsoft\SqlServer\ReportServer\ RS_ *\<EncodedInstanceName>* \v11\Admin</span><span class="sxs-lookup"><span data-stu-id="d952e-113">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11\Admin</span></span>|<span data-ttu-id="d952e-114">Representa la instalación y los parámetros de tiempo de ejecución de una instancia del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="d952e-114">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="d952e-115">Estos parámetros se guardan en el archivo de configuración del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="d952e-115">These parameters are stored in the configuration file for the report server.</span></span><br /><br /> <span data-ttu-id="d952e-116">**\*\* Importante \*\*** Esta clase solo está disponible con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="d952e-116">**\*\* Important \*\*** This class is only accessible with administrative privileges.</span></span>|  
  
 <span data-ttu-id="d952e-117">Se crea una instancia de cada una de las clases anteriores para cada instancia del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="d952e-117">An instance of each of the above classes is created for each report server instance.</span></span> <span data-ttu-id="d952e-118">Puede utilizar cualquier herramienta de Microsoft o de terceros para tener acceso a los objetos de WMI expuestos por el servidor de informes, incluidas las interfaces de programación de WMI, expuestas por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d952e-118">You can use any Microsoft or third party tools to access the WMI objects exposed by the report server, including WMI programming interfaces exposed by the .NET Framework itself.</span></span> <span data-ttu-id="d952e-119">En este tema se describe cómo acceder y usar las instancias de clases WMI con el comando de PowerShell [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span><span class="sxs-lookup"><span data-stu-id="d952e-119">This topic describes how to access and use the WMI class instances with the PowerShell command [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span></span>  
  
## <a name="determine-the-instance-name-in-the-namespace-string"></a><span data-ttu-id="d952e-120">Determinar el nombre de instancia en la cadena del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d952e-120">Determine the Instance Name in the Namespace String</span></span>  
 <span data-ttu-id="d952e-121">El nombre de instancia de la ruta de acceso del espacio de nombres para las clases de WMI de Reporting Services es una codificación de los nombres de instancia especificados al instalar las instancias con nombre de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d952e-121">The instance name in the namespace path for the Reporting Services WMI classes is an encoding of the instance names that you specify when installing the named Reporting Services instances.</span></span> <span data-ttu-id="d952e-122">Concretamente, los caracteres especiales en los nombres de instancia se codifican.</span><span class="sxs-lookup"><span data-stu-id="d952e-122">Namely, special characters in the instance names are encoded.</span></span> <span data-ttu-id="d952e-123">Por ejemplo, el carácter de subrayado (_) se codifica como "_5f", por lo que el nombre de instancia "My_Instance" se codificará como "My_5fInstance" en la ruta de acceso del espacio de nombres de WMI.</span><span class="sxs-lookup"><span data-stu-id="d952e-123">For example, an underline (_) is encoded as "_5f", so an instance name of "My_Instance" is encoded as "My_5fInstance" in the WMI namespace path.</span></span>  
  
 <span data-ttu-id="d952e-124">Para enumerar los nombres de instancia codificados de las instancias del servidor de informes en la ruta de acceso del espacio de nombres de WMI, utilice el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d952e-124">To list the encoded instance names of your report server instances in the WMI namespace path, use the following PowerShell command:</span></span>  
  
```powershell
Get-WmiObject -Namespace root\Microsoft\SqlServer\ReportServer -Class __Namespace -ComputerName hostname | Select Name  
```  
  
## <a name="access-the-wmi-classes-using-powershell"></a><span data-ttu-id="d952e-125">Obtener acceso a clases de WMI mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="d952e-125">Access the WMI Classes Using PowerShell</span></span>  
 <span data-ttu-id="d952e-126">Para obtener acceso a las clases de WMI, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d952e-126">To access the WMI classes, run the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace <namespacename> -Class <classname> -ComputerName <hostname>  
```  
  
 <span data-ttu-id="d952e-127">Por ejemplo, para tener acceso a la clase MSReportServer_ConfigurationSetting en la instancia predeterminada del servidor de informes del host myrshost, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="d952e-127">For example, to access the MSReportServer_ConfigurationSetting class on the default report server instance of the host myrshost, run the following command.</span></span> <span data-ttu-id="d952e-128">La instancia predeterminada del servidor de informes se debe instalar en myrshost para que el comando se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="d952e-128">The default report server instance must be installed on myrshost for this command to succeed.</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLSERER\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost  
```  
  
 <span data-ttu-id="d952e-129">Esta sintaxis de comando genera todos los nombres de propiedad y valores de la clase.</span><span class="sxs-lookup"><span data-stu-id="d952e-129">This command syntax outputs all class property names and values.</span></span> <span data-ttu-id="d952e-130">Observe que se devuelven todas las instancias de la clase MSReportServer_ConfigurationSetting, aunque esté obteniendo acceso a la clase en el espacio de nombres de la instancia predeterminada del servidor de informes (RS_MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="d952e-130">Note that all instances of the class MSReportServer_ConfigurationSetting is returned, even though you are accessing the class in the namespace of the default report server instance (RS_MSSQLSERVER).</span></span> <span data-ttu-id="d952e-131">Por ejemplo, si myrshost se instala con la instancia predeterminada del servidor de informes y una instancia con nombre del servidor de informes denominada SHAREPOINT, este comando devolverá dos objetos de WMI y generará los nombres de propiedad y valores para ambas instancias del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="d952e-131">For example, if myrshost is installed with the default report server instance and a named report server instance called SHAREPOINT, this command will return two WMI objects and output the property names and values for both report server instances.</span></span>  
  
 <span data-ttu-id="d952e-132">Para que se devuelva una instancia de clase específica cuando se devuelven varias instancias, use el parámetro -Filter para filtrar los resultados en función de propiedades con valores únicos, como InstanceName.</span><span class="sxs-lookup"><span data-stu-id="d952e-132">To return a specific class instance when multiple instances are returned, use the -Filter parameter to filter the results based on properties with unique values such as InstanceName.</span></span> <span data-ttu-id="d952e-133">Por ejemplo, para devolver solo el objeto de WMI de la instancia predeterminada del servidor de informes, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d952e-133">For example, to return only the WMI object for the default report server instance, use the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='MSSQLSERVER'"  
```  
  
## <a name="query-the-available-methods-and-properties"></a><span data-ttu-id="d952e-134">Consultar los métodos y propiedades disponibles</span><span class="sxs-lookup"><span data-stu-id="d952e-134">Query the Available Methods and Properties</span></span>  
 <span data-ttu-id="d952e-135">Para ver qué métodos y propiedades están disponibles en una de las clases de WMI de Reporting Services, canalice los resultados desde Get-WmiObject al comando Get-Member.</span><span class="sxs-lookup"><span data-stu-id="d952e-135">To see what methods and properties are available in one of the Reporting Services WMI classes, pipe the results from Get-WmiObject to the Get-Member command.</span></span> <span data-ttu-id="d952e-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d952e-136">For example:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost | Get-Member  
```  
  
 <span data-ttu-id="d952e-137">Para obtener documentación sobre las propiedades y los métodos de las clases de Reporting Services WMI, vea....</span><span class="sxs-lookup"><span data-stu-id="d952e-137">For documentation on the properties and methods of the Reporting Services WMI classes, see ....</span></span>  
  
## <a name="use-a-wmi-method-or-property"></a><span data-ttu-id="d952e-138">Utilizar un método o propiedad de WMI</span><span class="sxs-lookup"><span data-stu-id="d952e-138">Use a WMI Method or Property</span></span>  
 <span data-ttu-id="d952e-139">Una vez tenga los objetos de WMI en las clases de Reporting Services y conozca los métodos y propiedades disponibles, podrá usar esos métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="d952e-139">Once you have the WMI objects to the Reporting Services classes and know the available methods and properties, you can use these methods and properties.</span></span> <span data-ttu-id="d952e-140">Por ejemplo, si tiene una instancia con nombre del servidor de informes en modo integrado de SharePoint denominada SHAREPOINT, use la siguiente secuencia de comandos para recuperar la dirección URL del sitio de Administración central de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="d952e-140">For example, if you have a named report server instance in SharePoint integrated mode called SHAREPOINT, use the following command sequence to retrieve the URL for the SharePoint Central Administration site:</span></span>  
  
```powershell
$rsconfig = Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='SHAREPOINT'"  
$rsconfig.GetAdminSiteUrl()  
```  
  
## <a name="see-also"></a><span data-ttu-id="d952e-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d952e-141">See Also</span></span>
 <span data-ttu-id="d952e-142">[Reporting Services referencia de la biblioteca del proveedor WMI &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d952e-142">[Reporting Services WMI Provider Library Reference &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="d952e-143">Archivo de configuración RSReportServer</span><span class="sxs-lookup"><span data-stu-id="d952e-143">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
