---
title: Generar un esquema XDR insertado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XDR schemas [SQL Server]
- inline XDR schema generation [SQL Server]
- XMLDATA option
- FOR XML clause, inline XDR schema generation
ms.assetid: 2a40d617-9724-4f7d-80a4-a85c702f14d0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0e2bb7b4b482b79ab5550540dd5b24ffdd8d6636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751973"
---
# <a name="generate-an-inline-xdr-schema"></a><span data-ttu-id="715ca-102">Generar un esquema XDR insertado</span><span class="sxs-lookup"><span data-stu-id="715ca-102">Generate an Inline XDR Schema</span></span>
  <span data-ttu-id="715ca-103">La directiva **XMLDATA** de FOR XML devuelve un esquema XDR insertado junto con el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="715ca-103">The **XMLDATA** directive in FOR XML returns an inline XDR schema together with the query result.</span></span> <span data-ttu-id="715ca-104">Sin embargo, el esquema XDR no admite todos los nuevos tipos de datos y otras mejoras incluidas en [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="715ca-104">However, the XDR schema does not support all the new data types and other enhancements introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="715ca-105">En su lugar, se puede solicitar un esquema XSD insertado mediante la [directiva XMLSCHEMA](generate-an-inline-xsd-schema.md).</span><span class="sxs-lookup"><span data-stu-id="715ca-105">Instead, you can request an inline XSD schema by using [the XMLSCHEMA directive](generate-an-inline-xsd-schema.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="715ca-106">La directiva XMLDATA para la opción FOR XML ha quedado desusada.</span><span class="sxs-lookup"><span data-stu-id="715ca-106">The XMLDATA directive to the FOR XML option is deprecated.</span></span> <span data-ttu-id="715ca-107">Utilice la XSD generación en los modos RAW y AUTO.</span><span class="sxs-lookup"><span data-stu-id="715ca-107">Use XSD generation in the case of RAW and AUTO modes.</span></span> <span data-ttu-id="715ca-108">No hay sustitución para la directiva XMLDATA en modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="715ca-108">There is no replacement for the XMLDATA directive in EXPLICIT mode.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="715ca-109">Asimismo, es necesario tener en cuenta lo siguiente acerca de la compatibilidad del esquema XDR insertado:</span><span class="sxs-lookup"><span data-stu-id="715ca-109">Also note the following about the inline XDR schema support:</span></span>  
  
-   <span data-ttu-id="715ca-110">Si el resultado de la consulta FOR XML incluye columnas de tipo **xml** y se solicita un esquema XDR insertado, se devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="715ca-110">If the FOR XML query result includes columns of **xml** type and you request an inline XDR schema, an error is returned.</span></span> <span data-ttu-id="715ca-111">El esquema XDR insertado no admite estos tipos.</span><span class="sxs-lookup"><span data-stu-id="715ca-111">Inline XDR does not support these types.</span></span>  
  
-   <span data-ttu-id="715ca-112">Los tipos **(n)varchar(max)** y **(n)varbinary(max)** se asignarán a **(n)varchar(n)** y **varbinary(n)** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="715ca-112">The **(n)varchar(max)** and **(n)varbinary(max)** types will be mapped to **(n)varchar(n)** and **varbinary(n)**, respectively.</span></span>  
  
-   <span data-ttu-id="715ca-113">Cuando el modo de compatibilidad se establece en 90 o más, los valores de **timestamp** se consideran datos **varbinary(8)** , se tratan como datos binarios y se devuelven en el resultado de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="715ca-113">When compatibility mode is set to 90 or higher, **timestamp** values are considered as **varbinary(8)** data, are treated like binary data, and are returned in the result as follows:</span></span>  
  
    -   <span data-ttu-id="715ca-114">Cuando se especifica **binary base64** , se utiliza la codificación base 64.</span><span class="sxs-lookup"><span data-stu-id="715ca-114">Base 64 encoding is used when **binary base64** is specified.</span></span>  
  
    -   <span data-ttu-id="715ca-115">Cuando no se especifica **binary base64** , se utiliza la codificación URL en modo AUTO.</span><span class="sxs-lookup"><span data-stu-id="715ca-115">URL encoding is used in AUTO mode when **binary base64** is not specified.</span></span>  
  
  
