---
title: Conversión de la copia masiva de DB-Library a ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- converting DB-Library to ODBC bulk copy
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], DB-Library bulk copy
- ODBC, bulk copy operations
- DB-Library bulk copy
ms.assetid: 0bc15bdb-f19f-4537-ac6c-f249f42cf07f
author: rothja
ms.author: jroth
ms.openlocfilehash: 866900606e582f08695fd4695a1098f34fb2b426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675343"
---
# <a name="converting-from-db-library-to-odbc-bulk-copy"></a><span data-ttu-id="54ee3-102">Convertir un programa de copia masiva de DB-Library a ODBC</span><span class="sxs-lookup"><span data-stu-id="54ee3-102">Converting from DB-Library to ODBC Bulk Copy</span></span>
  <span data-ttu-id="54ee3-103">Convertir un programa de copia masiva de DB-Library a ODBC es fácil porque las funciones de copia masiva que admite el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client son similares a las funciones de copia masiva de DB-Library, con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="54ee3-103">Converting a DB-Library bulk copy program to ODBC is easy because the bulk copy functions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver are similar to the DB-Library bulk copy functions, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="54ee3-104">Las aplicaciones DB-Library pasan un puntero a una estructura DBPROCESS como primer parámetro de las funciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="54ee3-104">DB-Library applications pass a pointer to a DBPROCESS structure as the first parameter of bulk copy functions.</span></span> <span data-ttu-id="54ee3-105">En las aplicaciones ODBC, el puntero a DBPROCESS se reemplaza por un identificador de conexión ODBC.</span><span class="sxs-lookup"><span data-stu-id="54ee3-105">In ODBC applications, the DBPROCESS pointer is replaced with an ODBC connection handle.</span></span>  
  
-   <span data-ttu-id="54ee3-106">Las aplicaciones de DB-Library llaman a **BCP_SETL** antes de conectarse para habilitar las operaciones de copia masiva en DBPROCESS.</span><span class="sxs-lookup"><span data-stu-id="54ee3-106">DB-Library applications call **BCP_SETL** before connecting to enable bulk copy operations on a DBPROCESS.</span></span> <span data-ttu-id="54ee3-107">En su lugar, las aplicaciones ODBC llaman a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) antes de conectarse para habilitar las operaciones masivas en un identificador de conexión:</span><span class="sxs-lookup"><span data-stu-id="54ee3-107">ODBC applications instead call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) before connecting to enable bulk operations on a connection handle:</span></span>  
  
    ```  
    SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP,  
        (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
    ```  
  
-   <span data-ttu-id="54ee3-108">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client no es compatible con los controladores de mensajes y errores de DB-Library; debe llamar a **SQLGetDiagRec** para obtener los errores y mensajes generados por las funciones de copia masiva de ODBC.</span><span class="sxs-lookup"><span data-stu-id="54ee3-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support DB-Library message and error handlers; you must call **SQLGetDiagRec** to get errors and messages raised by the ODBC bulk copy functions.</span></span> <span data-ttu-id="54ee3-109">Las versiones ODBC de las funciones de copia masiva devuelven los códigos de retorno de copia masiva estándar, es decir, SUCCEED o FAILED, no códigos de retorno de estilo ODBC, como SQL_SUCCESS o SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="54ee3-109">The ODBC versions of bulk copy functions return the standard bulk copy return codes of SUCCEED or FAILED, not ODBC-style return codes, such as SQL_SUCCESS or SQL_ERROR.</span></span>  
  
-   <span data-ttu-id="54ee3-110">Los valores especificados para el parámetro*varlen* de DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)se interpretan de forma distinta que el parámetro_cbData_ de ODBC **bcp_bind**.</span><span class="sxs-lookup"><span data-stu-id="54ee3-110">The values specified for the DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*varlen* parameter are interpreted differently than the ODBC **bcp_bind**_cbData_ parameter.</span></span>  
  
    |<span data-ttu-id="54ee3-111">Condición indicada</span><span class="sxs-lookup"><span data-stu-id="54ee3-111">Condition indicated</span></span>|<span data-ttu-id="54ee3-112">Valor de *varlen* de DB-Library</span><span class="sxs-lookup"><span data-stu-id="54ee3-112">DB-Library *varlen* value</span></span>|<span data-ttu-id="54ee3-113">Valor *cbData* de ODBC</span><span class="sxs-lookup"><span data-stu-id="54ee3-113">ODBC *cbData* value</span></span>|  
    |-------------------------|--------------------------------|-------------------------|  
    |<span data-ttu-id="54ee3-114">Se suministraron valores NULL</span><span class="sxs-lookup"><span data-stu-id="54ee3-114">Null values supplied</span></span>|<span data-ttu-id="54ee3-115">0</span><span class="sxs-lookup"><span data-stu-id="54ee3-115">0</span></span>|<span data-ttu-id="54ee3-116">-1 (SQL_NULL_DATA)</span><span class="sxs-lookup"><span data-stu-id="54ee3-116">-1 (SQL_NULL_DATA)</span></span>|  
    |<span data-ttu-id="54ee3-117">Se suministraron datos variables</span><span class="sxs-lookup"><span data-stu-id="54ee3-117">Variable data supplied</span></span>|<span data-ttu-id="54ee3-118">-1</span><span class="sxs-lookup"><span data-stu-id="54ee3-118">-1</span></span>|<span data-ttu-id="54ee3-119">-10 (SQL_VARLEN_DATA)</span><span class="sxs-lookup"><span data-stu-id="54ee3-119">-10 (SQL_VARLEN_DATA)</span></span>|  
    |<span data-ttu-id="54ee3-120">Cadena binaria o carácter de longitud cero</span><span class="sxs-lookup"><span data-stu-id="54ee3-120">Zero length character or binary string</span></span>|<span data-ttu-id="54ee3-121">N/D</span><span class="sxs-lookup"><span data-stu-id="54ee3-121">NA</span></span>|<span data-ttu-id="54ee3-122">0</span><span class="sxs-lookup"><span data-stu-id="54ee3-122">0</span></span>|  
  
     <span data-ttu-id="54ee3-123">En DB-Library, un valor *varlen* de-1 indica que se están suministrando datos de longitud variable, que en el *cbData* de ODBC se interpreta para indicar que solo se proporcionan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="54ee3-123">In DB-Library, a *varlen* value of -1 indicates that variable length data is being supplied, which in the ODBC *cbData* is interpreted to mean that only NULL values are being supplied.</span></span> <span data-ttu-id="54ee3-124">Cambie cualquier especificación de *varlen* de DB-Library de-1 a SQL_VARLEN_DATA y cualquier especificación de *varlen* de 0 a SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="54ee3-124">Change any DB-Library *varlen* specifications of -1 to SQL_VARLEN_DATA and any *varlen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="54ee3-125">La_ \_ intercalación de archivo_ \*\* \_ Colfmt BCP\**de DB-Library y ODBC [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData\* tienen el mismo problema que los parámetros **bcp_bind**_varlen_ y *cbData* indicados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="54ee3-125">The DB-Library **bcp\_colfmt**_file\_collen_ and the ODBC [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData* have the same issue as the **bcp_bind**_varlen_ and *cbData* parameters noted above.</span></span> <span data-ttu-id="54ee3-126">Cambie cualquier especificación de *file_collen* de DB-Library de-1 a SQL_VARLEN_DATA y cualquier especificación de *file_collen* de 0 a SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="54ee3-126">Change any DB-Library *file_collen* specifications of -1 to SQL_VARLEN_DATA and any *file_collen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="54ee3-127">El parámetro *iValue* de la función [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) de ODBC es un puntero void.</span><span class="sxs-lookup"><span data-stu-id="54ee3-127">The *iValue* parameter of the ODBC [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) function is a void pointer.</span></span> <span data-ttu-id="54ee3-128">En DB-Library, *iValue* era un entero.</span><span class="sxs-lookup"><span data-stu-id="54ee3-128">In DB-Library, *iValue* was an integer.</span></span> <span data-ttu-id="54ee3-129">Convierta los valores de *iValue* de ODBC a void \*.</span><span class="sxs-lookup"><span data-stu-id="54ee3-129">Cast the values for the ODBC *iValue* to void \*.</span></span>  
  
-   <span data-ttu-id="54ee3-130">La opción **BCP_CONTROL** BCPMAXERRS especifica el número de filas individuales que pueden tener errores antes de que se produzca un error en una operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="54ee3-130">The **bcp_control** option BCPMAXERRS specifies how many individual rows can have errors before a bulk copy operation fails.</span></span> <span data-ttu-id="54ee3-131">El valor predeterminado de BCPMAXERRS es 0 (error en el primer error) en la versión de DB-Library de **bcp_control** y 10 en la versión de ODBC.</span><span class="sxs-lookup"><span data-stu-id="54ee3-131">The default for BCPMAXERRS is 0 (fail on first error) in the DB-Library version of **bcp_control** and 10 in the ODBC version.</span></span> <span data-ttu-id="54ee3-132">Las aplicaciones de DB-Library que dependen del valor predeterminado de 0 para finalizar una operación de copia masiva deben cambiarse para llamar a la **BCP_CONTROL** ODBC para establecer BCPMAXERRS en 0.</span><span class="sxs-lookup"><span data-stu-id="54ee3-132">DB-Library applications that depend on the default of 0 to terminate a bulk copy operation must be changed to call the ODBC **bcp_control** to set BCPMAXERRS to 0.</span></span>  
  
-   <span data-ttu-id="54ee3-133">La función **bcp_control** de ODBC admite las siguientes opciones no admitidas por la versión DB-Library de **bcp_control**:</span><span class="sxs-lookup"><span data-stu-id="54ee3-133">The ODBC **bcp_control** function supports the following options not supported by the DB-Library version of **bcp_control**:</span></span>  
  
    -   <span data-ttu-id="54ee3-134">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="54ee3-134">BCPODBC</span></span>  
  
         <span data-ttu-id="54ee3-135">Cuando se establece en TRUE, especifica que los valores **DateTime** y **smalldatetime** guardados en formato de caracteres tendrán el prefijo y el sufijo de la secuencia de escape de la marca de tiempo de ODBC.</span><span class="sxs-lookup"><span data-stu-id="54ee3-135">When set to TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will have the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="54ee3-136">Esto solo se aplica a las operaciones BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="54ee3-136">This only applies to BCP_OUT operations.</span></span>  
  
         <span data-ttu-id="54ee3-137">Con BCPODBC establecido en FALSE, un valor **DateTime** convertido en una cadena de caracteres se muestra como:</span><span class="sxs-lookup"><span data-stu-id="54ee3-137">With BCPODBC set to FALSE, a **datetime** value converted to a character string is output as:</span></span>  
  
        ```  
        1997-01-01 00:00:00.000  
        ```  
  
         <span data-ttu-id="54ee3-138">Con BCPODBC establecido en TRUE, el mismo valor **DateTime** se genera como:</span><span class="sxs-lookup"><span data-stu-id="54ee3-138">With BCPODBC set to TRUE, the same **datetime** value is output as:</span></span>  
  
        ```  
        {ts '1997-01-01 00:00:00.000' }  
        ```  
  
    -   <span data-ttu-id="54ee3-139">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="54ee3-139">BCPKEEPIDENTITY</span></span>  
  
         <span data-ttu-id="54ee3-140">Cuando se establece en TRUE, especifica que las funciones de copia masiva deben insertar valores de datos suministrados para las columnas con restricciones de identidad.</span><span class="sxs-lookup"><span data-stu-id="54ee3-140">When set to TRUE, specifies that bulk copy functions insert data values supplied for columns with identity constraints.</span></span> <span data-ttu-id="54ee3-141">Si no se establece, se generan nuevos valores de identidad para las filas insertadas.</span><span class="sxs-lookup"><span data-stu-id="54ee3-141">If this is not set, new identity values are generated for the inserted rows.</span></span>  
  
    -   <span data-ttu-id="54ee3-142">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="54ee3-142">BCPHINTS</span></span>  
  
         <span data-ttu-id="54ee3-143">Especifica diversas optimizaciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="54ee3-143">Specifies various bulk copy optimizations.</span></span> <span data-ttu-id="54ee3-144">Esta opción no puede usarse en la versión 6.5 ni en versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54ee3-144">This option cannot be used on 6.5 or earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="54ee3-145">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="54ee3-145">BCPFILECP</span></span>  
  
         <span data-ttu-id="54ee3-146">Especifica la página de códigos del archivo de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="54ee3-146">Specifies the code page of the bulk copy file.</span></span>  
  
    -   <span data-ttu-id="54ee3-147">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="54ee3-147">BCPUNICODEFILE</span></span>  
  
         <span data-ttu-id="54ee3-148">Especifica que un archivo de copia masiva en modo de carácter es un archivo Unicode.</span><span class="sxs-lookup"><span data-stu-id="54ee3-148">Specifies that a character mode bulk copy file is a Unicode file.</span></span>  
  
-   <span data-ttu-id="54ee3-149">La función **bcp_colfmt** de ODBC no admite el indicador de *File_Type* de SQLCHAR porque entra en conflicto con la definición de tipo SQLCHAR de ODBC.</span><span class="sxs-lookup"><span data-stu-id="54ee3-149">The ODBC **bcp_colfmt** function does not support the *file_type* indicator of SQLCHAR because it conflicts with the ODBC SQLCHAR typedef.</span></span> <span data-ttu-id="54ee3-150">En su lugar, use SQLCHARACTER para **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="54ee3-150">Use SQLCHARACTER instead for **bcp_colfmt**.</span></span>  
  
-   <span data-ttu-id="54ee3-151">En las versiones ODBC de las funciones de copia masiva, el formato para trabajar con valores **DateTime** y **smalldatetime** en cadenas de caracteres es el formato ODBC de AAAA-MM-DD HH: mm: SS. SSS; los valores **smalldatetime** usan el formato ODBC de AAAA-MM-DD HH: mm: SS.</span><span class="sxs-lookup"><span data-stu-id="54ee3-151">In the ODBC versions of bulk copy functions, the format for working with **datetime** and **smalldatetime** values in character strings is the ODBC format of yyyy-mm-dd hh:mm:ss.sss; **smalldatetime** values use the ODBC format of yyyy-mm-dd hh:mm:ss.</span></span>  
  
     <span data-ttu-id="54ee3-152">Las versiones de DB-Library de las funciones de copia masiva aceptan valores **DateTime** y **smalldatetime** en cadenas de caracteres mediante varios formatos:</span><span class="sxs-lookup"><span data-stu-id="54ee3-152">The DB-Library versions of the bulk copy functions accept **datetime** and **smalldatetime** values in character strings using several formats:</span></span>  
  
    -   <span data-ttu-id="54ee3-153">El formato predeterminado es *MMM DD AAAA HH: mmxx* , donde *XX* es AM o PM.</span><span class="sxs-lookup"><span data-stu-id="54ee3-153">The default format is *mmm dd yyyy hh:mmxx* where *xx* is either AM or PM.</span></span>  
  
    -   <span data-ttu-id="54ee3-154">cadenas de caracteres **DateTime** y **smalldatetime** en cualquier formato admitido por la función **dbconvert** de DB-Library.</span><span class="sxs-lookup"><span data-stu-id="54ee3-154">**datetime** and **smalldatetime** character strings in any format supported by the DB-Library **dbconvert** function.</span></span>  
  
    -   <span data-ttu-id="54ee3-155">Cuando se activa la casilla **Usar configuración internacional** en la pestaña **Opciones** de DB-Library de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herramienta de red de cliente, las funciones de copia masiva de DB-Library también aceptan fechas en el formato de fecha regional definido para la configuración regional del registro del equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="54ee3-155">When the **Use international settings** box is checked on the DB-Library **Options** tab of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility, the DB-Library bulk copy functions also accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
     <span data-ttu-id="54ee3-156">Las funciones de copia masiva de DB-Library no aceptan los formatos **DateTime** y **smalldatetime** de ODBC.</span><span class="sxs-lookup"><span data-stu-id="54ee3-156">The DB-Library bulk copy functions do not accept the ODBC **datetime** and **smalldatetime** formats.</span></span>  
  
     <span data-ttu-id="54ee3-157">Si el atributo SQL_SOPT_SS_REGIONALIZE de la instrucción está establecido en SQL_RE_ON, las funciones de copia masiva de ODBC aceptan fechas en el formato de fecha regional definido para la configuración regional del Registro del equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="54ee3-157">If the SQL_SOPT_SS_REGIONALIZE statement attribute is set to SQL_RE_ON, the ODBC bulk copy functions accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
-   <span data-ttu-id="54ee3-158">Al generar valores de **moneda** en formato de caracteres, las funciones de copia masiva de ODBC proporcionan cuatro dígitos de precisión y sin separadores de coma; Las versiones de DB-Library solo proporcionan dos dígitos de precisión e incluyen los separadores de comas.</span><span class="sxs-lookup"><span data-stu-id="54ee3-158">When outputting **money** values in character format, ODBC bulk copy functions supply four digits of precision and no comma separators; DB-Library versions only supply two digits of precision and include the comma separators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ee3-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54ee3-159">See Also</span></span>  
 <span data-ttu-id="54ee3-160">[Realizar operaciones de copia masiva &#40;ODBC&#41;](performing-bulk-copy-operations-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="54ee3-160">[Performing Bulk Copy Operations &#40;ODBC&#41;](performing-bulk-copy-operations-odbc.md) </span></span>  
 [<span data-ttu-id="54ee3-161">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="54ee3-161">Bulk Copy Functions</span></span>](../native-client-odbc-extensions-bulk-copy-functions/sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
