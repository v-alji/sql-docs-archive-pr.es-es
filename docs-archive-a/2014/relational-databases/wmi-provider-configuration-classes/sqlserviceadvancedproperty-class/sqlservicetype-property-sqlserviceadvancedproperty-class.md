---
title: Propiedad SqlServiceType (clase SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: 20f1663a-9a14-4f14-8c1b-8aa133e272c3
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 774c8599fd21e330fa3228336ab1ed3c73d65c85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677456"
---
# <a name="sqlservicetype-property-sqlserviceadvancedproperty-class"></a><span data-ttu-id="ff5bd-102">Propiedad SqlServiceType (clase SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="ff5bd-102">SqlServiceType Property (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="ff5bd-103">Obtiene el tipo del servicio administrado que está asociado a la propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="ff5bd-103">Gets the type of the managed service associated with the advanced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff5bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff5bd-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ff5bd-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ff5bd-105">Parts</span></span>  
 <span data-ttu-id="ff5bd-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ff5bd-106">*object*</span></span>  
 <span data-ttu-id="ff5bd-107">Objeto de la [clase SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) que representa una propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="ff5bd-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ff5bd-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ff5bd-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="ff5bd-109">Valor uint32 que especifica el tipo de servicio de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff5bd-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff5bd-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ff5bd-110">Remarks</span></span>  
 <span data-ttu-id="ff5bd-111">Los valores devueltos pueden ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff5bd-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="ff5bd-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="ff5bd-112">Type</span></span>|<span data-ttu-id="ff5bd-113">Definición</span><span class="sxs-lookup"><span data-stu-id="ff5bd-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="ff5bd-114">*1*</span><span class="sxs-lookup"><span data-stu-id="ff5bd-114">*1*</span></span>|<span data-ttu-id="ff5bd-115">MSSQLSERVER es el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff5bd-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="ff5bd-116">*2*</span><span class="sxs-lookup"><span data-stu-id="ff5bd-116">*2*</span></span>|<span data-ttu-id="ff5bd-117">SQLSERVERAGENT es el servicio Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff5bd-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="ff5bd-118">*3*</span><span class="sxs-lookup"><span data-stu-id="ff5bd-118">*3*</span></span>|<span data-ttu-id="ff5bd-119">MSFTESQL es el servicio de motor de búsqueda de texto completo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff5bd-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="ff5bd-120">*4*</span><span class="sxs-lookup"><span data-stu-id="ff5bd-120">*4*</span></span>|<span data-ttu-id="ff5bd-121">MsDtsServer es el servicio [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff5bd-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="ff5bd-122">*5*</span><span class="sxs-lookup"><span data-stu-id="ff5bd-122">*5*</span></span>|<span data-ttu-id="ff5bd-123">MSSQLServerOLAPService es el servicio [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff5bd-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="ff5bd-124">*6*</span><span class="sxs-lookup"><span data-stu-id="ff5bd-124">*6*</span></span>|<span data-ttu-id="ff5bd-125">ReportServer es el servicio [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff5bd-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="ff5bd-126">*7*</span><span class="sxs-lookup"><span data-stu-id="ff5bd-126">*7*</span></span>|<span data-ttu-id="ff5bd-127">SQLBrowser es el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="ff5bd-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff5bd-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff5bd-128">See Also</span></span>  
 <span data-ttu-id="ff5bd-129">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ff5bd-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
