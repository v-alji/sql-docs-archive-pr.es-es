---
title: Método StopService (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StopService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StopService method
ms.assetid: ef8e1856-4930-417a-8f52-be470fd3f15c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 534db69b9c5474638ef5e893847f7d6b9bbb645d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746812"
---
# <a name="stopservice-method-sqlservice-class"></a><span data-ttu-id="1502f-102">Método StopService (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="1502f-102">StopService Method (SqlService Class)</span></span>
  <span data-ttu-id="1502f-103">Intenta poner el servicio en estado de detención.</span><span class="sxs-lookup"><span data-stu-id="1502f-103">Attempts to place the service in the stopped state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1502f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1502f-104">Syntax</span></span>  
  
```  
  
object  
.StopService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="1502f-105">Partes</span><span class="sxs-lookup"><span data-stu-id="1502f-105">Parts</span></span>  
 <span data-ttu-id="1502f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="1502f-106">*object*</span></span>  
 <span data-ttu-id="1502f-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="1502f-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1502f-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1502f-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="1502f-109">Valor de `uint32` que es igual a 0 si se aceptó la solicitud de `ResumeService`, igual a 1 si no se admite dicha solicitud e igual a cualquier otro número para indicar que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="1502f-109">A `uint32` value, which is 0 if the `ResumeService` request was accepted, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1502f-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1502f-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1502f-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1502f-111">See Also</span></span>  
 <span data-ttu-id="1502f-112">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1502f-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
