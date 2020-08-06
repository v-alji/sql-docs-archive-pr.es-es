---
title: Configurar el Diseñador de diagramas de base de datos (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.InstallSqlDiagramSupport
helpviewer_keywords:
- Database Diagram Designer
- database diagrams [SQL Server], Database Diagram Designer
- diagrams [SQL Server], Database Diagram Designer
ms.assetid: 927321ee-b459-4f5b-9719-4a7a95639143
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d59fa2ed197a410de6b68e388e76d2bf21c334d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747381"
---
# <a name="set-up-database-diagram-designer-visual-database-tools"></a><span data-ttu-id="df1af-102">Configurar el Diseñador de diagramas de base de datos (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="df1af-102">Set Up Database Diagram Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="df1af-103">Para usar el diseñador de diagramas de base de datos, un miembro del rol **db_owner** debe configurarlo primero para controlar el acceso a los diagramas.</span><span class="sxs-lookup"><span data-stu-id="df1af-103">To use Database Diagram Designer, it must first be set up by a member of the **db_owner** role to control access to diagrams.</span></span>  
  
### <a name="to-set-up-database-diagramming"></a><span data-ttu-id="df1af-104">Para configurar diagramas de base de datos</span><span class="sxs-lookup"><span data-stu-id="df1af-104">To set up database diagramming</span></span>  
  
1.  <span data-ttu-id="df1af-105">En el Explorador de objetos, expanda un nodo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="df1af-105">From Object Explorer, expand a database node.</span></span>  
  
2.  <span data-ttu-id="df1af-106">Expanda el nodo de Diagramas de base de datos bajo la conexión de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="df1af-106">Expand the Database Diagrams node under the database connection.</span></span>  
  
3.  <span data-ttu-id="df1af-107">Seleccione **Sí** cuando se le pregunte si desea configurar la creación de diagramas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="df1af-107">Select **Yes** when prompted if you want to set up database diagramming.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="df1af-108">De esta forma creará la tabla de diagrama de base de datos, los procedimientos almacenados del sistema y una función del sistema en la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df1af-108">This will create the database diagram table, system stored procedures, and a system function on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="df1af-109">Visual Studio creará los siguientes objetos en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="df1af-109">Visual Studio will create the following objects on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="df1af-110">sysdiagrams - Tabla</span><span class="sxs-lookup"><span data-stu-id="df1af-110">sysdiagrams table</span></span>  
  
    2.  <span data-ttu-id="df1af-111">sp_alterdiagam - Procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="df1af-111">sp_alterdiagram stored procedure</span></span>  
  
    3.  <span data-ttu-id="df1af-112">sp_creatediagram - Procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="df1af-112">sp_creatediagram stored procedure</span></span>  
  
    4.  <span data-ttu-id="df1af-113">sp_dropdiagram - Procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="df1af-113">sp_dropdiagram stored procedure</span></span>  
  
    5.  <span data-ttu-id="df1af-114">sp_renamediagram - Procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="df1af-114">sp_renamediagram stored procedure</span></span>  
  
    6.  <span data-ttu-id="df1af-115">fn_diagramobjects - Función</span><span class="sxs-lookup"><span data-stu-id="df1af-115">fn_diagramobjects function</span></span>  
  
    7.  <span data-ttu-id="df1af-116">sp_helpdiagrams - Procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="df1af-116">sp_helpdiagrams stored procedure</span></span>  
  
    8.  <span data-ttu-id="df1af-117">sp_helpdiagramsdefinition - Procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="df1af-117">sp_helpdiagramsdefinition stored procedure</span></span>  
  
    9. <span data-ttu-id="df1af-118">sp_upgraddiagrams - Procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="df1af-118">sp_upgraddiagrams stored procedure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df1af-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df1af-119">See Also</span></span>  
 <span data-ttu-id="df1af-120">[Descripción de la propiedad de diagrama de base de datos &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="df1af-120">[Understand Database Diagram Ownership &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="df1af-121">[Actualizar diagramas de base de datos de ediciones anteriores &#40;Visual Database Tools&#41;](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="df1af-121">[Upgrade Database Diagrams from Previous Editions &#40;Visual Database Tools&#41;](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="df1af-122">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="df1af-122">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-authorization-transact-sql)  
  
  
