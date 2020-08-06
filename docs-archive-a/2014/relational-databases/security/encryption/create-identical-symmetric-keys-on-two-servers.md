---
title: Creación de claves simétricas idénticas en dos servidores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- symmetric keys [SQL Server], creating
ms.assetid: a13d0b21-a43b-43c0-9c22-7ba8f3d15e80
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 38eaccffff89b0be7e59f628fcfb9b6e772a02b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750617"
---
# <a name="create-identical-symmetric-keys-on-two-servers"></a><span data-ttu-id="d6867-102">Crear claves simétricas idénticas en dos servidores</span><span class="sxs-lookup"><span data-stu-id="d6867-102">Create Identical Symmetric Keys on Two Servers</span></span>
  <span data-ttu-id="d6867-103">En este tema se describe cómo crear claves simétricas idénticas en dos servidores diferentes de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6867-103">This topic describes how to create identical symmetric keys on two different servers in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d6867-104">Para descifrar el texto cifrado, se necesita la clave que se usó para cifrarlo.</span><span class="sxs-lookup"><span data-stu-id="d6867-104">In order to decrypt ciphertext, you need the key that was used to encrypt it.</span></span> <span data-ttu-id="d6867-105">Cuando el cifrado y el descifrado tienen lugar en una sola base de datos, la clave se almacena en la base de datos y está disponible, según los permisos, tanto para el cifrado como para el descifrado.</span><span class="sxs-lookup"><span data-stu-id="d6867-105">When both encryption and decryption occur in a single database, the key is stored in the database and it is available, depending on permissions, for both encryption and decryption.</span></span> <span data-ttu-id="d6867-106">Pero cuando ambos procesos ocurren en bases de datos diferentes o en servidores diferentes, la clave almacenada en una base de datos no está disponible para utilizarla en la segunda base de datos.</span><span class="sxs-lookup"><span data-stu-id="d6867-106">But when encryption and decryption occur in separate databases or on separate servers, the key stored in one database is not available for use on the second database</span></span>  
  
 <span data-ttu-id="d6867-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d6867-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d6867-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="d6867-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d6867-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="d6867-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d6867-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d6867-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="d6867-111">Para crear claves simétricas idénticas en dos servidores diferentes, mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d6867-111">To create identical symmetric keys on two different servers, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d6867-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d6867-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d6867-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="d6867-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d6867-114">Cuando se crea una clave simétrica, se debe cifrar mediante uno de los siguientes métodos: certificado, contraseña, clave simétrica, clave asimétrica o PROVIDER.</span><span class="sxs-lookup"><span data-stu-id="d6867-114">When a symmetric key is created, the symmetric key must be encrypted by using at least one of the following: certificate, password, symmetric key, asymmetric key, or PROVIDER.</span></span> <span data-ttu-id="d6867-115">La clave puede tener más de un cifrado de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="d6867-115">The key can have more than one encryption of each type.</span></span> <span data-ttu-id="d6867-116">En otras palabras, una misma clave simétrica puede cifrarse con varios certificados, contraseñas, claves simétricas y claves asimétricas a la vez.</span><span class="sxs-lookup"><span data-stu-id="d6867-116">In other words, a single symmetric key can be encrypted by using multiple certificates, passwords, symmetric keys, and asymmetric keys at the same time.</span></span>  
  
-   <span data-ttu-id="d6867-117">Si se utiliza una contraseña para cifrar una clave simétrica, en lugar de la clave pública de la clave maestra de base de datos, se utiliza el algoritmo de cifrado TRIPLE DES.</span><span class="sxs-lookup"><span data-stu-id="d6867-117">When a symmetric key is encrypted with a password instead of the public key of the database master key, the TRIPLE DES encryption algorithm is used.</span></span> <span data-ttu-id="d6867-118">Por ello, las claves creadas con un algoritmo de cifrado seguro, como AES, se protegen mediante un algoritmo menos seguro.</span><span class="sxs-lookup"><span data-stu-id="d6867-118">Because of this, keys that are created with a strong encryption algorithm, such as AES, are themselves secured by a weaker algorithm.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d6867-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d6867-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d6867-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="d6867-120">Permissions</span></span>  
 <span data-ttu-id="d6867-121">Necesita el permiso ALTER ANY SYMMETRIC KEY para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d6867-121">Requires ALTER ANY SYMMETRIC KEY permission on the database.</span></span> <span data-ttu-id="d6867-122">Si se especifica la cláusula AUTHORIZATION, es necesario el permiso IMPERSONATE para el usuario de base de datos o el permiso ALTER para el rol de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6867-122">If AUTHORIZATION is specified, requires IMPERSONATE permission on the database user or ALTER permission on the application role.</span></span> <span data-ttu-id="d6867-123">Si el cifrado se realiza mediante una clave asimétrica o un certificado, es necesario el permiso VIEW DEFINITION para el certificado o en la clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="d6867-123">If encryption is by certificate or asymmetric key, requires VIEW DEFINITION permission on the certificate or asymmetric key.</span></span> <span data-ttu-id="d6867-124">Solo los inicios de sesión de Windows, los inicios de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y los roles de aplicación pueden poseer claves simétricas.</span><span class="sxs-lookup"><span data-stu-id="d6867-124">Only Windows logins, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins, and application roles can own symmetric keys.</span></span> <span data-ttu-id="d6867-125">Los grupos y roles no pueden poseer claves simétricas.</span><span class="sxs-lookup"><span data-stu-id="d6867-125">Groups and roles cannot own symmetric keys.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d6867-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d6867-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-identical-symmetric-keys-on-two-different-servers"></a><span data-ttu-id="d6867-127">Para crear claves simétricas idénticas en dos servidores diferentes</span><span class="sxs-lookup"><span data-stu-id="d6867-127">To create identical symmetric keys on two different servers</span></span>  
  
1.  <span data-ttu-id="d6867-128">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6867-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d6867-129">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d6867-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d6867-130">Cree una clave ejecutando las siguientes instrucciones, CREATE MASTER KEY, CREATE CERTIFICATE y CREATE SYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="d6867-130">Create a key by running the following CREATE MASTER KEY, CREATE CERTIFICATE, and CREATE SYMMETRIC KEY statements.</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'My p@55w0Rd';  
    GO  
    CREATE CERTIFICATE [cert_keyProtection] WITH SUBJECT = 'Key Protection';  
    GO  
    CREATE SYMMETRIC KEY [key_DataShare] WITH  
        KEY_SOURCE = 'My key generation bits. This is a shared secret!',  
        ALGORITHM = AES_256,   
        IDENTITY_VALUE = 'Key Identity generation bits. Also a shared secret'  
        ENCRYPTION BY CERTIFICATE [cert_keyProtection];  
    GO  
    ```  
  
4.  <span data-ttu-id="d6867-131">Conéctese a una instancia de servidor independiente, abra otra ventana de consulta y ejecute las instrucciones SQL anteriores para crear la misma clave en el segundo servidor.</span><span class="sxs-lookup"><span data-stu-id="d6867-131">Connect to a separate server instance, open a different Query Window, and run the SQL statements above to create the same key on the second server.</span></span>  
  
5.  <span data-ttu-id="d6867-132">Pruebe las claves ejecutando primero la instrucción OPEN SYMMETRIC KEY y la instrucción SELECT después en el primer servidor.</span><span class="sxs-lookup"><span data-stu-id="d6867-132">Test the keys by first running the OPEN SYMMETRIC KEY statement and the SELECT statement below on the first server.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    SELECT encryptbykey(key_guid('key_DataShare'), 'MyData' )  
    GO  
    -- For example, the output might look like this: 0x2152F8DA8A500A9EDC2FAE26D15C302DA70D25563DAE7D5D1102E3056CE9EF95CA3E7289F7F4D0523ED0376B155FE9C3  
    ```  
  
6.  <span data-ttu-id="d6867-133">En el segundo servidor, pegue el resultado de la instrucción SELECT previa en el siguiente código como el valor de `@blob` y ejecute el siguiente código para comprobar que la clave duplicada pueda descifrar el texto cifrado.</span><span class="sxs-lookup"><span data-stu-id="d6867-133">On the second server, paste the result of the previous SELECT statement into the following code as the value of `@blob` and run the following code to verify that the duplicate key can decrypt the ciphertext.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    DECLARE @blob varbinary(8000);  
    SET @blob = SELECT CONVERT(varchar(8000), decryptbykey(@blob));  
    GO  
    ```  
  
7.  <span data-ttu-id="d6867-134">Cierre la clave simétrica en ambos servidores.</span><span class="sxs-lookup"><span data-stu-id="d6867-134">Close the symmetric key on both servers.</span></span>  
  
    ```  
    CLOSE SYMMETRIC KEY [key_DataShare];  
    GO  
    ```  
  
 <span data-ttu-id="d6867-135">Para obtener más información, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6867-135">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="d6867-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6867-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="d6867-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6867-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="d6867-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6867-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)  
  
-   [<span data-ttu-id="d6867-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6867-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
  
-   [<span data-ttu-id="d6867-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6867-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/decryptbykey-transact-sql)  
  
-   [<span data-ttu-id="d6867-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6867-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/open-symmetric-key-transact-sql)  
  
  
