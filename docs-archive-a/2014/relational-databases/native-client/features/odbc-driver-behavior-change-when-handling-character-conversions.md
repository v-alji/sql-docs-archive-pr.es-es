---
title: Cambio de comportamiento del controlador ODBC al administrar las conversiones de caracteres | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 682a232a-bf89-4849-88a1-95b2fbac1467
author: rothja
ms.author: jroth
ms.openlocfilehash: 5334b4268559ba155a53b3be655d87f7867779df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745250"
---
# <a name="odbc-driver-behavior-change-when-handling-character-conversions"></a><span data-ttu-id="5e2b1-102">Cambio de comportamiento del controlador ODBC al administrar las conversiones de caracteres</span><span class="sxs-lookup"><span data-stu-id="5e2b1-102">ODBC Driver Behavior Change When Handling Character Conversions</span></span>
  <span data-ttu-id="5e2b1-103">El [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] controlador ODBC de Native Client (SQLNCLI11.dll) ha cambiado la forma de las conversiones de SQL_WCHAR \* (NCHAR/NVARCHAR/nvarchar (Max)) y SQL_CHAR \* (CHAR/VARCHAR/NARCHAR (Max)).</span><span class="sxs-lookup"><span data-stu-id="5e2b1-103">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC Driver (SQLNCLI11.dll) changed how it does of SQL_WCHAR\* (NCHAR/NVARCHAR/NVARCHAR(MAX)) and SQL_CHAR\* (CHAR/VARCHAR/NARCHAR(MAX)) conversions.</span></span> <span data-ttu-id="5e2b1-104">Las funciones ODBC, como SQLGetData, SQLBindCol y SQLBindParameter, devuelven (-4) SQL_NO_TOTAL como el parámetro indicador de longitud al utilizar el controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-104">ODBC functions, such as SQLGetData, SQLBindCol, SQLBindParameter, return (-4) SQL_NO_TOTAL as the length/indicator parameter when using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client ODBC driver.</span></span> <span data-ttu-id="5e2b1-105">Las versiones anteriores del controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client devolvían un valor de longitud, que puede ser incorrecto.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-105">Prior versions of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver returned a length value, which can be incorrect.</span></span>  
  
## <a name="sqlgetdata-behavior"></a><span data-ttu-id="5e2b1-106">Comportamiento de SQLGetData</span><span class="sxs-lookup"><span data-stu-id="5e2b1-106">SQLGetData Behavior</span></span>  
 <span data-ttu-id="5e2b1-107">Muchas funciones de Windows permiten especificar un tamaño de búfer de 0, siendo la longitud devuelta el tamaño de los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-107">Many Windows functions let you specify a buffer size of 0 and the returned length is the size of the returned data.</span></span> <span data-ttu-id="5e2b1-108">El patrón siguiente es frecuente para los programadores de Windows:</span><span class="sxs-lookup"><span data-stu-id="5e2b1-108">The following pattern is common for Windows programmers:</span></span>  
  
```  
int iSize = 0;  
BYTE * pBuffer = NULL;  
GetMyFavoriteAPI(pBuffer, &iSize);   // Returns needed size in iSize  
pBuffer = new BYTE[iSize];   // Allocate buffer   
GetMyFavoriteAPI(pBuffer, &iSize);   // Retrieve actual data  
```  
  
 <span data-ttu-id="5e2b1-109">Sin embargo, no se debe utilizar **SQLGetData** en este escenario.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-109">However, **SQLGetData** should not be used in this scenario.</span></span> <span data-ttu-id="5e2b1-110">No se debe utilizar el patrón siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e2b1-110">The following pattern should not be used:</span></span>  
  
```  
// bad  
int iSize = 0;  
WCHAR * pBuffer = NULL;  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)0x1, 0, &iSize);   // Get storage size needed  
pBuffer = new WCHAR[(iSize/sizeof(WCHAR)) + 1];   // Allocate buffer  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)pBuffer, iSize, &iSize);   // Retrieve data  
```  
  
 <span data-ttu-id="5e2b1-111">Solo se puede llamar a **SQLGetData** para recuperar fragmentos de datos reales.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-111">**SQLGetData** can only be called to retrieve chunks of actual data.</span></span> <span data-ttu-id="5e2b1-112">No se admite el uso de **SQLGetData** para obtener el tamaño de los datos.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-112">Using **SQLGetData** to get the size of data is not unsupported.</span></span>  
  
 <span data-ttu-id="5e2b1-113">A continuación se muestra el impacto del cambio de controlador cuando se utiliza el patrón incorrecto.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-113">The following shows the impact of the driver change when you use the incorrect pattern.</span></span> <span data-ttu-id="5e2b1-114">Esta aplicación realiza una consulta en una columna `varchar` y el enlace se especifica como Unicode (SQL_UNICODE/SQL_WCHAR):</span><span class="sxs-lookup"><span data-stu-id="5e2b1-114">This application queries a `varchar` column and binding as Unicode (SQL_UNICODE/SQL_WCHAR):</span></span>  
  
 <span data-ttu-id="5e2b1-115">Misma`select convert(varchar(36), '123')`</span><span class="sxs-lookup"><span data-stu-id="5e2b1-115">Query:  `select convert(varchar(36), '123')`</span></span>  
  
```  
SQLGetData(hstmt, SQL_WCHAR, ....., (SQLPOINTER*) 0x1, 0 , &iSize);   // Attempting to determine storage size needed  
```  
  
|<span data-ttu-id="5e2b1-116">Versión del controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="5e2b1-116">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="5e2b1-117">Resultado de indicador o de longitud</span><span class="sxs-lookup"><span data-stu-id="5e2b1-117">Length or Indicator Outcome</span></span>|<span data-ttu-id="5e2b1-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e2b1-118">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="5e2b1-119">Native Client o anterior</span><span class="sxs-lookup"><span data-stu-id="5e2b1-119">Native Client or earlier</span></span>|<span data-ttu-id="5e2b1-120">6</span><span class="sxs-lookup"><span data-stu-id="5e2b1-120">6</span></span>|<span data-ttu-id="5e2b1-121">El controlador suponía incorrectamente que la conversión de CHAR en WCHAR se podía conseguir como longitud \* 2.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-121">The driver incorrectly assumed that converting CHAR to WCHAR could be accomplished as length \* 2.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="5e2b1-122">Native Client (versión 11.0.2100.60) o posterior</span><span class="sxs-lookup"><span data-stu-id="5e2b1-122">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="5e2b1-123">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="5e2b1-123">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="5e2b1-124">El controlador ya no supone que la conversión de CHAR a WCHAR o WCHAR a CHAR es una acción (multiplicar) \* 2 o (dividir)/2.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-124">The driver no longer assumes that converting from CHAR to WCHAR or WCHAR to CHAR is a (multiply) \*2 or (divide)/2 action.</span></span><br /><br /> <span data-ttu-id="5e2b1-125">Al llamar a **SQLGetData** ya no se devuelve la longitud de la conversión esperada.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-125">Calling **SQLGetData** no longer returns the length of the expected conversion.</span></span> <span data-ttu-id="5e2b1-126">El controlador detecta la conversión a o desde CHAR y WCHAR y devuelve (-4) SQL_NO_TOTAL en lugar del comportamiento \*2 o /2, que podría ser incorrecto.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-126">The driver detects the conversion to or from CHAR and WCHAR and returns (-4) SQL_NO_TOTAL instead of \*2 or /2 behavior that could be incorrect.</span></span>|  
  
 <span data-ttu-id="5e2b1-127">Use **SQLGetData** para recuperar los fragmentos de los datos.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-127">Use **SQLGetData** to retrieve the chunks of the data.</span></span> <span data-ttu-id="5e2b1-128">(Se muestra el pseudocódigo:)</span><span class="sxs-lookup"><span data-stu-id="5e2b1-128">(Pseudo code shown:)</span></span>  
  
```  
while( (SQL_SUCCESS or SQL_SUCCESS_WITH_INFO) == SQLFetch(...) ) {  
   SQLNumCols(...iTotalCols...)  
   for(int iCol = 1; iCol < iTotalCols; iCol++) {  
      WCHAR* pBufOrig, pBuffer = new WCHAR[100];  
      SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get original chunk  
      while(NOT ALL DATA RETREIVED (SQL_NO_TOTAL, ...) ) {  
         pBuffer += 50;   // Advance buffer for data retrieved  
         // May need to realloc the buffer when you reach current size  
         SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get next chunk  
      }  
   }  
}  
```  
  
## <a name="sqlbindcol-behavior"></a><span data-ttu-id="5e2b1-129">Comportamiento de SQLBindCol</span><span class="sxs-lookup"><span data-stu-id="5e2b1-129">SQLBindCol Behavior</span></span>  
 <span data-ttu-id="5e2b1-130">Misma`select convert(varchar(36), '1234567890')`</span><span class="sxs-lookup"><span data-stu-id="5e2b1-130">Query:  `select convert(varchar(36), '1234567890')`</span></span>  
  
```  
SQLBindCol(... SQL_W_CHAR, ...)   // Only bound a buffer of WCHAR[4] - Expecting String Data Right Truncation behavior  
```  
  
|<span data-ttu-id="5e2b1-131">Versión del controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="5e2b1-131">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="5e2b1-132">Resultado de indicador o de longitud</span><span class="sxs-lookup"><span data-stu-id="5e2b1-132">Length or Indicator Outcome</span></span>|<span data-ttu-id="5e2b1-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e2b1-133">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="5e2b1-134">Native Client o anterior</span><span class="sxs-lookup"><span data-stu-id="5e2b1-134">Native Client or earlier</span></span>|<span data-ttu-id="5e2b1-135">20</span><span class="sxs-lookup"><span data-stu-id="5e2b1-135">20</span></span>|<span data-ttu-id="5e2b1-136">-   **SQLFetch** informa de que hay un truncamiento en el lado derecho de los datos.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-136">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="5e2b1-137">-Length es la longitud de los datos devueltos, no lo que se almacenó (se supone que la conversión de \* 2 CHAR a WCHAR puede ser incorrecta para los glifos).</span><span class="sxs-lookup"><span data-stu-id="5e2b1-137">-   Length is the length of the data returned, not what was stored (assumes \*2 CHAR to WCHAR conversion which can be incorrect for glyphs).</span></span><br /><span data-ttu-id="5e2b1-138">-Los datos almacenados en el búfer son 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-138">-   Data stored in buffer is 123\0.</span></span> <span data-ttu-id="5e2b1-139">Se garantiza que el búfer está terminado en NULL.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-139">Buffer is guaranteed to be NULL terminated.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="5e2b1-140">Native Client (versión 11.0.2100.60) o posterior</span><span class="sxs-lookup"><span data-stu-id="5e2b1-140">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="5e2b1-141">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="5e2b1-141">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="5e2b1-142">-   **SQLFetch** informa de que hay un truncamiento en el lado derecho de los datos.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-142">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="5e2b1-143">-Length indica-4 (SQL_NO_TOTAL) porque no se convirtió el resto de los datos.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-143">-   Length indicates -4 (SQL_NO_TOTAL) because the rest of the data was not converted.</span></span><br /><span data-ttu-id="5e2b1-144">-Los datos almacenados en el búfer son 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-144">-   Data stored in the buffer is 123\0.</span></span> <span data-ttu-id="5e2b1-145">- Se garantiza que el búfer está terminado en NULL.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-145">- Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="sqlbindparameter-output-parameter-behavior"></a><span data-ttu-id="5e2b1-146">SQLBindParameter (comportamiento del parámetro OUTPUT)</span><span class="sxs-lookup"><span data-stu-id="5e2b1-146">SQLBindParameter (OUTPUT Parameter Behavior)</span></span>  
 <span data-ttu-id="5e2b1-147">Misma`create procedure spTest @p1 varchar(max) OUTPUT`</span><span class="sxs-lookup"><span data-stu-id="5e2b1-147">Query:  `create procedure spTest @p1 varchar(max) OUTPUT`</span></span>  
  
 `select @p1 = replicate('B', 1234)`  
  
```  
SQLBindParameter(... SQL_W_CHAR, ...)   // Only bind up to first 64 characters  
```  
  
|<span data-ttu-id="5e2b1-148">Versión del controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="5e2b1-148">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="5e2b1-149">Resultado de indicador o de longitud</span><span class="sxs-lookup"><span data-stu-id="5e2b1-149">Length or Indicator Outcome</span></span>|<span data-ttu-id="5e2b1-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e2b1-150">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="5e2b1-151">Native Client o anterior</span><span class="sxs-lookup"><span data-stu-id="5e2b1-151">Native Client or earlier</span></span>|<span data-ttu-id="5e2b1-152">2468</span><span class="sxs-lookup"><span data-stu-id="5e2b1-152">2468</span></span>|<span data-ttu-id="5e2b1-153">-   **SQLFetch** no devuelve más datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-153">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="5e2b1-154">-   **SQLMoreResults** no devuelve más datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-154">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="5e2b1-155">-Length indica el tamaño de los datos devueltos del servidor, no almacenados en el búfer.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-155">-   Length indicates the size of the data returned from server, not stored in buffer.</span></span><br /><span data-ttu-id="5e2b1-156">-El búfer original contiene 63 bytes y un terminador NULL.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-156">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="5e2b1-157">Se garantiza que el búfer está terminado en NULL.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-157">Buffer is guaranteed to be NULL terminated.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="5e2b1-158">Native Client (versión 11.0.2100.60) o posterior</span><span class="sxs-lookup"><span data-stu-id="5e2b1-158">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="5e2b1-159">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="5e2b1-159">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="5e2b1-160">-   **SQLFetch** no devuelve más datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-160">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="5e2b1-161">-   **SQLMoreResults** no devuelve más datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-161">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="5e2b1-162">-Length indica (-4) SQL_NO_TOTAL porque no se convirtió el resto de los datos.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-162">-   Length indicates (-4) SQL_NO_TOTAL because the rest of the data was not converted.</span></span><br /><span data-ttu-id="5e2b1-163">-El búfer original contiene 63 bytes y un terminador NULL.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-163">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="5e2b1-164">Se garantiza que el búfer está terminado en NULL.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-164">Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="performing-char-and-wchar-conversions"></a><span data-ttu-id="5e2b1-165">Realizar conversiones CHAR y WCHAR</span><span class="sxs-lookup"><span data-stu-id="5e2b1-165">Performing CHAR and WCHAR Conversions</span></span>  
 <span data-ttu-id="5e2b1-166">El controlador ODBC de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ofrece varias maneras de realizar las conversiones CHAR y WCHAR.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-166">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC driver offers several ways to perform CHAR and WCHAR conversions.</span></span> <span data-ttu-id="5e2b1-167">La lógica es similar a la manipulación de blobs (varchar (Max), nvarchar (Max),...):</span><span class="sxs-lookup"><span data-stu-id="5e2b1-167">The logic is similar to manipulating blobs (varchar(max), nvarchar(max), ...):</span></span>  
  
-   <span data-ttu-id="5e2b1-168">Los datos se guardan o se truncan en el búfer especificado al enlazar con **SQLBindCol** o **SQLBindParameter**.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-168">Data is saved or truncated into the specified buffer when binding with **SQLBindCol** or **SQLBindParameter**.</span></span>  
  
-   <span data-ttu-id="5e2b1-169">Si no realiza el enlace, puede recuperar los datos en fragmentos mediante **SQLGetData** y **SQLParamData**.</span><span class="sxs-lookup"><span data-stu-id="5e2b1-169">If you do not bind, you can retrieve the data in chunks by using **SQLGetData** and **SQLParamData**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e2b1-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e2b1-170">See Also</span></span>  
 [<span data-ttu-id="5e2b1-171">Características de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5e2b1-171">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
