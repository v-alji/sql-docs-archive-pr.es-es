---
title: Establecer la opción de base de datos PAGE_VERIFY en CHECKSUM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 686b9a4a-ea61-4263-9ab8-f444a3077679
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13296a976722390668b8ca6d901cf0dd080e5cc3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749734"
---
# <a name="set-the-page_verify-database-option-to-checksum"></a><span data-ttu-id="df92b-102">Establecer la opción de base de datos PAGE_VERIFY en CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="df92b-102">Set the PAGE_VERIFY Database Option to CHECKSUM</span></span>
  <span data-ttu-id="df92b-103">Esta regla comprueba si la opción de base de datos PAGE_VERIFY está establecida en CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="df92b-103">This rule checks whether PAGE_VERIFY database option is set to CHECKSUM.</span></span> <span data-ttu-id="df92b-104">Cuando CHECKSUM se habilita para la opción de base de datos PAGE_VERIFY, el [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] calcula una suma de comprobación teniendo en cuenta el contenido de toda la página y almacena el valor en el encabezado de página cuando esta se escribe en el disco.</span><span class="sxs-lookup"><span data-stu-id="df92b-104">When CHECKSUM is enabled for the PAGE_VERIFY database option, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] calculates a checksum over the contents of the whole page, and stores the value in the page header when a page is written to disk.</span></span> <span data-ttu-id="df92b-105">Si la página se lee desde el disco, la suma de comprobación se vuelve a calcular y se compara con el valor de suma de comprobación que está almacenado en el encabezado de página.</span><span class="sxs-lookup"><span data-stu-id="df92b-105">When the page is read from disk, the checksum is recomputed and compared to the checksum value that is stored in the page header.</span></span> <span data-ttu-id="df92b-106">De este modo se ayuda a proporcionar un alto nivel de integridad de los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="df92b-106">This helps provide a high level of data-file integrity.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="df92b-107">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="df92b-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="df92b-108">Establezca la opción de base de datos PAGE_VERIFY en CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="df92b-108">Set the PAGE_VERIFY database option to CHECKSUM.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="df92b-109">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="df92b-109">For More Information</span></span>  
 [<span data-ttu-id="df92b-110">Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="df92b-110">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
