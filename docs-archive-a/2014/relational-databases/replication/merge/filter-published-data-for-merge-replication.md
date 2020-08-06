---
title: Filtrar datos publicados para la replicación de mezcla | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication [SQL Server replication], filtering published data
- replication [SQL Server], filtering published data
ms.assetid: 46c5023d-7a3b-4455-becc-e159fcb5d6c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ad9ad45a64f57a6bef8255373180ea943af9893f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661966"
---
# <a name="filter-published-data-for-merge-replication"></a><span data-ttu-id="2645e-102">Filtrar datos publicados para la replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="2645e-102">Filter Published Data for Merge Replication</span></span>
  <span data-ttu-id="2645e-103">Además de los filtros de fila estáticos y los filtros de columna que se pueden definir en otros tipos de replicación, la replicación de mezcla ofrece filtros de fila con parámetros y filtros de combinación.</span><span class="sxs-lookup"><span data-stu-id="2645e-103">In addition to the static row filters and column filters you can define with other types of replication, merge replication offers parameterized row filters and join filters.</span></span> <span data-ttu-id="2645e-104">Para más información sobre los filtros de fila estáticos y los filtros de columna, vea [Filtrar datos publicados](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="2645e-104">For more information about static row filters and column filters, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
 <span data-ttu-id="2645e-105">La replicación de mezcla se utiliza en muchas aplicaciones que admiten usuarios móviles; estas aplicaciones normalmente tienen muchas suscripciones, cada una de las cuales recibe un conjunto de datos único.</span><span class="sxs-lookup"><span data-stu-id="2645e-105">Merge replication is used in many applications that support mobile users; these applications usually have a large number of subscriptions with each subscription receiving a unique data set.</span></span> <span data-ttu-id="2645e-106">Los filtros con parámetros combinados con los filtros de combinación permiten a un administrador configurar una publicación (o, como máximo, un pequeño número de publicaciones) y proporcionar diferentes conjuntos de datos a los usuarios, lo que reduce la sobrecarga de administración que supone la creación de varias publicaciones.</span><span class="sxs-lookup"><span data-stu-id="2645e-106">Parameterized filters combined with join filters allow an administrator to set up one publication (or at most a small number of publications) and yet provide different data sets to users, reducing the management overhead introduced by creating multiple publications.</span></span>  
  
-   <span data-ttu-id="2645e-107">Los filtros con parámetros permiten enviar diferentes particiones de datos a suscriptores distintos sin la necesidad de crear varias publicaciones.</span><span class="sxs-lookup"><span data-stu-id="2645e-107">Parameterized filters allow different partitions of data to be sent to different Subscribers without requiring multiple publications to be created.</span></span> <span data-ttu-id="2645e-108">Por ejemplo, se puede filtrar una tabla para que la replicación de los datos de un determinado vendedor se envíe solamente a ese vendedor.</span><span class="sxs-lookup"><span data-stu-id="2645e-108">For example, a table can be filtered so that data for a given sales representative is replicated only to that representative.</span></span> <span data-ttu-id="2645e-109">Los filtros con parámetros tienen diversas opciones que permiten adaptar el filtro para optimizar el rendimiento y ajustarse perfectamente a los requisitos de los datos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2645e-109">Parameterized filters have a variety of options that allow you to tailor filtering to optimize performance and best match your data and application requirements.</span></span> <span data-ttu-id="2645e-110">Para obtener más información, consulte [Filtros de fila con parámetros](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="2645e-110">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
-   <span data-ttu-id="2645e-111">Los filtros de combinación se utilizan normalmente junto con filtros con parámetros para ampliar el filtro a tablas relacionadas (también se pueden utilizar junto con filtros estáticos).</span><span class="sxs-lookup"><span data-stu-id="2645e-111">Join filters are typically used in conjunction with parameterized filters to extend filtering to related tables (they can also be used in conjunction with static filters).</span></span> <span data-ttu-id="2645e-112">Por ejemplo, el vendedor normalmente tiene datos en otras tablas, como las de clientes y pedidos.</span><span class="sxs-lookup"><span data-stu-id="2645e-112">For example, the sales representative typically has data in other tables such as customer and order tables.</span></span> <span data-ttu-id="2645e-113">Estos datos se pueden filtrar para que los vendedores solo reciban los datos de los pedidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="2645e-113">This data can be filtered so the sales representative receives only the data on her customers and her customers' orders.</span></span> <span data-ttu-id="2645e-114">Para obtener más información, consulte [Join Filters](join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="2645e-114">For more information, see [Join Filters](join-filters.md).</span></span>  
  
 <span data-ttu-id="2645e-115">Un filtro no debe incluir la columna `rowguidcol` que usa la replicación para identificar filas.</span><span class="sxs-lookup"><span data-stu-id="2645e-115">A filter must not include the `rowguidcol` used by replication to identify rows.</span></span> <span data-ttu-id="2645e-116">De forma predeterminada, es la columna agregada al configurar la replicación de mezcla y se denomina **rowguid**.</span><span class="sxs-lookup"><span data-stu-id="2645e-116">By default this is the column added at the time you set up merge replication and is named **rowguid**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2645e-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2645e-117">See Also</span></span>  
 [<span data-ttu-id="2645e-118">Publicar datos y objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="2645e-118">Publish Data and Database Objects</span></span>](../publish/publish-data-and-database-objects.md)  
  
  
