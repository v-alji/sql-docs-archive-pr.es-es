---
title: Deshabilitar una restricción FOREIGN KEY para la replicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
ms.assetid: 4211f2fd-d16a-4081-995c-43f1f0827f0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4ee7f2fb7b0a27870a09a9d99b723b7faf739aeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671960"
---
# <a name="disable-foreign-key-constraints-for-replication"></a><span data-ttu-id="6b6ad-102">Deshabilitar una restricción FOREIGN KEY para la replicación</span><span class="sxs-lookup"><span data-stu-id="6b6ad-102">Disable Foreign Key Constraints for Replication</span></span>
  <span data-ttu-id="6b6ad-103">Puede deshabilitar las restricciones de clave externa para la replicación en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b6ad-103">You can disable foreign key constraints for replication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6b6ad-104">Esto puede ser útil si se publican datos de una versión anterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b6ad-104">This can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b6ad-105">Si se publica la tabla mediante replicación, se deshabilitan automáticamente las restricciones FOREIGN KEY para las operaciones realizadas por los agentes de replicación.</span><span class="sxs-lookup"><span data-stu-id="6b6ad-105">If a table is published using replication, foreign key constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="6b6ad-106">Cuando un agente de replicación realiza una inserción, actualización o eliminación en un suscriptor, no se comprueba la restricción. En cambio, sí se comprueba cuando lo hace un usuario.</span><span class="sxs-lookup"><span data-stu-id="6b6ad-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="6b6ad-107">La restricción se deshabilitará para el agente de replicación porque ya se comprobó en el publicador cuando se insertaron, actualizaron o eliminaron los datos originalmente.</span><span class="sxs-lookup"><span data-stu-id="6b6ad-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span>  
  
 <span data-ttu-id="6b6ad-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6b6ad-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6b6ad-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6b6ad-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6b6ad-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6b6ad-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6b6ad-111">**Para deshabilitar una restricción de clave externa para la replicación, use:**</span><span class="sxs-lookup"><span data-stu-id="6b6ad-111">**To disable a foreign key constraint for replication, using:**</span></span>  
  
     [<span data-ttu-id="6b6ad-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6b6ad-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6b6ad-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6b6ad-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6b6ad-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6b6ad-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6b6ad-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6b6ad-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6b6ad-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="6b6ad-116">Permissions</span></span>  
 <span data-ttu-id="6b6ad-117">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="6b6ad-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6b6ad-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6b6ad-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="6b6ad-119">Para deshabilitar una restricción FOREIGN KEY para la replicación</span><span class="sxs-lookup"><span data-stu-id="6b6ad-119">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="6b6ad-120">En el **Explorador de objetos**, expanda la tabla con la restricción de clave externa que desee modificar y, a continuación, expanda la carpeta **Claves** .</span><span class="sxs-lookup"><span data-stu-id="6b6ad-120">In **Object Explorer**, expand the table with the foreign key constraint you want to modify, and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="6b6ad-121">Haga clic con el botón derecho en la restricción de clave externa y, luego, haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="6b6ad-121">Right-click the foreign key constraint and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="6b6ad-122">En el cuadro de diálogo **Relaciones de clave externa** , seleccione el valor **No** para **Exigir para replicación**.</span><span class="sxs-lookup"><span data-stu-id="6b6ad-122">In the **Foreign Key Relationships** dialog box, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="6b6ad-123">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6b6ad-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6b6ad-124">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6b6ad-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="6b6ad-125">Para deshabilitar una restricción FOREIGN KEY para la replicación</span><span class="sxs-lookup"><span data-stu-id="6b6ad-125">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="6b6ad-126">Para realizar esta tarea en [!INCLUDE[tsql](../../includes/tsql-md.md)], quite la restricción de clave externa.</span><span class="sxs-lookup"><span data-stu-id="6b6ad-126">To perform this task in [!INCLUDE[tsql](../../includes/tsql-md.md)], drop the foreign key constraint.</span></span> <span data-ttu-id="6b6ad-127">Después agregue una nueva restricción de clave externa y especifique la opción NOT FOR REPLICATION.</span><span class="sxs-lookup"><span data-stu-id="6b6ad-127">Then add a new foreign key constraint and specify the NOT FOR REPLICATION option.</span></span>  
  
 <span data-ttu-id="6b6ad-128">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6b6ad-128">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
