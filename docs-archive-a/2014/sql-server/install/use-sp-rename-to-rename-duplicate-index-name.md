---
title: Usar sp_rename para cambiar el nombre del índice duplicado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- table names [SQL Server]
- duplicate table names
- index names [SQL Server]
- sp_rename
- duplicate index names
ms.assetid: ee66c7a5-eb6d-4fcf-970c-ab099d78c8d9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b8ffe3b9befd0c7239d32094e5738e0fb2947c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751661"
---
# <a name="use-sp_rename-to-rename-duplicate-index-name"></a><span data-ttu-id="01789-102">Utilizar sp_rename para cambiar el nombre de índice duplicado</span><span class="sxs-lookup"><span data-stu-id="01789-102">Use sp_rename to rename duplicate index name</span></span>
  <span data-ttu-id="01789-103">El Asesor de actualizaciones ha detectado nombres de índice de vista o tabla duplicados.</span><span class="sxs-lookup"><span data-stu-id="01789-103">Upgrade Advisor has detected duplicate table or view index names.</span></span> <span data-ttu-id="01789-104">Cambie los nombres de los índices o quite los duplicados antes de actualizar.</span><span class="sxs-lookup"><span data-stu-id="01789-104">Rename the indexes to remove duplicates before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="01789-105">Componente</span><span class="sxs-lookup"><span data-stu-id="01789-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="01789-106">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="01789-106">Corrective Action</span></span>  
  
1.  <span data-ttu-id="01789-107">Localice los índices duplicados ejecutando la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="01789-107">Locate the duplicate indexes by executing the following query.</span></span>  
  
    ```  
    SELECT DISTINCT OBJECT_NAME(o.id), name  
    FROM sysindexes as o  
    WHERE EXISTS   
        (SELECT name FROM sysindexes  as i  
          WHERE i.id = o.id  
          AND i.name = o.name and i.indid < o.indid);  
    ```  
  
2.  <span data-ttu-id="01789-108">Utilice **sp_rename** para cambiar uno de los nombres de índice.</span><span class="sxs-lookup"><span data-stu-id="01789-108">Use **sp_rename** to change one of the index names.</span></span> <span data-ttu-id="01789-109">Como los nombres de índice son los mismos, no puede determinar qué índice cambiará de nombre.</span><span class="sxs-lookup"><span data-stu-id="01789-109">Because the index names are the same, you cannot determine which index will be renamed.</span></span> <span data-ttu-id="01789-110">Este paso le permite diferenciar los índices.</span><span class="sxs-lookup"><span data-stu-id="01789-110">This step allows you to differentiate the indexes.</span></span>  
  
    ```  
    EXEC sp_rename N'table_name.index_name', N'new_index_name', N'INDEX'  
    ```  
  
3.  <span data-ttu-id="01789-111">Compruebe qué índice ha cambiado de nombre ejecutando la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="01789-111">Verify which index was renamed by executing the following query.</span></span> <span data-ttu-id="01789-112">Esta consulta devuelve todos los índices (incluidos los nombres de columnas de clave) de la vista o tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="01789-112">This query returns all indexes (including key column names) on the specified table or view.</span></span>  
  
    ```  
    SELECT i.name AS IndexName, c.name AS ColumnName, ik.colid, ik.keyno  
    FROM sysindexes i  
    JOIN sysindexkeys ik ON i.id = ik.id and i.indid = ik.indid   
    JOIN syscolumns c ON c.id = ik.id and ik.colid = c.colid  
    WHERE i.id = OBJECT_ID('table_or_view_name')  
    ```  
  
4.  <span data-ttu-id="01789-113">Si fuera necesario, utilice de nuevo **sp_rename** para corregir los nombres de índice.</span><span class="sxs-lookup"><span data-stu-id="01789-113">If necessary, use **sp_rename** again to correct the index names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01789-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01789-114">See Also</span></span>  
 <span data-ttu-id="01789-115">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="01789-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="01789-116">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="01789-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
