---
title: Propiedad State (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- State Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- State property
ms.assetid: 9e09f419-947c-4d4b-9a49-2d3396c847cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a7456113d9ec4444507d1057892a65adf241992f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746813"
---
# <a name="state-property-sqlservice-class"></a><span data-ttu-id="06253-102">Propiedad State (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="06253-102">State Property (SqlService Class)</span></span>
  <span data-ttu-id="06253-103">Obtiene o establece el estado actual del servicio.</span><span class="sxs-lookup"><span data-stu-id="06253-103">Gets or sets the current state of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06253-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06253-104">Syntax</span></span>  
  
```  
  
object  
.State [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="06253-105">Partes</span><span class="sxs-lookup"><span data-stu-id="06253-105">Parts</span></span>  
 <span data-ttu-id="06253-106">*object*</span><span class="sxs-lookup"><span data-stu-id="06253-106">*object*</span></span>  
 <span data-ttu-id="06253-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="06253-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="06253-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="06253-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="06253-109">Valor uint32 que especifica el estado del servicio.</span><span class="sxs-lookup"><span data-stu-id="06253-109">A uint32 value that specifies the state of the service.</span></span>  
  
 <span data-ttu-id="06253-110">Los valores pueden ser alguno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="06253-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="06253-111">1</span><span class="sxs-lookup"><span data-stu-id="06253-111">1</span></span>  
 <span data-ttu-id="06253-112">Detenido.</span><span class="sxs-lookup"><span data-stu-id="06253-112">Stopped.</span></span> <span data-ttu-id="06253-113">El servicio está detenido.</span><span class="sxs-lookup"><span data-stu-id="06253-113">The service is stopped.</span></span>  
  
 <span data-ttu-id="06253-114">2</span><span class="sxs-lookup"><span data-stu-id="06253-114">2</span></span>  
 <span data-ttu-id="06253-115">Inicio pendiente.</span><span class="sxs-lookup"><span data-stu-id="06253-115">Start Pending.</span></span> <span data-ttu-id="06253-116">El servicio está a la espera de que se inicie.</span><span class="sxs-lookup"><span data-stu-id="06253-116">The service is waiting to start.</span></span>  
  
 <span data-ttu-id="06253-117">3</span><span class="sxs-lookup"><span data-stu-id="06253-117">3</span></span>  
 <span data-ttu-id="06253-118">Detención pendiente.</span><span class="sxs-lookup"><span data-stu-id="06253-118">Stop Pending.</span></span> <span data-ttu-id="06253-119">El servicio está a la espera de que se detenga.</span><span class="sxs-lookup"><span data-stu-id="06253-119">The service is waiting to stop.</span></span>  
  
 <span data-ttu-id="06253-120">4</span><span class="sxs-lookup"><span data-stu-id="06253-120">4</span></span>  
 <span data-ttu-id="06253-121">En ejecución.</span><span class="sxs-lookup"><span data-stu-id="06253-121">Running.</span></span> <span data-ttu-id="06253-122">El servicio está ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="06253-122">The service is running.</span></span>  
  
 <span data-ttu-id="06253-123">5</span><span class="sxs-lookup"><span data-stu-id="06253-123">5</span></span>  
 <span data-ttu-id="06253-124">Continuación pendiente.</span><span class="sxs-lookup"><span data-stu-id="06253-124">Continue Pending.</span></span> <span data-ttu-id="06253-125">El servicio está a la espera de continuar.</span><span class="sxs-lookup"><span data-stu-id="06253-125">The service is waiting to continue.</span></span>  
  
 <span data-ttu-id="06253-126">6</span><span class="sxs-lookup"><span data-stu-id="06253-126">6</span></span>  
 <span data-ttu-id="06253-127">Pausa pendiente.</span><span class="sxs-lookup"><span data-stu-id="06253-127">Pause Pending.</span></span> <span data-ttu-id="06253-128">El servicio está a la espera de que se ponga en pausa.</span><span class="sxs-lookup"><span data-stu-id="06253-128">The service is waiting to pause.</span></span>  
  
 <span data-ttu-id="06253-129">7</span><span class="sxs-lookup"><span data-stu-id="06253-129">7</span></span>  
 <span data-ttu-id="06253-130">En pausa.</span><span class="sxs-lookup"><span data-stu-id="06253-130">Paused.</span></span> <span data-ttu-id="06253-131">El servicio está en pausa.</span><span class="sxs-lookup"><span data-stu-id="06253-131">The service is paused.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06253-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="06253-132">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06253-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06253-133">See Also</span></span>  
 <span data-ttu-id="06253-134">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="06253-134">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
