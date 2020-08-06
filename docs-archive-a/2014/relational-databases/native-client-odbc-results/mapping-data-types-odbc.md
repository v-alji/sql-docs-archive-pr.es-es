---
title: Asignar tipos de datos (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- mapping data types [ODBC]
- result sets [ODBC], data types
- ODBC data types, mapping
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- data types [ODBC], mapping
- sql_variant data type
- SQL Server Native Client ODBC driver, data types
ms.assetid: 4ba0924d-9fca-4c48-aced-0a8d817b3dde
author: rothja
ms.author: jroth
ms.openlocfilehash: 545e738afb6b3283b2ff2f3830921da8ed13202f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750873"
---
# <a name="mapping-data-types-odbc"></a><span data-ttu-id="d8502-102">Asignar tipos de datos (ODBC)</span><span class="sxs-lookup"><span data-stu-id="d8502-102">Mapping Data Types (ODBC)</span></span>
  <span data-ttu-id="d8502-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client asigna [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de datos SQL a tipos de datos SQL de ODBC.</span><span class="sxs-lookup"><span data-stu-id="d8502-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types to ODBC SQL data types.</span></span> <span data-ttu-id="d8502-104">En las secciones siguientes se describen los tipos de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL y los tipos de datos ODBC SQL a los que se asignan.</span><span class="sxs-lookup"><span data-stu-id="d8502-104">The sections below discuss the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types and the ODBC SQL data types to which they map.</span></span> <span data-ttu-id="d8502-105">También se tratan los tipos de datos ODBC SQL y sus tipos de datos ODBC C correspondientes, así como las conversiones compatibles y predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="d8502-105">They also discuss the ODBC SQL data types and their corresponding ODBC C data types, and the supported and default conversions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8502-106">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo de datos **timestamp** se asigna al tipo de datos SQL_BINARY o SQL_VARBINARY ODBC porque los valores de las columnas **timestamp** no son valores **DateTime** , sino valores **binarios (8)** o **varbinary (8)** que indican la secuencia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] actividad de la fila.</span><span class="sxs-lookup"><span data-stu-id="d8502-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**timestamp** data type maps to the SQL_BINARY or SQL_VARBINARY ODBC data type because the values in **timestamp** columns are not **datetime** values, but **binary(8)** or **varbinary(8)** values that indicate the sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity on the row.</span></span> <span data-ttu-id="d8502-107">Si el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client encuentra un valor SQL_C_WCHAR (Unicode) con un número impar de bytes, se trunca el byte impar final.</span><span class="sxs-lookup"><span data-stu-id="d8502-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver encounters a SQL_C_WCHAR (Unicode) value that is an odd number of bytes, the trailing odd byte is truncated.</span></span>  
  
## <a name="dealing-with-sql_variant-data-type-in-odbc"></a><span data-ttu-id="d8502-108">Administrar tipos de datos sql_variant en ODBC</span><span class="sxs-lookup"><span data-stu-id="d8502-108">Dealing with sql_variant Data Type in ODBC</span></span>  
 <span data-ttu-id="d8502-109">La columna tipo de datos **sql_variant** puede contener cualquiera de los tipos de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , excepto los objetos grandes (LOB), como **Text**, **ntext**e **Image**.</span><span class="sxs-lookup"><span data-stu-id="d8502-109">The **sql_variant** data type column can contain any of the data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except large objects (LOBs), such as **text**, **ntext**, and **image**.</span></span> <span data-ttu-id="d8502-110">Por ejemplo, la columna puede contener valores **smallint** para algunas filas, valores **float** para otras filas y valores **CHAR/NCHAR** en el resto.</span><span class="sxs-lookup"><span data-stu-id="d8502-110">For example, the column could contain **smallint** values for some rows, **float** values for other rows, and **char/nchar** values in the remainder.</span></span>  
  
 <span data-ttu-id="d8502-111">El tipo de datos **sql_variant** es similar al tipo de datos **variant** de Microsoft Visual Basic??.</span><span class="sxs-lookup"><span data-stu-id="d8502-111">The **sql_variant** data type is similar to the **Variant** data type in Microsoft Visual Basic??.</span></span>  
  
### <a name="retrieving-data-from-the-server"></a><span data-ttu-id="d8502-112">Recuperar datos del servidor</span><span class="sxs-lookup"><span data-stu-id="d8502-112">Retrieving Data from the Server</span></span>  
 <span data-ttu-id="d8502-113">ODBC no tiene un concepto de tipos Variant, lo que limita el uso del tipo de datos **sql_variant** con un controlador ODBC en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8502-113">ODBC does not have a concept of variant types, limiting the use of the **sql_variant** data type with an ODBC driver in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d8502-114">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , si se especifica Binding, el tipo de datos **sql_variant** debe estar enlazado a uno de los tipos de datos ODBC documentados.</span><span class="sxs-lookup"><span data-stu-id="d8502-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if binding is specified, the **sql_variant** data type must be bound to one of the documented ODBC data types.</span></span> <span data-ttu-id="d8502-115">**SQL_CA_SS_VARIANT_TYPE**, un nuevo atributo específico del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client, devuelve el tipo de datos de una instancia de la columna **sql_variant** al usuario.</span><span class="sxs-lookup"><span data-stu-id="d8502-115">**SQL_CA_SS_VARIANT_TYPE**, a new attribute specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, returns the data type of an instance in the **sql_variant** column to the user.</span></span>  
  
 <span data-ttu-id="d8502-116">Si no se especifica ningún enlace, la función [SQLGetData](../native-client-odbc-api/sqlgetdata.md) se puede utilizar para determinar el tipo de datos de una instancia en la columna **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="d8502-116">If no binding is specified, the [SQLGetData](../native-client-odbc-api/sqlgetdata.md) function can be used to determine the data type of an instance in the **sql_variant** column.</span></span>  
  
 <span data-ttu-id="d8502-117">Para recuperar los datos de **sql_variant** siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d8502-117">To retrieve **sql_variant** data follow these steps.</span></span>  
  
1.  <span data-ttu-id="d8502-118">Llame a **SQLFetch** para colocar en la fila recuperada.</span><span class="sxs-lookup"><span data-stu-id="d8502-118">Call **SQLFetch** to position to the row retrieved.</span></span>  
  
2.  <span data-ttu-id="d8502-119">Llame a **SQLGetData**, especificando SQL_C_BINARY para el tipo y 0 para la longitud de los datos.</span><span class="sxs-lookup"><span data-stu-id="d8502-119">Call **SQLGetData**, specifying SQL_C_BINARY for the type and 0 for the data length.</span></span> <span data-ttu-id="d8502-120">Esto obliga al controlador a leer el encabezado **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="d8502-120">This forces the driver to read the **sql_variant** header.</span></span> <span data-ttu-id="d8502-121">El encabezado proporciona el tipo de datos de esa instancia en el **sql_variant** columna.</span><span class="sxs-lookup"><span data-stu-id="d8502-121">The header provides the data type of that instance in the **sql_variant** column.</span></span> <span data-ttu-id="d8502-122">**SQLGetData** devuelve el tamaño (en bytes) del valor.</span><span class="sxs-lookup"><span data-stu-id="d8502-122">**SQLGetData** returns the size (in bytes) of the value.</span></span>  
  
3.  <span data-ttu-id="d8502-123">Llame a [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) especificando **SQL_CA_SS_VARIANT_TYPE** como su valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="d8502-123">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) by specifying **SQL_CA_SS_VARIANT_TYPE** as its attribute value.</span></span> <span data-ttu-id="d8502-124">Esta función devolverá el tipo de datos C de la instancia de de la columna **sql_variant** al cliente.</span><span class="sxs-lookup"><span data-stu-id="d8502-124">This function will return the C data type of the instance in the **sql_variant** column to the client.</span></span>  
  
 <span data-ttu-id="d8502-125">A continuación se incluye un segmento de código que muestra los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="d8502-125">Here is a code segment showing the preceding steps.</span></span>  
  
```  
while ((retcode = SQLFetch (hstmt))==SQL_SUCCESS)  
{  
    if (retcode != SQL_SUCCESS && retcode != SQL_SUCCESS_WITH_INFO)  
    {  
        SQLError (NULL, NULL, hstmt, NULL,   
                    &lNativeError,szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    retcode = SQLGetData (hstmt, 1, SQL_C_BINARY,   
                                pBuff,0,&Indicator);//Figure out the length  
    if (retcode != SQL_SUCCESS_WITH_INFO && retcode != SQL_SUCCESS)  
    {  
        SQLError (NULL, NULL, hstmt, NULL, &lNativeError,   
                    szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    printf_s ("Byte length : %d ",Indicator); //Print out the byte length  
  
    int iValue = 0;  
    retcode = SQLColAttribute (hstmt, 1, SQL_CA_SS_VARIANT_TYPE, NULL,   
                                        NULL,NULL,&iValue);  //Figure out the type  
    printf_s ("Sub type = %d ",iValue);//Print the type, the return is C_type of the column]  
  
// Set up a new binding or do the SQLGetData on that column with   
// the appropriate type  
}  
```  
  
 <span data-ttu-id="d8502-126">Si el usuario crea el enlace mediante [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), el controlador Lee los metadatos y los datos.</span><span class="sxs-lookup"><span data-stu-id="d8502-126">If the user creates the binding using [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), the driver reads the metadata and the data.</span></span> <span data-ttu-id="d8502-127">A continuación, el controlador convierte los datos al tipo ODBC adecuado especificado en el enlace.</span><span class="sxs-lookup"><span data-stu-id="d8502-127">The driver then converts the data to the appropriate ODBC type specified in the binding.</span></span>  
  
### <a name="sending-data-to-the-server"></a><span data-ttu-id="d8502-128">Enviar datos al servidor</span><span class="sxs-lookup"><span data-stu-id="d8502-128">Sending Data to the Server</span></span>  
 <span data-ttu-id="d8502-129">**SQL_SS_VARIANT**, se utiliza un nuevo tipo de datos específico del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client para los datos enviados a una columna **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="d8502-129">**SQL_SS_VARIANT**, a new data type specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, is used for data sent to an **sql_variant** column.</span></span> <span data-ttu-id="d8502-130">Al enviar datos al servidor mediante parámetros (por ejemplo, INSERT INTO TableName VALUEs (?,?)), [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) se usa para especificar la información de parámetros, incluido el tipo C y el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d8502-130">When sending data to the server using parameters (for example, INSERT INTO TableName VALUES (?,?)), [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) is used to specify the parameter information including the C type and the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type.</span></span> <span data-ttu-id="d8502-131">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client convertirá el tipo de datos C en uno de los subtipos **sql_variant** adecuados.</span><span class="sxs-lookup"><span data-stu-id="d8502-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will convert the C data type to one of the appropriate **sql_variant** subtypes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8502-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8502-132">See Also</span></span>  
 [<span data-ttu-id="d8502-133">Procesar los resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="d8502-133">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
