---
title: Clave maestra de servicio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server]
- service master key [SQL Server], about service master key
ms.assetid: 85f2095d-2590-4f59-8a29-7e100edd02bb
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: baeeffd49ac89ce85cf64932fbfd4982d7243887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752058"
---
# <a name="service-master-key"></a><span data-ttu-id="f7bfe-102">clave maestra de servicio</span><span class="sxs-lookup"><span data-stu-id="f7bfe-102">Service Master Key</span></span>
  <span data-ttu-id="f7bfe-103">La clave maestra de servicio es la raíz de la jerarquía de cifrado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7bfe-103">The Service Master Key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="f7bfe-104">Se genera automáticamente la primera vez que se necesita para cifrar otra clave.</span><span class="sxs-lookup"><span data-stu-id="f7bfe-104">It is generated automatically the first time it is needed to encrypt another key.</span></span> <span data-ttu-id="f7bfe-105">De manera predeterminada, la clave maestra de servicio se cifra mediante la API de protección de datos de Windows y utilizando la clave del equipo local.</span><span class="sxs-lookup"><span data-stu-id="f7bfe-105">By default, the Service Master Key is encrypted using the Windows data protection API and using the local machine key.</span></span> <span data-ttu-id="f7bfe-106">La clave maestra de servicio solo puede abrirla la cuenta de servicio de Windows bajo la que se creó, o una entidad de seguridad con acceso al nombre y a la contraseña de la cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="f7bfe-106">The Service Master Key can only be opened by the Windows service account under which it was created or by a principal with access to both the service account name and its password.</span></span>  
  
 <span data-ttu-id="f7bfe-107">Para regenerar o restaurar la clave maestra de servicio, es necesario descifrar y volver a cifrar toda la jerarquía de cifrado.</span><span class="sxs-lookup"><span data-stu-id="f7bfe-107">Regenerating or restoring the Service Master Key involves decrypting and re-encrypting the complete encryption hierarchy.</span></span> <span data-ttu-id="f7bfe-108">A no ser que se haya vulnerado la seguridad de la clave, esta operación que hace un uso intensivo de los recursos se debe programar durante un período de poca actividad.</span><span class="sxs-lookup"><span data-stu-id="f7bfe-108">Unless the key has been compromised, this resource-intensive operation should be scheduled during a period of low demand.</span></span>  
  
 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] <span data-ttu-id="f7bfe-109">usa el algoritmo de cifrado AES para proteger la clave maestra de servicio (SMK) y la clave maestra de la base de datos (DMK).</span><span class="sxs-lookup"><span data-stu-id="f7bfe-109">uses the AES encryption algorithm to protect the service master key (SMK) and the database master key (DMK).</span></span> <span data-ttu-id="f7bfe-110">AES es un algoritmo de cifrado más reciente que el algoritmo 3DES empleado en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="f7bfe-110">AES is a newer encryption algorithm than 3DES used in earlier versions.</span></span> <span data-ttu-id="f7bfe-111">Después de actualizar una instancia de [!INCLUDE[ssDE](../../../includes/ssde-md.md)] a [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] , se deben volver a generar las claves SMK y DMK para actualizar las claves maestras al algoritmo AES.</span><span class="sxs-lookup"><span data-stu-id="f7bfe-111">After upgrading an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] the SMK and DMK should be regenerated in order to upgrade the master keys to AES.</span></span> <span data-ttu-id="f7bfe-112">Para obtener más información sobre cómo volver a generar la SMK, vea [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) y [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f7bfe-112">For more information about regenerating the SMK, see [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) and [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="f7bfe-113">Procedimiento recomendado</span><span class="sxs-lookup"><span data-stu-id="f7bfe-113">Best Practice</span></span>  
 <span data-ttu-id="f7bfe-114">Cree una copia de seguridad de la clave maestra de servicio y almacene esta copia en una ubicación segura fuera del sitio.</span><span class="sxs-lookup"><span data-stu-id="f7bfe-114">Back up the Service Master Key and store the backed up copy in a secure, off-site location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f7bfe-115">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f7bfe-115">Related Tasks</span></span>  
 [<span data-ttu-id="f7bfe-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bfe-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-service-master-key-transact-sql)  
  
 [<span data-ttu-id="f7bfe-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bfe-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-service-master-key-transact-sql)  
  
 [<span data-ttu-id="f7bfe-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bfe-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-service-master-key-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="f7bfe-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7bfe-119">See Also</span></span>  
 [<span data-ttu-id="f7bfe-120">Jerarquía de cifrado</span><span class="sxs-lookup"><span data-stu-id="f7bfe-120">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
