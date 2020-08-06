---
title: Trabajar con tablas en diagramas de base de datos (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], tables
- Table Designer, database diagrams
- tables [SQL Server], database diagrams
- database diagrams [SQL Server], Table Designer
ms.assetid: ee2c5d84-22bf-4597-ac70-a27ed8cc94f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: f648cd5fd08ed47c6670491ad5b7f3d75b7ead47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674485"
---
# <a name="work-with-tables-in-database-diagram-visual-database-tools"></a><span data-ttu-id="3f5ab-102">Trabajar con tablas en diagramas de base de datos (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3f5ab-102">Work with Tables in Database Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="3f5ab-103">Puede modificar y crear tablas de base de datos en el Diseñador de tablas o en el Diseñador de diagramas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3f5ab-103">You can modify and create database tables in either Table Designer or Database Diagram Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f5ab-104">Si se publica la tabla para la replicación, debe modificar el esquema mediante la instrucción Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) u Objetos de administración de SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="3f5ab-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="3f5ab-105">Si se modifica el esquema mediante el Diseñador de tablas o el Diseñador de diagramas de base de datos, se intentará eliminar la tabla y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="3f5ab-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="3f5ab-106">No se pueden eliminar objetos publicados, por lo que la modificación del esquema generará un error.</span><span class="sxs-lookup"><span data-stu-id="3f5ab-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f5ab-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3f5ab-107">In This Section</span></span>  
 [<span data-ttu-id="3f5ab-108">Agregar tablas a diagramas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3f5ab-108">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
 [<span data-ttu-id="3f5ab-109">Agregar tablas relacionadas a diagramas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3f5ab-109">Add Related Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-related-tables-to-diagrams-visual-database-tools.md)  
  
 [<span data-ttu-id="3f5ab-110">Guardar tablas seleccionadas en un diagrama &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3f5ab-110">Save Selected Tables on a Diagram &#40;Visual Database Tools&#41;</span></span>](save-selected-tables-on-a-diagram-visual-database-tools.md)  
  
 [<span data-ttu-id="3f5ab-111">Copiar tablas de un diagrama de base de datos a otro &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3f5ab-111">Copy Tables from One Database Diagrams to Another &#40;Visual Database Tools&#41;</span></span>](copy-tables-from-one-database-diagrams-to-another-visual-database-tools.md)  
  
 [<span data-ttu-id="3f5ab-112">Quitar tablas de diagramas de base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3f5ab-112">Remove Tables from Database Diagrams &#40;Visual Database Tools&#41;</span></span>](remove-tables-from-database-diagrams-visual-database-tools.md)  
  
 [<span data-ttu-id="3f5ab-113">Asignar relaciones varios a varios &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3f5ab-113">Map Many-to-Many Relationships &#40;Visual Database Tools&#41;</span></span>](map-many-to-many-relationships-visual-database-tools.md)  
  
 [<span data-ttu-id="3f5ab-114">Dibujar relaciones reflexivas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3f5ab-114">Draw Reflexive Relationships &#40;Visual Database Tools&#41;</span></span>](draw-reflexive-relationships-visual-database-tools.md)  
  
## <a name="reference"></a><span data-ttu-id="3f5ab-115">Referencia</span><span class="sxs-lookup"><span data-stu-id="3f5ab-115">Reference</span></span>  
 [<span data-ttu-id="3f5ab-116">Cuadro de diálogo Agregar tabla &#40;Diseñador de bases de datos&#41; &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3f5ab-116">Add Table Dialog Box &#40;Database Designer&#41; &#40;Visual Database Tools&#41;</span></span>](add-table-dialog-box-database-designer-visual-database-tools.md)  
  
## <a name="related-sections"></a><span data-ttu-id="3f5ab-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3f5ab-117">Related Sections</span></span>  
  
