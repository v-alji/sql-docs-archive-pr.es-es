---
title: Evitar conflictos con operaciones de base de datos en aplicaciones FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Win32 and Transact-SQL Conflicts
ms.assetid: 8b1ee196-69af-4f9b-9bf5-63d8ac2bc39b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0ac7e681766396d3a3b4412d91a968b4cdc653c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676024"
---
# <a name="avoid-conflicts-with-database-operations-in-filestream-applications"></a><span data-ttu-id="986b4-102">Evitar conflictos con operaciones de base de datos en aplicaciones FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="986b4-102">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>
  <span data-ttu-id="986b4-103">Las aplicaciones que usan SqlOpenFilestream() para abrir los identificadores de archivos de Win32 con el fin de leer o escribir datos BLOB de FILESTREAM pueden encontrar errores de conflictos con las instrucciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] que se administran en una transacción común.</span><span class="sxs-lookup"><span data-stu-id="986b4-103">Applications that use SqlOpenFilestream() to open Win32 file handles for reading or writing FILESTREAM BLOB data can encounter conflict errors with [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are managed in a common transaction.</span></span> <span data-ttu-id="986b4-104">Esto incluye las consultas de [!INCLUDE[tsql](../../includes/tsql-md.md)] o MARS que tardan mucho en finalizar la ejecución.</span><span class="sxs-lookup"><span data-stu-id="986b4-104">This includes [!INCLUDE[tsql](../../includes/tsql-md.md)] or MARS queries that take a long time to finish execution.</span></span> <span data-ttu-id="986b4-105">Las aplicaciones deben diseñarse cuidadosamente para ayudar a evitar estos tipos de conflictos.</span><span class="sxs-lookup"><span data-stu-id="986b4-105">Applications must be carefully designed to help avoid these types of conflicts.</span></span>  
  
 <span data-ttu-id="986b4-106">Cuando [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] o las aplicaciones intentan abrir BLOB de FILESTREAM, [!INCLUDE[ssDE](../../includes/ssde-md.md)] comprueba el contexto de transacciones asociado.</span><span class="sxs-lookup"><span data-stu-id="986b4-106">When [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or applications try to open FILESTREAM BLOBs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] checks the associated transaction context.</span></span> <span data-ttu-id="986b4-107">[!INCLUDE[ssDE](../../includes/ssde-md.md)] permite o deniega la solicitud en función de si la operación abierta opera con instrucciones DDL, instrucciones DML, la recuperación de los datos o la administración de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="986b4-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] allows or denies the request based on whether the open operation is working with DDL statements, DML statements, retrieving data, or managing transactions.</span></span> <span data-ttu-id="986b4-108">La tabla siguiente muestra cómo [!INCLUDE[ssDE](../../includes/ssde-md.md)] determina si una instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] se permitirá o denegará según el tipo de archivos que se abran en la transacción.</span><span class="sxs-lookup"><span data-stu-id="986b4-108">The following table shows how the [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines whether a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will be allowed or denied based on the type of files that are open in the transaction.</span></span>  
  
|<span data-ttu-id="986b4-109">Instrucciones Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="986b4-109">Transact-SQL statements</span></span>|<span data-ttu-id="986b4-110">Abierto para lectura</span><span class="sxs-lookup"><span data-stu-id="986b4-110">Opened for read</span></span>|<span data-ttu-id="986b4-111">Abierto para escritura</span><span class="sxs-lookup"><span data-stu-id="986b4-111">Opened for write</span></span>|  
|------------------------------|---------------------|----------------------|  
|<span data-ttu-id="986b4-112">Instrucciones DDL que trabajan con los metadatos de la base de datos, como CREATE TABLE, CREATE INDEX, DROP TABLE y ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="986b4-112">DDL statements that work with database metadata, such as CREATE TABLE, CREATE INDEX, DROP TABLE, and ALTER TABLE.</span></span>|<span data-ttu-id="986b4-113">Permitida</span><span class="sxs-lookup"><span data-stu-id="986b4-113">Allowed</span></span>|<span data-ttu-id="986b4-114">Se bloquean y agotan el tiempo de espera con un error.</span><span class="sxs-lookup"><span data-stu-id="986b4-114">Are blocked and fail with a time-out.</span></span>|  
|<span data-ttu-id="986b4-115">Instrucciones DML que trabajan con los datos que están almacenados en la base de datos, como UPDATE, DELETE e INSERT.</span><span class="sxs-lookup"><span data-stu-id="986b4-115">DML statements that work with the data that is stored in the database, such as UPDATE, DELETE, and INSERT.</span></span>|<span data-ttu-id="986b4-116">Permitida</span><span class="sxs-lookup"><span data-stu-id="986b4-116">Allowed</span></span>|<span data-ttu-id="986b4-117">Denegado</span><span class="sxs-lookup"><span data-stu-id="986b4-117">Denied</span></span>|  
|<span data-ttu-id="986b4-118">SELECT</span><span class="sxs-lookup"><span data-stu-id="986b4-118">SELECT</span></span>|<span data-ttu-id="986b4-119">Permitida</span><span class="sxs-lookup"><span data-stu-id="986b4-119">Allowed</span></span>|<span data-ttu-id="986b4-120">Permitida</span><span class="sxs-lookup"><span data-stu-id="986b4-120">Allowed</span></span>|  
|<span data-ttu-id="986b4-121">COMMIT TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="986b4-121">COMMIT TRANSACTION</span></span>|<span data-ttu-id="986b4-122">Denegado\*</span><span class="sxs-lookup"><span data-stu-id="986b4-122">Denied\*</span></span>|<span data-ttu-id="986b4-123">Denegado\*</span><span class="sxs-lookup"><span data-stu-id="986b4-123">Denied\*.</span></span>|  
|<span data-ttu-id="986b4-124">SAVE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="986b4-124">SAVE TRANSACTION</span></span>|<span data-ttu-id="986b4-125">Denegado\*</span><span class="sxs-lookup"><span data-stu-id="986b4-125">Denied\*</span></span>|<span data-ttu-id="986b4-126">Denegado\*</span><span class="sxs-lookup"><span data-stu-id="986b4-126">Denied\*</span></span>|  
|<span data-ttu-id="986b4-127">ROLLBACK</span><span class="sxs-lookup"><span data-stu-id="986b4-127">ROLLBACK</span></span>|<span data-ttu-id="986b4-128">Permitido\*</span><span class="sxs-lookup"><span data-stu-id="986b4-128">Allowed\*</span></span>|<span data-ttu-id="986b4-129">Permitido\*</span><span class="sxs-lookup"><span data-stu-id="986b4-129">Allowed\*</span></span>|  
  
 <span data-ttu-id="986b4-130">\* La transacción se cancela y se invalidan los identificadores abiertos para el contexto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="986b4-130">\* The transaction is canceled, and open handles for the transaction context are invalidated.</span></span> <span data-ttu-id="986b4-131">La aplicación debe cerrar todos los identificadores abiertos.</span><span class="sxs-lookup"><span data-stu-id="986b4-131">The application must close all open handles.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="986b4-132">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="986b4-132">Examples</span></span>  
 <span data-ttu-id="986b4-133">Los ejemplos siguientes muestran cómo las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] y el acceso FILESTREAM de Win32 pueden producir conflictos.</span><span class="sxs-lookup"><span data-stu-id="986b4-133">The following examples show how [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and FILESTREAM Win32 access can cause conflicts.</span></span>  
  
### <a name="a-opening-a-filestream-blob-for-write-access"></a><span data-ttu-id="986b4-134">A.</span><span class="sxs-lookup"><span data-stu-id="986b4-134">A.</span></span> <span data-ttu-id="986b4-135">Abrir un BLOB de FILESTREAM para acceso de escritura</span><span class="sxs-lookup"><span data-stu-id="986b4-135">Opening a FILESTREAM BLOB for write access</span></span>  
 <span data-ttu-id="986b4-136">En el ejemplo siguiente se muestra el efecto de abrir únicamente un archivo para acceso de escritura.</span><span class="sxs-lookup"><span data-stu-id="986b4-136">The following example shows the effect of opening a file for write access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//Write some date to the FILESTREAM BLOB.  
WriteFile(dstHandle, updateData, ...);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed. The FILESTREAM BLOB is  
//returned without the modifications that are made by  
//WriteFile(dstHandle, updateData, ...).  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed. The FILESTREAM BLOB  
//is returned with the updateData applied.  
```  
  
### <a name="b-opening-a-filestream-blob-for-read-access"></a><span data-ttu-id="986b4-137">B.</span><span class="sxs-lookup"><span data-stu-id="986b4-137">B.</span></span> <span data-ttu-id="986b4-138">Abrir un BLOB de FILESTREAM para acceso de lectura</span><span class="sxs-lookup"><span data-stu-id="986b4-138">Opening a FILESTREAM BLOB for read access</span></span>  
 <span data-ttu-id="986b4-139">En el ejemplo siguiente se muestra el efecto de abrir únicamente un archivo para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="986b4-139">The following example shows the effect of opening a file for read access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed. Any changes that are  
//made to the FILESTREAM BLOB will not be returned until  
//the dstHandle is closed.  
//SELECT statements will be allowed.  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="c-opening-and-closing-multiple-filestream-blob-files"></a><span data-ttu-id="986b4-140">C.</span><span class="sxs-lookup"><span data-stu-id="986b4-140">C.</span></span> <span data-ttu-id="986b4-141">Abrir y cerrar varios archivos BLOB de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="986b4-141">Opening and closing multiple FILESTREAM BLOB files</span></span>  
 <span data-ttu-id="986b4-142">Si hay varios archivos abiertos, se usa la regla más restrictiva.</span><span class="sxs-lookup"><span data-stu-id="986b4-142">If multiple files are open, the most restrictive rule is used.</span></span> <span data-ttu-id="986b4-143">En el ejemplo siguiente se abren dos archivos.</span><span class="sxs-lookup"><span data-stu-id="986b4-143">The following example opens two files.</span></span> <span data-ttu-id="986b4-144">El primero se abre durante la lectura y el segundo para la escritura.</span><span class="sxs-lookup"><span data-stu-id="986b4-144">The first file is opened for read and the second for write.</span></span> <span data-ttu-id="986b4-145">Se denegarán las instrucciones DML hasta que se abra el segundo archivo.</span><span class="sxs-lookup"><span data-stu-id="986b4-145">DML statements will be denied until the second file is opened.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
  
dstHandle1 =  OpenSqlFilestream(dstFilePath1, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
//Close the read handle. The write handle is still open.  
CloseHandle(dstHandle);  
//DML statements are still denied because the write handle is open.  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
CloseHandle(dstHandle1);  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="d-failing-to-close-a-cursor"></a><span data-ttu-id="986b4-146">D.</span><span class="sxs-lookup"><span data-stu-id="986b4-146">D.</span></span> <span data-ttu-id="986b4-147">No se puede cerrar un cursor</span><span class="sxs-lookup"><span data-stu-id="986b4-147">Failing to close a cursor</span></span>  
 <span data-ttu-id="986b4-148">El ejemplo siguiente muestra cómo un cursor de instrucción que no se cierra puede evitar que `OpenSqlFilestream()` abra el BLOB para acceso de escritura.</span><span class="sxs-lookup"><span data-stu-id="986b4-148">The following example shows how a statement cursor that is not closed can prevent `OpenSqlFilestream()` from opening the BLOB for write access.</span></span>  
  
```  
TCHAR *sqlDBQuery =  
TEXT("SELECT GET_FILESTREAM_TRANSACTION_CONTEXT(),")  
TEXT("Chart.PathName() FROM Archive.dbo.Records");  
  
//Execute a long-running Transact-SQL statement. Do not allow  
//the statement to complete before trying to  
//open the file.  
  
SQLExecDirect(hstmt, sqlDBQuery, SQL_NTS);  
  
//Before you call OpenSqlFilestream() any open files  
//that the Cursor the Transact-SQL statement is using  
// must be closed. In this example,  
//SQLCloseCursor(hstmt) is not called so that  
//the transaction will indicate that there is a file  
//open for reading. This will cause the call to  
//OpenSqlFilestream() to fail because the file is  
//still open.  
  
HANDLE srcHandle =  OpenSqlFilestream(srcFilePath,  
     Write, 0,  transactionToken,  cbTransactionToken,  0);  
  
//srcHandle will == INVALID_HANDLE_VALUE because the  
//cursor is still open.  
```  
  
## <a name="see-also"></a><span data-ttu-id="986b4-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="986b4-149">See Also</span></span>  
 <span data-ttu-id="986b4-150">[Obtener acceso a los datos FILESTREAM con OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="986b4-150">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="986b4-151">Usar conjuntos de resultados activos múltiples &#40;MARS&#41;</span><span class="sxs-lookup"><span data-stu-id="986b4-151">Using Multiple Active Result Sets &#40;MARS&#41;</span></span>](../native-client/features/using-multiple-active-result-sets-mars.md)  
  
  
