---
title: Cambiar el nombre de usuario sys | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sys user names [SQL Server]
ms.assetid: d622d646-83e4-4b6f-9a21-77b301af04b5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3af9d31a54adc5645cab6fcc7104ae7ff27a61b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662505"
---
# <a name="rename-user-sys"></a><span data-ttu-id="a97d6-102">Cambiar el nombre de usuario del sistema</span><span class="sxs-lookup"><span data-stu-id="a97d6-102">Rename user sys</span></span>
  <span data-ttu-id="a97d6-103">El Asesor de actualizaciones ha detectado el nombre de usuario **sys** en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="a97d6-103">Upgrade Advisor detected the user name **sys** in a database.</span></span> <span data-ttu-id="a97d6-104">Este nombre está reservado.</span><span class="sxs-lookup"><span data-stu-id="a97d6-104">This name is reserved.</span></span> <span data-ttu-id="a97d6-105">Cambie el nombre del usuario antes de actualizar.</span><span class="sxs-lookup"><span data-stu-id="a97d6-105">Rename the user before you upgrade.</span></span> <span data-ttu-id="a97d6-106">Si no se cambia el nombre del usuario, la base de datos quedará en estado sospechoso y no estará disponible hasta que se ponga en línea.</span><span class="sxs-lookup"><span data-stu-id="a97d6-106">If the user is not renamed, the database will be in a suspect state after the upgrade process and will be unavailable until the database is brought online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a97d6-107">Componente</span><span class="sxs-lookup"><span data-stu-id="a97d6-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a97d6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a97d6-108">Description</span></span>  
 <span data-ttu-id="a97d6-109">El usuario **sys** está reservado.</span><span class="sxs-lookup"><span data-stu-id="a97d6-109">User **sys** is reserved.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a97d6-110">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="a97d6-110">Corrective Action</span></span>  
  
### <a name="before-upgrade-procedure"></a><span data-ttu-id="a97d6-111">Procedimiento antes de la actualización</span><span class="sxs-lookup"><span data-stu-id="a97d6-111">Before Upgrade Procedure</span></span>  
 <span data-ttu-id="a97d6-112">Antes de actualizar, en cada base de datos que contenga el usuario **sys**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a97d6-112">Before you upgrade, in each database that contains user **sys**, do the following:</span></span>  
  
1.  <span data-ttu-id="a97d6-113">Cree un nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="a97d6-113">Create a new user.</span></span>  
  
2.  <span data-ttu-id="a97d6-114">Utilice la siguiente instrucción para mostrar todos los permisos concedidos por el usuario **sys** y concedidos al usuario **sys**.</span><span class="sxs-lookup"><span data-stu-id="a97d6-114">Use the following statements to display all permissions that are granted by user **sys** and granted to user **sys**.</span></span>  
  
    ```  
    -- Return permissions granted by user sys.  
    SELECT * FROM sysprotects WHERE grantor = USER_ID('sys')  
    -- Return permissions granted to user sys.  
    SELECT * FROM sysprotects WHERE uid = USER_ID('sys')  
    ```  
  
3.  <span data-ttu-id="a97d6-115">Para transferir al nuevo usuario la propiedad de todos los objetos pertenecientes a **sys** , utilice **sp_changeobjectowner**.</span><span class="sxs-lookup"><span data-stu-id="a97d6-115">To transfer ownership of all objects owned by **sys** to the new user, use **sp_changeobjectowner**.</span></span>  
  
4.  <span data-ttu-id="a97d6-116">Quite el usuario **sys**.</span><span class="sxs-lookup"><span data-stu-id="a97d6-116">Drop user **sys**.</span></span>  
  
5.  <span data-ttu-id="a97d6-117">Para restaurar los permisos originales capturados en el paso 2, utilice la cláusula AS *new_user* de la instrucción GRANT.</span><span class="sxs-lookup"><span data-stu-id="a97d6-117">To restore the original permissions captured in step 2, use the AS *new_user* clause of the GRANT statement.</span></span>  
  
6.  <span data-ttu-id="a97d6-118">Modifique los scripts que hacen referencia al nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="a97d6-118">Modify scripts to reference the new user.</span></span> <span data-ttu-id="a97d6-119">Por ejemplo, los scripts que contengan instrucciones como `SELECT * FROM sys.my`_`table` se deben cambiar a `SELECT * FROM new_user.my_table`.</span><span class="sxs-lookup"><span data-stu-id="a97d6-119">For example, scripts that contain statements such as `SELECT * FROM sys.my`_`table` must be changed to `SELECT * FROM new_user.my_table`.</span></span>  
  
### <a name="after-upgrade-procedure"></a><span data-ttu-id="a97d6-120">Procedimiento después de la actualización</span><span class="sxs-lookup"><span data-stu-id="a97d6-120">After Upgrade Procedure</span></span>  
 <span data-ttu-id="a97d6-121">Si no se ha cambiado el nombre del usuario **sys** antes de la actualización, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a97d6-121">If the user **sys** was not renamed prior to upgrading, do the following:</span></span>  
  
1.  <span data-ttu-id="a97d6-122">Ejecute la instrucción `ALTER DATABASE db_name SET ONLINE`.</span><span class="sxs-lookup"><span data-stu-id="a97d6-122">Execute the statement `ALTER DATABASE db_name SET ONLINE`.</span></span> <span data-ttu-id="a97d6-123">La base de datos estará en modo SINGLE_USER.</span><span class="sxs-lookup"><span data-stu-id="a97d6-123">The database will be in SINGLE_USER mode.</span></span>  
  
2.  <span data-ttu-id="a97d6-124">Siga todos los pasos de la sección Procedimiento antes de la actualización.</span><span class="sxs-lookup"><span data-stu-id="a97d6-124">Follow all steps in the Before Upgrade Procedure section.</span></span>  
  
3.  <span data-ttu-id="a97d6-125">Ejecute la instrucción `ALTER DATABASE db_name SET MULTI_USER`.</span><span class="sxs-lookup"><span data-stu-id="a97d6-125">Execute the statement `ALTER DATABASE db_name SET MULTI_USER`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97d6-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a97d6-126">See Also</span></span>  
 <span data-ttu-id="a97d6-127">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a97d6-127">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a97d6-128">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="a97d6-128">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
