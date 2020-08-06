---
title: Ver o modificar las propiedades de una directiva de administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view policy conditions
- Policy-Based Management, modify policy conditions
ms.assetid: 890d7384-8444-4767-bb6f-f5debb155747
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 08baec48bd13445ef56ea6a29520d23ebaf683b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670976"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-condition"></a><span data-ttu-id="737e5-102">Ver o modificar las propiedades de una condición de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="737e5-102">View or Modify the Properties of a Policy-Based Management Condition</span></span>
  <span data-ttu-id="737e5-103">En este tema se describe cómo ver o modificar las propiedades de una condición de administración basada en directivas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="737e5-103">This topic describes how to view or modify the properties of a Policy-Based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="737e5-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="737e5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="737e5-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="737e5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="737e5-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="737e5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="737e5-107">**Para ver o modificar las propiedades de una condición mediante:**</span><span class="sxs-lookup"><span data-stu-id="737e5-107">**To view or modify a condition's properties, using:**</span></span>  
  
     [<span data-ttu-id="737e5-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="737e5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="737e5-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="737e5-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="737e5-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="737e5-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="737e5-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="737e5-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="737e5-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="737e5-112">Permissions</span></span>  
 <span data-ttu-id="737e5-113">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="737e5-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="737e5-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="737e5-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-modify-a-conditions-properties"></a><span data-ttu-id="737e5-115">Para ver o modificar las propiedades de una condición</span><span class="sxs-lookup"><span data-stu-id="737e5-115">To view or modify a condition's properties</span></span>  
  
1.  <span data-ttu-id="737e5-116">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la condición que desea ver o modificar.</span><span class="sxs-lookup"><span data-stu-id="737e5-116">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="737e5-117">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="737e5-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="737e5-118">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="737e5-118">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="737e5-119">Haga clic en el signo más para expandir la carpeta **Condiciones** .</span><span class="sxs-lookup"><span data-stu-id="737e5-119">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="737e5-120">Haga clic con el botón derecho en la condición que quiere ver o editar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="737e5-120">Right-click the condition that you want to view or edit and select **Properties**.</span></span> <span data-ttu-id="737e5-121">Para más información sobre las opciones disponibles en el cuadro de diálogo **Abrir condición: -**_nombre_de_condición_, vea [Cuadro de diálogo Crear nueva condición o Abrir condición, página General](../../integration-services/general-page-of-integration-services-designers-options.md), [Cuadro de diálogo Abrir condición, página Directivas dependientes](open-condition-dialog-box-dependent-policies-page.md), [Cuadro de diálogo Crear nueva condición o Abrir condición, página Descripción](create-new-condition-or-open-condition-dialog-box-description-page.md) y [Cuadro de diálogo Edición avanzada &#40;condición&#41;](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="737e5-121">For more information on the available options in the **Open Condition -**_condition_name_ dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Open Condition Dialog Box, Dependent Policies Page](open-condition-dialog-box-dependent-policies-page.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="737e5-122">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="737e5-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="737e5-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="737e5-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-conditions-properties"></a><span data-ttu-id="737e5-124">Para ver las propiedades de una condición</span><span class="sxs-lookup"><span data-stu-id="737e5-124">To view a condition's properties</span></span>  
  
1.  <span data-ttu-id="737e5-125">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="737e5-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="737e5-126">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="737e5-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="737e5-127">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="737e5-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       description,  
       facet,  
       expression,  
       is_name_condition,  
       obj_name  
    FROM syspolicy_conditions;  
    GO  
  
    ```  
  
 <span data-ttu-id="737e5-128">Para obtener más información, vea [syspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="737e5-128">For more information, see [syspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span></span>  
  
  
