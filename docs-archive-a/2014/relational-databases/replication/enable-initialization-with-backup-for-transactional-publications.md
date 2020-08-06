---
title: Habilitar la inicialización con una copia de seguridad para las publicaciones transaccionales (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: 9df00514-aa9d-4ac6-9766-d226c9958175
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5e22614c8c4f5250db3966e747b686091512774
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663371"
---
# <a name="enable-initialization-with-a-backup-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="54aa8-102">Habilitar la inicialización con una copia de seguridad para las publicaciones transaccionales (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="54aa8-102">Enable Initialization with a Backup for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="54aa8-103">Para inicializar una suscripción a una publicación transaccional desde una copia de seguridad, habilite la publicación para permitir la inicialización desde la copia de seguridad y, después, especifique la información de la copia de seguridad al crear la suscripción:</span><span class="sxs-lookup"><span data-stu-id="54aa8-103">To initialize a subscription to a transactional publication from a backup, enable the publication to allow initialization from a backup, and then specify backup information when creating the subscription:</span></span>  
  
-   <span data-ttu-id="54aa8-104">Habilite la publicación en la página **Opciones de suscripción** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="54aa8-104">Enable the publication on the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="54aa8-105">Para obtener más información sobre el acceso a este cuadro de diálogo, vea [View and Modify Publication Properties](publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="54aa8-105">For more information about accessing this dialog box, see [View and Modify Publication Properties](publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="54aa8-106">Especifique la información de la copia de seguridad con el procedimiento almacenado [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54aa8-106">Specify backup information with the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="54aa8-107">Para obtener más información sobre los parámetros requeridos por **sp_addsubscription**, consulte [Inicializar una suscripción transaccional desde una copia de seguridad &#40;programación de la replicación con Transact-SQL&#41;](initialize-a-transactional-subscription-from-a-backup.md).</span><span class="sxs-lookup"><span data-stu-id="54aa8-107">For more information about the parameters required by **sp_addsubscription**, see [Initialize a Transactional Subscription from a Backup &#40;Replication Transact-SQL Programming&#41;](initialize-a-transactional-subscription-from-a-backup.md).</span></span>  
  
### <a name="to-enable-initialization-with-a-backup"></a><span data-ttu-id="54aa8-108">Para habilitar la inicialización con una copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="54aa8-108">To enable initialization with a backup</span></span>  
  
1.  <span data-ttu-id="54aa8-109">En la página **Opciones de suscripción** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** , seleccione un valor de **True** para la opción **Permitir inicialización desde archivos de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="54aa8-109">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, select a value of **True** for the **Allow initialization from backup files** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54aa8-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54aa8-110">See Also</span></span>  
 [<span data-ttu-id="54aa8-111">Inicializar una suscripción transaccional sin una instantánea</span><span class="sxs-lookup"><span data-stu-id="54aa8-111">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
