---
title: Método SetStartMode (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStartMode Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStartMode method
ms.assetid: f6f198b4-f9a4-468c-8977-76462ef06e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a9b7310623f526d7b106485ed9681df3aa100129
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662717"
---
# <a name="setstartmode-method-sqlservice-class"></a><span data-ttu-id="ebb19-102">Método SetStartMode (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="ebb19-102">SetStartMode Method (SqlService Class)</span></span>
  <span data-ttu-id="ebb19-103">Modifica el modo de inicio de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="ebb19-103">Modifies the start mode of the service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb19-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebb19-104">Syntax</span></span>  
  
```  
  
object  
.SetStartMode(  
StartMode  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ebb19-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ebb19-105">Parts</span></span>  
 <span data-ttu-id="ebb19-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ebb19-106">*object*</span></span>  
 <span data-ttu-id="ebb19-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="ebb19-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ebb19-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ebb19-108">Parameters</span></span>  
 <span data-ttu-id="ebb19-109">*StartMode*</span><span class="sxs-lookup"><span data-stu-id="ebb19-109">*StartMode*</span></span>  
 <span data-ttu-id="ebb19-110">Valor de `uint32` que especifica el modo de inicio de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="ebb19-110">A `uint32` value that specifies the start mode of the service instance.</span></span>  
  
 <span data-ttu-id="ebb19-111">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ebb19-111">The valid values are as follows:</span></span>  
  
 <span data-ttu-id="ebb19-112">Valor = 0.</span><span class="sxs-lookup"><span data-stu-id="ebb19-112">Value = 0.</span></span> <span data-ttu-id="ebb19-113">Boot: controlador de dispositivo iniciado por el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ebb19-113">Boot - Device driver started by the operating system loader.</span></span> <span data-ttu-id="ebb19-114">Este valor solamente es válido para servicios de controladores.</span><span class="sxs-lookup"><span data-stu-id="ebb19-114">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="ebb19-115">Valor = 1.</span><span class="sxs-lookup"><span data-stu-id="ebb19-115">Value = 1.</span></span> <span data-ttu-id="ebb19-116">System: controlador de dispositivo iniciado por el método `IoInitSystem`.</span><span class="sxs-lookup"><span data-stu-id="ebb19-116">System - Device driver started by the `IoInitSystem` method.</span></span> <span data-ttu-id="ebb19-117">Este valor solamente es válido para servicios de controladores.</span><span class="sxs-lookup"><span data-stu-id="ebb19-117">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="ebb19-118">Valor = 2.</span><span class="sxs-lookup"><span data-stu-id="ebb19-118">Value = 2.</span></span> <span data-ttu-id="ebb19-119">Automatic: servicio que el administrador de control de servicios iniciará automáticamente durante el inicio del sistema.</span><span class="sxs-lookup"><span data-stu-id="ebb19-119">Automatic - Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="ebb19-120">Valor = 3.</span><span class="sxs-lookup"><span data-stu-id="ebb19-120">Value = 3.</span></span> <span data-ttu-id="ebb19-121">Manual: servicio que el administrador de equipo iniciará cuando un proceso llame al método `StartService`.</span><span class="sxs-lookup"><span data-stu-id="ebb19-121">Manual - Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="ebb19-122">Valor = 4.</span><span class="sxs-lookup"><span data-stu-id="ebb19-122">Value = 4.</span></span> <span data-ttu-id="ebb19-123">Disabled: el servicio ya no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="ebb19-123">Disabled - Service can no longer be started.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ebb19-124">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ebb19-124">Property Value/Return Value</span></span>  
 <span data-ttu-id="ebb19-125">Valor de `uint32` que es igual a 0 si se modificó el servicio correctamente o igual a 1 si no se admite la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ebb19-125">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="ebb19-126">Cualquier otro número indica que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="ebb19-126">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebb19-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ebb19-127">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb19-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ebb19-128">See Also</span></span>  
 <span data-ttu-id="ebb19-129">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ebb19-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
