---
title: Usar el proveedor SQLXMLOLEDB (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXMLOLEDB Provider, samples
- ClientSideXML property
ms.assetid: fbcefac5-29c9-478b-b0e0-d510b593f446
author: rothja
ms.author: jroth
ms.openlocfilehash: 74e3c53eecd657d610c2fe90e108e0290e9b05b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673598"
---
# <a name="using-the-sqlxmloledb-provider-sqlxml-40"></a><span data-ttu-id="647f3-102">Usar el proveedor SQLXMLOLEDB (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="647f3-102">Using the SQLXMLOLEDB Provider (SQLXML 4.0)</span></span>
  <span data-ttu-id="647f3-103">En los temas de esta sección se proporcionan aplicaciones de ejemplo ADO que muestran el uso de las propiedades específicas del proveedor SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="647f3-103">The topics in this section provide ADO sample applications that illustrate the use of SQLXMLOLEDB Provider-specific properties.</span></span>  
  
## <a name="application-requirements-for-sqlxmloledb-40-provider"></a><span data-ttu-id="647f3-104">Requisitos de aplicación del proveedor de SQLXMLOLEDB 4.0</span><span class="sxs-lookup"><span data-stu-id="647f3-104">Application Requirements for SQLXMLOLEDB 4.0 Provider</span></span>  
 <span data-ttu-id="647f3-105">Para crear ejemplos funcionales que utilicen SQLXMLOLEDB 4.0, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="647f3-105">To create working samples that use SQLXMLOLEDB 4.0, you must do the following:</span></span>  
  
1.  <span data-ttu-id="647f3-106">Cree una aplicación .exe en Microsoft Visual Basic y agregue una de las referencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="647f3-106">Create a Microsoft Visual Basic .exe application and add one of the following references:</span></span>  
  
    -   <span data-ttu-id="647f3-107">Biblioteca de Microsoft Objetos de datos ActiveX 2,6</span><span class="sxs-lookup"><span data-stu-id="647f3-107">Microsoft ActiveX Data Objects 2.6 Library</span></span>  
  
    -   <span data-ttu-id="647f3-108">Biblioteca de Microsoft Objetos de datos ActiveX 2,7</span><span class="sxs-lookup"><span data-stu-id="647f3-108">Microsoft ActiveX Data Objects 2.7 Library</span></span>  
  
    -   <span data-ttu-id="647f3-109">Biblioteca Microsoft ActiveX Data Objects 2.8</span><span class="sxs-lookup"><span data-stu-id="647f3-109">Microsoft ActiveX Data Objects 2.8 Library</span></span>  
  
2.  <span data-ttu-id="647f3-110">Implemente e instale SQLXML 4.0 y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="647f3-110">Deploy and install SQLXML 4.0 and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
     <span data-ttu-id="647f3-111">Para obtener más información, vea en [SQLXML 4,0 Programming Concepts](../../sqlxml/sqlxml-4-0-programming-concepts.md) and [Installing SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="647f3-111">For more information, see on [SQLXML 4.0 Programming Concepts](../../sqlxml/sqlxml-4-0-programming-concepts.md) and [Installing SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="647f3-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="647f3-112">In This Section</span></span>  
 [<span data-ttu-id="647f3-113">Ejecutar consultas SQL &#40;proveedor SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="647f3-113">Executing SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="647f3-114">Muestra el uso de las propiedades raíz Clientsidexml, y XML para ejecutar consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="647f3-114">Illustrates the use of the ClientSideXML and xml root properties to execute SQL queries.</span></span>  
  
 [<span data-ttu-id="647f3-115">Ejecutar plantillas que contienen consultas SQL &#40;proveedor SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="647f3-115">Executing Templates That Contain SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="647f3-116">Muestra el uso de la propiedad Clientsidexml,.</span><span class="sxs-lookup"><span data-stu-id="647f3-116">Illustrates the use of the ClientSideXML property.</span></span>  
  
 [<span data-ttu-id="647f3-117">Ejecutar consultas XPath &#40;proveedor SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="647f3-117">Executing XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="647f3-118">Muestra el uso de las propiedades Clientsidexml,, ruta de acceso base y esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="647f3-118">Illustrates the use of the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="647f3-119">Ejecutar consultas XPath con espacios de nombres &#40;proveedor SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="647f3-119">Executing XPath Queries with Namespaces &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-with-namespaces-sqlxmloledb-provider.md)  
 <span data-ttu-id="647f3-120">Muestra cómo realizar consultas contra esquemas certificados por espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="647f3-120">Illustrates how to query against namespace-qualified schemas.</span></span>  
  
 [<span data-ttu-id="647f3-121">Ejecutar plantillas que contienen consultas XPath &#40;proveedor SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="647f3-121">Executing Templates That Contain XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="647f3-122">Muestra cómo ejecutar plantillas con consultas SQL mediante las propiedades Clientsidexml,, ruta de acceso base y esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="647f3-122">Illustrates how to execute templates with SQL queries using the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="647f3-123">Aplicar una transformación XSL &#40;proveedor SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="647f3-123">Applying an XSL Transformation &#40;SQLXMLOLEDB Provider&#41;</span></span>](applying-an-xsl-transformation-sqlxmloledb-provider.md)  
 <span data-ttu-id="647f3-124">Muestra el uso de las propiedades Clientsidexml, y XSL para aplicar una transformación XSL.</span><span class="sxs-lookup"><span data-stu-id="647f3-124">Illustrates the use of the ClientSideXML and xsl properties in applying an XSL transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647f3-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="647f3-125">See Also</span></span>  
 [<span data-ttu-id="647f3-126">Requisitos del sistema para SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="647f3-126">System Requirements for SQL Server Native Client</span></span>](../../native-client/system-requirements-for-sql-server-native-client.md)  
  
  
