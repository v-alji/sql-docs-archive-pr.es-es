---
title: Creación de una tabla para almacenar datos FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], table storage
ms.assetid: 029c3059-5c83-43e2-a859-9027031b7de1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 484d7b58ce949df79dc7e17ee4dc7307b70c0154
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745822"
---
# <a name="create-a-table-for-storing-filestream-data"></a><span data-ttu-id="04bf1-102">Crear una tabla para almacenar datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="04bf1-102">Create a Table for Storing FILESTREAM Data</span></span>
  <span data-ttu-id="04bf1-103">En este tema se muestra cómo crear una tabla para almacenar datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="04bf1-103">This topic shows how to create a table for storing FILESTREAM data.</span></span>  
  
 <span data-ttu-id="04bf1-104">Cuando la base de datos tiene un grupo de archivos FILESTREAM, es posible crear o modificar tablas para almacenar datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="04bf1-104">When the database has a FILESTREAM filegroup, you can create or modify tables to store FILESTREAM data.</span></span> <span data-ttu-id="04bf1-105">Para especificar que una columna contiene datos FILESTREAM, se ha de crear una columna `varbinary(max)` y agregar el atributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="04bf1-105">To specify that a column contains FILESTREAM data, you create a `varbinary(max)` column and add the FILESTREAM attribute.</span></span>  
  
### <a name="to-create-a-table-to-store-filestream-data"></a><span data-ttu-id="04bf1-106">Para crear una tabla para almacenar datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="04bf1-106">To create a table to store FILESTREAM data</span></span>  
  
1.  <span data-ttu-id="04bf1-107">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], haga clic en **Nueva consulta** para mostrar el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="04bf1-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="04bf1-108">Copie el código [!INCLUDE[tsql](../../includes/tsql-md.md)] del ejemplo siguiente en el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="04bf1-108">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code from the following example into the Query Editor.</span></span> <span data-ttu-id="04bf1-109">Este código [!INCLUDE[tsql](../../includes/tsql-md.md)] crea una tabla habilitada para FILESTREAM denominada Records.</span><span class="sxs-lookup"><span data-stu-id="04bf1-109">This [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled table called Records.</span></span>  
  
3.  <span data-ttu-id="04bf1-110">Para crear la tabla, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="04bf1-110">To create the table, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04bf1-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04bf1-111">Example</span></span>  
 <span data-ttu-id="04bf1-112">En el siguiente ejemplo de código se muestra cómo crear una tabla denominada `Records`.</span><span class="sxs-lookup"><span data-stu-id="04bf1-112">The following code example shows how to create a table that is named `Records`.</span></span> <span data-ttu-id="04bf1-113">La columna `Id` es una columna `ROWGUIDCOL` y es necesaria para usar datos FILESTREAM con las API de Win32.</span><span class="sxs-lookup"><span data-stu-id="04bf1-113">The `Id` column is a `ROWGUIDCOL` column and is required to use FILESTREAM data with Win32 APIs.</span></span> <span data-ttu-id="04bf1-114">La columna `SerialNumber` es una columna `UNIQUE INTEGER`.</span><span class="sxs-lookup"><span data-stu-id="04bf1-114">The `SerialNumber` column is a `UNIQUE INTEGER`.</span></span> <span data-ttu-id="04bf1-115">La columna `Chart` es una columna `FILESTREAM` y se usa para almacenar `Chart` en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="04bf1-115">The `Chart` column is a `FILESTREAM` column and is used to store the `Chart` in the file system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04bf1-116">En este ejemplo se hace referencia a la base de datos de archivo que se creó en [Crear una base de datos habilitada para FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="04bf1-116">This example refers to the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
 [!code-sql[FILESTREAM#FS_CreateTable](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_createtable)]  
  
## <a name="see-also"></a><span data-ttu-id="04bf1-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04bf1-117">See Also</span></span>  
 <span data-ttu-id="04bf1-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04bf1-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 [<span data-ttu-id="04bf1-119">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04bf1-119">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
