---
title: Especificar un tipo de suscripción de mezcla y la prioridad de resolución de conflictos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], merge subscription resolvers
- conflict resolution [SQL Server replication], merge replication
ms.assetid: 2b828d83-2341-4924-b92a-4f81a22246c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a19ae6246fe59308283fbaf2f35e2c49f96b140c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752106"
---
# <a name="specify-a-merge-subscription-type-and-conflict-resolution-priority-sql-server-management-studio"></a><span data-ttu-id="3d2dd-102">Especificar un tipo de suscripción de mezcla y la prioridad de resolución de conflictos (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3d2dd-102">Specify a Merge Subscription Type and Conflict Resolution Priority (SQL Server Management Studio)</span></span>
  <span data-ttu-id="3d2dd-103">Especifique un tipo de suscripción de mezcla y la prioridad de resolución de conflictos en la página **Tipo de suscripción** del Asistente para nuevas suscripciones.</span><span class="sxs-lookup"><span data-stu-id="3d2dd-103">Specify a merge subscription type and conflict resolution priority on the **Subscription Type** page of the New Subscription Wizard.</span></span> <span data-ttu-id="3d2dd-104">Para obtener más información sobre cómo utilizar este asistente, vea [Create a Pull Subscription](create-a-pull-subscription.md) y [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3d2dd-104">For more information about using this wizard, see [Create a Pull Subscription](create-a-pull-subscription.md) and [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="3d2dd-105">El tipo de suscripción no se puede modificar después de crear la suscripción, pero se puede modificar la prioridad del tipo de suscripción de servidor en el cuadro de diálogo **Propiedades de suscripción - \<Publisher>: \<PublicationDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="3d2dd-105">Subscription type cannot be modified after a subscription is created, but priority can be modified for the server subscription type in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box.</span></span> <span data-ttu-id="3d2dd-106">Para obtener más información acerca de cómo obtener acceso a este cuadro de diálogo, vea [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) y [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3d2dd-106">For more information about accessing this dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
### <a name="to-specify-a-merge-subscription-type-and-conflict-resolution-priority"></a><span data-ttu-id="3d2dd-107">Para especificar un tipo de suscripción de mezcla y la prioridad de resolución de conflictos</span><span class="sxs-lookup"><span data-stu-id="3d2dd-107">To specify a merge subscription type and conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="3d2dd-108">En la página **Tipo de suscripción** del Asistente para nuevas suscripciones, seleccione **Cliente** o **Servidor** en la opción **Tipo de suscripción** .</span><span class="sxs-lookup"><span data-stu-id="3d2dd-108">On the **Subscription Type** page of the New Subscription Wizard, select **Client** or **Server** for the **Subscription Type** option.</span></span>  
  
2.  <span data-ttu-id="3d2dd-109">Si selecciona el tipo de suscripción **Servidor**, escriba también un valor (de 0,00 a 99,99) en la opción **Prioridad para la resolución de conflictos** .</span><span class="sxs-lookup"><span data-stu-id="3d2dd-109">If you select a subscription type of **Server**, also enter a value (0.00 to 99.99) for the **Priority for Conflict Resolution** option.</span></span>  
  
### <a name="to-modify-the-conflict-resolution-priority"></a><span data-ttu-id="3d2dd-110">Para modificar la prioridad de resolución de conflictos</span><span class="sxs-lookup"><span data-stu-id="3d2dd-110">To modify the conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="3d2dd-111">En **Propiedades de suscripción -\<Publisher>: \<PublicationDatabase>** en el publicador, escriba un valor (de 0,00 a 99,99) en la opción **Prioridad**.</span><span class="sxs-lookup"><span data-stu-id="3d2dd-111">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** at the Publisher, enter a value (0.00 to 99.99) for the **Priority** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d2dd-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d2dd-112">See Also</span></span>  
 <span data-ttu-id="3d2dd-113">[Detección y resolución de conflictos de replicación de mezcla avanzada](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="3d2dd-113">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 [<span data-ttu-id="3d2dd-114">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="3d2dd-114">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
