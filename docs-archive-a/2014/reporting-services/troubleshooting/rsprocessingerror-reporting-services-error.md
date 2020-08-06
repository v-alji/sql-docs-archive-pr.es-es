---
title: rsProcessingError - Error de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsProcessingError
ms.assetid: 414ee58a-8251-4367-9a8e-10c068d17280
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ca98c5532db080ab1e146e2aaa81e24fcb25579b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675203"
---
# <a name="rsprocessingerror---reporting-services-error"></a><span data-ttu-id="c0038-102">rsProcessingError - Error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c0038-102">rsProcessingError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="c0038-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c0038-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c0038-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="c0038-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="c0038-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="c0038-105">Event ID</span></span>|<span data-ttu-id="c0038-106">rsProcessingError</span><span class="sxs-lookup"><span data-stu-id="c0038-106">rsProcessingError</span></span>|  
|<span data-ttu-id="c0038-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="c0038-107">Event Source</span></span>|<span data-ttu-id="c0038-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources</span><span class="sxs-lookup"><span data-stu-id="c0038-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources</span></span>|  
|<span data-ttu-id="c0038-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c0038-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="c0038-110">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c0038-110">Message Text</span></span>|<span data-ttu-id="c0038-111">Error al procesar el informe.</span><span class="sxs-lookup"><span data-stu-id="c0038-111">Errors have occurred in report processing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c0038-112">Explicación</span><span class="sxs-lookup"><span data-stu-id="c0038-112">Explanation</span></span>  
 <span data-ttu-id="c0038-113">Se encontraron uno o varios errores al publicar, procesar, obtener una vista previa localmente, ver desde el servidor de informes, o crear una suscripción para un informe.</span><span class="sxs-lookup"><span data-stu-id="c0038-113">One or more errors were encountered while publishing, processing, previewing locally, viewing from the report server, or creating a subscription for a report.</span></span> <span data-ttu-id="c0038-114">Este mensaje de error indica que se ha detectado, como mínimo, un error.</span><span class="sxs-lookup"><span data-stu-id="c0038-114">This error message indicates at least one error was detected.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="c0038-115">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="c0038-115">Possible Causes</span></span>  
 <span data-ttu-id="c0038-116">Las causas posibles incluyen:</span><span class="sxs-lookup"><span data-stu-id="c0038-116">Possible causes include:</span></span>  
  
-   <span data-ttu-id="c0038-117">Se ha producido un error de procesamiento en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c0038-117">A processing error occurred on the report server.</span></span>  
  
-   <span data-ttu-id="c0038-118">Se ha producido un error de procesamiento durante el procesamiento local de informes al obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="c0038-118">A processing error occurred during local report processing when previewing a report.</span></span>  
  
-   <span data-ttu-id="c0038-119">El resultado de la evaluación de una expresión de grupo es un tipo de datos incorrecto.</span><span class="sxs-lookup"><span data-stu-id="c0038-119">A group expression evaluated to an incorrect data type.</span></span>  
  
-   <span data-ttu-id="c0038-120">Una definición de filtro especificaba dos expresiones que se evaluaron como tipos de datos que no se pudieron comparar.</span><span class="sxs-lookup"><span data-stu-id="c0038-120">A filter definition specified two expressions that evaluated to data types that could not be compared.</span></span>  
  
-   <span data-ttu-id="c0038-121">Una expresión hace referencia a un campo no existente en la colección de campos.</span><span class="sxs-lookup"><span data-stu-id="c0038-121">An expression referenced a non-existing field in the Fields collection.</span></span>  
  
-   <span data-ttu-id="c0038-122">Una expresión incluía una llamada a una función de agregado con un ámbito no válido o en conflicto.</span><span class="sxs-lookup"><span data-stu-id="c0038-122">An expression included an aggregate function call with an invalid or conflicting scope.</span></span>  
  
-   <span data-ttu-id="c0038-123">Una expresión hacía referencia a un parámetro no existente en la colección Parámetros del informe.</span><span class="sxs-lookup"><span data-stu-id="c0038-123">An expression referenced a non-existing parameter in the Report Parameters collection.</span></span>  
  
-   <span data-ttu-id="c0038-124">No se pudo cargar un ensamblado personalizado o un ensamblado de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que estaba implementado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="c0038-124">A custom assembly or a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] assembly that was incorrectly deployed failed to load.</span></span>  
  
-   <span data-ttu-id="c0038-125">Un parámetro que tiene la propiedad que acepta valores NULL establecida en `False` ha detectado un valor null en el parámetro.</span><span class="sxs-lookup"><span data-stu-id="c0038-125">A parameter that has the Nullable property set to `False` has detected a null value in the parameter.</span></span>  
  
-   <span data-ttu-id="c0038-126">Una presión para la propiedad Hidden de una región de datos contiene un error: Referencia a objeto no establecida como instancia de un objeto.</span><span class="sxs-lookup"><span data-stu-id="c0038-126">An expression for the Hidden property of a data region contains an error: Object reference not set to an instance of an object.</span></span>  
  
-   <span data-ttu-id="c0038-127">Una expresión incluía una llamada de función no válida o un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="c0038-127">An expression included an invalid function call or syntax error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c0038-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c0038-128">User Action</span></span>  
  
### <a name="finding-more-information"></a><span data-ttu-id="c0038-129">Buscar más información</span><span class="sxs-lookup"><span data-stu-id="c0038-129">Finding More Information</span></span>  
 <span data-ttu-id="c0038-130">Realice una o más de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0038-130">Do one or more of the following actions:</span></span>  
  
-   <span data-ttu-id="c0038-131">Si ve el informe desde el servidor de informes o como una suscripción, lea todo el texto del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="c0038-131">If you are viewing the report from the report server or if you are viewing the report as a subscription, look at the entire text of the error message.</span></span> <span data-ttu-id="c0038-132">En él se proporciona información adicional.</span><span class="sxs-lookup"><span data-stu-id="c0038-132">Additional information is provided in the expanded text.</span></span>  
  
-   <span data-ttu-id="c0038-133">Si está creando un informe en el Diseñador de informes y observa este error al obtener una vista previa o al publicar el informe, se proporcionará información adicional en la ventana Lista de errores.</span><span class="sxs-lookup"><span data-stu-id="c0038-133">If you are authoring a report in Report Designer and see this error when you preview or publish the report, additional information is provided in the Error List window.</span></span>  
  
-   <span data-ttu-id="c0038-134">Si está creando un informe en Report Designer Preview, lea todo el texto del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="c0038-134">If you are authoring a report in Report Designer Preview, look at the entire text of the error message.</span></span> <span data-ttu-id="c0038-135">En él se proporciona información adicional.</span><span class="sxs-lookup"><span data-stu-id="c0038-135">Additional information is provided in the expanded text.</span></span>  
  
-   <span data-ttu-id="c0038-136">Si está viendo un informe como administrador local en el servidor de informes, puede ver la pila de llamadas si hace clic con el botón derecho en la página y selecciona **Ver código fuente**.</span><span class="sxs-lookup"><span data-stu-id="c0038-136">If you are viewing a report on the report server, and if you are running as local administrator on the report server, you can view the call stack if you right-click the page and select **View Source**.</span></span> <span data-ttu-id="c0038-137">En ella se proporciona información adicional.</span><span class="sxs-lookup"><span data-stu-id="c0038-137">Additional information is provided in the call stack.</span></span>  
  
-   <span data-ttu-id="c0038-138">Si actúa como administrador local en el servidor de informes, busque `ReportProcessingException`en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="c0038-138">If you are running as local administrator on the report server, search the log file for `ReportProcessingException`.</span></span> <span data-ttu-id="c0038-139">Las entradas del registro contienen más información.</span><span class="sxs-lookup"><span data-stu-id="c0038-139">Log entries contain more information.</span></span> <span data-ttu-id="c0038-140">El archivo de registro del servidor de informes se encuentra normalmente en \<*drive*> : \Archivos de programa\Microsoft SQL Server\MSRS12. MSSQLSERVER\Reporting Services\LogFiles\ ReportServerService__*marcadefechayhora*. log.</span><span class="sxs-lookup"><span data-stu-id="c0038-140">The report server log file is typically located at \<*drive*>:\Program Files\Microsoft SQL Server\MSRS12.MSSQLSERVER\Reporting Services\LogFiles\ReportServerService__*datetimestamp*.log.</span></span> <span data-ttu-id="c0038-141">Para más información, vea [Archivos de registro y orígenes de Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="c0038-141">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
### <a name="failed-to-load-expression-host-assembly"></a><span data-ttu-id="c0038-142">Error al cargar el ensamblado de expresiones</span><span class="sxs-lookup"><span data-stu-id="c0038-142">Failed to Load Expression Host Assembly</span></span>  
 <span data-ttu-id="c0038-143">Los ensamblados personalizados necesitan tener un nombre seguro y el atributo AllowPartiallyTrustedCallers establecido.</span><span class="sxs-lookup"><span data-stu-id="c0038-143">Custom assemblies must have strong name signing and the attribute AllowPartiallyTrustedCallers set.</span></span> <span data-ttu-id="c0038-144">Para obtener más información, consulte [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md) y [Understanding Security Policies](../extensions/secure-development/understanding-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c0038-144">For more information, see [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md) and [Understanding Security Policies](../extensions/secure-development/understanding-security-policies.md).</span></span>  
  
### <a name="a-built-in-global-name-does-not-exist"></a><span data-ttu-id="c0038-145">Un nombre global integrado no existe</span><span class="sxs-lookup"><span data-stu-id="c0038-145">A Built-in Global Name Does Not Exist</span></span>  
 <span data-ttu-id="c0038-146">Compruebe la ortografía de las expresiones.</span><span class="sxs-lookup"><span data-stu-id="c0038-146">Check the spelling in expressions.</span></span> <span data-ttu-id="c0038-147">En los parámetros y nombres de campo globales integrados se distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c0038-147">Built-in globals, parameters, and field names are case-sensitive.</span></span> <span data-ttu-id="c0038-148">En la expresión que produce el error, compruebe que el nombre existe realmente en el informe y que está escrito con la grafía correcta.</span><span class="sxs-lookup"><span data-stu-id="c0038-148">In the expression causing the error, check that the name actually exists in the report and that it is spelled correctly.</span></span> <span data-ttu-id="c0038-149">Para obtener más información, vea [Colecciones integradas en expresiones &#40;Generador de informes y SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c0038-149">For more information, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
### <a name="parameter-properties-and-null"></a><span data-ttu-id="c0038-150">Propiedades de parámetros y NULL</span><span class="sxs-lookup"><span data-stu-id="c0038-150">Parameter Properties and Null</span></span>  
 <span data-ttu-id="c0038-151">Los parámetros de varios valores no pueden ser NULL.</span><span class="sxs-lookup"><span data-stu-id="c0038-151">A multivalue parameter cannot be Null.</span></span> <span data-ttu-id="c0038-152">Para más información, vea [Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c0038-152">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
### <a name="main-report-with-subreport-could-not-be-processed"></a><span data-ttu-id="c0038-153">No se puede procesar el informe principal con subinforme</span><span class="sxs-lookup"><span data-stu-id="c0038-153">Main Report with Subreport Could Not Be Processed</span></span>  
 <span data-ttu-id="c0038-154">La misma versión del procesador de informes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] debe procesar un informe con subinformes.</span><span class="sxs-lookup"><span data-stu-id="c0038-154">A report with subreports must be processed by the same version of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report processor.</span></span> <span data-ttu-id="c0038-155">Al actualizar los informes a la versión actual del esquema de definición de informe, el informe principal y los subinformes pueden actualizarse o no al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c0038-155">When upgrading reports to the current version of the report definition schema, the main report and the subreports may or may not be updated at the same time.</span></span> <span data-ttu-id="c0038-156">Si la versión no es compatible entre un informe y sus subinformes, se muestra el mensaje siguiente: "No se pudo procesar el subinforme".</span><span class="sxs-lookup"><span data-stu-id="c0038-156">If the version is not compatible between a report and its subreports, the following message is displayed: "Subreport could not be processed."</span></span>  
  
 <span data-ttu-id="c0038-157">Debe cambiar el informe principal o los subinformes para que todos los informes se puedan procesar con la misma versión del procesador de informes.</span><span class="sxs-lookup"><span data-stu-id="c0038-157">You must change either the main report or the subreports so that all the reports can be processed by the same version of the report processor.</span></span> <span data-ttu-id="c0038-158">Para obtener información sobre los motivos por los que no se puede actualizar un informe, vea [Actualizar informes](../install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="c0038-158">For information about why a report fails to upgrade, see [Upgrade Reports](../install-windows/upgrade-reports.md).</span></span>  
  
### <a name="verify-function-calls-are-visual-basic-and-not-sql"></a><span data-ttu-id="c0038-159">Compruebe que las llamadas a funciones son de Visual Basic y no de SQL</span><span class="sxs-lookup"><span data-stu-id="c0038-159">Verify Function Calls are Visual Basic and Not SQL</span></span>  
 <span data-ttu-id="c0038-160">Puede utilizar funciones SQL en el texto de consulta en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="c0038-160">You can use SQL functions in query text on a relational database.</span></span> <span data-ttu-id="c0038-161">No puede utilizar las funciones de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] en texto de consulta.</span><span class="sxs-lookup"><span data-stu-id="c0038-161">You cannot use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions in query text.</span></span>  
  
 <span data-ttu-id="c0038-162">En [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], las expresiones pueden utilizar las funciones de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] , las funciones de System.Math o System.String, las funciones completas de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , o las funciones personalizadas que se proporcionen en un código o ensamblado personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0038-162">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], expressions can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions, System.Math or System.String functions, fully qualified [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] functions, or custom functions that you provide in custom code or a custom assembly.</span></span> <span data-ttu-id="c0038-163">No puede utilizar funciones SQL en una expresión.</span><span class="sxs-lookup"><span data-stu-id="c0038-163">You cannot use SQL functions in an expression.</span></span>  
  
 <span data-ttu-id="c0038-164">Compruebe que las llamadas a funciones realizadas en la consulta y en las expresiones son válidas.</span><span class="sxs-lookup"><span data-stu-id="c0038-164">Verify that the function calls made in the query and in the expressions are valid.</span></span>  
  
### <a name="cannot-compare-data-types-for-a-filter"></a><span data-ttu-id="c0038-165">No se pueden comparar los tipos de datos para un filtro</span><span class="sxs-lookup"><span data-stu-id="c0038-165">Cannot Compare Data Types for a Filter</span></span>  
 <span data-ttu-id="c0038-166">En una ecuación de filtro, la expresión de filtro que define lo que se ha de filtrar y el valor de filtro deben ser del mismo tipo de datos para poder compararse.</span><span class="sxs-lookup"><span data-stu-id="c0038-166">In a filter equation, the filter expression that defines what to filter on and the filter value must be the same data type in order to be compared.</span></span> <span data-ttu-id="c0038-167">Si ve alguno de los errores siguientes, modifique la expresión de campo o el valor de filtro para que los tipos de datos coincidan:</span><span class="sxs-lookup"><span data-stu-id="c0038-167">If you see one of the following errors, modify the field expression or the filter value so that the data types match:</span></span>  
  
-   <span data-ttu-id="c0038-168">El procesamiento de *\<report item type>* para *\<report item name>* no se puede realizar.</span><span class="sxs-lookup"><span data-stu-id="c0038-168">The processing of *\<report item type>* for the *\<report item name>* cannot be performed.</span></span> <span data-ttu-id="c0038-169">No se pueden comparar datos de tipos *\<type>* y *\<type>* .</span><span class="sxs-lookup"><span data-stu-id="c0038-169">Cannot compare data of types *\<type>* and *\<type>*.</span></span> <span data-ttu-id="c0038-170">Compruebe el tipo de datos devuelto por *\<report item name>* .</span><span class="sxs-lookup"><span data-stu-id="c0038-170">Please check the data type returned by the *\<report item name>*.</span></span>  
  
-   <span data-ttu-id="c0038-171">No se pudo evaluar el *\<property name>* .</span><span class="sxs-lookup"><span data-stu-id="c0038-171">Failed to evaluate the *\<property name>*.</span></span>  
  
-   <span data-ttu-id="c0038-172">No se pudo evaluar el *\<property name>* .</span><span class="sxs-lookup"><span data-stu-id="c0038-172">Failed to evaluate the *\<property name>*.</span></span> <span data-ttu-id="c0038-173">Hace referencia a un campo de conjunto de información que tiene un error: *\<error string>* .</span><span class="sxs-lookup"><span data-stu-id="c0038-173">It references a dataset field which has an error: *\<error string>*.</span></span>  
  
 <span data-ttu-id="c0038-174">Para obtener más información, vea [Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c0038-174">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
### <a name="invalid-or-conflicting-scope-specification-in-an-aggregate-function-call"></a><span data-ttu-id="c0038-175">Especificación no válida o de ámbito en conflicto en la llamada a una función de agregado</span><span class="sxs-lookup"><span data-stu-id="c0038-175">Invalid or Conflicting Scope Specification in an Aggregate Function Call</span></span>  
 <span data-ttu-id="c0038-176">Al incluir llamadas a funciones de agregado en una expresión de una celda Tablix, el procesador de informes evalúa la expresión en el ámbito de los grupos más internos a los que pertenece la celda.</span><span class="sxs-lookup"><span data-stu-id="c0038-176">When you include aggregate function calls to an expression in a Tablix cell, the report processor evaluates the expression in the scope of the innermost groups to which the cell belongs.</span></span>  
  
 <span data-ttu-id="c0038-177">También se puede pasar el nombre de un ámbito concreto a una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="c0038-177">You can also pass the name of a specific scope to an aggregate function.</span></span> <span data-ttu-id="c0038-178">El ámbito puede hacer referencia al nombre de un conjunto de datos, una región de datos o el nombre un ámbito superior en la jerarquía de datos.</span><span class="sxs-lookup"><span data-stu-id="c0038-178">Scope can refer to the name of a dataset, a data region, or the name of a scope higher on the data hierarchy.</span></span> <span data-ttu-id="c0038-179">Esto se aplica a los mensajes siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0038-179">This applies to the following messages:</span></span>  
  
-   <span data-ttu-id="c0038-180">*\<report item type>*' *\<report item name>* ' Tiene un ámbito no válido ' ' *\<scope name>* .</span><span class="sxs-lookup"><span data-stu-id="c0038-180">The *\<report item type>* '*\<report item name>*' has an invalid scope "*\<scope name>*".</span></span> <span data-ttu-id="c0038-181">El ámbito debe ser el actual o estar dentro del actual.</span><span class="sxs-lookup"><span data-stu-id="c0038-181">The scope must be the current scope, or contained within the current scope.</span></span>  
  
-   <span data-ttu-id="c0038-182">La *\<property name>* expresión para *\<report item type>* ' *\<report item name>* ' tiene un parámetro de ámbito que no es válido para una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="c0038-182">The *\<property name>* expression for the *\<report item type>* '*\<report item name>*' has a scope parameter that is not valid for an aggregate function.</span></span> <span data-ttu-id="c0038-183">El parámetro de ámbito debe establecerse en una constante de cadena que sea igual al nombre de un grupo contenedor, al nombre de una región de datos contenedora o al nombre de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="c0038-183">The scope parameter must be set to a string constant that is equal to either the name of a containing group, the name of a containing data region, or the name of a dataset.</span></span>  
  
 <span data-ttu-id="c0038-184">Para las funciones de agregado que calculan totales acumulados (`Previous`, `RunningValue` o `RowNumber`), se puede especificar un parámetro de ámbito que sea un nombre de grupo de filas o de grupo de columnas, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="c0038-184">For aggregate functions that calculate running totals (`Previous`, `RunningValue`, or `RowNumber`), you can specify a scope parameter that is either a row group name or a column group name, but not both.</span></span> <span data-ttu-id="c0038-185">Esto se aplica al mensaje de error siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0038-185">This applies to the following error message:</span></span>  
  
-   <span data-ttu-id="c0038-186">`Previous``RunningValue`o `RowNumber` las funciones de agregado utilizadas en las celdas de datos de *\<report item type>* ' *\<report item name>* ' hacen referencia a los ámbitos de agrupación de las columnas y filas de *\<report item type>* .</span><span class="sxs-lookup"><span data-stu-id="c0038-186">`Previous`, `RunningValue` or `RowNumber` aggregate functions used in the data cells of the *\<report item type>* '*\<report item name>*' refer to grouping scopes in both the columns and rows of the *\<report item type>*.</span></span> <span data-ttu-id="c0038-187">Los parámetros de ámbito de todas las `Previous` `RunningValue` funciones de agregado de `RowNumber` *\<report item type>* pueden hacer referencia a agrupaciones de filas o agrupaciones de columnas de datos, pero no a ambas.</span><span class="sxs-lookup"><span data-stu-id="c0038-187">The scope parameters of all `Previous`, `RunningValue` and `RowNumber` aggregate functions within a *\<report item type>* can refer to row groupings or data column groupings, but not both.</span></span>  
  
 <span data-ttu-id="c0038-188">Para más información, vea [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](../report-design/expression-scope-for-totals-aggregates-and-built-in-collections.md) y [Colecciones integradas en expresiones &#40;Generador de informes y SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c0038-188">For more information, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](../report-design/expression-scope-for-totals-aggregates-and-built-in-collections.md) and [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
### <a name="default-dataset-scope-for-a-top-level-text-box"></a><span data-ttu-id="c0038-189">Ámbito del conjunto de datos predeterminado para un cuadro de texto de nivel superior</span><span class="sxs-lookup"><span data-stu-id="c0038-189">Default Dataset Scope for a Top Level Text Box</span></span>  
 <span data-ttu-id="c0038-190">No utilice un ámbito predeterminado para un cuadro de texto agregado a la superficie de diseño del informe cuando éste tenga más de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="c0038-190">Do not use a default scope for a text box added to the report design surface when the report has more than one dataset.</span></span> <span data-ttu-id="c0038-191">Utilice una expresión que incluya el nombre del conjunto de datos como ámbito, y una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="c0038-191">Use an expression that includes the name of the dataset as the scope, and an aggregate function.</span></span> <span data-ttu-id="c0038-192">Por ejemplo, `=First(Fields!FieldName.Value, "DataSet2")`.</span><span class="sxs-lookup"><span data-stu-id="c0038-192">For example, `=First(Fields!FieldName.Value, "DataSet2")`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0038-193">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0038-193">See Also</span></span>  
 <span data-ttu-id="c0038-194">[Expresiones &#40;Generador de informes y SSRS&#41;](../report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c0038-194">[Expressions &#40;Report Builder and SSRS&#41;](../report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c0038-195">[Referencia a las funciones de agregado &#40;Generador de informes y SSRS&#41;](../report-design/report-builder-functions-aggregate-functions-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c0038-195">[Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](../report-design/report-builder-functions-aggregate-functions-reference.md) </span></span>  
 <span data-ttu-id="c0038-196">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c0038-196">[Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c0038-197">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](../report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c0038-197">[Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="c0038-198">[Filtros de uso frecuente &#40;Generador de informes y SSRS&#41;](../report-design/commonly-used-filters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c0038-198">[Commonly Used Filters &#40;Report Builder and SSRS&#41;](../report-design/commonly-used-filters-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c0038-199">[Colección Campos del conjunto de datos &#40;Generador de informes y SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c0038-199">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c0038-200">[Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c0038-200">[Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span></span>  
 [<span data-ttu-id="c0038-201">Usar referencias a la colección de parámetros &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c0038-201">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](../report-design/built-in-collections-parameters-collection-references-report-builder.md)  
  
  