---
title: Almacenamiento en caché automático (dimensiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- dimensions [Analysis Services], proactive caching
- proactive caching [Analysis Services]
ms.assetid: 7d57fe93-6e5f-4a50-844f-dd2bbdbb94a5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50c723d46b6c51fae0ccc227b5e58cf96f72c7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663772"
---
# <a name="proactive-caching-dimensions"></a><span data-ttu-id="cfbfb-102">Almacenamiento en caché automático (Dimensiones)</span><span class="sxs-lookup"><span data-stu-id="cfbfb-102">Proactive Caching (Dimensions)</span></span>
  <span data-ttu-id="cfbfb-103">El almacenamiento en caché automático proporciona la creación y administración automáticas de la memoria caché MOLAP para objetos OLAP.</span><span class="sxs-lookup"><span data-stu-id="cfbfb-103">Proactive caching provides automatic MOLAP cache creation and management for OLAP objects.</span></span> <span data-ttu-id="cfbfb-104">Los cubos incorporan inmediatamente los cambios que se realizan en los datos de la base de datos, basándose en las notificaciones recibidas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cfbfb-104">The cubes immediately incorporate changes that are made to the data in the database, based upon notifications received from the database.</span></span> <span data-ttu-id="cfbfb-105">El objetivo del almacenamiento en caché automático consiste en proporcionar el rendimiento de MOLAP tradicional, a la vez que se conserva la inmediatez y la facilidad de administración que proporciona ROLAP.</span><span class="sxs-lookup"><span data-stu-id="cfbfb-105">The goal of proactive caching is to provide the performance of traditional MOLAP, while retaining the immediacy and ease of management offered by ROLAP.</span></span>  
  
 <span data-ttu-id="cfbfb-106">Un objeto <xref:Microsoft.AnalysisServices.ProactiveCaching> simple se compone de una especificación de tiempo y una notificación de tabla.</span><span class="sxs-lookup"><span data-stu-id="cfbfb-106">A simple <xref:Microsoft.AnalysisServices.ProactiveCaching> object is composed of: timing specification, and table notification.</span></span> <span data-ttu-id="cfbfb-107">La especificación de tiempo define el horario para actualizar la caché una vez recibida una notificación de cambio.</span><span class="sxs-lookup"><span data-stu-id="cfbfb-107">The timing specification defines the timeframe for updating the cache after a change notification has been received.</span></span> <span data-ttu-id="cfbfb-108">La notificación de tabla define el esquema de la notificación entre la tabla de datos y el objeto <xref:Microsoft.AnalysisServices.ProactiveCaching>.</span><span class="sxs-lookup"><span data-stu-id="cfbfb-108">The table notification defines the notification schema between the data table and the <xref:Microsoft.AnalysisServices.ProactiveCaching> object.</span></span>  
  
  
