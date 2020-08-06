---
title: Método SetServiceAccount (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccount Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccount method
ms.assetid: d5782892-e9d8-4d48-92af-b3afe9610f84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6087a531802a7752ea794a44147c79fb7c3fa3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744554"
---
# <a name="setserviceaccount-method-sqlservice-class"></a><span data-ttu-id="f0f73-102">Método SetServiceAccount (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="f0f73-102">SetServiceAccount Method (SqlService Class)</span></span>
  <span data-ttu-id="f0f73-103">Intenta cambiar el nombre de usuario y la contraseña con los que se ejecuta la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="f0f73-103">Attempts to change the user name and password that the service instance runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f73-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0f73-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccount(  
ServiceStartName , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f0f73-105">Partes</span><span class="sxs-lookup"><span data-stu-id="f0f73-105">Parts</span></span>  
 <span data-ttu-id="f0f73-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f0f73-106">*object*</span></span>  
 <span data-ttu-id="f0f73-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="f0f73-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="f0f73-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0f73-108">Parameters</span></span>  
 <span data-ttu-id="f0f73-109">*ServiceStartName*</span><span class="sxs-lookup"><span data-stu-id="f0f73-109">*ServiceStartName*</span></span>  
 <span data-ttu-id="f0f73-110">Valor de cadena que especifica el nombre de la cuenta en la que se ejecuta el servicio.</span><span class="sxs-lookup"><span data-stu-id="f0f73-110">A string value that specifies the account name that the service runs under.</span></span> <span data-ttu-id="f0f73-111">Según el tipo de servicio, el nombre de cuenta puede tener la forma NombreDominio\NombreUsuario.</span><span class="sxs-lookup"><span data-stu-id="f0f73-111">Depending on the service type, the account name might be in the form of DomainName\Username.</span></span> <span data-ttu-id="f0f73-112">El proceso del servicio se registrará con uno de estos dos formatos cuando se ejecute:</span><span class="sxs-lookup"><span data-stu-id="f0f73-112">When it runs, the service process will be logged using one of two forms:</span></span>  
  
-   <span data-ttu-id="f0f73-113">Si la cuenta pertenece al dominio integrado, puede especificarse \NombreUsuario.</span><span class="sxs-lookup"><span data-stu-id="f0f73-113">If the account belongs to the built-in domain, \Username can be specified.</span></span>  
  
-   <span data-ttu-id="f0f73-114">Si se especifica NULL, el servicio se iniciará sesión como la cuenta **LocalSystem** .</span><span class="sxs-lookup"><span data-stu-id="f0f73-114">If NULL is specified, the service will be logged on as the **LocalSystem** account.</span></span>  
  
 <span data-ttu-id="f0f73-115">En el caso de los controladores de kernel o de nivel de sistema, *StartName* contiene el nombre de objeto del controlador, ya sea \FileSystem\Rdr o \Driver\Xns, que el sistema de e/s utiliza para cargar el controlador de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f0f73-115">For kernel or system-level drivers, *StartName* contains the driver object name, either \FileSystem\Rdr or \Driver\Xns, which the I/O system uses to load the device driver.</span></span> <span data-ttu-id="f0f73-116">Además, si se especifica NULL, el controlador se ejecutará con un nombre de objeto predeterminado creado por el sistema de E/S basado en el nombre del servicio. Ejemplo: DWDOM\Admin.</span><span class="sxs-lookup"><span data-stu-id="f0f73-116">If NULL is specified, the driver runs with a default object name created by the I/O system based on the service name, for example, DWDOM\Admin.</span></span>  
  
 <span data-ttu-id="f0f73-117">*ServiceStartPassword*</span><span class="sxs-lookup"><span data-stu-id="f0f73-117">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="f0f73-118">Valor de cadena que especifica la contraseña para el nombre de cuenta en el parámetro *StartName* .</span><span class="sxs-lookup"><span data-stu-id="f0f73-118">A string value that specifies the password for the account name in the *StartName* parameter.</span></span> <span data-ttu-id="f0f73-119">Especifique NULL si no va a cambiar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="f0f73-119">Specify NULL if you are not changing the password.</span></span> <span data-ttu-id="f0f73-120">Especifique una cadena vacía si el servicio no tiene contraseña.</span><span class="sxs-lookup"><span data-stu-id="f0f73-120">Specify an empty string if the service has no password.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f0f73-121">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f0f73-121">Property Value/Return Value</span></span>  
 <span data-ttu-id="f0f73-122">Valor de `uint32` que es igual a 0 si se modificó el servicio correctamente o igual a 1 si no se admite la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f0f73-122">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="f0f73-123">Cualquier otro número indica que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="f0f73-123">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0f73-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f0f73-124">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f73-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0f73-125">See Also</span></span>  
 <span data-ttu-id="f0f73-126">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f0f73-126">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
