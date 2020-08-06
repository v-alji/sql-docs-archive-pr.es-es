---
title: Capturar columnas mediante IRow::GetColumns (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- IRow interface
ms.assetid: a4f79906-da0e-42f2-b0e9-812c29f39e48
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e3eb9e2b55ad03ae4b5739850557836589649d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744695"
---
# <a name="fetch-columns-using-irowgetcolumns-ole-db"></a><span data-ttu-id="2d1ea-102">Capturar columnas mediante IRow::GetColumns (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="2d1ea-102">Fetch Columns Using IRow::GetColumns (OLE DB)</span></span>
  <span data-ttu-id="2d1ea-103">La interfaz `IRow` permite el acceso directo a las columnas de una fila única del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-103">The `IRow` interface allows direct access to columns of a single row in the result set.</span></span> <span data-ttu-id="2d1ea-104">Así, `IRow` supone una manera eficaz de recuperar las columnas de un conjunto de resultados con una fila.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-104">Thus, `IRow` is an efficient way to retrieve columns from a result set with one row.</span></span>  
  
 <span data-ttu-id="2d1ea-105">Existe un ejemplo de código disponible que muestra cómo capturar una fila única mediante `IRow`.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-105">A code sample is available that showshow to fetch a single row using `IRow`.</span></span> <span data-ttu-id="2d1ea-106">En este ejemplo, se recupera una columna a la vez de la fila.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-106">In this sample, one column at a time is retrieved from the row.</span></span> <span data-ttu-id="2d1ea-107">El ejemplo muestra:</span><span class="sxs-lookup"><span data-stu-id="2d1ea-107">The sample shows:</span></span>  
  
-   <span data-ttu-id="2d1ea-108">Cómo capturar un grupo de columnas (en secuencia).</span><span class="sxs-lookup"><span data-stu-id="2d1ea-108">How to fetch a group of columns (in sequence).</span></span>  
  
-   <span data-ttu-id="2d1ea-109">Cómo tener acceso dos veces a una columna.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-109">How to access a column twice.</span></span> <span data-ttu-id="2d1ea-110">La primera vez se obtiene el ancho de columna real y después se tiene acceso a los datos reales.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-110">The first time the actual column width is obtained, and later the actual data is accessed.</span></span> <span data-ttu-id="2d1ea-111">En la estructura DBCOLUMNACCESS, si **pdata** es NULL y **cbMaxLen** es 0, la llamada a `IRow` - `>GetColumns()` solo devuelve la longitud real de la columna.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-111">In the DBCOLUMNACCESS structure, if **pData** is NULL and **cbMaxLen** is 0, the call to `IRow`-`>GetColumns()` returns only the actual column length.</span></span> <span data-ttu-id="2d1ea-112">En este caso, se puede llamar a `IRow->GetColumns()` de nuevo en la misma columna para recuperar los datos reales.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-112">In this case, `IRow->GetColumns()` can be called again on the same column to retrieve the actual data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2d1ea-113">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-113">When possible, use Windows Authentication.</span></span> <span data-ttu-id="2d1ea-114">Si la autenticación de Windows no está disponible, solicite a los usuarios que escriban sus credenciales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-114">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="2d1ea-115">No guarde las credenciales en un archivo.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-115">Avoid storing credentials in a file.</span></span> <span data-ttu-id="2d1ea-116">Si debe conservar las credenciales, debe cifrarlas con la [API Crypto de Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="2d1ea-116">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-fetch-columns-using-irowgetcolumns"></a><span data-ttu-id="2d1ea-117">Para capturar columnas mediante IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="2d1ea-117">To fetch columns using IRow::GetColumns</span></span>  
  
1.  <span data-ttu-id="2d1ea-118">Establezca una conexión con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-118">Establish a connection to the data source.</span></span>  
  
2.  <span data-ttu-id="2d1ea-119">Ejecute el comando (en el siguiente ejemplo, se llama a ICommandExecute::Execute() con IID_IRow).</span><span class="sxs-lookup"><span data-stu-id="2d1ea-119">Execute the command (in the following example, ICommandExecute::Execute() is called with IID_IRow).</span></span>  
  
3.  <span data-ttu-id="2d1ea-120">Ejecute IRow::GetColumns () para capturar una o más columnas de la fila resultante.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-120">Execute IRow::GetColumns() to fetch one or more columns in the resulting row.</span></span> <span data-ttu-id="2d1ea-121">Si desea buscar el tamaño de columna real antes de capturar los datos, establezca pData de DBCOLUMNACCESS en NULL.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-121">If you want to find the actual column size before fetching data, set the pData in DBCOLUMNACCESS to NULL.</span></span> <span data-ttu-id="2d1ea-122">La llamada a IRow::GetColumns() solo devuelve el ancho de columna.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-122">The call to IRow::GetColumns() returns only the column width.</span></span> <span data-ttu-id="2d1ea-123">Otra llamada a IRow::GetColumns() capturará los datos.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-123">Another call the IRow::GetColumns() will fetch the data.</span></span>  
  
4.  <span data-ttu-id="2d1ea-124">Ejecute IRow::GetColumns() hasta obtener acceso a todas las columnas que necesita.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-124">Execute IRow::GetColumns() until all the columns you need are accessed.</span></span> <span data-ttu-id="2d1ea-125">Se debe tener acceso a las columnas en secuencia.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-125">The columns must be accessed in sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d1ea-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d1ea-126">Example</span></span>  
 <span data-ttu-id="2d1ea-127">En este ejemplo se muestra cómo se utiliza la interfaz IRow para permitir el acceso directo a las columnas de una sola fila del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-127">This sample shows how to use the IRow interface to allow direct access to columns of a single row in the result set.</span></span> <span data-ttu-id="2d1ea-128">Este ejemplo muestra:</span><span class="sxs-lookup"><span data-stu-id="2d1ea-128">The example shows:</span></span>  
  
-   <span data-ttu-id="2d1ea-129">Cómo capturar un grupo de columnas en secuencia.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-129">How to fetch a group of columns in sequence.</span></span>  
  
-   <span data-ttu-id="2d1ea-130">Cómo acceder dos veces a una columna - la primera vez se obtiene el ancho de columna real y, a continuación, se obtiene acceso a los datos reales.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-130">How to access a column twice - the first time the actual column width is obtained and then later the actual data is accessed.</span></span>  
  
 <span data-ttu-id="2d1ea-131">En la estructura DBCOLUMNACCESS, si pData es NULL y cbMaxLen es 0, la llamada a IRow->GetColumns devuelve solo la longitud de columna real.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-131">In the DBCOLUMNACCESS structure, if pData is NULL and cbMaxLen is 0, the call to IRow->GetColumns returns only the actual column length.</span></span> <span data-ttu-id="2d1ea-132">En este caso, se puede llamar a IRow->GetColumns de nuevo sobre la misma columna para recuperar los datos reales.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-132">In this case IRow->GetColumns can be called again on the same column to retrieve the actual data.</span></span> <span data-ttu-id="2d1ea-133">Este ejemplo no es compatible con IA64.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-133">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="2d1ea-134">Este ejemplo requiere la base de datos de ejemplo AdventureWorks que se puede descargar de la página principal que muestra [ejemplos y proyectos de la comunidad de Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384) .</span><span class="sxs-lookup"><span data-stu-id="2d1ea-134">This sample requires the AdventureWorks sample database, which you can download from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.</span></span>  
  
 <span data-ttu-id="2d1ea-135">La primera lista de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) crea una tabla usada por el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-135">The first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing creates a table used by the sample.</span></span>  
  
 <span data-ttu-id="2d1ea-136">Compile con ole32.lib oleaut32.lib y ejecute la segunda lista de código (C++).</span><span class="sxs-lookup"><span data-stu-id="2d1ea-136">Compile with ole32.lib oleaut32.lib and execute the second (C++) code listing.</span></span> <span data-ttu-id="2d1ea-137">Esta aplicación se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del equipo.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-137">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="2d1ea-138">En algunos sistemas operativos Windows, deberá cambiar (localhost) o (local) al nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d1ea-138">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="2d1ea-139">Para conectarse a una instancia con nombre, cambie la cadena de conexión de L"(local)" a L"(local)\\nombre", donde "nombre" es la instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-139">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="2d1ea-140">De forma predeterminada, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express se instala en una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-140">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="2d1ea-141">Asegúrese de que la variable de entorno INCLUDE incluye el directorio que contiene sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-141">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
 <span data-ttu-id="2d1ea-142">La tercera lista de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) elimina la tabla usada por el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2d1ea-142">The third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing deletes the table used by the sample.</span></span>  
  
```  
use AdventureWorks  
go  
  
if exists (select name from sysobjects where name = 'MyTable')  
     drop table MyTable  
go  
  
create table MyTable  
(  
     col1  int,  
     col2  varchar(50),  
     col3  char(50),  
     col4  datetime,  
     col5  float,  
     col6  money,  
     col7  sql_variant,  
     col8  binary(50),  
     col9  text,  
     col10 image  
)  
go  
insert into MyTable  
values  
(  
     10,  
     'abcdefghijklmnopqrstuvwxyz',  
     'ABCDEFGHIJKLMNOPQRSTUVWXYZ',  
     '11/1/1999 11:52 AM',  
     3.14,  
     99.95,  
     convert(nchar(50), N'AbCdEfGhIjKlMnOpQrStUvWxYz'),  
     0x123456789,  
     replicate('AAAAABBBBB', 500),  
     replicate(0x123456789, 500)  
)  
Go  
```  
  
```  
// compile with: ole32.lib oleaut32.lib  
#define DBINITCONSTANTS  
#define OLEDBVER 0x0250   // to include correct interfaces  
  
#include <stdio.h>  
#include <windows.h>  
#include <iostream>  
#include <oledb.h>  
#include <sqlncli.h>  
  
using namespace std;  
  
int InitializeAndEstablishConnection();  
HRESULT GetColumnSize(IRow* pUnkRow, ULONG iCol);  
ULONG PrintData(ULONG iCols, ULONG iStart, DBCOLUMNINFO* prgInfo, DBCOLUMNACCESS* prgColumns);  
HRESULT GetColumns(IRow* pUnkRow, ULONG iStart, ULONG iEnd);  
  
IDBInitialize*       pIDBInitialize     = NULL;  
IDBProperties*       pIDBProperties     = NULL;  
IDBCreateSession*    pIDBCreateSession  = NULL;  
IDBCreateCommand*    pIDBCreateCommand  = NULL;  
ICommandText*        pICommandText      = NULL;  
IRow   *             pIRow              = NULL;  
DBCOLUMNINFO*        pDBColumnInfo      = NULL;  
IAccessor*           pIAccessor         = NULL;  
DBPROP               InitProperties[4];  
DBPROPSET            rgInitPropSet[1];  
ULONG                i, j;  
HRESULT              hresult;  
DBROWCOUNT           cNumRows = 0;  
ULONG                lNumCols;  
WCHAR*               pStringsBuffer;  
DBBINDING*           pBindings;  
ULONG                ConsumerBufColOffset = 0;  
HACCESSOR            hAccessor;  
ULONG                lNumRowsRetrieved;  
HROW                 hRows[10];  
HROW*                pRows = &hRows[0];  
  
int main() {  
   ULONG iidx = 0;  
   WCHAR* wCmdString = OLESTR(" SELECT * FROM MyTable");  
  
   // Call a function to initialize and establish connection.   
   if (InitializeAndEstablishConnection() == -1) {  
      cout << "Failed to initialize and establish connection.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Create a session object.  
   if (FAILED(pIDBInitialize->QueryInterface (   
      IID_IDBCreateSession, (void**) &pIDBCreateSession))) {  
      cout << "Failed to obtain IDBCreateSession interface.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   if (FAILED(pIDBCreateSession->CreateSession( NULL, IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand))) {  
      cout << "pIDBCreateSession->CreateSession failed.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Access the ICommandText interface.  
   if (FAILED(pIDBCreateCommand->CreateCommand( NULL, IID_ICommandText, (IUnknown**) &pICommandText))) {  
      cout << "Failed to access ICommand interface.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Use SetCommandText() to specify the command text.  
   if (FAILED(pICommandText->SetCommandText(DBGUID_DBSQL, wCmdString))) {  
      cout << "Failed to set command text.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Fetch columns 1-5 and then 6-10 and display the contents  
   if (FAILED(hresult = pICommandText->Execute(NULL, IID_IRow, NULL, &cNumRows, (IUnknown **) &pIRow))) {  
      cout << "Failed to execute command.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   hresult = GetColumns(pIRow, 1, 5);  
   hresult = GetColumns(pIRow, 6, 10);  
  
   hresult = pIRow->Release();  
  
   // Execute the command.  
   if (FAILED(hresult = pICommandText->Execute(NULL, IID_IRow, NULL, &cNumRows, (IUnknown **) &pIRow))) {  
      cout << "Failed to execute command.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Get columns  
   for ( iidx = 1 ; iidx <= 10 ; iidx++ ) {  
      if (FAILED(hresult = GetColumnSize(pIRow, iidx))) {  
         cout << "Failed to get column size.\n";  
         // Insert your code for cleanup and error handling.     
         return -1;  
      }  
  
      hresult = GetColumns(pIRow, iidx, iidx);  
   }  
  
   pIRow->Release();  
  
   // Release memory.  
   pICommandText->Release();  
   pIDBCreateCommand->Release();  
   pIDBCreateSession->Release();  
  
   if (FAILED(pIDBInitialize->Uninitialize())) {  
      // Uninitialize not required, but fails if an interface has not been released.  Can be used for debugging.  
      cout << "Problem uninitializing.\n";  
   }  
  
   pIDBInitialize->Release();  
  
   // Release the COM library.  
   CoUninitialize();  
  
   return 0;  
};  
  
//--------------------------------------------------------------------  
BOOL InitColumn(DBCOLUMNACCESS* pCol, DBCOLUMNINFO* pInfo) {  
   // If text or image column is being read,in which case the max  possible length of a value is   
   // the column is hugh,we will limit that size to 512 bytes (for illustration purposes).  
   DBLENGTH ulSize = (pInfo->ulColumnSize < 0x7fffffff) ? pInfo->ulColumnSize : 512;  
  
   // Verify dta buffer is large enough.  
   if (pCol->cbMaxLen < (ulSize + 1)) {  
      if (pCol->pData) {  
         delete [] pCol->pData;  
         pCol->pData = NULL;  
      }  
  
      // Allocate data buffer  
      void * p = pCol->pData = new WCHAR[ulSize + 1];  
      if (!(p /* pCol->pData = new WCHAR[ulSize + 1] */ ))  
         return FALSE;  
  
      // set the max length of caller-initialized memory.  
      pCol->cbMaxLen = sizeof(WCHAR) * (ulSize + 1);  
  
      // In the above 2 steps, pData is pointing to memory (it is not NULL) and cbMaxLen has a value   
      // (not 0), so next call to IRow->GetData() will read the data from the column.  
   }  
  
   // Clear memory buffer  
   ZeroMemory((void*) pCol->pData, pCol->cbMaxLen);  
  
   // Set properties.  
   pCol->wType = DBTYPE_WSTR;  
   pCol->columnid = pInfo->columnid;  
   pCol->cbDataLen = 0;  
   pCol->dwStatus = 0;  
   pCol->dwReserved = 0;  
   pCol->bPrecision = 0;  
   pCol->bScale = 0;  
   return TRUE;  
}  
  
//--------------------------------------------------------------------  
HRESULT GetColumns(IRow* pUnkRow, ULONG iStart, ULONG iEnd) {  
// Start and end are same. Thus, get only one column.  
   HRESULT hr;  
   ULONG iidx;   // loop counter  
   DBORDINAL cColumns;   // Count of columns  
   ULONG cUserCols;   // Count of user columns  
  
   DBCOLUMNINFO* prgInfo;   // Column of info. array  
   OLECHAR* pColNames;   // Array of column names  
  
   DBCOLUMNACCESS* prgColumns;   // Ptr to column access structures array  
   DBCOLUMNINFO* pCurrInfo;  
   DBCOLUMNACCESS* pCurrCol;  
  
   IColumnsInfo* pIColumnsInfo = NULL;  
  
   // Initialize  
   cColumns = 0;  
   prgInfo = NULL;  
   pColNames = NULL;  
   prgColumns = NULL;  
  
   printf("Retrieving data\n");  
  
   // Get column info to build column access array  
   hr = pUnkRow->QueryInterface(IID_IColumnsInfo, (void**)&pIColumnsInfo);  
   if (FAILED(hr))  
      goto CLEANUP;  
   hr = pIColumnsInfo->GetColumnInfo(&cColumns, &prgInfo, &pColNames);  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   printf("In GetColumns(), Columns= %d\n", cColumns);  
  
   // Determine no. of columns to retrieve. Since iEnd and iStart is same, this is redundent step.    
   // cUserCols will always be 1.  
   cUserCols = iEnd - iStart + 1;   
  
   // Walk list of columns and setup a DBCOLUMNACCESS structure  
   if (!(prgColumns= new DBCOLUMNACCESS[cUserCols])) {   // cUserCols is only 1  
      hr = E_FAIL;  
      goto CLEANUP;  
   }  
  
   ZeroMemory((void*) prgColumns, sizeof(DBCOLUMNACCESS) * cUserCols);  
  
   for ( iidx = 0 ; iidx < cUserCols ; iidx++ ) {  
      pCurrInfo = prgInfo + iidx + iStart - 1;  
      pCurrCol = prgColumns + iidx;  
  
      // Here the values of DBCOLUMNACCESS elements is set (pData and cbMaxLen)Thus IRow->GetColumns()   
      // will return actual data.  
      if (InitColumn(pCurrCol, pCurrInfo) == FALSE)  
         goto CLEANUP;  
   }  
  
   hr = pUnkRow->GetColumns(cUserCols, prgColumns);   // cUserCols = 1  
   if (FAILED(hr))  
      printf("Error occured\n");  
  
   // Show data.  
   PrintData(cUserCols, iStart, prgInfo, prgColumns);  
  
CLEANUP:  
   if (pIColumnsInfo)  
      pIColumnsInfo->Release();  
   if (prgColumns)  
      delete [] prgColumns;  
  
   return hr;  
}  
  
// This function returns the actual width of the data in the column (not the columnwidth in   
// DBCOLUMNFO structure which is the width of the column)  
HRESULT GetColumnSize(IRow* pUnkRow, ULONG iCol) {  
   HRESULT        hr = NOERROR;  
   DBORDINAL      cColumns = 0;   // Count the columns  
   DBCOLUMNINFO*  prgInfo;   // Column info array  
   OLECHAR*       pColNames;  
   DBCOLUMNACCESS column;  
   DBCOLUMNINFO*  pCurrInfo;  
   IColumnsInfo*  pIColumnsInfo = NULL;  
  
   // Initialize  
   prgInfo = NULL;  
   pColNames = NULL;  
  
   printf("Checking column size\n");  
  
   // Get column info to build column access array  
   hr = pUnkRow->QueryInterface(IID_IColumnsInfo, (void**) &pIColumnsInfo);  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   hr = pIColumnsInfo->GetColumnInfo(&cColumns, &prgInfo, &pColNames);  
   if (FAILED(hr))  
      goto CLEANUP;  
   printf("Value of cColumns is %d\n", cColumns);  
  
   // Setup a DBCOLUMNACCESS structure: Here pData is set to NULL and cbMaxLen is set to 0. Thus   
   // IRow->GetColumns() returns only the actual column length in cbDataLen member of DBCOLUMNACCESS   
   // structure. In this case you can call IRow->GetColumns() again for the same  column to retrieve   
   // actual data in the second call.  
   ZeroMemory((void*) &column, sizeof(DBCOLUMNACCESS));  
   column.pData = NULL;  
  
   pCurrInfo = prgInfo + iCol - 1;  
  
   // Get the column id in DBCOLUMNACCESS structure. It is then used in GetColumn().  
   column.columnid = pCurrInfo->columnid;   
  
   printf("column.columnid value is %d\n", column.columnid);  
   // We know which column to get. The column.columnid gives the column no.  
   hr = pUnkRow->GetColumns(1, &column);   
   if (FAILED(hr))  
      printf("Errors occured\n");  
  
   // Show data  
   PrintData(1, iCol, prgInfo, &column);  
  
CLEANUP:  
   if (pIColumnsInfo)  
      pIColumnsInfo->Release();  
   return hr;  
}  
  
BOOL GetStatus(DWORD dwStatus, WCHAR* pwszStatus) {  
   switch (dwStatus) {  
   case DBSTATUS_S_OK:  
      wcscpy_s(pwszStatus, 255, L"DBSTATUS_S_OK");  
      break;  
   case DBSTATUS_E_UNAVAILABLE:  
      wcscpy_s(pwszStatus, 255, L"DBSTATUS_E_UNAVAILABLE");  
      break;  
   case DBSTATUS_S_TRUNCATED:  
      wcscpy_s(pwszStatus, 255, L"DBSTATUS_S_TRUNCATED");  
      break;  
   }  
   return TRUE;  
}  
  
ULONG PrintData(ULONG iCols, ULONG iStart, DBCOLUMNINFO* prgInfo, DBCOLUMNACCESS* prgColumns) {  
   WCHAR wszStatus[255];  
   DBCOLUMNINFO* pCurrInfo;  
   DBCOLUMNACCESS* pCurrCol;  
   ULONG iidx;  
  
   printf("No. Name       Status     Length  Max  Data\n");  
  
   for ( iidx = 0 ; iidx < iCols ; iidx++ ) {  
      pCurrInfo = prgInfo + iidx + iStart - 1;  
      pCurrCol = prgColumns + iidx;  
  
      GetStatus(pCurrCol->dwStatus, wszStatus);   
      // was the data successfully retrieved?  
      wprintf(L"%-3d %-*s %-20s %-3d %-3d %-20s\n", iStart+iidx,   
                                                    10,   
                                                    pCurrInfo->pwszName,   
                                                    wszStatus,  
                                                    pCurrCol->cbDataLen,  
                                                    pCurrCol->cbMaxLen,  
                                                    (WCHAR*) pCurrCol->pData);  
   }  
  
   wprintf(L"\n");  
   return iidx;  
}  
  
int InitializeAndEstablishConnection() {      
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQLNCLI provider.  
   hresult = CoCreateInstance(CLSID_SQLNCLI11,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDBInitialize,  
                              (void **) &pIDBInitialize);  
  
   if (FAILED(hresult)) {  
      printf("Failed to get IDBInitialize interface.\n");  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Initialize the property values needed to establish the connection.  
   for ( i = 0 ; i < 4 ; i++ )   
      VariantInit(&InitProperties[i].vValue);  
  
   // Server name.  
   InitProperties[0].dwPropertyID  = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt     = VT_BSTR;  
  
   InitProperties[0].vValue.bstrVal= SysAllocString(L"(local)");  
   InitProperties[0].dwOptions     = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid         = DB_NULLID;  
  
   // Database.  
   InitProperties[1].dwPropertyID  = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt     = VT_BSTR;  
   InitProperties[1].vValue.bstrVal= SysAllocString(L"AdventureWorks");  
   InitProperties[1].dwOptions     = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid         = DB_NULLID;  
  
   InitProperties[2].dwPropertyID  = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt     = VT_BSTR;  
   InitProperties[2].vValue.bstrVal= SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions     = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid         = DB_NULLID;  
  
   // Now that the properties are set, construct the DBPROPSET structure (rgInitPropSet). The DBPROPSET   
   // structure is used to pass an array of DBPROP structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet= DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties    = 4;  
   rgInitPropSet[0].rgProperties   = InitProperties;  
  
   // Set initialization properties.  
   hresult = pIDBInitialize->QueryInterface(IID_IDBProperties, (void **)&pIDBProperties);  
   if (FAILED(hresult)) {  
      cout << "Failed to get IDBProperties interface.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   hresult = pIDBProperties->SetProperties(1, rgInitPropSet);   
   if (FAILED(hresult)) {  
      cout << "Failed to set initialization properties.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   pIDBProperties->Release();  
  
   // Now establish the connection to the data source.  
   if (FAILED(pIDBInitialize->Initialize()))  
      cout << "Problem establishing connection to the data source.\n";  
  
   return 0;  
}  
```  
  
```  
use AdventureWorks  
go  
  
if exists (select name from sysobjects where name = 'MyTable')  
     drop table MyTable  
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d1ea-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d1ea-143">See Also</span></span>  
 [<span data-ttu-id="2d1ea-144">Temas de procedimientos de OLE DB</span><span class="sxs-lookup"><span data-stu-id="2d1ea-144">OLE DB How-to Topics</span></span>](ole-db-how-to-topics.md)  
  
  