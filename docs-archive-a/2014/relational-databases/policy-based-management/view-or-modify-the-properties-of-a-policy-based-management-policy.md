---
title: Ver o modificar las propiedades de una directiva de administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, modify policies
- Policy-Based Management, view policies
ms.assetid: ba805504-5db5-4731-a8da-a0e89cb20c37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: da2226d3049a84098eb8e561635161f73b71ab10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670977"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-policy"></a><span data-ttu-id="5cc67-102">Ver o modificar las propiedades de una directiva de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="5cc67-102">View or Modify the Properties of a Policy-Based Management Policy</span></span>
  <span data-ttu-id="5cc67-103">En este tema se describe cómo ver o modificar las propiedades de una directiva de administración basada en directivas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cc67-103">This topic describes how to view or modify a Policy-Based Management policy's properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5cc67-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5cc67-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5cc67-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5cc67-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5cc67-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5cc67-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5cc67-107">**Para ver o modificar las propiedades de una directiva mediante:**</span><span class="sxs-lookup"><span data-stu-id="5cc67-107">**To view or modify a policy's properties, using:**</span></span>  
  
     [<span data-ttu-id="5cc67-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5cc67-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5cc67-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5cc67-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5cc67-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5cc67-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5cc67-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5cc67-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5cc67-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="5cc67-112">Permissions</span></span>  
 <span data-ttu-id="5cc67-113">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="5cc67-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5cc67-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5cc67-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-all-policies-on-an-object"></a><span data-ttu-id="5cc67-115">Para ver las propiedades de todas las directivas de un objeto</span><span class="sxs-lookup"><span data-stu-id="5cc67-115">To view the properties of all policies on an object</span></span>  
  
1.  <span data-ttu-id="5cc67-116">En el Explorador de objetos, haga clic con el botón derecho en un servidor, objeto de servidor, base de datos u objeto de base de datos, elija **Directivas** y seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="5cc67-116">In Object Explorer, right-click a server, server object, database, or database object, point to **Policies** and select **View**.</span></span> <span data-ttu-id="5cc67-117">Para más información sobre las opciones disponibles en el cuadro de diálogo **Ver directivas -**_nombre_de_objeto_, vea [Cuadro de diálogo Ver directivas](view-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="5cc67-117">For more information on the available options in the **View Policies -**_object_name_ dialog box, see [View Policies Dialog Box](view-policies-dialog-box.md).</span></span>  
  
2.  <span data-ttu-id="5cc67-118">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5cc67-118">When finished, click **Close**.</span></span>  
  
#### <a name="to-view-or-modify-a-specific-policys-properties"></a><span data-ttu-id="5cc67-119">Para ver o modificar las propiedades de una directiva específica</span><span class="sxs-lookup"><span data-stu-id="5cc67-119">To view or modify a specific policy's properties</span></span>  
  
1.  <span data-ttu-id="5cc67-120">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la directiva de administración basada en directivas que quiera ver o modificar.</span><span class="sxs-lookup"><span data-stu-id="5cc67-120">In **Object Explorer**, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="5cc67-121">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="5cc67-121">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="5cc67-122">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="5cc67-122">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="5cc67-123">Haga clic en el signo más para expandir la carpeta **Directivas** .</span><span class="sxs-lookup"><span data-stu-id="5cc67-123">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="5cc67-124">Haga clic con el botón derecho en la directiva que quiera ver o editar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5cc67-124">Right-click the policy that you want to view or modify and select **Properties**.</span></span> <span data-ttu-id="5cc67-125">Para más información sobre las opciones disponibles en el cuadro de diálogo **Abrir directiva -**_nombre_de_directiva_, vea [Cuadro de diálogo Crear nueva directiva o Abrir directiva, página General](../../integration-services/general-page-of-integration-services-designers-options.md) y [Cuadro de diálogo Crear nueva directiva o Abrir directiva, página Descripción](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="5cc67-125">For more information on the available options in the **Open Policy -**_policy_name_ dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) and [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
6.  <span data-ttu-id="5cc67-126">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5cc67-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5cc67-127">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5cc67-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-policys-properties"></a><span data-ttu-id="5cc67-128">Para ver las propiedades de una directiva</span><span class="sxs-lookup"><span data-stu-id="5cc67-128">To view a policy's properties</span></span>  
  
1.  <span data-ttu-id="5cc67-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cc67-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5cc67-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5cc67-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5cc67-131">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5cc67-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       execution_mode,  
       description,  
       is_enabled,  
       job_id  
    FROM syspolicy_policies;  
    GO  
    ```  
  
 <span data-ttu-id="5cc67-132">Para obtener más información, vea [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5cc67-132">For more information, see [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span></span>  
  
  
