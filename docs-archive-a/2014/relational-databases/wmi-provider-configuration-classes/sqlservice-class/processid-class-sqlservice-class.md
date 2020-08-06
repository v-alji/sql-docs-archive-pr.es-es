---
title: Clase ProcessId (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ProcessId Class (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProcessId property
ms.assetid: 99b5a2e9-b44a-48a0-993e-04bd15c7fef4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 7c4c40eea826b5009e52d26b1d930eaf5febbcdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672836"
---
# <a name="processid-class-sqlservice-class"></a><span data-ttu-id="925bf-102">Clase ProcessId (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="925bf-102">ProcessId Class (SqlService Class)</span></span>
  <span data-ttu-id="925bf-103">Obtiene el id. del proceso del sistema que identifica un servicio de forma inequívoca.</span><span class="sxs-lookup"><span data-stu-id="925bf-103">Gets the system process ID that uniquely identifies a service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="925bf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="925bf-104">Syntax</span></span>  
  
```  
  
object  
.ProcessId [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="925bf-105">Partes</span><span class="sxs-lookup"><span data-stu-id="925bf-105">Parts</span></span>  
 <span data-ttu-id="925bf-106">*object*</span><span class="sxs-lookup"><span data-stu-id="925bf-106">*object*</span></span>  
 <span data-ttu-id="925bf-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="925bf-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="925bf-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="925bf-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="925bf-109">Valor `uint32` que especifica el id. que identifica el proceso de forma inequívoca.</span><span class="sxs-lookup"><span data-stu-id="925bf-109">A `uint32` value that specifies the ID that uniquely identifies the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="925bf-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="925bf-110">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="925bf-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="925bf-111">Example</span></span>  
  
```  
mysqlservice.ProcessId = 324  
```  
  
## <a name="see-also"></a><span data-ttu-id="925bf-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="925bf-112">See Also</span></span>  
 <span data-ttu-id="925bf-113">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="925bf-113">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
