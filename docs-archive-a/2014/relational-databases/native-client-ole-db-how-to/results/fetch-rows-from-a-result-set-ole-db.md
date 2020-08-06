---
title: Cómo capturar filas de un conjunto de resultados (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rows [OLE DB]
ms.assetid: 8e9916a5-61e1-468e-8a5c-1ab8b5110737
author: rothja
ms.author: jroth
ms.openlocfilehash: 920c6c826391beb6a910dceb0c69ca7128abe757
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744691"
---
# <a name="fetch-rows-from-a-result-set-ole-db"></a><span data-ttu-id="49c50-102">Cómo capturar filas de un conjunto de resultados (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="49c50-102">Fetch Rows from a Result Set (OLE DB)</span></span>
  <span data-ttu-id="49c50-103">En este ejemplo se muestra cómo capturar filas de un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="49c50-103">This sample shows how to fetch rows from a result set.</span></span> <span data-ttu-id="49c50-104">Este ejemplo no es compatible con IA64.</span><span class="sxs-lookup"><span data-stu-id="49c50-104">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="49c50-105">Este ejemplo requiere la base de datos de ejemplo AdventureWorks que se puede descargar de la página principal que muestra [ejemplos y proyectos de la comunidad de Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384) .</span><span class="sxs-lookup"><span data-stu-id="49c50-105">This sample requires the AdventureWorks sample database, which you can download from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="49c50-106">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="49c50-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="49c50-107">Si la autenticación de Windows no está disponible, solicite a los usuarios que escriban sus credenciales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="49c50-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="49c50-108">No guarde las credenciales en un archivo.</span><span class="sxs-lookup"><span data-stu-id="49c50-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="49c50-109">Si debe conservar las credenciales, debe cifrarlas con la [API Crypto de Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="49c50-109">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49c50-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49c50-110">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="49c50-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="49c50-111">Description</span></span>  
 <span data-ttu-id="49c50-112">Compile con ole32.lib oleaut32.lib y ejecute la siguiente lista de código C++.</span><span class="sxs-lookup"><span data-stu-id="49c50-112">Compile with ole32.lib oleaut32.lib and execute the following C++ code listing.</span></span> <span data-ttu-id="49c50-113">Esta aplicación se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] del equipo.</span><span class="sxs-lookup"><span data-stu-id="49c50-113">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="49c50-114">En algunos sistemas operativos Windows, deberá cambiar (localhost) o (local) al nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49c50-114">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="49c50-115">Para conectarse a una instancia con nombre, cambie la cadena de conexión de L"(local)" a L"(local)\\nombre", donde "nombre" es la instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="49c50-115">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="49c50-116">De forma predeterminada, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Express se instala en una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="49c50-116">By default, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="49c50-117">Asegúrese de que la variable de entorno INCLUDE incluye el directorio que contiene sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="49c50-117">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
### <a name="code"></a><span data-ttu-id="49c50-118">Código</span><span class="sxs-lookup"><span data-stu-id="49c50-118">Code</span></span>  
  
```  
// compile with: ole32.lib oleaut32.lib  
int InitializeAndEstablishConnection();  
int ProcessResultSet();  
  
#define UNICODE  
#define _UNICODE  
#define DBINITCONSTANTS  
#define INITGUID  
#define OLEDBVER 0x0250   // to include correct interfaces  
  
#include <stdio.h>  
#include <tchar.h>  
#include <stddef.h>  
#include <windows.h>  
#include <iostream>  
#include <oledb.h>  
#include <sqlncli.h>  
#include <msdadc.h>   // for IDataConvert  
#include <msdaguid.h>   // for IDataConvert  
  
using namespace std;  
  
IDBInitialize* pIDBInitialize = NULL;  
IDBProperties* pIDBProperties = NULL;  
IDBCreateSession* pIDBCreateSession = NULL;  
IDBCreateCommand* pIDBCreateCommand = NULL;  
ICommandText* pICommandText = NULL;  
IRowset* pIRowset = NULL;  
IColumnsInfo* pIColumnsInfo = NULL;  
  
DBCOLUMNINFO* pDBColumnInfo = NULL;  
IAccessor* pIAccessor =  NULL;  
DBPROP InitProperties[4];  
DBPROPSET rgInitPropSet[1];  
  
ULONG i, j;  
HRESULT hr;  
DBROWCOUNT cNumRows = 0;  
DBORDINAL lNumCols;  
WCHAR* pStringsBuffer;  
DBBINDING* pBindings;  
DBLENGTH ConsumerBufColOffset = 0;  
HACCESSOR hAccessor;  
DBCOUNTITEM lNumRowsRetrieved;  
HROW hRows[10];  
HROW* pRows = &hRows[0];  
  
int main() {  
   // The command to execute.  
   WCHAR* wCmdString = OLESTR("SELECT StandardCost, ListPrice FROM Production.Product WHERE ListPrice > 14.00");  
  
   // Call a function to initialize and establish connection.   
   if (InitializeAndEstablishConnection() == -1) {  
      // Handle error.  
      cout << "Failed to initialize and connect to the server.\n";  
      return -1;  
   }  
  
   // Create a session object.  
   if (FAILED(pIDBInitialize->QueryInterface( IID_IDBCreateSession,  
      (void**) &pIDBCreateSession))) {  
         cout << "Failed to obtain IDBCreateSession interface.\n";  
         // Handle error.  
         return -1;  
   }  
  
   if (FAILED(pIDBCreateSession->CreateSession( NULL,   
      IID_IDBCreateCommand,   
      (IUnknown**) &pIDBCreateCommand))) {  
         cout << "pIDBCreateSession->CreateSession failed.\n";  
         // Handle error.  
         return -1;  
   }  
  
   // Access the ICommandText interface.  
   if (FAILED(pIDBCreateCommand->CreateCommand( NULL,   
      IID_ICommandText,   
      (IUnknown**) &pICommandText))) {  
         cout << "Failed to access ICommand interface.\n";  
         // Handle error.  
         return -1;  
   }  
  
   // Use SetCommandText() to specify the command text.  
   if (FAILED(pICommandText->SetCommandText(DBGUID_DBSQL, wCmdString))) {  
      cout << "Failed to set command text.\n";  
      // Handle error.  
      return -1;  
   }  
  
   // Execute the command.  
   if (FAILED(hr = pICommandText->Execute( NULL,   
      IID_IRowset,   
      NULL,   
      &cNumRows,   
      (IUnknown **) &pIRowset))) {  
         cout << "Failed to execute command.\n";  
         // Handle error.  
         return -1;  
   }  
  
   // Process the result set.  
   ProcessResultSet();   
  
   pIRowset->Release();  
  
   // Free up memory.  
   pICommandText->Release();  
   pIDBCreateCommand->Release();  
   pIDBCreateSession->Release();  
  
   if (FAILED(pIDBInitialize->Uninitialize())) {  
      // Uninitialize is not required, but it fails if an interface  
      // has not been released.  This can be used for debugging.  
      cout << "Problem uninitializing.\n";  
   }  
  
   pIDBInitialize->Release();  
   CoUninitialize();  
};  
  
int InitializeAndEstablishConnection() {      
   CoInitialize(NULL);  
  
   // Obtain access to the SQLNCLI provider.  
   hr = CoCreateInstance( CLSID_SQLNCLI11,  
      NULL,  
      CLSCTX_INPROC_SERVER,  
      IID_IDBInitialize,  
      (void **) &pIDBInitialize);  
  
   if (FAILED(hr)) {  
      printf("Failed to get IDBInitialize interface.\n");  
      // Handle errors here.  
      return -1;  
   }  
  
   // Initialize the property values needed to establish the connection.  
   for ( i = 0 ; i < 4 ; i++ )  
      VariantInit(&InitProperties[i].vValue);  
  
   // Server name.  
   InitProperties[0].dwPropertyID = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt = VT_BSTR;  
  
   InitProperties[0].vValue.bstrVal= SysAllocString(L"(local)");  
   InitProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid = DB_NULLID;  
  
   // Database.  
   InitProperties[1].dwPropertyID = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt = VT_BSTR;  
   InitProperties[1].vValue.bstrVal = SysAllocString(L"AdventureWorks");  
   InitProperties[1].dwOptions = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid = DB_NULLID;  
  
   InitProperties[2].dwPropertyID = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt = VT_BSTR;  
   InitProperties[2].vValue.bstrVal = SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid = DB_NULLID;  
  
   // Properties are set, now construct the DBPROPSET structure (rgInitPropSet) used to pass   
   // an array of DBPROP structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties = 4;  
   rgInitPropSet[0].rgProperties = InitProperties;  
  
   // Set initialization properties.  
   hr = pIDBInitialize->QueryInterface(IID_IDBProperties, (void **)&pIDBProperties);  
   if (FAILED(hr)) {  
      cout << "Failed to get IDBProperties interface.\n";  
      // Handle errors here.  
      return -1;  
   }  
  
   hr = pIDBProperties->SetProperties(1, rgInitPropSet);   
   if (FAILED(hr)) {  
      cout << "Failed to set initialization properties.\n";  
      // Handle errors here.  
      return -1;  
   }  
  
   pIDBProperties->Release();  
  
   // Now establish the connection to the data source.  
   if (FAILED(pIDBInitialize->Initialize())) {  
      cout << "Problem in establishing connection to the data"  
         "source.\n";  
      // Handle errors here.  
      return -1;  
   }  
   return 0;  
}  
  
// Retrieve and display data resulting from a query.  
int ProcessResultSet() {  
   // Obtain access to the IColumnInfo interface, from the Rowset object.  
   hr = pIRowset->QueryInterface(IID_IColumnsInfo, (void **)&pIColumnsInfo);  
   if (FAILED(hr)) {  
      cout << "Failed to get IColumnsInfo interface.\n";  
      // Handle errors here.  
      return -1;  
   }   
  
   // Retrieve the column information.  
   pIColumnsInfo->GetColumnInfo(&lNumCols, &pDBColumnInfo, &pStringsBuffer);  
  
   // Free the column information interface.  
   pIColumnsInfo->Release();  
  
   // Create a DBBINDING array.  
   DBBINDING * p = (pBindings = new DBBINDING[lNumCols]);  
   if (!(p /* pBindings = new DBBINDING[lNumCols] */ ))  
      return -1;  
  
   // Using the ColumnInfo structure, fill out the pBindings array.  
   for ( j = 0 ; j < lNumCols ; j++ ) {  
      pBindings[j].iOrdinal = j+1;  
      pBindings[j].obValue = ConsumerBufColOffset;  
      pBindings[j].pTypeInfo = NULL;  
      pBindings[j].pObject = NULL;  
      pBindings[j].pBindExt = NULL;  
      pBindings[j].dwPart = DBPART_VALUE;  
      pBindings[j].dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
      pBindings[j].eParamIO = DBPARAMIO_NOTPARAM;  
      pBindings[j].cbMaxLen = (pDBColumnInfo[j].wType == DBTYPE_WSTR) ? pDBColumnInfo[j].ulColumnSize * 2 : pDBColumnInfo[j].ulColumnSize;  
      pBindings[j].dwFlags = 0;  
      pBindings[j].wType = pDBColumnInfo[j].wType;  
      pBindings[j].bPrecision = pDBColumnInfo[j].bPrecision;  
      pBindings[j].bScale = pDBColumnInfo[j].bScale;  
  
      // Compute the next buffer offset.  
      ConsumerBufColOffset =   
         ConsumerBufColOffset + pBindings[j].cbMaxLen;  
   };  
  
   // Get the IAccessor interface.  
   hr = pIRowset->QueryInterface(IID_IAccessor, (void **) &pIAccessor);  
   if (FAILED(hr)) {  
      cout << "Failed to obtain IAccessor interface.\n";  
      // Handle errors here.  
      return -1;  
   }  
  
   // Create an accessor from the set of bindings (pBindings).  
   pIAccessor->CreateAccessor(DBACCESSOR_ROWDATA, lNumCols, pBindings, 0, &hAccessor, NULL);  
  
   // Print column names.  
   for ( j = 0 ; j < lNumCols ; j++ )  
      printf("%-40S", pDBColumnInfo[j].pwszName);  
  
   printf("\n");   // new line after the column names  
  
   // Get a set of 10 rows.  
   pIRowset->GetNextRows( NULL, 0, 10, &lNumRowsRetrieved, &pRows);  
  
   // Allocate space for the row buffer.  
   BYTE * pBuffer = new BYTE[ConsumerBufColOffset];  
   if (!(pBuffer /* = new BYTE[ConsumerBufColOffset] */ )) {  
      // Free up all allocated memory.  
      pIAccessor->ReleaseAccessor(hAccessor, NULL);  
      pIAccessor->Release();  
      delete [] pBindings;  
  
      return 0;  
   }  
  
   // Create an instance of the data conversion library to convert DBTYPE_CY to string for display  
   IDataConvert* pIDataConvert;  
   CoCreateInstance(CLSID_OLEDB_CONVERSIONLIBRARY,  
      NULL,  
      CLSCTX_INPROC_SERVER,  
      IID_IDataConvert,  
      (void**)&pIDataConvert);  
  
   // variables used in DataConvert  
   DBLENGTH cbDstLength;  
   DBSTATUS dbsStatus;  
   char strCurrency0[25];  
   char strCurrency1[25];  
  
   // Display the rows.  
   while ( lNumRowsRetrieved > 0 ) {  
      // For each row, print the column data.  
      for ( j = 0 ; j < lNumRowsRetrieved ; j++ ) {  
         // Clear the buffer.  
         memset(pBuffer, 0, ConsumerBufColOffset);  
  
         // Get the row data values.  
         pIRowset->GetData(hRows[j], hAccessor, pBuffer);  
  
         // Convert DBTYPE_CY values to string   
         pIDataConvert->DataConvert(DBTYPE_CY,   // wSrcType  
            DBTYPE_STR,   // wDstType  
            sizeof(LARGE_INTEGER),   // cbSrcLength   
            &cbDstLength,   // pcbDstLength  
            &pBuffer[pBindings[0].obValue],   // pSrc  
            strCurrency0,   // pDst  
            sizeof(strCurrency0),   //cbDstMaxLength  
            DBSTATUS_S_OK,   // dbsSrcStatus  
            &dbsStatus,   // pdbsStatus  
            0,   // bPrecision (used for DBTYPE_NUMERIC only)  
            0,   // bScale (used for DBTYPE_NUMERIC only)  
            DBDATACONVERT_DEFAULT);   // dwFlags  
  
         pIDataConvert->DataConvert(DBTYPE_CY,   // wSrcType  
            DBTYPE_STR,   // wDstType  
            sizeof(LARGE_INTEGER),   // cbSrcLength   
            &cbDstLength,   // pcbDstLength  
            &pBuffer[pBindings[1].obValue],   // pSrc  
            strCurrency1,   // pDst  
            sizeof(strCurrency1),   // cbDstMaxLength  
            DBSTATUS_S_OK,   // dbsSrcStatus  
            &dbsStatus,   // pdbsStatus  
            0,   // bPrecision (used for DBTYPE_NUMERIC only)  
            0,   // bScale (used for DBTYPE_NUMERIC only)  
            DBDATACONVERT_DEFAULT); // dwFlags  
  
         // Print cost and price values.  
         printf("%-40s%s\n", strCurrency0, strCurrency1); //sparra  
      };  
  
      // Release the rows retrieved.  
      pIRowset->ReleaseRows(lNumRowsRetrieved, hRows, NULL, NULL, NULL);  
  
      // Get the next set of 10 rows.  
      pIRowset->GetNextRows(NULL, 0, 10, &lNumRowsRetrieved, &pRows);  
   }  
  
   // Free up all allocated memory.  
   delete [] pBuffer;  
   pIAccessor->ReleaseAccessor(hAccessor, NULL);  
   pIAccessor->Release();  
   delete [] pBindings;  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="49c50-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49c50-119">See Also</span></span>  
 [<span data-ttu-id="49c50-120">Temas de procedimientos para procesar resultados &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="49c50-120">Processing Results How-to Topics &#40;OLE DB&#41;</span></span>](processing-results-how-to-topics-ole-db.md)  
  
  