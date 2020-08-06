---
title: Modifique las instrucciones UPDATETEXT que leen y escriben en objetos binarios grandes (BLOB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- UPDATETEXT statement
- text [SQL Server], UPDATETEXT statements
ms.assetid: b85da6a7-42f6-4707-a25e-3ded8958b94f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 061e7bad0bae5a74d103406265ad79195f79f7db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672465"
---
# <a name="modify-updatetext-statements-that-read-and-write-to-binary-large-objects-blobs"></a><span data-ttu-id="96bcc-102">Modificar instrucciones UPDATETEXT que leen y escriben en objetos binarios grandes (BLOB)</span><span class="sxs-lookup"><span data-stu-id="96bcc-102">Modify UPDATETEXT statements that read and write to binary large objects (BLOBs)</span></span>
  <span data-ttu-id="96bcc-103">El Asesor de actualizaciones ha detectado instrucciones UPDATETEXT que leen y escriben en los mismos objetos binarios grandes (BLOB) mediante el mismo puntero de texto.</span><span class="sxs-lookup"><span data-stu-id="96bcc-103">Upgrade Advisor detected UPDATETEXT statements that read and write to the same binary large objects (BLOB) by using the same text pointer.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="96bcc-104">no admite el uso de punteros de texto de esta forma.</span><span class="sxs-lookup"><span data-stu-id="96bcc-104">does not support the use of text pointers in this manner.</span></span>  
  
## <a name="component"></a><span data-ttu-id="96bcc-105">Componente</span><span class="sxs-lookup"><span data-stu-id="96bcc-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="96bcc-106">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="96bcc-106">Corrective Action</span></span>  
 <span data-ttu-id="96bcc-107">Copie los objetos BLOB en una tabla temporal o en una variable de tabla y, a continuación, vuelva a asignar el valor a la columna original.</span><span class="sxs-lookup"><span data-stu-id="96bcc-107">Copy the BLOB to a temporary table or to a table variable, and then assign the value back to the original column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96bcc-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96bcc-108">See Also</span></span>  
 <span data-ttu-id="96bcc-109">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="96bcc-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="96bcc-110">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="96bcc-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
