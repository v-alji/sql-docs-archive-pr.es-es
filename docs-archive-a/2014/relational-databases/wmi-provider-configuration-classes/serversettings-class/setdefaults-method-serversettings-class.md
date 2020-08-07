---
title: Método SetDefaults (clase ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 76e4cfab-4b15-4da4-bb2f-8aac6f927f79
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 93dd2eee5a395d4d7463ebf9b85530fcf82d1888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745674"
---
# <a name="setdefaults-method-serversettings-class"></a><span data-ttu-id="58348-102">Método SetDefaults (clase ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="58348-102">SetDefaults Method (ServerSettings Class)</span></span>
  <span data-ttu-id="58348-103">Establece todos los valores predeterminados de la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con la opción de sobrescribir los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="58348-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58348-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58348-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="58348-105">Partes</span><span class="sxs-lookup"><span data-stu-id="58348-105">Parts</span></span>  
 <span data-ttu-id="58348-106">*object*</span><span class="sxs-lookup"><span data-stu-id="58348-106">*object*</span></span>  
 <span data-ttu-id="58348-107">Objeto de la [clase ServerSettings](serversettings-class.md) que representa una [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instancia de cliente.</span><span class="sxs-lookup"><span data-stu-id="58348-107">A [ServerSettings Class](serversettings-class.md) object that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="58348-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58348-108">Parameters</span></span>  
  
|<span data-ttu-id="58348-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="58348-109">Parameter</span></span>|<span data-ttu-id="58348-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="58348-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58348-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="58348-111">*OverwriteAll*</span></span>|<span data-ttu-id="58348-112">Valor booleano que especifica si se van a sobrescribir los valores existentes en la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: `true` si se sobrescriben los datos existentes o `false` si no se sobrescriben.</span><span class="sxs-lookup"><span data-stu-id="58348-112">A Boolean value that specifies whether to overwrite existing values on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="58348-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="58348-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="58348-114">Valor u`int32` que es igual a 0 si se modificó el servicio correctamente, igual a 1 si no se admite la solicitud e igual a cualquier otro número para indicar que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="58348-114">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58348-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="58348-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58348-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58348-116">See Also</span></span>  
 <span data-ttu-id="58348-117">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="58348-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
