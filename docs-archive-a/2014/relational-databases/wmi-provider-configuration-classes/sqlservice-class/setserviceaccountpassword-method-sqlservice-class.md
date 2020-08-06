---
title: Método SetServiceAccountPassword (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccountPassword Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccountPassword method
ms.assetid: e577a1ac-985c-4799-bb38-9393efc3def2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e7a83a6d3686b2ec2df98ae79b4c9d3347f621ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744555"
---
# <a name="setserviceaccountpassword-method-sqlservice-class"></a><span data-ttu-id="ccbcb-102">Método SetServiceAccountPassword (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="ccbcb-102">SetServiceAccountPassword Method (SqlService Class)</span></span>
  <span data-ttu-id="ccbcb-103">Modifica la contraseña de la cuenta en la que se ejecuta el servicio al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-103">Modifies the password for the account that the referenced service runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccbcb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccbcb-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccountPassword(  
AccountOldPassword , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ccbcb-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ccbcb-105">Parts</span></span>  
 <span data-ttu-id="ccbcb-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-106">*object*</span></span>  
 <span data-ttu-id="ccbcb-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ccbcb-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccbcb-108">Parameters</span></span>  
 <span data-ttu-id="ccbcb-109">*AccountOldPassword*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-109">*AccountOldPassword*</span></span>  
 <span data-ttu-id="ccbcb-110">Valor de cadena que especifica la contraseña existente para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-110">A string value that specifies the existing password for the account.</span></span>  
  
 <span data-ttu-id="ccbcb-111">*ServiceStartPassword*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-111">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="ccbcb-112">Valor de cadena que especifica la nueva contraseña para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-112">A string value that specifies the new password for the account.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ccbcb-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ccbcb-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="ccbcb-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccbcb-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ccbcb-115">Remarks</span></span>  
  
