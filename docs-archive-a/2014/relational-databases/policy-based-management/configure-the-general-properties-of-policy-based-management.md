---
title: Configuración de las propiedades generales de la administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.PolicyManagement.f1
helpviewer_keywords:
- Policy-Based Management, configure properties
ms.assetid: 6d1e0e37-29ea-408a-a055-384984d884be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2efb37fafa29bcb043dedbcfa8719d0092b1c77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745719"
---
# <a name="configure-the-general-properties-of-policy-based-management"></a><span data-ttu-id="15c38-102">Configurar las propiedades generales de la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="15c38-102">Configure the General Properties of Policy-Based Management</span></span>
  <span data-ttu-id="15c38-103">En este tema se describe cómo se configuran las propiedades para la administración basada en directivas de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15c38-103">This topic describes how to configure the properties for Policy-Based Management in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="15c38-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="15c38-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="15c38-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="15c38-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="15c38-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="15c38-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="15c38-107">**Para configurar la administración basada en directivas se configura con:**</span><span class="sxs-lookup"><span data-stu-id="15c38-107">**To configure Policy-Based Management, using:**</span></span>  
  
     [<span data-ttu-id="15c38-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15c38-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="15c38-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15c38-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="15c38-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="15c38-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="15c38-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="15c38-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="15c38-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="15c38-112">Permissions</span></span>  
 <span data-ttu-id="15c38-113">Requiere la pertenencia al rol fijo de base de datos PolicyAdministratorRole.</span><span class="sxs-lookup"><span data-stu-id="15c38-113">Requires membership in the PolicyAdministratorRole fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="15c38-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15c38-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="15c38-115">Para configurar la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="15c38-115">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="15c38-116">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que quiere configurar las propiedades de administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="15c38-116">In **Object Explorer**, click the plus sign to expand the server where you want to configure Policy-Based Management properties.</span></span>  
  
2.  <span data-ttu-id="15c38-117">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="15c38-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="15c38-118">Haga clic con el botón derecho en **Administración de directivas** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="15c38-118">Right-click **Policy Management** and select **Properties**.</span></span>  
  
     <span data-ttu-id="15c38-119">Las siguientes opciones están disponibles en el cuadro de diálogo **Propiedades de Administración de directivas** .</span><span class="sxs-lookup"><span data-stu-id="15c38-119">The following options are available in **Policy Management Properties** dialog box.</span></span>  
  
     <span data-ttu-id="15c38-120">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="15c38-120">**Enabled**</span></span>  
     <span data-ttu-id="15c38-121">Especifica si la administración basada en directivas se habilita.</span><span class="sxs-lookup"><span data-stu-id="15c38-121">Specifies whether Policy-Based Management is enabled.</span></span>  
  
     <span data-ttu-id="15c38-122">**HistoryRetentionInDays**</span><span class="sxs-lookup"><span data-stu-id="15c38-122">**HistoryRetentionInDays**</span></span>  
     <span data-ttu-id="15c38-123">Especifica el número de días que se debería conservar el historial de evaluaciones de directivas.</span><span class="sxs-lookup"><span data-stu-id="15c38-123">Specifies the number of days that policy evaluation history should be retained.</span></span> <span data-ttu-id="15c38-124">Si este valor es 0 (el valor predeterminado), el historial no se quitará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="15c38-124">If this value is 0 (the default), the history will not be automatically removed.</span></span>  
  
     <span data-ttu-id="15c38-125">**LogOnSuccess**</span><span class="sxs-lookup"><span data-stu-id="15c38-125">**LogOnSuccess**</span></span>  
     <span data-ttu-id="15c38-126">Especifica si la administración basada en directivas registra las evaluaciones de la directiva correctas.</span><span class="sxs-lookup"><span data-stu-id="15c38-126">Specifies whether Policy-Based Management logs successful policy evaluations.</span></span>  
  
    -   <span data-ttu-id="15c38-127">Cuando este valor es false (el predeterminado), solo se registran las evaluaciones de las directivas con errores.</span><span class="sxs-lookup"><span data-stu-id="15c38-127">When this value is false (the default), only failed policy evaluations are logged.</span></span>  
  
    -   <span data-ttu-id="15c38-128">Cuando este valor es true, se registran tanto las evaluaciones de directivas correctas como las que tienen errores.</span><span class="sxs-lookup"><span data-stu-id="15c38-128">When this value is true, both successful and failed policy evaluations are logged.</span></span>  
  
4.  <span data-ttu-id="15c38-129">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="15c38-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="15c38-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15c38-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="15c38-131">Para configurar la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="15c38-131">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="15c38-132">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15c38-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="15c38-133">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="15c38-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="15c38-134">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="15c38-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- enables Policy-Based Management   
    USE msdb;  
    GO  
    EXEC dbo.sp_syspolicy_configure   
         @name = N'Enabled',   
         @value = 1;  
    GO  
    ```  
  
 <span data-ttu-id="15c38-135">Para obtener más información, vea [sp_syspolicy_configure&#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15c38-135">For more information, see [sp_syspolicy_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span></span>  
  
  
