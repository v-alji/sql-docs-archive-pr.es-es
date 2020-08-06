---
title: Asignar relaciones de varios a varios (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], many-to-many
- junction tables [SQL Server]
- many-to-many relationships [SQL Server]
- mapping many-to-many relationships [SQL Server]
- database diagrams [SQL Server], relationships
ms.assetid: 2977cf92-98b5-48b2-b0fd-8fbc7040f2b4
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbcbdbdf8d8371baa2a817e43b831535723be7ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676794"
---
# <a name="map-many-to-many-relationships-visual-database-tools"></a><span data-ttu-id="9dfa3-102">Asignar relaciones varios a varios (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9dfa3-102">Map Many-to-Many Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="9dfa3-103">Las relaciones varios a varios permiten relacionar cada fila de una tabla con muchas filas de otra tabla y viceversa.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-103">Many-to-many relationships let you relate each row in one table to many rows in another table, and vice versa.</span></span> <span data-ttu-id="9dfa3-104">Por ejemplo, puede crear una relación varios a varios entre la tabla `authors` y la tabla `titles` para asociar a cada autor con todos sus libros y a cada libro con todos sus autores.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-104">For example, you could create a many-to-many relationship between the `authors` table and the `titles` table to match each author to all of his or her books and to match each book to all of its authors.</span></span> <span data-ttu-id="9dfa3-105">Si se crea una relación uno a varios desde cada tabla, se indicaría incorrectamente que cada libro tiene un solo autor o que cada autor solo puede escribir un libro.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-105">Creating a one-to-many relationship from either table would incorrectly indicate that every book can have only one author, or that every author can write only one book.</span></span>  
  
 <span data-ttu-id="9dfa3-106">Las relaciones varios a varios entre tablas se implementan en las bases de datos mediante tablas de unión.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-106">Many-to-many relationships between tables are accommodated in databases by means of junction tables.</span></span> <span data-ttu-id="9dfa3-107">Una tabla de unión contiene las columnas de clave principal de las dos tablas que desea relacionar.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-107">A junction table contains the primary key columns of the two tables you want to relate.</span></span> <span data-ttu-id="9dfa3-108">Después debe crear una relación entre las columnas de clave principal de cada una de las dos tablas y las columnas coincidentes en la tabla de unión.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-108">You then create a relationship from the primary key columns of each of those two tables to the matching columns in the junction table.</span></span> <span data-ttu-id="9dfa3-109">En la base datos pubs, la tabla `titleauthor` es una tabla de unión.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-109">In the pubs database, the `titleauthor` table is a junction table.</span></span>  
  
### <a name="to-create-a-many-to-many-relationship-between-tables"></a><span data-ttu-id="9dfa3-110">Para crear una relación varios a varios entre tablas</span><span class="sxs-lookup"><span data-stu-id="9dfa3-110">To create a many-to-many relationship between tables</span></span>  
  
1.  <span data-ttu-id="9dfa3-111">Agregue en el diagrama de base de datos las tablas entre las que desea crear una relación varios a varios.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-111">In your database diagram, add the tables that you want to create a many-to-many relationship between.</span></span>  
  
2.  <span data-ttu-id="9dfa3-112">Cree una tercera tabla; para ello, haga clic con el botón derecho en el diagrama y elija **Nueva tabla** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-112">Create a third table by right-clicking the diagram and choosing **New Table** from the shortcut menu.</span></span> <span data-ttu-id="9dfa3-113">Se convertirá en la tabla de unión.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-113">This will become the junction table.</span></span>  
  
3.  <span data-ttu-id="9dfa3-114">En el cuadro de diálogo **Elegir nombre** , cambie el nombre de tabla asignado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-114">In the **Choose Name** dialog box, change the system-assigned table name.</span></span> <span data-ttu-id="9dfa3-115">Por ejemplo, la tabla de unión situada entre la tabla `titles` y la tabla `authors` se denomina ahora `titleauthors`.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-115">For example, the junction table between the `titles` table and the `authors` table is now named `titleauthors`.</span></span>  
  
4.  <span data-ttu-id="9dfa3-116">Copie las columnas de clave principal de cada una de las otras dos tablas en la tabla de unión.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-116">Copy the primary key columns from each of the other two tables to the junction table.</span></span> <span data-ttu-id="9dfa3-117">Puede agregar otras columnas a esta tabla, así como a cualquier otra tabla.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-117">You can add other columns to this table, just as you can to any other table.</span></span>  
  
5.  <span data-ttu-id="9dfa3-118">En la tabla de unión, establezca la clave principal para incluir todas las columnas de clave principal de las otras dos tablas.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-118">In the junction table, set the primary key to include all the primary key columns from the other two tables.</span></span> <span data-ttu-id="9dfa3-119">Para obtener más información, consulte [Create Primary Keys](../../relational-databases/tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="9dfa3-119">For details, see [Create Primary Keys](../../relational-databases/tables/create-primary-keys.md).</span></span>  
  
6.  <span data-ttu-id="9dfa3-120">Defina una relación uno a varios entre las dos tablas principales y la tabla de unión.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-120">Define a one-to-many relationship between each of the two primary tables and the junction table.</span></span> <span data-ttu-id="9dfa3-121">La tabla de unión debe estar en el lado "varios" de las dos relaciones que cree.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-121">The junction table should be at the "many" side of both of the relationships you create.</span></span> <span data-ttu-id="9dfa3-122">Para obtener más información, vea [crear relaciones de clave externa](../../relational-databases/tables/create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="9dfa3-122">For details, see [Create Foreign Key Relationships](../../relational-databases/tables/create-foreign-key-relationships.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9dfa3-123">Al crear una tabla de unión en un diagrama de base de datos, no se insertan datos de las tablas relacionadas en la tabla de unión.</span><span class="sxs-lookup"><span data-stu-id="9dfa3-123">The creation of a junction table in a database diagram does not insert data from the related tables into the junction table.</span></span> <span data-ttu-id="9dfa3-124">Para más información sobre cómo insertar datos en una tabla, consulte [Crear consultas de inserción de resultados &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9dfa3-124">For information about inserting data into a table, see [Create Insert Results Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dfa3-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9dfa3-125">See Also</span></span>  
 [<span data-ttu-id="9dfa3-126">Trabajar con diagramas de base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9dfa3-126">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](work-with-database-diagrams-visual-database-tools.md)  
  
  
