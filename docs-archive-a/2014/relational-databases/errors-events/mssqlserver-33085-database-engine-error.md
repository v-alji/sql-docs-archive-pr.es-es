---
title: MSSQLSERVER_33085 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33085 (Database Engine error)
ms.assetid: c27b8d1d-668a-4ba8-8b61-25a5ebbc5485
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d774ab115c2d0ddbbd7b35c7e32db17e39fcb2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672053"
---
# <a name="mssqlserver_33085"></a><span data-ttu-id="92886-102">MSSQLSERVER_33085</span><span class="sxs-lookup"><span data-stu-id="92886-102">MSSQLSERVER_33085</span></span>
    
## <a name="details"></a><span data-ttu-id="92886-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="92886-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="92886-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="92886-104">Product Name</span></span>|<span data-ttu-id="92886-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="92886-105">SQL Server</span></span>|  
|<span data-ttu-id="92886-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="92886-106">Event ID</span></span>|<span data-ttu-id="92886-107">33085</span><span class="sxs-lookup"><span data-stu-id="92886-107">33085</span></span>|  
|<span data-ttu-id="92886-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="92886-108">Event Source</span></span>|<span data-ttu-id="92886-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="92886-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="92886-110">Componente</span><span class="sxs-lookup"><span data-stu-id="92886-110">Component</span></span>|<span data-ttu-id="92886-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="92886-111">SQLEngine</span></span>|  
|<span data-ttu-id="92886-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="92886-112">Symbolic Name</span></span>|<span data-ttu-id="92886-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="92886-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span></span>|  
|<span data-ttu-id="92886-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="92886-114">Message Text</span></span>|<span data-ttu-id="92886-115">Uno o más métodos no se pueden encontrar en la biblioteca de proveedores de servicios criptográficos '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="92886-115">One or more methods cannot be found in cryptographic provider library '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="92886-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="92886-116">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="92886-117">no pudo utilizar el proveedor de servicios criptográficos enumerado en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="92886-117">was unable to use the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="92886-118">El proveedor de servicios criptográficos no admitió un método necesario.</span><span class="sxs-lookup"><span data-stu-id="92886-118">The cryptographic provider did not support a required method.</span></span> <span data-ttu-id="92886-119">El estado del error indica qué método no se encontró.</span><span class="sxs-lookup"><span data-stu-id="92886-119">The state of the error indicates which method was not found.</span></span>  
  
|<span data-ttu-id="92886-120">State</span><span class="sxs-lookup"><span data-stu-id="92886-120">State</span></span>|<span data-ttu-id="92886-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="92886-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="92886-122">1</span><span class="sxs-lookup"><span data-stu-id="92886-122">1</span></span>|<span data-ttu-id="92886-123">SqlCryptInitializeProvider</span><span class="sxs-lookup"><span data-stu-id="92886-123">SqlCryptInitializeProvider</span></span>|  
|<span data-ttu-id="92886-124">2</span><span class="sxs-lookup"><span data-stu-id="92886-124">2</span></span>|<span data-ttu-id="92886-125">SqlCryptFreeProvider</span><span class="sxs-lookup"><span data-stu-id="92886-125">SqlCryptFreeProvider</span></span>|  
|<span data-ttu-id="92886-126">3</span><span class="sxs-lookup"><span data-stu-id="92886-126">3</span></span>|<span data-ttu-id="92886-127">SqlCryptOpenSession</span><span class="sxs-lookup"><span data-stu-id="92886-127">SqlCryptOpenSession</span></span>|  
|<span data-ttu-id="92886-128">4</span><span class="sxs-lookup"><span data-stu-id="92886-128">4</span></span>|<span data-ttu-id="92886-129">SqlCryptCloseSession</span><span class="sxs-lookup"><span data-stu-id="92886-129">SqlCryptCloseSession</span></span>|  
|<span data-ttu-id="92886-130">5</span><span class="sxs-lookup"><span data-stu-id="92886-130">5</span></span>|<span data-ttu-id="92886-131">SqlCryptGetProviderInfo</span><span class="sxs-lookup"><span data-stu-id="92886-131">SqlCryptGetProviderInfo</span></span>|  
|<span data-ttu-id="92886-132">6</span><span class="sxs-lookup"><span data-stu-id="92886-132">6</span></span>|<span data-ttu-id="92886-133">SqlCryptGetNextAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="92886-133">SqlCryptGetNextAlgorithmId</span></span>|  
|<span data-ttu-id="92886-134">7</span><span class="sxs-lookup"><span data-stu-id="92886-134">7</span></span>|<span data-ttu-id="92886-135">SqlCryptGetAlgorithmInfo</span><span class="sxs-lookup"><span data-stu-id="92886-135">SqlCryptGetAlgorithmInfo</span></span>|  
|<span data-ttu-id="92886-136">8</span><span class="sxs-lookup"><span data-stu-id="92886-136">8</span></span>|<span data-ttu-id="92886-137">SqlCryptCreateKey</span><span class="sxs-lookup"><span data-stu-id="92886-137">SqlCryptCreateKey</span></span>|  
|<span data-ttu-id="92886-138">9</span><span class="sxs-lookup"><span data-stu-id="92886-138">9</span></span>|<span data-ttu-id="92886-139">SqlCryptDropKey</span><span class="sxs-lookup"><span data-stu-id="92886-139">SqlCryptDropKey</span></span>|  
|<span data-ttu-id="92886-140">10</span><span class="sxs-lookup"><span data-stu-id="92886-140">10</span></span>|<span data-ttu-id="92886-141">SqlCryptGetNextKeyId</span><span class="sxs-lookup"><span data-stu-id="92886-141">SqlCryptGetNextKeyId</span></span>|  
|<span data-ttu-id="92886-142">11</span><span class="sxs-lookup"><span data-stu-id="92886-142">11</span></span>|<span data-ttu-id="92886-143">SqlCryptGetKeyInfoByKeyId</span><span class="sxs-lookup"><span data-stu-id="92886-143">SqlCryptGetKeyInfoByKeyId</span></span>|  
|<span data-ttu-id="92886-144">12</span><span class="sxs-lookup"><span data-stu-id="92886-144">12</span></span>|<span data-ttu-id="92886-145">SqlCryptGetKeyInfoByThumb</span><span class="sxs-lookup"><span data-stu-id="92886-145">SqlCryptGetKeyInfoByThumb</span></span>|  
|<span data-ttu-id="92886-146">13</span><span class="sxs-lookup"><span data-stu-id="92886-146">13</span></span>|<span data-ttu-id="92886-147">SqlCryptGetKeyInfoByName</span><span class="sxs-lookup"><span data-stu-id="92886-147">SqlCryptGetKeyInfoByName</span></span>|  
|<span data-ttu-id="92886-148">14</span><span class="sxs-lookup"><span data-stu-id="92886-148">14</span></span>|<span data-ttu-id="92886-149">SqlCryptExportKey</span><span class="sxs-lookup"><span data-stu-id="92886-149">SqlCryptExportKey</span></span>|  
|<span data-ttu-id="92886-150">15</span><span class="sxs-lookup"><span data-stu-id="92886-150">15</span></span>|<span data-ttu-id="92886-151">SqlCryptImportKey</span><span class="sxs-lookup"><span data-stu-id="92886-151">SqlCryptImportKey</span></span>|  
|<span data-ttu-id="92886-152">16</span><span class="sxs-lookup"><span data-stu-id="92886-152">16</span></span>|<span data-ttu-id="92886-153">SqlCryptEncrypt</span><span class="sxs-lookup"><span data-stu-id="92886-153">SqlCryptEncrypt</span></span>|  
|<span data-ttu-id="92886-154">17</span><span class="sxs-lookup"><span data-stu-id="92886-154">17</span></span>|<span data-ttu-id="92886-155">SqlCryptDecrypt</span><span class="sxs-lookup"><span data-stu-id="92886-155">SqlCryptDecrypt</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="92886-156">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="92886-156">User Action</span></span>  
 <span data-ttu-id="92886-157">Póngase en contacto con el proveedor de servicios criptográficos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="92886-157">Contact the cryptographic provider for more information.</span></span>  
  
  
