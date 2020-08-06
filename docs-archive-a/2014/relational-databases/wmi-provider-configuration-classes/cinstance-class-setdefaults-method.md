---
title: Método SetDefaults (clase CInstance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (CInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: ed9e99c2-3e28-4ee8-bc20-61ca05984973
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5e589796f973592d7f9f549bffbbf8dfbe49cc27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661847"
---
# <a name="setdefaults-method-cinstance-class"></a><span data-ttu-id="1b9a1-102">Método SetDefaults (clase CInstance)</span><span class="sxs-lookup"><span data-stu-id="1b9a1-102">SetDefaults Method (CInstance Class)</span></span>
  <span data-ttu-id="1b9a1-103">Establece todos los valores predeterminados para la instancia del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cliente con la opción de sobrescribir los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="1b9a1-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b9a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b9a1-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="1b9a1-105">Partes</span><span class="sxs-lookup"><span data-stu-id="1b9a1-105">Parts</span></span>  
 <span data-ttu-id="1b9a1-106">*object*</span><span class="sxs-lookup"><span data-stu-id="1b9a1-106">*object*</span></span>  
 <span data-ttu-id="1b9a1-107">Objeto de la [clase CInstance](cinstance-class.md) que representa una instancia del cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b9a1-107">A [CInstance Class](cinstance-class.md) object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="1b9a1-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b9a1-108">Parameters</span></span>  
  
|<span data-ttu-id="1b9a1-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1b9a1-109">Parameter</span></span>|<span data-ttu-id="1b9a1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b9a1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b9a1-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="1b9a1-111">*OverwriteAll*</span></span>|<span data-ttu-id="1b9a1-112">Valor booleano que especifica si se van a sobrescribir los valores existentes en la instancia del cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: `true` para sobrescribir los datos existentes o `false` para no sobrescribirlos.</span><span class="sxs-lookup"><span data-stu-id="1b9a1-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1b9a1-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1b9a1-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="1b9a1-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="1b9a1-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b9a1-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1b9a1-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b9a1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b9a1-116">See Also</span></span>  
 [<span data-ttu-id="1b9a1-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="1b9a1-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
