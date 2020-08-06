---
title: Definir tablas y columnas UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- user-defined types [CLR integration], columns
- UDTs [CLR integration], columns
- columns [CLR integration]
- user-defined types [CLR integration], tables
- tables [CLR integration]
- UDTs [CLR integration], tables
- UDTs [CLR integration], indexes
- user-defined types [CLR integration], indexes
- indexes [CLR integration]
ms.assetid: aea495f4-ce26-4952-b019-38f012625f3f
author: rothja
ms.author: jroth
ms.openlocfilehash: aa9596629ed8b4877b1793fa0c56956c52989499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678206"
---
# <a name="defining-udt-tables-and-columns"></a><span data-ttu-id="174a8-102">Definir tablas y columnas de UDT</span><span class="sxs-lookup"><span data-stu-id="174a8-102">Defining UDT Tables and Columns</span></span>
  <span data-ttu-id="174a8-103">Una vez que el ensamblado que contiene la definición de tipo definido por el usuario (UDT) se ha registrado en una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] base de datos, se puede utilizar en una definición de columna.</span><span class="sxs-lookup"><span data-stu-id="174a8-103">Once the assembly containing the user-defined type (UDT) definition has been registered in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, it can be used in a column definition.</span></span>  
  
## <a name="creating-tables-with-udts"></a><span data-ttu-id="174a8-104">Crear tablas con UDT</span><span class="sxs-lookup"><span data-stu-id="174a8-104">Creating Tables with UDTs</span></span>  
 <span data-ttu-id="174a8-105">No hay ninguna sintaxis especial para crear una columna UDT de una tabla.</span><span class="sxs-lookup"><span data-stu-id="174a8-105">There is no special syntax for creating a UDT column in a table.</span></span> <span data-ttu-id="174a8-106">Puede utilizar el nombre del UDT en una definición de columna como si fuera uno de los tipos de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] intrínsecos.</span><span class="sxs-lookup"><span data-stu-id="174a8-106">You can use the name of the UDT in a column definition as though it were one of the intrinsic [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="174a8-107">La siguiente [!INCLUDE[tsql](../../includes/tsql-md.md)] instrucción CREATE TABLE crea una tabla denominada **Points**, con una columna denominada **ID,** que se define como una `int` columna de identidad y la clave principal de la tabla.</span><span class="sxs-lookup"><span data-stu-id="174a8-107">The following CREATE TABLE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement creates a table named **Points**, with a column named **ID,** which is defined as an `int` identity column and \ the primary key for the table.</span></span> <span data-ttu-id="174a8-108">La segunda columna se denomina **PointValue**, con un tipo de datos **Point**.</span><span class="sxs-lookup"><span data-stu-id="174a8-108">The second column is named **PointValue**, with a data type of **Point**.</span></span> <span data-ttu-id="174a8-109">El nombre de esquema que se usa en este ejemplo es **DBO**.</span><span class="sxs-lookup"><span data-stu-id="174a8-109">The schema name used in this example is **dbo**.</span></span> <span data-ttu-id="174a8-110">Observe que debe tener los permisos necesarios para especificar un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="174a8-110">Note that you must have the necessary permissions to specify a schema name.</span></span> <span data-ttu-id="174a8-111">Si omite el nombre de esquema, se utiliza el esquema predeterminado para el usuario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="174a8-111">If you omit the schema name, the default schema for the database user is used.</span></span>  
  
```  
CREATE TABLE dbo.Points   
(ID int IDENTITY(1,1) PRIMARY KEY, PointValue Point)  
```  
  
## <a name="creating-indexes-on-udt-columns"></a><span data-ttu-id="174a8-112">Crear índices en columnas UDT</span><span class="sxs-lookup"><span data-stu-id="174a8-112">Creating Indexes on UDT Columns</span></span>  
 <span data-ttu-id="174a8-113">Hay dos opciones para indizar una columna UDT:</span><span class="sxs-lookup"><span data-stu-id="174a8-113">There are two options for indexing a UDT column:</span></span>  
  
-   <span data-ttu-id="174a8-114">Indizar el valor completo.</span><span class="sxs-lookup"><span data-stu-id="174a8-114">Index the full value.</span></span> <span data-ttu-id="174a8-115">En este caso, si el UDT es binario ordenado, puede crear un índice sobre la columna UDT completa utilizando la instrucción CREATE INDEX de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="174a8-115">In this case, if the UDT is binary ordered, you can create an index over the entire UDT column by using the CREATE INDEX [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
-   <span data-ttu-id="174a8-116">Indizar las expresiones UDT.</span><span class="sxs-lookup"><span data-stu-id="174a8-116">Index UDT expressions.</span></span> <span data-ttu-id="174a8-117">Puede crear los índices en las columnas calculadas mantenidas en las expresiones UDT.</span><span class="sxs-lookup"><span data-stu-id="174a8-117">You can create indexes on persisted computed columns over UDT expressions.</span></span> <span data-ttu-id="174a8-118">La expresión UDT puede ser un campo, método o propiedad de un UDT.</span><span class="sxs-lookup"><span data-stu-id="174a8-118">The UDT expression can be a field, method, or property of a UDT.</span></span> <span data-ttu-id="174a8-119">La expresión debe ser determinista y no realizar el acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="174a8-119">The expression must be deterministic and must not perform data access.</span></span>  
  
 <span data-ttu-id="174a8-120">Para obtener más información, vea [tipos definidos por el usuario CLR](clr-user-defined-types.md) y [CREATE index &#40;&#41;de Transact-SQL ](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="174a8-120">For more information, see [CLR User-Defined Types](clr-user-defined-types.md) and [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="174a8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="174a8-121">See Also</span></span>  
 [<span data-ttu-id="174a8-122">Trabajar con tipos definidos por el usuario en SQL Server</span><span class="sxs-lookup"><span data-stu-id="174a8-122">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
