---
title: Establezca la intercalación de bases de datos definidas por el usuario para que coincidan con las de las bases de datos maestra y modelo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: c686446f-dae1-4b05-a3df-837b3422988d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b48696fb56c40062d62f04845715170887f84fda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744290"
---
# <a name="set-the-collation-of-user-defined-databases-to-match-those-of-the-master-and-model-databases"></a><span data-ttu-id="2377b-102">Establecer la intercalación de bases de datos definidas por el usuario para que coincidan con las de las bases de datos modelo y maestra</span><span class="sxs-lookup"><span data-stu-id="2377b-102">Set the Collation of User-defined Databases to Match Those of the master and model Databases</span></span>
  <span data-ttu-id="2377b-103">Esta regla comprueba si las bases de datos definidas por el usuario se definen utilizando una intercalación de base de datos que es igual a la intercalación de las bases de datos maestra o modelo.</span><span class="sxs-lookup"><span data-stu-id="2377b-103">This rule checks whether user-defined databases are defined by using a database collation that is the same as the collation for master or model.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="2377b-104">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="2377b-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="2377b-105">Recomendamos que las intercalaciones de bases de datos definidas por el usuario coincidan con la intercalación de las bases de datos maestra o modelo.</span><span class="sxs-lookup"><span data-stu-id="2377b-105">We recommend that the collations of user-defined databases match the collation of master or model.</span></span> <span data-ttu-id="2377b-106">De lo contrario, pueden producirse conflictos de intercalación que podrían impedir que el código se ejecute.</span><span class="sxs-lookup"><span data-stu-id="2377b-106">Otherwise, collation conflicts can occur that might prevent code from executing.</span></span> <span data-ttu-id="2377b-107">Por ejemplo, cuando un procedimiento almacenado une una tabla a una tabla temporal, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] podría finalizar el lote y devolver un error de conflicto de intercalación si las intercalaciones de la base de datos definida por el usuario y la base de datos modelo son diferentes.</span><span class="sxs-lookup"><span data-stu-id="2377b-107">For example, when a stored procedure joins one table to a temporary table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] might end the batch and return a collation conflict error if the collations of the user-defined database and the model database are different.</span></span> <span data-ttu-id="2377b-108">Esto se debe a que las tablas temporales se crean en tempdb, que basa su intercalación en la de la base de datos modelo.</span><span class="sxs-lookup"><span data-stu-id="2377b-108">This occurs because temporary tables are created in tempdb, which bases its collation on that of model.</span></span>  
  
 <span data-ttu-id="2377b-109">Si experimenta errores de conflictos de intercalación, considere una de las soluciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2377b-109">If you experience collation conflict errors, consider one of the following solutions:</span></span>  
  
-   <span data-ttu-id="2377b-110">Exporte los datos de la base de datos de usuario e impórtelos en tablas nuevas que tengan la misma intercalación que las bases de datos modelo y maestra.</span><span class="sxs-lookup"><span data-stu-id="2377b-110">Export the data from the user database and import it into new tables that have the same collation as the master and model databases.</span></span>  
  
-   <span data-ttu-id="2377b-111">Vuelva a generar las bases de datos del sistema para utilizar una intercalación que coincida con la intercalación de las bases de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="2377b-111">Rebuild the system databases to use a collation that matches the user database collation.</span></span> <span data-ttu-id="2377b-112">Para obtener más información acerca de cómo volver a generar las bases de datos del sistema, vea [volver a generar bases de datos del sistema](../relational-databases/databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2377b-112">For more information about how to rebuild the system databases, see [Rebuild System Databases](../relational-databases/databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="2377b-113">Modifique cualquier procedimiento almacenado que una las tablas de usuario a las tablas en tempdb para crear las tablas en tempdb utilizando la intercalación de la base de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="2377b-113">Modify any stored procedures that join user tables to tables in tempdb to create the tables in tempdb by using the collation of the user database.</span></span> <span data-ttu-id="2377b-114">Para ello, agregue la cláusula `COLLATE database_default` a las definiciones de columna de la tabla temporal, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2377b-114">To do this, add the `COLLATE database_default` clause to the column definitions of the temporary table, as shown in the following example:</span></span>  
  
    ```  
    CREATE TABLE #temp1 ( c1 int, c2 varchar(30) COLLATE database_default )  
    ```  
  
## <a name="for-more-information"></a><span data-ttu-id="2377b-115">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="2377b-115">For More Information</span></span>  
 [<span data-ttu-id="2377b-116">Establecer o cambiar la intercalación de base de datos</span><span class="sxs-lookup"><span data-stu-id="2377b-116">Set or Change the Database Collation</span></span>](../relational-databases/collations/set-or-change-the-database-collation.md)  
  
 [<span data-ttu-id="2377b-117">Establecer o cambiar la intercalación de columnas</span><span class="sxs-lookup"><span data-stu-id="2377b-117">Set or Change the Column Collation</span></span>](../relational-databases/collations/set-or-change-the-column-collation.md)  
  
 [<span data-ttu-id="2377b-118">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2377b-118">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
 [<span data-ttu-id="2377b-119">COLLATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2377b-119">COLLATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/collations)  
  
 [<span data-ttu-id="2377b-120">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2377b-120">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
 [<span data-ttu-id="2377b-121">Artículo 325335 de Microsoft Knowledge base</span><span class="sxs-lookup"><span data-stu-id="2377b-121">Microsoft Knowledge Base article 325335</span></span>](https://go.microsoft.com/fwlink/?linkid=117751)  
  
 [<span data-ttu-id="2377b-122">Cómo instalar SQL Server 2008 desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="2377b-122">How to: Install SQL Server 2008 from the Command Prompt</span></span>](https://go.microsoft.com/fwlink/?LinkId=81585)  
  
## <a name="see-also"></a><span data-ttu-id="2377b-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2377b-123">See Also</span></span>  
 [<span data-ttu-id="2377b-124">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="2377b-124">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
