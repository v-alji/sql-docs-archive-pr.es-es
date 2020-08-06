---
title: Método RemoveCertificate (clase SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- RemoveCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveCertificate method
ms.assetid: 7e5dbafa-a634-4617-9622-510514fce0ce
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4b876cd75778d1da9c9a46f65f39b915ebee0552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744574"
---
# <a name="removecertificate-method-sinstance-class"></a><span data-ttu-id="846f4-102">Método RemoveCertificate (clase SInstance)</span><span class="sxs-lookup"><span data-stu-id="846f4-102">RemoveCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="846f4-103">Quita el certificado de seguridad actual de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="846f4-103">Removes the current security certificate from the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="846f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="846f4-104">Syntax</span></span>  
  
```  
  
object  
.RemoveCertificate()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="846f4-105">Partes</span><span class="sxs-lookup"><span data-stu-id="846f4-105">Parts</span></span>  
 <span data-ttu-id="846f4-106">*object*</span><span class="sxs-lookup"><span data-stu-id="846f4-106">*object*</span></span>  
 <span data-ttu-id="846f4-107">Objeto de la [clase SInstance](sinstance-class.md) que representa la configuración del servidor en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="846f4-107">An [SInstance Class](sinstance-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="846f4-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="846f4-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="846f4-109">Valor unit 32 que es igual a 0 si se modificó el servicio correctamente, igual a 1 si no se admite la solicitud e igual a cualquier otro número para indicar que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="846f4-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="846f4-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="846f4-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="846f4-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="846f4-111">See Also</span></span>  
 <span data-ttu-id="846f4-112">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="846f4-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
