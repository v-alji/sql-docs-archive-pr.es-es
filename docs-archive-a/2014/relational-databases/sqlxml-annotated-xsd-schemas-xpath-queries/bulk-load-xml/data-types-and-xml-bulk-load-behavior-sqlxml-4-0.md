---
title: Tipos de datos y comportamiento de carga masiva XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- bulk load [SQLXML], data types
- data types [SQLXML], XML Bulk Load
- XML Bulk Load [SQLXML], data types
ms.assetid: d1ac1939-1f6c-4398-b7a7-a79ca608a4f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b03423f3bb88166d0d9ce5b0df450d4455e7ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674745"
---
# <a name="data-types-and-xml-bulk-load-behavior-sqlxml-40"></a><span data-ttu-id="6a428-102">Tipos de datos y comportamiento de la carga masiva XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="6a428-102">Data Types and XML Bulk Load Behavior (SQLXML 4.0)</span></span>
  <span data-ttu-id="6a428-103">Generalmente se omiten los tipos de datos que se especifican en el esquema de asignación (XSD o tipo XDR y `sql:datatype`), excepto en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6a428-103">The data types that are specified in the mapping schema (XSD or XDR type and `sql:datatype`) are generally ignored, except in the following cases:</span></span>  
  
 <span data-ttu-id="6a428-104">En XSD:</span><span class="sxs-lookup"><span data-stu-id="6a428-104">In XSD:</span></span>  
  
-   <span data-ttu-id="6a428-105">Si el tipo es `dateTime` o `time`, debe especificar `sql:datatype` porque la carga masiva XML realiza la conversión de datos antes de enviarlos a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a428-105">If the type is `dateTime` or `time`, you must specify the `sql:datatype` because XML Bulk Load performs data conversion before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="6a428-106">Cuando se realiza la carga masiva en una columna de `uniqueidentifier` tipo en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y el valor XSD es un GUID que incluye llaves ({y}), debe especificar **SQL: DataType = "uniqueidentifier"** para quitar las llaves antes de que se inserte el valor en la columna.</span><span class="sxs-lookup"><span data-stu-id="6a428-106">When you are bulk loading into a column of `uniqueidentifier` type in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and the XSD value is a GUID that includes braces ({ and }), you must specify **sql:datatype="uniqueidentifier"** to remove the braces before the value is inserted into the column.</span></span> <span data-ttu-id="6a428-107">Si no se especifica `sql:datatype`, el valor se envía con las llaves y se produce un error en la inserción.</span><span class="sxs-lookup"><span data-stu-id="6a428-107">If `sql:datatype` is not specified, the value is sent with the braces and the insert fails.</span></span>  
  
 <span data-ttu-id="6a428-108">Para obtener más información sobre `sql:datatype` , vea [conversiones de tipos de datos y la anotación sql: DataType &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="6a428-108">For more information about `sql:datatype`, see [Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="6a428-109">En XDR:</span><span class="sxs-lookup"><span data-stu-id="6a428-109">In XDR:</span></span>  
  
-   <span data-ttu-id="6a428-110">Si `dt:type` es `datetime`, `time`, `dateTime.tz` o `time.tz`, debe especificar los tipos de datos `dt:type` y `sql:datatype` porque la carga masiva XML realiza la conversión de datos antes de enviar los datos a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a428-110">If the `dt:type` is `datetime`, `time`, `dateTime.tz`, or `time.tz`, you must specify both the `dt:type` and `sql:datatype` data types because XML Bulk Load performs data conversion before it sends the data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="6a428-111">Si los datos XML son del tipo `uuid` , `sql:datatype` se debe especificar; **DT: type = "UUID"** también es necesario, a menos que los datos sean datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="6a428-111">If your XML data is of type `uuid`, `sql:datatype` must be specified; **dt:type="uuid"** is also required, unless the data is string data.</span></span> <span data-ttu-id="6a428-112">Si no especifica `dt:uuid`, la carga masiva XML acepta cadenas con llaves (y las quita si es necesario).</span><span class="sxs-lookup"><span data-stu-id="6a428-112">If you do not specify `dt:uuid`, XML Bulk Load accepts strings with braces (and removes them if needed).</span></span>  
  
-   <span data-ttu-id="6a428-113">Si los datos XML son `bin.base64` o `bin.hex`, debe especificar el tipo de datos XML con `dt:type`.</span><span class="sxs-lookup"><span data-stu-id="6a428-113">If the XML data is `bin.base64` or `bin.hex`, you must specify the XML data type with `dt:type`.</span></span> <span data-ttu-id="6a428-114">A continuación, la carga masiva XML carga los datos en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como una representación hexadecimal de los datos.</span><span class="sxs-lookup"><span data-stu-id="6a428-114">XML Bulk Load then loads the data into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a hexadecimal representation of the data.</span></span>  
  
  
