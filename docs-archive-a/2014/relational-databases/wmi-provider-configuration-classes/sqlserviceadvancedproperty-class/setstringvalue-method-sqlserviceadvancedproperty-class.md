---
title: Método SetStringValue (clase SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (SqlServiceAdvancedProperty Class )
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: a02d05f6-1072-4709-9ecc-e23e51c8c898
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d7939c6af677ac77b9d8005571406315905bfd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746804"
---
# <a name="setstringvalue-method-sqlserviceadvancedproperty-class-"></a><span data-ttu-id="2f7a8-102">Método SetStringValue (clase SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="2f7a8-102">SetStringValue Method (SqlServiceAdvancedProperty Class )</span></span>
  <span data-ttu-id="2f7a8-103">Establece el valor de cadena de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="2f7a8-103">Sets the string value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f7a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f7a8-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="2f7a8-105">Partes</span><span class="sxs-lookup"><span data-stu-id="2f7a8-105">Parts</span></span>  
 <span data-ttu-id="2f7a8-106">*object*</span><span class="sxs-lookup"><span data-stu-id="2f7a8-106">*object*</span></span>  
 <span data-ttu-id="2f7a8-107">Objeto de la [clase SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) que representa una propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="2f7a8-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2f7a8-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2f7a8-108">Parameters</span></span>  
  
|<span data-ttu-id="2f7a8-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="2f7a8-109">Parameter</span></span>|<span data-ttu-id="2f7a8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f7a8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f7a8-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="2f7a8-111">*StrValue*</span></span>|<span data-ttu-id="2f7a8-112">Valor de cadena que especifica el valor de la propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="2f7a8-112">A string value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2f7a8-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2f7a8-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="2f7a8-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="2f7a8-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f7a8-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2f7a8-115">Remarks</span></span>  
 <span data-ttu-id="2f7a8-116">El tipo de valor de la propiedad debe ser `string` para establecer la propiedad en un valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="2f7a8-116">The property value type must be `string` to be able to set the property to a string value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f7a8-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f7a8-117">See Also</span></span>  
 <span data-ttu-id="2f7a8-118">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2f7a8-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
