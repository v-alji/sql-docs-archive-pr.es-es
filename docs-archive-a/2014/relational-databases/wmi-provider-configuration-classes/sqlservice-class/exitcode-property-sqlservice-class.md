---
title: Propiedad ExitCode (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ExitCode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ExitCode property
ms.assetid: e6b8bff2-946f-4abe-bd50-1f7bb11fdddf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f7f5414afd8507a1fc9c592d6b8226692e9683a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670874"
---
# <a name="exitcode-property-sqlservice-class"></a><span data-ttu-id="526eb-102">Propiedad ExitCode (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="526eb-102">ExitCode Property (SqlService Class)</span></span>
  <span data-ttu-id="526eb-103">Obtiene o establece el código de error de Win32 de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] que define los problemas encontrados al iniciar y detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="526eb-103">Gets or sets the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 error code that defines problems encountered when starting and stopping the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="526eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="526eb-104">Syntax</span></span>  
  
```  
  
object  
.ExitCode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="526eb-105">Partes</span><span class="sxs-lookup"><span data-stu-id="526eb-105">Parts</span></span>  
 <span data-ttu-id="526eb-106">*object*</span><span class="sxs-lookup"><span data-stu-id="526eb-106">*object*</span></span>  
 <span data-ttu-id="526eb-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="526eb-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="526eb-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="526eb-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="526eb-109">Valor de `uint32` que especifica el código de salida.</span><span class="sxs-lookup"><span data-stu-id="526eb-109">A `uint32` value that specifies the exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="526eb-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="526eb-110">Remarks</span></span>  
 <span data-ttu-id="526eb-111">Esta propiedad se establece en ERROR_SERVICE_SPECIFIC_ERROR (1066) si el error es exclusivo del servicio representado por esta clase.</span><span class="sxs-lookup"><span data-stu-id="526eb-111">This property is set to ERROR_SERVICE_SPECIFIC_ERROR (1066) when the error is unique to the service represented by this class.</span></span> <span data-ttu-id="526eb-112">El servicio establece este valor en NO_ERROR cuando se ejecuta y también cuando finaliza normalmente.</span><span class="sxs-lookup"><span data-stu-id="526eb-112">The service sets this value to NO_ERROR when running, and again upon normal termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="526eb-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="526eb-113">See Also</span></span>  
 <span data-ttu-id="526eb-114">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="526eb-114">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
