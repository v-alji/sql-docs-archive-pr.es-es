---
title: Deshabilitar restricciones CHECK para la replicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, disabling
- constraints [SQL Server], disabling
- disabling constraints
- constraints [SQL Server], check
ms.assetid: af98fc70-24dd-4bd3-a0a3-f701dfa67b2c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 98b6ca7c3525edeffdb47f294db568d3c115b2c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661872"
---
# <a name="disable-check-constraints-for-replication"></a><span data-ttu-id="5fed8-102">Deshabilitar restricciones CHECK para la replicación</span><span class="sxs-lookup"><span data-stu-id="5fed8-102">Disable Check Constraints for Replication</span></span>
  <span data-ttu-id="5fed8-103">Puede deshabilitar las restricciones CHECK en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fed8-103">You can disable check constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5fed8-104">También puede deshabilitar explícitamente las restricciones CHECK para la replicación, lo que puede resultar útil si se publican datos de una versión anterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fed8-104">You can also explicitly disable check constraints for replication, which can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5fed8-105">Si una tabla se publica mediante replicación, se deshabilitan automáticamente las restricciones CHECK para las operaciones realizadas por los agentes de replicación.</span><span class="sxs-lookup"><span data-stu-id="5fed8-105">If a table is published using replication, check constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="5fed8-106">Cuando un agente de replicación realiza una inserción, actualización o eliminación en un suscriptor, no se comprueba la restricción. En cambio, sí se comprueba cuando lo hace un usuario.</span><span class="sxs-lookup"><span data-stu-id="5fed8-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="5fed8-107">La restricción se deshabilitará para el agente de replicación porque ya se comprobó en el publicador cuando se insertaron, actualizaron o eliminaron los datos originalmente.</span><span class="sxs-lookup"><span data-stu-id="5fed8-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span> <span data-ttu-id="5fed8-108">Para obtener más información, vea [Especificar opciones de esquema](../replication/publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="5fed8-108">For more information, see [Specify Schema Options](../replication/publish/specify-schema-options.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5fed8-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5fed8-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5fed8-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5fed8-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5fed8-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="5fed8-111">Permissions</span></span>  
 <span data-ttu-id="5fed8-112">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="5fed8-112">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5fed8-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5fed8-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="5fed8-114">Para deshabilitar una restricción CHECK para la replicación</span><span class="sxs-lookup"><span data-stu-id="5fed8-114">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="5fed8-115">En el **Explorador de objetos**, expanda la tabla con la restricción CHECK que desee modificar y, a continuación, expanda la carpeta **Restricciones** .</span><span class="sxs-lookup"><span data-stu-id="5fed8-115">In **Object Explorer**, expand the table with the check constraint you want to modify, and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="5fed8-116">Haga clic con el botón derecho en la restricción CHECK que quiera cambiar y, después, haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="5fed8-116">Right-click the check constraint you wish to modify and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="5fed8-117">En el cuadro de diálogo **Restricciones CHECK** , bajo **Diseñador de tablas**, seleccione el valor **No** para **Exigir para replicación**.</span><span class="sxs-lookup"><span data-stu-id="5fed8-117">In the **Check Constraints** dialog box, under **Table Designer**, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="5fed8-118">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5fed8-118">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5fed8-119">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5fed8-119">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="5fed8-120">Para deshabilitar una restricción CHECK para la replicación</span><span class="sxs-lookup"><span data-stu-id="5fed8-120">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="5fed8-121">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fed8-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5fed8-122">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5fed8-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5fed8-123">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5fed8-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5fed8-124">En el ejemplo se crea una tabla con una columna IDENTITY y una restricción CHECK.</span><span class="sxs-lookup"><span data-stu-id="5fed8-124">The example creates a table with an IDENTITY column and a CHECK constraint on the table.</span></span> <span data-ttu-id="5fed8-125">Después, se quita la restricción y se vuelve a crear especificando la cláusula NOT FOR REPLICATION.</span><span class="sxs-lookup"><span data-stu-id="5fed8-125">The example then drops the constraint and recreates it specifying the NOT FOR REPLICATION clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.doc_exd (column_a int IDENTITY (1,1)   
    CONSTRAINT exd_check CHECK (column_a > 1))   
  
    ALTER TABLE dbo.doc_exd   
    DROP CONSTRAINT exd_check;   
    GO  
    ALTER TABLE dbo.doc_exd    
    ADD CONSTRAINT exd_check CHECK NOT FOR REPLICATION (column_a > 1);  
    ```  
  
 <span data-ttu-id="5fed8-126">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5fed8-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>   
## <a name="see-also"></a><span data-ttu-id="5fed8-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5fed8-127">See Also</span></span>  
 [<span data-ttu-id="5fed8-128">Especificar opciones de esquema</span><span class="sxs-lookup"><span data-stu-id="5fed8-128">Specify Schema Options</span></span>](../replication/publish/specify-schema-options.md)  
  
  
