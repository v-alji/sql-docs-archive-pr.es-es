---
title: Acceso a datos desde objetos de base de datos CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], data access
- routines [CLR integration]
- data access [CLR integration]
- ADO.NET [CLR integration]
- internal data access [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], data access
- managed code [SQL Server], database objects
- .NET Data Access Provider for SQL Server [CLR integration]
- managed code [SQL Server], data access
- SqlClient provider
- in-process data access providers [CLR integration]
ms.assetid: 9a0f4dee-71c1-42e9-a85e-52382807010f
author: rothja
ms.author: jroth
ms.openlocfilehash: d229d490a9f3a7bc6f613259ee0535218de47975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676508"
---
# <a name="data-access-from-clr-database-objects"></a><span data-ttu-id="346b6-102">Acceso a datos de objetos de base de datos de CLR</span><span class="sxs-lookup"><span data-stu-id="346b6-102">Data Access from CLR Database Objects</span></span>
  <span data-ttu-id="346b6-103">Una rutina Common Language Runtime (CLR) puede acceder fácilmente a los datos almacenados en la instancia de [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] en la que se ejecuta, así como a los datos almacenados en instancias remotas.</span><span class="sxs-lookup"><span data-stu-id="346b6-103">A common language runtime (CLR) routine may easily access data stored in the instance of [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] in which it runs, as well as data stored in remote instances.</span></span> <span data-ttu-id="346b6-104">El contexto del usuario en el que se ejecuta el código, determina los datos concretos a los que la rutina puede tener acceso.</span><span class="sxs-lookup"><span data-stu-id="346b6-104">Which particular data the routine can access is determined by the user context in which the code is running.</span></span> <span data-ttu-id="346b6-105">Obtener acceso a los datos desde un objeto de base de datos CLR mediante el proveedor de datos de .NET Framework para los [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] datos de las aplicaciones cliente administradas y de nivel intermedio.</span><span class="sxs-lookup"><span data-stu-id="346b6-105">Access data from within a CLR database object by using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data from managed client and middle-tier applications.</span></span> <span data-ttu-id="346b6-106">Debido a esto, puede aprovechar sus conocimientos de ADO.NET y `SqlClient` en aplicaciones cliente y de nivel medio.</span><span class="sxs-lookup"><span data-stu-id="346b6-106">Because of this, you can leverage your knowledge of ADO.NET and `SqlClient` in client and middle-tier applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="346b6-107">De forma predeterminada, los métodos de tipo definido por el usuario y funciones definidas por el usuario no pueden tener acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="346b6-107">User-defined type methods and user-defined functions are not allowed to perform data access by default.</span></span> <span data-ttu-id="346b6-108">Debe establecer la propiedad `DataAccess` de `SqlMethodAttribute` o `SqlFunctionAttribute` en `DataAccessKind.Read` para habilitar el acceso a datos de solo lectura desde métodos de tipo definido por el usuario (UDT) o funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="346b6-108">You must set the `DataAccess` property of `SqlMethodAttribute` or `SqlFunctionAttribute` to `DataAccessKind.Read` to enable read-only data access from user-defined type (UDT) methods or user-defined functions.</span></span> <span data-ttu-id="346b6-109">Las operaciones de modificación de datos o las funciones definidas por el usuario no se permiten desde los UDT y, si se intentan producen excepciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="346b6-109">Data modification operations are not allowed from UDTs or user-defined functions, and throws exceptions at execution time if attempted.</span></span>  
  
 <span data-ttu-id="346b6-110">En esta sección únicamente se discuten las diferencias de funcionalidad y de comportamiento concretas cuando se tiene acceso a los datos desde un objeto de base de datos de CLR.</span><span class="sxs-lookup"><span data-stu-id="346b6-110">This section discusses only the specific functional and behavioral differences when accessing data from within a CLR database object.</span></span> <span data-ttu-id="346b6-111">Para obtener más información acerca de las características y funcionalidad de ADO.NET, vea la documentación de ADO.NET que se incluye en .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="346b6-111">For more information about the features and functionality of ADO.NET, see the ADO.NET documentation included in the .NET Framework SDK.</span></span>  
  
 <span data-ttu-id="346b6-112">En la siguiente tabla se muestran los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="346b6-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="346b6-113">Conexión de contexto</span><span class="sxs-lookup"><span data-stu-id="346b6-113">Context Connection</span></span>](context-connection.md)  
 <span data-ttu-id="346b6-114">Describe la conexión de contexto a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="346b6-114">Describes the context connection to SQL Server.</span></span>  
  
 [<span data-ttu-id="346b6-115">Suplantación y credenciales para conexiones</span><span class="sxs-lookup"><span data-stu-id="346b6-115">Impersonation and Credentials for Connections</span></span>](impersonation-and-credentials-for-connections.md)  
 <span data-ttu-id="346b6-116">Describe la suplantación de conexiones y las credenciales de conexión.</span><span class="sxs-lookup"><span data-stu-id="346b6-116">Describes impersonating connections and connection credentials.</span></span>  
  
 [<span data-ttu-id="346b6-117">Extensiones específicas en proceso de SQL Server a ADO.NET</span><span class="sxs-lookup"><span data-stu-id="346b6-117">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md)  
 <span data-ttu-id="346b6-118">Describe los objetos concretos en proceso `SqlPipe`, `SqlContext`, `SqlTriggerContext` y `SqlDataRecord`.</span><span class="sxs-lookup"><span data-stu-id="346b6-118">Discusses the in-process specific `SqlPipe`, `SqlContext`, `SqlTriggerContext`, and `SqlDataRecord` objects.</span></span>  
  
 [<span data-ttu-id="346b6-119">Integración CLR y transacciones</span><span class="sxs-lookup"><span data-stu-id="346b6-119">CLR Integration and Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="346b6-120">Describe cómo se integra el nuevo marco de transacciones que se proporciona en el espacio de nombres System.Transactions con ADO.NET y con la integración CLR de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="346b6-120">Describes how the new transaction framework provided in the System.Transactions namespace integrates with ADO.NET and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span>  
  
 [<span data-ttu-id="346b6-121">Serialización XML de objetos de base de datos de CLR</span><span class="sxs-lookup"><span data-stu-id="346b6-121">XML Serialization from CLR Database Objects</span></span>](../../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md)  
 <span data-ttu-id="346b6-122">Explica cómo habilitar escenarios de serialización XML de objetos de base de datos de CLR en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="346b6-122">Explains how to enable XML serialization scenarios of CLR database objects inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
  
