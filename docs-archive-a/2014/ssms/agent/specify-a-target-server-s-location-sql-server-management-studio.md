---
title: Especificar una ubicación de&#39;s del servidor de destino (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], location
ms.assetid: 511ff311-21f5-4f2f-839f-b4deee26ec98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 938528ab78f0f457cde69d8fd4d5432cc14a79b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675100"
---
# <a name="specify-a-target-server39s-location-sql-server-management-studio"></a><span data-ttu-id="1596e-102">Especificar la ubicación de un servidor de destino (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1596e-102">Specify a Target Server&#39;s Location (SQL Server Management Studio)</span></span>
  <span data-ttu-id="1596e-103">En este tema se describe cómo especificar la ubicación de un servidor de destino en una configuración de administración multiservidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1596e-103">This topic describes how to specify the location of a target server in a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1596e-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="1596e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1596e-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="1596e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1596e-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="1596e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1596e-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1596e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1596e-108">**Para especificar la ubicación de un servidor de destino, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="1596e-108">**To specify a target server's location, using:**</span></span>  
  
     [<span data-ttu-id="1596e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1596e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1596e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1596e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1596e-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1596e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1596e-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="1596e-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="1596e-113">La realización de esta acción modifica el Registro.</span><span class="sxs-lookup"><span data-stu-id="1596e-113">Performing this action edits the registry.</span></span> <span data-ttu-id="1596e-114">No se recomienda la modificación manual del Registro porque los cambios inapropiados o incorrectos pueden causar graves problemas de configuración en el sistema.</span><span class="sxs-lookup"><span data-stu-id="1596e-114">Manual editing of the registry is not recommended because inappropriate or incorrect changes can cause serious configuration problems for your system.</span></span> <span data-ttu-id="1596e-115">Por tanto, solo los usuarios experimentados deben utilizar el programa Editor del Registro para modificar el Registro.</span><span class="sxs-lookup"><span data-stu-id="1596e-115">Therefore, only experienced users should use the Registry Editor program to edit the registry.</span></span> <span data-ttu-id="1596e-116">Para obtener más información, consulte la documentación de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="1596e-116">For more information, see the Microsoft Windows documentation.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1596e-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1596e-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1596e-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="1596e-118">Permissions</span></span>  
 <span data-ttu-id="1596e-119">Requiere la pertenencia al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="1596e-119">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1596e-120">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1596e-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="1596e-121">Para especificar la ubicación de un servidor de destino</span><span class="sxs-lookup"><span data-stu-id="1596e-121">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="1596e-122">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor maestro en el que desea especificar la ubicación de un servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="1596e-122">In **Object Explorer**, click the plus sign to expand the master server on which you want to specify a target server's location.</span></span>  
  
2.  <span data-ttu-id="1596e-123">Haga clic con el botón derecho en **Agente SQL Server**, seleccione **Administración multiservidor**y seleccione **Administrar servidores de destino**.</span><span class="sxs-lookup"><span data-stu-id="1596e-123">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="1596e-124">Haga clic con el botón derecho en un servidor de destino y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1596e-124">Right-click a target server and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="1596e-125">En el cuadro **Ubicación** , escriba la ubicación del servidor y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1596e-125">In the **Location** box, enter a location for the server, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1596e-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1596e-126">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="1596e-127">Para especificar la ubicación de un servidor de destino</span><span class="sxs-lookup"><span data-stu-id="1596e-127">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="1596e-128">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1596e-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1596e-129">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="1596e-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1596e-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1596e-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- enlists the current server into the AdventureWorks1 master server.   
    -- The location for the current server is Building 21, Room 309, Rack 5  
    EXEC dbo.sp_msx_enlist N'AdventureWorks2012',   
        N'Building 21, Room 309, Rack 5' ;  
    GO  
    ```  
  
 <span data-ttu-id="1596e-131">Para obtener más información, vea [sp_msx_enlist &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1596e-131">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
  
