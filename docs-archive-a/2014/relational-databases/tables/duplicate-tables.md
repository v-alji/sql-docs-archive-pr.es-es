---
title: Tablas duplicadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- tables [SQL Server], duplicating
- duplicating tables
- table copying [SQL Server]
ms.assetid: c6b07423-d1e5-4e5e-8681-5088921f5df3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 793a38416f86a5b43a3e3bb2420127d7acf2af1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670911"
---
# <a name="duplicate-tables"></a><span data-ttu-id="a4626-102">Tablas duplicadas</span><span class="sxs-lookup"><span data-stu-id="a4626-102">Duplicate Tables</span></span>
  <span data-ttu-id="a4626-103">Puede duplicar una tabla existente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] si crea una nueva tabla y, a continuación, copia la información de columna de una tabla existente.</span><span class="sxs-lookup"><span data-stu-id="a4626-103">You can duplicate an existing table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] by creating a new table and then copying column information from an existing table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a4626-104">Esta operación solo duplica la estructura de la tabla, pero no duplica ninguna fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a4626-104">This operation duplicates only the structure of a table; it does not duplicate any table rows.</span></span>  
  
 <span data-ttu-id="a4626-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a4626-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a4626-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a4626-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a4626-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a4626-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a4626-108">**Para duplicar una tabla con:**</span><span class="sxs-lookup"><span data-stu-id="a4626-108">**To duplicate a table, using:**</span></span>  
  
     [<span data-ttu-id="a4626-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4626-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a4626-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a4626-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a4626-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a4626-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a4626-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a4626-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a4626-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="a4626-113">Permissions</span></span>  
 <span data-ttu-id="a4626-114">Requiere el permiso CREATE TABLE en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="a4626-114">Requires CREATE TABLE permission in the destination database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a4626-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4626-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-duplicate-a-table"></a><span data-ttu-id="a4626-116">Para duplicar una tabla</span><span class="sxs-lookup"><span data-stu-id="a4626-116">To duplicate a table</span></span>  
  
1.  <span data-ttu-id="a4626-117">Asegúrese de que está conectado a la base de datos en la que desea crear la tabla y de que la base de datos está seleccionada en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="a4626-117">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="a4626-118">En el Explorador de objetos, haga clic con el botón derecho en **Tablas** y, luego, haga clic en **Nueva tabla**.</span><span class="sxs-lookup"><span data-stu-id="a4626-118">In Object Explorer, right-click **Tables** and click **New Table**.</span></span>  
  
3.  <span data-ttu-id="a4626-119">En el Explorador de objetos, haga clic con el botón derecho en la tabla que quiera copiar y, depués, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="a4626-119">In Object Explorer right-click the table you want to copy and click **Design**.</span></span>  
  
4.  <span data-ttu-id="a4626-120">Seleccione las columnas de la tabla existente y haga clic en **Copiar** en el menú **Edición**.</span><span class="sxs-lookup"><span data-stu-id="a4626-120">Select the columns in the existing table and, from the **Edit** menu, click **Copy**.</span></span>  
  
5.  <span data-ttu-id="a4626-121">Vuelva a la ventana nueva y seleccione la primera fila.</span><span class="sxs-lookup"><span data-stu-id="a4626-121">Switch back to the new table and select the first row.</span></span>  
  
6.  <span data-ttu-id="a4626-122">En el menú **Edición** , haga clic en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="a4626-122">From the **Edit** menu, click **Paste**.</span></span>  
  
7.  <span data-ttu-id="a4626-123">En el menú **Archivo** , haga clic en **Guardar**_nombre de tabla_.</span><span class="sxs-lookup"><span data-stu-id="a4626-123">From the **File** menu, click **Save**_table name_.</span></span>  
  
8.  <span data-ttu-id="a4626-124">En el cuadro de diálogo **Elegir nombre** , escriba un nombre para la tabla nueva y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4626-124">In the **Choose Name** dialog box, type a name for the new table and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a4626-125">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a4626-125">Using Transact-SQL</span></span>  
  
#### <a name="to-duplicate-a-table-in-query-editor"></a><span data-ttu-id="a4626-126">Para duplicar una tabla en el editor de consultas</span><span class="sxs-lookup"><span data-stu-id="a4626-126">To duplicate a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="a4626-127">Asegúrese de que está conectado a la base de datos en la que desea crear la tabla y de que la base de datos está seleccionada en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="a4626-127">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="a4626-128">Haga clic con el botón derecho en la tabla que quiera duplicar, seleccione **Incluir tabla como**, seleccione **CREATE to**y, por último, **Nueva ventana del Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="a4626-128">Right-click the table you wish to duplicate, point to **Script Table as**, then point to **CREATE to**, and then select **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="a4626-129">Cambie el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a4626-129">Change the name of the table.</span></span>  
  
4.  <span data-ttu-id="a4626-130">Quite las columnas que no se necesiten en la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="a4626-130">Remove any columns that are not needed in the new table.</span></span>  
  
5.  <span data-ttu-id="a4626-131">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a4626-131">Click **Execute**.</span></span>  
  
  
