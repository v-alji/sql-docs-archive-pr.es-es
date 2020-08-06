---
title: Convertir esquemas XDR anotados en esquemas XSD equivalentes (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XDR schemas, converting schemas
- annotated XSD schemas, converting schemas
- XDR to XSD Converter tool [SQLXML]
- XDR schemas [SQLXML], converting
- converting annotated schemas
- mapping schema [SQLXML], conversions
- XSD schemas [SQLXML], converting schemas
ms.assetid: 151c94a8-66d3-4c46-a5ff-a22df456940a
author: rothja
ms.author: jroth
ms.openlocfilehash: c36eb17aacb61a47fad0f389de9a3c216202827d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674722"
---
# <a name="converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-40"></a><span data-ttu-id="56d75-102">Convertir esquemas XDR anotados en esquemas XSD equivalentes (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="56d75-102">Converting Annotated XDR Schemas to Equivalent XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="56d75-103">El lenguaje de definición de esquemas XML (XSD) es el sucesor del lenguaje de definición de esquemas reducidos de datos XML (XDR).</span><span class="sxs-lookup"><span data-stu-id="56d75-103">The XML Schema Definition (XSD) language is the successor to the XML-Data Reduced (XDR) schema definition language.</span></span> <span data-ttu-id="56d75-104">Con la introducción de la compatibilidad con XSD en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, se asume que los nuevos esquemas anotados se crean utilizando XSD.</span><span class="sxs-lookup"><span data-stu-id="56d75-104">With the introduction of XSD support in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, it is assumed that new annotated schemas are created using XSD.</span></span> <span data-ttu-id="56d75-105">SQLXML 4.0 incluye una herramienta de conversión de XDR a XSD diseñada para ayudarle a convertir sus esquemas XDR anotados en esquemas XSD equivalentes.</span><span class="sxs-lookup"><span data-stu-id="56d75-105">SQLXML 4.0 includes an XDR to XSD converter tool that is designed to help you convert your existing annotated XDR schemas to equivalent XSD schemas.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="56d75-106">Utilice esta herramienta únicamente cuando desee convertir los esquemas XDR anotados en XSD para utilizarlos con SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="56d75-106">Use this tool only when you want to convert annotated XDR schemas to XSD for use with SQLXML 4.0.</span></span> <span data-ttu-id="56d75-107">No se trata de una herramienta de conversión de XDR a XSD de uso general.</span><span class="sxs-lookup"><span data-stu-id="56d75-107">This is not a general purpose XDR to XSD converter tool.</span></span> <span data-ttu-id="56d75-108">Es posible que los esquemas XSD convertidos no se comporten de mismo modo que los esquemas XDR originales cuando se utilicen en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="56d75-108">The converted XSD schemas may not behave the same as the original XDR schemas when used in other environments.</span></span>  
  
 <span data-ttu-id="56d75-109">Si el archivo XDR de entrada especifica la codificación dentro de la declaración XML, ésta se convierte en la codificación del archivo XSD de salida generado.</span><span class="sxs-lookup"><span data-stu-id="56d75-109">If the input XDR file specifies the encoding within the XML declaration, this becomes the encoding of the XSD output file that is generated.</span></span>  
  
 <span data-ttu-id="56d75-110">La herramienta de conversión (Cvtschema.exe) se instala en la carpeta Archivos de programa\SQLXML 4.0\bin y se ejecuta en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="56d75-110">The converter tool (Cvtschema.exe) is installed in the Program Files\SQLXML 4.0\bin folder and is executed at the command prompt.</span></span>  
  
 <span data-ttu-id="56d75-111">Ésta es la sintaxis general:</span><span class="sxs-lookup"><span data-stu-id="56d75-111">This is the general syntax:</span></span>  
  
```  
cvtschema XDRFileName, [-y], [-w] [-?]  
```  
  
 <span data-ttu-id="56d75-112">Donde:</span><span class="sxs-lookup"><span data-stu-id="56d75-112">Where:</span></span>  
  
 <span data-ttu-id="56d75-113">XDRFileName</span><span class="sxs-lookup"><span data-stu-id="56d75-113">XDRFileName</span></span>  
 <span data-ttu-id="56d75-114">Es el nombre del archivo XDR que se convertirá en XSD.</span><span class="sxs-lookup"><span data-stu-id="56d75-114">Is the name of the XDR file that is to be converted to XSD.</span></span> <span data-ttu-id="56d75-115">La herramienta lee el archivo XDR de entrada y crea un archivo XSD de salida en el directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="56d75-115">The tool reads the input XDR file and creates an XSD output file in the current working directory.</span></span> <span data-ttu-id="56d75-116">Si el archivo de entrada tiene la extensión .xdr o .xml, el archivo XSD de salida se crea con el mismo nombre pero con la extensión .xsd.</span><span class="sxs-lookup"><span data-stu-id="56d75-116">If the input file has an .xdr or .xml extension, the output XSD file is created with the same name but with an .xsd extension.</span></span> <span data-ttu-id="56d75-117">Si la extensión del archivo de entrada es distinta de .xml o .xdr (o si no tiene extensión), el archivo de salida se crea con el mismo nombre y se anexa la extensión .xsd al nombre del archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="56d75-117">If the input file extension is other than .xml or .xdr (or if the extension is missing), the output file is created with the same name and the .xsd extension is appended to the input file name.</span></span> <span data-ttu-id="56d75-118">Por ejemplo, si el nombre del archivo XDR de entrada es SampleFile.abc, el XSD resultante se guardará como SampleFile.abc.xsd.</span><span class="sxs-lookup"><span data-stu-id="56d75-118">For example, if the input XDR file name is SampleFile.abc, the resulting XSD is saved as SampleFile.abc.xsd.</span></span>  
  
 <span data-ttu-id="56d75-119">-y</span><span class="sxs-lookup"><span data-stu-id="56d75-119">-y</span></span>  
 <span data-ttu-id="56d75-120">(Opcional) Sobrescribe el archivo XSD existente con el archivo XSD generado por la herramienta de conversión.</span><span class="sxs-lookup"><span data-stu-id="56d75-120">(Optional) Overwrites the existing XSD file with the XSD file that is generated by the converter tool.</span></span> <span data-ttu-id="56d75-121">Si no se especifica la marca, la herramienta le solicita que especifique si desea sobrescribir el archivo XSD existente y le ofrece la posibilidad de cambiar el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="56d75-121">If the flag is not specified, the tool prompts you to specify whether you want to overwrite the existing XSD file and gives you the option to change the output file name.</span></span>  
  
 <span data-ttu-id="56d75-122">-w</span><span class="sxs-lookup"><span data-stu-id="56d75-122">-w</span></span>  
 <span data-ttu-id="56d75-123">(Opcional) Devuelve advertencias de errores recuperables que se generan durante el proceso de conversión de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="56d75-123">(Optional) Returns nonfatal warnings that are generated in the conversion process by the tool.</span></span> <span data-ttu-id="56d75-124">De forma predeterminada, la herramienta solo muestra los mensajes de errores irrecuperables.</span><span class="sxs-lookup"><span data-stu-id="56d75-124">By default, the tool displays messages only for fatal errors.</span></span>  
  
 <span data-ttu-id="56d75-125">-?</span><span class="sxs-lookup"><span data-stu-id="56d75-125">-?</span></span>  
 <span data-ttu-id="56d75-126">Devuelve una lista de las opciones que puede especificar con `cvtschema`, junto con una explicación.</span><span class="sxs-lookup"><span data-stu-id="56d75-126">Returns a list of options that you can specify with `cvtschema`, along with an explanation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56d75-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56d75-127">See Also</span></span>  
 <span data-ttu-id="56d75-128">[Asignar tipos de datos XSD a tipos de datos de XPath &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="56d75-128">[Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="56d75-129">Anotaciones XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="56d75-129">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml-annotated-xsd-schemas-using/xsd-annotations-sqlxml-4-0.md)  
  
  
