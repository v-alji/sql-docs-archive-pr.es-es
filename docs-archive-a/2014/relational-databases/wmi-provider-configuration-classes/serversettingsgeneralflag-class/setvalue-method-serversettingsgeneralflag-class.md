---
title: Método SetValue (clase ServerSettingsGeneralFlag) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ServerSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: a889feac-c0e0-4635-b506-843863d86967
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 74c4c189b72b7a469794e0828faf062a88cdf46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752026"
---
# <a name="setvalue-method-serversettingsgeneralflag-class"></a><span data-ttu-id="733cd-102">Método SetValue (clase ServerSettingsGeneralFlag)</span><span class="sxs-lookup"><span data-stu-id="733cd-102">SetValue Method (ServerSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="733cd-103">Establece todos los valores de la marca a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="733cd-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="733cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="733cd-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="733cd-105">Partes</span><span class="sxs-lookup"><span data-stu-id="733cd-105">Parts</span></span>  
 <span data-ttu-id="733cd-106">*object*</span><span class="sxs-lookup"><span data-stu-id="733cd-106">*object*</span></span>  
 <span data-ttu-id="733cd-107">Objeto de la [clase ServerSettingsGeneralFlag](serversettingsgeneralflag-class.md) que representa una marca general para la configuración del servidor.</span><span class="sxs-lookup"><span data-stu-id="733cd-107">A [ServerSettingsGeneralFlag Class](serversettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="733cd-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="733cd-108">Parameters</span></span>  
  
|<span data-ttu-id="733cd-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="733cd-109">Parameter</span></span>|<span data-ttu-id="733cd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="733cd-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="733cd-111">*Valor*</span><span class="sxs-lookup"><span data-stu-id="733cd-111">*Value*</span></span>|<span data-ttu-id="733cd-112">Valor booleano que especifica el valor de la marca.</span><span class="sxs-lookup"><span data-stu-id="733cd-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="733cd-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="733cd-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="733cd-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="733cd-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="733cd-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="733cd-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="733cd-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="733cd-116">See Also</span></span>  
 <span data-ttu-id="733cd-117">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="733cd-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
