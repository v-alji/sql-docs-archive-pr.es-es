---
title: Importar y exportar datos de forma masiva con la utilidad bcp (SQL Server) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], bcp utility
- bulk importing [SQL Server], bcp utility
- bcp utility [SQL Server], about bcp utility
ms.assetid: 73e949de-67a3-4c84-9735-7da1ad4ba34a
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: ''
ms.date: 06/14/2017
ms.openlocfilehash: 7d1892b26f3c638a696d8ed15e739f56ac2e682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675373"
---
# <a name="import-and-export-bulk-data-by-using-the-bcp-utility-sql-server"></a><span data-ttu-id="ae27e-102">Importar y exportar datos de forma masiva con la utilidad bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ae27e-102">Import and Export Bulk Data by Using the bcp Utility (SQL Server)</span></span>

<span data-ttu-id="ae27e-103">Este tema constituye una introducción al uso de la [utilidad bcp](../../tools/bcp-utility.md) para exportar datos desde cualquier lugar de una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la que funcione una instrucción SELECT, incluidas las vistas con particiones.</span><span class="sxs-lookup"><span data-stu-id="ae27e-103">This topic provides an overview for using the [bcp utility](../../tools/bcp-utility.md) to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database where a SELECT statement works, including partitioned views.</span></span>  
  
 <span data-ttu-id="ae27e-104">La utilidad bcp (Bcp.exe) es una herramienta de línea de comandos que utiliza la API de importación masiva de Bulk Copy Program o Programa de copia masiva (BCP).</span><span class="sxs-lookup"><span data-stu-id="ae27e-104">The bcp utility (Bcp.exe) is a command-line tool that uses the Bulk Copy Program (BCP) API.</span></span> <span data-ttu-id="ae27e-105">La utilidad bcp realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ae27e-105">The bcp utility performs the following tasks:</span></span>  
  
-   <span data-ttu-id="ae27e-106">Exportaciones masivas de datos de una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="ae27e-106">Bulk exports data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into a data file.</span></span>  
  
-   <span data-ttu-id="ae27e-107">Exportaciones masivas de una consulta.</span><span class="sxs-lookup"><span data-stu-id="ae27e-107">Bulk exports data from a query.</span></span>  
  
-   <span data-ttu-id="ae27e-108">Importaciones masivas de datos de un archivo de datos a una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae27e-108">Bulk imports data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
-   <span data-ttu-id="ae27e-109">Genera archivos de formato.</span><span class="sxs-lookup"><span data-stu-id="ae27e-109">Generates format files.</span></span>  
  
 <span data-ttu-id="ae27e-110">A la utilidad bcp se accede con el comando **bcp** .</span><span class="sxs-lookup"><span data-stu-id="ae27e-110">The bcp utility is accessed by the **bcp** command.</span></span> <span data-ttu-id="ae27e-111">Para usar el comando **bcp** para realizar importaciones masivas de datos, debe conocer el esquema de la tabla y los tipos de datos de sus columnas, a menos que se use un archivo con un formato ya existente.</span><span class="sxs-lookup"><span data-stu-id="ae27e-111">To use the **bcp** command to bulk import data, you must understand the schema of the table and the data types of its columns, unless you are using a pre-existing format file.</span></span>  
  
 <span data-ttu-id="ae27e-112">La utilidad bcp permite exportar datos de una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un archivo de datos para usarlos en otros programas.</span><span class="sxs-lookup"><span data-stu-id="ae27e-112">The bcp utility can export data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table to a data file for use in other programs.</span></span> <span data-ttu-id="ae27e-113">También permite importar datos a una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde otro programa, normalmente otro sistema de administración de bases de datos (DBMS).</span><span class="sxs-lookup"><span data-stu-id="ae27e-113">The utility can also import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table from another program, usually another database management system (DBMS).</span></span> <span data-ttu-id="ae27e-114">Los datos se exportan primero desde el programa de origen a un archivo de datos y, después, se copian del archivo de datos a una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae27e-114">The data is first exported from the source program to a data file and then, in a separate operation, copied from the data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="ae27e-115">El comando **bcp** proporciona modificadores para especificar el tipo de datos del archivo de datos y otra información.</span><span class="sxs-lookup"><span data-stu-id="ae27e-115">The **bcp** command provides switches that you use to specify the data type of the data file and other information.</span></span> <span data-ttu-id="ae27e-116">Si no se especifican estos modificadores, el comando solicitará información de formato, como el tipo de campos de datos de un archivo de datos</span><span class="sxs-lookup"><span data-stu-id="ae27e-116">If these switches are not specified, the command prompts for formatting information, such as the type of data fields in a data file.</span></span> <span data-ttu-id="ae27e-117">A continuación, el comando preguntará si se desea crear un archivo de formato con las respuestas interactivas.</span><span class="sxs-lookup"><span data-stu-id="ae27e-117">The command then asks whether you want to create a format file that contains your interactive responses.</span></span> <span data-ttu-id="ae27e-118">Si desea flexibilidad para operaciones futuras de importación o exportación masivas, un archivo de formato suele resultar útil.</span><span class="sxs-lookup"><span data-stu-id="ae27e-118">If you want flexibility for future bulk-import or bulk-export operations, a format file is often useful.</span></span> <span data-ttu-id="ae27e-119">Puede especificar el archivo de formato en comandos **bcp** posteriores para archivos de datos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="ae27e-119">You can specify the format file on later **bcp** commands for equivalent data files.</span></span> <span data-ttu-id="ae27e-120">Para obtener más información, vea [Especificar formatos de datos por razones de compatibilidad mediante bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ae27e-120">For more information, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae27e-121">La utilidad bcp se escribe utilizando la copia masiva de ODBC</span><span class="sxs-lookup"><span data-stu-id="ae27e-121">The bcp utility is written by using the ODBC bulk-copy</span></span>  
  
 <span data-ttu-id="ae27e-122">Para obtener una descripción de la sintaxis del comando **bcp** , vea [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ae27e-122">For a description of the **bcp** command syntax, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ae27e-123">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ae27e-123">Examples</span></span>

 <span data-ttu-id="ae27e-124">Para consultar los ejemplos de **bcp** , vea:</span><span class="sxs-lookup"><span data-stu-id="ae27e-124">For **bcp** examples, see:</span></span>  
  
-   [<span data-ttu-id="ae27e-125">bcp (utilidad)</span><span class="sxs-lookup"><span data-stu-id="ae27e-125">bcp Utility</span></span>](../../tools/bcp-utility.md)  
  
-   [<span data-ttu-id="ae27e-126">Crear un archivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae27e-126">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="ae27e-127">Ejemplos de importación y exportación en bloque de documentos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae27e-127">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
  
-   [<span data-ttu-id="ae27e-128">Mantener valores de identidad al importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae27e-128">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="ae27e-129">Mantener valores NULL o usar valores predeterminados durante la importación en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae27e-129">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="ae27e-130">Especificar terminadores de campo y de fila &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae27e-130">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="ae27e-131">Usar un archivo de formato para importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae27e-131">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="ae27e-132">Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae27e-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="ae27e-133">Usar el formato nativo para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae27e-133">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="ae27e-134">Usar el formato de caracteres Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae27e-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="ae27e-135">Usar el formato nativo Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae27e-135">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  

## <a name="see-also"></a><span data-ttu-id="ae27e-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae27e-136">See Also</span></span>

<span data-ttu-id="ae27e-137">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) 
 [Cláusula SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) 
 [BCP, utilidad](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ae27e-137">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql)
[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql)
[bcp Utility](../../tools/bcp-utility.md) </span></span>  
<span data-ttu-id="ae27e-138">[Preparar la importación masiva de datos &#40;SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md) 
 [BULK INSERT &#40;&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) 
 de Transact-SQL [Importación y exportación masivas de datos &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) 
 [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) 
 [Cree un archivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="ae27e-138">[Prepare to Bulk Import Data &#40;SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md)
[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql)
[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md)
[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)
[Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span></span>