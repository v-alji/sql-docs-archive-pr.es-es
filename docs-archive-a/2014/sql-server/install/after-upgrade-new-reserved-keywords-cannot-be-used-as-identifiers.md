---
title: Después de la actualización, las nuevas palabras clave reservadas no se pueden usar como identificadores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- keywords [SQL Server], after upgrade
- keywords [SQL Server], reserved
- keywords [SQL Server]
ms.assetid: cb242081-54f8-4273-a8ef-52f3751c25ef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 36f7f8cadcba5e114feee4a3c42de6f40070ce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672532"
---
# <a name="after-upgrade-new-reserved-keywords-cannot-be-used-as-identifiers"></a><span data-ttu-id="523b1-102">Después de la actualización, las nuevas palabras clave reservadas no se pueden utilizar como identificadores</span><span class="sxs-lookup"><span data-stu-id="523b1-102">After upgrade, new reserved keywords cannot be used as identifiers</span></span>
  <span data-ttu-id="523b1-103">El Asesor de actualizaciones detectó el uso de palabras que son palabras clave reservadas.</span><span class="sxs-lookup"><span data-stu-id="523b1-103">Upgrade Advisor detected the use of words that are reserved keywords.</span></span> <span data-ttu-id="523b1-104">Una palabra clave reservada no se puede utilizar como identificador o nombre de objeto a menos que el nombre se delimite.</span><span class="sxs-lookup"><span data-stu-id="523b1-104">A reserved keyword cannot be used as an identifier or object name unless the name is delimited.</span></span>  
  
## <a name="component"></a><span data-ttu-id="523b1-105">Componente</span><span class="sxs-lookup"><span data-stu-id="523b1-105">Component</span></span>  
 <span data-ttu-id="523b1-106">Motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="523b1-106">Database Engine</span></span>  
  
## <a name="description"></a><span data-ttu-id="523b1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="523b1-107">Description</span></span>  
 <span data-ttu-id="523b1-108">En el nivel de compatibilidad 90 o inferior, las palabras siguientes no son palabras clave reservadas y se pueden utilizar como identificadores o nombres de objeto en scripts de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="523b1-108">At compatibility level 90 or lower, the following words are not reserved keywords and can be used as identifiers or object names in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="523b1-109">En el nivel de compatibilidad 100, estas palabras son palabras clave totalmente reservadas y no se deben utilizar como identificadores o nombres de objeto.</span><span class="sxs-lookup"><span data-stu-id="523b1-109">At compatibility level 100, these words are fully reserved keywords and should not be used as identifiers or object names.</span></span>  
  
-   <span data-ttu-id="523b1-110">EXTERNAL</span><span class="sxs-lookup"><span data-stu-id="523b1-110">EXTERNAL</span></span>  
  
-   <span data-ttu-id="523b1-111">MERGE</span><span class="sxs-lookup"><span data-stu-id="523b1-111">MERGE</span></span>  
  
-   <span data-ttu-id="523b1-112">PIVOT</span><span class="sxs-lookup"><span data-stu-id="523b1-112">PIVOT</span></span>  
  
-   <span data-ttu-id="523b1-113">REVERT</span><span class="sxs-lookup"><span data-stu-id="523b1-113">REVERT</span></span>  
  
-   <span data-ttu-id="523b1-114">STOPLIST</span><span class="sxs-lookup"><span data-stu-id="523b1-114">STOPLIST</span></span>  
  
-   <span data-ttu-id="523b1-115">TABLESAMPLE</span><span class="sxs-lookup"><span data-stu-id="523b1-115">TABLESAMPLE</span></span>  
  
-   <span data-ttu-id="523b1-116">UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="523b1-116">UNPIVOT</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="523b1-117">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="523b1-117">Corrective Action</span></span>  
 <span data-ttu-id="523b1-118">Recomendamos que cambie el nombre del objeto.</span><span class="sxs-lookup"><span data-stu-id="523b1-118">We recommend that you rename the object.</span></span> <span data-ttu-id="523b1-119">Si no es posible antes de actualizar, utilice uno de los métodos siguientes hasta que se pueda cambiar el nombre:</span><span class="sxs-lookup"><span data-stu-id="523b1-119">If that cannot be done before upgrading, use one of the following methods until the name can be changed:</span></span>  
  
-   <span data-ttu-id="523b1-120">Conserve el valor de nivel de compatibilidad de la base de datos en 90 o inferior.</span><span class="sxs-lookup"><span data-stu-id="523b1-120">Retain the database compatibility level setting of 90 or lower.</span></span>  
  
-   <span data-ttu-id="523b1-121">Consulte el objeto utilizando identificadores delimitados.</span><span class="sxs-lookup"><span data-stu-id="523b1-121">Refer to the object by using delimited identifiers.</span></span> <span data-ttu-id="523b1-122">Por ejemplo, la instrucción `CREATE TABLE [MERGE] ([MERGE] int);` usa corchetes para delimitar el nombre de objeto Merge.</span><span class="sxs-lookup"><span data-stu-id="523b1-122">For example, the statement `CREATE TABLE [MERGE] ([MERGE] int);` uses brackets to delimit the object name MERGE.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="523b1-123">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="523b1-123">External Resources</span></span>  
 [<span data-ttu-id="523b1-124">Palabras clave reservadas &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="523b1-124">Reserved Keywords &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reserved-keywords-transact-sql)  
  
 [<span data-ttu-id="523b1-125">MERGE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="523b1-125">MERGE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/merge-transact-sql)  
  
 [<span data-ttu-id="523b1-126">Identificadores delimitados (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="523b1-126">Delimited Identifiers (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112509)  
  
 [<span data-ttu-id="523b1-127">Nivel de compatibilidad de ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="523b1-127">ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level)  
  
  
