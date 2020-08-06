---
title: Compilar aplicaciones con SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], building applications
- SQLNCLI, building applications
- applications [SQL Server Native Client]
- SQL Server Native Client, building applications
ms.assetid: 254a2b48-f0e3-43b5-a48d-3d666c2a779f
author: rothja
ms.author: jroth
ms.openlocfilehash: d08fe1042ab1a79f6b48648f5a774b4fbac49ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674072"
---
# <a name="building-applications-with-sql-server-native-client"></a><span data-ttu-id="57273-102">Generar aplicaciones con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="57273-102">Building Applications with SQL Server Native Client</span></span>
  <span data-ttu-id="57273-103">Al desarrollar una aplicación que usa la biblioteca de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, pueden surgir algunos problemas.</span><span class="sxs-lookup"><span data-stu-id="57273-103">When developing an application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library, there are a number of issues that come into play.</span></span> <span data-ttu-id="57273-104">En los temas de esta sección se tratan muchos de estos problemas, incluyendo la actualización de MDAC a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, mediante los archivos de encabezado y biblioteca de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, y la información general de las distintas cadenas de conexión que se pueden usar con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="57273-104">The topics in this section discuss many of these issues including upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files, and an overview of the various connection strings that can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57273-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="57273-105">In This Section</span></span>  
 [<span data-ttu-id="57273-106">Instalar SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="57273-106">Installing SQL Server Native Client</span></span>](installing-sql-server-native-client.md)  
 <span data-ttu-id="57273-107">Se describe cómo se instala [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, las ubicaciones en las que se instalan diversos componentes y cómo desinstalar [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="57273-107">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is installed, the locations that various components are installed to, and how to uninstall [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="57273-108">Componentes de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="57273-108">Components of SQL Server Native Client</span></span>](components-of-sql-server-native-client.md)  
 <span data-ttu-id="57273-109">Se describen los componentes que constituyen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client incluidos los archivos de biblioteca, recurso, ayuda y encabezado.</span><span class="sxs-lookup"><span data-stu-id="57273-109">Discusses the components that make up [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client including library, resource, help, and header files.</span></span>  
  
 [<span data-ttu-id="57273-110">Usar palabras clave de cadena de conexión con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="57273-110">Using Connection String Keywords with SQL Server Native Client</span></span>](using-connection-string-keywords-with-sql-server-native-client.md)  
 <span data-ttu-id="57273-111">Se describen los diversos tipos de cadenas de conexión que se pueden usar cuando se realiza la conexión a una base de datos a través de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="57273-111">Discusses the various types of connection strings that can be used when connecting to a database through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="57273-112">Utilizar los archivos de encabezado y de biblioteca de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="57273-112">Using the SQL Server Native Client Header and Library Files</span></span>](using-the-sql-server-native-client-header-and-library-files.md)  
 <span data-ttu-id="57273-113">Se describe cómo usar los archivos de encabezado y biblioteca de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="57273-113">Discusses how to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files within an application.</span></span>  
  
 [<span data-ttu-id="57273-114">Actualizar una aplicación de MDCA a SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="57273-114">Updating an Application to SQL Server Native Client from MDAC</span></span>](updating-an-application-to-sql-server-native-client-from-mdac.md)  
 <span data-ttu-id="57273-115">Se describen las diferencias que existen entre [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client y MDAC, y los problemas que deberían tenerse en cuenta a la hora de realizar la actualización de MDAC a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="57273-115">Discusses the differences between [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and MDAC and issues that should be considered when upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="57273-116">Actualización de una aplicación desde SQL Server 2005 Native Client</span><span class="sxs-lookup"><span data-stu-id="57273-116">Updating an Application from SQL Server 2005 Native Client</span></span>](updating-an-application-from-sql-server-2005-native-client.md)  
 <span data-ttu-id="57273-117">Se describen los problemas que deben tenerse en cuenta a la hora de realizar la actualización de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client en [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57273-117">Discusses issues that should be considered when upgrading from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span>  
  
 [<span data-ttu-id="57273-118">Utilizar ADO con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="57273-118">Using ADO with SQL Server Native Client</span></span>](using-ado-with-sql-server-native-client.md)  
 <span data-ttu-id="57273-119">Se describe el modo en que ADO usa [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client para obtener acceso a la funcionalidad de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y usarla.</span><span class="sxs-lookup"><span data-stu-id="57273-119">Discusses how ADO can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access and use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span>  
  
 [<span data-ttu-id="57273-120">Directivas de soporte para SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="57273-120">Support Policies for SQL Server Native Client</span></span>](support-policies-for-sql-server-native-client.md)  
 <span data-ttu-id="57273-121">Se describe cómo se pueden usar varios componentes de acceso a datos con versiones diferentes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="57273-121">Discusses how various data-access components can be used with different versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="57273-122">Conexión a una Azure SQL Database con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="57273-122">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>](connecting-to-a-windows-azure-sql-database-using-sql-server-native-client.md)  
 <span data-ttu-id="57273-123">Describe cómo conectarse a una base de datos de [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="57273-123">Discusses how to connect to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57273-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57273-124">See Also</span></span>  
 <span data-ttu-id="57273-125">[Programación de SQL Server Native Client](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="57273-125">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 <span data-ttu-id="57273-126">[Temas de procedimientos de ODBC](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="57273-126">[ODBC How-to Topics](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span></span>  
 [<span data-ttu-id="57273-127">Temas de procedimientos de OLE DB</span><span class="sxs-lookup"><span data-stu-id="57273-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
