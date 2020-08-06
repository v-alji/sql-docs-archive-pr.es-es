---
title: Replicación a través de Internet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Web publishing [SQL Server replication], about Web publishing
- Web publishing [SQL Server replication]
- Internet [SQL Server replication]
- Internet [SQL Server replication], publishing
ms.assetid: 04e7f4ed-e244-4bbe-ba12-09c33abea09e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46c61f8a5383c87d46fa0dbda18876b43ffb7739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662791"
---
# <a name="replication-over-the-internet"></a><span data-ttu-id="82a5c-102">Replicación por Internet</span><span class="sxs-lookup"><span data-stu-id="82a5c-102">Replication over the Internet</span></span>
  <span data-ttu-id="82a5c-103">La replicación de datos por Internet permite a usuarios desconectados y remotos obtener acceso a los datos cuando los necesiten, por medio de una conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="82a5c-103">Replicating data over the Internet allows remote, disconnected users to access data when they need it using a connection to the Internet.</span></span> <span data-ttu-id="82a5c-104">Los datos se replican a través de Internet mediante:</span><span class="sxs-lookup"><span data-stu-id="82a5c-104">Replicate data over the Internet using:</span></span>  
  
-   <span data-ttu-id="82a5c-105">Una red privada virtual (VPN).</span><span class="sxs-lookup"><span data-stu-id="82a5c-105">A Virtual Private Network (VPN).</span></span> <span data-ttu-id="82a5c-106">Para más información, vea [Publicar datos a través de Internet mediante VPN](publish-data-over-the-internet-using-vpn.md).</span><span class="sxs-lookup"><span data-stu-id="82a5c-106">For more information, see [Publish Data over the Internet Using VPN](publish-data-over-the-internet-using-vpn.md).</span></span>  
  
-   <span data-ttu-id="82a5c-107">La opción de sincronización web para replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="82a5c-107">The Web synchronization option for merge replication.</span></span> <span data-ttu-id="82a5c-108">Para más información, consulte [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="82a5c-108">For more information, see [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span></span>  
  
 <span data-ttu-id="82a5c-109">Todos los tipos de replicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueden replicar datos a través de VPN, pero tenga en cuenta la sincronización web si está utilizando replicación de combinación.</span><span class="sxs-lookup"><span data-stu-id="82a5c-109">All types of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication can replicate data over a VPN, but you should consider Web synchronization if you are using merge replication.</span></span>  
  
  
