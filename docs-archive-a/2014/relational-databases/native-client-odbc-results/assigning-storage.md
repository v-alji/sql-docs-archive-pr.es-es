---
title: Asignación de almacenamiento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- column-wise binding [ODBC]
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- SQLBindCol function
- storing data [ODBC]
- result sets [ODBC], storage
- SQL Server Native Client ODBC driver, data storage
- row-wise binding
- binding result sets [SQL Server Native Client]
- array binding
ms.assetid: 11c81955-5300-495f-925f-9256f2587b58
author: rothja
ms.author: jroth
ms.openlocfilehash: ada18c91493d91b36ced51bf84c32513a0c5f5df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675312"
---
# <a name="assigning-storage"></a><span data-ttu-id="dd0f0-102">Asignar almacenamiento</span><span class="sxs-lookup"><span data-stu-id="dd0f0-102">Assigning Storage</span></span>
  <span data-ttu-id="dd0f0-103">Una aplicación puede asignar almacenamiento para los resultados antes o después de ejecutar una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-103">An application can assign storage for results before or after it executes a SQL statement.</span></span> <span data-ttu-id="dd0f0-104">Si una aplicación prepara o ejecuta primero la instrucción SQL, puede realizar consultas sobre el conjunto de resultados antes de asignar almacenamiento para los resultados.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-104">If an application prepares or executes the SQL statement first, it can inquire about the result set before it assigns storage for results.</span></span> <span data-ttu-id="dd0f0-105">Por ejemplo, si no se conoce el conjunto de resultados, la aplicación debe recuperar el número de columnas para poder asignar almacenamiento al mismo.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-105">For example, if the result set is unknown, the application must retrieve the number of columns before it can assign storage for them.</span></span>  
  
 <span data-ttu-id="dd0f0-106">Para asociar el almacenamiento de una columna de datos, una aplicación llama a [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)y lo pasa:</span><span class="sxs-lookup"><span data-stu-id="dd0f0-106">To associate storage for a column of data, an application calls [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)and passes it:</span></span>  
  
-   <span data-ttu-id="dd0f0-107">El tipo al que deben convertirse los datos.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-107">The data type to which the data is to be converted.</span></span>  
  
-   <span data-ttu-id="dd0f0-108">La dirección de un búfer de salida para los datos.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-108">The address of an output buffer for the data.</span></span>  
  
     <span data-ttu-id="dd0f0-109">La aplicación debe asignar este búfer, que debe ser lo suficientemente grande como para albergar los datos en el formato al que se conviertan.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-109">The application must allocate this buffer, and it must be large enough to hold the data in the form to which it is converted.</span></span>  
  
-   <span data-ttu-id="dd0f0-110">La longitud del búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-110">The length of the output buffer.</span></span>  
  
     <span data-ttu-id="dd0f0-111">Este valor se omite si los datos devueltos tienen un ancho fijo en C, como un entero, un número real o una estructura de fecha.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-111">This value is ignored if the returned data has a fixed width in C, such as an integer, real number, or date structure.</span></span>  
  
-   <span data-ttu-id="dd0f0-112">La dirección de un búfer de almacenamiento donde devolver el número de bytes de los datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-112">The address of a storage buffer in which to return the number of bytes of available data.</span></span>  
  
 <span data-ttu-id="dd0f0-113">Una aplicación también puede enlazar las columnas del conjunto de resultados a matrices de variables de programa para que las filas del conjunto de resultados puedan capturarse en bloques.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-113">An application can also bind result set columns to arrays of program variables to support fetching result set rows in blocks.</span></span> <span data-ttu-id="dd0f0-114">Existen dos tipos distintos de enlaces de matriz:</span><span class="sxs-lookup"><span data-stu-id="dd0f0-114">There are two different types of array binding:</span></span>  
  
-   <span data-ttu-id="dd0f0-115">El enlace de modo de columna finaliza cuando cada columna se enlaza a su propia matriz de variables.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-115">Column-wise binding is finished when each column is bound to its own array of variables.</span></span>  
  
     <span data-ttu-id="dd0f0-116">El enlace de modo de columna se especifica llamando a [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) con el *atributo* establecido en SQL_ATTR_ROW_BIND_TYPE y *ValuePtr* establecido en SQL_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-116">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to SQL_BIND_BY_COLUMN.</span></span> <span data-ttu-id="dd0f0-117">Todas las matrices deben tener el mismo número de elementos.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-117">All the arrays must have the same number of elements.</span></span>  
  
-   <span data-ttu-id="dd0f0-118">El enlace de modo de fila finaliza cuando todos los parámetros de la instrucción SQL se enlazan como una unidad a una matriz de estructuras que contienen variables individuales para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-118">Row-wise binding is finished when all the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>  
  
     <span data-ttu-id="dd0f0-119">El enlace de modo de fila se especifica mediante una llamada a **SQLSetStmtAttr** con el *atributo* establecido en SQL_ATTR_ROW_BIND_TYPE y *ValuePtr* establecido en el tamaño de la estructura que contiene las variables que recibirán las columnas del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-119">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to the size of the structure holding the variables that will receive the result set columns.</span></span>  
  
 <span data-ttu-id="dd0f0-120">La aplicación también establece SQL_ATTR_ROW_ARRAY_SIZE en el número de elementos de las matrices de columnas o filas y establece SQL_ATTR_ROW_STATUS_PTR y SQL_ATTR_ROWS_FETCHED_PTR.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-120">The application also sets SQL_ATTR_ROW_ARRAY_SIZE to the number of elements in the column or row arrays and sets SQL_ATTR_ROW_STATUS_PTR and SQL_ATTR_ROWS_FETCHED_PTR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd0f0-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd0f0-121">See Also</span></span>  
 [<span data-ttu-id="dd0f0-122">Procesar los resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="dd0f0-122">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
