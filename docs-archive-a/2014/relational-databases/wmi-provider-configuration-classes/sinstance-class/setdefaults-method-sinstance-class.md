---
title: Método SetDefaults (clase SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: dc3c6a85-0711-4688-bf4f-91168c57af28
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: c581834d3c97bed622d16fbb35e48704f8679531
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744573"
---
# <a name="setdefaults-method-sinstance-class"></a><span data-ttu-id="ec1e9-102">Método SetDefaults (clase SInstance)</span><span class="sxs-lookup"><span data-stu-id="ec1e9-102">SetDefaults Method (SInstance Class)</span></span>
  <span data-ttu-id="ec1e9-103">Establece todos los valores predeterminados de la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con la opción de sobrescribir los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="ec1e9-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec1e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec1e9-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ec1e9-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ec1e9-105">Parts</span></span>  
 <span data-ttu-id="ec1e9-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ec1e9-106">*object*</span></span>  
 <span data-ttu-id="ec1e9-107">Objeto de la [clase SInstance](sinstance-class.md) que representa una instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="ec1e9-107">An [SInstance Class](sinstance-class.md) object that represents a server instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ec1e9-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec1e9-108">Parameters</span></span>  
  
|<span data-ttu-id="ec1e9-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="ec1e9-109">Parameter</span></span>|<span data-ttu-id="ec1e9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec1e9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec1e9-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="ec1e9-111">*OverwriteAll*</span></span>|<span data-ttu-id="ec1e9-112">Valor booleano que especifica si se va a sobrescribir el valor existente en la instancia del cliente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: `true` si se sobrescriben los datos existentes o `false` si no se sobrescriben.</span><span class="sxs-lookup"><span data-stu-id="ec1e9-112">A Boolean value that specifies whether to overwrite existing value on the instance of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client: `true` if existing data is overwritten, or `false` if existing data is not overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ec1e9-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ec1e9-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="ec1e9-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="ec1e9-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec1e9-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec1e9-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec1e9-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec1e9-116">See Also</span></span>  
 <span data-ttu-id="ec1e9-117">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ec1e9-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
