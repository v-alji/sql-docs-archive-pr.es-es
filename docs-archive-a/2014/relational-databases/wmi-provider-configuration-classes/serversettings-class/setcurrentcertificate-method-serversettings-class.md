---
title: Método SetCurrentCertificate (clase ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: f9c6e172-11be-42de-b19b-a5b3436e84da
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 7071937a7d7e601597fe008187448bb16a5a15ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745676"
---
# <a name="setcurrentcertificate-method-serversettings-class"></a><span data-ttu-id="66a45-102">Método SetCurrentCertificate (clase ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="66a45-102">SetCurrentCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="66a45-103">Establece el certificado de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="66a45-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66a45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66a45-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="66a45-105">Partes</span><span class="sxs-lookup"><span data-stu-id="66a45-105">Parts</span></span>  
 <span data-ttu-id="66a45-106">*object*</span><span class="sxs-lookup"><span data-stu-id="66a45-106">*object*</span></span>  
 <span data-ttu-id="66a45-107">Objeto [ServerSettings Class] ServerSettings-class.md) que representa la configuración del servidor en una instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66a45-107">A [ServerSettings Class]serversettings-class.md) object that represents the server setting on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="66a45-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66a45-108">Parameters</span></span>  
  
|<span data-ttu-id="66a45-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="66a45-109">Parameter</span></span>|<span data-ttu-id="66a45-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="66a45-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66a45-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="66a45-111">*SHA*</span></span>|<span data-ttu-id="66a45-112">Valor de cadena que especifica el certificado de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="66a45-112">A string value that specifies the current security certificate.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="66a45-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="66a45-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="66a45-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="66a45-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66a45-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="66a45-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a45-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66a45-116">See Also</span></span>  
 <span data-ttu-id="66a45-117">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="66a45-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
