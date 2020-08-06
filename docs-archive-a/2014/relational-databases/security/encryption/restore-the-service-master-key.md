---
title: Restaurar la clave maestra de servicio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], importing
- service master key [SQL Server], restoring
ms.assetid: 14bdbbbe-d384-4692-b670-4243d2466fe1
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 2ad99fc9baa518d50678ddd6e6db1ec554658823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752065"
---
# <a name="restore-the-service-master-key"></a><span data-ttu-id="71da6-102">Restaurar la clave maestra de servicio</span><span class="sxs-lookup"><span data-stu-id="71da6-102">Restore the Service Master Key</span></span>
  <span data-ttu-id="71da6-103">En este tema se describe cómo restaurar la clave maestra de servicio en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71da6-103">This topic describes how to restore the service master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="71da6-104">Es improbable que alguna vez deba restaurar la clave maestra de servicio.</span><span class="sxs-lookup"><span data-stu-id="71da6-104">It is unlikely that you will ever need to restore the service master key.</span></span> <span data-ttu-id="71da6-105">Si tiene que hacerlo, debe proceder con mucha precaución.</span><span class="sxs-lookup"><span data-stu-id="71da6-105">If you do, you should proceed with extreme caution.</span></span> <span data-ttu-id="71da6-106">Para obtener más información, consulte [Back Up the Service Master Key](service-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="71da6-106">For more information, see [Back Up the Service Master Key](service-master-key.md).</span></span>  
  
 <span data-ttu-id="71da6-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="71da6-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="71da6-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="71da6-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="71da6-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="71da6-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="71da6-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="71da6-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="71da6-111">Para restaurar la clave maestra de servicio utilizando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="71da6-111">To restore the service master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="71da6-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="71da6-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="71da6-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="71da6-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="71da6-114">Al restaurar la clave maestra de servicio, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] descifra todas las claves y secretos cifrados con la clave maestra de servicio actual y, a continuación, los cifra con la clave maestra de servicio cargada desde el archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71da6-114">When the service master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys and secrets that have been encrypted with the current service master key, and then encrypts them with the service master key loaded from the backup file.</span></span>  
  
-   <span data-ttu-id="71da6-115">Si se producen errores durante cualquier descifrado, se producirán errores en la restauración.</span><span class="sxs-lookup"><span data-stu-id="71da6-115">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="71da6-116">Puede utilizar la opción FORCE para omitir los errores, pero esta opción provocará la pérdida de los datos que no sea posible descifrar.</span><span class="sxs-lookup"><span data-stu-id="71da6-116">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="71da6-117">La regeneración de la jerarquía de cifrado es una operación que requiere un uso intensivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="71da6-117">Regenerating the encryption hierarchy is a resource-intensive operation.</span></span> <span data-ttu-id="71da6-118">Debe programarla durante un período de baja demanda.</span><span class="sxs-lookup"><span data-stu-id="71da6-118">You should schedule this during a period of low demand.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="71da6-119">La clave maestra de servicio es la raíz de la jerarquía de cifrado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71da6-119">The service master key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="71da6-120">La clave maestra de servicio protege directa o indirectamente las demás claves del árbol.</span><span class="sxs-lookup"><span data-stu-id="71da6-120">The service master key directly or indirectly secures all other keys in the tree.</span></span> <span data-ttu-id="71da6-121">Si no es posible descifrar una clave dependiente durante una restauración forzada, se perderán los datos que protege la clave.</span><span class="sxs-lookup"><span data-stu-id="71da6-121">If a dependent key cannot be decrypted during a forced restore, data that is secured by that key will be lost.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="71da6-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="71da6-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="71da6-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="71da6-123">Permissions</span></span>  
 <span data-ttu-id="71da6-124">Requiere el permiso CONTROL SERVER en el servidor.</span><span class="sxs-lookup"><span data-stu-id="71da6-124">Requires CONTROL SERVER permission on the server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="SSMSProcedure"></a> <span data-ttu-id="71da6-125">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="71da6-125">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-the-service-master-key"></a><span data-ttu-id="71da6-126">Para restaurar la clave maestra de servicio</span><span class="sxs-lookup"><span data-stu-id="71da6-126">To restore the service master key</span></span>  
  
1.  <span data-ttu-id="71da6-127">Recupere una copia de seguridad de la clave maestra de servicio, ya sea desde un medio físico de copia de seguridad o desde un directorio del sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="71da6-127">Retrieve a copy of the backed-up service master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="71da6-128">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71da6-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="71da6-129">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="71da6-129">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="71da6-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="71da6-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the service master key from a backup file.  
    RESTORE SERVICE MASTER KEY   
        FROM FILE = 'c:\temp_backups\keys\service_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="71da6-131">La ruta de acceso de archivo a la clave y la contraseña de la clave (si existe) serán distintas de las que se indica más arriba.</span><span class="sxs-lookup"><span data-stu-id="71da6-131">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="71da6-132">Asegúrese de que ambas son específicas para la instalación del servidor y de la clave.</span><span class="sxs-lookup"><span data-stu-id="71da6-132">Please make sure that both are specific to your server and key set-up.</span></span>  
  
  
