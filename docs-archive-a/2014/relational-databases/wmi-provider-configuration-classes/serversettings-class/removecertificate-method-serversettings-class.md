---
title: Método RemoveCertificate (clase ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- RemoveCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveCertificate method
ms.assetid: 9ffdbc39-93f5-48fb-859a-86a3ad545827
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 00731fab5c4bdec61848df93829dd5013a7454f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744576"
---
# <a name="removecertificate-method-serversettings-class"></a><span data-ttu-id="07c84-102">Método RemoveCertificate (clase ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="07c84-102">RemoveCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="07c84-103">Quita el certificado de seguridad actual de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07c84-103">Removes the current security certificate from the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07c84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07c84-104">Syntax</span></span>  
  
```  
  
object  
.RemoveCertificate()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="07c84-105">Partes</span><span class="sxs-lookup"><span data-stu-id="07c84-105">Parts</span></span>  
 <span data-ttu-id="07c84-106">*object*</span><span class="sxs-lookup"><span data-stu-id="07c84-106">*object*</span></span>  
 <span data-ttu-id="07c84-107">Objeto de la [clase ServerSettings](serversettings-class.md) que representa la configuración del servidor en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07c84-107">A [ServerSettings Class](serversettings-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="07c84-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="07c84-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="07c84-109">Valor u`int32` que es igual a 0 si se modificó el servicio correctamente, igual a 1 si no se admite la solicitud e igual a cualquier otro número para indicar que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="07c84-109">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07c84-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="07c84-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07c84-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07c84-111">See Also</span></span>  
 <span data-ttu-id="07c84-112">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="07c84-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
