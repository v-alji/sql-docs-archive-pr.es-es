---
title: el carácter 0xFFFF no es válido como identificador de objeto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- 0xFFFF character [SQL Server]
ms.assetid: b2c9c8cf-9194-45e0-be6b-2d5ec52e8153
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4594c1cca0fc183100d927842cc2b533694bf90e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672544"
---
# <a name="0xffff-character-is-not-valid-as-an-object-identifier"></a><span data-ttu-id="18854-102">El carácter 0xFFFF no es válido como identificador de objeto</span><span class="sxs-lookup"><span data-stu-id="18854-102">0xFFFF character is not valid as an object identifier</span></span>
  <span data-ttu-id="18854-103">El Asesor de actualizaciones ha detectado el carácter 0xFFFF en un identificador de objeto.</span><span class="sxs-lookup"><span data-stu-id="18854-103">Upgrade Advisor has detected the 0xFFFF character in an object identifier.</span></span> <span data-ttu-id="18854-104">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores, no se puede hacer referencia a objetos como bases de datos, tablas y columnas que contienen este carácter en su identificador, ni cambiarles el nombre si el modo de compatibilidad de bases de datos está establecido en 90 o posterior.</span><span class="sxs-lookup"><span data-stu-id="18854-104">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later, objects such as databases, tables, and columns that contain this character in their identifiers cannot be referenced or renamed when the database compatibility mode is set to 90 or later.</span></span> <span data-ttu-id="18854-105">Al actualizar a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], las bases de datos de usuario conservan sus modos de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="18854-105">When you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], user databases maintain their compatibility mode.</span></span> <span data-ttu-id="18854-106">Antes de cambiar el modo de compatibilidad de bases de datos al 90 o posterior, cambie el nombre del objeto que contiene el carácter 0xFFFF.</span><span class="sxs-lookup"><span data-stu-id="18854-106">Before you change the database compatibility mode to 90 or later, rename the object that contains the 0xFFFF character.</span></span>  
  
 <span data-ttu-id="18854-107">Para obtener más información acerca de los identificadores, vea "Identificadores" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18854-107">For more information about identifiers, see "Identifiers" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="18854-108">Para obtener más información sobre los modos de compatibilidad de la base de datos, vea "sp_dbcmptlevel" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18854-108">For more information about database compatibility modes, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="18854-109">Componente</span><span class="sxs-lookup"><span data-stu-id="18854-109">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18854-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18854-110">See Also</span></span>  
 <span data-ttu-id="18854-111">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="18854-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="18854-112">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="18854-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
