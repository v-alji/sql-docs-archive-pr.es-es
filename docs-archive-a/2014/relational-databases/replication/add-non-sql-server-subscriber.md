---
title: Agregar suscriptor que no sea de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.addnonsqlsubscriber.f1
ms.assetid: 21beeaa0-4b9e-48da-be63-1b9ff14e03d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e36d048b11fcc71b27ab0ab2ee815b0284187c4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673660"
---
# <a name="add-non-sql-server-subscriber"></a><span data-ttu-id="e0b00-102">Agregar suscriptor que no sea de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e0b00-102">Add Non-SQL Server Subscriber</span></span>
  <span data-ttu-id="e0b00-103">La replicación admite la creación de publicaciones de inserción a publicaciones de instantáneas y transaccionales para suscriptores de Oracle e IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="e0b00-103">Replication supports creating push subscriptions to snapshot and transactional publications for Oracle and IBM DB2 Subscribers.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e0b00-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="e0b00-104">Options</span></span>  
 <span data-ttu-id="e0b00-105">**Tipo de suscriptor que se agregará**</span><span class="sxs-lookup"><span data-stu-id="e0b00-105">**Type of Subscriber to add**</span></span>  
 <span data-ttu-id="e0b00-106">Seleccione un suscriptor de Oracle o IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="e0b00-106">Select an Oracle Subscriber or IBM DB2 Subscriber.</span></span> <span data-ttu-id="e0b00-107">Para obtener más información sobre cómo admitir estos suscriptores, vea [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) (Suscriptores que no son de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="e0b00-107">For more information about support for these Subscribers, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
 <span data-ttu-id="e0b00-108">**Nombre del origen de datos**</span><span class="sxs-lookup"><span data-stu-id="e0b00-108">**Data source name**</span></span>  
 <span data-ttu-id="e0b00-109">Nombre utilizado para localizar la base de datos en una red.</span><span class="sxs-lookup"><span data-stu-id="e0b00-109">The name used to locate the database on a network.</span></span> <span data-ttu-id="e0b00-110">La replicación produce una cadena de conexión a la base de datos utilizando el nombre del origen de datos, combinado con el inicio de sesión, la contraseña y las opciones de conexión especificadas en la página **Seguridad del Agente de distribución** de este asistente.</span><span class="sxs-lookup"><span data-stu-id="e0b00-110">Replication produces a connection string for the database using the data source name, combined with the login, password, and any connection options you specify in the **Distribution Agent Security** page in this wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0b00-111">[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no valida el nombre del origen de datos y la cadena de conexión hasta que el Agente de distribución intenta inicializar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="e0b00-111">The data source name and connection string are not validated by [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until the Distribution Agent attempts to initialize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b00-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0b00-112">See Also</span></span>  
 <span data-ttu-id="e0b00-113">[Crear una suscripción para un suscriptor que no sea de SQL Server](create-a-subscription-for-a-non-sql-server-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="e0b00-113">[Create a Subscription for a Non-SQL Server Subscriber](create-a-subscription-for-a-non-sql-server-subscriber.md) </span></span>  
 <span data-ttu-id="e0b00-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="e0b00-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="e0b00-115">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="e0b00-115">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
