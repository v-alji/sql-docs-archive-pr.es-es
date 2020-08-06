---
title: Método SetNumValue (clase SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumValue method
ms.assetid: a5e1056b-0b75-4ad6-99c1-89246010d815
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 01388855a27dcf14754f677a42c13f8d29cbaacc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746805"
---
# <a name="setnumvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="4bc31-102">Método SetNumValue (clase SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="4bc31-102">SetNumValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="4bc31-103">Establece el valor numérico de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="4bc31-103">Sets the numeric value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bc31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bc31-104">Syntax</span></span>  
  
```  
  
object  
.SetNumValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="4bc31-105">Partes</span><span class="sxs-lookup"><span data-stu-id="4bc31-105">Parts</span></span>  
 <span data-ttu-id="4bc31-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4bc31-106">*object*</span></span>  
 <span data-ttu-id="4bc31-107">Objeto de la [clase SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) que representa una propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="4bc31-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="4bc31-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4bc31-108">Parameters</span></span>  
  
|<span data-ttu-id="4bc31-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="4bc31-109">Parameter</span></span>|<span data-ttu-id="4bc31-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bc31-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4bc31-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="4bc31-111">*NumValue*</span></span>|<span data-ttu-id="4bc31-112">Valor `uint32` que especifica el valor de la propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="4bc31-112">A `uint32` value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4bc31-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4bc31-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="4bc31-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="4bc31-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bc31-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4bc31-115">Remarks</span></span>  
 <span data-ttu-id="4bc31-116">El tipo de valor de propiedad debe ser numérico para poder establecer la propiedad en un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="4bc31-116">The property value type must be numeric to be able to set the property to a numeric value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc31-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4bc31-117">See Also</span></span>  
 <span data-ttu-id="4bc31-118">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4bc31-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
