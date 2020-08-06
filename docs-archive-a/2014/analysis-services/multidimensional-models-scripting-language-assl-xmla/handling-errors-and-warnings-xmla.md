---
title: Control de errores y advertencias (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- inline errors [XMLA]
- SOAP faults [XML for Analysis]
- XML for Analysis, errors
- faults [XML for Analysis]
- messages [XML for Analysis]
- XMLA, errors
- warnings [XML for Analysis]
- inline warnings [XMLA]
ms.assetid: ab895282-098d-468e-9460-032598961f45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07b88d800237e5b4b06af0c1ff11cbd0af846600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671769"
---
# <a name="handling-errors-and-warnings-xmla"></a><span data-ttu-id="84ce1-102">Controlar errores y advertencias (XMLA)</span><span class="sxs-lookup"><span data-stu-id="84ce1-102">Handling Errors and Warnings (XMLA)</span></span>
  <span data-ttu-id="84ce1-103">El control de errores es necesario cuando una llamada al método [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) o [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) XML for Analysis (XMLA) no se ejecuta, se ejecuta correctamente, pero genera errores o advertencias, o se ejecuta correctamente, pero devuelve resultados que contienen errores.</span><span class="sxs-lookup"><span data-stu-id="84ce1-103">Error handling is required when an XML for Analysis (XMLA) [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) or [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method call does not run, runs successfully but generates errors or warnings, or runs successfully but returns results that contain errors.</span></span>  
  
|<span data-ttu-id="84ce1-104">Error</span><span class="sxs-lookup"><span data-stu-id="84ce1-104">Error</span></span>|<span data-ttu-id="84ce1-105">Notificación</span><span class="sxs-lookup"><span data-stu-id="84ce1-105">Reporting</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="84ce1-106">La llamada al método XMLA no se ejecuta</span><span class="sxs-lookup"><span data-stu-id="84ce1-106">The XMLA method call does not run</span></span>|[!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="84ce1-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] devuelve un mensaje de error de SOAP que contiene los detalles del error.</span><span class="sxs-lookup"><span data-stu-id="84ce1-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns a SOAP fault message that contains the details of the failure.</span></span><br /><br /> <span data-ttu-id="84ce1-108">Para obtener más información, vea la sección [control de errores de SOAP](#handling_soap_faults).</span><span class="sxs-lookup"><span data-stu-id="84ce1-108">For more information, see the section, [Handling SOAP Faults](#handling_soap_faults).</span></span>|  
|<span data-ttu-id="84ce1-109">Errores o advertencias en una llamada a método correcta</span><span class="sxs-lookup"><span data-stu-id="84ce1-109">Errors or warnings on a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="84ce1-110">incluye un elemento de [error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) o [ADVERTENCIA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) para cada error o advertencia, respectivamente, en la propiedad [messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) del elemento [raíz](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) que contiene los resultados de la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="84ce1-110">includes an [error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) or [warning](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) element for each error or warning, respectively, in the [Messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) property of the [root](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) element that contains the results of the method call.</span></span><br /><br /> <span data-ttu-id="84ce1-111">Para obtener más información, vea la sección [control de errores y advertencias](#handling_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="84ce1-111">For more information, see the section, [Handling Errors and Warnings](#handling_errors_and_warnings).</span></span>|  
|<span data-ttu-id="84ce1-112">Errores en el resultado de una llamada a método correcta</span><span class="sxs-lookup"><span data-stu-id="84ce1-112">Errors in the result for a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="84ce1-113">incluye un `error` elemento o insertado `warning` para el error o advertencia, respectivamente, dentro del elemento de [celda](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) o [fila](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) adecuado de los resultados de la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="84ce1-113">includes an inline `error` or `warning` element for the error or warning, respectively, within the appropriate [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) or [row](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) element of the results of the method call.</span></span><br /><br /> <span data-ttu-id="84ce1-114">Para obtener más información, vea la sección [control de errores y advertencias en línea](#handling_inline_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="84ce1-114">For more information, see the section, [Handling Inline Errors and Warnings](#handling_inline_errors_and_warnings).</span></span>|  
  
##  <a name="handling-soap-faults"></a><a name="handling_soap_faults"></a><span data-ttu-id="84ce1-115">Control de errores de SOAP</span><span class="sxs-lookup"><span data-stu-id="84ce1-115">Handling SOAP Faults</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="84ce1-116">devuelve un error de SOAP cuando se producen las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="84ce1-116">returns a SOAP fault when the following situations occur:</span></span>  
  
-   <span data-ttu-id="84ce1-117">El mensaje SOAP que contiene el método XMLA no estaba bien formado o la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no lo pudo validar.</span><span class="sxs-lookup"><span data-stu-id="84ce1-117">The SOAP message that contains the XMLA method was not well-formed or could not be validated by the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="84ce1-118">Se ha producido un error de comunicaciones o de otro tipo que afecta al mensaje SOAP que contiene el método XMLA.</span><span class="sxs-lookup"><span data-stu-id="84ce1-118">A communications or other error occurred involving the SOAP message that contains the XMLA method.</span></span>  
  
-   <span data-ttu-id="84ce1-119">El método XMLA no se ejecutó en la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84ce1-119">The XMLA method did not run on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="84ce1-120">Los códigos de error de SOAP para XMLstartA empiezan por "XMLForAnalysis", seguido de un punto y del código de resultado HRESULT hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="84ce1-120">The SOAP fault codes for XMLstartA start with "XMLForAnalysis", followed by a period and the hexadecimal HRESULT result code.</span></span> <span data-ttu-id="84ce1-121">Por ejemplo, un código de error de "`0x80000005`" tiene el formato "`XMLForAnalysis.0x80000005`".</span><span class="sxs-lookup"><span data-stu-id="84ce1-121">For example, an error code of "`0x80000005`" is formatted as "`XMLForAnalysis.0x80000005`".</span></span> <span data-ttu-id="84ce1-122">Para obtener más información sobre el formato de error de SOAP, consulte la información sobre errores de SOAP en Simple Object Access Protocol (SOAP) 1.1 de W3C.</span><span class="sxs-lookup"><span data-stu-id="84ce1-122">For more information about the SOAP fault format, see Soap Fault in the W3C Simple Object Access Protocol (SOAP) 1.1.</span></span>  
  
### <a name="fault-code-information"></a><span data-ttu-id="84ce1-123">Información del código de error</span><span class="sxs-lookup"><span data-stu-id="84ce1-123">Fault Code Information</span></span>  
 <span data-ttu-id="84ce1-124">En la tabla siguiente se muestra la información de código de error de XMLA incluida en la sección de detalles de la respuesta SOAP.</span><span class="sxs-lookup"><span data-stu-id="84ce1-124">The following table shows the XMLA fault code information that is contained in the detail section of the SOAP response.</span></span> <span data-ttu-id="84ce1-125">Las columnas son los atributos de un error en la sección de detalles de un error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="84ce1-125">The columns are the attributes of an error in the detail section of a SOAP fault.</span></span>  
  
|<span data-ttu-id="84ce1-126">Nombre de la columna</span><span class="sxs-lookup"><span data-stu-id="84ce1-126">Column name</span></span>|<span data-ttu-id="84ce1-127">Tipo</span><span class="sxs-lookup"><span data-stu-id="84ce1-127">Type</span></span>|<span data-ttu-id="84ce1-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="84ce1-128">Description</span></span>|<span data-ttu-id="84ce1-129">Null permitido<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="84ce1-129">Null allowed<sup>1</sup></span></span>|  
|-----------------|----------|-----------------|------------------------------|  
|`ErrorCode`|`UnsignedInt`|<span data-ttu-id="84ce1-130">Código de retorno que indica la ejecución correcta o el error del método.</span><span class="sxs-lookup"><span data-stu-id="84ce1-130">Return code that indicates the success or failure of the method.</span></span> <span data-ttu-id="84ce1-131">El valor hexadecimal debe convertirse en un valor `UnsignedInt`.</span><span class="sxs-lookup"><span data-stu-id="84ce1-131">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="84ce1-132">No</span><span class="sxs-lookup"><span data-stu-id="84ce1-132">No</span></span>|  
|`WarningCode`|`UnsignedInt`|<span data-ttu-id="84ce1-133">Código de retorno que indica una condición de advertencia.</span><span class="sxs-lookup"><span data-stu-id="84ce1-133">Return code that indicates a warning condition.</span></span> <span data-ttu-id="84ce1-134">El valor hexadecimal debe convertirse en un valor `UnsignedInt`.</span><span class="sxs-lookup"><span data-stu-id="84ce1-134">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="84ce1-135">Sí</span><span class="sxs-lookup"><span data-stu-id="84ce1-135">Yes</span></span>|  
|`Description`|`String`|<span data-ttu-id="84ce1-136">Texto y descripción del error o la advertencia devueltos por el componente que generó el error.</span><span class="sxs-lookup"><span data-stu-id="84ce1-136">Error or warning text and description returned by the component that generated the error.</span></span>|<span data-ttu-id="84ce1-137">Sí</span><span class="sxs-lookup"><span data-stu-id="84ce1-137">Yes</span></span>|  
|`Source`|`String`|<span data-ttu-id="84ce1-138">Nombre del componente que generó el error o la advertencia.</span><span class="sxs-lookup"><span data-stu-id="84ce1-138">Name of the component that generated the error or warning.</span></span>|<span data-ttu-id="84ce1-139">Sí</span><span class="sxs-lookup"><span data-stu-id="84ce1-139">Yes</span></span>|  
|`HelpFile`|`String`|<span data-ttu-id="84ce1-140">Ruta de acceso o dirección URL del tema o el archivo de Ayuda que describe el error o la advertencia.</span><span class="sxs-lookup"><span data-stu-id="84ce1-140">Path or URL to the Help file or topic that describes the error or warning.</span></span>|<span data-ttu-id="84ce1-141">Sí</span><span class="sxs-lookup"><span data-stu-id="84ce1-141">Yes</span></span>|  
  
 <span data-ttu-id="84ce1-142"><sup>1</sup> indica si los datos son obligatorios y deben devolverse, o si los datos son opcionales y se permite una cadena NULL si la columna no se aplica.</span><span class="sxs-lookup"><span data-stu-id="84ce1-142"><sup>1</sup> Indicates whether the data is required and must be returned, or whether the data is optional and a null string is allowed if the column does not apply.</span></span>  
  
 <span data-ttu-id="84ce1-143">A continuación se muestra un ejemplo de un error de SOAP que se produjo al no poderse realizar una llamada a método:</span><span class="sxs-lookup"><span data-stu-id="84ce1-143">The following is an example of a SOAP fault that occurred when a method call failed:</span></span>  
  
```  
<?xml version="1.0"?>  
   <SOAP-ENV:Envelope  
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
   SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
      <SOAP-ENV:Fault>  
         <faultcode>XMLAnalysisError.0x80000005</faultcode>  
         <faultstring>The XML for Analysis provider encountered an error.</faultstring>  
         <faultactor>XML for Analysis Provider</faultactor>  
         <detail>  
<Error  
ErrorCode="2147483653"  
Description="An unexpected error has occurred."  
Source="XML for Analysis Provider"  
HelpFile="" />  
         </detail>  
      </SOAP-ENV:Fault>  
</SOAP-ENV:Envelope>  
```  
  
##  <a name="handling-errors-and-warnings"></a><a name="handling_errors_and_warnings"></a><span data-ttu-id="84ce1-144">Control de errores y advertencias</span><span class="sxs-lookup"><span data-stu-id="84ce1-144">Handling Errors and Warnings</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="84ce1-145">devuelve la propiedad `Messages` en el elemento `root` de un comando si se producen las siguientes situaciones después de ejecutarse dicho comando:</span><span class="sxs-lookup"><span data-stu-id="84ce1-145">returns the `Messages` property in the `root` element for a command if the following situations occur after that command runs:</span></span>  
  
-   <span data-ttu-id="84ce1-146">El método se ejecutó correctamente, pero se produjo un error en la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] después de la llamada a método correcta.</span><span class="sxs-lookup"><span data-stu-id="84ce1-146">The method itself did not fail, but a failure occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the method call succeeded.</span></span>  
  
-   <span data-ttu-id="84ce1-147">La instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] devuelve una advertencia cuando el comando se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="84ce1-147">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance returns a warning when the command is successful.</span></span>  
  
 <span data-ttu-id="84ce1-148">La propiedad `Messages` sigue al resto de las propiedades contenidas en el elemento `root` y puede contener uno o más elementos `Message`.</span><span class="sxs-lookup"><span data-stu-id="84ce1-148">The `Messages` property follows all other properties that are contained by the `root` element, and can contain one or more `Message` elements.</span></span> <span data-ttu-id="84ce1-149">A su vez, cada elemento `Message` puede contener un elemento `error` o `warning` único que describa cualquier error o advertencia, respectivamente, que se hayan producido para el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="84ce1-149">In turn, each `Message` element can contain either a single `error` or `warning` element describing any errors or warnings, respectively, that occurred for the specified command.</span></span>  
  
 <span data-ttu-id="84ce1-150">Para obtener más información sobre los errores y las advertencias que se incluyen en la `Messages` propiedad, vea [elemento messages &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="84ce1-150">For more information about errors and warnings that are contained in the `Messages` property, see [Messages Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span></span>  
  
### <a name="handling-errors-during-serialization"></a><span data-ttu-id="84ce1-151">Controlar errores durante la serialización</span><span class="sxs-lookup"><span data-stu-id="84ce1-151">Handling Errors During Serialization</span></span>  
 <span data-ttu-id="84ce1-152">Si se produce un error después de que la [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instancia ya haya empezado a serializar la salida de un comando ejecutado correctamente, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] devuelve un elemento [Exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) en un espacio de nombres diferente en el punto del error.</span><span class="sxs-lookup"><span data-stu-id="84ce1-152">If an error occurs after the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance has already begun serializing the output of a successfully run command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an [Exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) element in a different namespace at the point of the error.</span></span> <span data-ttu-id="84ce1-153">A continuación, la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cierra todos los elementos abiertos para que el documento XML que se envía al cliente sea válido.</span><span class="sxs-lookup"><span data-stu-id="84ce1-153">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance then closes all open elements so that the XML document sent to the client is a valid document.</span></span> <span data-ttu-id="84ce1-154">La instancia también devuelve un elemento `Messages` que contiene la descripción del error.</span><span class="sxs-lookup"><span data-stu-id="84ce1-154">The instance also returns a `Messages` element that contains the description of the error.</span></span>  
  
##  <a name="handling-inline-errors-and-warnings"></a><a name="handling_inline_errors_and_warnings"></a><span data-ttu-id="84ce1-155">Control de errores y advertencias en línea</span><span class="sxs-lookup"><span data-stu-id="84ce1-155">Handling Inline Errors and Warnings</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="84ce1-156">devuelve un elemento `error` o `warning` insertado para un comando si el método XMLA en sí se ejecutó correctamente, pero se produjo un error específico de un elemento de datos en los resultados devueltos por el método en la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] después de haberse realizado correctamente la llamada al método XMLA.</span><span class="sxs-lookup"><span data-stu-id="84ce1-156">returns an inline `error` or `warning` for a command if the XMLA method itself did not fail, but an error specific to a data element in the results returned by the method occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the XMLA method call succeeded.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="84ce1-157">proporciona `error` elementos y insertados `warning` si se producen problemas específicos de una celda o de otros datos contenidos dentro de un `root` elemento mediante el tipo de datos [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) , como un error de seguridad o un error de formato para una celda.</span><span class="sxs-lookup"><span data-stu-id="84ce1-157">supplies inline `error` and `warning` elements if issues specific to a cell or to other data that are contained within a `root` element using the [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) data type occur, such as a security error or formatting error for a cell.</span></span> <span data-ttu-id="84ce1-158">En estos casos, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] devuelve un elemento `error` o `warning` en el elemento `Cell` o `row` que contiene el error o la advertencia, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="84ce1-158">In these cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an `error` or `warning` element in the `Cell` or `row` element that contains the error or warning, respectively.</span></span>  
  
 <span data-ttu-id="84ce1-159">En el ejemplo siguiente se muestra un conjunto de resultados que contiene un error en el conjunto de filas devuelto desde un `Execute` método mediante el comando [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="84ce1-159">The following example illustrates a result set that contains an error in the rowset returned from an `Execute` method using the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command.</span></span>  
  
```  
<return>  
   ...  
   <root>  
      ...  
      <CellData>  
      ...  
         <Cell CellOrdinal="10">  
            <Value>  
               <Error>  
                  <ErrorCode>2148497527</ErrorCode>   
                  <Description>Security Error.</Description>   
               </Error>  
            </Value>  
         </Cell>  
      </CellData>  
      ...  
   </root>  
   ...  
</return>  
```  
  
## <a name="see-also"></a><span data-ttu-id="84ce1-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84ce1-160">See Also</span></span>  
 [<span data-ttu-id="84ce1-161">Desarrollar con XMLA en Analysis Services</span><span class="sxs-lookup"><span data-stu-id="84ce1-161">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
