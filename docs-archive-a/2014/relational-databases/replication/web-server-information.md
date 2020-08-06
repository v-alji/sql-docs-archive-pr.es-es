---
title: Información del servidor web | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.webserverinformation.f1
ms.assetid: 86d72275-45c7-459f-98cf-f5a366ed279c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7b461ed26b3e234f083add3312e256e164efc9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671466"
---
# <a name="web-server-information"></a><span data-ttu-id="3830d-102">Información del servidor web</span><span class="sxs-lookup"><span data-stu-id="3830d-102">Web Server Information</span></span>
  <span data-ttu-id="3830d-103">Para usar la opción de sincronización web en la replicación de mezcla se necesita la información del servidor web.</span><span class="sxs-lookup"><span data-stu-id="3830d-103">Web server information is required to use the Web synchronization option for merge replication.</span></span> <span data-ttu-id="3830d-104">Para más información sobre cómo configurar la sincronización web, vea [Configurar la sincronización web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="3830d-104">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3830d-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="3830d-105">Options</span></span>  
 <span data-ttu-id="3830d-106">**Dirección del servidor web**</span><span class="sxs-lookup"><span data-stu-id="3830d-106">**Web server address**</span></span>  
 <span data-ttu-id="3830d-107">Si se especifica una dirección de servidor web en la página **Instantánea FTP e Internet** del cuadro de diálogo **Propiedades de la publicación**, aparecerá en este cuadro de texto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3830d-107">If you specified a Web server address in the **FTP Snapshot andInternet** page of the **Publication Properties** dialog box, it appears in this text box as a default.</span></span> <span data-ttu-id="3830d-108">Puede aceptar la dirección predeterminada o escribir una dirección completa de servidor web para el servidor de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) que sincroniza la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3830d-108">Either accept the default or enter a fully qualified Web server address for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) server that synchronizes this subscription.</span></span>  
  
 <span data-ttu-id="3830d-109">**¿Cómo se conectarán los suscriptores al servidor web?**</span><span class="sxs-lookup"><span data-stu-id="3830d-109">**How will each Subscriber connect to the Web server?**</span></span>  
 <span data-ttu-id="3830d-110">Especifique el tipo de autenticación usado para conectar con el servidor web.</span><span class="sxs-lookup"><span data-stu-id="3830d-110">Specify the type of authentication used to connect to the Web server.</span></span> <span data-ttu-id="3830d-111">Se recomienda usar Autenticación básica para las conexiones con el servidor IIS junto con SSL (Capa de sockets seguros).</span><span class="sxs-lookup"><span data-stu-id="3830d-111">It is recommended to use Basic Authentication for connections to the IIS server in conjunction with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="3830d-112">Si selecciona Autenticación básica, escriba el nombre de inicio de sesión y la contraseña para conectar desde el suscriptor con el servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="3830d-112">If you select Basic Authentication, enter the login and password that will be used to connect from the Subscriber to the IIS server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3830d-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3830d-113">See Also</span></span>  
 <span data-ttu-id="3830d-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="3830d-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="3830d-115">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md)  (Ver y modificar las propiedades de una suscripción de extracción)</span><span class="sxs-lookup"><span data-stu-id="3830d-115">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="3830d-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="3830d-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 <span data-ttu-id="3830d-117">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="3830d-117">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="3830d-118">Sincronización web para la replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="3830d-118">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
