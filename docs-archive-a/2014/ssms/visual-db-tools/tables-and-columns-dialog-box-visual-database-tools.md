---
title: Tablas y columnas (cuadro de diálogo, Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.tablesandcolumns
ms.assetid: 8cf27be1-e66d-4735-a428-9ab4b33af4f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28e0c52b74413a3a5a4122412c6028b34e974b09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676291"
---
# <a name="tables-and-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="f3343-102">Tablas y columnas (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="f3343-102">Tables and Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="f3343-103">Utilice este cuadro de diálogo para asignar una clave principal de una tabla a una clave externa de otra.</span><span class="sxs-lookup"><span data-stu-id="f3343-103">Use this dialog box to map a primary key in one table to a foreign key in another.</span></span> <span data-ttu-id="f3343-104">Para obtener acceso a este cuadro de diálogo, en el menú **Diseñador de tablas** haga clic en **Relaciones**.</span><span class="sxs-lookup"><span data-stu-id="f3343-104">To access this dialog box, from the **Table Designer** menu, click **Relationships**.</span></span> <span data-ttu-id="f3343-105">En el cuadro de diálogo **Relaciones de clave externa**, haga clic en el campo **Especificación de tablas y columnas** y, luego, haga clic en los puntos suspensivos **(...)** que aparecen a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3343-105">In the **Foreign Key Relationships** dialog box, click the **Tables and Columns Specification** field, and then click the ellipses **(...)** to the right of the property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3343-106">Si se publica la tabla para la replicación, debe modificar el esquema mediante la instrucción Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) u Objetos de administración de SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="f3343-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="f3343-107">Si se modifica el esquema mediante el Diseñador de tablas o el Diseñador de diagramas de base de datos, se intentará eliminar la tabla y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="f3343-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="f3343-108">No se pueden eliminar objetos publicados, por lo que la modificación del esquema generará un error.</span><span class="sxs-lookup"><span data-stu-id="f3343-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f3343-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="f3343-109">Options</span></span>  
 <span data-ttu-id="f3343-110">**Nombre de relación**</span><span class="sxs-lookup"><span data-stu-id="f3343-110">**Relationship name**</span></span>  
 <span data-ttu-id="f3343-111">Muestra el nombre de relación.</span><span class="sxs-lookup"><span data-stu-id="f3343-111">Shows the name of the relationship.</span></span>  
  
 <span data-ttu-id="f3343-112">**Tabla de clave principal**</span><span class="sxs-lookup"><span data-stu-id="f3343-112">**Primary Key Table**</span></span>  
 <span data-ttu-id="f3343-113">Enumera las tablas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f3343-113">Lists the tables in the database.</span></span> <span data-ttu-id="f3343-114">Elija la tabla que estará en el lado de la clave principal de la relación.</span><span class="sxs-lookup"><span data-stu-id="f3343-114">Choose the table that will be on the primary-key side of the relationship.</span></span>  
  
 <span data-ttu-id="f3343-115">**Tabla de clave externa**</span><span class="sxs-lookup"><span data-stu-id="f3343-115">**Foreign Key Table**</span></span>  
 <span data-ttu-id="f3343-116">Muestra la tabla del lado de la clave externa de la relación.</span><span class="sxs-lookup"><span data-stu-id="f3343-116">Shows the table on the foreign key side of the relationship.</span></span> <span data-ttu-id="f3343-117">Ésta es la tabla que está actualmente seleccionada en el Diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="f3343-117">This is the table currently selected in Table Designer.</span></span>  
  
 <span data-ttu-id="f3343-118">**Cuadrícula debajo de la tabla de clave principal**</span><span class="sxs-lookup"><span data-stu-id="f3343-118">**Grid beneath Primary Key Table**</span></span>  
 <span data-ttu-id="f3343-119">Enumere las columnas de la tabla seleccionada en la lista **Tabla de clave principal** .</span><span class="sxs-lookup"><span data-stu-id="f3343-119">List the columns of the table selected in the **Primary Key Table** list.</span></span> <span data-ttu-id="f3343-120">Especifique las columnas que contribuyen a la clave principal de esa tabla.</span><span class="sxs-lookup"><span data-stu-id="f3343-120">Enter the columns contributing to that table's primary key.</span></span>  
  
 <span data-ttu-id="f3343-121">**Cuadrícula debajo de la tabla de clave externa**</span><span class="sxs-lookup"><span data-stu-id="f3343-121">**Grid beneath Foreign Key Table**</span></span>  
 <span data-ttu-id="f3343-122">Enumere las columnas de la tabla seleccionada en la lista **Tabla de clave externa** .</span><span class="sxs-lookup"><span data-stu-id="f3343-122">List the columns of the table selected in the **Foreign Key Table** list.</span></span> <span data-ttu-id="f3343-123">Especifique la columna de clave externa de la tabla de clave externa que corresponde a la columna de clave principal.</span><span class="sxs-lookup"><span data-stu-id="f3343-123">Enter the foreign-key column of the foreign-key table that corresponds to the primary key column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3343-124">Las columnas que elija para la clave externa deben tener el mismo tipo de datos que las columnas principales correspondientes.</span><span class="sxs-lookup"><span data-stu-id="f3343-124">The columns you choose for the foreign key must have the same data type of the primary columns they correspond to.</span></span> <span data-ttu-id="f3343-125">Debe haber un número igual de columnas en cada una de las claves.</span><span class="sxs-lookup"><span data-stu-id="f3343-125">There must be an equal number of columns in each of the keys.</span></span> <span data-ttu-id="f3343-126">Por ejemplo, si la clave principal de la tabla en el lado principal de la relación se compone de dos columnas, necesitará hacer coincidir cada una de esas columnas con una columna de la tabla del lado de la clave externa de la relación.</span><span class="sxs-lookup"><span data-stu-id="f3343-126">For example, if the primary key of the table on the primary side of the relationship is made up of two columns, you will need to match each of those columns with a column in the table for the foreign key side of the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3343-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3343-127">See Also</span></span>  
 [<span data-ttu-id="f3343-128">Crear relaciones de clave externa</span><span class="sxs-lookup"><span data-stu-id="f3343-128">Create Foreign Key Relationships</span></span>](../../relational-databases/tables/create-foreign-key-relationships.md)  
  
  
