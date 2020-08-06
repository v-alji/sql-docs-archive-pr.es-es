---
title: Propiedad ErrorControl (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ErrorControl Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ErrorControl property
ms.assetid: cbb1e0fa-5bfc-4b1b-a6ed-f7d5cfad4d73
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 73c726af514f2880484cf927282fc0e007f07e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748698"
---
# <a name="errorcontrol-property-sqlservice-class"></a><span data-ttu-id="338d5-102">Propiedad ErrorControl (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="338d5-102">ErrorControl Property (SqlService Class)</span></span>
  <span data-ttu-id="338d5-103">Obtiene o establece la gravedad del error si el servicio no se puede iniciar durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="338d5-103">Gets or sets the severity of the error if the service fails to start during startup.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="338d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="338d5-104">Syntax</span></span>  
  
```  
  
object  
.ErrorControl [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="338d5-105">Partes</span><span class="sxs-lookup"><span data-stu-id="338d5-105">Parts</span></span>  
 <span data-ttu-id="338d5-106">*object*</span><span class="sxs-lookup"><span data-stu-id="338d5-106">*object*</span></span>  
 <span data-ttu-id="338d5-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="338d5-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="338d5-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="338d5-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="338d5-109">Valor de cadena que especifica la gravedad del error notificado si se produce un error en el servicio durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="338d5-109">A string value that specifies the error severity reported if the service fails during startup.</span></span> <span data-ttu-id="338d5-110">En la siguiente tabla se muestran los valores posibles.</span><span class="sxs-lookup"><span data-stu-id="338d5-110">The following table shows the possible values.</span></span>  
  
 <span data-ttu-id="338d5-111">Ignorar</span><span class="sxs-lookup"><span data-stu-id="338d5-111">Ignore</span></span>  
 <span data-ttu-id="338d5-112">No se notifica al usuario.</span><span class="sxs-lookup"><span data-stu-id="338d5-112">User is not notified.</span></span>  
  
 <span data-ttu-id="338d5-113">Normal</span><span class="sxs-lookup"><span data-stu-id="338d5-113">Normal</span></span>  
 <span data-ttu-id="338d5-114">Se notifica al usuario.</span><span class="sxs-lookup"><span data-stu-id="338d5-114">User is notified.</span></span>  
  
 <span data-ttu-id="338d5-115">Grave</span><span class="sxs-lookup"><span data-stu-id="338d5-115">Severe</span></span>  
 <span data-ttu-id="338d5-116">El sistema se reinicia con la última configuración válida conocida.</span><span class="sxs-lookup"><span data-stu-id="338d5-116">System is restarted with the last-known-good configuration.</span></span>  
  
 <span data-ttu-id="338d5-117">Crítica</span><span class="sxs-lookup"><span data-stu-id="338d5-117">Critical</span></span>  
 <span data-ttu-id="338d5-118">El sistema intenta reiniciarse con una configuración válida.</span><span class="sxs-lookup"><span data-stu-id="338d5-118">System attempts to restart with a good configuration.</span></span>  
  
 <span data-ttu-id="338d5-119">Desconocido</span><span class="sxs-lookup"><span data-stu-id="338d5-119">Unknown</span></span>  
 <span data-ttu-id="338d5-120">Se desconoce la gravedad.</span><span class="sxs-lookup"><span data-stu-id="338d5-120">The severity is unknown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="338d5-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="338d5-121">Remarks</span></span>  
 <span data-ttu-id="338d5-122">El valor indica la acción realizada por el programa de inicio si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="338d5-122">The value indicates the action taken by the startup program if a failure occurs.</span></span> <span data-ttu-id="338d5-123">El sistema registra todos los errores.</span><span class="sxs-lookup"><span data-stu-id="338d5-123">All errors are logged by the computer system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338d5-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="338d5-124">See Also</span></span>  
 <span data-ttu-id="338d5-125">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="338d5-125">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
