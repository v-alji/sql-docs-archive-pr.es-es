---
title: LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c178a308-8d99-47fc-8a49-5a480dc592f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 32ae8ebe102008d08a6059328ed57cd118ece019
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677125"
---
# <a name="localdb_error_instance_folder_path_too_long"></a><span data-ttu-id="59427-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="59427-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>
    
## <a name="details"></a><span data-ttu-id="59427-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="59427-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59427-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="59427-104">Product Name</span></span>|<span data-ttu-id="59427-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="59427-105">SQL Server</span></span>|  
|<span data-ttu-id="59427-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="59427-106">Event ID</span></span>|<span data-ttu-id="59427-107">260</span><span class="sxs-lookup"><span data-stu-id="59427-107">260</span></span>|  
|<span data-ttu-id="59427-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="59427-108">Event Source</span></span>|<span data-ttu-id="59427-109">SQL Server Local Database Runtime 12.0</span><span class="sxs-lookup"><span data-stu-id="59427-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="59427-110">Componente</span><span class="sxs-lookup"><span data-stu-id="59427-110">Component</span></span>|<span data-ttu-id="59427-111">API de Local Database Runtime</span><span class="sxs-lookup"><span data-stu-id="59427-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="59427-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="59427-112">Message Text</span></span>|<span data-ttu-id="59427-113">La longitud de la ruta de acceso completa de la carpeta de la instancia de Local Database es mayor que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="59427-113">The full path length of the Local Database instance folder is longer than MAX_PATH.</span></span> <span data-ttu-id="59427-114">La instancia debe almacenarse en la carpeta:%% LOCALAPPDATA%% \ Microsoft\Microsoft SQL Server local DB\Instances \\<nombre de instancia \> .</span><span class="sxs-lookup"><span data-stu-id="59427-114">The instance must be stored in folder: %%LOCALAPPDATA%%\Microsoft\Microsoft SQL Server Local DB\Instances\\<instance name\>.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="59427-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="59427-115">Explanation</span></span>  
 <span data-ttu-id="59427-116">La ruta de acceso donde la instancia debe almacenarse es mayor que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="59427-116">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="59427-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="59427-117">User Action</span></span>  
 <span data-ttu-id="59427-118">Cree una nueva ruta de acceso que sea menor que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="59427-118">Create a new path that is shorter than MAX_PATH.</span></span>  
  
  
