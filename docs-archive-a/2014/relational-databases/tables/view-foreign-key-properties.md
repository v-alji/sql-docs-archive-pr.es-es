---
title: Ver las propiedades de clave externa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], attributes
- displaying foreign keys attributes
- viewing foreign keys attributes
ms.assetid: b0e57cb7-9b26-4b96-b76a-1f59f5f498c5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5860a0cf26b983d75bab86862ee1e5fdd7737712
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663302"
---
# <a name="view-foreign-key-properties"></a><span data-ttu-id="98ee9-102">Ver las propiedades de clave externa</span><span class="sxs-lookup"><span data-stu-id="98ee9-102">View Foreign Key Properties</span></span>
  <span data-ttu-id="98ee9-103">Puede ver los atributos de clave externa de una relación en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ee9-103">You can view the foreign key attributes of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="98ee9-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="98ee9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="98ee9-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="98ee9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="98ee9-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="98ee9-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="98ee9-107">**Para ver los atributos de clave externa de una tabla específica, use:**</span><span class="sxs-lookup"><span data-stu-id="98ee9-107">**To view the foreign key attributes of a specific table, using:**</span></span>  
  
     [<span data-ttu-id="98ee9-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98ee9-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="98ee9-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98ee9-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="98ee9-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="98ee9-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="98ee9-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="98ee9-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="98ee9-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="98ee9-112">Permissions</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="98ee9-113">Para obtener más información, consulte [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="98ee9-113">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="98ee9-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98ee9-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a><span data-ttu-id="98ee9-115">Para ver los atributos de clave externa de una relación en una tabla específica</span><span class="sxs-lookup"><span data-stu-id="98ee9-115">To view the foreign key attributes of a relationship in a specific table</span></span>  
  
1.  <span data-ttu-id="98ee9-116">Abra en el Diseñador de tablas la tabla que contiene la clave externa que quiera ver; después, haga clic con el botón derecho en el Diseñador de tablas y elija **Relaciones** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="98ee9-116">Open the Table Designer for the table containing the foreign key you want to view, right-click in the Table Designer, and choose **Relationships** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="98ee9-117">En el cuadro de diálogo **Relaciones de clave externa** , seleccione la relación con propiedades que desea ver.</span><span class="sxs-lookup"><span data-stu-id="98ee9-117">In the **Foreign Key Relationships** dialog box, select the relationship with properties you want to view.</span></span>  
  
 <span data-ttu-id="98ee9-118">Si las columnas de clave externa están relacionadas con una clave principal, las columnas de clave principal se identifican en el **Diseñador de tablas** mediante un símbolo de clave principal en el selector de fila.</span><span class="sxs-lookup"><span data-stu-id="98ee9-118">If the foreign key columns are related to a primary key, the primary key columns are identified in **Table Designer** by a primary key symbol in the row selector.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="98ee9-119">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98ee9-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a><span data-ttu-id="98ee9-120">Para ver los atributos de clave externa de una relación en una tabla específica</span><span class="sxs-lookup"><span data-stu-id="98ee9-120">To view the foreign key attributes of a relationship in a specific table</span></span>  
  
1.  <span data-ttu-id="98ee9-121">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ee9-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="98ee9-122">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="98ee9-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="98ee9-123">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="98ee9-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="98ee9-124">El ejemplo devuelve todas las claves externas y sus propiedades para la tabla `HumanResources.Employee` en la base de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="98ee9-124">The example returns all foreign keys and their properties for the table `HumanResources.Employee` in the sample database.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT   
        f.name AS foreign_key_name  
       ,OBJECT_NAME(f.parent_object_id) AS table_name  
       ,COL_NAME(fc.parent_object_id, fc.parent_column_id) AS constraint_column_name  
       ,OBJECT_NAME (f.referenced_object_id) AS referenced_object  
       ,COL_NAME(fc.referenced_object_id, fc.referenced_column_id) AS referenced_column_name  
       ,is_disabled  
       ,delete_referential_action_desc  
       ,update_referential_action_desc  
    FROM sys.foreign_keys AS f  
    INNER JOIN sys.foreign_key_columns AS fc   
       ON f.object_id = fc.constraint_object_id   
    WHERE f.parent_object_id = OBJECT_ID('HumanResources.Employee');  
    ```  
  
 <span data-ttu-id="98ee9-125">Para obtener más información, vea [sys.foreign_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) y [sys.foreign_key_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="98ee9-125">For more information, see [sys.foreign_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) and [sys.foreign_key_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
