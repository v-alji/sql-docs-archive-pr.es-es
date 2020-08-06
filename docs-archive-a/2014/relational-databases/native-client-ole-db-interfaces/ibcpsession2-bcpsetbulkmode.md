---
title: IBCPSession2::BCPSetBulkMode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BCPSetBulkMode function
ms.assetid: babba19f-e67b-450c-b0e6-523a0f9d23ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 9605ff9b8effde1b4a77ba0d8554c719a8a8d1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676493"
---
# <a name="ibcpsession2bcpsetbulkmode"></a><span data-ttu-id="5467c-102">IBCPSession2::BCPSetBulkMode</span><span class="sxs-lookup"><span data-stu-id="5467c-102">IBCPSession2::BCPSetBulkMode</span></span>
  <span data-ttu-id="5467c-103">IBCPSession2::BCPSetBulkMode proporciona una alternativa a [IBCPSession::BCPColFmt &#40;OLE DB&#41;](ibcpsession-bcpcolfmt-ole-db.md) para especificar el formato de columna.</span><span class="sxs-lookup"><span data-stu-id="5467c-103">IBCPSession2::BCPSetBulkMode provides an alternative to [IBCPSession::BCPColFmt &#40;OLE DB&#41;](ibcpsession-bcpcolfmt-ole-db.md) for specifying the column format.</span></span> <span data-ttu-id="5467c-104">A diferencia de IBCPSession::BCPColFmt, que establece atributos de formato de columna, IBCPSession2::BCPSetBulkMode establece todos los atributos.</span><span class="sxs-lookup"><span data-stu-id="5467c-104">Unlike IBCPSession::BCPColFmt, which sets individual column format attributes, IBCPSession2::BCPSetBulkMode sets all attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5467c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5467c-105">Syntax</span></span>  
  
```  
  
HRESULT BCPSetBulkMode (  
      int property,  
   void * pField,  
   int cbField,  
   void * pRow,  
   int cbRow  
);  
```  
  
## <a name="arguments"></a><span data-ttu-id="5467c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5467c-106">Arguments</span></span>  
 <span data-ttu-id="5467c-107">*property*</span><span class="sxs-lookup"><span data-stu-id="5467c-107">*property*</span></span>  
 <span data-ttu-id="5467c-108">Constante de tipo BYTE.</span><span class="sxs-lookup"><span data-stu-id="5467c-108">A constant of type BYTE.</span></span> <span data-ttu-id="5467c-109">Vea la tabla en la sección Comentarios para obtener una lista de las constantes.</span><span class="sxs-lookup"><span data-stu-id="5467c-109">See the table in the Remarks section for a list of the constants.</span></span>  
  
 <span data-ttu-id="5467c-110">*pField*</span><span class="sxs-lookup"><span data-stu-id="5467c-110">*pField*</span></span>  
 <span data-ttu-id="5467c-111">Puntero al valor de terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="5467c-111">The pointer to the field terminator value.</span></span>  
  
 <span data-ttu-id="5467c-112">cbField</span><span class="sxs-lookup"><span data-stu-id="5467c-112">cbField</span></span>  
 <span data-ttu-id="5467c-113">Longitud en bytes del valor de terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="5467c-113">The length in bytes of the field terminator value.</span></span>  
  
 <span data-ttu-id="5467c-114">pRow</span><span class="sxs-lookup"><span data-stu-id="5467c-114">pRow</span></span>  
 <span data-ttu-id="5467c-115">Puntero al valor de terminador de fila.</span><span class="sxs-lookup"><span data-stu-id="5467c-115">The pointer to the row terminator value.</span></span>  
  
 <span data-ttu-id="5467c-116">cbRow</span><span class="sxs-lookup"><span data-stu-id="5467c-116">cbRow</span></span>  
 <span data-ttu-id="5467c-117">Longitud en bytes del valor de terminador de fila.</span><span class="sxs-lookup"><span data-stu-id="5467c-117">The length in bytes of the row terminator value.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="5467c-118">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="5467c-118">Returns</span></span>  
 <span data-ttu-id="5467c-119">IBCPSession2::BCPSetBulkMode puede devolver uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="5467c-119">IBCPSession2::BCPSetBulkMode can return one of the following:</span></span>  
  
|||  
|-|-|  
|`S_OK`|<span data-ttu-id="5467c-120">El método se ha llevado a cabo de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="5467c-120">The method succeeded.</span></span>|  
|`E_FAIL`|<span data-ttu-id="5467c-121">Se ha producido un error específico del proveedor; para obtener más información, use la interfaz ISQLServerErrorInfo.</span><span class="sxs-lookup"><span data-stu-id="5467c-121">A provider specific error occurred, for detailed information use the ISQLServerErrorInfo interface.</span></span>|  
|`E_UNEXPECTED`|<span data-ttu-id="5467c-122">No se esperaba la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="5467c-122">The call to the method was unexpected.</span></span> <span data-ttu-id="5467c-123">Por ejemplo, `IBCPSession2::BCPInit` no se llamó al método antes de llamar a IBCPSession2:: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="5467c-123">For example, the `IBCPSession2::BCPInit` method was not called before calling IBCPSession2::BCPSetBulkMode.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="5467c-124">El argumento no era válido.</span><span class="sxs-lookup"><span data-stu-id="5467c-124">The argument was invalid.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="5467c-125">Error de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="5467c-125">Out of memory error.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5467c-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5467c-126">Remarks</span></span>  
 <span data-ttu-id="5467c-127">Se puede usar IBCPSession2::BCPSetBulkMode para crear una copia masiva fuera de una consulta o una tabla.</span><span class="sxs-lookup"><span data-stu-id="5467c-127">IBCPSession2::BCPSetBulkMode can be used to bulk copy out of either a query or a table.</span></span> <span data-ttu-id="5467c-128">Cuando IBCPSession2::BCPSetBulkMode se usa para la copia masiva de una instrucción de consulta, es necesario realizar antes una llamada a `IBCPSession::BCPControl(BCP_OPTIONS_HINTS, ...)` para especificar la instrucción de consulta.</span><span class="sxs-lookup"><span data-stu-id="5467c-128">When IBCPSession2::BCPSetBulkMode is used to bulk copy out of a query statement, it must be called before calling `IBCPSession::BCPControl(BCP_OPTIONS_HINTS, ...)` to specify the query statement.</span></span>  
  
 <span data-ttu-id="5467c-129">Debe evitarse combinar la sintaxis de llamada RPC con la sintaxis de consulta por lotes (`{rpc func};SELECT * from Tbl`, por ejemplo) en el texto del mismo comando,</span><span class="sxs-lookup"><span data-stu-id="5467c-129">You should avoid combining RPC call syntax with batch query syntax (`{rpc func};SELECT * from Tbl`, for example) in a single command text.</span></span>  <span data-ttu-id="5467c-130">porque haría que ICommandPrepare::Prepare devolviese un error y le impediría recuperar metadatos.</span><span class="sxs-lookup"><span data-stu-id="5467c-130">This will cause ICommandPrepare::Prepare to return an error and prevent you from retrieving metadata.</span></span> <span data-ttu-id="5467c-131">Utilice la sintaxis de ODBC CALL (`{call func}; SELECT * from Tbl`, por ejemplo) si necesita combinar la ejecución del procedimiento almacenado y la consulta por lotes en el texto del mismo comando.</span><span class="sxs-lookup"><span data-stu-id="5467c-131">Use ODBC CALL syntax (`{call func}; SELECT * from Tbl`, for example) if you need to combine stored procedure execution and batch query in a single command text.</span></span>  
  
 <span data-ttu-id="5467c-132">En la lista siguiente se enumeran las constantes del parámetro *property* .</span><span class="sxs-lookup"><span data-stu-id="5467c-132">The following table lists the constants for the *property* parameter.</span></span>  
  
|<span data-ttu-id="5467c-133">Propiedad</span><span class="sxs-lookup"><span data-stu-id="5467c-133">Property</span></span>|<span data-ttu-id="5467c-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="5467c-134">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="5467c-135">BCP_OUT_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="5467c-135">BCP_OUT_CHARACTER_MODE</span></span>|<span data-ttu-id="5467c-136">Especifica el modo de salida de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5467c-136">Specifies character output mode.</span></span><br /><br /> <span data-ttu-id="5467c-137">Corresponde a la opción-c en BCP.EXE y a IBCPSession:: BCPColFmt con la propiedad *eUserDataType* establecida en `BCP_TYPE_SQLCHARACTER` .</span><span class="sxs-lookup"><span data-stu-id="5467c-137">Corresponds to the -c option in BCP.EXE, and to IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLCHARACTER`.</span></span>|  
|<span data-ttu-id="5467c-138">BCP_OUT_WIDE_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="5467c-138">BCP_OUT_WIDE_CHARACTER_MODE</span></span>|<span data-ttu-id="5467c-139">Especifica el modo de salida de Unicode.</span><span class="sxs-lookup"><span data-stu-id="5467c-139">Specifies Unicode output mode.</span></span><br /><br /> <span data-ttu-id="5467c-140">Corresponde a la opción-w de BCP.EXE y IBCPSession:: BCPColFmt con la propiedad *eUserDataType* establecida en `BCP_TYPE_SQLNCHAR` .</span><span class="sxs-lookup"><span data-stu-id="5467c-140">Corresponds to the -w option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLNCHAR`.</span></span>|  
|<span data-ttu-id="5467c-141">BCP_OUT_NATIVE_TEXT_MODE</span><span class="sxs-lookup"><span data-stu-id="5467c-141">BCP_OUT_NATIVE_TEXT_MODE</span></span>|<span data-ttu-id="5467c-142">Especifica los tipos nativos para los tipos no de caracteres y Unicode para los tipos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5467c-142">Specifies native types for non-character types and Unicode for character types.</span></span><br /><br /> <span data-ttu-id="5467c-143">Corresponde a la opción-N de BCP.EXE y IBCPSession:: BCPColFmt con la propiedad *eUserDataType* establecida en `BCP_TYPE_SQLNCHAR` si el tipo de columna es una cadena o `BCP_TYPE_DEFAULT` no es una cadena.</span><span class="sxs-lookup"><span data-stu-id="5467c-143">Corresponds to the -N option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLNCHAR` if the column type is a string or `BCP_TYPE_DEFAULT` if not a string.</span></span>|  
|<span data-ttu-id="5467c-144">BCP_OUT_NATIVE_MODE</span><span class="sxs-lookup"><span data-stu-id="5467c-144">BCP_OUT_NATIVE_MODE</span></span>|<span data-ttu-id="5467c-145">Especifica los tipos de base de datos nativos.</span><span class="sxs-lookup"><span data-stu-id="5467c-145">Specifies native database types.</span></span><br /><br /> <span data-ttu-id="5467c-146">Corresponde a la opción-n de BCP.EXE y IBCPSession:: BCPColFmt con la propiedad *eUserDataType* establecida en `BCP_TYPE_DEFAULT` .</span><span class="sxs-lookup"><span data-stu-id="5467c-146">Corresponds to the -n option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_DEFAULT`.</span></span>|  
  
 <span data-ttu-id="5467c-147">Puede llamar a IBCPSession::BCPControl e IBCPSession2::BCPSetBulkMode para las opciones IBCPSession::BCPControl que no entran en conflicto con IBCPSession2::BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="5467c-147">You can call IBCPSession::BCPControl and IBCPSession2::BCPSetBulkMode for IBCPSession::BCPControl options that do not conflict with IBCPSession2::BCPSetBulkMode.</span></span> <span data-ttu-id="5467c-148">Por ejemplo, puede llamar a IBCPSession:: BCPControl con `BCP_OPTION_FIRST` y IBCPSession2:: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="5467c-148">For example, you can call IBCPSession::BCPControl with `BCP_OPTION_FIRST` and IBCPSession2::BCPSetBulkMode.</span></span>  
  
 <span data-ttu-id="5467c-149">No se puede llamar a IBCPSession:: BCPControl con `BCP_OPTION_TEXTFILE` y IBCPSession2:: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="5467c-149">You cannot call IBCPSession::BCPControl with `BCP_OPTION_TEXTFILE` and IBCPSession2::BCPSetBulkMode.</span></span>  
  
 <span data-ttu-id="5467c-150">Si intenta llamar a IBCPSession2::BCPSetBulkMode con una secuencia de llamadas a funciones que incluye IBCPSession::BCPColFmt, IBCPSession::BCPControl e IBCPSession::BCPReadFmt, una de las llamadas a funciones devolverá un error de secuencia.</span><span class="sxs-lookup"><span data-stu-id="5467c-150">If you attempt to call IBCPSession2::BCPSetBulkMode with a sequence of function calls that includes IBCPSession::BCPColFmt, IBCPSession::BCPControl, and IBCPSession::BCPReadFmt, one of the function calls will return a sequence error failure.</span></span> <span data-ttu-id="5467c-151">Si elige corregir el error, llame a IBCPSession::BCPInit para restablecer los valores de configuración y volver a empezar.</span><span class="sxs-lookup"><span data-stu-id="5467c-151">If you choose to correct the failure, call IBCPSession::BCPInit to reset the settings and start over.</span></span>  
  
 <span data-ttu-id="5467c-152">En la siguiente tabla se presentan algunos ejemplos de llamadas a función que producen un error de secuencia de función:</span><span class="sxs-lookup"><span data-stu-id="5467c-152">The following table presents some examples of function calls that result in a function sequence error:</span></span>  
  
 <span data-ttu-id="5467c-153">Secuencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="5467c-153">Call sequence</span></span>  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_IN);  
BCPSetBulkMode();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPSetBulkMode();  
BCPReadFmt();  
```  
  
```  
BCPInit(NULL, "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_HINTS, "select ...");  
BCPSetBulkMode();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPSetBulkMode();  
BCPColFmt();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPReadFmt();  
BCPColFmt();  
```  
  
```  
BCPInit(NULL, "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPSetBulkMode();  
BCPControl(BCP_OPTION_HINTS, "select ...");  
BCPReadFmt();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPColumns();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPSetColFmt();  
```  
  
## <a name="example"></a><span data-ttu-id="5467c-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5467c-154">Example</span></span>  
 <span data-ttu-id="5467c-155">En el siguiente ejemplo se crean cuatro archivos con valores distintos de IBCPSession2::BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="5467c-155">The following sample creates four files using different settings of IBCPSession2::BCPSetBulkMode.</span></span>  
  
```  
  
// compile with: sqlncli11.lib oleaut32.lib ole32.lib  
  
#include <stdio.h>  
#include "sqlncli.h"  
  
IDBInitialize*  g_pIDBInitialize = NULL;  
IBCPSession2 * g_pIBcpSession = NULL;  
class COLEDBPropSet : public DBPROPSET {  
public:  
   COLEDBPropSet() {  
      rgProperties = NULL;  
      cProperties = 0;  
   };  
   COLEDBPropSet(const GUID& guid) {  
      rgProperties = NULL;  
      cProperties = 0;  
      guidPropertySet = guid;  
   };  
   ~COLEDBPropSet() {  
      for ( ULONG i = 0 ; i < cProperties ; i++ )  
         VariantClear(&rgProperties[i].vValue);  
      CoTaskMemFree(rgProperties);  
   }  
   void SetGUID(const GUID& guid) {  
      guidPropertySet = guid;  
   };  
   bool AddProperty(DWORD dwPropertyID, bool bValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID = dwPropertyID;  
      rgProperties[cProperties].vValue.vt = VT_BOOL;  
      rgProperties[cProperties].vValue.boolVal = (bValue) ? VARIANT_TRUE : VARIANT_FALSE;  
      cProperties++;  
      return true;  
   };  
   bool AddProperty(DWORD dwPropertyID, long nValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID  = dwPropertyID;  
      rgProperties[cProperties].vValue.vt     = VT_I4;  
      rgProperties[cProperties].vValue.lVal   = nValue;  
      cProperties++;  
      return true;  
   };  
   bool AddProperty(DWORD dwPropertyID,LPCWSTR szValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID = dwPropertyID;  
      rgProperties[cProperties].vValue.vt = VT_BSTR;  
      rgProperties[cProperties].vValue.bstrVal = SysAllocString(szValue);  
      cProperties++;  
      return true;  
   };  
   bool Add() {  
      DBPROP* p = (DBPROP*)CoTaskMemRealloc(rgProperties, (cProperties + 1) * sizeof(DBPROP));  
      if (p != NULL) {  
         rgProperties = p;  
         rgProperties[cProperties].dwOptions = DBPROPOPTIONS_REQUIRED;  
         rgProperties[cProperties].colid = DB_NULLID;  
         rgProperties[cProperties].vValue.vt = VT_EMPTY;  
         return true;  
      }  
      else  
         return false;  
   };  
};  
  
void OLEDBCleanUp() {  
   if (g_pIDBInitialize) {  
      g_pIDBInitialize->Release();  
      g_pIDBInitialize = NULL;  
   }  
   if (g_pIBcpSession) {  
      g_pIBcpSession->Release();  
      g_pIBcpSession = NULL;  
   }  
}  
  
BOOL MakeOLEDBConnect(LPWSTR  pServer) {  
   BOOL ret = true;  
   IDBProperties * pIDBProperties = NULL;  
   IDBCreateSession * pIDBCreateSession = NULL;  
   COLEDBPropSet PropSet(DBPROPSET_DBINIT);  
   COLEDBPropSet BcpProperty(DBPROPSET_SQLSERVERDATASOURCE);  
   try {  
      HRESULT hr = CoInitializeEx(NULL,COINIT_MULTITHREADED);   
      hr = CoCreateInstance(SQLNCLI_CLSID, NULL, CLSCTX_INPROC_SERVER, IID_IDBInitialize, (LPVOID *)&g_pIDBInitialize);  
      if (FAILED(hr)) {  
         printf("CoCreateInstance failed\n");  
         return false;  
      }  
      PropSet.AddProperty(DBPROP_INIT_DATASOURCE, (LPWSTR)pServer);  
      PropSet.AddProperty(DBPROP_AUTH_INTEGRATED, L"SSPI");  
      hr = g_pIDBInitialize->QueryInterface(IID_IDBProperties, (void**) &pIDBProperties);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->QueryInterface(IID_IDBProperties...) failed\n");  
         throw false;  
      }  
      hr = pIDBProperties->SetProperties(1, &PropSet);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->SetProperties(...) failed\n");  
         throw false;  
      }  
      hr = g_pIDBInitialize->Initialize();  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->Initialize() failed\n");  
         throw false;  
      }  
      BcpProperty.AddProperty(SSPROP_ENABLEFASTLOAD, true);  
      BcpProperty.AddProperty(SSPROP_ENABLEBULKCOPY, true);  
      hr = pIDBProperties->SetProperties(1, &BcpProperty);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->SetProperties() for bcp failed\n");  
         throw false;  
      }  
      hr = g_pIDBInitialize->QueryInterface(IID_IDBCreateSession, (void**) &pIDBCreateSession);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->QueryInterface(IID_IDBCreateSession..) failed\n");  
         throw false;  
      }  
  
      hr = pIDBCreateSession->CreateSession(NULL, IID_IBCPSession2, (IUnknown**) &g_pIBcpSession);  
      if (FAILED(hr)) {  
         printf("g_pIDBCreateSession->CreateSession() failed\n");  
         throw false;  
      }  
   }  
   catch(...) {  
      ret = false;  
   }  
   if (pIDBProperties)  
      pIDBProperties->Release();  
   if (pIDBCreateSession)  
      pIDBCreateSession->Release();  
   return ret;  
}  
  
BOOL BCPSetBulkMode(LPWSTR pszServer, LPTSTR pszQureryOut, char BCPType, LPWSTR pszDataFile) {  
   HRESULThr;  
   if (!MakeOLEDBConnect(pszServer))  
      return false;  
   hr = g_pIBcpSession->BCPInit(NULL, pszDataFile, NULL, BCP_DIRECTION_OUT );   // bcp init for queryout  
   if (FAILED(hr)) {  
      printf("BCP init failed\n");  
      OLEDBCleanUp();  
      return false;  
   }  
   // setbulkmode  
   char ColTerm[] = "\t";  
   char RowTerm[] = "\r\n";  
   wchar_t wColTerm[] = L"\t";  
   wchar_t wRowTerm[] = L"\r\n";  
   BYTE * pColTerm = NULL;  
   int cbColTerm = NULL;  
   BYTE * pRowTerm = 0;  
   int cbRowTerm = 0;  
   int bulkmode = -1;  
  
   if(BCPType == 'c') {   // bcp -c  
      pColTerm = (BYTE*)ColTerm;  
      pRowTerm = (BYTE*)RowTerm;  
      cbColTerm = 1;  
      cbRowTerm = 2;  
      bulkmode = BCP_OUT_CHARACTER_MODE;  
   }  
   else  
      if(BCPType == 'w') {   // bcp -w  
         pColTerm = (BYTE*)wColTerm;  
         pRowTerm = (BYTE*)wRowTerm;  
         cbColTerm = 2;  
         cbRowTerm = 4;  
         bulkmode = BCP_OUT_WIDE_CHARACTER_MODE;  
      }  
      else  
         if (BCPType == 'n')   // bcp -n  
            bulkmode = BCP_OUT_NATIVE_MODE;  
         else  
            if (BCPType == 'N')   // bcp -n  
               bulkmode = BCP_OUT_NATIVE_TEXT_MODE;  
            else {  
               printf("unknown bcp mode\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            hr = g_pIBcpSession->BCPSetBulkMode(bulkmode, pColTerm, cbColTerm, pRowTerm, cbRowTerm);  
            if (FAILED(hr)) {  
               printf("BCPSetBulkMode failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
  
            // set queryout TSQL statement  
            hr = g_pIBcpSession->BCPControl(BCP_OPTION_HINTS, pszQureryOut);  
            if (FAILED(hr)) {  
               printf("BCPControl failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            // bcp copy  
            DBROWCOUNT nRowsInserted = 0;  
            hr = g_pIBcpSession->BCPExec(&nRowsInserted);  
            if (FAILED(hr)) {  
               printf("BCPExec failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            printf("bcp done\n");  
            OLEDBCleanUp();  
            return true;  
}  
  
int main() {  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -c test', 1,2") , 'c', L"bcpc.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -w test', 1,2") , 'w', L"bcpw.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -c test', 1,2") , 'n', L"bcpn.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -w test', 1,2") , 'N', L"bcp_N.dat");  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5467c-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5467c-156">See Also</span></span>  
 [<span data-ttu-id="5467c-157">IBCPSession2 &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5467c-157">IBCPSession2 &#40;OLE DB&#41;</span></span>](ibcpsession2-ole-db.md)  
  
  
