---
title: Creación de una clave maestra de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2019
ms.prod: sql-server-2014
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], creating
ms.assetid: 8cb24263-e97d-4e4d-9429-6cf494a4d5eb
author: jaszymas
ms.author: jaszymas
ms.reviewer: carlrab
ms.openlocfilehash: cb8305d9d5a3c72e6dffafd231f21110a5abdd14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750614"
---
# <a name="create-a-database-master-key"></a><span data-ttu-id="6475b-102">Crear la clave maestra de una base de datos</span><span class="sxs-lookup"><span data-stu-id="6475b-102">Create a Database Master Key</span></span>

<span data-ttu-id="6475b-103">En este tema se describe cómo crear una clave maestra de base de datos en la `master` base de datos de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6475b-103">This topic describes how to create a database master key in the `master` database in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>

<span data-ttu-id="6475b-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6475b-104">**In This Topic**</span></span>

- <span data-ttu-id="6475b-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6475b-105">**Before you begin:**</span></span>

  [<span data-ttu-id="6475b-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6475b-106">Security</span></span>](#Security)

- [<span data-ttu-id="6475b-107">Para crear una clave maestra de base de datos mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6475b-107">To create a database master key using Transact-SQL</span></span>](#TsqlProcedure)

## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6475b-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6475b-108">Before You Begin</span></span>

### <a name="security"></a><a name="Security"></a> <span data-ttu-id="6475b-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6475b-109">Security</span></span>

#### <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6475b-110">Permisos</span><span class="sxs-lookup"><span data-stu-id="6475b-110">Permissions</span></span>

<span data-ttu-id="6475b-111">Necesita el permiso CONTROL en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6475b-111">Requires CONTROL permission on the database.</span></span>

## <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6475b-112">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6475b-112">Using Transact-SQL</span></span>

### <a name="to-create-a-database-master-key"></a><span data-ttu-id="6475b-113">Para crear la clave maestra de una base de datos</span><span class="sxs-lookup"><span data-stu-id="6475b-113">To create a database master key</span></span>

1. <span data-ttu-id="6475b-114">Elija una contraseña para cifrar la copia de la clave maestra que se almacenará en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6475b-114">Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span>
2. <span data-ttu-id="6475b-115">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6475b-115">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>
3. <span data-ttu-id="6475b-116">Expanda **Bases de datos del sistema**, haga clic con el botón derecho en `master` y, después, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6475b-116">Expand **System Databases**, right-click `master` and then click **New Query**.</span></span>
4. <span data-ttu-id="6475b-117">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6475b-117">Copy and paste the following example into the query window and click **Execute**.</span></span>

  ```sql
  -- Creates the master key.
  -- The key is encrypted using the password "23987hxJ#KL95234nl0zBe."
  CREATE MASTER KEY ENCRYPTION BY PASSWORD = '23987hxJ#KL95234nl0zBe';
```

<span data-ttu-id="6475b-118">Para obtener más información, vea [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6475b-118">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql).</span></span>
