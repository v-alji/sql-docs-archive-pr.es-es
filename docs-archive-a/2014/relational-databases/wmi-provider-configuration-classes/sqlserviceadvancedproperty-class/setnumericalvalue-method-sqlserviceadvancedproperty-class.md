---
title: Método SetNumericalValue (clase SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: 950ed1e8-0538-4db4-807c-a2c36f43cf6b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: db823938d77f4e2c67284cae0f11faca12aba6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748691"
---
# <a name="setnumericalvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="ddf24-102">Método SetNumericalValue (clase SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="ddf24-102">SetNumericalValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="ddf24-103">Establece el valor numérico de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="ddf24-103">Sets the numeric value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddf24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddf24-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ddf24-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ddf24-105">Parts</span></span>  
 <span data-ttu-id="ddf24-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ddf24-106">*object*</span></span>  
 <span data-ttu-id="ddf24-107">Objeto de la [clase SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) que representa una propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="ddf24-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ddf24-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ddf24-108">Parameters</span></span>  
  
|<span data-ttu-id="ddf24-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="ddf24-109">Parameter</span></span>|<span data-ttu-id="ddf24-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddf24-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ddf24-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="ddf24-111">*NumValue*</span></span>|<span data-ttu-id="ddf24-112">Valor `uint32` que especifica el valor de la propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="ddf24-112">A `uint32` value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ddf24-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ddf24-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="ddf24-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="ddf24-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddf24-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ddf24-115">Remarks</span></span>  
 <span data-ttu-id="ddf24-116">El tipo de valor de propiedad debe ser numérico para poder establecer la propiedad en un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="ddf24-116">The property value type must be numeric to be able to set the property to a numeric value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf24-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddf24-117">See Also</span></span>  
 <span data-ttu-id="ddf24-118">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ddf24-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
