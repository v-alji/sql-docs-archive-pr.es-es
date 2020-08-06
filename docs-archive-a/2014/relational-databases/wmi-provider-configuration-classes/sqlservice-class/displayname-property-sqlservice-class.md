---
title: Propiedad DisplayName (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- DisplayName Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- DisplayName property
ms.assetid: 49c408aa-6eb4-45cd-8d5c-60f065f24f5c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 147fc298d6d263caf1e4ad6852d4b02f86911572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748700"
---
# <a name="displayname-property-sqlservice-class"></a><span data-ttu-id="f8408-102">Propiedad DisplayName (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="f8408-102">DisplayName Property (SqlService Class)</span></span>
  <span data-ttu-id="f8408-103">Obtiene el nombre para mostrar del servicio.</span><span class="sxs-lookup"><span data-stu-id="f8408-103">Gets the display name of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8408-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8408-104">Syntax</span></span>  
  
```  
  
object  
.DisplayName [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="f8408-105">Partes</span><span class="sxs-lookup"><span data-stu-id="f8408-105">Parts</span></span>  
 <span data-ttu-id="f8408-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f8408-106">*object*</span></span>  
 <span data-ttu-id="f8408-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="f8408-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f8408-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f8408-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f8408-109">Valor de cadena que especifica el nombre para mostrar del servicio.</span><span class="sxs-lookup"><span data-stu-id="f8408-109">A string value that specifies the display name of the service.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8408-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f8408-110">Remarks</span></span>  
 <span data-ttu-id="f8408-111">Esta cadena tiene una longitud máxima de 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f8408-111">This string has a maximum length of 256 characters.</span></span> <span data-ttu-id="f8408-112">Se conserva el uso de mayúsculas y minúsculas del nombre en el Administrador de configuración de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8408-112">The name is case-preserved in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="f8408-113">Sin embargo, las comparaciones de nombres para mostrar siempre se realizan sin distinción entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f8408-113">However, display name comparisons are always case-insensitive.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8408-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8408-114">Example</span></span>  
  
```  
mysqlservice.DisplayName = "Atdisk"  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8408-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8408-115">See Also</span></span>  
 <span data-ttu-id="f8408-116">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f8408-116">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
