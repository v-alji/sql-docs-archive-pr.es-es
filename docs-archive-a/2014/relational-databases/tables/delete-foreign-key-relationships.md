---
title: Eliminación de relaciones de claves externas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], deleting
- removing foreign keys
- deleting foreign keys
ms.assetid: 9c9e9ae4-9e03-4137-acb6-b18928a0c4ca
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ae466b9fce53073bfc0645c753246023ff3269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672869"
---
# <a name="delete-foreign-key-relationships"></a><span data-ttu-id="4b72e-102">Eliminar relaciones entre claves externas.</span><span class="sxs-lookup"><span data-stu-id="4b72e-102">Delete Foreign Key Relationships</span></span>
  <span data-ttu-id="4b72e-103">Puede eliminar una restricción de clave externa en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b72e-103">You can delete a foreign key constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4b72e-104">Al eliminar una restricción de clave externa se elimina el requisito de forzar la integridad referencial.</span><span class="sxs-lookup"><span data-stu-id="4b72e-104">Deleting a foreign key constraint removes the requirement to enforce referential integrity.</span></span>  
  
 <span data-ttu-id="4b72e-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4b72e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4b72e-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4b72e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4b72e-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4b72e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4b72e-108">**Para eliminar una restricción de clave externa, use:**</span><span class="sxs-lookup"><span data-stu-id="4b72e-108">**To delete a foreign key constraint, using:**</span></span>  
  
     [<span data-ttu-id="4b72e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b72e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4b72e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b72e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4b72e-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4b72e-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4b72e-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4b72e-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4b72e-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="4b72e-113">Permissions</span></span>  
 <span data-ttu-id="4b72e-114">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="4b72e-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4b72e-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b72e-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="4b72e-116">Para eliminar una restricción FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="4b72e-116">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="4b72e-117">En el **Explorador de objetos**, expanda la tabla con la restricción y, a continuación, expanda **Claves**.</span><span class="sxs-lookup"><span data-stu-id="4b72e-117">In **Object Explorer**, expand the table with the constraint and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="4b72e-118">Haga clic con el botón derecho en la restricción y, después, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4b72e-118">Right-click the constraint and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="4b72e-119">En el cuadro de diálogo **Eliminar objeto** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b72e-119">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4b72e-120">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b72e-120">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="4b72e-121">Para eliminar una restricción FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="4b72e-121">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="4b72e-122">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b72e-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4b72e-123">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4b72e-123">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4b72e-124">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4b72e-124">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.DocExe   
    DROP CONSTRAINT FK_Column_B;   
    GO  
    ```  
  
 <span data-ttu-id="4b72e-125">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b72e-125">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
