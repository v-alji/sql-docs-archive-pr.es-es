---
title: Hacer copias de seguridad de una clave maestra de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], exporting
ms.assetid: 7ad9a0a0-6e4f-4f7b-8801-8c1b9d49c4d8
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 9a66d28fea8289719d3efb2351409e0f14379ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750625"
---
# <a name="back-up-a-database-master-key"></a><span data-ttu-id="6fc44-102">Hacer copias de seguridad de una clave maestra de una base de datos</span><span class="sxs-lookup"><span data-stu-id="6fc44-102">Back Up a Database Master Key</span></span>
  <span data-ttu-id="6fc44-103">En este tema se describe cómo realizar una copia de seguridad de la clave maestra de una base de datos en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fc44-103">This topic describes how to back up a database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6fc44-104">La clave maestra de una base de datos se usa para cifrar otras claves y certificados de la base de datos</span><span class="sxs-lookup"><span data-stu-id="6fc44-104">The database master key is used to encrypt other keys and certificates inside a database.</span></span> <span data-ttu-id="6fc44-105">Si se elimina o daña, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] podría ser incapaz de descifrar esas claves y los datos cifrados que las utilizan quedarían inutilizables y perdidos.</span><span class="sxs-lookup"><span data-stu-id="6fc44-105">If it is deleted or corrupted, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may be unable to decrypt those keys, and the data encrypted using them will be effectively lost.</span></span> <span data-ttu-id="6fc44-106">Por ello, se debe hacer una copia de seguridad de la clave maestra de la base de datos y guardar la copia de seguridad en un lugar protegido fuera de las instalaciones.</span><span class="sxs-lookup"><span data-stu-id="6fc44-106">For this reason, you should back up the database master key and store the backup in a secure off-site location.</span></span>  
  
 <span data-ttu-id="6fc44-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6fc44-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6fc44-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6fc44-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6fc44-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6fc44-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6fc44-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6fc44-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="6fc44-111">Para realizar una copia de seguridad de la clave maestra de una base de datos mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6fc44-111">To back up a database master key using Transact-SQL</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6fc44-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6fc44-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6fc44-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6fc44-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6fc44-114">Es necesario abrir la clave maestra y, por tanto, descifrarla antes de realizar una copia de seguridad de la misma.</span><span class="sxs-lookup"><span data-stu-id="6fc44-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="6fc44-115">Si está cifrada con la clave maestra de servicio, no es necesario abrir explícitamente la clave maestra.</span><span class="sxs-lookup"><span data-stu-id="6fc44-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened.</span></span> <span data-ttu-id="6fc44-116">Pero si la clave maestra solo está cifrada con una contraseña, debe abrirse explícitamente.</span><span class="sxs-lookup"><span data-stu-id="6fc44-116">But if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="6fc44-117">Se recomienda realizar una copia de seguridad de la clave maestra inmediatamente después de crearla y guardarla en un lugar seguro y alejado de las instalaciones.</span><span class="sxs-lookup"><span data-stu-id="6fc44-117">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6fc44-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6fc44-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6fc44-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="6fc44-119">Permissions</span></span>  
 <span data-ttu-id="6fc44-120">Necesita el permiso CONTROL en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6fc44-120">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="Procedure"></a><span data-ttu-id="6fc44-121">Usar SQL Server Management Studio con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6fc44-121">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-database-master-key"></a><span data-ttu-id="6fc44-122">Para hacer una copia de seguridad de la clave maestra de una base de datos</span><span class="sxs-lookup"><span data-stu-id="6fc44-122">To back-up the database master key</span></span>  
  
1.  <span data-ttu-id="6fc44-123">En [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], conéctese a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que contenga la clave maestra de base de datos de la que desea hacer una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6fc44-123">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the database master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="6fc44-124">Elija una contraseña que se utilizará para cifrar la clave maestra de base de datos en el medio de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6fc44-124">Choose a password that will be used to encrypt the database master key on the backup medium.</span></span> <span data-ttu-id="6fc44-125">Esta contraseña se somete a comprobaciones de complejidad.</span><span class="sxs-lookup"><span data-stu-id="6fc44-125">This password is subject to complexity checks.</span></span>  
  
3.  <span data-ttu-id="6fc44-126">Hágase con un medio de copia de seguridad extraíble para guardar una copia de seguridad de la clave.</span><span class="sxs-lookup"><span data-stu-id="6fc44-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="6fc44-127">Identifique un directorio NTFS en el que va a crear la copia de seguridad de la clave.</span><span class="sxs-lookup"><span data-stu-id="6fc44-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="6fc44-128">En este directorio creará el archivo indicado en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fc44-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="6fc44-129">El directorio debe estar protegido mediante listas de control de acceso (ACL) muy restrictivas.</span><span class="sxs-lookup"><span data-stu-id="6fc44-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="6fc44-130">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fc44-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="6fc44-131">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6fc44-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="6fc44-132">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6fc44-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key. Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;   
    GO  
    OPEN MASTER KEY DECRYPTION BY PASSWORD = 'sfj5300osdVdgwdfkli7';   
  
    BACKUP MASTER KEY TO FILE = 'c:\temp\exportedmasterkey'   
        ENCRYPTION BY PASSWORD = 'sd092735kjn$&adsg';   
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="6fc44-133">La ruta de acceso de archivo a la clave y la contraseña de la clave (si existe) serán distintas de las que se indica más arriba.</span><span class="sxs-lookup"><span data-stu-id="6fc44-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="6fc44-134">Asegúrese de que ambas son específicas para la instalación del servidor y de la clave.</span><span class="sxs-lookup"><span data-stu-id="6fc44-134">Please make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="6fc44-135">Copie el archivo en el medio de copia de seguridad y compruebe que la copia es correcta.</span><span class="sxs-lookup"><span data-stu-id="6fc44-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="6fc44-136">Guarde la copia de seguridad en una ubicación segura fuera de las instalaciones.</span><span class="sxs-lookup"><span data-stu-id="6fc44-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="6fc44-137">Para obtener más información, vea [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) y [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6fc44-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  
