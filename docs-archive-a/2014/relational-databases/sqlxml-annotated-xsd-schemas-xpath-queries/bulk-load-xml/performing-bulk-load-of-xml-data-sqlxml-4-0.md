---
title: Realizar la carga masiva de datos XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML]
- bulk load [SQLXML]
- data insertions [SQLXML]
- SQLXML, bulk loading
- XSD schemas [SQLXML], XML Bulk Load
- XDR schemas [SQLXML], XML Bulk Load
- inserting data
ms.assetid: 3708b493-322e-4f3c-9b27-441d0c0ee346
author: rothja
ms.author: jroth
ms.openlocfilehash: ec540ff082b02fa43b9abd9f294752073eb68d5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744029"
---
# <a name="performing-bulk-load-of-xml-data-sqlxml-40"></a><span data-ttu-id="5ea0f-102">Realizar la carga masiva de datos XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="5ea0f-102">Performing Bulk Load of XML Data (SQLXML 4.0)</span></span>
  <span data-ttu-id="5ea0f-103">Carga masiva XML es un objeto COM independiente que permite cargar datos XML semiestructurados en tablas de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ea0f-103">XML Bulk Load is a standalone COM object that allows you to load semistructured XML data into Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ea0f-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5ea0f-104">In This Section</span></span>  
 [<span data-ttu-id="5ea0f-105">Introducción a la carga masiva XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5ea0f-105">Introduction to XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](introduction-to-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="5ea0f-106">Proporciona información general sobre la carga masiva de datos XML con la utilidad Carga masiva XML.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-106">Provides general information about bulk loading XML data with the XML Bulk Load utility.</span></span> <span data-ttu-id="5ea0f-107">Entre los temas se incluye la transmisión de datos XML por secuencias y las diferentes entre las operaciones de carga masiva con y sin transacciones.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-107">Topics include XML data streaming and transacted vs. nontransacted bulk load operations.</span></span>  
  
 [<span data-ttu-id="5ea0f-108">Proceso de generación de registros &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5ea0f-108">Record Generation Process &#40;SQLXML 4.0&#41;</span></span>](record-generation-process-sqlxml-4-0.md)  
 <span data-ttu-id="5ea0f-109">Describe el proceso y las reglas mediante los que se generan los registros para la carga masiva XML.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-109">Describes the process and rules by which records are generated for XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="5ea0f-110">Interpretación de anotaciones &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5ea0f-110">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
 <span data-ttu-id="5ea0f-111">Describe cómo Carga masiva XML interpreta las anotaciones en esquemas XSD y XDR.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-111">Describes how XML Bulk Load interprets annotations in XSD and XDR schemas.</span></span>  
  
 [<span data-ttu-id="5ea0f-112">SQL Server modelo de objetos de carga masiva XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5ea0f-112">SQL Server XML Bulk Load Object Model &#40;SQLXML 4.0&#41;</span></span>](sql-server-xml-bulk-load-object-model-sqlxml-4-0.md)  
 <span data-ttu-id="5ea0f-113">Describe el objeto SQLXMLBulkLoad y sus métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-113">Describes the SQLXMLBulkLoad object and its methods and properties.</span></span>  
  
 [<span data-ttu-id="5ea0f-114">Ejemplos de carga masiva XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5ea0f-114">XML Bulk Load Examples &#40;SQLXML 4.0&#41;</span></span>](xml-bulk-load-examples-sqlxml-4-0.md)  
 <span data-ttu-id="5ea0f-115">Proporciona código de ejemplo que utiliza Carga masiva XML.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-115">Provides example code that uses XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="5ea0f-116">Tipos de datos y comportamiento de la carga masiva XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5ea0f-116">Data Types and XML Bulk Load Behavior &#40;SQLXML 4.0&#41;</span></span>](data-types-and-xml-bulk-load-behavior-sqlxml-4-0.md)  
 <span data-ttu-id="5ea0f-117">Describe el comportamiento de Carga masiva XML con diferentes tipos en XSD y XDR.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-117">Describes XML Bulk Load Behavior with different types in XSD and XDR.</span></span>  
  
 [<span data-ttu-id="5ea0f-118">Instrucciones y limitaciones de la carga masiva XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5ea0f-118">Guidelines and Limitations of XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="5ea0f-119">Enumera algunos aspectos que se deben tener en cuenta al trabajar con Carga masiva XML.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-119">Lists some issues to be aware of when working with XML Bulk Load.</span></span>  
  
  
