---
title: Restaurar una clave maestra de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], importing
ms.assetid: 16897cc5-db8f-43bb-a38e-6855c82647cf
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 614ba8bdc494ae7e7e5b3ed7b62390721ef642a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752062"
---
# <a name="restore-a-database-master-key"></a><span data-ttu-id="124bd-102">Restaurar una clave maestra de base de datos</span><span class="sxs-lookup"><span data-stu-id="124bd-102">Restore a Database Master Key</span></span>
  <span data-ttu-id="124bd-103">En este tema se describe cómo restaurar la clave maestra de una base de datos en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="124bd-103">This topic describes how to restore the database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="124bd-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="124bd-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="124bd-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="124bd-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="124bd-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="124bd-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="124bd-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="124bd-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="124bd-108">Para restaurar la clave maestra de una base de datos utilizando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="124bd-108">To restore the database master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="124bd-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="124bd-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="124bd-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="124bd-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="124bd-111">Al restaurar la clave maestra, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] descifra todas las claves cifradas con la clave maestra actualmente activa y cifra estas claves con la clave maestra restaurada.</span><span class="sxs-lookup"><span data-stu-id="124bd-111">When the master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys that are encrypted with the currently active master key, and then encrypts these keys with the restored master key.</span></span> <span data-ttu-id="124bd-112">Esta operación requiere un uso intensivo de recursos, por lo que debe programarse durante un período de baja demanda.</span><span class="sxs-lookup"><span data-stu-id="124bd-112">This resource-intensive operation should be scheduled during a period of low demand.</span></span> <span data-ttu-id="124bd-113">Si la clave maestra de base de datos no se encuentra abierta, no puede abrirse o alguna de las claves cifradas con ella no pueden descifrarse, la operación de restauración no se puede realizar.</span><span class="sxs-lookup"><span data-stu-id="124bd-113">If the current database master key is not open or cannot be opened, or if any of the keys that are encrypted by it cannot be decrypted, the restore operation fails.</span></span>  
  
-   <span data-ttu-id="124bd-114">Si se producen errores durante cualquier descifrado, se producirán errores en la restauración.</span><span class="sxs-lookup"><span data-stu-id="124bd-114">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="124bd-115">Puede utilizar la opción FORCE para omitir los errores, pero esta opción provocará la pérdida de los datos que no sea posible descifrar.</span><span class="sxs-lookup"><span data-stu-id="124bd-115">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="124bd-116">Si se cifró la clave maestra con la clave maestra de servicio, la clave maestra restaurada también se cifrará con la clave maestra de servicio.</span><span class="sxs-lookup"><span data-stu-id="124bd-116">If the master key was encrypted by the service master key, the restored master key will also be encrypted by the service master key.</span></span>  
  
-   <span data-ttu-id="124bd-117">Si no hay una clave maestra en la base de datos actual, RESTORE MASTER KEY creará una clave maestra.</span><span class="sxs-lookup"><span data-stu-id="124bd-117">If there is no master key in the current database, RESTORE MASTER KEY creates a master key.</span></span> <span data-ttu-id="124bd-118">La nueva clave maestra no se cifrará automáticamente con la clave maestra de servicio.</span><span class="sxs-lookup"><span data-stu-id="124bd-118">The new master key will not be automatically encrypted with the service master key.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="124bd-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="124bd-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="124bd-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="124bd-120">Permissions</span></span>  
 <span data-ttu-id="124bd-121">Necesita el permiso CONTROL en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="124bd-121">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="SSMSProcedure"></a><span data-ttu-id="124bd-122">Usar SQL Server Management Studio con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="124bd-122">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-restore-the-database-master-key"></a><span data-ttu-id="124bd-123">Para restaurar la clave maestra de una base de datos</span><span class="sxs-lookup"><span data-stu-id="124bd-123">To restore the database master key</span></span>  
  
1.  <span data-ttu-id="124bd-124">Recupere una copia de seguridad de la clave maestra de la base de datos, ya sea desde un medio físico de copia de seguridad o desde un directorio del sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="124bd-124">Retrieve a copy of the backed-up database master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="124bd-125">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="124bd-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="124bd-126">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="124bd-126">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="124bd-127">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="124bd-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the database master key of the AdventureWorks2012 database.  
    USE AdventureWorks2012;  
    GO  
    RESTORE MASTER KEY   
        FROM FILE = 'c:\backups\keys\AdventureWorks2012_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003#GHkf02597gheij04'   
        ENCRYPTION BY PASSWORD = '259087M#MyjkFkjhywiyedfgGDFD';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="124bd-128">La ruta de acceso de archivo a la clave y la contraseña de la clave (si existe) serán distintas de las que se indica más arriba.</span><span class="sxs-lookup"><span data-stu-id="124bd-128">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="124bd-129">Asegúrese de que ambas son específicas para la instalación del servidor y de la clave.</span><span class="sxs-lookup"><span data-stu-id="124bd-129">Please make sure that both are specific to your server and key set-up.</span></span>  
  
 <span data-ttu-id="124bd-130">Para obtener más información, vea [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="124bd-130">For more information, see [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)</span></span>  
  
  
