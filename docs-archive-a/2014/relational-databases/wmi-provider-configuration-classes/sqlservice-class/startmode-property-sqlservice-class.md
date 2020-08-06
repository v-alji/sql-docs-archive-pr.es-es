---
title: Propiedad StartMode (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartMode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartMode property
ms.assetid: c0c2c7f8-d4ae-44f2-ad8e-aecfcb7c2878
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bafffcc3c8f82f69896d0a22e9b0a9060e04cd10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746819"
---
# <a name="startmode-property-sqlservice-class"></a><span data-ttu-id="16d63-102">Propiedad StartMode (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="16d63-102">StartMode Property (SqlService Class)</span></span>
  <span data-ttu-id="16d63-103">Obtiene el modo de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="16d63-103">Gets the start mode of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d63-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16d63-104">Syntax</span></span>  
  
```  
  
object  
.StartMode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="16d63-105">Partes</span><span class="sxs-lookup"><span data-stu-id="16d63-105">Parts</span></span>  
 <span data-ttu-id="16d63-106">*object*</span><span class="sxs-lookup"><span data-stu-id="16d63-106">*object*</span></span>  
 <span data-ttu-id="16d63-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="16d63-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="16d63-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="16d63-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="16d63-109">Valor uint32 que especifica el modo del servicio.</span><span class="sxs-lookup"><span data-stu-id="16d63-109">A uint32 value that specifies the mode of the service.</span></span>  
  
 <span data-ttu-id="16d63-110">Los valores pueden ser alguno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="16d63-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="16d63-111">Arranque</span><span class="sxs-lookup"><span data-stu-id="16d63-111">Boot</span></span>  
 <span data-ttu-id="16d63-112">Valor = 0.</span><span class="sxs-lookup"><span data-stu-id="16d63-112">Value = 0.</span></span> <span data-ttu-id="16d63-113">Servicio iniciado por el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="16d63-113">Service started by the operating system loader.</span></span> <span data-ttu-id="16d63-114">Esta opción solo es válida para los servicios del controlador.</span><span class="sxs-lookup"><span data-stu-id="16d63-114">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="16d63-115">Sistema</span><span class="sxs-lookup"><span data-stu-id="16d63-115">System</span></span>  
 <span data-ttu-id="16d63-116">Valor = 1.</span><span class="sxs-lookup"><span data-stu-id="16d63-116">Value = 1.</span></span> <span data-ttu-id="16d63-117">Servicio iniciado por el método `IoInitSystem`.</span><span class="sxs-lookup"><span data-stu-id="16d63-117">Service started by the `IoInitSystem` method.</span></span> <span data-ttu-id="16d63-118">Esta opción solo es válida para los servicios del controlador.</span><span class="sxs-lookup"><span data-stu-id="16d63-118">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="16d63-119">Automático</span><span class="sxs-lookup"><span data-stu-id="16d63-119">Automatic</span></span>  
 <span data-ttu-id="16d63-120">Valor = 2.</span><span class="sxs-lookup"><span data-stu-id="16d63-120">Value = 2.</span></span> <span data-ttu-id="16d63-121">Servicio que el administrador de control de servicios iniciará automáticamente durante el inicio del sistema.</span><span class="sxs-lookup"><span data-stu-id="16d63-121">Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="16d63-122">Manual</span><span class="sxs-lookup"><span data-stu-id="16d63-122">Manual</span></span>  
 <span data-ttu-id="16d63-123">Valor = 3.</span><span class="sxs-lookup"><span data-stu-id="16d63-123">Value = 3.</span></span> <span data-ttu-id="16d63-124">Servicio que Computer Manager iniciará cuando un proceso llame al método `StartService`.</span><span class="sxs-lookup"><span data-stu-id="16d63-124">Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="16d63-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="16d63-125">Disabled</span></span>  
 <span data-ttu-id="16d63-126">Valor = 4.</span><span class="sxs-lookup"><span data-stu-id="16d63-126">Value = 4.</span></span> <span data-ttu-id="16d63-127">El servicio no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="16d63-127">Service cannot be started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16d63-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="16d63-128">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d63-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16d63-129">See Also</span></span>  
 <span data-ttu-id="16d63-130">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="16d63-130">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
