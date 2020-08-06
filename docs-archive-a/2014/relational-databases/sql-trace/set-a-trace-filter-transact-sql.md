---
title: Método SetBoolValue (clase SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SetBoolValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetBoolValue method
ms.assetid: 5252b439-fce5-446a-8e57-99e3054bee69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0c7142d6f192e94e9850b3c1a8a9481dc15a222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745102"
---
# <a name="setboolvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="9d4c0-102">Método SetBoolValue (clase SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="9d4c0-102">SetBoolValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="9d4c0-103">Establece el valor booleano de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="9d4c0-103">Sets the Boolean value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d4c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d4c0-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="9d4c0-105">Partes</span><span class="sxs-lookup"><span data-stu-id="9d4c0-105">Parts</span></span>  
 <span data-ttu-id="9d4c0-106">*object*</span><span class="sxs-lookup"><span data-stu-id="9d4c0-106">*object*</span></span>  
 <span data-ttu-id="9d4c0-107">Objeto de la [clase SqlServiceAdvancedProperty](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) que representa una propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="9d4c0-107">A [SqlServiceAdvancedProperty Class](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="9d4c0-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d4c0-108">Parameters</span></span>  
  
|<span data-ttu-id="9d4c0-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9d4c0-109">Parameter</span></span>|<span data-ttu-id="9d4c0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d4c0-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d4c0-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="9d4c0-111">*BoolValue*</span></span>|<span data-ttu-id="9d4c0-112">Valor booleano que especifica el valor de la propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="9d4c0-112">A Boolean value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9d4c0-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9d4c0-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="9d4c0-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="9d4c0-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d4c0-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9d4c0-115">Remarks</span></span>  
 <span data-ttu-id="9d4c0-116">El tipo de valor de la propiedad debe ser booleano para establecer la propiedad en un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="9d4c0-116">The property value type must be Boolean to set the property to a Boolean value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d4c0-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d4c0-117">See Also</span></span>  
 <span data-ttu-id="9d4c0-118">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9d4c0-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
