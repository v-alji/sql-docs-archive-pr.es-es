---
title: Temas de procedimientos de ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 151f2066-1c37-410f-88f4-b27dfca66031
author: rothja
ms.author: jroth
ms.openlocfilehash: cfeb120b9fa1fedb5358b5e12dabed7835f9a6b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748765"
---
# <a name="odbc-how-to-topics"></a><span data-ttu-id="a7320-102">Temas de procedimientos de ODBC</span><span class="sxs-lookup"><span data-stu-id="a7320-102">ODBC How-to Topics</span></span>
  <span data-ttu-id="a7320-103">Para poder usar el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , es necesario que sea capaz de crear orígenes de datos ODBC y que se asegure de que el servidor tiene la versión correcta de los procedimientos almacenados de catálogo.</span><span class="sxs-lookup"><span data-stu-id="a7320-103">To use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver, you must be able to create ODBC data sources and ensure that the server has the correct version of the catalog stored procedures.</span></span> <span data-ttu-id="a7320-104">Para codificar una aplicación ODBC que usa SQL Server, debe saber cómo asignar identificadores de ODBC, establecer atributos, conectarse a una instancia de SQL Server, ejecutar consultas y procesar resultados.</span><span class="sxs-lookup"><span data-stu-id="a7320-104">To code an ODBC application that uses SQL Server, you must know how to allocate ODBC handles, set attributes, connect to an instance of SQL Server, execute queries, and process results.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7320-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a7320-105">In This Section</span></span>  
  
-   [<span data-ttu-id="a7320-106">Temas de procedimientos de configuración del controlador ODBC de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a7320-106">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
-   [<span data-ttu-id="a7320-107">Asignar identificadores y conectarse a SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-107">Allocate Handles and Connect to SQL Server &#40;ODBC&#41;</span></span>](allocate-handles-and-connect-to-sql-server-odbc.md)  
  
-   [<span data-ttu-id="a7320-108">Temas de procedimientos de ejecución de consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-108">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](execute-queries/executing-queries-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="a7320-109">Temas de procedimientos de procesamiento de resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-109">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="a7320-110">Temas de procedimientos de uso de cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-110">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](cursors/using-cursors-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="a7320-111">Usar Microsoft Coordinador de transacciones distribuidas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-111">Use Microsoft Distributed Transaction Coordinator &#40;ODBC&#41;</span></span>](use-microsoft-distributed-transaction-coordinator-odbc.md)  
  
-   [<span data-ttu-id="a7320-112">Temas de procedimientos de ejecución de procedimientos almacenados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-112">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="a7320-113">Temas de procedimientos de administración de columnas de texto e imagen &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-113">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="a7320-114">Temas de procedimientos de generación de perfiles de rendimiento del controlador ODBC &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-114">Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-odbc.md)  
  
-   [<span data-ttu-id="a7320-115">Procesar errores de ODBC &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-115">Process ODBC Errors &#40;ODBC&#41;</span></span>](process-odbc-errors-odbc.md)  
  
-   [<span data-ttu-id="a7320-116">Temas de procedimientos de la copia masiva con el controlador ODBC de SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-116">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copy/bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="a7320-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7320-117">See Also</span></span>  
 [<span data-ttu-id="a7320-118">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7320-118">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
