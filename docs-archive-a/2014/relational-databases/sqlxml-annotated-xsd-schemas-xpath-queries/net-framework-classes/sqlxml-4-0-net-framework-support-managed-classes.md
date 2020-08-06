---
title: Clases administradas de SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- .NET Framework [SQLXML], Managed Classes
- SQL Server .NET Data Provider
- Managed Classes [SQLXML], about managed classes
- providers [SQLXML], SQL Server .NET Data Provider
- data providers [SQLXML], SQL Server .NET Data Provider
- Managed Classes [SQLXML]
- XML [SQLXML]
- SQLXML Managed Classes
- providers [SQLXML], SQLXML Managed Classes
- data providers [SQLXML], SQLXML Managed Classes
- SQLXML, Managed Classes
ms.assetid: 73a5faeb-dabf-4895-acb5-a9651b646065
author: rothja
ms.author: jroth
ms.openlocfilehash: bb8d2d4f2d2fc512901e4ad37f0e46cf696b9475
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661873"
---
# <a name="sqlxml-managed-classes"></a><span data-ttu-id="9824f-102">clases administradas de SQLXML</span><span class="sxs-lookup"><span data-stu-id="9824f-102">SQLXML Managed Classes</span></span>
  <span data-ttu-id="9824f-103">Las clases administradas de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML exponen la funcionalidad de SQLXML 4.0 dentro de [!INCLUDE[msCoName](../../../includes/msconame-md.md)].NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9824f-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes exposes the functionality of SQLXML 4.0 inside the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="9824f-104">Con las clases administradas de SQLXML, puede escribir una aplicación C# para tener acceso a los datos XML desde una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], introducir los datos en el entorno .NET Framework, procesar los datos y devolver las actualizaciones a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como un DiffGram para aplicar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="9824f-104">With SQLXML Managed Classes, you can write a C# application to access XML data from an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], bring the data into the .NET Framework environment, process the data, and send the updates back to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a DiffGram to apply the updates.</span></span> <span data-ttu-id="9824f-105">Debe utilizar un esquema de asignación al aplicar actualizaciones a una base de datos [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizando clases administradas de SQLXML.</span><span class="sxs-lookup"><span data-stu-id="9824f-105">You must use a mapping schema when applying updates to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database using SQLXML Managed Classes.</span></span> <span data-ttu-id="9824f-106">Para obtener un ejemplo funcional, vea [obtener acceso a la funcionalidad de SQLXML en el entorno de .net](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9824f-106">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="9824f-107">Para utilizar las clases administradas de SQLXML con SQLXML 4.0, debe instalar Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9824f-107">To use the SQLXML Managed Classes with SQLXML 4.0, you must install Microsoft Visual Studio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9824f-108">.NET Framework incluye el proveedor de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].NET.</span><span class="sxs-lookup"><span data-stu-id="9824f-108">The .NET Framework includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .NET Data Provider.</span></span> <span data-ttu-id="9824f-109">Este proveedor se puede utilizar para tener acceso a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] desde el entorno .NET; sin embargo, solamente puede administrar consultas SQL tradicionales (es decir, consultas a la base de datos relacional con la excepción de consultas FOR XML).</span><span class="sxs-lookup"><span data-stu-id="9824f-109">This provider can be used to access [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the .NET environment; however, it can handle only traditional SQL queries (that is, relational database queries with the exception of FOR XML queries).</span></span> <span data-ttu-id="9824f-110">No puede ejecutar plantillas XML o consultas XPath del servidor en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9824f-110">You cannot execute XML templates or the server-side XPath queries in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9824f-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9824f-111">In This Section</span></span>  
 [<span data-ttu-id="9824f-112">Modelo de objetos de clases administradas SQLXML</span><span class="sxs-lookup"><span data-stu-id="9824f-112">SQLXML Managed Classes Object Model</span></span>](../../../database-engine/dev-guide/sqlxml-managed-classes-object-model.md)  
 <span data-ttu-id="9824f-113">Documenta las clases administradas de SQLXML y sus propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="9824f-113">Documents SQLXML Managed Classes and their properties and methods.</span></span>  
  
 [<span data-ttu-id="9824f-114">Utilizar clases administradas de SQLXML</span><span class="sxs-lookup"><span data-stu-id="9824f-114">Using the SQLXML Managed Classes</span></span>](sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="9824f-115">Se proporcionan ejemplos de uso de las clases administradas de SQLXML.</span><span class="sxs-lookup"><span data-stu-id="9824f-115">Provides examples of using SQLXML Managed Classes.</span></span>  
  
  
