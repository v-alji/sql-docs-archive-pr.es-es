---
title: Usar las clases administradas de SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXML Managed Classes, sample applications
- examples [SQLXML], managed classes
- Managed Classes [SQLXML], samples
ms.assetid: 3f021290-00ee-44e1-af4b-33d3ba8c6302
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 634a0e4110b13931201edd026ee95028cb94e859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746454"
---
# <a name="using-the-sqlxml-managed-classes"></a><span data-ttu-id="2151c-102">Utilizar clases administradas de SQLXML</span><span class="sxs-lookup"><span data-stu-id="2151c-102">Using the SQLXML Managed Classes</span></span>
  <span data-ttu-id="2151c-103">En esta sección se proporcionan aplicaciones de ejemplo que muestran cómo utilizar las clases administradas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML.</span><span class="sxs-lookup"><span data-stu-id="2151c-103">This section provides sample applications that demonstrate how to use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML Managed Classes.</span></span>  
  
 <span data-ttu-id="2151c-104">Para obtener información sobre el acceso y la modificación de datos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] el [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework y sobre el uso de DiffGrams para actualizar datos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tablas, vea [obtener acceso a la funcionalidad de SQLXML en el entorno de .net](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2151c-104">For information about accessing and modifying data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] within the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, and about using DiffGrams to update data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, see [Accessing SQLXML Functionality in the .NET Environment](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2151c-105">También puede escribir aplicaciones de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio para realizar una carga masiva de documentos XML mediante la carga masiva XML.</span><span class="sxs-lookup"><span data-stu-id="2151c-105">You can also write [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio applications to bulk load XML documents by using XML Bulk Load.</span></span> <span data-ttu-id="2151c-106">Para obtener más información, vea [realizar la carga masiva de datos XML &#40;SQLXML 4,0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2151c-106">For more information, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span> <span data-ttu-id="2151c-107">Debe agregar una referencia a la DLL de carga masiva XML (Xblkld4.dll) en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2151c-107">You must add a reference to the XML Bulk Load DLL (Xblkld4.dll) in your application.</span></span> <span data-ttu-id="2151c-108">Ésta es una DLL COM para la que Visual Studio .NET crea automáticamente la biblioteca de contenedores.</span><span class="sxs-lookup"><span data-stu-id="2151c-108">This is a COM DLL for which Visual Studio .NET automatically creates the wrapper library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2151c-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2151c-109">In This Section</span></span>  
 [<span data-ttu-id="2151c-110">Ejecutar consultas SQL &#40;clases administradas de SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="2151c-110">Executing SQL Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
  [<span data-ttu-id="2151c-111">Ejecutar consultas SQL mediante el método ExecuteXMLReader</span><span class="sxs-lookup"><span data-stu-id="2151c-111">Executing SQL Queries by Using the ExecuteXMLReader Method</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-sql-queries-by-using-the-executexmlreader-method.md)  
  [<span data-ttu-id="2151c-112">Procesar XML en el lado cliente &#40;clases administradas de SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="2151c-112">Processing XML on the Client Side &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/processing-xml-on-the-client-side-sqlxml-managed-classes.md)  
  [<span data-ttu-id="2151c-113">Ejecutar consultas XPath &#40;clases administradas de SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="2151c-113">Executing XPath Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-sqlxml-managed-classes.md)  
  [<span data-ttu-id="2151c-114">Ejecutar consultas XPath con espacios de nombres &#40;clases administradas de SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="2151c-114">Executing XPath Queries with Namespaces &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-with-namespaces-sqlxml-managed-classes.md)  
  [<span data-ttu-id="2151c-115">Ejecutar archivos de plantilla utilizando la propiedad CommandText</span><span class="sxs-lookup"><span data-stu-id="2151c-115">Executing Template Files by Using the CommandText Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandtext-property.md)  
  [<span data-ttu-id="2151c-116">Ejecutar archivos de plantilla utilizando la propiedad CommandStream</span><span class="sxs-lookup"><span data-stu-id="2151c-116">Executing Template Files by Using the CommandStream Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandstream-property.md)  
  [<span data-ttu-id="2151c-117">Aplicar una transformación XSL &#40;clases administradas de SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="2151c-117">Applying an XSL Transformation &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/applying-an-xsl-transformation-sqlxml-managed-classes.md)  
  
