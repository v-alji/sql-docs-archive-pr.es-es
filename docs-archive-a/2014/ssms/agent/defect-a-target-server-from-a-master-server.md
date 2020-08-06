---
title: Dar de baja un servidor de destino desde un servidor maestro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
ms.assetid: a6da262b-7b38-4ce4-bfd6-6a557c6e8a84
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b17703fa87f5c0d3e7146a1660ac1ca7c7c1d81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745641"
---
# <a name="defect-a-target-server-from-a-master-server"></a><span data-ttu-id="a701f-102">Dar de baja un servidor de destino desde un servidor maestro</span><span class="sxs-lookup"><span data-stu-id="a701f-102">Defect a Target Server from a Master Server</span></span>
  <span data-ttu-id="a701f-103">En este tema se describe cómo dar de baja un servidor de destino de un servidor maestro en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] u Objetos de administración de SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="a701f-103">This topic describes how to defect a target server from a master server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="a701f-104">Ejecute este procedimiento en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a701f-104">Run this procedure from the target server.</span></span>  
  
 <span data-ttu-id="a701f-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a701f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a701f-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a701f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a701f-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a701f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a701f-108">**Para dar de baja un servidor de destino, usando:**</span><span class="sxs-lookup"><span data-stu-id="a701f-108">**To defect a target server, using:**</span></span>  
  
     [<span data-ttu-id="a701f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a701f-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a701f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a701f-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a701f-111">SMO</span><span class="sxs-lookup"><span data-stu-id="a701f-111">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a701f-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a701f-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a701f-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a701f-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a701f-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="a701f-114">Permissions</span></span>  
 <span data-ttu-id="a701f-115">Para ejecutar este procedimiento almacenado, un usuario debe ser miembro del rol fijo de servidor `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="a701f-115">To execute this stored procedure, a user must be a member of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a701f-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a701f-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="a701f-117">Para dar de baja un servidor de destino desde un servidor maestro</span><span class="sxs-lookup"><span data-stu-id="a701f-117">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="a701f-118">En el **Explorador de objetos**, expanda un servidor que esté configurado como servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a701f-118">In **Object Explorer**, expand a server that is configured as a target server.</span></span>  
  
2.  <span data-ttu-id="a701f-119">Haga clic con el botón derecho en **Agente SQL Server**, seleccione **Administración de multiservidor**y, luego, haga clic en **Dar de baja**.</span><span class="sxs-lookup"><span data-stu-id="a701f-119">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Defect**.</span></span>  
  
3.  <span data-ttu-id="a701f-120">Haga clic en **Sí** para confirmar que desea dar de baja este servidor de destino en un servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="a701f-120">Click **Yes** to confirm that you want to defect this target server from a master server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a701f-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a701f-121">Using Transact-SQL</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="a701f-122">Para dar de baja un servidor de destino desde un servidor maestro</span><span class="sxs-lookup"><span data-stu-id="a701f-122">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="a701f-123">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a701f-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a701f-124">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="a701f-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a701f-125">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a701f-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```sql
sp_msx_defect ;  
```  
  
 <span data-ttu-id="a701f-126">Para obtener más información, vea [sp_msx_defect &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a701f-126">For more information, see [sp_msx_defect &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="a701f-127">Usar Objetos de administración de SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="a701f-127">Using SQL Server Management Objects (SMO)</span></span>  
 <span data-ttu-id="a701f-128">Use `MsxDefect Method`.</span><span class="sxs-lookup"><span data-stu-id="a701f-128">Use the `MsxDefect Method`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a701f-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a701f-129">See Also</span></span>  
 <span data-ttu-id="a701f-130">[Crear un entorno multiservidor](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="a701f-130">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="a701f-131">[Administración automatizada en una empresa](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="a701f-131">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="a701f-132">Dar de baja varios servidores de destino desde un servidor maestro</span><span class="sxs-lookup"><span data-stu-id="a701f-132">Defect Multiple Target Servers from a Master Server</span></span>](defect-multiple-target-servers-from-a-master-server.md)  
