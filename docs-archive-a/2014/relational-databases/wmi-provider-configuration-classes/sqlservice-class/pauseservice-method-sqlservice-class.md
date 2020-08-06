---
title: Método PauseService (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PauseService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PauseService method
ms.assetid: 5c3a8feb-58b8-4385-b4c8-bf33cf4d276d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8286e123bbbc279ba461336c5716eeb208c5b238
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672837"
---
# <a name="pauseservice-method-sqlservice-class"></a><span data-ttu-id="415d3-102">Método PauseService (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="415d3-102">PauseService Method (SqlService Class)</span></span>
  <span data-ttu-id="415d3-103">Intenta poner el servicio en estado de pausa.</span><span class="sxs-lookup"><span data-stu-id="415d3-103">Attempts to place the service in the paused state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="415d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="415d3-104">Syntax</span></span>  
  
```  
  
object  
.PauseService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="415d3-105">Partes</span><span class="sxs-lookup"><span data-stu-id="415d3-105">Parts</span></span>  
 <span data-ttu-id="415d3-106">*object*</span><span class="sxs-lookup"><span data-stu-id="415d3-106">*object*</span></span>  
 <span data-ttu-id="415d3-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="415d3-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="415d3-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="415d3-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="415d3-109">Valor unit32 que es igual a 0 si se detuvo el servicio correctamente, igual a 1 si no se admite la solicitud e igual a cualquier otro número para indicar que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="415d3-109">A uint32 value, which is 0 if the service was successfully stopped, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="415d3-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="415d3-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="415d3-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="415d3-111">See Also</span></span>  
 <span data-ttu-id="415d3-112">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="415d3-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
