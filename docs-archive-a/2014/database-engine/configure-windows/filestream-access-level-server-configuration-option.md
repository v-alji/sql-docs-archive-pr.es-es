---
title: filestream access level (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], access level
- filestream access level
ms.assetid: b88f6ff2-795e-4730-bfb8-dbc6a958f2ad
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dfa43b8e6e1762e87dd9c2abbdf7a583963e196e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677241"
---
# <a name="filestream-access-level-server-configuration-option"></a><span data-ttu-id="ef3d9-102">filestream access level (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="ef3d9-102">filestream access level Server Configuration Option</span></span>
  <span data-ttu-id="ef3d9-103">Utilice la opción filestream_access_level para cambiar el nivel de acceso de FILESTREAM para esta instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef3d9-103">Use the filestream_access_level option to change the FILESTREAM access level for this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef3d9-104">Antes de que esta opción tenga cualquier efecto, debe estar habilitada la configuración de administración de Windows para FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ef3d9-104">Before this option has any effect, the Windows administration settings for FILESTREAM must be enabled.</span></span> <span data-ttu-id="ef3d9-105">Puede habilitar esta configuración al instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o utilizando el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef3d9-105">You can enable these settings when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
|<span data-ttu-id="ef3d9-106">Value</span><span class="sxs-lookup"><span data-stu-id="ef3d9-106">Value</span></span>|<span data-ttu-id="ef3d9-107">Definición</span><span class="sxs-lookup"><span data-stu-id="ef3d9-107">Definition</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="ef3d9-108">0</span><span class="sxs-lookup"><span data-stu-id="ef3d9-108">0</span></span>|<span data-ttu-id="ef3d9-109">Deshabilita la compatibilidad de FILESTREAM para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="ef3d9-109">Disables FILESTREAM support for this instance.</span></span>|  
|<span data-ttu-id="ef3d9-110">1</span><span class="sxs-lookup"><span data-stu-id="ef3d9-110">1</span></span>|<span data-ttu-id="ef3d9-111">Habilita FILESTREAM para el acceso a [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef3d9-111">Enables FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span>|  
|<span data-ttu-id="ef3d9-112">2</span><span class="sxs-lookup"><span data-stu-id="ef3d9-112">2</span></span>|<span data-ttu-id="ef3d9-113">Habilita FILESTREAM para el acceso de transmisión por secuencias a [!INCLUDE[tsql](../../includes/tsql-md.md)] y Win32.</span><span class="sxs-lookup"><span data-stu-id="ef3d9-113">Enables FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] and Win32 streaming access.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef3d9-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef3d9-114">See Also</span></span>  
 <span data-ttu-id="ef3d9-115">[Configuración del motor de base de datos - Secuencia de archivo](../../sql-server/install/database-engine-configuration-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="ef3d9-115">[Database Engine Configuration - Filestream](../../sql-server/install/database-engine-configuration-filestream.md) </span></span>  
 [<span data-ttu-id="ef3d9-116">Enable and Configure FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="ef3d9-116">Enable and Configure FILESTREAM</span></span>](../../relational-databases/blob/enable-and-configure-filestream.md)  
  
  
