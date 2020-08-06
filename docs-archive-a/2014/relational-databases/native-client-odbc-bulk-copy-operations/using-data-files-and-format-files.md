---
title: Usar archivos de datos y archivos de formato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- ODBC, functions
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [SQL Server Native Client]
- ODBC, bulk copy operations
- bulk copy [ODBC], data files
ms.assetid: c01b7155-3f0a-473d-90b7-87a97bc56ca5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e0ee92f79e2c8cab9605db0188e01898df8c23e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750926"
---
# <a name="using-data-files-and-format-files"></a><span data-ttu-id="5213e-102">Utilizar archivos de datos y archivos de formato</span><span class="sxs-lookup"><span data-stu-id="5213e-102">Using Data Files and Format Files</span></span>
  <span data-ttu-id="5213e-103">El programa de copia masiva más simple hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5213e-103">The simplest bulk copy program does the following:</span></span>  
  
1.  <span data-ttu-id="5213e-104">Llama a [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) para especificar la copia masiva de salida (establecer BCP_OUT) de una tabla o vista en un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="5213e-104">Calls [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to specify bulk copying out (set BCP_OUT) from a table or view to a data file.</span></span>  
  
2.  <span data-ttu-id="5213e-105">Llama a [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) para ejecutar la operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="5213e-105">Calls [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="5213e-106">El archivo de datos se crea en modo nativo; por tanto, los datos de todas las columnas de la tabla o la vista se almacenan en el archivo de datos con el mismo formato que en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5213e-106">The data file is created in native mode; therefore, data from all columns in the table or view are stored in the data file in the same format as in the database.</span></span> <span data-ttu-id="5213e-107">A continuación, se puede realizar una copia masiva del archivo en un servidor mediante estos mismos pasos y estableciendo DB_IN en lugar de DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="5213e-107">The file can then be bulk copied into a server by using these same steps and setting DB_IN instead of DB_OUT.</span></span> <span data-ttu-id="5213e-108">Esto solamente funciona si las tablas de destino y origen tienen exactamente la misma estructura.</span><span class="sxs-lookup"><span data-stu-id="5213e-108">This works only if both the source and target tables have exactly the same structure.</span></span> <span data-ttu-id="5213e-109">El archivo de datos resultante también puede ser una entrada a la utilidad **BCP** mediante el modificador **/n** (modo nativo).</span><span class="sxs-lookup"><span data-stu-id="5213e-109">The resulting data file can also be input to the **bcp** utility by using the **/n** (native mode) switch.</span></span>  
  
 <span data-ttu-id="5213e-110">Para realizar la copia masiva del conjunto de resultados de una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] en lugar de directamente de una tabla o vista:</span><span class="sxs-lookup"><span data-stu-id="5213e-110">To bulk copy out the result set of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement instead of directly from a table or view:</span></span>  
  
1.  <span data-ttu-id="5213e-111">Llame a **bcp_init** para especificar las copias masivas, pero especifique NULL para el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="5213e-111">Call **bcp_init** to specify bulk copying out, but specify NULL for the table name.</span></span>  
  
2.  <span data-ttu-id="5213e-112">Llame a [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) con *EOPTION* establecido en BCPHINTS y *iValue* establecido en un puntero a una cadena SQLTCHAR que contiene la instrucción Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5213e-112">Call [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) with *eOption* set to BCPHINTS and *iValue* set to a pointer to a SQLTCHAR string containing the Transact-SQL statement.</span></span>  
  
3.  <span data-ttu-id="5213e-113">Llame a **bcp_exec** para ejecutar la operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="5213e-113">Call **bcp_exec** to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="5213e-114">La instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] puede ser cualquier instrucción que genere un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5213e-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be any statement that generates a result set.</span></span> <span data-ttu-id="5213e-115">Se crea el archivo de datos que contiene el primer conjunto de resultados de la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5213e-115">The data file is created containing the first result set of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="5213e-116">La copia masiva omite cualquier conjunto de resultados tras la primera si la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] genera varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="5213e-116">Bulk copy ignores any result set after the first if the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement generates multiple result sets.</span></span>  
  
 <span data-ttu-id="5213e-117">Para crear un archivo de datos en el que los datos de columna se almacenen en un formato diferente que en la tabla, llame a [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) para especificar el número de columnas que se van a cambiar y, a continuación, llame a [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) para cada columna cuyo formato desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="5213e-117">To create a data file in which column data is stored in a different format than in the table, call [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to specify how many columns will be changed, then call [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column whose format you want to change.</span></span> <span data-ttu-id="5213e-118">Esto se hace después de llamar a **bcp_init** pero antes de llamar a **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="5213e-118">This is done after calling **bcp_init** but before calling **bcp_exec**.</span></span> <span data-ttu-id="5213e-119">**bcp_colfmt** especifica el formato en el que se almacenan los datos de la columna en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="5213e-119">**bcp_colfmt** specifies the format in which the column's data is stored in the data file.</span></span> <span data-ttu-id="5213e-120">Se puede usar cuando se realiza una copia masiva de dentro o fuera. También puede usar **bcp_colfmt** para establecer los terminadores de fila y de columna.</span><span class="sxs-lookup"><span data-stu-id="5213e-120">It can be used when bulk copying in or out. You can also use **bcp_colfmt** to set the row and column terminators.</span></span> <span data-ttu-id="5213e-121">Por ejemplo, si los datos no contienen caracteres de tabulación, puede crear un archivo delimitado por tabuladores mediante **bcp_colfmt** para establecer el carácter de tabulación como el terminador de cada columna.</span><span class="sxs-lookup"><span data-stu-id="5213e-121">For example, if your data contains no tab characters, you can create a tab-delimited file by using **bcp_colfmt** to set the tab character as the terminator for each column.</span></span>  
  
 <span data-ttu-id="5213e-122">Cuando se realiza una copia masiva y se usa **bcp_colfmt**, puede crear fácilmente un archivo de formato que describa el archivo de datos que ha creado llamando a [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) después de la última llamada a **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="5213e-122">When bulk copying out and using **bcp_colfmt**, you can easily create a format file describing the data file you have created by calling [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) after the last call to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="5213e-123">Cuando se realiza una copia masiva desde un archivo de datos descrito por un archivo de formato, se lee el archivo de formato mediante una llamada a [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) después de **bcp_init** pero antes de **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="5213e-123">When bulk copying in from a data file described by a format file, read the format file by calling [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) after **bcp_init** but before **bcp_exec**.</span></span>  
  
 <span data-ttu-id="5213e-124">La función **bcp_control** controla varias opciones cuando se realiza una copia masiva [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="5213e-124">The **bcp_control** function controls several options when bulk copying into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file.</span></span> <span data-ttu-id="5213e-125">**bcp_control** establece opciones, como el número máximo de errores antes de la finalización, la fila del archivo en el que se va a iniciar la copia masiva, la fila en la que se va a detener y el tamaño del lote.</span><span class="sxs-lookup"><span data-stu-id="5213e-125">**bcp_control** sets options, such as the maximum number of errors before termination, the row in the file on which to start the bulk copy, the row to stop on, and the batch size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5213e-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5213e-126">See Also</span></span>  
 [<span data-ttu-id="5213e-127">Realizar operaciones de copia masiva &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="5213e-127">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
