---
title: Cambiar la disponibilidad de un operador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- reactivating operators
- removing operators
- deleting operators
- available operators [SQL Server]
- dropping operators
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- disabling operators
- operators (users) [Database Engine], changing availability with Management Studio
ms.assetid: 10d58b92-b67b-47e2-af9c-9f9fd6968bba
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb369ea6a2d1edf1ed8f4377b627fb1ba7339a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677383"
---
# <a name="change-an-operator39s-availability"></a><span data-ttu-id="53e5e-102">Cambiar la disponibilidad de un operador</span><span class="sxs-lookup"><span data-stu-id="53e5e-102">Change an Operator&#39;s Availability</span></span>
  <span data-ttu-id="53e5e-103">En este tema se describe cómo cambiar la programación de un operador para recibir notificaciones de alerta en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53e5e-103">This topic describes how to change an operator's schedule for receiving alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="53e5e-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="53e5e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="53e5e-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="53e5e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="53e5e-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="53e5e-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="53e5e-107">**Para cambiar la disponibilidad de un operador, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="53e5e-107">**To change an operator's availability, using:**</span></span>  
  
     [<span data-ttu-id="53e5e-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="53e5e-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="53e5e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="53e5e-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="53e5e-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="53e5e-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="53e5e-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="53e5e-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="53e5e-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="53e5e-112">Permissions</span></span>  
 <span data-ttu-id="53e5e-113">Solo los miembros del rol fijo de servidor **sysadmin** pueden editar operadores.</span><span class="sxs-lookup"><span data-stu-id="53e5e-113">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="53e5e-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="53e5e-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="53e5e-115">Para cambiar la disponibilidad de un operador</span><span class="sxs-lookup"><span data-stu-id="53e5e-115">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="53e5e-116">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene el operador que desea habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="53e5e-116">In **Object Explorer**, click the plus sign to expand server that contains the operator that you want to enable or disable.</span></span>  
  
2.  <span data-ttu-id="53e5e-117">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="53e5e-117">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="53e5e-118">Haga clic en el signo más para expandir la carpeta **Operadores** .</span><span class="sxs-lookup"><span data-stu-id="53e5e-118">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="53e5e-119">Haga clic con el botón derecho en el operador que desea habilitar o deshabilitar y seleccione **Propiedades**; luego, haga clic en la pestaña **General** .</span><span class="sxs-lookup"><span data-stu-id="53e5e-119">Right-click the operator that you want to enable or disable and select **Properties**, then click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="53e5e-120">En el cuadro de diálogo**propiedades** de _operator_name_, Active o desactive la casilla **habilitado** .</span><span class="sxs-lookup"><span data-stu-id="53e5e-120">In the _operator_name_**Properties** dialog box, select or clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="53e5e-121">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="53e5e-121">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="53e5e-122">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="53e5e-122">Using Transact-SQL</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="53e5e-123">Para cambiar la disponibilidad de un operador</span><span class="sxs-lookup"><span data-stu-id="53e5e-123">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="53e5e-124">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53e5e-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="53e5e-125">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="53e5e-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="53e5e-126">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="53e5e-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- disables the 'Fran??ois Ajenstat' operator  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="53e5e-127">Para obtener más información, vea [sp_update_operator &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53e5e-127">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
