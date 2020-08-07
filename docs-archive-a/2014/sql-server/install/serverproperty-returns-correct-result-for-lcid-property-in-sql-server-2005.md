---
title: SERVERPROPERTY devuelve el resultado correcto para la propiedad LCID en SQL Server 2005 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SERVERPROPERTY function
ms.assetid: 833a2fc9-b480-4697-aa7b-9677e78ee0b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebb125a86e6e30f2c3638004593da7657f02f1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746103"
---
# <a name="serverproperty-returns-correct-result-for-lcid-property-in-sql-server-2005"></a><span data-ttu-id="c6c96-102">SERVERPROPERTY devuelve el resultado correcto para la propiedad LCID en SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="c6c96-102">SERVERPROPERTY returns correct result for LCID property in SQL Server 2005</span></span>
  <span data-ttu-id="c6c96-103">Cuando SERVERPROPERTY('LCID') se ejecuta en servidores de intercalación binaria, la función devuelve un valor de identificador regional de Windows (LCID), independientemente de la intercalación actual del servidor.</span><span class="sxs-lookup"><span data-stu-id="c6c96-103">When SERVERPROPERTY('LCID') is run on binary collation servers, the function returns the Windows locale identifier (LCID) that corresponds to the collation of the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6c96-104">Para el caso de los archivos por lotes y archivos de seguimiento que contengan referencias a SERVERPROPERTY ('LCID') y que se ejecuten en otras instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el Asesor de actualizaciones detectará este cambio de comportamiento solo si el resto de instancias tienen la misma intercalación que la instancia actual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6c96-104">For batch and trace files that contain references to SERVERPROPERTY ('LCID') and are run on other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Upgrade Advisor will detect this behavior change only if the other instances have the same collation as the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c6c96-105">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="c6c96-105">Corrective Action</span></span>  
 <span data-ttu-id="c6c96-106">Modifique las aplicaciones de forma que SERVERPROPERTY('LCID') devuelva el LCID de Windows que corresponda con la intercalación del servidor.</span><span class="sxs-lookup"><span data-stu-id="c6c96-106">Modify applications to expect SERVERPROPERTY('LCID') to return the Windows LCID that corresponds to the collation of the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c96-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6c96-107">See Also</span></span>  
 <span data-ttu-id="c6c96-108">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c6c96-108">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c6c96-109">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="c6c96-109">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
