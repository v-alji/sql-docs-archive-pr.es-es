---
title: Modifique las aplicaciones para esperar valores BIGINT de sysperfinfo. cntr_value | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sysperfinfo
- bigint values [SQL Server]
ms.assetid: b0345303-6e9a-4078-8148-6e1bce207b8c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 108a9b981debc95e182b16847c39a03d4b242088
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749594"
---
# <a name="modify-applications-to-expect-bigint-values-from-sysperfinfocntr_value"></a><span data-ttu-id="8e27a-102">Modificar las aplicaciones para obtener valores bigint de sysperfinfo.cntr_value</span><span class="sxs-lookup"><span data-stu-id="8e27a-102">Modify applications to expect bigint values from sysperfinfo.cntr_value</span></span>
  <span data-ttu-id="8e27a-103">sysperfinfo devuelve un `bigint` valor para la columna cntr_value.</span><span class="sxs-lookup"><span data-stu-id="8e27a-103">sysperfinfo returns a `bigint` value for the cntr_value column.</span></span>  
  
## <a name="component"></a><span data-ttu-id="8e27a-104">Componente</span><span class="sxs-lookup"><span data-stu-id="8e27a-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="8e27a-105">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="8e27a-105">Corrective Action</span></span>  
 <span data-ttu-id="8e27a-106">Modifique las aplicaciones que utilizan sysperfinfo para asegurarse de que puedan controlar los valores `bigint` de la columna cntr_value.</span><span class="sxs-lookup"><span data-stu-id="8e27a-106">Modify applications that use sysperfinfo to ensure that they can handle the `bigint` values of the cntr_value column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e27a-107">sysperfinfo es una vista de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="8e27a-107">sysperfinfo is a compatibility view.</span></span> <span data-ttu-id="8e27a-108">Debe utilizar en su lugar la vista de administración dinámica sys.dm_os_performance_counter.</span><span class="sxs-lookup"><span data-stu-id="8e27a-108">You should use the sys.dm_os_performance_counter dynamic management view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e27a-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e27a-109">See Also</span></span>  
 <span data-ttu-id="8e27a-110">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8e27a-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="8e27a-111">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="8e27a-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
