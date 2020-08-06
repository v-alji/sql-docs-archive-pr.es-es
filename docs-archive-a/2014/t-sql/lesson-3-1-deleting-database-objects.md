---
title: Eliminación de objetos de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- deleting database objects
ms.assetid: dbb94fdf-c85b-477b-8e84-f830d259bade
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 6bd69935dbfac020c4c75bb391e7932009fd4197
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663263"
---
# <a name="deleting-database-objects"></a><span data-ttu-id="05d33-102">Eliminar objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="05d33-102">Deleting Database Objects</span></span>
  <span data-ttu-id="05d33-103">Para quitar todas los seguimientos de este tutorial, podría eliminar únicamente la base de datos.</span><span class="sxs-lookup"><span data-stu-id="05d33-103">To remove all traces of this tutorial, you could just delete the database.</span></span> <span data-ttu-id="05d33-104">No obstante, en este tema, recorrerá los pasos para revertir cada una de las acciones llevadas a cabo en el tutorial.</span><span class="sxs-lookup"><span data-stu-id="05d33-104">However, in this topic, you will go through the steps to reverse every action you took doing the tutorial.</span></span>  
  
### <a name="removing-permissions-and-objects"></a><span data-ttu-id="05d33-105">Quitar permisos y objetos</span><span class="sxs-lookup"><span data-stu-id="05d33-105">Removing permissions and objects</span></span>  
  
1.  <span data-ttu-id="05d33-106">Antes de eliminar objetos, asegúrese de que está en la base de datos correcta:</span><span class="sxs-lookup"><span data-stu-id="05d33-106">Before you delete objects, make sure you are in the correct database:</span></span>  
  
    ```  
    USE TestData;  
    GO  
    ```  
  
2.  <span data-ttu-id="05d33-107">Use la instrucción `REVOKE` para quitar el permiso de ejecución para `Mary` en el procedimiento almacenado:</span><span class="sxs-lookup"><span data-stu-id="05d33-107">Use the `REVOKE` statement to remove execute permission for `Mary` on the stored procedure:</span></span>  
  
    ```  
    REVOKE EXECUTE ON pr_Names FROM Mary;  
    GO  
  
    ```  
  
3.  <span data-ttu-id="05d33-108">Use la instrucción `DROP` para quitar el permiso de `Mary` para tener acceso a la base de datos `TestData` :</span><span class="sxs-lookup"><span data-stu-id="05d33-108">Use the `DROP` statement to remove permission for `Mary` to access the `TestData` database:</span></span>  
  
    ```  
    DROP USER Mary;  
    GO  
  
    ```  
  
4.  <span data-ttu-id="05d33-109">Use la instrucción `DROP` para quitar el permiso de `Mary` para tener acceso a esta instancia de [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="05d33-109">Use the `DROP` statement to remove permission for `Mary` to access this instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span></span>  
  
    ```  
    DROP LOGIN [<computer_name>\Mary];  
    GO  
  
    ```  
  
5.  <span data-ttu-id="05d33-110">Use la instrucción `DROP` para quitar el procedimiento almacenado `pr_Names`:</span><span class="sxs-lookup"><span data-stu-id="05d33-110">Use the `DROP` statement to remove the store procedure `pr_Names`:</span></span>  
  
    ```  
    DROP PROC pr_Names;  
    GO  
  
    ```  
  
6.  <span data-ttu-id="05d33-111">Use la instrucción `DROP` para quitar la vista `vw_Names`:</span><span class="sxs-lookup"><span data-stu-id="05d33-111">Use the `DROP` statement to remove the view `vw_Names`:</span></span>  
  
    ```  
    DROP View vw_Names;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="05d33-112">Use la instrucción `DELETE` para quitar todas las filas de la tabla `Products` :</span><span class="sxs-lookup"><span data-stu-id="05d33-112">Use the `DELETE` statement to remove all rows from the `Products` table:</span></span>  
  
    ```  
    DELETE FROM Products;  
    GO  
  
    ```  
  
8.  <span data-ttu-id="05d33-113">Use la instrucción `DROP` para quitar la tabla `Products` :</span><span class="sxs-lookup"><span data-stu-id="05d33-113">Use the `DROP` statement to remove the `Products` table:</span></span>  
  
    ```  
    DROP Table Products;  
    GO  
  
    ```  
  
9. <span data-ttu-id="05d33-114">No puede quitar la base de datos `TestData` mientras esté en la base de datos; por tanto, cambie primero el contexto a otra base de datos y, a continuación, use la instrucción `DROP` para quitar la base de datos `TestData` :</span><span class="sxs-lookup"><span data-stu-id="05d33-114">You cannot remove the `TestData` database while you are in the database; therefore, first switch context to another database, and then use the `DROP` statement to remove the `TestData` database:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    DROP DATABASE TestData;  
    GO  
  
    ```  
  
 <span data-ttu-id="05d33-115">Esto finaliza el tutorial de escritura de instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05d33-115">This concludes the Writing [!INCLUDE[tsql](../includes/tsql-md.md)] Statements tutorial.</span></span> <span data-ttu-id="05d33-116">Recuerde que este tutorial es una introducción breve y en él no se describen todas las opciones de las instrucciones que se usan.</span><span class="sxs-lookup"><span data-stu-id="05d33-116">Remember, this tutorial is a brief overview and it does not describe all the options to the statements that are used.</span></span> <span data-ttu-id="05d33-117">El diseño y la creación de una estructura de base de datos eficaz y la configuración del acceso seguro a los datos requiere una base de datos más compleja que la que se muestra en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="05d33-117">Designing and creating an efficient database structure and configuring secure access to the data requires a more complex database than that shown in this tutorial.</span></span>  
  
## <a name="return-to-sql-server-tools-portal"></a><span data-ttu-id="05d33-118">Volver al portal de las herramientas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="05d33-118">Return to SQL Server Tools Portal</span></span>  
 [<span data-ttu-id="05d33-119">Tutorial: Escribir instrucciones Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="05d33-119">Tutorial: Writing Transact-SQL Statements</span></span>](tutorial-writing-transact-sql-statements.md)  
  
## <a name="see-also"></a><span data-ttu-id="05d33-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05d33-120">See Also</span></span>  
 <span data-ttu-id="05d33-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="05d33-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="05d33-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="05d33-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span></span>  
 <span data-ttu-id="05d33-123">[DROP LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="05d33-123">[DROP LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span></span>  
 <span data-ttu-id="05d33-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="05d33-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="05d33-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="05d33-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span></span>  
 <span data-ttu-id="05d33-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="05d33-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="05d33-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="05d33-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 [<span data-ttu-id="05d33-128">DROP DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="05d33-128">DROP DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-database-audit-specification-transact-sql)  
  
  
