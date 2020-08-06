---
title: Arquitectura del formato XML del lado cliente y del lado servidor (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], XML formatting architecture
- SQLOLEDB provider
- client-side XML formatting
- data providers [SQLXML], XML formatting architecture
- SQLNCLI, XML
- server-side XML formatting
- SQL Server Native Client, XML
- SQLXMLOLEDB Provider, XML formatting architecture
ms.assetid: 52440d9e-89fd-4c15-a008-a1ea99f41387
author: rothja
ms.author: jroth
ms.openlocfilehash: ae1a9c60a7a7966f4eff2a08b4557487f5aec58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674710"
---
# <a name="architecture-of-client-side-and-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="514b0-102">Arquitectura de aplicación de formato XML en el cliente y en el servidor (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="514b0-102">Architecture of Client-side and Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="514b0-103">La ilustración siguiente muestra la arquitectura del formato XML en el lado servidor.</span><span class="sxs-lookup"><span data-stu-id="514b0-103">The following illustration shows the architecture of XML formatting on the server side.</span></span>  
  
 <span data-ttu-id="514b0-104">![Arquitectura de formato XML en el servidor.](../../../database-engine/dev-guide/media/serversidexml.gif "Arquitectura de formato XML en el servidor.")</span><span class="sxs-lookup"><span data-stu-id="514b0-104">![Architecture of XML formatting on the server side.](../../../database-engine/dev-guide/media/serversidexml.gif "Architecture of XML formatting on the server side.")</span></span>  
  
 <span data-ttu-id="514b0-105">En este ejemplo, el comando que se especifica en el cliente se envía al servidor.</span><span class="sxs-lookup"><span data-stu-id="514b0-105">In this example, the command that is specified on the client is sent to the server.</span></span> <span data-ttu-id="514b0-106">El servidor genera un documento XML y lo devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="514b0-106">The server produces an XML document and returns it to the client.</span></span> <span data-ttu-id="514b0-107">En este caso, el servidor tiene una instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="514b0-107">In this case, the server has an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="514b0-108">Con el formato XML del lado servidor, puede utilizar el proveedor SQLXMLOLEDB o el proveedor SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="514b0-108">With server-side XML formatting, you can use either the SQLXMLOLEDB provider or the SQLOLEDB provider.</span></span>  <span data-ttu-id="514b0-109">El proveedor SQLXMLOLEDB utiliza Sqlxml4.dll, incluido en SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="514b0-109">The SQLXMLOLEDB provider uses Sqlxml4.dll, which is included in SQLXML 4.0.</span></span> <span data-ttu-id="514b0-110">Al utilizar el proveedor SQLOLEDB, de forma predeterminada obtiene la funcionalidad SQLXML que proporciona Sqlxmlx.dll, incluida con [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows o en Microsoft Data Access Components (MDAC) 2.6 o posterior.</span><span class="sxs-lookup"><span data-stu-id="514b0-110">When you use the SQLOLEDB provider, by default you get the SQLXML functionality provided by Sqlxmlx.dll, which is included with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows or in Microsoft Data Access Components (MDAC) 2.6 or later.</span></span> <span data-ttu-id="514b0-111">Para usar Sqlxml4.dll con SQLOLEDB, debe establecer la propiedad versión de SQLXML en "SQLXML. 4.0" en el objeto de conexión SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="514b0-111">To use Sqlxml4.dll with SQLOLEDB, you must set the SQLXML Version property to "SQLXML.4.0" on the SQLOLEDB Connection object.</span></span> <span data-ttu-id="514b0-112">En cualquier caso, el servidor genera el documento XML y lo envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="514b0-112">In either case, the server produces the XML document and sends it to the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="514b0-113">Los diagramas de actualización y las consultas XPath se analizan en el cliente.</span><span class="sxs-lookup"><span data-stu-id="514b0-113">XPath queries and updategrams are parsed on the client.</span></span> <span data-ttu-id="514b0-114">Para obtener la plantilla XPath o la funcionalidad de diagrama de actualización en SQLXML 4.0, utilice Sqlxml4.dll.</span><span class="sxs-lookup"><span data-stu-id="514b0-114">To get the XPath template or updategram functionality in SQLXML 4.0, use Sqlxml4.dll.</span></span>  
  
 <span data-ttu-id="514b0-115">La ilustración siguiente muestra la arquitectura del formato XML del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="514b0-115">The following illustration shows the architecture of XML formatting on the client side.</span></span>  
  
 <span data-ttu-id="514b0-116">![Arquitectura de formato XML en el lado cliente.](../../../database-engine/dev-guide/media/clientsidexml.gif "Arquitectura de formato XML en el lado cliente.")</span><span class="sxs-lookup"><span data-stu-id="514b0-116">![Architecture of XML formatting on the client side.](../../../database-engine/dev-guide/media/clientsidexml.gif "Architecture of XML formatting on the client side.")</span></span>  
  
 <span data-ttu-id="514b0-117">En este ejemplo, el cliente utiliza el proveedor SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="514b0-117">In this example, the client uses the SQLXMLOLEDB provider.</span></span> <span data-ttu-id="514b0-118">En la cadena de conexión, la propiedad del proveedor de datos debe establecerse en SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="514b0-118">In the connection string, the Data Provider property must be set to SQLOLEDB.</span></span> <span data-ttu-id="514b0-119">(Este es el único valor aceptado en SQLXML 4,0). El comando que se ejecuta en el cliente se envía al servidor.</span><span class="sxs-lookup"><span data-stu-id="514b0-119">(This is the only value accepted in SQLXML 4.0.) The command that is executed on the client is sent to the server.</span></span> <span data-ttu-id="514b0-120">El conjunto de filas que se genera en el servidor se envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="514b0-120">The rowset that is generated on the server is sent to the client.</span></span> <span data-ttu-id="514b0-121">En el cliente se lleva a cabo el formato del documento XML a partir del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="514b0-121">The formatting of the XML document from the rowset is performed on the client.</span></span>  
  
 <span data-ttu-id="514b0-122">En SQLXML 4.0, se pueden utilizar como proveedores de datos [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) o el proveedor SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="514b0-122">In SQLXML 4.0, either the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) or the SQLOLEDB provider can be used as the data provider.</span></span> <span data-ttu-id="514b0-123">Puede tener acceso a cualquier origen de datos.</span><span class="sxs-lookup"><span data-stu-id="514b0-123">You can potentially access any data source.</span></span> <span data-ttu-id="514b0-124">La transformación XML se puede aplicar en el cliente siempre que la consulta devuelva un único conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="514b0-124">As long as the query returns a single rowset, the XML transformation can be applied on the client.</span></span>  
  
  
