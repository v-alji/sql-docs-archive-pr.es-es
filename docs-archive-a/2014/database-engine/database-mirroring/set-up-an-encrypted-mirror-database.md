---
title: Establecer una base de datos reflejada cifrada| Microsoft Docs
ms.custom: ''
ms.date: 06/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], database mirroring
- encryption [SQL Server], database mirroring
- database master key [SQL Server], database mirroring
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 7329a575-be29-46e0-abc6-1344db37920c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a5148411792f1ea881bba59e599252284575bbdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746481"
---
# <a name="set-up-an-encrypted-mirror-database"></a><span data-ttu-id="fa794-102">Establecer una base de datos reflejada cifrada</span><span class="sxs-lookup"><span data-stu-id="fa794-102">Set Up an Encrypted Mirror Database</span></span>

<span data-ttu-id="fa794-103">Para habilitar el descifrado automático de la clave maestra de base de datos de una base de datos reflejada, debe proporcionar la contraseña que usó para cifrar la clave maestra a la instancia del servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="fa794-103">To enable automatic decryption of the database master key of a mirror database, you must provide the password used to encrypt the master key to the mirror server instance.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="fa794-104">y las versiones posteriores incluyen mecanismos para transferir la contraseña.</span><span class="sxs-lookup"><span data-stu-id="fa794-104">and later versions include mechanisms to transfer the password.</span></span> <span data-ttu-id="fa794-105">Use **sp_control_dbmasterkey_password** para crear una credencial para la clave maestra de base de datos antes de iniciar la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fa794-105">Use **sp_control_dbmasterkey_password** to create a credential for the database master key before you start database mirroring.</span></span> <span data-ttu-id="fa794-106">Debe repetir este proceso para cada base de datos que se vaya a reflejar.</span><span class="sxs-lookup"><span data-stu-id="fa794-106">You must repeat this process for every database that will be mirrored.</span></span> <span data-ttu-id="fa794-107">Para obtener más información, vea [sp_control_dbmasterkey_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fa794-107">For more information, see [sp_control_dbmasterkey_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql).</span></span>
  
> [!CAUTION]  
>  <span data-ttu-id="fa794-108">No habilite el descifrado por error de una base de datos que debe permanecer inaccesible a **sa** y a otras entidades de seguridad de servidor con amplios privilegios.</span><span class="sxs-lookup"><span data-stu-id="fa794-108">Do not enable failover decryption of a database that must remain inaccessible to **sa** and other highly privileged server principals.</span></span> <span data-ttu-id="fa794-109">Puede configurar una base de datos de forma que su jerarquía de claves no pueda descifrarse con la clave maestra de servicio.</span><span class="sxs-lookup"><span data-stu-id="fa794-109">You can configure a database so that its key hierarchy cannot be decrypted by the service master key.</span></span> <span data-ttu-id="fa794-110">Esta opción se admite como una defensa a fondo para bases de datos que contienen información que no debe estar accesible para **sa** u otras entidades de seguridad de servidor con muchos privilegios.</span><span class="sxs-lookup"><span data-stu-id="fa794-110">This option is supported as a defense-in-depth for databases that contain information that should not be accessible to **sa** or other highly privileged server principals.</span></span> <span data-ttu-id="fa794-111">Si habilita el descifrado de conmutación por error de este tipo de bases de datos eliminará la defensa a fondo, permitiendo así que **sa** y otras entidades de seguridad de servidor con muchos privilegios descifren la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fa794-111">Enabling failover decryption of such a database removes this defense-in-depth, enabling **sa** and other highly privileged server principals to decrypt the database.</span></span>  


<!-- Note: We cannot append '?view=sql-server-2016' to these, even tho in theory we might want to. -->

## <a name="see-also"></a><span data-ttu-id="fa794-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa794-112">See Also</span></span>

[<span data-ttu-id="fa794-113">sp_control_dbmasterkey_password &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fa794-113">sp_control_dbmasterkey_password &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql)

[<span data-ttu-id="fa794-114">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fa794-114">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)

[<span data-ttu-id="fa794-115">ALTER MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fa794-115">ALTER MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-master-key-transact-sql)

[<span data-ttu-id="fa794-116">Jerarquía de cifrado</span><span class="sxs-lookup"><span data-stu-id="fa794-116">Encryption Hierarchy</span></span>](../../relational-databases/security/encryption/encryption-hierarchy.md)

[<span data-ttu-id="fa794-117">Configurar la creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa794-117">Setting Up Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)

