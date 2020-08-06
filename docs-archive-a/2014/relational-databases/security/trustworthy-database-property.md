---
title: Propiedad de base de datos TRUSTWORTHY | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database property
ms.assetid: 64b2a53d-4416-4a19-acc0-664a61b45348
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23391fe48037d4cd7f69aef7df6649949301a0f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745106"
---
# <a name="trustworthy-database-property"></a><span data-ttu-id="bed33-102">Propiedad de base de datos TRUSTWORTHY</span><span class="sxs-lookup"><span data-stu-id="bed33-102">TRUSTWORTHY Database Property</span></span>
  <span data-ttu-id="bed33-103">La propiedad de base de datos TRUSTWORTHY sirve para indicar si la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] confía en la base de datos y en su contenido.</span><span class="sxs-lookup"><span data-stu-id="bed33-103">The TRUSTWORTHY database property is used to indicate whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trusts the database and the contents within it.</span></span> <span data-ttu-id="bed33-104">De forma predeterminada, se establece en OFF, pero puede establecerse en ON mediante la instrucción ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="bed33-104">By default, this setting is OFF, but can be set to ON by using the ALTER DATABASE statement.</span></span> <span data-ttu-id="bed33-105">Por ejemplo, `ALTER DATABASE AdventureWorks2012 SET TRUSTWORTHY ON;`.</span><span class="sxs-lookup"><span data-stu-id="bed33-105">For example, `ALTER DATABASE AdventureWorks2012 SET TRUSTWORTHY ON;`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bed33-106">Para establecer esta opción, debe ser miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="bed33-106">To set this option, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="bed33-107">Esta propiedad se puede utilizar para reducir determinadas amenazas que existan como resultado de adjuntar una base de datos que contenga uno de los objetos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bed33-107">This property can be used to reduce certain threats that can exist as a result of attaching a database that contains one of the following objects:</span></span>  
  
-   <span data-ttu-id="bed33-108">Ensamblados malintencionados con permisos establecidos en EXTERNAL_ACCESS o UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="bed33-108">Malicious assemblies with an EXTERNAL_ACCESS or UNSAFE permission setting.</span></span> <span data-ttu-id="bed33-109">Para más información, consulte [CLR Integration Security](../clr-integration/security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="bed33-109">For more information, see [CLR Integration Security](../clr-integration/security/clr-integration-security.md).</span></span>  
  
-   <span data-ttu-id="bed33-110">Módulos malintencionados que se definen para ejecutarse como si se tratase de usuarios con un alto nivel de privilegios.</span><span class="sxs-lookup"><span data-stu-id="bed33-110">Malicious modules that are defined to execute as high privileged users.</span></span> <span data-ttu-id="bed33-111">Para obtener más información, vea [EXECUTE AS &#40;cláusula de Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bed33-111">For more information, see [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="bed33-112">Ambas situaciones requieren un nivel específico de privilegios y están protegidas mediante mecanismos apropiados cuando se utilizan en el contexto de una base de datos que ya está adjunta a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bed33-112">Both of these situations require a specific degree of privileges and are protected against by appropriate mechanisms when they are used in the context of a database that is already attached to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bed33-113">Sin embargo, si se deja la base de datos sin conexión, un usuario que tenga acceso al archivo de la base de datos podría adjuntarlo a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que desee y agregar contenido malintencionado a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bed33-113">However, if the database is taken offline, a user that has access to the database file can potentially attach it to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] of his or her choice and add malicious content to the database.</span></span> <span data-ttu-id="bed33-114">Cuando se separan y adjuntan bases de datos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se establecen ciertos permisos en los archivos de datos y de registro que restringen el acceso a los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="bed33-114">When databases are detached and attached in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], certain permissions are set on the data and log files that restrict access to the database files.</span></span>  
  
 <span data-ttu-id="bed33-115">Puesto que no se puede confiar inmediatamente en una base de datos que se adjunta a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no se permite a la base de datos el acceso a recursos situados fuera del ámbito de la misma hasta que se marque explícitamente como de confianza.</span><span class="sxs-lookup"><span data-stu-id="bed33-115">Because a database that is attached to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be immediately trusted, the database is not allowed to access resources beyond the scope of the database until the database is explicitly marked trustworthy.</span></span> <span data-ttu-id="bed33-116">Además, los módulos que se han diseñado para tener acceso a recursos situados fuera de la base de datos, y los ensamblados con permisos EXTERNAL_ACCESS y UNSAFE, tienen requisitos adicionales para ejecutarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="bed33-116">Also, modules that are designed to access resources outside the database, and assemblies with either the EXTERNAL_ACCESS and UNSAFE permission setting, have additional requirements in order to run successfully.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="bed33-117">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="bed33-117">Related Content</span></span>  
 [<span data-ttu-id="bed33-118">Centro de seguridad para el Motor de base de datos de SQL Server y Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="bed33-118">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="bed33-119">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bed33-119">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
