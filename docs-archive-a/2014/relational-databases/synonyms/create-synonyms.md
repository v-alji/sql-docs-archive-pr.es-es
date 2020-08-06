---
title: Creación de sinónimos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
f1_keywords:
- sql12.swb.synonym.general.f1
helpviewer_keywords:
- creating synonyms
- synonyms [SQL Server], creating
ms.assetid: fedfa7a5-d0b6-4e2b-90f4-a08122958e33
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dc18c9d0d6048c4190ba56725dd332f2dfb629e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661868"
---
# <a name="create-synonyms"></a><span data-ttu-id="06507-102">Crear sinónimos</span><span class="sxs-lookup"><span data-stu-id="06507-102">Create Synonyms</span></span>
  <span data-ttu-id="06507-103">En este tema se describe cómo crear un sinónimo en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06507-103">This topic describes how to create a synonym in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="06507-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="06507-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="06507-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="06507-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="06507-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="06507-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="06507-107">**Para crear un sinónimo, mediante:**</span><span class="sxs-lookup"><span data-stu-id="06507-107">**To create a synonym, using:**</span></span>  
  
     [<span data-ttu-id="06507-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06507-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="06507-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06507-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="06507-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="06507-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="06507-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="06507-111">Security</span></span>  
 <span data-ttu-id="06507-112">Para crear un sinónimo en un esquema determinado, el usuario debe tener el permiso CREATE SYNONYM y ser propietario del esquema o tener el permiso ALTER SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="06507-112">To create a synonym in a given schema, a user must have CREATE SYNONYM permission and either own the schema or have ALTER SCHEMA permission.</span></span> <span data-ttu-id="06507-113">El permiso CREATE SYNONYM se puede conceder.</span><span class="sxs-lookup"><span data-stu-id="06507-113">The CREATE SYNONYM permission is a grantable permission.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="06507-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="06507-114">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="06507-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06507-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="06507-116">Para crear un sinónimo</span><span class="sxs-lookup"><span data-stu-id="06507-116">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="06507-117">En el **Explorador de objetos**, expanda la base de datos donde desea crear la nueva vista.</span><span class="sxs-lookup"><span data-stu-id="06507-117">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="06507-118">Haga clic con el botón derecho en la carpeta **Sinónimos** y después haga clic en **Nuevo sinónimo...** .</span><span class="sxs-lookup"><span data-stu-id="06507-118">Right-click the **Synonyms** folder, then click **New Synonym...**.</span></span>  
  
3.  <span data-ttu-id="06507-119">En el cuadro de diálogo **Agregar sinónimo** , escriba la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="06507-119">In the **Add Synonym** dialog box, enter the following information.</span></span>  
  
     <span data-ttu-id="06507-120">**Nombre de sinónimo**</span><span class="sxs-lookup"><span data-stu-id="06507-120">**Synonym name**</span></span>  
     <span data-ttu-id="06507-121">Escriba el nombre que desea utilizar para este objeto.</span><span class="sxs-lookup"><span data-stu-id="06507-121">Type the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="06507-122">**Esquema de sinónimos**</span><span class="sxs-lookup"><span data-stu-id="06507-122">**Synonym schema**</span></span>  
     <span data-ttu-id="06507-123">Escriba el esquema del nuevo nombre que desea utilizar para este objeto.</span><span class="sxs-lookup"><span data-stu-id="06507-123">Type the schema of the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="06507-124">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="06507-124">**Server name**</span></span>  
     <span data-ttu-id="06507-125">Escriba la instancia de servidor a la que va a conectarse.</span><span class="sxs-lookup"><span data-stu-id="06507-125">Type the server instance to connect to.</span></span>  
  
     <span data-ttu-id="06507-126">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="06507-126">**Database name**</span></span>  
     <span data-ttu-id="06507-127">Escriba o seleccione la base de datos que contiene el objeto.</span><span class="sxs-lookup"><span data-stu-id="06507-127">Type or select the database containing the object.</span></span>  
  
     <span data-ttu-id="06507-128">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="06507-128">**Schema**</span></span>  
     <span data-ttu-id="06507-129">Escriba o seleccione el esquema al que pertenece el objeto.</span><span class="sxs-lookup"><span data-stu-id="06507-129">Type or select the schema that owns the object.</span></span>  
  
     <span data-ttu-id="06507-130">**Tipo de objeto**</span><span class="sxs-lookup"><span data-stu-id="06507-130">**Object type**</span></span>  
     <span data-ttu-id="06507-131">Seleccione el tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="06507-131">Select the type of object.</span></span>  
  
     <span data-ttu-id="06507-132">**Nombre de objeto**</span><span class="sxs-lookup"><span data-stu-id="06507-132">**Object name**</span></span>  
     <span data-ttu-id="06507-133">Escriba el nombre del objeto al que hace referencia el sinónimo.</span><span class="sxs-lookup"><span data-stu-id="06507-133">Type the name of the object to which the synonym refers.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="06507-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06507-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="06507-135">Para crear un sinónimo</span><span class="sxs-lookup"><span data-stu-id="06507-135">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="06507-136">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06507-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="06507-137">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="06507-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="06507-138">Copie y pegue los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="06507-138">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="06507-139">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06507-139">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="06507-140">En el siguiente ejemplo se crea un sinónimo para una tabla existente en la base de datos de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="06507-140">The following example creates a synonym for an existing table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="06507-141">El sinónimo se utiliza en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="06507-141">The synonym is then used in subsequent examples.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyAddressType  
FOR AdventureWorks2012.Person.AddressType;  
GO  
```  
  
 <span data-ttu-id="06507-142">En el siguiente ejemplo se inserta una fila en la tabla base a la que hace referencia el sinónimo `MyAddressType` .</span><span class="sxs-lookup"><span data-stu-id="06507-142">The following example inserts a row into the base table that is referenced by the `MyAddressType` synonym.</span></span>  
  
```  
USE tempdb;  
GO  
INSERT INTO MyAddressType (Name)  
VALUES ('Test');  
GO  
```  
  
 <span data-ttu-id="06507-143">En el siguiente ejemplo se muestra cómo se puede hacer referencia a un sinónimo en SQL dinámica.</span><span class="sxs-lookup"><span data-stu-id="06507-143">The following example demonstrates how a synonym can be referenced in dynamic SQL.</span></span>  
  
```  
USE tempdb;  
GO  
EXECUTE ('SELECT Name FROM MyAddressType');  
GO  
```  
  
  
