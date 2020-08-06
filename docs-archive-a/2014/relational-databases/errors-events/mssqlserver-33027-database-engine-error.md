---
title: MSSQLSERVER_33027 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33027 (Database Engine error)
ms.assetid: bfdc626e-7958-4511-987d-3b687824e8af
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f6bb461b42b66368224fffd2c14f9b4da61abf5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672056"
---
# <a name="mssqlserver_33027"></a><span data-ttu-id="70a77-102">MSSQLSERVER_33027</span><span class="sxs-lookup"><span data-stu-id="70a77-102">MSSQLSERVER_33027</span></span>
    
## <a name="details"></a><span data-ttu-id="70a77-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="70a77-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70a77-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="70a77-104">Product Name</span></span>|<span data-ttu-id="70a77-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="70a77-105">SQL Server</span></span>|  
|<span data-ttu-id="70a77-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="70a77-106">Event ID</span></span>|<span data-ttu-id="70a77-107">33027</span><span class="sxs-lookup"><span data-stu-id="70a77-107">33027</span></span>|  
|<span data-ttu-id="70a77-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="70a77-108">Event Source</span></span>|<span data-ttu-id="70a77-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="70a77-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="70a77-110">Componente</span><span class="sxs-lookup"><span data-stu-id="70a77-110">Component</span></span>|<span data-ttu-id="70a77-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="70a77-111">SQLEngine</span></span>|  
|<span data-ttu-id="70a77-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="70a77-112">Symbolic Name</span></span>|<span data-ttu-id="70a77-113">SEC_CRYPTOPROV_CANTLOADDLL</span><span class="sxs-lookup"><span data-stu-id="70a77-113">SEC_CRYPTOPROV_CANTLOADDLL</span></span>|  
|<span data-ttu-id="70a77-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="70a77-114">Message Text</span></span>|<span data-ttu-id="70a77-115">No se pudo cargar el proveedor de servicios criptográficos '%.\*ls' debido a una firma Authenticode o una ruta de archivo no válida.</span><span class="sxs-lookup"><span data-stu-id="70a77-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span> <span data-ttu-id="70a77-116">Revise los mensajes de otros errores anteriores.</span><span class="sxs-lookup"><span data-stu-id="70a77-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="70a77-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="70a77-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="70a77-118">no ha podido utilizar el proveedor de servicios criptográficos enumerado en el mensaje de error porque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no ha podido cargar la DLL.</span><span class="sxs-lookup"><span data-stu-id="70a77-118">was unable to use the cryptographic provider listed in the error message, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not load the DLL.</span></span> <span data-ttu-id="70a77-119">O el nombre no es válido o la firma Authenticode no es válida.</span><span class="sxs-lookup"><span data-stu-id="70a77-119">Either the name is invalid or the Authenticode signature is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="70a77-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="70a77-120">User Action</span></span>  
 <span data-ttu-id="70a77-121">Compruebe que el archivo está presente y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiene permiso de acceso a esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="70a77-121">Check that the file is present and that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has permission to access that location.</span></span> <span data-ttu-id="70a77-122">Compruebe el registro de errores para ver posibles mensajes relacionados adicionales.</span><span class="sxs-lookup"><span data-stu-id="70a77-122">Check the error log for additional related messages.</span></span> <span data-ttu-id="70a77-123">De lo contrario, póngase en contacto con el proveedor de servicios criptográficos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="70a77-123">Otherwise, contact the cryptographic provider for more information.</span></span>  
  
  
