---
title: Compatibilidad con tipos de datos para mejoras de fecha y hora de OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB], data type support
- OLE DB, date/time improvements
ms.assetid: d40e3fd6-9057-4371-8236-95cef300603e
author: rothja
ms.author: jroth
ms.openlocfilehash: 834583fdec63a8f613e623c239f9c3a1c9398950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748749"
---
# <a name="data-type-support-for-ole-db-date-and-time-improvements"></a><span data-ttu-id="95eba-102">Compatibilidad con tipos de datos para mejoras de fecha y hora de OLE DB</span><span class="sxs-lookup"><span data-stu-id="95eba-102">Data Type Support for OLE DB Date and Time Improvements</span></span>
  <span data-ttu-id="95eba-103">En este tema se proporciona información sobre los tipos OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) que admiten tipos de datos de fecha y hora [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95eba-103">This topic provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date/time data types.</span></span>  
  
## <a name="data-type-mapping-in-rowsets-and-parameters"></a><span data-ttu-id="95eba-104">Asignar tipos de datos en conjuntos de filas y parámetros</span><span class="sxs-lookup"><span data-stu-id="95eba-104">Data Type Mapping in Rowsets and Parameters</span></span>  
 <span data-ttu-id="95eba-105">OLE DB proporciona dos nuevos tipos de datos para admitir los nuevos tipos de servidor: DBTYPE_DBTIME2 y DBTYPE_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="95eba-105">OLE DB provides two new data types to support the new server types: DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET.</span></span> <span data-ttu-id="95eba-106">La tabla siguiente muestra la asignación completa de tipo de servidor:</span><span class="sxs-lookup"><span data-stu-id="95eba-106">The following table shows the complete server type mapping:</span></span>  
  
|<span data-ttu-id="95eba-107">Tipo de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95eba-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="95eba-108">Tipo de datos de OLE DB</span><span class="sxs-lookup"><span data-stu-id="95eba-108">OLE DB data type</span></span>|<span data-ttu-id="95eba-109">Value</span><span class="sxs-lookup"><span data-stu-id="95eba-109">Value</span></span>|  
|-----------------------------------------|----------------------|-----------|  
|<span data-ttu-id="95eba-110">datetime</span><span class="sxs-lookup"><span data-stu-id="95eba-110">datetime</span></span>|<span data-ttu-id="95eba-111">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="95eba-111">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="95eba-112">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="95eba-112">135 (oledb.h)</span></span>|  
|<span data-ttu-id="95eba-113">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="95eba-113">smalldatetime</span></span>|<span data-ttu-id="95eba-114">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="95eba-114">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="95eba-115">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="95eba-115">135 (oledb.h)</span></span>|  
|<span data-ttu-id="95eba-116">date</span><span class="sxs-lookup"><span data-stu-id="95eba-116">date</span></span>|<span data-ttu-id="95eba-117">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="95eba-117">DBTYPE_DBDATE</span></span>|<span data-ttu-id="95eba-118">133 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="95eba-118">133 (oledb.h)</span></span>|  
|<span data-ttu-id="95eba-119">time</span><span class="sxs-lookup"><span data-stu-id="95eba-119">time</span></span>|<span data-ttu-id="95eba-120">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="95eba-120">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="95eba-121">145 (SQLNCLI. h)</span><span class="sxs-lookup"><span data-stu-id="95eba-121">145 (sqlncli.h)</span></span>|  
|<span data-ttu-id="95eba-122">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="95eba-122">datetimeoffset</span></span>|<span data-ttu-id="95eba-123">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="95eba-123">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="95eba-124">146 (SQLNCLI. h)</span><span class="sxs-lookup"><span data-stu-id="95eba-124">146 (sqlncli.h)</span></span>|  
|<span data-ttu-id="95eba-125">datetime2</span><span class="sxs-lookup"><span data-stu-id="95eba-125">datetime2</span></span>|<span data-ttu-id="95eba-126">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="95eba-126">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="95eba-127">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="95eba-127">135 (oledb.h)</span></span>|  
  
## <a name="data-formats-strings-and-literals"></a><span data-ttu-id="95eba-128">Formatos de datos: Cadenas y literales</span><span class="sxs-lookup"><span data-stu-id="95eba-128">Data Formats: Strings and Literals</span></span>  
  
|<span data-ttu-id="95eba-129">Tipo de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95eba-129">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="95eba-130">Tipo de datos de OLE DB</span><span class="sxs-lookup"><span data-stu-id="95eba-130">OLE DB data type</span></span>|<span data-ttu-id="95eba-131">Formato de cadena para conversiones de cliente</span><span class="sxs-lookup"><span data-stu-id="95eba-131">String format for client conversions</span></span>|  
|-----------------------------------------|----------------------|------------------------------------------|  
|<span data-ttu-id="95eba-132">datetime</span><span class="sxs-lookup"><span data-stu-id="95eba-132">datetime</span></span>|<span data-ttu-id="95eba-133">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="95eba-133">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="95eba-134">'aaaa-mm-dd hh:mm:ss[.999]'</span><span class="sxs-lookup"><span data-stu-id="95eba-134">'yyyy-mm-dd hh:mm:ss[.999]'</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="95eba-135">admite hasta tres dígitos de la fracción de segundo para Datetime.</span><span class="sxs-lookup"><span data-stu-id="95eba-135">supports up to three fractional second digits for Datetime.</span></span>|  
|<span data-ttu-id="95eba-136">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="95eba-136">smalldatetime</span></span>|<span data-ttu-id="95eba-137">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="95eba-137">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="95eba-138">'aaaa-mm-dd hh:mm:ss'</span><span class="sxs-lookup"><span data-stu-id="95eba-138">'yyyy-mm-dd hh:mm:ss'</span></span><br /><br /> <span data-ttu-id="95eba-139">Este tipo de datos tiene una precisión de un minuto.</span><span class="sxs-lookup"><span data-stu-id="95eba-139">This data type has an accuracy of one minute.</span></span> <span data-ttu-id="95eba-140">El componente de segundos será cero en salida y será redondeado por el servidor al producir los resultados.</span><span class="sxs-lookup"><span data-stu-id="95eba-140">The seconds component will be zero on output and will be rounded by the server on input.</span></span>|  
|<span data-ttu-id="95eba-141">date</span><span class="sxs-lookup"><span data-stu-id="95eba-141">date</span></span>|<span data-ttu-id="95eba-142">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="95eba-142">DBTYPE_DBDATE</span></span>|<span data-ttu-id="95eba-143">'aaaa-mm-dd'</span><span class="sxs-lookup"><span data-stu-id="95eba-143">'yyyy-mm-dd'</span></span>|  
|<span data-ttu-id="95eba-144">time</span><span class="sxs-lookup"><span data-stu-id="95eba-144">time</span></span>|<span data-ttu-id="95eba-145">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="95eba-145">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="95eba-146">'hh:mm:ss[.9999999]'</span><span class="sxs-lookup"><span data-stu-id="95eba-146">'hh:mm:ss[.9999999]'</span></span><br /><br /> <span data-ttu-id="95eba-147">Las fracciones de segundo se pueden especificar si se desea utilizando hasta siete dígitos.</span><span class="sxs-lookup"><span data-stu-id="95eba-147">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="95eba-148">datetime2</span><span class="sxs-lookup"><span data-stu-id="95eba-148">datetime2</span></span>|<span data-ttu-id="95eba-149">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="95eba-149">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="95eba-150">'aaaa-mm-dd hh:mm:ss[.fffffff]'</span><span class="sxs-lookup"><span data-stu-id="95eba-150">'yyyy-mm-dd hh:mm:ss[.fffffff]'</span></span><br /><br /> <span data-ttu-id="95eba-151">Las fracciones de segundo se pueden especificar si se desea utilizando hasta siete dígitos.</span><span class="sxs-lookup"><span data-stu-id="95eba-151">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="95eba-152">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="95eba-152">datetimeoffset</span></span>|<span data-ttu-id="95eba-153">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="95eba-153">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="95eba-154">'aaaa-mm-dd hh:mm:ss[.fffffff] +/-hh:mm'</span><span class="sxs-lookup"><span data-stu-id="95eba-154">'yyyy-mm-dd hh:mm:ss[.fffffff] +/-hh:mm'</span></span><br /><br /> <span data-ttu-id="95eba-155">Las fracciones de segundo se pueden especificar si se desea utilizando hasta siete dígitos.</span><span class="sxs-lookup"><span data-stu-id="95eba-155">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
  
 <span data-ttu-id="95eba-156">No hay ningún cambio en las secuencias de escape para los literales de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="95eba-156">There are no changes to the escape sequences for date/time literals.</span></span>  
  
 <span data-ttu-id="95eba-157">Las fracciones de segundo de los resultados utilizan un punto (.), en lugar de dos puntos (:).</span><span class="sxs-lookup"><span data-stu-id="95eba-157">Fractional seconds in results use a dot (.) rather than a colon (:).</span></span>  
  
 <span data-ttu-id="95eba-158">Los valores de cadena devueltos a las aplicaciones siempre tendrán la misma longitud para una columna determinada.</span><span class="sxs-lookup"><span data-stu-id="95eba-158">String values returned to applications will always be the same length for a given column.</span></span> <span data-ttu-id="95eba-159">Los componentes de año, mes, día, hora, minuto y segundo se rellenarán con ceros a la izquierda hasta su ancho máximo.</span><span class="sxs-lookup"><span data-stu-id="95eba-159">Year, month, day, hour, minute, and second components will be padded with leading zeros to their maximum width.</span></span> <span data-ttu-id="95eba-160">Habrá exactamente un espacio entre la fecha y la hora, y exactamente un espacio entre la hora y el ajuste de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="95eba-160">There will be exactly one space between date and time and exactly one space between the time and timezone offset.</span></span> <span data-ttu-id="95eba-161">Un ajuste de zona horaria siempre irá precedido de un signo.</span><span class="sxs-lookup"><span data-stu-id="95eba-161">A timezone offset will always be preceded by a sign.</span></span> <span data-ttu-id="95eba-162">Este signo será un más (+) cuando el desplazamiento sea cero.</span><span class="sxs-lookup"><span data-stu-id="95eba-162">This sign will be a plus (+) when the offset is zero.</span></span> <span data-ttu-id="95eba-163">No habrá ningún espacio en blanco entre el signo y el valor de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="95eba-163">There will be no white space between the sign and the offset value.</span></span> <span data-ttu-id="95eba-164">Las fracciones de segundo se rellenarán con ceros finales, si es necesario, hasta la precisión definida para la columna, pero no más.</span><span class="sxs-lookup"><span data-stu-id="95eba-164">Fractional seconds will be padded with trailing zeros, if necessary, up to the defined precision for the column, but no further.</span></span> <span data-ttu-id="95eba-165">Para las columnas datetime, habrá tres dígitos de fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="95eba-165">For datetime columns, there will be three fractional seconds digits.</span></span> <span data-ttu-id="95eba-166">Para las columnas de smalldatetime, no habrá dígitos de fracciones de segundo y los segundos siempre serán cero.</span><span class="sxs-lookup"><span data-stu-id="95eba-166">For smalldatetime columns, there will be no fractional seconds digits and the seconds will always be zero.</span></span>  
  
 <span data-ttu-id="95eba-167">Las conversiones de los valores de cadena proporcionados por la aplicación serán más flexibles y permitirán valores de componente menores que el ancho máximo.</span><span class="sxs-lookup"><span data-stu-id="95eba-167">Conversions from string values provided by the application will be more flexible and will allow component values less than maximum width.</span></span> <span data-ttu-id="95eba-168">Los años pueden ser de 1-4 dígitos.</span><span class="sxs-lookup"><span data-stu-id="95eba-168">Years can be 1-4 digits.</span></span> <span data-ttu-id="95eba-169">Los meses, días, horas, minutos y segundos pueden tener 1 o 2 dígitos.</span><span class="sxs-lookup"><span data-stu-id="95eba-169">Months, days, hours, minutes, and seconds can be 1 or 2 digits.</span></span> <span data-ttu-id="95eba-170">Puede haber espacio en blanco arbitrario entre los ajustes de fecha/hora y de hora/zona horaria.</span><span class="sxs-lookup"><span data-stu-id="95eba-170">There can be arbitrary white space between date/time and time/timezone offsets.</span></span> <span data-ttu-id="95eba-171">El signo de un ajuste con cero horas y cero minutos puede ser más o menos.</span><span class="sxs-lookup"><span data-stu-id="95eba-171">The sign of an offset with zero hours and zero minutes can be plus or minus.</span></span> <span data-ttu-id="95eba-172">Se permiten ceros finales para las fracciones de segundo hasta un máximo de 9 dígitos.</span><span class="sxs-lookup"><span data-stu-id="95eba-172">Trailing zeros are allowed for fractional seconds up to a maximum of 9 digits.</span></span> <span data-ttu-id="95eba-173">Un componente de hora puede finalizar con un separador decimal y ningún dígito para las fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="95eba-173">A time component can terminate with a decimal point and no fractional seconds digits.</span></span>  
  
 <span data-ttu-id="95eba-174">Una cadena vacía no es un literal válido de fecha y hora y no representa un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="95eba-174">An empty string is not a valid date/time literal and it does not represent a NULL value.</span></span> <span data-ttu-id="95eba-175">Un intento para convertir una cadena vacía en un valor de fecha y hora producirá errores con SQLState 22018 y el mensaje "Valor de carácter no válido para especificación cast".</span><span class="sxs-lookup"><span data-stu-id="95eba-175">An attempt to convert an empty string to a date/time value will result in errors with SQLState 22018 and the message "Invalid character value for cast specification".</span></span>  
  
## <a name="data-formats-data-structures"></a><span data-ttu-id="95eba-176">Formatos de datos: Estructuras de datos</span><span class="sxs-lookup"><span data-stu-id="95eba-176">Data Formats: Data Structures</span></span>  
 <span data-ttu-id="95eba-177">En las estructuras específicas de OLE DB descritas a continuación, OLE DB cumple las mismas restricciones que ODBC.</span><span class="sxs-lookup"><span data-stu-id="95eba-177">In the OLE DB-specific structures described below, OLE DB conforms to the same constraints as ODBC.</span></span> <span data-ttu-id="95eba-178">Se toman del calendario Gregoriano:</span><span class="sxs-lookup"><span data-stu-id="95eba-178">These are taken from the Gregorian calendar:</span></span>  
  
-   <span data-ttu-id="95eba-179">El intervalo de meses va de 1 a 12.</span><span class="sxs-lookup"><span data-stu-id="95eba-179">Month range is 1 through 12.</span></span>  
  
-   <span data-ttu-id="95eba-180">El intervalo de campos de día va de 1 al número de días del mes y debe ser coherente con los campos de año y de mes, teniendo en cuenta los años bisiestos.</span><span class="sxs-lookup"><span data-stu-id="95eba-180">Day field range is 1 through the number of days in the month, and must be consistent with year and month fields, taking account of leap years.</span></span>  
  
-   <span data-ttu-id="95eba-181">El intervalo de fechas va de 0 a 23.</span><span class="sxs-lookup"><span data-stu-id="95eba-181">Hour range is 0 through 23.</span></span>  
  
-   <span data-ttu-id="95eba-182">El intervalo de minutos va de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="95eba-182">Minute range is 0 through 59.</span></span>  
  
-   <span data-ttu-id="95eba-183">El intervalo de segundos va de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="95eba-183">Seconds range from 0 through 59.</span></span> <span data-ttu-id="95eba-184">Esto permite incluir hasta dos segundos intercalares para mantener la sincronización con el tiempo sidéreo.</span><span class="sxs-lookup"><span data-stu-id="95eba-184">This allows up to two leap seconds to maintain synchronization with sidereal time.</span></span>  
  
 <span data-ttu-id="95eba-185">Las implementaciones de las siguientes estructuras existentes de OLE DB se han modificado para admitir los nuevos tipos de datos de fecha y hora de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95eba-185">Implementations for the following existing OLE DB structs have been modified to support the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span> <span data-ttu-id="95eba-186">Las definiciones, sin embargo, no han cambiado.</span><span class="sxs-lookup"><span data-stu-id="95eba-186">The definitions, however, have not changed.</span></span>  
  
-   <span data-ttu-id="95eba-187">DBTYPE_DATE (Es un tipo DATE de automatización.</span><span class="sxs-lookup"><span data-stu-id="95eba-187">DBTYPE_DATE (This is an automation DATE type.</span></span> <span data-ttu-id="95eba-188">Se representa internamente como `double` ..</span><span class="sxs-lookup"><span data-stu-id="95eba-188">It is internally represented as a `double`..</span></span> <span data-ttu-id="95eba-189">La parte entera es el número de días transcurridos desde el 30 de diciembre de 1899 y la parte decimal es una fracción de un día.</span><span class="sxs-lookup"><span data-stu-id="95eba-189">The whole part is the number of days since December 30, 1899 and the fractional part is the fraction of a day.</span></span> <span data-ttu-id="95eba-190">Este tipo tiene una exactitud de 1 segundo, de modo que tiene una escala efectiva de 0.)</span><span class="sxs-lookup"><span data-stu-id="95eba-190">This type has an accuracy of 1 second, so has an effective scale of 0.)</span></span>  
  
-   <span data-ttu-id="95eba-191">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="95eba-191">DBTYPE_DBDATE</span></span>  
  
-   <span data-ttu-id="95eba-192">DBTYPE_DBTIME</span><span class="sxs-lookup"><span data-stu-id="95eba-192">DBTYPE_DBTIME</span></span>  
  
-   <span data-ttu-id="95eba-193">DBTYPE_DBTIMESTAMP (OLE DB define el campo de fracción como el número de milmillonésimas de segundo (nanosegundos) y va de 0 a 999.999.999)</span><span class="sxs-lookup"><span data-stu-id="95eba-193">DBTYPE_DBTIMESTAMP (the fraction field is defined by OLE DB as the number of billionths of a second (nanoseconds) and ranges from 0-999,999,999)</span></span>  
  
-   <span data-ttu-id="95eba-194">DBTYPE_FILETIME</span><span class="sxs-lookup"><span data-stu-id="95eba-194">DBTYPE_FILETIME</span></span>  
  
### <a name="dbtype_dbtime2"></a><span data-ttu-id="95eba-195">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="95eba-195">DBTYPE_DBTIME2</span></span>  
 <span data-ttu-id="95eba-196">Esta estructura se rellena hasta los 12 bytes en sistemas operativos de 32 bits y 64 bits.</span><span class="sxs-lookup"><span data-stu-id="95eba-196">This struct is padded to 12 bytes on both 32-bit and 64-bit operating systems.</span></span>  
  
```  
typedef struct tagDBTIME2 {  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    } DBTIME2;  
```  
  
### <a name="dbtype_-dbtimestampoffset"></a><span data-ttu-id="95eba-197">DBTYPE_ DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="95eba-197">DBTYPE_ DBTIMESTAMPOFFSET</span></span>  
  
```  
typedef struct tagDBTIMESTAMPOFFSET {  
    SHORT year;  
    USHORT month;  
    USHORT day;  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    SHORT timezone_hour;  
    SHORT timezone_minute;  
    } DBTIMESTAMPOFFSET;  
```  
  
 <span data-ttu-id="95eba-198">Si `timezone_hour` es negativo, `timezone_minute` debe ser negativo o cero.</span><span class="sxs-lookup"><span data-stu-id="95eba-198">If `timezone_hour` is negative, `timezone_minute` must be negative or zero.</span></span> <span data-ttu-id="95eba-199">Si `timezone_hour` es positivo, `timezone minute` debe ser positivo o cero.</span><span class="sxs-lookup"><span data-stu-id="95eba-199">If `timezone_hour` is positive, `timezone minute` must be positive or zero.</span></span> <span data-ttu-id="95eba-200">Si `timezone_hour` es cero, `timezone minute` puede contener un valor entre -59 y +59.</span><span class="sxs-lookup"><span data-stu-id="95eba-200">If `timezone_hour` is zero, `timezone minute` can hold a value between -59 and +59.</span></span>  
  
### <a name="ssvariant"></a><span data-ttu-id="95eba-201">SSVARIANT</span><span class="sxs-lookup"><span data-stu-id="95eba-201">SSVARIANT</span></span>  
 <span data-ttu-id="95eba-202">Esta estructura incluye a partir de ahora las nuevas estructuras DBTYPE_DBTIME2 y DBTYPE_DBTIMESTAMPOFFSET, y agrega la escala de fracciones de segundo para los tipos adecuados.</span><span class="sxs-lookup"><span data-stu-id="95eba-202">This struct now includes the new structures, DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET, and adds fractional seconds scale for appropriate types.</span></span>  
  
```  
struct SSVARIANT {  
   SSVARTYPE vt;  
   DWORD dwReserved1;  
   DWORD dwReserved2;  
   union {  
// ...  
      DBTIMESTAMP tsDateTimeVal;  
      DBDATE dDateVal;  
      struct _Time2Val {  
         DBTIME2 tTime2Val;  
         BYTE bScale;  
      } Time2Val;  
      struct _DateTimeVal {  
         DBTIMESTAMP tsDateTimeVal;  
         BYTE bScale;  
      } DateTimeVal;  
      struct _DateTimeOffsetVal {   
         DBTIMESTAMPOFFSET tsoDateTimeOffsetVal;  
         BYTE bScale;  
      } DateTimeOffsetVal;  
// ...  
   };  
};  
```  
  
 <span data-ttu-id="95eba-203">Además, la enumeración asociada con la codificación de tipo SSVARIANT, que determina el tipo de enumeración, se extenderá como sigue:</span><span class="sxs-lookup"><span data-stu-id="95eba-203">In addition, the enum associated with SSVARIANT type encoding, which determines the type of the enum, will be extended as follows:</span></span>  
  
```  
enum SQLVARENUM {  
// ...  
   // Datetime  
   VT_SS_DATETIME      = DBTYPE_DBTIMESTAMP,  
   VT_SS_SMALLDATETIME = 206,  
  
   VT_SS_DATE = DBTYPE_DBDATE,  
   VT_SS_TIME2 = DBTYPE_DBTIME2,  
   VT_SS_DATETIME2 = 212  
   VT_SS_DATETIMEOFFSET = DBTYPE_DBTIMESTAMPOFFSET  
};  
```  
  
 <span data-ttu-id="95eba-204">Las aplicaciones que migran a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client y utilizan `sql_variant`, y que se apoyan en la precisión limitada de `datetime` tendrán que actualizarse si el esquema subyacente está actualizado para utilizar `datetime2` en lugar de `datetime`.</span><span class="sxs-lookup"><span data-stu-id="95eba-204">Applications migrating to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client that use `sql_variant` and rely on the limited precision of `datetime` will have to be updated if the underlying schema is updated to use `datetime2` rather than `datetime`.</span></span>  
  
 <span data-ttu-id="95eba-205">Las macros de acceso para SSVARIANT también se han extendido con la adición de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95eba-205">The access macros for SSVARIANT have also been extended with the addition of the following:</span></span>  
  
```  
#define V_SS_DATETIME2(X)       V_SS_UNION(X, DateTimeVal)  
#define V_SS_TIME2(X)           V_SS_UNION(X, Time2Val)  
#define V_SS_DATE(X)            V_SS_UNION(X, dDateVal)  
#define V_SS_DATETIMEOFFSET(X)  V_SS_UNION(X, DateTimeOffsetVal)  
```  
  
## <a name="data-type-mapping-in-itabledefinitioncreatetable"></a><span data-ttu-id="95eba-206">Asignar tipo de datos en ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="95eba-206">Data Type Mapping in ITableDefinition::CreateTable</span></span>  
 <span data-ttu-id="95eba-207">La siguiente asignación de tipos se usa con las estructuras DBCOLUMNDESC que se emplean en ITableDefinition::CreateTable:</span><span class="sxs-lookup"><span data-stu-id="95eba-207">The following type mapping is used with DBCOLUMNDESC structures used by ITableDefinition::CreateTable:</span></span>  
  
|<span data-ttu-id="95eba-208">Tipo de datos de OLE DB (*wType*)</span><span class="sxs-lookup"><span data-stu-id="95eba-208">OLE DB data type (*wType*)</span></span>|<span data-ttu-id="95eba-209">Tipo de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95eba-209">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="95eba-210">Notas</span><span class="sxs-lookup"><span data-stu-id="95eba-210">Notes</span></span>|  
|----------------------------------|-----------------------------------------|-----------|  
|<span data-ttu-id="95eba-211">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="95eba-211">DBTYPE_DBDATE</span></span>|<span data-ttu-id="95eba-212">date</span><span class="sxs-lookup"><span data-stu-id="95eba-212">date</span></span>||  
|<span data-ttu-id="95eba-213">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="95eba-213">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="95eba-214">`datetime2`(p)</span><span class="sxs-lookup"><span data-stu-id="95eba-214">`datetime2`(p)</span></span>|<span data-ttu-id="95eba-215">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client inspecciona el miembro *BSCALE* de miembros para determinar la precisión de las fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="95eba-215">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="95eba-216">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="95eba-216">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="95eba-217">`time`(p)</span><span class="sxs-lookup"><span data-stu-id="95eba-217">`time`(p)</span></span>|<span data-ttu-id="95eba-218">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client inspecciona el miembro *BSCALE* de miembros para determinar la precisión de las fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="95eba-218">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="95eba-219">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="95eba-219">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="95eba-220">`datetimeoffset`(p)</span><span class="sxs-lookup"><span data-stu-id="95eba-220">`datetimeoffset`(p)</span></span>|<span data-ttu-id="95eba-221">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client inspecciona el miembro *BSCALE* de miembros para determinar la precisión de las fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="95eba-221">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
  
 <span data-ttu-id="95eba-222">Cuando una aplicación especifica DBTYPE_DBTIMESTAMP en *wType*, puede invalidar la asignación a proporcionando `datetime2` un nombre de tipo en *pwszTypeName*.</span><span class="sxs-lookup"><span data-stu-id="95eba-222">When an application specifies DBTYPE_DBTIMESTAMP in *wType*, it can override the mapping to `datetime2` by supplying a type name in *pwszTypeName*.</span></span> <span data-ttu-id="95eba-223">Si `datetime` se especifica, *bScale* debe ser 3.</span><span class="sxs-lookup"><span data-stu-id="95eba-223">If `datetime` is specified, *bScale* must be 3.</span></span> <span data-ttu-id="95eba-224">Si `smalldatetime` se especifica, *bScale* debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="95eba-224">If `smalldatetime` is specified, *bScale* must be 0.</span></span> <span data-ttu-id="95eba-225">Si *bScale* no es coherente con *wType* y *pwszTypeName*, se devuelve DB_E_BADSCALE.</span><span class="sxs-lookup"><span data-stu-id="95eba-225">If *bScale* is not consistent with *wType* and *pwszTypeName*,DB_E_BADSCALE is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95eba-226">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95eba-226">See Also</span></span>  
 [<span data-ttu-id="95eba-227">Mejoras de fecha y hora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="95eba-227">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
