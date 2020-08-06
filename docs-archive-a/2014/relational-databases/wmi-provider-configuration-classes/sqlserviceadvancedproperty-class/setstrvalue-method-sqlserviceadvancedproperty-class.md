---
title: Método SetStrValue (clase SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 1fededc3-81ba-4b08-83f9-189b96140799
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d977eb9845c820c4128d1d60337151eeb3893eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746802"
---
# <a name="setstrvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="62486-102">Método SetStrValue (clase SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="62486-102">SetStrValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="62486-103">Establece el valor de cadena de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="62486-103">Sets the string value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62486-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62486-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="62486-105">Partes</span><span class="sxs-lookup"><span data-stu-id="62486-105">Parts</span></span>  
 <span data-ttu-id="62486-106">*object*</span><span class="sxs-lookup"><span data-stu-id="62486-106">*object*</span></span>  
 <span data-ttu-id="62486-107">Objeto de la [clase SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) que representa una propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="62486-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="62486-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62486-108">Parameters</span></span>  
  
|<span data-ttu-id="62486-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="62486-109">Parameter</span></span>|<span data-ttu-id="62486-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="62486-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62486-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="62486-111">*StrValue*</span></span>|<span data-ttu-id="62486-112">Valor de cadena que especifica el valor de la propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="62486-112">A string value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="62486-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="62486-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="62486-114">Valor unit 32 que es igual a 0 si se modificó el servicio correctamente, igual a 1 si no se admite la solicitud e igual a cualquier otro número para indicar que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="62486-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62486-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="62486-115">Remarks</span></span>  
 <span data-ttu-id="62486-116">El tipo de valor de la propiedad debe ser *string* para establecer la propiedad en un valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="62486-116">The property value type must be *string* to set the property to a string value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62486-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62486-117">See Also</span></span>  
 <span data-ttu-id="62486-118">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="62486-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
