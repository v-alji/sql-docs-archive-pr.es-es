---
title: Consultar procedimientos almacenados extendidos instalados en SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], querying
ms.assetid: e02348e6-dba6-438a-98b6-684244bb034d
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f44db9053ad18c3a6902a30aaab4f81610c5a8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670392"
---
# <a name="querying-extended-stored-procedures-installed-in-sql-server"></a><span data-ttu-id="be663-102">Consultar procedimientos almacenados extendidos instalados en SQL Server</span><span class="sxs-lookup"><span data-stu-id="be663-102">Querying Extended Stored Procedures Installed in SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="be663-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="be663-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="be663-104">Un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usuario autenticado puede mostrar los procedimientos almacenados extendidos definidos actualmente y el nombre de la dll a la que pertenece cada uno mediante la ejecución del procedimiento de sistema **sp_helpextendedproc** .</span><span class="sxs-lookup"><span data-stu-id="be663-104">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authenticated user can display the currently defined extended stored procedures and the name of the DLL to which each belongs by running the **sp_helpextendedproc** system procedure.</span></span> <span data-ttu-id="be663-105">Por ejemplo, en el ejemplo siguiente se devuelve el archivo DLL al que pertenece **xp_hello** :</span><span class="sxs-lookup"><span data-stu-id="be663-105">For example, the following example returns the DLL to which **xp_hello** belongs:</span></span>  
  
```  
sp_helpextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="be663-106">Si se ejecuta **sp_helpextendedproc** sin especificar un procedimiento almacenado extendido, se muestran todos los procedimientos almacenados extendidos y sus dll.</span><span class="sxs-lookup"><span data-stu-id="be663-106">If **sp_helpextendedproc** is executed without specifying an extended stored procedure, all the extended stored procedures and their DLLs are displayed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="be663-107">Solamente se devolverá información para los procedimientos almacenados extendidos que posea el usuario o para los que tenga permisos.</span><span class="sxs-lookup"><span data-stu-id="be663-107">Information will be returned for only those extended stored procedures that the logged in user owns or has permissions to.</span></span> <span data-ttu-id="be663-108">Solo los miembros del rol fijo de servidor **sysadmin** y de los roles fijos de base de datos **db_owner**, **db_securityadmin**y **db_ddladmin** pueden ver información de todos los procedimientos almacenados extendidos.</span><span class="sxs-lookup"><span data-stu-id="be663-108">Only members of the **sysadmin** fixed server role and the **db_owner**, **db_securityadmin**, and the **db_ddladmin** fixed database roles can view information for all extended stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be663-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be663-109">See Also</span></span>  
 <span data-ttu-id="be663-110">[sp_helpextendedproc &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="be663-110">[sp_helpextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span></span>  
 <span data-ttu-id="be663-111">[sp_addextendedproc &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="be663-111">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="be663-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="be663-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
