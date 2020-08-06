---
title: Método SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseQueryTimeout method
ms.assetid: bd2809e5-7848-45b3-a502-b04fc698b646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ab6b5bf27eca5e9d6d083d03af48c0ab71b4dd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748571"
---
# <a name="setdatabasequerytimeout-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="1e567-102">Método SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="1e567-102">SetDatabaseQueryTimeout Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="1e567-103">Especifica el valor de tiempo de espera predeterminado para las consultas de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="1e567-103">Specifies the default time-out value for report server database queries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e567-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e567-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseQueryTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseQueryTimeout (Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e567-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e567-105">Parameters</span></span>  
 <span data-ttu-id="1e567-106">*LogonTimeout*</span><span class="sxs-lookup"><span data-stu-id="1e567-106">*LogonTimeout*</span></span>  
 <span data-ttu-id="1e567-107">El valor de tiempo de espera predeterminado, en segundos, para las consultas de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="1e567-107">The default timeout value, in seconds, for report server database queries.</span></span>  
  
 <span data-ttu-id="1e567-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="1e567-108">*HRESULT*</span></span>  
 <span data-ttu-id="1e567-109">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="1e567-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e567-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1e567-110">Return Value</span></span>  
 <span data-ttu-id="1e567-111">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="1e567-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="1e567-112">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e567-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="1e567-113">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="1e567-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e567-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e567-114">Requirements</span></span>  
 <span data-ttu-id="1e567-115">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e567-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e567-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e567-116">See Also</span></span>  
 [<span data-ttu-id="1e567-117">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1e567-117">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
