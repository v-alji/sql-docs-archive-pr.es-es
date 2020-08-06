---
title: Realizar una copia de seguridad de la clave maestra de servicio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], exporting
ms.assetid: f60b917c-6408-48be-b911-f93b05796904
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: b79212040df67c22ae7e34cd380a1a1f1bd10773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750618"
---
# <a name="back-up-the-service-master-key"></a><span data-ttu-id="f67e6-102">Hacer una copia de seguridad de la clave maestra de servicio</span><span class="sxs-lookup"><span data-stu-id="f67e6-102">Back Up the Service Master Key</span></span>
  <span data-ttu-id="f67e6-103">En este tema se describe cómo realizar una copia de seguridad de la clave maestra de servicio en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f67e6-103">This topic describes how to back-up the Service Master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f67e6-104">La clave maestra de servicio es la raíz de la jerarquía de cifrado.</span><span class="sxs-lookup"><span data-stu-id="f67e6-104">The service master key is the root of the encryption hierarchy.</span></span> <span data-ttu-id="f67e6-105">Debe realizar una copia de seguridad de la clave maestra de servicio y almacenarla en una ubicación segura y fuera de las instalaciones.</span><span class="sxs-lookup"><span data-stu-id="f67e6-105">It should be backed up and stored in a secure, off-site location.</span></span> <span data-ttu-id="f67e6-106">Crear esta copia de seguridad debe ser una de las primeras acciones de administración que se realicen en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f67e6-106">Creating this backup should be one of the first administrative actions performed on the server.</span></span>  
  
 <span data-ttu-id="f67e6-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f67e6-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f67e6-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f67e6-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f67e6-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f67e6-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f67e6-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f67e6-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="f67e6-111">Para realizar una copia de seguridad de la clave maestra de servicio</span><span class="sxs-lookup"><span data-stu-id="f67e6-111">To back-up the Service Master key</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f67e6-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f67e6-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f67e6-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f67e6-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f67e6-114">Es necesario abrir la clave maestra y, por tanto, descifrarla antes de realizar una copia de seguridad de la misma.</span><span class="sxs-lookup"><span data-stu-id="f67e6-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="f67e6-115">Si está cifrada con la clave maestra de servicio, la clave maestra no tiene que abrirse explícitamente; sin embargo, si la clave maestra está cifrada únicamente con una contraseña, debe abrirse explícitamente.</span><span class="sxs-lookup"><span data-stu-id="f67e6-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened; however, if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="f67e6-116">Se recomienda realizar una copia de seguridad de la clave maestra inmediatamente después de crearla y guardarla en un lugar seguro y alejado de las instalaciones.</span><span class="sxs-lookup"><span data-stu-id="f67e6-116">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f67e6-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f67e6-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f67e6-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="f67e6-118">Permissions</span></span>  
 <span data-ttu-id="f67e6-119">Necesita el permiso CONTROL en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f67e6-119">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="Procedure"></a> <span data-ttu-id="f67e6-120">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f67e6-120">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-service-master-key"></a><span data-ttu-id="f67e6-121">Para realizar una copia de seguridad de la clave maestra de servicio</span><span class="sxs-lookup"><span data-stu-id="f67e6-121">To back-up the Service Master key</span></span>  
  
1.  <span data-ttu-id="f67e6-122">En [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], conéctese a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que contenga la clave maestra de servicio de la que desea hacer una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f67e6-122">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the service master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="f67e6-123">Elija una contraseña que se utilizará para cifrar la clave maestra de servicio en el medio de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f67e6-123">Choose a password that will be used to encrypt the service master key on the backup medium.</span></span> <span data-ttu-id="f67e6-124">Esta contraseña se somete a comprobaciones de complejidad.</span><span class="sxs-lookup"><span data-stu-id="f67e6-124">This password is subject to complexity checks.</span></span> <span data-ttu-id="f67e6-125">Para obtener más información, vea [Password Policy](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f67e6-125">For more information, see [Password Policy](../password-policy.md).</span></span>  
  
3.  <span data-ttu-id="f67e6-126">Hágase con un medio de copia de seguridad extraíble para guardar una copia de seguridad de la clave.</span><span class="sxs-lookup"><span data-stu-id="f67e6-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="f67e6-127">Identifique un directorio NTFS en el que va a crear la copia de seguridad de la clave.</span><span class="sxs-lookup"><span data-stu-id="f67e6-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="f67e6-128">En este directorio creará el archivo indicado en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="f67e6-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="f67e6-129">El directorio debe estar protegido mediante listas de control de acceso (ACL) muy restrictivas.</span><span class="sxs-lookup"><span data-stu-id="f67e6-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="f67e6-130">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f67e6-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="f67e6-131">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f67e6-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="f67e6-132">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f67e6-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key.  
    -- Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;  
    GO  
    BACKUP SERVICE MASTER KEY TO FILE = 'c:\temp_backups\keys\service_master_ key'   
        ENCRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f67e6-133">La ruta de acceso de archivo a la clave y la contraseña de la clave (si existe) serán distintas de las que se indica más arriba.</span><span class="sxs-lookup"><span data-stu-id="f67e6-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="f67e6-134">Asegúrese de que ambas son específicas para la instalación del servidor y de la clave.</span><span class="sxs-lookup"><span data-stu-id="f67e6-134">Make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="f67e6-135">Copie el archivo en el medio de copia de seguridad y compruebe que la copia es correcta.</span><span class="sxs-lookup"><span data-stu-id="f67e6-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="f67e6-136">Guarde la copia de seguridad en una ubicación segura fuera de las instalaciones.</span><span class="sxs-lookup"><span data-stu-id="f67e6-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="f67e6-137">Para obtener más información, vea [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) y [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f67e6-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  
