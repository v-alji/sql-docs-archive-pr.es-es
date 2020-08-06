---
title: Método SetValue (clase ClientSettingsGeneralFlag) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ClientSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: 34443689-a0e0-4668-a811-17532c6fd271
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: fffa44bd8743f96a43ca4d1787d8d2afaad5e6cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744608"
---
# <a name="setvalue-method-clientsettingsgeneralflag-class"></a><span data-ttu-id="9ee67-102">Método SetValue (clase ClientSettingsGeneralFlag)</span><span class="sxs-lookup"><span data-stu-id="9ee67-102">SetValue Method (ClientSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="9ee67-103">Establece todos los valores de la marca a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="9ee67-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ee67-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="9ee67-105">Partes</span><span class="sxs-lookup"><span data-stu-id="9ee67-105">Parts</span></span>  
 <span data-ttu-id="9ee67-106">*object*</span><span class="sxs-lookup"><span data-stu-id="9ee67-106">*object*</span></span>  
 <span data-ttu-id="9ee67-107">Objeto de la [clase ClientSettingsGeneralFlag](clientsettingsgeneralflag-class.md) que representa una marca general para la configuración del servidor.</span><span class="sxs-lookup"><span data-stu-id="9ee67-107">A [ClientSettingsGeneralFlag Class](clientsettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="9ee67-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ee67-108">Parameters</span></span>  
  
|<span data-ttu-id="9ee67-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9ee67-109">Parameter</span></span>|<span data-ttu-id="9ee67-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ee67-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ee67-111">*Valor*</span><span class="sxs-lookup"><span data-stu-id="9ee67-111">*Value*</span></span>|<span data-ttu-id="9ee67-112">Valor booleano que especifica el valor de la marca.</span><span class="sxs-lookup"><span data-stu-id="9ee67-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9ee67-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9ee67-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="9ee67-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="9ee67-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ee67-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9ee67-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee67-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ee67-116">See Also</span></span>  
 [<span data-ttu-id="9ee67-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="9ee67-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
