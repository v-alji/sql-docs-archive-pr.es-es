---
title: Comunicación con SQL Server (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, communicating with SQL Server
- ODBC applications, communicating with SQL Server
- ODBC, communicating with SQL Server
ms.assetid: cca3dcf0-2a7e-465a-84de-7ce055360eb6
author: rothja
ms.author: jroth
ms.openlocfilehash: c41ac2dcce9c5bdbdd351148d16bcaa8f067d22f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748786"
---
# <a name="communicating-with-sql-server-odbc"></a><span data-ttu-id="5f808-102">Comunicar con SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="5f808-102">Communicating with SQL Server (ODBC)</span></span>
  <span data-ttu-id="5f808-103">Para que una aplicación ODBC se comunique con una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , debe asignar el entorno y los identificadores de conexión y conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5f808-103">For an ODBC application to communicate with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it must allocate environment and connection handles and connect to the data source.</span></span> <span data-ttu-id="5f808-104">Una vez establecida una conexión, la aplicación puede enviar consultas al servidor y procesar cualquier conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5f808-104">After a connection is established, the application can send queries to the server and process any result sets.</span></span> <span data-ttu-id="5f808-105">Cuando la aplicación ha terminado de usar el origen de datos, se desconecta del origen de datos y libera el identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="5f808-105">When the application has finished using the data source, it disconnects from the data source and frees the connection handle.</span></span> <span data-ttu-id="5f808-106">Cuando la aplicación ha liberado todos sus identificadores de conexión, libera el identificador del entorno.</span><span class="sxs-lookup"><span data-stu-id="5f808-106">When the application has freed all its connection handles, it frees the environment handle.</span></span>  
  
 <span data-ttu-id="5f808-107">Una aplicación puede conectarse a cualquier número de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="5f808-107">An application can connect to any number of data sources.</span></span> <span data-ttu-id="5f808-108">La aplicación puede usar una combinación de controladores y orígenes de datos, el mismo controlador y una combinación de orígenes de datos o incluso el mismo controlador y varias conexiones al mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5f808-108">The application can use a combination of drivers and data sources, the same driver and a combination of data sources, or even the same driver and multiple connections to the same data source.</span></span>  
  
 <span data-ttu-id="5f808-109">Puede descargar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] los ejemplos de ODBC de Native Client en la página de [descargas de SQL Server](https://go.microsoft.com/fwlink/?LinkId=62796) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="5f808-109">You can download [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC samples from the [SQL Server Downloads](https://go.microsoft.com/fwlink/?LinkId=62796) page on MSDN.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f808-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5f808-110">In This Section</span></span>  
  
-   [<span data-ttu-id="5f808-111">Asignar un identificador de entorno</span><span class="sxs-lookup"><span data-stu-id="5f808-111">Allocating an Environment Handle</span></span>](allocating-an-environment-handle.md)  
  
-   [<span data-ttu-id="5f808-112">Asignar un identificador de conexión</span><span class="sxs-lookup"><span data-stu-id="5f808-112">Allocating a Connection Handle</span></span>](allocating-a-connection-handle.md)  
  
-   [<span data-ttu-id="5f808-113">Orígenes de datos de ODBC para SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5f808-113">SQL Server Native Client ODBC Data Sources</span></span>](../../integration-services/connection-manager/data-sources.md)  
  
-   [<span data-ttu-id="5f808-114">Conectar con un origen de datos &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="5f808-114">Connecting to a Data Source &#40;ODBC&#41;</span></span>](connecting-to-a-data-source-odbc.md)  
  
-   [<span data-ttu-id="5f808-115">Desconectarse de un origen de datos</span><span class="sxs-lookup"><span data-stu-id="5f808-115">Disconnecting from a Data Source</span></span>](disconnecting-from-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="5f808-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f808-116">See Also</span></span>  
 <span data-ttu-id="5f808-117">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="5f808-117">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="5f808-118">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="5f808-118">SQLSetEnvAttr</span></span>](../native-client-odbc-api/sqlsetenvattr.md)  
  
  
