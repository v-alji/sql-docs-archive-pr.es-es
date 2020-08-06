---
title: Inicializar una suscripción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- snapshot replication [SQL Server], initializing subscriptions
- transactional replication, initializing subscriptions
- initializing subscriptions [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], about initializing subscriptions
- merge replication [SQL Server replication], initializing subscriptions
ms.assetid: d6013845-cb7a-4203-8e21-edce32f1d330
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1f024d360fdeab477ace09970b4f140a97696c2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663346"
---
# <a name="initialize-a-subscription"></a><span data-ttu-id="2e014-102">Inicializar una suscripción</span><span class="sxs-lookup"><span data-stu-id="2e014-102">Initialize a Subscription</span></span>
  <span data-ttu-id="2e014-103">Los suscriptores de una topología de replicación se deben inicializar con el fin de que tengan una copia del esquema de cada artículo de la publicación a la que están suscritos y de los objetos de replicación que se requieran, como procedimientos almacenados, desencadenadores y tablas de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2e014-103">Subscribers in a replication topology must be initialized, so that they have a copy of the schema from each article in the publication they have subscribed to and any replication objects that are required, such as stored procedures, triggers, and metadata tables.</span></span> <span data-ttu-id="2e014-104">Además, el suscriptor normalmente recibe un conjunto de datos inicial.</span><span class="sxs-lookup"><span data-stu-id="2e014-104">In addition, the Subscriber typically receives an initial dataset.</span></span> <span data-ttu-id="2e014-105">El método de inicialización predeterminado usa una instantánea completa que incluye el esquema, objetos de replicación y datos, aunque las publicaciones también se pueden inicializar sin una instantánea completa.</span><span class="sxs-lookup"><span data-stu-id="2e014-105">The default initialization method uses a full snapshot that includes schema, replication objects, and data, but publications can also be initialized without a full snapshot.</span></span>  
  
 <span data-ttu-id="2e014-106">Para obtener más información, consulte [Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) y [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="2e014-106">For more information, see [Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) and [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
  
