---
title: Importar de forma masiva datos de objetos de gran tamaño mediante el proveedor de conjuntos de filas bulk OPENROWSET (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- SINGLE_NCLOB option
- bulk rowset providers [SQL Server]
- bulk importing [SQL Server], data formats
- OPENROWSET function, bulk importing large data
- SINGLE_CLOB option
- data formats [SQL Server], large-object data
- large data, bulk imports
- SINGLE_BLOB option
ms.assetid: 171cdd5c-1e47-4bd7-b99a-4f0fd4e10526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0f43aa2fa5e7f7ef0b2c8f1f6e5e6ff28e02f9f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671991"
---
# <a name="bulk-import-large-object-data-by-using-the-openrowset-bulk-rowset-provider-sql-server"></a><span data-ttu-id="c204a-102">Importar de forma masiva datos de objetos de gran tamaño mediante el proveedor de conjuntos de filas BULK OPENROWSET (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c204a-102">Bulk Import Large-Object Data by using the OPENROWSET Bulk Rowset Provider (SQL Server)</span></span>
  <span data-ttu-id="c204a-103">El proveedor de conjuntos de filas BULK OPENROWSET de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite realizar la importación masiva de un archivo de datos como datos de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="c204a-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OPENROWSET Bulk Rowset Provider enables you to bulk import a data file as large-object data.</span></span>  
  
 <span data-ttu-id="c204a-104">Los tipos de datos de objetos grandes admitidos por el proveedor de conjuntos de filas BULK OPENROWSET son: **varbinary**(max) o **image**, **varchar**(max) o **text**, y **nvarchar**(max) o **ntext**.</span><span class="sxs-lookup"><span data-stu-id="c204a-104">The large-object data types supported by OPENROWSET Bulk Rowset Provider are **varbinary**(max) or **image**, **varchar**(max) or **text**, and **nvarchar**(max) or **ntext**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c204a-105">Los tipos de datos **image**, **text** y **ntext** han quedado en desuso.</span><span class="sxs-lookup"><span data-stu-id="c204a-105">The **image**, **text** and **ntext** data types are deprecated.</span></span>  
  
 <span data-ttu-id="c204a-106">La cláusula BULK de OPENROWSET admite tres opciones para importar el contenido de un archivo de datos como un conjunto de filas de fila única y columna única.</span><span class="sxs-lookup"><span data-stu-id="c204a-106">The OPENROWSET BULK clause supports three options for importing the contents of a data file as a single-row, single-column rowset.</span></span> <span data-ttu-id="c204a-107">Puede especificar una de estas opciones de objetos grandes en lugar de usar un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="c204a-107">You can specify one of these large-object options instead of using a format file.</span></span> <span data-ttu-id="c204a-108">Las opciones son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c204a-108">These options are as follows:</span></span>  
  
 <span data-ttu-id="c204a-109">SINGLE_BLOB</span><span class="sxs-lookup"><span data-stu-id="c204a-109">SINGLE_BLOB</span></span>  
 <span data-ttu-id="c204a-110">Lee el contenido de *data_file* como un archivo de una sola fila y devuelve el contenido como un conjunto de filas de una sola columna del tipo **varbinary(max)** .</span><span class="sxs-lookup"><span data-stu-id="c204a-110">Reads the contents of *data_file* as a single-row, returns the contents as a single-column rowset of type **varbinary(max)**.</span></span>  
  
 <span data-ttu-id="c204a-111">SINGLE_CLOB</span><span class="sxs-lookup"><span data-stu-id="c204a-111">SINGLE_CLOB</span></span>  
 <span data-ttu-id="c204a-112">Lee el contenido del archivo de datos especificado como caracteres y devuelve el contenido como un conjunto de filas de una sola fila y una sola columna del tipo **varchar(max)** , mediante la intercalación de la base de datos actual, como un documento de texto o de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word.</span><span class="sxs-lookup"><span data-stu-id="c204a-112">Reads the contents of the specified data file as characters, returns the contents as a single-row, single-column rowset of type **varchar(max)**, using the collation of the current database; such as a text or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word document.</span></span>  
  
 <span data-ttu-id="c204a-113">SINGLE_NCLOB</span><span class="sxs-lookup"><span data-stu-id="c204a-113">SINGLE_NCLOB</span></span>  
 <span data-ttu-id="c204a-114">Lee el contenido del archivo de datos especificado como Unicode y devuelve el contenido como un conjunto de filas de una sola fila y una sola columna del tipo **nvarchar(max)** , mediante la intercalación de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="c204a-114">Reads the contents of the specified data file as Unicode, returns the contents as a single-row, single-column rowset of type **nvarchar(max)**, using the collation of the current database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c204a-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c204a-115">See Also</span></span>  
 <span data-ttu-id="c204a-116">[Importación en bloque de datos mediante las instrucciones BULK INSERT u OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c204a-116">[Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span></span>  
 <span data-ttu-id="c204a-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c204a-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="c204a-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c204a-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="c204a-119">[Mantener valores NULL o usar valores predeterminados durante la importación en bloque &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c204a-119">[Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span></span>  
 <span data-ttu-id="c204a-120">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c204a-120">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="c204a-121">BULK INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c204a-121">BULK INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/bulk-insert-transact-sql)  
  
  
