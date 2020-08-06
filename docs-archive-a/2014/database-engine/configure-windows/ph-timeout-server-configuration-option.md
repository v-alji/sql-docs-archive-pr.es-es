---
title: PH timeout (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- time limit for protocol handler wait [SQL Server]
- timeout options [SQL Server], ph timeout option
- protocols [SQL Server], timing out
- ph timeout option
ms.assetid: ed19a07c-83fe-4582-9c9e-41b1ce571850
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 515ed74a4b92259d53770bf6d970626eba686453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744857"
---
# <a name="ph-timeout-server-configuration-option"></a><span data-ttu-id="ebf66-102">PH timeout (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="ebf66-102">PH timeout Server Configuration Option</span></span>
  <span data-ttu-id="ebf66-103">Use la opción ph timeout para especificar el tiempo, en segundos, que el controlador de protocolo de texto completo debe esperar para conectarse a una base de datos antes de que se agote el tiempo de espera. El valor predeterminado es 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="ebf66-103">Use the PH timeout option to specify the time, in seconds, that the full-text protocol handler should wait to connect to a database before timing out. The default value is 60 seconds.</span></span> <span data-ttu-id="ebf66-104">Aumente el valor de ph timeout cuando se esté agotando el tiempo de espera de los intentos de conexión debido a problemas de red temporales.</span><span class="sxs-lookup"><span data-stu-id="ebf66-104">Increase the ph timeout value when connection attempts are timing out due to temporary network issues.</span></span>  
  
 <span data-ttu-id="ebf66-105">El controlador de protocolo de texto completo se aloja en el host de demonio de filtro y se utiliza para capturar de SQL Server los datos cuyo índice de texto completo se va a crear.</span><span class="sxs-lookup"><span data-stu-id="ebf66-105">The full-text protocol handler is hosted in the filter daemon host and is used to fetch from SQL Server the data to be full-text indexed.</span></span> <span data-ttu-id="ebf66-106">Para obtener más información sobre los componentes de búsqueda de texto completo, vea [Búsqueda de texto completo](../../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="ebf66-106">For more information about full-text search components, see [Full-Text Search](../../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="ebf66-107">Al intentar capturar una fila de datos, si el controlador de protocolo no puede conectar con SQL Server dentro del tiempo especificado, notifica un error de tiempo de espera para esa fila.</span><span class="sxs-lookup"><span data-stu-id="ebf66-107">When attempting to fetch a data row, if the protocol handler cannot connect to SQL Server within the specified time, it reports a time-out error for that row.</span></span> <span data-ttu-id="ebf66-108">El recopilador de texto completo lo volverá a intentar más tarde.</span><span class="sxs-lookup"><span data-stu-id="ebf66-108">The full-text gatherer will retry the row later.</span></span> <span data-ttu-id="ebf66-109">Para obtener más información sobre el recopilador de texto completo, vea [Rellenar índices de texto completo](../../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="ebf66-109">For more information about the full-text gatherer, see [Populate Full-Text Indexes](../../relational-databases/indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf66-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ebf66-110">See Also</span></span>  
 <span data-ttu-id="ebf66-111">[Búsqueda de texto completo](../../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="ebf66-111">[Full-Text Search](../../relational-databases/search/full-text-search.md) </span></span>  
 <span data-ttu-id="ebf66-112">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ebf66-112">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="ebf66-113">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ebf66-113">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="ebf66-114">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ebf66-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
