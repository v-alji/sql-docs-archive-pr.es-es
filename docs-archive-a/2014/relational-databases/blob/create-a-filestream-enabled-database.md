---
title: Creación de una base de datos habilitada para FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FILESTREAM-enabled databases
ms.assetid: 0fc16356-76f7-44b8-a58b-f0b7c43694ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0fe6e5bc6e4f60bc0703482f3bf4d761104b3c5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746307"
---
# <a name="create-a-filestream-enabled-database"></a><span data-ttu-id="1b8db-102">crear una base de datos habilitada para FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="1b8db-102">Create a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="1b8db-103">En este tema se muestra la forma de crear una base de datos que admite FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="1b8db-103">This topic shows how to create a database that supports FILESTREAM.</span></span> <span data-ttu-id="1b8db-104">Dado que FILESTREAM utiliza un tipo especial de grupo de archivos, cuando cree la base de datos, debe especificar la cláusula CONTAINS FILESTREAM para un grupo de archivos como mínimo.</span><span class="sxs-lookup"><span data-stu-id="1b8db-104">Because FILESTREAM uses a special type of filegroup, when you create the database, you must specify the CONTAINS FILESTREAM clause for at least one filegroup.</span></span>  
  
 <span data-ttu-id="1b8db-105">Un grupo de archivos FILESTREAM puede contener más de un archivo.</span><span class="sxs-lookup"><span data-stu-id="1b8db-105">A FILESTREAM filegroup can contain more than one file.</span></span> <span data-ttu-id="1b8db-106">Para obtener un ejemplo de código en el que se muestra cómo crear un grupo de archivos FILESTREAM que contiene varios archivos, vea [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1b8db-106">For a code example that demonstrates how to create a FILESTREAM filegroup that contains multiple files, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
### <a name="to-create-a-filestream-enabled-database"></a><span data-ttu-id="1b8db-107">Para crear una base de datos habilitada para FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="1b8db-107">To create a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="1b8db-108">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], haga clic en **Nueva consulta** para mostrar el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="1b8db-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="1b8db-109">Copiar el [!INCLUDE[tsql](../../includes/tsql-md.md)] código crea una base de datos habilitada para FileStream denominada Archive.</span><span class="sxs-lookup"><span data-stu-id="1b8db-109">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled database called Archive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1b8db-110">Para este script, debe existir el directorio C:\Data.</span><span class="sxs-lookup"><span data-stu-id="1b8db-110">For this script, the directory C:\Data must exist.</span></span>  
  
3.  <span data-ttu-id="1b8db-111">Para generar la base de datos, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1b8db-111">To build the database, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b8db-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b8db-112">Example</span></span>  
 <span data-ttu-id="1b8db-113">En el ejemplo de código siguiente se crea una base de datos con el nombre de `Archive`.</span><span class="sxs-lookup"><span data-stu-id="1b8db-113">The following code example creates a database that is named `Archive`.</span></span> <span data-ttu-id="1b8db-114">La base de datos contiene tres grupos de archivos: `PRIMARY`, `Arch1`y `FileStreamGroup1`.</span><span class="sxs-lookup"><span data-stu-id="1b8db-114">The database contains three filegroups: `PRIMARY`, `Arch1`, and `FileStreamGroup1`.</span></span> <span data-ttu-id="1b8db-115">`PRIMARY` and `Arch1` son grupos de archivos normales que no pueden contener datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="1b8db-115">`PRIMARY` and `Arch1` are regular filegroups that cannot contain FILESTREAM data.</span></span> <span data-ttu-id="1b8db-116">`FileStreamGroup1` es el grupo de archivos `FILESTREAM` .</span><span class="sxs-lookup"><span data-stu-id="1b8db-116">`FileStreamGroup1` is the `FILESTREAM` filegroup.</span></span>  
  
```sql  
CREATE DATABASE Archive   
ON  
PRIMARY ( NAME = Arch1,  
    FILENAME = 'c:\data\archdat1.mdf'),  
FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
    FILENAME = 'c:\data\filestream1')  
LOG ON  ( NAME = Archlog1,  
    FILENAME = 'c:\data\archlog1.ldf')  
GO  
```  
  
 <span data-ttu-id="1b8db-117">Para un grupo de archivos `FILESTREAM` , `FILENAME` hace referencia a una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="1b8db-117">For a `FILESTREAM` filegroup, `FILENAME` refers to a path.</span></span> <span data-ttu-id="1b8db-118">La ruta de acceso hasta la última carpeta debe existir y la última carpeta no debe existir.</span><span class="sxs-lookup"><span data-stu-id="1b8db-118">The path up to the last folder must exist, and the last folder must not exist.</span></span> <span data-ttu-id="1b8db-119">En este ejemplo, `c:\data` debe existir.</span><span class="sxs-lookup"><span data-stu-id="1b8db-119">In this example, `c:\data` must exist.</span></span> <span data-ttu-id="1b8db-120">Sin embargo, la subcarpeta `filestream1` no puede existir al ejecutar la instrucción `CREATE DATABASE` .</span><span class="sxs-lookup"><span data-stu-id="1b8db-120">However, the `filestream1` subfolder cannot exist when you execute the `CREATE DATABASE` statement.</span></span> <span data-ttu-id="1b8db-121">Para obtener más información sobre la sintaxis, vea [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1b8db-121">For more information about the syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
 <span data-ttu-id="1b8db-122">Después de ejecutar el ejemplo anterior, aparecen un archivo filestream.hdr y una carpeta $FSLOG en la carpeta c:\Data\filestream1.</span><span class="sxs-lookup"><span data-stu-id="1b8db-122">After you run the previous example, a filestream.hdr file and an $FSLOG folder appears in the c:\Data\filestream1 folder.</span></span> <span data-ttu-id="1b8db-123">El archivo filestream.hdr es un archivo de encabezado para el contenedor de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="1b8db-123">The filestream.hdr file is a header file for the FILESTREAM container.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1b8db-124">El archivo filestream.hdr es un archivo de sistema importante.</span><span class="sxs-lookup"><span data-stu-id="1b8db-124">The filestream.hdr file is an important system file.</span></span> <span data-ttu-id="1b8db-125">Contiene información de encabezado de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="1b8db-125">It contains FILESTREAM header information.</span></span> <span data-ttu-id="1b8db-126">No quite ni modifique este archivo.</span><span class="sxs-lookup"><span data-stu-id="1b8db-126">Do not remove or modify this file.</span></span>  
  
 <span data-ttu-id="1b8db-127">Para las bases de datos existentes, puede usar la instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) para agregar un grupo de archivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="1b8db-127">For existing databases, you can use the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to add a FILESTREAM filegroup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8db-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b8db-128">See Also</span></span>  
 <span data-ttu-id="1b8db-129">[CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1b8db-129">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="1b8db-130">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b8db-130">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
