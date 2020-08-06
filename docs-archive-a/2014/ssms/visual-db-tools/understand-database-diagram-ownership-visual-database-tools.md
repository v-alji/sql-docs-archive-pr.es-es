---
title: Descripción de la propiedad de un diagrama de base de datos (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.CannotOpenWithInvalidOwner
helpviewer_keywords:
- diagrams [SQL Server], ownership
- database diagrams [SQL Server], ownership
- owners [SQL Server], database diagrams
ms.assetid: 4a27a48e-c4ef-4017-82b8-0cac4d0bbcac
author: stevestein
ms.author: sstein
ms.openlocfilehash: 21d0f6f006328d8843bbbe12ee066a8564fb722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747378"
---
# <a name="understand-database-diagram-ownership-visual-database-tools"></a><span data-ttu-id="ed96a-102">Descripción de la propiedad de un diagrama de base de datos (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ed96a-102">Understand Database Diagram Ownership (Visual Database Tools)</span></span>
  <span data-ttu-id="ed96a-103">Para usar el diseñador de diagramas de base de datos, debe primero configurarlo un miembro del rol db_owner (un rol de las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ) para controlar el acceso a los diagramas.</span><span class="sxs-lookup"><span data-stu-id="ed96a-103">To use Database Diagram Designer it must first be set up by a member of the db_owner role (a role of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases) to control access to diagrams.</span></span> <span data-ttu-id="ed96a-104">Cada diagrama tiene un único propietario: el usuario que lo ha creado.</span><span class="sxs-lookup"><span data-stu-id="ed96a-104">Each diagram has one and only one owner, the user who created it.</span></span> <span data-ttu-id="ed96a-105">Para obtener más información sobre la configuración de diagramas, vea [configurar el diseñador de diagramas de base de datos &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ed96a-105">For more information on setting up diagramming see [Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="ed96a-106">Conviene tener en cuenta algunos aspectos sobre la propiedad de los diagramas:</span><span class="sxs-lookup"><span data-stu-id="ed96a-106">Some points to keep in mind about diagram ownership:</span></span>  
  
-   <span data-ttu-id="ed96a-107">Aunque cualquier usuario con acceso a una base de datos puede crear un diagrama, una vez que se ha creado, los únicos usuarios que pueden verlo son su creador y cualquier miembro del rol db_owner.</span><span class="sxs-lookup"><span data-stu-id="ed96a-107">Although any user with access to a database can create a diagram, once the diagram has been created, the only users who can see it are the diagram's creator and any member of the db_owner role.</span></span>  
  
-   <span data-ttu-id="ed96a-108">La propiedad de los diagramas solo se puede transferir a los miembros del rol db_owner.</span><span class="sxs-lookup"><span data-stu-id="ed96a-108">Ownership of diagrams can only be transferred to members of the db_owner role.</span></span> <span data-ttu-id="ed96a-109">Esto solo es posible si el propietario anterior del diagrama se ha eliminado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ed96a-109">This is only possible if the previous owner of the diagram has been removed from the database.</span></span>  
  
-   <span data-ttu-id="ed96a-110">Si se ha eliminado de la base de datos el propietario de un diagrama, el diagrama permanecerá en la base de datos hasta que el miembro del rol db_owner intente abrirlo.</span><span class="sxs-lookup"><span data-stu-id="ed96a-110">If the owner of a diagram has been removed from the database, the diagram will remain in the database until a member of the db_owner role attempts to open it.</span></span> <span data-ttu-id="ed96a-111">En ese momento, el miembro de db_owner podrá decidir si asume su propiedad.</span><span class="sxs-lookup"><span data-stu-id="ed96a-111">At that point the db_owner member can choose to take over ownership of the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed96a-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed96a-112">See Also</span></span>  
 <span data-ttu-id="ed96a-113">[Trabajar con diagramas de base de datos &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ed96a-113">[Work with Database Diagrams &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ed96a-114">Configurar el Diseñador de diagramas de base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ed96a-114">Set Up Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
