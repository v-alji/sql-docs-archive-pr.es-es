---
title: Dar de alta un servidor de destino en un servidor maestro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- enlisting target servers [SQL Server]
- SQL Server Agent jobs, target servers
- master servers [SQL Server], enlisting target servers
- SQL Server Agent jobs, master servers
- target servers [SQL Server], enlisting
ms.assetid: 7633adb5-d140-4e58-a8f2-5b4b50c2f95b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 256f1a78d298d89a36412ee5689695f3ab3fde8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662483"
---
# <a name="enlist-a-target-server-to-a-master-server"></a><span data-ttu-id="d7683-102">Dar de alta un servidor de destino en un servidor maestro</span><span class="sxs-lookup"><span data-stu-id="d7683-102">Enlist a Target Server to a Master Server</span></span>
  <span data-ttu-id="d7683-103">En este tema se describe el modo de agregar servidores de destino a una configuración de la administración multiservidor.</span><span class="sxs-lookup"><span data-stu-id="d7683-103">This topic describes how to add target servers to a multiserver administration configuration.</span></span> <span data-ttu-id="d7683-104">Ejecute este procedimiento en el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="d7683-104">Run this procedure from the master server.</span></span> <span data-ttu-id="d7683-105">en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]u Objetos de administración de SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="d7683-105">in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="d7683-106">Para información sobre cómo la cuenta de Windows usada para el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afecta a un entorno multiservidor, consulte [Crear un entorno multiservidor](create-a-multiserver-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d7683-106">For information about how the Windows account used for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service affects a multiserver environment, see [Create a Multiserver Environment](create-a-multiserver-environment.md).</span></span>  
  
 <span data-ttu-id="d7683-107">El cifrado SSL (Capa de sockets seguros) y la validación de certificados completos se habilita para las conexiones entre los servidores maestros y los servidores de destino de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d7683-107">Full Secure Sockets Layer (SSL) encryption and certificate validation is enabled for connections between master servers and target servers by default.</span></span> <span data-ttu-id="d7683-108">Para más información, [Establecer opciones de cifrado en servidores de destino](set-encryption-options-on-target-servers.md).</span><span class="sxs-lookup"><span data-stu-id="d7683-108">For more information, see [Set Encryption Options on Target Servers](set-encryption-options-on-target-servers.md).</span></span>  
  
 <span data-ttu-id="d7683-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d7683-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d7683-110">**Para dar de alta un servidor de destino, usando:**</span><span class="sxs-lookup"><span data-stu-id="d7683-110">**To enlist a target server, using:**</span></span>  
  
     [<span data-ttu-id="d7683-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d7683-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d7683-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d7683-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="d7683-113">SMO</span><span class="sxs-lookup"><span data-stu-id="d7683-113">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d7683-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d7683-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="d7683-115">Para dar de alta un servidor de destino</span><span class="sxs-lookup"><span data-stu-id="d7683-115">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="d7683-116">En el **Explorador de objetos**, expanda un servidor que esté configurado como servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="d7683-116">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="d7683-117">Haga clic con el botón derecho en **Agente SQL Server**, seleccione **Administración de multiservidor**y, luego, en **Agregar servidores de destino**.</span><span class="sxs-lookup"><span data-stu-id="d7683-117">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Add Target Servers**.</span></span>  
  
3.  <span data-ttu-id="d7683-118">Complete el Asistente para establecer servidor de destino, que le guía a través del proceso.</span><span class="sxs-lookup"><span data-stu-id="d7683-118">Complete the Target Server Wizard, which guides you through the process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d7683-119">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d7683-119">Using Transact-SQL</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="d7683-120">Para dar de alta un servidor de destino</span><span class="sxs-lookup"><span data-stu-id="d7683-120">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="d7683-121">Use el procedimiento almacenado `sp_msx_enlist`.</span><span class="sxs-lookup"><span data-stu-id="d7683-121">Use the `sp_msx_enlist` stored procedure.</span></span>  <span data-ttu-id="d7683-122">Para obtener más información, vea [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="d7683-122">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="d7683-123">Usar Objetos de administración de SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="d7683-123">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7683-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7683-124">See Also</span></span>  
 [<span data-ttu-id="d7683-125">Administración automatizada en una empresa</span><span class="sxs-lookup"><span data-stu-id="d7683-125">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
