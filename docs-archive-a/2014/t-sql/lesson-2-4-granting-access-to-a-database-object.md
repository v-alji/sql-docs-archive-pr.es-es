---
title: Concesión de acceso a un objeto de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- granting access to database objects
ms.assetid: a44d9bbf-f58e-4734-b7f4-eb3b492b777b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 22bd0bb1f01e59ec30f7cf1bbf128c890d3d5d64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676766"
---
# <a name="granting-access-to-a-database-object"></a><span data-ttu-id="dd1fd-102">Conceder acceso a un objeto de base de datos</span><span class="sxs-lookup"><span data-stu-id="dd1fd-102">Granting Access to a Database Object</span></span>
  <span data-ttu-id="dd1fd-103"> Como administrador, puede ejecutar la instrucción SELECT desde la tabla **Products** y la vista **vw_Names** y ejecutar el procedimiento **pr_Names**; en cambio, Mary no puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="dd1fd-103">As an administrator, you can execute the SELECT from the **Products** table and the **vw_Names** view, and execute the **pr_Names** procedure; however, Mary cannot.</span></span> <span data-ttu-id="dd1fd-104">Para conceder a Mary los permisos necesarios, use la instrucción GRANT.</span><span class="sxs-lookup"><span data-stu-id="dd1fd-104">To grant Mary the necessary permissions, use the GRANT statement.</span></span>  
  
### <a name="procedure-title"></a><span data-ttu-id="dd1fd-105">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="dd1fd-105">Procedure Title</span></span>  
  
1.  <span data-ttu-id="dd1fd-106">Ejecute la siguiente instrucción para conceder a `Mary` el permiso `EXECUTE` para el procedimiento almacenado `pr_Names` .</span><span class="sxs-lookup"><span data-stu-id="dd1fd-106">Execute the following statement to give `Mary` the `EXECUTE` permission for the `pr_Names` stored procedure.</span></span>  
  
    ```  
    GRANT EXECUTE ON pr_Names TO Mary;  
    GO  
    ```  
  
 <span data-ttu-id="dd1fd-107">En este escenario, Mary solo puede tener acceso a la tabla **Products** si utiliza el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="dd1fd-107">In this scenario, Mary can only access the **Products** table by using the stored procedure.</span></span> <span data-ttu-id="dd1fd-108">Si desea que Mary pueda ejecutar una instrucción SELECT con la vista, también debe ejecutar `GRANT SELECT ON vw_Names TO Mary`.</span><span class="sxs-lookup"><span data-stu-id="dd1fd-108">If you want Mary to be able to execute a SELECT statement against the view, then you must also execute `GRANT SELECT ON vw_Names TO Mary`.</span></span> <span data-ttu-id="dd1fd-109">Para quitar el acceso a objetos de base de datos, use la instrucción REVOKE.</span><span class="sxs-lookup"><span data-stu-id="dd1fd-109">To remove access to database objects, use the REVOKE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd1fd-110">Si la tabla, la vista y el procedimiento almacenado no son propiedad del mismo esquema, la concesión de permisos es más compleja.</span><span class="sxs-lookup"><span data-stu-id="dd1fd-110">If the table, the view, and the stored procedure are not owned by the same schema, granting permissions becomes more complex.</span></span>  
  
## <a name="about-grant"></a><span data-ttu-id="dd1fd-111">Acerca de GRANT</span><span class="sxs-lookup"><span data-stu-id="dd1fd-111">About GRANT</span></span>  
 <span data-ttu-id="dd1fd-112">Para ejecutar un procedimiento almacenado, debe tener permiso EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="dd1fd-112">You must have EXECUTE permission to execute a stored procedure.</span></span> <span data-ttu-id="dd1fd-113">Para tener acceso a datos y cambiarlos, debe tener permisos SELECT, INSERT, UPDATE y DELETE.</span><span class="sxs-lookup"><span data-stu-id="dd1fd-113">You must have SELECT, INSERT, UPDATE, and DELETE permissions to access and change data.</span></span> <span data-ttu-id="dd1fd-114">La instrucción GRANT también se usa para otros permisos, como el permiso para crear tablas.</span><span class="sxs-lookup"><span data-stu-id="dd1fd-114">The GRANT statement is also used for other permissions, such as permission to create tables.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dd1fd-115">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="dd1fd-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dd1fd-116">Resumen: Configuración de permisos en objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="dd1fd-116">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="dd1fd-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd1fd-117">See Also</span></span>  
 <span data-ttu-id="dd1fd-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dd1fd-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="dd1fd-119">REVOKE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dd1fd-119">REVOKE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/revoke-transact-sql)  
  
  
