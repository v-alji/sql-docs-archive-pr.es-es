---
title: Agregar un origen de datos (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: b4ac6f0e-8e6a-4b1a-9a7e-60e0a69b2180
author: rothja
ms.author: jroth
ms.openlocfilehash: 519990e9dd9d84f75c4efc6c76b910f0a359f52f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671040"
---
# <a name="add-a-data-source-odbc"></a><span data-ttu-id="fa85e-102">Agregar un origen de datos (ODBC)</span><span class="sxs-lookup"><span data-stu-id="fa85e-102">Add a Data Source (ODBC)</span></span>
  <span data-ttu-id="fa85e-103">Puede Agregar un origen de datos mediante el administrador ODBC, mediante programación (mediante [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) o mediante la creación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="fa85e-103">You can add a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by creating a file.</span></span>  
  
### <a name="to-add-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="fa85e-104">Para agregar un origen de datos mediante el Administrador ODBC</span><span class="sxs-lookup"><span data-stu-id="fa85e-104">To add a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="fa85e-105">En el **Panel de control**, acceda a **herramientas administrativas** y, a continuación, a **orígenes de datos (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-105">From the **Control Panel**, access **Administrative Tools** and then **Data Sources (ODBC)**.</span></span> <span data-ttu-id="fa85e-106">De modo alternativo, puede invocar odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="fa85e-106">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="fa85e-107">Haga clic en la pestaña **DSN de usuario**, **DSN de sistema**o **DSN de archivo** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-107">Click the **User DSN**, **System DSN**, or **File DSN** tab, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="fa85e-108">Haga clic en **SQL Server**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-108">Click **SQL Server**, and then click **Finish**.</span></span>  
  
4.  <span data-ttu-id="fa85e-109">Complete los pasos del Asistente para crear un nuevo origen de datos para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fa85e-109">Complete the Steps in the Create a New Data Source to SQL Server Wizard.</span></span>  
  
### <a name="to-add-a-data-source-programmatically"></a><span data-ttu-id="fa85e-110">Para agregar un origen de datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="fa85e-110">To add a data source programmatically</span></span>  
  
1.  <span data-ttu-id="fa85e-111">Llame a [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) con el segundo parámetro establecido en ODBC_ADD_DSN o en ODBC_ADD_SYS_DSN.</span><span class="sxs-lookup"><span data-stu-id="fa85e-111">Call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) with the second parameter set to either ODBC_ADD_DSN or ODBC_ADD_SYS_DSN.</span></span>  
  
### <a name="to-add-a-file-data-source"></a><span data-ttu-id="fa85e-112">Para agregar un origen de datos de archivo</span><span class="sxs-lookup"><span data-stu-id="fa85e-112">To add a file data source</span></span>  
  
1.  <span data-ttu-id="fa85e-113">Llame a [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) con un parámetro SAVEFILE = file_name en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="fa85e-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) with a SAVEFILE=file_name parameter in the connect string.</span></span> <span data-ttu-id="fa85e-114">Si la conexión se realiza correctamente, el controlador ODBC crea un origen de datos de archivo con los parámetros de conexión en la ubicación señalada por el parámetro SAVEFILE.</span><span class="sxs-lookup"><span data-stu-id="fa85e-114">If the connect is successful, the ODBC driver creates a file data source with the connection parameters in the location pointed to by the SAVEFILE parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa85e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa85e-115">See Also</span></span>  
 [<span data-ttu-id="fa85e-116">Temas de procedimientos de configuración del controlador ODBC de SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa85e-116">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
