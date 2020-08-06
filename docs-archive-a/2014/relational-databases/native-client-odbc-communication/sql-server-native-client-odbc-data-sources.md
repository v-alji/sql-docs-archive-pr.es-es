---
title: SQL Server Native Client orígenes de datos ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, about data sources
- ODBC data sources, names
- data sources [SQL Server Native Client]
- names [ODBC]
- ODBC applications, data sources
- SQL Server Native Client ODBC driver, data sources
- ODBC data sources
ms.assetid: a6a50fd0-d439-43fd-b76f-16ec02f478c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 6960118e13f0843640b18056bda655726cbbbd29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672938"
---
# <a name="sql-server-native-client-odbc-data-sources"></a><span data-ttu-id="69b25-102">Orígenes de datos de ODBC para SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="69b25-102">SQL Server Native Client ODBC Data Sources</span></span>
  <span data-ttu-id="69b25-103">Un nombre del origen de datos (DSN) de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] identifica un origen de datos ODBC que contiene toda la información que una aplicación ODBC necesita para conectar a una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en un servidor concreto.</span><span class="sxs-lookup"><span data-stu-id="69b25-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source name (DSN) identifies an ODBC data source containing all of the information that an ODBC application needs to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a specific server.</span></span> <span data-ttu-id="69b25-104">Existen dos métodos que puede utilizar para definir un nombre del origen de datos ODBC:</span><span class="sxs-lookup"><span data-stu-id="69b25-104">There are two ways you can define an ODBC data source name:</span></span>  
  
-   <span data-ttu-id="69b25-105">En un equipo cliente, abra herramientas administrativas en el panel de control y haga doble clic en **orígenes de datos (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="69b25-105">On a client computer, open Administrative Tools in Control Panel, and double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="69b25-106">Así abrirá el Administrador de orígenes de datos ODBC, que puede utilizar para crear un DSN.</span><span class="sxs-lookup"><span data-stu-id="69b25-106">This will open the ODBC Data Source Administrator, which you can use to create a DSN.</span></span>  
  
-   <span data-ttu-id="69b25-107">En una aplicación ODBC, llame a [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="69b25-107">In an ODBC application, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="69b25-108">Un origen de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contiene:</span><span class="sxs-lookup"><span data-stu-id="69b25-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source contains:</span></span>  
  
-   <span data-ttu-id="69b25-109">El nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="69b25-109">The name of the data source.</span></span>  
  
-   <span data-ttu-id="69b25-110">Cualquier información necesaria para conectar a una instancia concreta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69b25-110">Any information needed to connect to a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="69b25-111">La base de datos predeterminada que se utilizará en una instancia concreta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (opcional).</span><span class="sxs-lookup"><span data-stu-id="69b25-111">The default database to use on a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (optional).</span></span>  
  
-   <span data-ttu-id="69b25-112">Valores como las opciones ANSI que se van a utilizar, si se registran estadísticas de rendimiento, etc. (opcional).</span><span class="sxs-lookup"><span data-stu-id="69b25-112">Settings such as which ANSI options to use, whether to log performance statistics, and so on (optional).</span></span>  
  
 <span data-ttu-id="69b25-113">No es necesario contar con una aplicación ODBC para conectar a través de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="69b25-113">An ODBC application is not required to connect through a data source.</span></span> <span data-ttu-id="69b25-114">Sin embargo, la aplicación debe proporcionar la misma información de conectividad a una función de conexión de ODBC que el controlador encontraría en un DSN.</span><span class="sxs-lookup"><span data-stu-id="69b25-114">However, the application must provide the same connectivity information to an ODBC connect function that the driver would otherwise find in a DSN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b25-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69b25-115">See Also</span></span>  
 [<span data-ttu-id="69b25-116">Comunicarse con SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="69b25-116">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
