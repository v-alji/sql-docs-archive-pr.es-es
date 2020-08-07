---
title: Replicación de datos en columnas cifradas (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], replicating data
- encryption [SQL Server replication]
- publishing [SQL Server replication], encrypted columns
ms.assetid: d1f8f586-e5a3-4a71-9391-11198d42bfa3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e1528d81faa352fdcdf37abe9ad93fda190445c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746241"
---
# <a name="replicate-data-in-encrypted-columns-sql-server-management-studio"></a><span data-ttu-id="33acd-102">Replicar datos en columnas cifradas (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="33acd-102">Replicate Data in Encrypted Columns (SQL Server Management Studio)</span></span>
  <span data-ttu-id="33acd-103">La replicación le permite publicar datos de columna cifrados.</span><span class="sxs-lookup"><span data-stu-id="33acd-103">Replication enables you to publish encrypted column data.</span></span> <span data-ttu-id="33acd-104">Para descifrar y usar estos datos en el suscriptor, la clave usada para cifrar los datos en el publicador también debe estar presente en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="33acd-104">To decrypt and use this data at the Subscriber, the key that was used to encrypt the data at the Publisher must also be present on the Subscriber.</span></span> <span data-ttu-id="33acd-105">La replicación no ofrece un mecanismo de seguridad para transportar las claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="33acd-105">Replication does not provide a secure mechanism to transport encryption keys.</span></span> <span data-ttu-id="33acd-106">Debe volver a crear manualmente la clave de cifrado en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="33acd-106">You must manually re-create the encryption key at the Subscriber.</span></span> <span data-ttu-id="33acd-107">En este tema se muestra cómo cifrar una columna en el publicador y asegurarse de que la clave de cifrado esté disponible en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="33acd-107">This topic shows you how to encrypt a column at the Publisher and make sure that the encryption key is available at the Subscriber.</span></span>  
  
 <span data-ttu-id="33acd-108">Los pasos básicos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="33acd-108">The basic steps are as follows:</span></span>  
  
1.  <span data-ttu-id="33acd-109">Cree la clave simétrica en el publicador.</span><span class="sxs-lookup"><span data-stu-id="33acd-109">Create the symmetric key at the Publisher.</span></span>  
  
2.  <span data-ttu-id="33acd-110">Cifre los datos de la columna con la clave simétrica.</span><span class="sxs-lookup"><span data-stu-id="33acd-110">Encrypt column data with the symmetric key.</span></span>  
  
3.  <span data-ttu-id="33acd-111">Publique la tabla con la columna cifrada.</span><span class="sxs-lookup"><span data-stu-id="33acd-111">Publish the table with the encrypted column.</span></span>  
  
4.  <span data-ttu-id="33acd-112">Suscríbase a la publicación.</span><span class="sxs-lookup"><span data-stu-id="33acd-112">Subscribe to the publication.</span></span>  
  
5.  <span data-ttu-id="33acd-113">Inicialice la suscripción.</span><span class="sxs-lookup"><span data-stu-id="33acd-113">Initialize the subscription.</span></span>  
  
6.  <span data-ttu-id="33acd-114">Vuelva a crear la clave simétrica en el suscriptor con los mismos valores para ALGORITHM, KEY_SOURCE e IDENTITY_VALUE que en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="33acd-114">Recreate the symmetric key at the Subscriber using same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span>  
  
7.  <span data-ttu-id="33acd-115">Obtenga acceso a los datos de columna cifrados.</span><span class="sxs-lookup"><span data-stu-id="33acd-115">Access the encrypted column data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33acd-116">Debe usar una clave simétrica para cifrar los datos de columna.</span><span class="sxs-lookup"><span data-stu-id="33acd-116">You should use a symmetric key to encrypt column data.</span></span> <span data-ttu-id="33acd-117">La propia clave simétrica puede protegerse mediante distintos métodos en el publicador y el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="33acd-117">The symmetric key itself can be secured by different means at the Publisher and Subscriber.</span></span>  
  
### <a name="to-create-and-replicate-encrypted-column-data"></a><span data-ttu-id="33acd-118">Para crear y replicar los datos de columna cifrados</span><span class="sxs-lookup"><span data-stu-id="33acd-118">To create and replicate encrypted column data</span></span>  
  
1.  <span data-ttu-id="33acd-119">En el publicador, ejecute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="33acd-119">At the Publisher, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="33acd-120">El valor de KEY_SOURCE son datos importantes que pueden utilizarse para volver a crear la clave simétrica y descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="33acd-120">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="33acd-121">KEY_SOURCE siempre debe almacenarse y transportarse de forma segura.</span><span class="sxs-lookup"><span data-stu-id="33acd-121">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
2.  <span data-ttu-id="33acd-122">Ejecute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) para abrir la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="33acd-122">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
3.  <span data-ttu-id="33acd-123">Use la función [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) para cifrar los datos de columna en el publicador.</span><span class="sxs-lookup"><span data-stu-id="33acd-123">Use the [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) function to encrypt column data at the Publisher.</span></span>  
  
4.  <span data-ttu-id="33acd-124">Ejecute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) para cerrar la clave.</span><span class="sxs-lookup"><span data-stu-id="33acd-124">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
5.  <span data-ttu-id="33acd-125">Publique la tabla que contiene la columna cifrada.</span><span class="sxs-lookup"><span data-stu-id="33acd-125">Publish the table that contains the encrypted column.</span></span> <span data-ttu-id="33acd-126">Para obtener más información, vea [Crear una suscripción](../publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="33acd-126">For more information, see [Create a Publication](../publish/create-a-publication.md).</span></span>  
  
6.  <span data-ttu-id="33acd-127">Suscríbase a la publicación.</span><span class="sxs-lookup"><span data-stu-id="33acd-127">Subscribe to the publication.</span></span> <span data-ttu-id="33acd-128">Para obtener más información, vea [Crear una suscripción de extracción](../create-a-pull-subscription.md) o [Crear una suscripción de inserción](../create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="33acd-128">For more information, see [Create a Pull Subscription](../create-a-pull-subscription.md) or [Create a Push Subscription](../create-a-push-subscription.md).</span></span>  
  
7.  <span data-ttu-id="33acd-129">Inicialice la suscripción.</span><span class="sxs-lookup"><span data-stu-id="33acd-129">Initialize the subscription.</span></span> <span data-ttu-id="33acd-130">Para más información, consulte [Crear y aplicar la instantánea inicial](../create-and-apply-the-initial-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="33acd-130">For more information, see [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).</span></span>  
  
8.  <span data-ttu-id="33acd-131">En el suscriptor, ejecute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) con los mismos valores para ALGORITHM, KEY_SOURCE e IDENTITY_VALUE que en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="33acd-131">At the Subscriber, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span> <span data-ttu-id="33acd-132">Puede especificar un valor distinto para ENCRYPTION BY.</span><span class="sxs-lookup"><span data-stu-id="33acd-132">You can specify a different value for ENCRYPTION BY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="33acd-133">El valor de KEY_SOURCE son datos importantes que pueden utilizarse para volver a crear la clave simétrica y descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="33acd-133">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="33acd-134">KEY_SOURCE siempre debe almacenarse y transportarse de forma segura.</span><span class="sxs-lookup"><span data-stu-id="33acd-134">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
9. <span data-ttu-id="33acd-135">Ejecute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) para abrir la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="33acd-135">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
10. <span data-ttu-id="33acd-136">Use la función [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) para descifrar los datos replicados en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="33acd-136">Use the [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) function to decrypt replicated data at the Subscriber.</span></span>  
  
11. <span data-ttu-id="33acd-137">Ejecute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) para cerrar la clave.</span><span class="sxs-lookup"><span data-stu-id="33acd-137">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33acd-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33acd-138">Example</span></span>  
 <span data-ttu-id="33acd-139">En este ejemplo se crea una clave simétrica, un certificado que se usa para ayudar a proteger la clave simétrica y una clave maestra.</span><span class="sxs-lookup"><span data-stu-id="33acd-139">This example creates a symmetric key, a certificate that is used to help secure the symmetric key, and a master key.</span></span> <span data-ttu-id="33acd-140">Estas claves se crean en la base de datos de publicaciones y,</span><span class="sxs-lookup"><span data-stu-id="33acd-140">These keys are created in the publication database.</span></span> <span data-ttu-id="33acd-141">a continuación, se usan para crear una columna cifrada (EncryptedCreditCardApprovalCode) en la tabla `SalesOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="33acd-141">They are then used to create an encrypted column (EncryptedCreditCardApprovalCode) in the `SalesOrderHeader` table.</span></span> <span data-ttu-id="33acd-142">Esta columna se publica en la publicación AdvWorksSalesOrdersMerge en lugar de en la columna CreditCardApprovalCode no cifrada.</span><span class="sxs-lookup"><span data-stu-id="33acd-142">This column is published in the AdvWorksSalesOrdersMerge publication instead of the unencrypted CreditCardApprovalCode column.</span></span> <span data-ttu-id="33acd-143">Cuando sea posible, pida a los usuarios que proporcionen credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="33acd-143">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="33acd-144">Si debe almacenar las credenciales en un archivo de script, proteja el archivo para evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="33acd-144">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_PublishEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/publishencryptedcolumn.sql#sp_publishencryptedcolumn)]  
  
 [!code-sql[HowTo#sp_AddMergeArticle](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepub.sql#sp_addmergearticle)]  
  
## <a name="example"></a><span data-ttu-id="33acd-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33acd-145">Example</span></span>  
 <span data-ttu-id="33acd-146">En este ejemplo se vuelve a crear la misma clave simétrica en la base de datos de suscripciones con los mismos valores ALGORITHM, KEY_SOURCE e IDENTITY_VALUE del primer ejemplo.</span><span class="sxs-lookup"><span data-stu-id="33acd-146">This example recreates the same symmetric key in the subscription database using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE from the first example.</span></span> <span data-ttu-id="33acd-147">En este ejemplo se da por supuesto que ya ha inicializado una suscripción a la publicación AdvWorksSalesOrdersMerge para replicar la columna cifrada.</span><span class="sxs-lookup"><span data-stu-id="33acd-147">This example assumes that you have already initialized a subscription to the AdvWorksSalesOrdersMerge publication to replicate the encrypted column.</span></span> <span data-ttu-id="33acd-148">Cuando sea posible, pida a los usuarios que proporcionen credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="33acd-148">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="33acd-149">Si tiene que almacenar credenciales en un archivo de script, debe proteger el archivo durante el almacenamiento y el transporte para evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="33acd-149">If you must store credentials in a script file, you must secure the file during storage and transport to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_SubscriberEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/subscriberencryptedcolumn.sql#sp_subscriberencryptedcolumn)]  
  
## <a name="see-also"></a><span data-ttu-id="33acd-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33acd-150">See Also</span></span>  
 <span data-ttu-id="33acd-151">[Seguridad de Replicación de SQL Server](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="33acd-151">[SQL Server Replication Security](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="33acd-152">Crear claves simétricas idénticas en dos servidores</span><span class="sxs-lookup"><span data-stu-id="33acd-152">Create Identical Symmetric Keys on Two Servers</span></span>](../../security/encryption/create-identical-symmetric-keys-on-two-servers.md)  
  
  
