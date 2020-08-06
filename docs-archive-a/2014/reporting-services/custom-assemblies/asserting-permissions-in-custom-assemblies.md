---
title: Validar los permisos en ensamblados personalizados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- secure calls [Reporting Services]
- custom assemblies [Reporting Services], permissions
- permission sets [Reporting Services]
- asserting permissions
- permissions [Reporting Services], custom assemblies
- limited permission sets
- security configuration files [Reporting Services]
ms.assetid: 3afb9631-f15e-405e-990b-ee102828f298
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cba3c0b74712b6b4d0f6b5c58925cfd562f0df77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661806"
---
# <a name="asserting-permissions-in-custom-assemblies"></a><span data-ttu-id="157e3-102">Validar los permisos en ensamblados personalizados</span><span class="sxs-lookup"><span data-stu-id="157e3-102">Asserting Permissions in Custom Assemblies</span></span>
  <span data-ttu-id="157e3-103">De forma predeterminada, el código de ensamblado personalizado se ejecuta con el conjunto de permisos de **Ejecución** limitado.</span><span class="sxs-lookup"><span data-stu-id="157e3-103">By default, custom assembly code runs with the limited **Execution** permission set.</span></span> <span data-ttu-id="157e3-104">En algunos casos, puede desear implementar un ensamblado personalizado que realice llamadas protegidas a los recursos protegidos dentro del sistema de seguridad (como un archivo o el Registro).</span><span class="sxs-lookup"><span data-stu-id="157e3-104">In some cases, you may wish to implement a custom assembly that makes secured calls to protected resources within your security system (such as a file or the registry).</span></span> <span data-ttu-id="157e3-105">Para ello, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="157e3-105">In order to accomplish this, you must do the following:</span></span>  
  
1.  <span data-ttu-id="157e3-106">Identifique los permisos exactos que el código necesita para realizar la llamada segura.</span><span class="sxs-lookup"><span data-stu-id="157e3-106">Identify the exact permissions that your code needs in order to make the secured call.</span></span> <span data-ttu-id="157e3-107">Si este método forma parte de una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] biblioteca, esta información debe incluirse en la documentación del método.</span><span class="sxs-lookup"><span data-stu-id="157e3-107">If this method is part of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] library, this information should be included in the method documentation.</span></span>  
  
2.  <span data-ttu-id="157e3-108">Modifique los archivos de configuración de directiva de servidor de informes para conceder los permisos necesarios al ensamblado personalizado.</span><span class="sxs-lookup"><span data-stu-id="157e3-108">Modify the report server policy configuration files in order to grant the custom assembly the required permissions.</span></span> <span data-ttu-id="157e3-109">Para más información sobre los archivos de configuración de directivas de seguridad, vea [Usar los archivos de directivas de seguridad de Reporting Services](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span><span class="sxs-lookup"><span data-stu-id="157e3-109">For more information about the security policy configuration files, see [Using Reporting Services Security Policy Files](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span></span>  
  
3.  <span data-ttu-id="157e3-110">Valide los permisos necesarios como parte del método en el que se realiza la llamada segura.</span><span class="sxs-lookup"><span data-stu-id="157e3-110">Assert the required permissions as part of the method in which the secure call is made.</span></span> <span data-ttu-id="157e3-111">Esto es necesario porque el código de ensamblado personalizado al que llama el servidor de informes forma parte del ensamblado de expresiones del informe, que se ejecuta de forma predeterminada con el permiso de **Ejecución**.</span><span class="sxs-lookup"><span data-stu-id="157e3-111">This is required because the custom assembly code that is called by the report server is part of the report expression host assembly, which runs with **Execution** permission by default.</span></span> <span data-ttu-id="157e3-112">El conjunto de permisos de **Ejecución** permite la ejecución del código, pero no usar recursos protegidos.</span><span class="sxs-lookup"><span data-stu-id="157e3-112">The **Execution** permission set enables code to run, but not to use protected resources.</span></span>  
  
4.  <span data-ttu-id="157e3-113">Marque el ensamblado personalizado con **AllowPartiallyTrustedCallersAttribute** si está firmado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="157e3-113">Mark the custom assembly with **AllowPartiallyTrustedCallersAttribute** if it is signed with a strong name.</span></span> <span data-ttu-id="157e3-114">Esto es necesario porque a los ensamblados personalizados se les llama desde una expresión de informe que forma parte del ensamblado de expresiones del informe, al que, de forma predeterminada, no se le concede **FullTrust**; por tanto, realiza las llamadas de forma "parcialmente confiable".</span><span class="sxs-lookup"><span data-stu-id="157e3-114">This is required because custom assemblies are called from a report expression that is part of the report expression host assembly, which, by default, is not granted **FullTrust**; thus it is a "partially trusted" caller.</span></span> <span data-ttu-id="157e3-115">Para más información, vea [Usar ensamblados personalizados con nombre seguro](using-strong-named-custom-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="157e3-115">For more information, see [Using Strong-Named Custom Assemblies](using-strong-named-custom-assemblies.md).</span></span>  
  
## <a name="implementing-a-secure-call"></a><span data-ttu-id="157e3-116">Implementar una llamada segura</span><span class="sxs-lookup"><span data-stu-id="157e3-116">Implementing a Secure Call</span></span>  
 <span data-ttu-id="157e3-117">Puede modificar los archivos de configuración de directiva para conceder permisos concretos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="157e3-117">You can modify the policy configuration files to grant your assembly specific permissions.</span></span> <span data-ttu-id="157e3-118">Por ejemplo, si estuviera escribiendo un ensamblado personalizado para administrar la conversión de moneda, podría necesitar leer las tasas de cambio de moneda actuales de un archivo.</span><span class="sxs-lookup"><span data-stu-id="157e3-118">For example, if you were writing a custom assembly to handle currency conversion, you might need to read the current currency exchange rates from a file.</span></span> <span data-ttu-id="157e3-119">Para recuperar la información de la tasa, necesitaría agregar un permiso de seguridad adicional, **FileIOPermission**, al conjunto de permisos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="157e3-119">To retrieve the rate information, you would need to add an additional security permission, **FileIOPermission**, to your permission set for the assembly.</span></span> <span data-ttu-id="157e3-120">Puede realizar la entrada adicional siguiente en el archivo de configuración de directiva:</span><span class="sxs-lookup"><span data-stu-id="157e3-120">You can make the following additional entry in the policy configuration file:</span></span>  
  
```  
<PermissionSet class="NamedPermissionSet"  
   version="1"  
   Name="CurrencyRatesFilePermissionSet"  
   Description="A special permission set that grants read access to my currency rates file.">  
      <IPermission class="FileIOPermission"  
         version="1"  
         Read="C:\CurrencyRates.xml"/>  
      <IPermission class="SecurityPermission"  
         version="1"  
         Flags="Execution, Assertion"/>  
</PermissionSet>  
```  
  
 <span data-ttu-id="157e3-121">A continuación, agrega un grupo de código que hace referencia a ese conjunto de permisos:</span><span class="sxs-lookup"><span data-stu-id="157e3-121">You then add a code group that references that permission set:</span></span>  
  
```  
<CodeGroup class="UnionCodeGroup"  
   version="1"  
   PermissionSetName="CurrencyRatesFilePermissionSet"  
   Name="MyNewCodeGroup"  
   Description="A special code group for my custom assembly.">  
   <IMembershipCondition class="UrlMembershipCondition"  
      version="1"  
      Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\MSSQL\Reporting Services\ReportServer\bin\CurrencyConversion.dll"/>  
</CodeGroup>  
```  
  
 <span data-ttu-id="157e3-122">Para que el código adquiera el permiso adecuado, debe validar el permiso dentro del código de ensamblado personalizado.</span><span class="sxs-lookup"><span data-stu-id="157e3-122">In order for your code to acquire the appropriate permission, you must assert the permission within your custom assembly code.</span></span> <span data-ttu-id="157e3-123">Por ejemplo, si desea agregar acceso de solo lectura a un archivo XML, C:\CurrencyRates.xml, debe agregar el código siguiente al método:</span><span class="sxs-lookup"><span data-stu-id="157e3-123">For example, if you want to add read-only access to an XML file, C:\CurrencyRates.xml, you must add the following code to your method:</span></span>  
  
```  
// C#  
FileIOPermission permission = new FileIOPermission(FileIOPermissionAccess.Read, @"C:\CurrencyRates.xml");  
try  
{  
   permission.Assert();  
   // Load the XML currency rates file  
   XmlDocument doc = new XmlDocument();  
   doc.Load(@"C:\CurrencyRates.xml");  
...  
```  
  
 <span data-ttu-id="157e3-124">También puede agregar la aserción como un atributo de método:</span><span class="sxs-lookup"><span data-stu-id="157e3-124">You can also add the assertion as a method attribute:</span></span>  
  
```  
[FileIOPermissionAttribute(SecurityAction.Assert, Read=@"C:\CurrencyRates.xml")]  
```  
  
 <span data-ttu-id="157e3-125">Para obtener más información, vea el tema sobre la seguridad de .NET Framework en la Guía del programador de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="157e3-125">For more information, see ".NET Framework Security" in the .NET Framework Developer's Guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="157e3-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="157e3-126">See Also</span></span>  
 [<span data-ttu-id="157e3-127">Usar ensamblados personalizados con informes</span><span class="sxs-lookup"><span data-stu-id="157e3-127">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
