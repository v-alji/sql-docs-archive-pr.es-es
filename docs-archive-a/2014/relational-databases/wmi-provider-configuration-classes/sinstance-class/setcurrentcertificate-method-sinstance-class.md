---
title: Método SetCurrentCertificate (clase SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 7349fb87-b973-4160-a2be-cab73abf5b31
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 44e65ab30659cacca09e63a94a1f3596a182dda5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744575"
---
# <a name="setcurrentcertificate-method-sinstance-class"></a><span data-ttu-id="96a49-102">Método SetCurrentCertificate (clase SInstance)</span><span class="sxs-lookup"><span data-stu-id="96a49-102">SetCurrentCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="96a49-103">Establece el certificado de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="96a49-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96a49-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96a49-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="96a49-105">Partes</span><span class="sxs-lookup"><span data-stu-id="96a49-105">Parts</span></span>  
 <span data-ttu-id="96a49-106">*object*</span><span class="sxs-lookup"><span data-stu-id="96a49-106">*object*</span></span>  
 <span data-ttu-id="96a49-107">Objeto de la [clase SInstance](sinstance-class.md) que representa la configuración del servidor en una instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96a49-107">An [SInstance Class](sinstance-class.md) object that represents the server setting on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="96a49-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96a49-108">Parameters</span></span>  
  
|<span data-ttu-id="96a49-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="96a49-109">Parameter</span></span>|<span data-ttu-id="96a49-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="96a49-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="96a49-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="96a49-111">*SHA*</span></span>|<span data-ttu-id="96a49-112">Valor de cadena que especifica el certificado de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="96a49-112">A string value that specifies the current security certificate.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="96a49-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="96a49-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="96a49-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="96a49-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96a49-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="96a49-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a49-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96a49-116">See Also</span></span>  
 <span data-ttu-id="96a49-117">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="96a49-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
