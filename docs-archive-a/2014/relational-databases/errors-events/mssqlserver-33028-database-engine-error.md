---
title: MSSQLSERVER_33028 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33028 (Database Engine error)
ms.assetid: c5cec0e4-0bcd-4907-826f-e7d835cfcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 555dcf0220793abc0e8af81b3f56867f9960c5f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672055"
---
# <a name="mssqlserver_33028"></a><span data-ttu-id="34c33-102">MSSQLSERVER_33028</span><span class="sxs-lookup"><span data-stu-id="34c33-102">MSSQLSERVER_33028</span></span>
    
## <a name="details"></a><span data-ttu-id="34c33-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="34c33-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34c33-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="34c33-104">Product Name</span></span>|<span data-ttu-id="34c33-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="34c33-105">SQL Server</span></span>|  
|<span data-ttu-id="34c33-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="34c33-106">Event ID</span></span>|<span data-ttu-id="34c33-107">33028</span><span class="sxs-lookup"><span data-stu-id="34c33-107">33028</span></span>|  
|<span data-ttu-id="34c33-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="34c33-108">Event Source</span></span>|<span data-ttu-id="34c33-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="34c33-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="34c33-110">Componente</span><span class="sxs-lookup"><span data-stu-id="34c33-110">Component</span></span>|<span data-ttu-id="34c33-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="34c33-111">SQLEngine</span></span>|  
|<span data-ttu-id="34c33-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="34c33-112">Symbolic Name</span></span>|<span data-ttu-id="34c33-113">SEC_CRYPTOPROV_CANTOPENSESSION</span><span class="sxs-lookup"><span data-stu-id="34c33-113">SEC_CRYPTOPROV_CANTOPENSESSION</span></span>|  
|<span data-ttu-id="34c33-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="34c33-114">Message Text</span></span>|<span data-ttu-id="34c33-115">No se puede abrir la sesión para %S_MSG '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="34c33-115">Cannot open session for %S_MSG '%.\*ls'.</span></span> <span data-ttu-id="34c33-116">Código de error de proveedor: %d.</span><span class="sxs-lookup"><span data-stu-id="34c33-116">Provider error code: %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="34c33-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="34c33-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="34c33-118">no pudo abrir el proveedor de servicios criptográficos enumerado en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="34c33-118">was unable to open the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="34c33-119">El proveedor de servicios criptográficos proporcionó el código de error enumerado.</span><span class="sxs-lookup"><span data-stu-id="34c33-119">The cryptographic provider supplied the error code listed.</span></span> <span data-ttu-id="34c33-120">Puede que tenga que ponerse en contacto con su proveedor de servicios criptográficos para obtener más información sobre el error.</span><span class="sxs-lookup"><span data-stu-id="34c33-120">You may need to contact your cryptographic provider for more information about the error.</span></span>  
  
|<span data-ttu-id="34c33-121">Código de error</span><span class="sxs-lookup"><span data-stu-id="34c33-121">Error code</span></span>|<span data-ttu-id="34c33-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="34c33-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="34c33-123">0</span><span class="sxs-lookup"><span data-stu-id="34c33-123">0</span></span>|<span data-ttu-id="34c33-124">Correcto.</span><span class="sxs-lookup"><span data-stu-id="34c33-124">Success.</span></span> <span data-ttu-id="34c33-125">Ningún error.</span><span class="sxs-lookup"><span data-stu-id="34c33-125">No error.</span></span>|  
|<span data-ttu-id="34c33-126">1</span><span class="sxs-lookup"><span data-stu-id="34c33-126">1</span></span>|<span data-ttu-id="34c33-127">Error.</span><span class="sxs-lookup"><span data-stu-id="34c33-127">Failure.</span></span> <span data-ttu-id="34c33-128">Se ha producido un error no especificado o inesperado.</span><span class="sxs-lookup"><span data-stu-id="34c33-128">An unspecified or unexpected error occurred.</span></span> <span data-ttu-id="34c33-129">No se dispone de información adicional.</span><span class="sxs-lookup"><span data-stu-id="34c33-129">Additional information is not available.</span></span>|  
|<span data-ttu-id="34c33-130">2</span><span class="sxs-lookup"><span data-stu-id="34c33-130">2</span></span>|<span data-ttu-id="34c33-131">Búfer insuficiente.</span><span class="sxs-lookup"><span data-stu-id="34c33-131">Insufficient Buffer.</span></span> <span data-ttu-id="34c33-132">No se pudo asignar espacio para el proveedor de servicios criptográficos.</span><span class="sxs-lookup"><span data-stu-id="34c33-132">Space could not be allocated for the cryptographic provider.</span></span>|  
|<span data-ttu-id="34c33-133">3</span><span class="sxs-lookup"><span data-stu-id="34c33-133">3</span></span>|<span data-ttu-id="34c33-134">No compatible.</span><span class="sxs-lookup"><span data-stu-id="34c33-134">Not Supported.</span></span> <span data-ttu-id="34c33-135">El proveedor de servicios criptográficos no admite esta versión.</span><span class="sxs-lookup"><span data-stu-id="34c33-135">The cryptographic provider is not supported by this release.</span></span> <span data-ttu-id="34c33-136">Seleccione otro proveedor de servicios criptográficos.</span><span class="sxs-lookup"><span data-stu-id="34c33-136">Select another cryptographic provider.</span></span>|  
|<span data-ttu-id="34c33-137">4</span><span class="sxs-lookup"><span data-stu-id="34c33-137">4</span></span>|<span data-ttu-id="34c33-138">Not Found.</span><span class="sxs-lookup"><span data-stu-id="34c33-138">Not Found.</span></span> <span data-ttu-id="34c33-139">El proveedor de servicios criptográficos especificado no está presente o no se tiene autorización para el acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="34c33-139">The specified cryptographic provider is not present or you do not have authorization to access the files.</span></span>|  
|<span data-ttu-id="34c33-140">5</span><span class="sxs-lookup"><span data-stu-id="34c33-140">5</span></span>|<span data-ttu-id="34c33-141">Error de autorización.</span><span class="sxs-lookup"><span data-stu-id="34c33-141">Authorization Failure.</span></span> <span data-ttu-id="34c33-142">Puede ser el resultado de proporcionar un nombre de usuario o una contraseña incorrectos al crear la credencial.</span><span class="sxs-lookup"><span data-stu-id="34c33-142">Can result from providing an incorrect password or username when creating the credential.</span></span> <span data-ttu-id="34c33-143">Puede producirse si la credencial no existe.</span><span class="sxs-lookup"><span data-stu-id="34c33-143">Can result if the credential does not exist.</span></span>|  
|<span data-ttu-id="34c33-144">6</span><span class="sxs-lookup"><span data-stu-id="34c33-144">6</span></span>|<span data-ttu-id="34c33-145">Argumento no válido.</span><span class="sxs-lookup"><span data-stu-id="34c33-145">Invalid Argument.</span></span> <span data-ttu-id="34c33-146">Se ha pasado un argumento no válido al proveedor de servicios criptográficos.</span><span class="sxs-lookup"><span data-stu-id="34c33-146">An invalid argument was passed to the cryptographic provider.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="34c33-147">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="34c33-147">User Action</span></span>  
 <span data-ttu-id="34c33-148">Resuelva el error o póngase en contacto con el proveedor de servicios criptográficos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34c33-148">Resolve the error, or contact the cryptographic provider for more information.</span></span>  
  
  
