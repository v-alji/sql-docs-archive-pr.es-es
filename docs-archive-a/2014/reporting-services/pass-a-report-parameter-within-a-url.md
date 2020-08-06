---
title: Pasar un parámetro de informe en una dirección URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], passing parameters
- passing parameters [Reporting Services]
ms.assetid: f93a94cc-27b5-435a-aa85-69e6ec6459ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cf41ed82728d5d7c840276e135937b08f83fb131
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749168"
---
# <a name="pass-a-report-parameter-within-a-url"></a><span data-ttu-id="f80a4-102">Pasar un parámetro de informe en una dirección URL</span><span class="sxs-lookup"><span data-stu-id="f80a4-102">Pass a Report Parameter Within a URL</span></span>
  <span data-ttu-id="f80a4-103">Puede pasar parámetros de informe a un informe incluyéndolos en un informe URL.</span><span class="sxs-lookup"><span data-stu-id="f80a4-103">You can pass report parameters to a report by including them in a report URL.</span></span> <span data-ttu-id="f80a4-104">Estos parámetros de dirección URL no tienen prefijo porque se pasan directamente al motor de procesamiento de informes.</span><span class="sxs-lookup"><span data-stu-id="f80a4-104">These URL parameters are not prefixed because they are passed directly to the report processing engine.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f80a4-105">Es importante que la dirección URL incluya la sintaxis de proxy de `_vti_bin` para enrutar la solicitud a través de SharePoint y el proxy HTTP de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f80a4-105">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="f80a4-106">El proxy agrega algún contexto a la solicitud HTTP, contexto que es necesario para garantizar la correcta ejecución del informe para los servidores de informes de modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f80a4-106">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
>   
>  <span data-ttu-id="f80a4-107">Si no incluye la sintaxis de proxy, debe prefijar el parámetro con *RP:*.</span><span class="sxs-lookup"><span data-stu-id="f80a4-107">If you don't include the proxy syntax, then you need to prefix the parameter with *rp:*.</span></span>  
  
 <span data-ttu-id="f80a4-108">Todos los parámetros de consulta pueden tener parámetros de informe correspondientes.</span><span class="sxs-lookup"><span data-stu-id="f80a4-108">All query parameters can have corresponding report parameters.</span></span> <span data-ttu-id="f80a4-109">Para pasar un parámetro de consulta a un informe, pase el parámetro de informe correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f80a4-109">You pass a query parameter to a report by passing the corresponding report parameter.</span></span> <span data-ttu-id="f80a4-110">Para más información, vea [Crear una consulta en el Diseñador de consultas relacionales &#40;Generador de informes y SSRS&#41;](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f80a4-110">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f80a4-111">Los parámetros de informe distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f80a4-111">Report parameters are case-sensitive.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="f80a4-112">Los parámetros de informe distinguen mayúsculas de minúsculas y usan los caracteres especiales siguientes:</span><span class="sxs-lookup"><span data-stu-id="f80a4-112">Report parameters are case-sensitive and utilize the following special characters:</span></span>  
> 
>  -   <span data-ttu-id="f80a4-113">Cualquier carácter de espacio en blanco en la cadena de dirección URL se reemplaza con los caracteres "% 20", según los estándares de codificación de direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="f80a4-113">Any space characters in the URL string are replaced with the characters "%20," according to URL encoding standards.</span></span>  
> -   <span data-ttu-id="f80a4-114">Un carácter de espacio en la parte del parámetro de la dirección URL se reemplaza con un carácter más (+).</span><span class="sxs-lookup"><span data-stu-id="f80a4-114">A space character in the parameter portion of the URL is replaced with a plus character (+).</span></span>  
> -   <span data-ttu-id="f80a4-115">Un punto y coma en cualquier parte de la cadena se reemplaza con los caracteres “%3A”.</span><span class="sxs-lookup"><span data-stu-id="f80a4-115">A semicolon in any portion of the string is replaced with the characters "%3A."</span></span>  
> -   <span data-ttu-id="f80a4-116">Los exploradores deberían realizar de forma automática la codificación de dirección URL apropiada.</span><span class="sxs-lookup"><span data-stu-id="f80a4-116">Browsers should automatically perform the proper URL encoding.</span></span> <span data-ttu-id="f80a4-117">No tiene que codificar ninguno de los caracteres manualmente.</span><span class="sxs-lookup"><span data-stu-id="f80a4-117">You do not have to encode any of the characters manually.</span></span>  
  
 <span data-ttu-id="f80a4-118">Para establecer un parámetro de informe dentro de una dirección URL, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f80a4-118">To set a report parameter within a URL, use the following syntax:</span></span>  
  
```  
  
parameter=value  
```  
  
 <span data-ttu-id="f80a4-119">Por ejemplo, para especificar dos parámetros, "ReportMonth" y "ReportYear", definidos en un informe, use las direcciones URL siguientes para un servidor de informes en modo nativo:</span><span class="sxs-lookup"><span data-stu-id="f80a4-119">For example, to specify two parameters, "ReportMonth" and "ReportYear", defined in a report, use the following URL for a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="f80a4-120">Por ejemplo, para especificar los mismos parámetros definidos en un informe, use las direcciones URL siguientes para un servidor de informes en modo integrado de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="f80a4-120">For example, to specify the same two parameters defined in a report, use the following URL for a SharePoint integrated mode report server.</span></span> <span data-ttu-id="f80a4-121">Anote `/_vti_bin`:</span><span class="sxs-lookup"><span data-stu-id="f80a4-121">Note the `/_vti_bin`:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="f80a4-122">Para pasar un valor NULL para un parámetro, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f80a4-122">To pass a null value for a parameter, use the following syntax:</span></span>  
  
```  
  
parameter  
:isnull=true  
  
```  
  
 <span data-ttu-id="f80a4-123">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="f80a4-123">For example,</span></span>  
  
```  
SalesOrderNumber:isnull=true  
```  
  
 <span data-ttu-id="f80a4-124">Para pasar un valor `Boolean`, use 0 para FALSE o 1 para TRUE.</span><span class="sxs-lookup"><span data-stu-id="f80a4-124">To pass a `Boolean` value, use 0 for false and 1 for true.</span></span> <span data-ttu-id="f80a4-125">Para pasar un valor `Float`, incluya el separador decimal correspondiente a la configuración regional del servidor.</span><span class="sxs-lookup"><span data-stu-id="f80a4-125">To pass a `Float` value, include the decimal separator of the server locale</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f80a4-126">Si un informe contiene un parámetro de informe con un valor predeterminado y el valor de la propiedad `Prompt` es `false` (es decir, la propiedad Preguntar al usuario no está seleccionada en el Administrador de informes), no puede pasar un valor dentro de una dirección URL para ese parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="f80a4-126">If your report contains a report parameter that has a default value and the value of the `Prompt` property is `false` (that is, the Prompt User property is not selected in Report Manager), then you cannot pass a value for that report parameter within a URL.</span></span> <span data-ttu-id="f80a4-127">Esto proporciona a los administradores una opción para evitar que los usuarios finales agreguen o modifiquen los valores de ciertos parámetros de informe.</span><span class="sxs-lookup"><span data-stu-id="f80a4-127">This provides administrators an option for preventing end users from adding or modifying the values of certain report parameters.</span></span>  
  
##  <a name="additional-examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="f80a4-128">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="f80a4-128">Additional Examples</span></span>  
 <span data-ttu-id="f80a4-129">En el ejemplo siguiente de dirección URL se incluyen espacios en blanco y varios parámetros</span><span class="sxs-lookup"><span data-stu-id="f80a4-129">The following URL example includes spaces and multiple parameters</span></span>  
  
-   <span data-ttu-id="f80a4-130">El nombre de carpeta de "Equipo de educación de usuarios de SQL Server" incluye espacios en blanco y, por tanto, el signo "+" reemplaza cada espacio.</span><span class="sxs-lookup"><span data-stu-id="f80a4-130">Folder name of "SQL Server User Education Team" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="f80a4-131">El nombre de informe "informe de proyecto de equipo" incluye espacios en blanco y, por tanto, el signo "+" reemplaza cada espacio.</span><span class="sxs-lookup"><span data-stu-id="f80a4-131">Report name of "team project report" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="f80a4-132">Pasa dos parámetros de "teamgrouping2" con un valor de "xgroup" y "teamgrouping1" con un valor de "ygroup".</span><span class="sxs-lookup"><span data-stu-id="f80a4-132">Passes two parameters of "teamgrouping2" with a value of "xgroup" and "teamgrouping1" with a value of "ygroup".</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup  
```  
  
 <span data-ttu-id="f80a4-133">En el ejemplo siguiente de dirección URL se incluye un parámetro "OrderID" con varios valores.</span><span class="sxs-lookup"><span data-stu-id="f80a4-133">The following URL example includes a multi-value parameter "OrderID.</span></span> <span data-ttu-id="f80a4-134">El formato de un parámetro multivalor es repetir el nombre del parámetro para cada valor.</span><span class="sxs-lookup"><span data-stu-id="f80a4-134">The format for a Multi-Value parameter is to repeat the parameter name for each value.</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup&OrderID=747&OrderID=787&OrderID=12  
```  
  
 <span data-ttu-id="f80a4-135">En el siguiente ejemplo de dirección URL se pasa un único parámetro de *SellStartDate* con un valor de "7/1/2005" para un servidor de informes en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f80a4-135">The following URL example passes a single parameter of *SellStartDate* with a value of "7/1/2005", for a native mode report server.</span></span>  
  
```  
http://myserver/ReportServer/Pages/ReportViewer.aspx?%2fProduct_and_Sales_Report_AdventureWorks&SellStartDate=7/1/2005  
```  
  
## <a name="see-also"></a><span data-ttu-id="f80a4-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f80a4-136">See Also</span></span>  
 <span data-ttu-id="f80a4-137">[Acceso URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f80a4-137">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="f80a4-138">Referencia de parámetros de acceso URL</span><span class="sxs-lookup"><span data-stu-id="f80a4-138">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
