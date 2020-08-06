---
title: Eliminar un origen de datos (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: 910e3e16-7b91-49d8-80bb-b4243926afaa
author: rothja
ms.author: jroth
ms.openlocfilehash: 6e8acd6414b39b317ff0fcfe1b7b9fbab38ae0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671038"
---
# <a name="delete-a-data-source-odbc"></a><span data-ttu-id="1be45-102">Eliminar un origen de datos (ODBC)</span><span class="sxs-lookup"><span data-stu-id="1be45-102">Delete a Data Source (ODBC)</span></span>
  <span data-ttu-id="1be45-103">Puede eliminar un origen de datos mediante el administrador ODBC, mediante programación (mediante [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) o eliminando un archivo (si es un nombre de origen de datos de archivo).</span><span class="sxs-lookup"><span data-stu-id="1be45-103">You can delete a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by deleting a file (if a file data source name).</span></span>  
  
### <a name="to-delete-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="1be45-104">Para eliminar un origen de datos mediante el Administrador ODBC</span><span class="sxs-lookup"><span data-stu-id="1be45-104">To delete a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="1be45-105">En el **Panel de control**, Abra **herramientas administrativas**y, a continuación, haga doble clic en **orígenes de datos (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="1be45-105">In **Control Panel**, open **Administrative Tools**, and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="1be45-106">Como alternativa, puede ejecutar odbcad32.exe desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="1be45-106">Alternatively, you can run odbcad32.exe from the command prompt.</span></span>  
  
2.  <span data-ttu-id="1be45-107">Haga clic en la pestaña **DSN de usuario**, **DSN de sistema**o DSN de **archivo** .</span><span class="sxs-lookup"><span data-stu-id="1be45-107">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="1be45-108">Haga clic en el origen de datos para eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="1be45-108">Click the data source to delete.</span></span>  
  
4.  <span data-ttu-id="1be45-109">Haga clic en **quitar**y confirme la eliminación.</span><span class="sxs-lookup"><span data-stu-id="1be45-109">Click **Remove**, and then confirm the deletion.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1be45-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1be45-110">Example</span></span>  
 <span data-ttu-id="1be45-111">Para eliminar un origen de datos mediante programación, llame a [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) utilizando ODBC_REMOVE_DSN o ODBC_REMOVE_SYS_DSN como segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="1be45-111">To programmatically delete a data source, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) using either ODBC_REMOVE_DSN or ODBC_REMOVE_SYS_DSN as the second parameter.</span></span>  
  
 <span data-ttu-id="1be45-112">El ejemplo siguiente se muestra cómo se puede eliminar un origen de datos mediante programación.</span><span class="sxs-lookup"><span data-stu-id="1be45-112">The following sample shows how you can programmatically delete a data source.</span></span>  
  
```  
// remove_odbc_data_source.cpp  
// compile with: ODBCCP32.lib user32.lib  
#include <iostream>  
#include <windows.h>  
#include <odbcinst.h>  
  
int main() {   
   LPCSTR provider = "SQL Server";   // Windows SQL Server Driver  
   LPCSTR provider = "SQL Server";   // Windows SQL Server driver  
   LPCSTR provider2 = "SQL Server Native Client 11.0";   // SQL Server 2012 Native Client driver  
   LPCSTR dsnname = "DSN=data2";  
   BOOL retval = SQLConfigDataSource(NULL, ODBC_REMOVE_DSN, provider, dsnname);  
   std::cout << retval;   // 1 if successful  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1be45-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1be45-113">See Also</span></span>  
 [<span data-ttu-id="1be45-114">Temas de procedimientos de configuración del controlador ODBC de SQL Server</span><span class="sxs-lookup"><span data-stu-id="1be45-114">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
