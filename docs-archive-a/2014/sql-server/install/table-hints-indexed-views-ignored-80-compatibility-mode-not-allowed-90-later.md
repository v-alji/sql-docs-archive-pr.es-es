---
title: Las sugerencias de tabla de las definiciones de vistas indizadas se omiten en el modo de compatibilidad 80 y no se permiten en el modo 90 o posterior | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- query hints [SQL Server]
- indexed views [SQL Server], query hints
ms.assetid: 405dfcff-a3a6-4e6d-a53a-ed77bbacdd13
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cf3cb2b06dc477d93c8fd42312b4835ded42afb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747879"
---
# <a name="table-hints-in-indexed-view-definitions-are-ignored-in-80-compatibility-mode-and-are-not-allowed-in-90-mode-or-later"></a><span data-ttu-id="2faa1-102">Las sugerencias de tabla en definiciones de vistas indizadas se omiten cuando el modo de compatibilidad es 80, mientras que en los modos 90 y superiores, no se permite su uso</span><span class="sxs-lookup"><span data-stu-id="2faa1-102">Table hints in indexed view definitions are ignored in 80 compatibility mode and are not allowed in 90 mode or later</span></span>
  <span data-ttu-id="2faa1-103">Las sugerencias de tabla en las definiciones de las vistas indizadas no se permiten en el modo de compatibilidad 90 o superior.</span><span class="sxs-lookup"><span data-stu-id="2faa1-103">Table hints in the definitions of indexed views are not permitted in the compatibility mode of 90 or later.</span></span> <span data-ttu-id="2faa1-104">Para obtener más información, vea los temas siguientes en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: "Diseñar vistas indizadas", "Crear vistas indizadas" y "Sugerencia de consulta ([!INCLUDE[tsql](../../includes/tsql-md.md)])".</span><span class="sxs-lookup"><span data-stu-id="2faa1-104">For more information, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online: "Designing Indexed Views," "Creating Indexed Views," and "Query Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])."</span></span>  
  
## <a name="component"></a><span data-ttu-id="2faa1-105">Componente</span><span class="sxs-lookup"><span data-stu-id="2faa1-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="2faa1-106">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="2faa1-106">Corrective Action</span></span>  
 <span data-ttu-id="2faa1-107">Las sugerencias de tabla se deben quitar de las definiciones de las vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="2faa1-107">Table hints must be removed from the definitions of indexed views.</span></span> <span data-ttu-id="2faa1-108">Independientemente del modo de compatibilidad que se utilice, es recomendable que pruebe la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2faa1-108">Regardless of which compatibility mode is used, we recommend that you test the application.</span></span> <span data-ttu-id="2faa1-109">Al hacerlo, puede asegurarse de que funciona como es de esperar a la hora de crear, actualizar u obtener acceso a las vistas indizadas, incluyendo el caso en el que las vistas indizadas estén en concordancia con ciertas consultas.</span><span class="sxs-lookup"><span data-stu-id="2faa1-109">By testing the application, you can make sure it performs as expected when indexed views are created, updated, and accessed, including when indexed views are matched to queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2faa1-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2faa1-110">See Also</span></span>  
 <span data-ttu-id="2faa1-111">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2faa1-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2faa1-112">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="2faa1-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
