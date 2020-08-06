---
title: Un nombre de canalización con nombre no válido puede bloquear la actualización | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- invalid named pipes [SQL Server]
- named pipes
ms.assetid: 58c2199c-4fdf-4d43-ac1c-842703344b75
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bacfd3d097d7cccb0a5780328c4db95dc5afc733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749609"
---
# <a name="invalid-named-pipe-name-can-block-upgrade"></a><span data-ttu-id="63ede-102">Un nombre no válido de la canalización con nombre puede bloquear la actualización</span><span class="sxs-lookup"><span data-stu-id="63ede-102">Invalid named pipe name can block upgrade</span></span>
  <span data-ttu-id="63ede-103">La actualización no es posible si el protocolo de canalizaciones con nombre no está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="63ede-103">Upgrade fails if the named pipes protocol is incorrectly configured.</span></span>  
  
## <a name="component"></a><span data-ttu-id="63ede-104">Componente</span><span class="sxs-lookup"><span data-stu-id="63ede-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="63ede-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="63ede-105">Description</span></span>  
 <span data-ttu-id="63ede-106">Durante la actualización, el programa de instalación inicia la [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] instancia con compatibilidad de memoria compartida, una canalización con nombre que solo acepta conexiones locales.</span><span class="sxs-lookup"><span data-stu-id="63ede-106">During upgrade, the Setup program starts the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] instance with shared memory support, a named pipe that only accepts local connections.</span></span> <span data-ttu-id="63ede-107">Si el nombre de canalización especificado en el servidor no está en blanco, debe comenzar con la cadena " \\ \\ .\pipe \\ " para ser válido.</span><span class="sxs-lookup"><span data-stu-id="63ede-107">If the pipe name specified on the server is not blank, it must begin with the string "\\\\.\pipe\\" to be valid.</span></span> <span data-ttu-id="63ede-108">Si el nombre de la canalización no es válido, [!INCLUDE[ssDE](../../includes/ssde-md.md)] no se iniciará y se producirá un error en la instalación.</span><span class="sxs-lookup"><span data-stu-id="63ede-108">If the pipe name is not valid, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will not start, and setup will fail.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="63ede-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="63ede-109">Corrective Action</span></span>  
 <span data-ttu-id="63ede-110">Use la \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herramienta de red\*\* para proporcionar un nombre de canalización válido y, a continuación, ejecute el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="63ede-110">Use the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Utility** to supply a valid pipe name, and then run Setup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ede-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63ede-111">See Also</span></span>  
 <span data-ttu-id="63ede-112">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="63ede-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="63ede-113">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="63ede-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
