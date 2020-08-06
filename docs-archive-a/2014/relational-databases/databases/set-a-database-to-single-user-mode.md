---
title: Establecer una base de datos en modo de usuario único | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- single-user mode [SQL Server], database option
ms.assetid: fb5254eb-b635-4b39-8361-136fd36f2b1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 16281b5fa7d4f6698bb6c498915bfa84779b3e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744125"
---
# <a name="set-a-database-to-single-user-mode"></a><span data-ttu-id="fee8e-102">Establecer una base de datos en modo de usuario único</span><span class="sxs-lookup"><span data-stu-id="fee8e-102">Set a Database to Single-user Mode</span></span>
  <span data-ttu-id="fee8e-103">En este tema se describe cómo establecer una base de datos definida por el usuario en modo de usuario único en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fee8e-103">This topic describes how to set a user-defined database to single-user mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fee8e-104">El modo de usuario único se suele utilizar para operaciones de mantenimiento y especifica que solo un usuario puede tener acceso a la base de datos cada vez.</span><span class="sxs-lookup"><span data-stu-id="fee8e-104">Single-user mode specifies that only one user at a time can access the database and is generally used for maintenance actions.</span></span>  
  
 <span data-ttu-id="fee8e-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="fee8e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fee8e-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="fee8e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fee8e-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fee8e-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fee8e-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fee8e-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="fee8e-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fee8e-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fee8e-110">**Para establecer una base de datos en modo de usuario único, use:**</span><span class="sxs-lookup"><span data-stu-id="fee8e-110">**To set a database to single-user mode, using:**</span></span>  
  
     [<span data-ttu-id="fee8e-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fee8e-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fee8e-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fee8e-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fee8e-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fee8e-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fee8e-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fee8e-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fee8e-115">Si hay otros usuarios conectados a la base de datos en el momento de establecer la base de datos en modo de usuario único, sus conexiones a la base de datos se cerrarán sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="fee8e-115">If other users are connected to the database at the time that you set the database to single-user mode, their connections to the database will be closed without warning.</span></span>  
  
-   <span data-ttu-id="fee8e-116">La base de datos permanece en modo de usuario único incluso si el usuario que estableció la opción cierra la sesión.</span><span class="sxs-lookup"><span data-stu-id="fee8e-116">The database remains in single-user mode even if the user that set the option logs off.</span></span> <span data-ttu-id="fee8e-117">A partir de ese momento, un usuario distinto, pero solo uno, puede conectarse a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fee8e-117">At that point, a different user, but only one, can connect to the database.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="fee8e-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fee8e-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="fee8e-119">Antes de establecer la base de datos como SINGLE_USER, compruebe que la opción AUTO_UPDATE_STATISTICS_ASYNC está establecida en OFF.</span><span class="sxs-lookup"><span data-stu-id="fee8e-119">Before you set the database to SINGLE_USER, verify that the AUTO_UPDATE_STATISTICS_ASYNC option is set to OFF.</span></span> <span data-ttu-id="fee8e-120">Cuando esta opción se establece en ON, el subproceso en segundo plano que se usa para actualizar las estadísticas realiza una conexión con la base de datos y no se podrá tener acceso a la base de datos en modo de usuario único.</span><span class="sxs-lookup"><span data-stu-id="fee8e-120">When this option is set to ON, the background thread that is used to update statistics takes a connection against the database, and you will be unable to access the database in single-user mode.</span></span> <span data-ttu-id="fee8e-121">Para obtener más información, vea [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="fee8e-121">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fee8e-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fee8e-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fee8e-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="fee8e-123">Permissions</span></span>  
 <span data-ttu-id="fee8e-124">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fee8e-124">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fee8e-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fee8e-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="fee8e-126">Para establecer una base de datos en modo de usuario único</span><span class="sxs-lookup"><span data-stu-id="fee8e-126">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="fee8e-127">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="fee8e-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fee8e-128">Haga clic con el botón derecho en la base de datos que quiera cambiar y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fee8e-128">Right-click the database to change, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="fee8e-129">En el cuadro de diálogo **Propiedades de la base de datos** , haga clic en la página **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="fee8e-129">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="fee8e-130">En la opción **Restringir acceso** , seleccione el modo único ( **Single**).</span><span class="sxs-lookup"><span data-stu-id="fee8e-130">From the **Restrict Access** option, select **Single**.</span></span>  
  
5.  <span data-ttu-id="fee8e-131">Si hay otros usuarios conectados a la base de datos, aparecerá un mensaje **Conexiones abiertas** .</span><span class="sxs-lookup"><span data-stu-id="fee8e-131">If other users are connected to the database, an **Open Connections** message will appear.</span></span> <span data-ttu-id="fee8e-132">Para cambiar la propiedad y cerrar el resto de conexiones, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fee8e-132">To change the property and close all other connections, click **Yes**.</span></span>  
  
 <span data-ttu-id="fee8e-133">También puede utilizar este procedimiento para establecer la base de datos en modo de acceso múltiple (Multiple) o restringido (Restricted).</span><span class="sxs-lookup"><span data-stu-id="fee8e-133">You can also set the database to Multiple or Restricted access by using this procedure.</span></span> <span data-ttu-id="fee8e-134">Para obtener más información sobre las opciones de Restringir acceso, vea [Propiedades de la base de datos &#40;página Opciones&#41;](database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="fee8e-134">For more information about the Restrict Access options, see [Database Properties &#40;Options Page&#41;](database-properties-options-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fee8e-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fee8e-135">Using Transact-SQL</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="fee8e-136">Para establecer una base de datos en modo de usuario único</span><span class="sxs-lookup"><span data-stu-id="fee8e-136">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="fee8e-137">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fee8e-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fee8e-138">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="fee8e-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fee8e-139">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="fee8e-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="fee8e-140">En este ejemplo la base de datos se establece en el modo `SINGLE_USER` para obtener acceso exclusivo.</span><span class="sxs-lookup"><span data-stu-id="fee8e-140">This example sets the database to `SINGLE_USER` mode to obtain exclusive access.</span></span> <span data-ttu-id="fee8e-141">A continuación, el ejemplo establece el estado de la base de datos [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] en `READ_ONLY` y devuelve el acceso a la base de datos para todos los usuarios. La opción de terminación `WITH ROLLBACK IMMEDIATE` se especifica en la primera instrucción `ALTER DATABASE` .</span><span class="sxs-lookup"><span data-stu-id="fee8e-141">The example then sets the state of the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to `READ_ONLY` and returns access to the database to all users.The termination option `WITH ROLLBACK IMMEDIATE` is specified in the first `ALTER DATABASE` statement.</span></span> <span data-ttu-id="fee8e-142">Esto hará que todas las transacciones incompletas se reviertan y que el resto de las conexiones a la base de datos [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] se desconecten de inmediato.</span><span class="sxs-lookup"><span data-stu-id="fee8e-142">This will cause all incomplete transactions to be rolled back and any other connections to the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to be immediately disconnected.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase8](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase8)]  
  
## <a name="see-also"></a><span data-ttu-id="fee8e-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fee8e-143">See Also</span></span>  
 [<span data-ttu-id="fee8e-144">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fee8e-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
