---
title: contained database authentication (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- contained_database_authentication_TSQL
- contained database authentication
helpviewer_keywords:
- contained database, enabling
- contained database authentication option
ms.assetid: b80768d2-ac20-4035-a335-d9adb74b3f6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf5bf07c8b0913ff81f31ff0ca64a18eee0f2ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674317"
---
# <a name="contained-database-authentication-server-configuration-option"></a><span data-ttu-id="1ddfe-102">contained database authentication (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="1ddfe-102">contained database authentication Server Configuration Option</span></span>
  <span data-ttu-id="1ddfe-103">Utilice la opción **autenticación de base de datos independiente** para habilitar las bases de datos independientes en la instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ddfe-103">Use the **contained database authentication** option to enable contained databases on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1ddfe-104">Esta opción de servidor permite controlar la **autenticación de base de datos independiente**.</span><span class="sxs-lookup"><span data-stu-id="1ddfe-104">This server option allows you to control **contained database authentication**.</span></span>  
  
-   <span data-ttu-id="1ddfe-105">Cuando la opción **autenticación de base de datos independiente** está desactivada (0) para la instancia, no se pueden crear bases de datos independientes ni tampoco adjuntarse a [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ddfe-105">When **contained database authentication** is off (0) for the instance, contained databases cannot be created, or attached to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="1ddfe-106">Cuando la opción **autenticación de base de datos independiente** está activada (1) para la instancia, se pueden crear bases de datos independientes y, también, adjuntarse a [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ddfe-106">When **contained database authentication** is on (1) for the instance, contained databases can be created, or attached to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="1ddfe-107">Una base de datos independiente incluye todos los metadatos y la configuración de la base de datos necesarios para definirla, y no tiene dependencias de configuración en la instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] donde esté instalada.</span><span class="sxs-lookup"><span data-stu-id="1ddfe-107">A contained database includes all database settings and metadata required to define the database and has no configuration dependencies on the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] where the database is installed.</span></span> <span data-ttu-id="1ddfe-108">Los usuarios pueden conectarse a la base de datos sin autenticar un inicio de sesión en el nivel [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ddfe-108">Users can connect to the database without authenticating a login at the [!INCLUDE[ssDE](../../includes/ssde-md.md)] level.</span></span> <span data-ttu-id="1ddfe-109">Aislar la base de datos del Motor de base de datos permite moverla fácilmente a otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ddfe-109">Isolating the database from the Database Engine makes it possible to easily move the database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1ddfe-110">Al incluir toda la configuración de la base de datos en la base de datos, se permite que sus propietarios administren toda su configuración.</span><span class="sxs-lookup"><span data-stu-id="1ddfe-110">Including all the database settings in the database enables database owners to manage all the configuration settings for the database.</span></span> <span data-ttu-id="1ddfe-111">Para obtener más información acerca de las bases de datos independientes, vea [Contained Databases](../../relational-databases/databases/contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1ddfe-111">For more information about contained databases, see [Contained Databases](../../relational-databases/databases/contained-databases.md).</span></span>  
  
 <span data-ttu-id="1ddfe-112">Si una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiene bases de datos independientes, la configuración de **autenticación de base de datos independiente** se puede establecer en 0 mediante el uso de la instrucción **RECONFIGURE WITH OVERRIDE** .</span><span class="sxs-lookup"><span data-stu-id="1ddfe-112">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has any contained databases the **contained database authentication** setting can be set to 0 by using the **RECONFIGURE WITH OVERRIDE** statement.</span></span> <span data-ttu-id="1ddfe-113">Al establecer **autenticación de base de datos independiente** en 0 se deshabilitará la autenticación de base de datos independiente para las bases de datos independientes.</span><span class="sxs-lookup"><span data-stu-id="1ddfe-113">Setting **contained database authentication** to 0 will disable contained database authentication for the contained databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1ddfe-114">Cuando se habilitan las bases de datos independientes, los usuarios de la base de datos con el permiso ALTER ANY USER, como los miembros de los roles de base de datos db_owner y db_accessadmin, pueden otorgar acceso a las bases de datos y, al hacerlo, otorgan acceso a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ddfe-114">When contained databases are enabled, database users with the ALTER ANY USER permission, such as members of the db_owner and db_accessadmin database roles, can grant access to databases and by doing so, grant access to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1ddfe-115">Esto significa que el control sobre el acceso al servidor ya no se limita a los miembros con roles fijos de sysadmin y securityadmin, y a los inicios de sesión con el permiso ALTER ANY LOGIN y de servidor de CONTROL de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="1ddfe-115">This means that control over access to the server is no longer limited to members of the sysadmin and securityadmin fixed server role, and logins with the server level CONTROL SERVER and ALTER ANY LOGIN permission.</span></span> <span data-ttu-id="1ddfe-116">Antes de permitir las bases de datos independientes, debe entender los riesgos asociados a ellas.</span><span class="sxs-lookup"><span data-stu-id="1ddfe-116">Before allowing contained databases, you should understand the risks associated with contained databases.</span></span> <span data-ttu-id="1ddfe-117">Para más información, vea [Security Best Practices with Contained Databases](../../relational-databases/databases/security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1ddfe-117">For more information, see [Security Best Practices with Contained Databases](../../relational-databases/databases/security-best-practices-with-contained-databases.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1ddfe-118">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1ddfe-118">Examples</span></span>  
 <span data-ttu-id="1ddfe-119">En el siguiente ejemplo se habilitan las bases de datos independientes en la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ddfe-119">The following example enables contained databases on the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ddfe-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ddfe-120">See Also</span></span>  
 <span data-ttu-id="1ddfe-121">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ddfe-121">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="1ddfe-122">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ddfe-122">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 [<span data-ttu-id="1ddfe-123">Opciones de configuración de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ddfe-123">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
