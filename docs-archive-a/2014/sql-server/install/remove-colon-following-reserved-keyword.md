---
title: Quitar dos puntos después de la palabra clave reservada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reserved keywords
ms.assetid: 4f23f7e4-7b4d-4e19-86c9-7527bb8b107d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fc6882439338509a3c716129d9504f209ab1e555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751710"
---
# <a name="remove-colon-following-reserved-keyword"></a><span data-ttu-id="10aa4-102">Quitar los dos puntos que siguen a las palabras claves reservadas</span><span class="sxs-lookup"><span data-stu-id="10aa4-102">Remove colon following reserved keyword</span></span>
  <span data-ttu-id="10aa4-103">El Asesor de actualizaciones detectó un script que contiene dos puntos (:) después de una palabra clave reservada.</span><span class="sxs-lookup"><span data-stu-id="10aa4-103">The Upgrade Advisor detected a script that contains a colon (:) following a reserved keyword.</span></span> <span data-ttu-id="10aa4-104">En versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], esta sintaxis no se tenía en cuenta y las instrucciones se ejecutaban correctamente.</span><span class="sxs-lookup"><span data-stu-id="10aa4-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this syntax is ignored and the statements execute successfully.</span></span> <span data-ttu-id="10aa4-105">Ahora, esta sintaxis hace que la instrucción no se pueda ejecutar si el modo de compatibilidad de la base de datos está establecido en 100 o más.</span><span class="sxs-lookup"><span data-stu-id="10aa4-105">Now, this syntax causes the statement to fail when the database compatibility mode is set to 100 or later.</span></span>  
  
 <span data-ttu-id="10aa4-106">Las bases de datos de usuario mantienen su modo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="10aa4-106">User databases maintain their compatibility mode.</span></span>  
  
## <a name="component"></a><span data-ttu-id="10aa4-107">Componente</span><span class="sxs-lookup"><span data-stu-id="10aa4-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="10aa4-108">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="10aa4-108">Corrective Action</span></span>  
 <span data-ttu-id="10aa4-109">Antes de cambiar el modo de compatibilidad de la base de datos a 100 o más, modifique sus scripts quitando los dos puntos que siguen a las palabras clave reservadas.</span><span class="sxs-lookup"><span data-stu-id="10aa4-109">Before you change the database compatibility mode to 100 or later, modify your scripts by removing colons that follow reserved keywords.</span></span> <span data-ttu-id="10aa4-110">Para obtener más información, vea "sp_dbcmptlevel" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10aa4-110">For more information, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10aa4-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10aa4-111">See Also</span></span>  
 <span data-ttu-id="10aa4-112">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="10aa4-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="10aa4-113">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="10aa4-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
