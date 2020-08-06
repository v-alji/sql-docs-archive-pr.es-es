---
title: Propiedad SqlServiceType (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: dbff2968-3011-41d6-a141-52d814af0213
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 18e0fc741d19eefbb93dbcb7fb6fd4a221ce86d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746820"
---
# <a name="sqlservicetype-property-sqlservice-class"></a><span data-ttu-id="73ca4-102">Propiedad SqlServiceType (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="73ca4-102">SqlServiceType Property (SqlService Class)</span></span>
  <span data-ttu-id="73ca4-103">Obtiene el tipo del servicio administrado.</span><span class="sxs-lookup"><span data-stu-id="73ca4-103">Gets the type of the managed service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73ca4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73ca4-104">Syntax</span></span>  
  
```  
  
object  
.SqlServiceType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="73ca4-105">Partes</span><span class="sxs-lookup"><span data-stu-id="73ca4-105">Parts</span></span>  
 <span data-ttu-id="73ca4-106">*object*</span><span class="sxs-lookup"><span data-stu-id="73ca4-106">*object*</span></span>  
 <span data-ttu-id="73ca4-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="73ca4-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="73ca4-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="73ca4-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="73ca4-109">Valor de uint32 que especifica el tipo de servicio de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73ca4-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73ca4-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73ca4-110">Remarks</span></span>  
 <span data-ttu-id="73ca4-111">Los valores devueltos pueden ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="73ca4-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="73ca4-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="73ca4-112">Type</span></span>|<span data-ttu-id="73ca4-113">Definición</span><span class="sxs-lookup"><span data-stu-id="73ca4-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="73ca4-114">*1*</span><span class="sxs-lookup"><span data-stu-id="73ca4-114">*1*</span></span>|<span data-ttu-id="73ca4-115">MSSQLSERVER es el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73ca4-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="73ca4-116">*2*</span><span class="sxs-lookup"><span data-stu-id="73ca4-116">*2*</span></span>|<span data-ttu-id="73ca4-117">SQLSERVERAGENT es el servicio Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73ca4-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="73ca4-118">*3*</span><span class="sxs-lookup"><span data-stu-id="73ca4-118">*3*</span></span>|<span data-ttu-id="73ca4-119">MSFTESQL es el servicio de motor de búsqueda de texto completo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73ca4-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="73ca4-120">*4*</span><span class="sxs-lookup"><span data-stu-id="73ca4-120">*4*</span></span>|<span data-ttu-id="73ca4-121">MsDtsServer es el servicio [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73ca4-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="73ca4-122">*5*</span><span class="sxs-lookup"><span data-stu-id="73ca4-122">*5*</span></span>|<span data-ttu-id="73ca4-123">MSSQLServerOLAPService es el servicio [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73ca4-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="73ca4-124">*6*</span><span class="sxs-lookup"><span data-stu-id="73ca4-124">*6*</span></span>|<span data-ttu-id="73ca4-125">ReportServer es el servicio [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73ca4-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="73ca4-126">*7*</span><span class="sxs-lookup"><span data-stu-id="73ca4-126">*7*</span></span>|<span data-ttu-id="73ca4-127">SQLBrowser es el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="73ca4-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73ca4-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73ca4-128">See Also</span></span>  
 <span data-ttu-id="73ca4-129">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="73ca4-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
