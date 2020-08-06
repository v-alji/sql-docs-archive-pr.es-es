---
title: Programación del recopilador de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- data collector [SQL Server], programming
ms.assetid: 53b4752b-055d-4716-b2bc-75b4cce84101
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9f4da839f25da8f8aab3e21fa98547eff72d2140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751438"
---
# <a name="data-collector-programming"></a><span data-ttu-id="da27f-102">Programar el recopilador de datos</span><span class="sxs-lookup"><span data-stu-id="da27f-102">Data Collector Programming</span></span>
  <span data-ttu-id="da27f-103">La API del recopilador de datos en <xref:Microsoft.SqlServer.Management.Collector>, permite el control mediante programación de todas las operaciones de configuración a través del modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="da27f-103">The data collector API, in <xref:Microsoft.SqlServer.Management.Collector>, allows programmatic control of all configuration operations through the object model.</span></span> <span data-ttu-id="da27f-104">Además, muchas de las operaciones de recopilación de datos que utilizan la API se implementan como procedimientos almacenados que se instalan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="da27f-104">In addition, many of the data collection operations that use the API are implemented as stored procedures that are installed on the server.</span></span>

 <span data-ttu-id="da27f-105">En la siguiente ilustración se muestran elementos clave del modelo de objetos del recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="da27f-105">The following illustration shows key elements of the data collector object model.</span></span>

 <span data-ttu-id="da27f-106">![Modelo de objetos del recopilador de datos](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "Modelo de objetos del recopilador de datos")</span><span class="sxs-lookup"><span data-stu-id="da27f-106">![The Data Collector Object Model](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "The Data Collector Object Model")</span></span>


