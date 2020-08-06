---
title: bcp_init | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_init
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_init function
ms.assetid: 6a25862c-7f31-4873-ab65-30f3abde89d2
author: rothja
ms.author: jroth
ms.openlocfilehash: 72d48b2a07e425e0863084c700c4de93d2776739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671053"
---
# <a name="bcp_init"></a><span data-ttu-id="b2659-102">bcp_init</span><span class="sxs-lookup"><span data-stu-id="b2659-102">bcp_init</span></span>
  <span data-ttu-id="b2659-103">Inicializa la operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b2659-103">Initializes the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2659-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2659-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_init (  
HDBC   
hdbc  
,  
LPCTSTR   
szTable  
,  
LPCTSTR   
szDataFile  
,  
LPCTSTR   
szErrorFile  
,  
INT   
eDirection  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2659-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b2659-105">Arguments</span></span>  
 <span data-ttu-id="b2659-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="b2659-106">*hdbc*</span></span>  
 <span data-ttu-id="b2659-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b2659-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="b2659-108">*szTable*</span><span class="sxs-lookup"><span data-stu-id="b2659-108">*szTable*</span></span>  
 <span data-ttu-id="b2659-109">Es el nombre de la tabla de base de datos en o de la que se va a copiar.</span><span class="sxs-lookup"><span data-stu-id="b2659-109">Is the name of the database table to be copied into or out of.</span></span> <span data-ttu-id="b2659-110">Este nombre también puede incluir el nombre de la base de datos o el nombre del propietario.</span><span class="sxs-lookup"><span data-stu-id="b2659-110">This name can also include the database name or the owner name.</span></span> <span data-ttu-id="b2659-111">Por ejemplo, **pubs. Gracie. titles**, **pubs.. titles**, **Gracie. titles**y **titles** son nombres de tabla válidos.</span><span class="sxs-lookup"><span data-stu-id="b2659-111">For example, **pubs.gracie.titles**, **pubs..titles**, **gracie.titles**, and **titles** are all legal table names.</span></span>  
  
 <span data-ttu-id="b2659-112">Si *eDirection* es DB_OUT, *szTable* también puede ser el nombre de una vista de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b2659-112">If *eDirection* is DB_OUT, *szTable* can also be the name of a database view.</span></span>  
  
 <span data-ttu-id="b2659-113">Si *eDirection* es DB_OUT y se especifica una instrucción SELECT mediante [bcp_control](bcp-control.md) antes de que se llame a [bcp_exec](bcp-exec.md) , **bcp_init**_szTable_ debe establecerse en NULL.</span><span class="sxs-lookup"><span data-stu-id="b2659-113">If *eDirection* is DB_OUT and a SELECT statement is specified using [bcp_control](bcp-control.md) before [bcp_exec](bcp-exec.md) is called, **bcp_init**_szTable_ must be set to NULL.</span></span>  
  
 <span data-ttu-id="b2659-114">*szDataFile*</span><span class="sxs-lookup"><span data-stu-id="b2659-114">*szDataFile*</span></span>  
 <span data-ttu-id="b2659-115">Es el nombre del archivo de usuario en o del que se va a copiar.</span><span class="sxs-lookup"><span data-stu-id="b2659-115">Is the name of the user file to be copied into or out of.</span></span> <span data-ttu-id="b2659-116">Si los datos se copian directamente de las variables mediante [bcp_sendrow](bcp-sendrow.md), establezca *szDataFile* en NULL.</span><span class="sxs-lookup"><span data-stu-id="b2659-116">If data is being copied directly from variables by using [bcp_sendrow](bcp-sendrow.md), set *szDataFile* to NULL.</span></span>  
  
 <span data-ttu-id="b2659-117">*szErrorFile*</span><span class="sxs-lookup"><span data-stu-id="b2659-117">*szErrorFile*</span></span>  
 <span data-ttu-id="b2659-118">Es el nombre del archivo de error que se va a rellenar con mensajes de progreso, mensajes de error y copias de filas que, por cualquier razón, no se puedan copiar de un archivo de usuario en una tabla.</span><span class="sxs-lookup"><span data-stu-id="b2659-118">Is the name of the error file to be filled with progress messages, error messages, and copies of any rows that, for any reason, could not be copied from a user file to a table.</span></span> <span data-ttu-id="b2659-119">Si se pasa NULL como *szErrorFile*, no se utiliza ningún archivo de error.</span><span class="sxs-lookup"><span data-stu-id="b2659-119">If NULL is passed as *szErrorFile*, no error file is used.</span></span>  
  
 <span data-ttu-id="b2659-120">*eDirection*</span><span class="sxs-lookup"><span data-stu-id="b2659-120">*eDirection*</span></span>  
 <span data-ttu-id="b2659-121">Es la dirección de la copia, DB_IN o DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="b2659-121">Is the direction of the copy, either DB_IN or DB_OUT.</span></span> <span data-ttu-id="b2659-122">DB_IN indica una copia de variables de programa o de un archivo de usuario en una tabla.</span><span class="sxs-lookup"><span data-stu-id="b2659-122">DB_IN indicates a copy from program variables or a user file to a table.</span></span> <span data-ttu-id="b2659-123">DB_OUT indica una copia de una tabla de base de datos en un archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="b2659-123">DB_OUT indicates a copy from a database table to a user file.</span></span> <span data-ttu-id="b2659-124">Se debe especificar un nombre de archivo de usuario con DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="b2659-124">You must specify a user file name with DB_OUT.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="b2659-125">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="b2659-125">Returns</span></span>  
 <span data-ttu-id="b2659-126">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="b2659-126">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2659-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b2659-127">Remarks</span></span>  
 <span data-ttu-id="b2659-128">Llame a **bcp_init** antes de llamar a cualquier otra función de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b2659-128">Call **bcp_init** before calling any other bulk-copy function.</span></span> <span data-ttu-id="b2659-129">**bcp_init** realiza las inicializaciones necesarias para una copia masiva de datos entre la estación de trabajo y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2659-129">**bcp_init** performs the necessary initializations for a bulk copy of data between the workstation and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b2659-130">Se debe proporcionar la función **bcp_init** con un identificador de conexión ODBC habilitado para su uso con funciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b2659-130">The **bcp_init** function must be provided with an ODBC connection handle enabled for use with bulk copy functions.</span></span> <span data-ttu-id="b2659-131">Para habilitar el identificador, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_BCP establecido en SQL_BCP_ON en un identificador de conexión asignado, pero no conectado.</span><span class="sxs-lookup"><span data-stu-id="b2659-131">To enable the handle, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_BCP set to SQL_BCP_ON on an allocated, but not connected, connection handle.</span></span> <span data-ttu-id="b2659-132">Intentar asignar el atributo en un identificador conectado produce un error.</span><span class="sxs-lookup"><span data-stu-id="b2659-132">Attempting to assign the attribute on a connected handle results in an error.</span></span>  
  
 <span data-ttu-id="b2659-133">Cuando se especifica un archivo de datos, **bcp_init** examina la estructura de la tabla de origen o de destino de la base de datos, no del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="b2659-133">When a data file is specified, **bcp_init** examines the structure of the database source or target table, not the data file.</span></span> <span data-ttu-id="b2659-134">**bcp_init** especifica los valores de formato de datos para el archivo de datos basándose en cada columna de la tabla, la vista o el conjunto de resultados de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b2659-134">**bcp_init** specifies data format values for the data file based on each column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="b2659-135">Esta especificación incluye el tipo de datos de cada columna, la presencia o ausencia de cadenas de bytes de un indicador de longitud o nulo y de terminador en los datos, y el ancho de los tipos de datos de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="b2659-135">This specification includes the data type of each column, the presence or absence of a length or null indicator and terminator byte strings in the data, and the width of fixed-length data types.</span></span> <span data-ttu-id="b2659-136">**bcp_init** establece estos valores de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2659-136">**bcp_init** sets these values as follows:</span></span>  
  
-   <span data-ttu-id="b2659-137">El tipo de datos especificado es el tipo de datos de la columna de la tabla de base de datos, la vista o el conjunto de resultados de una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="b2659-137">The data type specified is the data type of the column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="b2659-138">Los tipos de datos nativos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificados en sqlncli.h enumeran el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="b2659-138">The data type is enumerated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types specified in sqlncli.h.</span></span> <span data-ttu-id="b2659-139">Los propios datos están representados en el formato del equipo.</span><span class="sxs-lookup"><span data-stu-id="b2659-139">Data itself is represented in its computer form.</span></span> <span data-ttu-id="b2659-140">Es decir, los datos de una columna de tipo de datos **enteros** se representan mediante una secuencia de cuatro bytes que es grande o Little-Endian según el equipo que creó el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="b2659-140">That is, data from a column of **integer** data type is represented by a four-byte sequence that is big-or little-endian based on the computer that created the data file.</span></span>  
  
-   <span data-ttu-id="b2659-141">Si un tipo de datos de base de datos es de longitud fija, los datos del archivo de datos también serán de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="b2659-141">If a database data type is fixed in length, the data file data is also fixed in length.</span></span> <span data-ttu-id="b2659-142">Las funciones de copia masiva que procesan datos (por ejemplo, [bcp_exec](bcp-exec.md)) analizan las filas de datos, lo que espera que la longitud de los datos del archivo de datos sea idéntica a la longitud de los datos especificados en la tabla de base de datos, la vista o la lista de columnas Select.</span><span class="sxs-lookup"><span data-stu-id="b2659-142">Bulk-copy functions that process data (for example, [bcp_exec](bcp-exec.md)) parse data rows expecting the length of the data in the data file to be identical to the length of the data specified in the database table, view, or SELECT column list.</span></span> <span data-ttu-id="b2659-143">Por ejemplo, los datos de una columna de base de datos definida como **Char (13)** deben estar representados por 13 caracteres para cada fila de datos del archivo.</span><span class="sxs-lookup"><span data-stu-id="b2659-143">For example, data for a database column defined as **char(13)** must be represented by 13 characters for each row of data in the file.</span></span> <span data-ttu-id="b2659-144">Los datos de longitud fija pueden tener como prefijo un indicador nulo si la columna de base de datos permite valores nulos.</span><span class="sxs-lookup"><span data-stu-id="b2659-144">Fixed-length data can be prefixed with a null indicator if the database column allows null values.</span></span>  
  
-   <span data-ttu-id="b2659-145">Cuando se define la secuencia de bytes del terminador, la longitud de dicha secuencia se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="b2659-145">When terminator-byte sequence is defined, the length of the terminator-byte sequence is set to 0.</span></span>  
  
-   <span data-ttu-id="b2659-146">Cuando se copia en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el archivo de datos debe tener datos para cada columna de la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b2659-146">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data file must have data for each column in the database table.</span></span> <span data-ttu-id="b2659-147">Cuando se copia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], los datos de todas las columnas de la tabla de base de datos, la vista o el conjunto de resultados de la instrucción SELECT se copian en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="b2659-147">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data from all columns in the database table, view, or SELECT result set are copied to the data file.</span></span>  
  
-   <span data-ttu-id="b2659-148">Cuando se copia en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la posición ordinal de una columna en el archivo de datos debe ser idéntica a la posición ordinal de la columna en la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b2659-148">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the ordinal position of a column in the data file must be identical to the ordinal position of the column in the database table.</span></span> <span data-ttu-id="b2659-149">Al copiar desde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , **bcp_exec** coloca los datos en función de la posición ordinal de la columna en la tabla de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b2659-149">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp_exec** places data based on the ordinal position of the column in the database table.</span></span>  
  
-   <span data-ttu-id="b2659-150">Si un tipo de datos de la base de datos es de longitud variable (por ejemplo, **varbinary (22)**) o si una columna de base de datos puede contener valores NULL, los datos del archivo de datos van precedidos por un indicador de longitud/nulo.</span><span class="sxs-lookup"><span data-stu-id="b2659-150">If a database data type is variable in length (for example, **varbinary(22)**) or if a database column can contain null values, data in the data file is prefixed by a length/null indicator.</span></span> <span data-ttu-id="b2659-151">El ancho del indicador varía en función del tipo de datos y de la versión de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b2659-151">The width of the indicator varies based on the data type and version of bulk copy.</span></span>  
  
 <span data-ttu-id="b2659-152">Para cambiar los valores de formato de datos especificados para un archivo de datos, llame a [bcp_columns](bcp-columns.md) y [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="b2659-152">To change data format values specified for a data file, call [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
 <span data-ttu-id="b2659-153">Las copias masivas en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se pueden optimizar para tablas que no contienen índices estableciendo el modelo de recuperación de la base de datos en SIMPLE o BULK_LOGGED.</span><span class="sxs-lookup"><span data-stu-id="b2659-153">Bulk copies to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be optimized for tables that do not contain indexes by setting the database recovery model to SIMPLE or BULK_LOGGED.</span></span> <span data-ttu-id="b2659-154">Para obtener más información, consulte [requisitos previos para el registro mínimo en la importación en bloque](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) y [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2659-154">For more information, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) and [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="b2659-155">Si no se usa ningún archivo de datos, debe llamar a [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) para especificar el formato y la ubicación en memoria de los datos fsor cada columna y, a continuación, copiar las filas de datos en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [bcp_sendrow](bcp-sendrow.md)mediante.</span><span class="sxs-lookup"><span data-stu-id="b2659-155">If no data file is used, you must call [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) to specify the format and location in memory of the data fsor each column, then copy data rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2659-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2659-156">Example</span></span>  
 <span data-ttu-id="b2659-157">En este ejemplo se muestra cómo se usa la función ODBC bcp_init con un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="b2659-157">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
 <span data-ttu-id="b2659-158">Antes de compilar y ejecutar el código de C++, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2659-158">Before you compile and run the C++ code, you need to do the following:</span></span>  
  
-   <span data-ttu-id="b2659-159">Crear un origen de datos ODBC denominado Test.</span><span class="sxs-lookup"><span data-stu-id="b2659-159">Create an ODBC data source called Test.</span></span> <span data-ttu-id="b2659-160">Puede asociar este origen de datos a cualquier base de datos.</span><span class="sxs-lookup"><span data-stu-id="b2659-160">You can associate this data source with any database.</span></span>  
  
-   <span data-ttu-id="b2659-161">Ejecutar la consulta siguiente [!INCLUDE[tsql](../../includes/tsql-md.md)] en la base de datos:</span><span class="sxs-lookup"><span data-stu-id="b2659-161">Run the following [!INCLUDE[tsql](../../includes/tsql-md.md)] on the database:</span></span>  
  
    ```  
    CREATE TABLE BCPDate (cola int, colb datetime);  
    ```  
  
-   <span data-ttu-id="b2659-162">En el directorio donde ejecutará la aplicación, agregue un archivo con el nombre Bcpfmt.fmt y agregue esto al archivo:</span><span class="sxs-lookup"><span data-stu-id="b2659-162">In the directory where you will run the application, add a file called Bcpfmt.fmt, and add this to the file:</span></span>  
  
    ```  
    8.0  
    2  
    1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
    2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
    ```  
  
-   <span data-ttu-id="b2659-163">En el directorio donde ejecutará la aplicación, agregue un archivo con el nombre Bcpodbc.bcp y agregue esto al archivo:</span><span class="sxs-lookup"><span data-stu-id="b2659-163">In the directory where you will run the application, add a file called Bcpodbc.bcp, and add this to the file:</span></span>  
  
    ```  
    1  
    2  
    ```  
  
 <span data-ttu-id="b2659-164">Ahora puede compilar y ejecutar el código de C++.</span><span class="sxs-lookup"><span data-stu-id="b2659-164">Now you are ready to compile and run the C++ code.</span></span>  
  
```  
// compile with: odbc32.lib sqlncli11.lib  
#include <stdio.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;   
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
   SDWORD cRows;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"Test", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2659-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2659-165">See Also</span></span>  
 [<span data-ttu-id="b2659-166">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="b2659-166">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
