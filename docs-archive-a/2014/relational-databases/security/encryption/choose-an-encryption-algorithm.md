---
title: Selección de un algoritmo de cifrado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], algorithms
- encryption [SQL Server], algorithms
- security [SQL Server], encryption
- algorithms [SQL Server encryption]
ms.assetid: 8227028c-a9c9-489d-bd27-fbf8242634ae
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b2c5292b4a00a3ad81e53fdbc603bb584130613
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750621"
---
# <a name="choose-an-encryption-algorithm"></a><span data-ttu-id="184d7-102">Elegir un algoritmo de cifrado</span><span class="sxs-lookup"><span data-stu-id="184d7-102">Choose an Encryption Algorithm</span></span>
  <span data-ttu-id="184d7-103">El cifrado es una de las medidas defensivas con que cuenta cualquier administrador que desee proteger una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="184d7-103">Encryption is one of several defenses-in-depth that are available to the administrator who wants to secure an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="184d7-104">Los algoritmos de cifrado definen las transformaciones de datos que los usuarios no autorizados no pueden revertir fácilmente.</span><span class="sxs-lookup"><span data-stu-id="184d7-104">Encryption algorithms define data transformations that cannot be easily reversed by unauthorized users.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="184d7-105">permite a los administradores y los desarrolladores de software elegir entre varios algoritmos, incluidos DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, RC4 de 128 bits, DESX, AES de 128 bits, AES de 192 bits y AES de 256 bits.</span><span class="sxs-lookup"><span data-stu-id="184d7-105">allows administrators and developers to choose from among several algorithms, including DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, 128-bit RC4, DESX, 128-bit AES, 192-bit AES, and 256-bit AES.</span></span>  
  
 <span data-ttu-id="184d7-106">Ningún algoritmo único resulta idóneo para todas las situaciones. Además, ofrecer información detallada sobre las ventajas de cada uno queda fuera del ámbito de los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="184d7-106">No single algorithm is ideal for all situations, and guidance on the merits of each is beyond the scope of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="184d7-107">No obstante, se aplican los siguientes principios generales:</span><span class="sxs-lookup"><span data-stu-id="184d7-107">However, the following general principles apply:</span></span>  
  
-   <span data-ttu-id="184d7-108">El cifrado seguro suele consumir más recursos de la CPU que un cifrado menos seguro.</span><span class="sxs-lookup"><span data-stu-id="184d7-108">Strong encryption generally consumes more CPU resources than weak encryption.</span></span>  
  
-   <span data-ttu-id="184d7-109">Las claves largas suelen producir un cifrado más seguro que las claves cortas.</span><span class="sxs-lookup"><span data-stu-id="184d7-109">Long keys generally yield stronger encryption than short keys.</span></span>  
  
-   <span data-ttu-id="184d7-110">El cifrado asimétrico es menos seguro que el simétrico con la misma longitud de clave, pero es relativamente lento.</span><span class="sxs-lookup"><span data-stu-id="184d7-110">Asymmetric encryption is weaker than symmetric encryption using the same key length, but it is relatively slow.</span></span>  
  
-   <span data-ttu-id="184d7-111">Los cifrados en bloque con claves largas son más seguros que los cifrados de flujo.</span><span class="sxs-lookup"><span data-stu-id="184d7-111">Block ciphers with long keys are stronger than stream ciphers.</span></span>  
  
-   <span data-ttu-id="184d7-112">Las contraseñas largas y complejas son más seguras que las contraseñas cortas.</span><span class="sxs-lookup"><span data-stu-id="184d7-112">Long, complex passwords are stronger than short passwords.</span></span>  
  
-   <span data-ttu-id="184d7-113">Si cifra una gran cantidad de datos, debe cifrar los datos con una clave simétrica y cifrar la clave simétrica con una clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="184d7-113">If you are encrypting lots of data, you should encrypt the data using a symmetric key, and encrypt the symmetric key with an asymmetric key.</span></span>  
  
-   <span data-ttu-id="184d7-114">Los datos cifrados no se pueden comprimir, pero los datos comprimidos se pueden cifrar.</span><span class="sxs-lookup"><span data-stu-id="184d7-114">Encrypted data cannot be compressed, but compressed data can be encrypted.</span></span> <span data-ttu-id="184d7-115">Si usa compresión, debe comprimir los datos antes de cifrarlos.</span><span class="sxs-lookup"><span data-stu-id="184d7-115">If you use compression, you should compress data before encrypting it.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="184d7-116">El algoritmo RC4 se admite únicamente por razones de compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="184d7-116">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="184d7-117">El material nuevo solo se puede cifrar con RC4 o RC4_128 cuando la base de datos tenga el nivel de compatibilidad 90 o 100.</span><span class="sxs-lookup"><span data-stu-id="184d7-117">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="184d7-118">(No se recomienda). Use un algoritmo más reciente como uno de los algoritmos AES en su lugar.</span><span class="sxs-lookup"><span data-stu-id="184d7-118">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="184d7-119">En [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] y versiones posteriores, el material cifrado con RC4 o RC4_128 se puede descifrar en cualquier nivel de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="184d7-119">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] and higher material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
>   
>  <span data-ttu-id="184d7-120">El uso repetido de la misma RC4 o RC4_128 KEY_GUID en bloques diferentes de datos producirá la misma clave RC4 porque [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no proporciona un valor de salt automáticamente.</span><span class="sxs-lookup"><span data-stu-id="184d7-120">Repeated use of the same RC4 or RC4_128 KEY_GUID on different blocks of data will result in the same RC4 key because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not provide a salt automatically.</span></span> <span data-ttu-id="184d7-121">El uso repetido de la misma clave RC4 es un error conocido que producirá un cifrado muy poco seguro.</span><span class="sxs-lookup"><span data-stu-id="184d7-121">Using the same RC4 key repeatedly is a well-known error that will result in very weak encryption.</span></span> <span data-ttu-id="184d7-122">Por consiguiente, hemos dejado de utilizar las palabras clave RC4_128 y RC4.</span><span class="sxs-lookup"><span data-stu-id="184d7-122">Therefore, we have deprecated the RC4 and RC4_128 keywords.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="184d7-123">Para obtener más información acerca de los algoritmos y la tecnología de cifrado, vea la sección referente a [conceptos claves de seguridad](https://go.microsoft.com/fwlink/?LinkId=62082) de la publicación .NET Framework Developer's Guide en MSDN.</span><span class="sxs-lookup"><span data-stu-id="184d7-123">For more information about encryption algorithms and encryption technology, see [Key Security Concepts](https://go.microsoft.com/fwlink/?LinkId=62082) in the .NET Framework Developer's Guide on MSDN.</span></span>  
  
 <span data-ttu-id="184d7-124">**Clarificación con respecto a los algoritmos DES:**</span><span class="sxs-lookup"><span data-stu-id="184d7-124">**Clarification regarding DES algorithms:**</span></span>  
  
-   <span data-ttu-id="184d7-125">DESX se denominó incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="184d7-125">DESX was incorrectly named.</span></span> <span data-ttu-id="184d7-126">Las claves simétricas creadas con ALGORITHM = DESX realmente utilizan el cifrado TRIPLE DES con una clave de 192 bits.</span><span class="sxs-lookup"><span data-stu-id="184d7-126">Symmetric keys created with ALGORITHM = DESX actually use the TRIPLE DES cipher with a 192-bit key.</span></span> <span data-ttu-id="184d7-127">No se proporciona el algoritmo DESX.</span><span class="sxs-lookup"><span data-stu-id="184d7-127">The DESX algorithm is not provided.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
-   <span data-ttu-id="184d7-128">Las claves simétricas creadas con ALGORITHM = TRIPLE_DES_3KEY utilizan TRIPLE DES con una clave de 192 bits.</span><span class="sxs-lookup"><span data-stu-id="184d7-128">Symmetric keys created with ALGORITHM = TRIPLE_DES_3KEY use TRIPLE DES with a 192-bit key.</span></span>  
  
-   <span data-ttu-id="184d7-129">Las claves simétricas creadas con ALGORITHM = TRIPLE_DES utilizan TRIPLE DES con una clave de 128 bits.</span><span class="sxs-lookup"><span data-stu-id="184d7-129">Symmetric keys created with ALGORITHM = TRIPLE_DES use TRIPLE DES with a 128-bit key.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="184d7-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="184d7-130">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="184d7-131">Cifrar mediante una clave simétrica.</span><span class="sxs-lookup"><span data-stu-id="184d7-131">Encrypting using a symmetric key.</span></span>|[<span data-ttu-id="184d7-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="184d7-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)|  
|<span data-ttu-id="184d7-133">Cifrar mediante una clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="184d7-133">Encrypting using an asymmetric key.</span></span>|[<span data-ttu-id="184d7-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="184d7-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)|  
|<span data-ttu-id="184d7-135">Cifrar mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="184d7-135">Encrypting using a certificate.</span></span>|[<span data-ttu-id="184d7-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="184d7-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)|  
|<span data-ttu-id="184d7-137">Cifrar los archivos de base de datos mediante el cifrado de datos transparente.</span><span class="sxs-lookup"><span data-stu-id="184d7-137">Encrypting database files using transparent data encryption.</span></span>|[<span data-ttu-id="184d7-138">Cifrado de datos transparente &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="184d7-138">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)|  
|<span data-ttu-id="184d7-139">Cómo cifrar una columna de una tabla.</span><span class="sxs-lookup"><span data-stu-id="184d7-139">How to encrypt one column of a table.</span></span>|[<span data-ttu-id="184d7-140">Cifrar una columna de datos</span><span class="sxs-lookup"><span data-stu-id="184d7-140">Encrypt a Column of Data</span></span>](encrypt-a-column-of-data.md)|  
  
## <a name="see-also"></a><span data-ttu-id="184d7-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="184d7-141">See Also</span></span>  
 <span data-ttu-id="184d7-142">[Cifrado de SQL Server](sql-server-encryption.md) </span><span class="sxs-lookup"><span data-stu-id="184d7-142">[SQL Server Encryption](sql-server-encryption.md) </span></span>  
 [<span data-ttu-id="184d7-143">Jerarquía de cifrado</span><span class="sxs-lookup"><span data-stu-id="184d7-143">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
