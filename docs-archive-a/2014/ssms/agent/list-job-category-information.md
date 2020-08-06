---
title: Mostrar información de categorías de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 0fc668d4-6244-4fef-b90e-62d2c776cd7c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 924e2b064980b2ea7068230610414262995da1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747882"
---
# <a name="list-job-category-information"></a><span data-ttu-id="dd3e7-102">Mostrar información de categorías de trabajo</span><span class="sxs-lookup"><span data-stu-id="dd3e7-102">List Job Category Information</span></span>
  <span data-ttu-id="dd3e7-103">Cómo Mostrar información de categorías de trabajo en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dd3e7-103">How to list job category information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  

  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dd3e7-104">Seguridad</span><span class="sxs-lookup"><span data-stu-id="dd3e7-104">Security</span></span>  
 <span data-ttu-id="dd3e7-105">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="dd3e7-105">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="dd3e7-106">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dd3e7-106">Using Transact-SQL</span></span>  
  
#### <a name="to-list-job-category-information"></a><span data-ttu-id="dd3e7-107">Para mostrar información de categorías de trabajo</span><span class="sxs-lookup"><span data-stu-id="dd3e7-107">To list job category information</span></span>  
  
1.  <span data-ttu-id="dd3e7-108">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd3e7-108">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dd3e7-109">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="dd3e7-109">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dd3e7-110">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="dd3e7-110">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- returns information about jobs that are administered locally  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_category  
        @type = N'LOCAL' ;  
    GO  
    ```  
  
 <span data-ttu-id="dd3e7-111">Para obtener más información, vea [sp_help_category &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dd3e7-111">For more information, see [sp_help_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span></span>  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="dd3e7-112">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="dd3e7-112">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="dd3e7-113">**Para mostrar información de categorías de trabajo**</span><span class="sxs-lookup"><span data-stu-id="dd3e7-113">**To list job category information**</span></span>  
  
 <span data-ttu-id="dd3e7-114">Utilice la clase `JobCategory` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd3e7-114">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell..</span></span> <span data-ttu-id="dd3e7-115">Para obtener más información, vea [Objetos de administración de SQL Server &#40;SMO&#41; guía de programación](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span><span class="sxs-lookup"><span data-stu-id="dd3e7-115">For more information, see [SQL Server Management Objects &#40;SMO&#41; Programming Guide](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span></span>  
