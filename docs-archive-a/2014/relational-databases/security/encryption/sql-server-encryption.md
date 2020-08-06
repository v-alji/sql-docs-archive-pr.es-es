---
title: Cifrado de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], about encryption
- security [SQL Server], encryption
- cryptography [SQL Server], about cryptography
ms.assetid: ead0150e-4943-4ad5-84c8-36f85c7278f4
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 6fc68e6f3280a8e23d6a1bf4f364aadfffd69f85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752049"
---
# <a name="sql-server-encryption"></a><span data-ttu-id="aef75-102">Cifrado de SQL Server</span><span class="sxs-lookup"><span data-stu-id="aef75-102">SQL Server Encryption</span></span>
  <span data-ttu-id="aef75-103">El cifrado es el proceso consistente en ofuscar los datos mediante el uso de una clave o contraseña.</span><span class="sxs-lookup"><span data-stu-id="aef75-103">Encryption is the process of obfuscating data by the use of a key or password.</span></span> <span data-ttu-id="aef75-104">Esto puede hacer que los datos sean inútiles sin la clave o contraseña de descifrado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="aef75-104">This can make the data useless without the corresponding decryption key or password.</span></span> <span data-ttu-id="aef75-105">El cifrado no resuelve los problemas de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="aef75-105">Encryption does not solve access control problems.</span></span> <span data-ttu-id="aef75-106">Sin embargo, mejora la seguridad debido a que limita la pérdida de datos, incluso si se superan los controles de acceso.</span><span class="sxs-lookup"><span data-stu-id="aef75-106">However, it enhances security by limiting data loss even if access controls are bypassed.</span></span> <span data-ttu-id="aef75-107">Por ejemplo, si el equipo host de base de datos no está configurado correctamente y un usuario malintencionado obtiene datos confidenciales, esa información robada podría resultar inservible si está cifrada.</span><span class="sxs-lookup"><span data-stu-id="aef75-107">For example, if the database host computer is misconfigured and a hacker obtains sensitive data, that stolen information might be useless if it is encrypted.</span></span>  
  
 <span data-ttu-id="aef75-108">Puede utilizar el cifrado en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para las conexiones, los datos y los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="aef75-108">You can use encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for connections, data, and stored procedures.</span></span> <span data-ttu-id="aef75-109">La tabla siguiente contiene más información acerca del cifrado en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aef75-109">The following table contains more information about encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aef75-110">Aunque el cifrado es una valiosa herramienta para ayudar a garantizar la seguridad, no está indicado para todos los datos o conexiones.</span><span class="sxs-lookup"><span data-stu-id="aef75-110">Although encryption is a valuable tool to help ensure security, it should not be considered for all data or connections.</span></span> <span data-ttu-id="aef75-111">Cuando decida si debe implementar el cifrado, debe tener en cuenta el modo en que los usuarios obtendrán acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="aef75-111">When you are deciding whether to implement encryption, consider how users will access data.</span></span> <span data-ttu-id="aef75-112">Si los usuarios tienen acceso a los datos a través de una red pública, podría ser necesario el cifrado de datos para aumentar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="aef75-112">If users access data over a public network, data encryption might be required to increase security.</span></span> <span data-ttu-id="aef75-113">Sin embargo, si todo el acceso se realiza dentro de una configuración de intranet segura, el cifrado podría no ser necesario.</span><span class="sxs-lookup"><span data-stu-id="aef75-113">However, if all access involves a secure intranet configuration, encryption might not be required.</span></span> <span data-ttu-id="aef75-114">Cualquier uso del cifrado también debería incluir una estrategia de mantenimiento para las contraseñas, las claves y los certificados.</span><span class="sxs-lookup"><span data-stu-id="aef75-114">Any use of encryption should also include a maintenance strategy for passwords, keys, and certificates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aef75-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="aef75-115">In This Section</span></span>  
 [<span data-ttu-id="aef75-116">Jerarquía de cifrado</span><span class="sxs-lookup"><span data-stu-id="aef75-116">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
 <span data-ttu-id="aef75-117">Información acerca de la jerarquía de cifrado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aef75-117">Information about the encryption hierarchy in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="aef75-118">Elegir un algoritmo de cifrado</span><span class="sxs-lookup"><span data-stu-id="aef75-118">Choose an Encryption Algorithm</span></span>](choose-an-encryption-algorithm.md)  
 <span data-ttu-id="aef75-119">Información acerca del modo de seleccionar un algoritmo de cifrado efectivo.</span><span class="sxs-lookup"><span data-stu-id="aef75-119">Information about how to select an effective encrypting algorithm.</span></span>  
  
 [<span data-ttu-id="aef75-120">Cifrado de datos transparente &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="aef75-120">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)  
 <span data-ttu-id="aef75-121">Información general sobre cómo cifrar datos de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="aef75-121">General information about how to encrypt data transparently.</span></span>  
  
 [<span data-ttu-id="aef75-122">SQL Server y claves de cifrado de base de datos &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="aef75-122">SQL Server and Database Encryption Keys &#40;Database Engine&#41;</span></span>](sql-server-and-database-encryption-keys-database-engine.md)  
 <span data-ttu-id="aef75-123">En [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], las claves de cifrado incluyen una combinación de claves públicas, privadas y simétricas que se utilizan para proteger la información confidencial.</span><span class="sxs-lookup"><span data-stu-id="aef75-123">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], encryption keys include a combination of public, private, and symmetric keys that are used to protect sensitive data.</span></span> <span data-ttu-id="aef75-124">En esta sección se explica cómo implementar y administrar las claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="aef75-124">This section explains how to implement and manage encryption keys.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="aef75-125">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="aef75-125">Related Content</span></span>  
 [<span data-ttu-id="aef75-126">Proteger SQL Server</span><span class="sxs-lookup"><span data-stu-id="aef75-126">Securing SQL Server</span></span>](../securing-sql-server.md)  
 <span data-ttu-id="aef75-127">Información general sobre el modo de proteger la plataforma [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y cómo trabajar con los usuarios y los objetos protegibles.</span><span class="sxs-lookup"><span data-stu-id="aef75-127">Overview of how to help secure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] platform, and how to work with users and securable objects.</span></span>  
  
 [<span data-ttu-id="aef75-128">Funciones de cifrado &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aef75-128">Cryptographic Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cryptographic-functions-transact-sql)  
 <span data-ttu-id="aef75-129">Información sobre el modo de implementar las funciones criptográficas.</span><span class="sxs-lookup"><span data-stu-id="aef75-129">Information about how to implement cryptographic functions.</span></span>  
  
 [<span data-ttu-id="aef75-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aef75-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbypassphrase-transact-sql)  
 <span data-ttu-id="aef75-131">Información sobre cómo utilizar una contraseña para cifrar datos.</span><span class="sxs-lookup"><span data-stu-id="aef75-131">Information about how to use a password to encrypt data.</span></span>  
  
 [<span data-ttu-id="aef75-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aef75-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
 <span data-ttu-id="aef75-133">Información sobre cómo utilizar una clave simétrica para cifrar datos.</span><span class="sxs-lookup"><span data-stu-id="aef75-133">Information about how to use a symmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="aef75-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aef75-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbyasymkey-transact-sql)  
 <span data-ttu-id="aef75-135">Información sobre cómo utilizar una clave asimétrica para cifrar datos.</span><span class="sxs-lookup"><span data-stu-id="aef75-135">Information about how to use an asymmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="aef75-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aef75-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbycert-transact-sql)  
 <span data-ttu-id="aef75-137">Información sobre cómo utilizar un certificado para cifrar datos.</span><span class="sxs-lookup"><span data-stu-id="aef75-137">Information about how to use a certificate to encrypt data.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="aef75-138">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="aef75-138">External Resources</span></span>  
 [<span data-ttu-id="aef75-139">10 pasos para SQL Server la seguridad 2005</span><span class="sxs-lookup"><span data-stu-id="aef75-139">10 Steps to SQL Server 2005 Security</span></span>](https://www.itprotoday.com/sql-server/10-steps-sql-server-2005-security)  
 <span data-ttu-id="aef75-140">Información actual sobre la seguridad en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aef75-140">Current information about [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef75-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aef75-141">See Also</span></span>  
 <span data-ttu-id="aef75-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aef75-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span></span>  
 <span data-ttu-id="aef75-143">[SQL Server y claves de cifrado de base de datos &#40;motor de base de datos&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="aef75-143">[SQL Server and Database Encryption Keys &#40;Database Engine&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span></span>  
 [<span data-ttu-id="aef75-144">Hacer copia de seguridad y restaurar claves de cifrado de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="aef75-144">Back Up and Restore Reporting Services Encryption Keys</span></span>](../../../reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)  
  
  
