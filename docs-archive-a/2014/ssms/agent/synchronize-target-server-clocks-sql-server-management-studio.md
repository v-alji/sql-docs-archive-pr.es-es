---
title: Sincronizar los relojes de los servidores de destino (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- clocks [SQL Server]
- master servers [SQL Server], clock synchronization
- synchronization [SQL Server], target server clocks
- target servers [SQL Server], clock synchronization
ms.assetid: 4fb80502-d271-4d06-bcbc-bfbbceb5f2a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e7150cd42699503ab22cdd89fb6206194bd64e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743900"
---
# <a name="synchronize-target-server-clocks-sql-server-management-studio"></a><span data-ttu-id="29245-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="29245-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span></span>
  <span data-ttu-id="29245-103">En este tema se describe cómo sincronizar los relojes de los servidores de destino en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] con el reloj del servidor maestro mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29245-103">This topic describes how to synchronize target server clocks in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] with the master server clock by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="29245-104">La sincronización de los relojes del sistema admite la programación de trabajos.</span><span class="sxs-lookup"><span data-stu-id="29245-104">Synchronizing these system clocks supports your job schedules.</span></span>  
  
 <span data-ttu-id="29245-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="29245-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="29245-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="29245-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="29245-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="29245-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="29245-108">**Para sincronizar los relojes de los servidores de destino, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="29245-108">**To synchronize target server clocks, using:**</span></span>  
  
     [<span data-ttu-id="29245-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29245-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="29245-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29245-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="29245-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="29245-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="29245-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="29245-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="29245-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="29245-113">Permissions</span></span>  
 <span data-ttu-id="29245-114">Requiere la pertenencia al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="29245-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="29245-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29245-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="29245-116">Para sincronizar los relojes de los servidores de destino</span><span class="sxs-lookup"><span data-stu-id="29245-116">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="29245-117">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor donde desea sincroniza los relojes de los servidores de destino con el reloj del servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="29245-117">In **Object Explorer,** click the plus sign to expand the server where you want to synchronize the target server clocks with the master server clock.</span></span>  
  
2.  <span data-ttu-id="29245-118">Haga clic con el botón derecho en **Agente SQL Server**, seleccione **Administración multiservidor**y seleccione **Administrar servidores de destino**.</span><span class="sxs-lookup"><span data-stu-id="29245-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="29245-119">En el cuadro de diálogo **Administrar servidores de destino** , haga clic en **Exponer instrucciones**.</span><span class="sxs-lookup"><span data-stu-id="29245-119">In the **Manage Target Servers** dialog box, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="29245-120">En la lista **Tipo de instrucción** , seleccione **Sincronizar relojes**.</span><span class="sxs-lookup"><span data-stu-id="29245-120">In the **Instruction type** list, select **Synchronize clocks**.</span></span>  
  
5.  <span data-ttu-id="29245-121">En **Destinatarios**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="29245-121">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="29245-122">Haga clic en **Todos los servidores de destino** para sincronizar los relojes de todos los servidores de destino con el reloj del servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="29245-122">Click **All target servers** to synchronize all target server clocks with the master server clock.</span></span>  
  
    -   <span data-ttu-id="29245-123">Haga clic en **Estos servidores de destino** para sincronizar determinados relojes de servidores y, a continuación, seleccione cada servidor de destino cuyo reloj desee sincronizar con el reloj del servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="29245-123">Click **These target servers** to synchronize certain server clocks, and then select each target server whose clock you want to synchronize with the master server clock.</span></span>  
  
6.  <span data-ttu-id="29245-124">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="29245-124">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="29245-125">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29245-125">Using Transact-SQL</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="29245-126">Para sincronizar los relojes de los servidores de destino</span><span class="sxs-lookup"><span data-stu-id="29245-126">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="29245-127">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29245-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="29245-128">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="29245-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="29245-129">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="29245-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- resynchronizes the SEATTLE1 target server  
    EXEC dbo.sp_resync_targetserver  
        N'SEATTLE1' ;  
    GO  
    ```  
  
 <span data-ttu-id="29245-130">Para obtener más información, vea [sp_resync_targetserver &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="29245-130">For more information, see [sp_resync_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span></span>  
  
  