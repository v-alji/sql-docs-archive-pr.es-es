---
title: Problemas de evolución de bases de datos (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], multuser database changes
- database evolution [SQL Server]
ms.assetid: 1ed6ae10-d212-4ec2-8569-1b94ab1cba6d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80daa694cd015a83657368902b07da254e6196ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749554"
---
# <a name="issues-of-database-evolution-visual-database-tools"></a><span data-ttu-id="dca3c-102">Problemas de evolución de bases de datos (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="dca3c-102">Issues of Database Evolution (Visual Database Tools)</span></span>
  <span data-ttu-id="dca3c-103">Si cambia la estructura de una base de datos implementada, debe tener especial cuidado para que la modificación sea compatible con la estructura de la base de datos y los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="dca3c-103">If you change the structure of a deployed database, you must take special care that your alteration is compatible with the existing data and database structure.</span></span> <span data-ttu-id="dca3c-104">Es posible que tenga que seguir pasos especiales cuando realice las modificaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="dca3c-104">You might need to take special steps when you make the following modifications:</span></span>  
  
-   <span data-ttu-id="dca3c-105">**Agregar una restricción** Si agrega una restricción, es posible que la base de datos ya contenga datos que no la satisfagan.</span><span class="sxs-lookup"><span data-stu-id="dca3c-105">**Adding a Constraint** If you add a constraint, the database might already contain data that does not satisfy it.</span></span> <span data-ttu-id="dca3c-106">Cuando intente guardar la restricción nueva, el [cuadro de diálogo Notificaciones después de guardar &#40;Visual Database Tools&#41;](visual-database-tools.md) le informará que el servidor de base de datos no pudo crear la restricción.</span><span class="sxs-lookup"><span data-stu-id="dca3c-106">When you try to save the new constraint, the [Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not create the constraint.</span></span> <span data-ttu-id="dca3c-107">Para forzar a la base de datos a aceptar la restricción nueva, puede desactivar la casilla **Comprobar datos existentes al crear**.</span><span class="sxs-lookup"><span data-stu-id="dca3c-107">To force the database to accept the new constraint, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="dca3c-108">**Agregar una relación** Si agrega una relación, es posible que la base de datos ya contenga filas de la tabla de clave externa sin filas correspondientes en la tabla de clave principal.</span><span class="sxs-lookup"><span data-stu-id="dca3c-108">**Adding a Relationship** If you add a relationship, the database might already contain rows of the foreign-key table that do not have corresponding rows in the primary-key table.</span></span> <span data-ttu-id="dca3c-109">Es decir, es posible que los datos existentes no satisfagan la integridad referencial.</span><span class="sxs-lookup"><span data-stu-id="dca3c-109">That is, the existing data might not satisfy referential integrity.</span></span> <span data-ttu-id="dca3c-110">Cuando intente guardar la relación nueva, el [cuadro de diálogo Notificaciones después de guardar &#40;Visual Database Tools&#41;](visual-database-tools.md) le informará que el servidor de base de datos no pudo guardar la tabla de clave externa revisada.</span><span class="sxs-lookup"><span data-stu-id="dca3c-110">When you try to save the new relationship, the[Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not save the revised foreign-key table.</span></span> <span data-ttu-id="dca3c-111">Para forzar a la base de datos a aceptar la modificación, puede desactivar la casilla **Comprobar datos existentes al crear**.</span><span class="sxs-lookup"><span data-stu-id="dca3c-111">To force the database to accept the modification, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="dca3c-112">**Modificar una tabla que contribuye a una vista indizada** Si modifica una tabla que contribuye a una vista indizada de Microsoft SQL Server, se perderán los índices de la vista.</span><span class="sxs-lookup"><span data-stu-id="dca3c-112">**Modifying a Table Contributing to an Indexed View** If you modify a table that contributes to a Microsoft SQL Server indexed view, the indexes on the view will be lost.</span></span> <span data-ttu-id="dca3c-113">Vea los Libros en pantalla de SQL Server para obtener información sobre cómo volver a crear ííndices.</span><span class="sxs-lookup"><span data-stu-id="dca3c-113">See the SQL Server Books Online for information on recreating indexes.</span></span>  
  
-   <span data-ttu-id="dca3c-114">**Eliminar un objeto** Si elimina un objeto, como una columna, una tabla o una vista, primero asegúrese de no hay ningún otro objeto en la base de datos que contenga una referencia a ese objeto.</span><span class="sxs-lookup"><span data-stu-id="dca3c-114">**Deleting an Object** If you delete an object, such as a column, table, or view, check first to be sure that the object is not referenced by another object in the database.</span></span>  
  
 <span data-ttu-id="dca3c-115">Independientemente de la manera en que se modifique el diseño de base de datos, debe conservar un historial de las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="dca3c-115">No matter how you alter the database design, you should retain a history of the alterations.</span></span> <span data-ttu-id="dca3c-116">Una posibilidad es conservar scripts SQL para todas las modificaciones que haya realizado en la base de datos de producción.</span><span class="sxs-lookup"><span data-stu-id="dca3c-116">One approach is to retain SQL scripts for all modifications that you ever make to your production database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca3c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dca3c-117">See Also</span></span>  
 <span data-ttu-id="dca3c-118">[Restricciones UNIQUE y restricciones check](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="dca3c-118">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="dca3c-119">Entornos multiusuario &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="dca3c-119">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
