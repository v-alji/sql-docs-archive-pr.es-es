---
title: Método SetDefaults (clase ClientSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ClientSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 056508f3-a5c8-467c-a196-dc1ef1f5178f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b6985ebfa4a9145dd3474cec31f32cdab9c11cdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676890"
---
# <a name="setdefaults-method-clientsettings-class"></a><span data-ttu-id="b4786-102">Método SetDefaults (clase ClientSettings)</span><span class="sxs-lookup"><span data-stu-id="b4786-102">SetDefaults Method (ClientSettings Class)</span></span>
  <span data-ttu-id="b4786-103">Establece todos los valores predeterminados para la instancia del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cliente con la opción de sobrescribir los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="b4786-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4786-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4786-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="b4786-105">Partes</span><span class="sxs-lookup"><span data-stu-id="b4786-105">Parts</span></span>  
 <span data-ttu-id="b4786-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b4786-106">*object*</span></span>  
 <span data-ttu-id="b4786-107">Objeto `ClientSettings` que representa una instancia del cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4786-107">A `ClientSettings` object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="b4786-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4786-108">Parameters</span></span>  
  
|<span data-ttu-id="b4786-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b4786-109">Parameter</span></span>|<span data-ttu-id="b4786-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4786-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4786-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="b4786-111">*OverwriteAll*</span></span>|<span data-ttu-id="b4786-112">Valor booleano que especifica si se van a sobrescribir los valores existentes en la instancia del cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4786-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client.</span></span> <span data-ttu-id="b4786-113">`true` si se van a sobrescribir los datos existentes; `false` si no se van a sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="b4786-113">`true` to overwrite existing data; `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b4786-114">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4786-114">Property Value/Return Value</span></span>  
 <span data-ttu-id="b4786-115">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="b4786-115">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4786-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b4786-116">Remarks</span></span>  
  
