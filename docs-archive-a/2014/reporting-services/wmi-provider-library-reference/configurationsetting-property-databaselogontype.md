---
title: Propiedad DatabaseLogonType (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonType
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonType property
ms.assetid: 6b592582-4c35-4029-ab86-982fff47d8d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bb5a4149c29fb7532b7140a2616dd856e6db2b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748551"
---
# <a name="databaselogontype-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ba694-102">Propiedad DatabaseLogonType (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="ba694-102">DatabaseLogonType Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ba694-103">Especifica si el servidor de informes usa una cuenta de servicio de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, una cuenta de usuario de Windows o un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para tener acceso a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="ba694-103">Specifies whether the report server uses a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows service account, a Windows user account, or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to access the report server database.</span></span> <span data-ttu-id="ba694-104">Solo lectura.</span><span class="sxs-lookup"><span data-stu-id="ba694-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba694-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba694-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonType As Integer  
```  
  
```csharp  
public int DatabaseLogonType;  
```  
  
## <a name="property-values"></a><span data-ttu-id="ba694-106">Valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="ba694-106">Property Values</span></span>  
 <span data-ttu-id="ba694-107">Un objeto `integer` que representa el tipo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="ba694-107">An `integer` object that represents the login type.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="ba694-108">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba694-108">Example Code</span></span>  
 [<span data-ttu-id="ba694-109">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ba694-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="ba694-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba694-110">Remarks</span></span>  
 <span data-ttu-id="ba694-111">Los valores son:</span><span class="sxs-lookup"><span data-stu-id="ba694-111">Values are:</span></span>  
  
-   <span data-ttu-id="ba694-112">0 para el inicio de sesión de Windows</span><span class="sxs-lookup"><span data-stu-id="ba694-112">0 for Windows login</span></span>  
  
-   <span data-ttu-id="ba694-113">1 para el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba694-113">1 for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login</span></span>  
  
-   <span data-ttu-id="ba694-114">2 para el inicio de sesión como un servicio</span><span class="sxs-lookup"><span data-stu-id="ba694-114">2 to log in as a service</span></span>  
  
 <span data-ttu-id="ba694-115">Si especifica 0 (Windows), debe establecer el valor de la propiedad [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) en una cuenta de usuario de Windows válida correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ba694-115">If you specify 0 (Windows), you must set the value in the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) property to a corresponding a valid Windows user account.</span></span>  
  
 <span data-ttu-id="ba694-116">Si especifica 1 (SQL Server), asegúrese de que el valor de [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) se corresponda con un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] válido.</span><span class="sxs-lookup"><span data-stu-id="ba694-116">If you specify 1 (SQL Server), make sure the value of the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) corresponds to a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="ba694-117">Si especifica 2 (servicio de Windows), el servidor de informes usará una cuenta de [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] y la cuenta de servicio de Windows para tener acceso a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="ba694-117">If you specify 2 (Windows service), the report server uses an [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account and the Windows service account to access the report server database.</span></span> <span data-ttu-id="ba694-118">Se omite la propiedad DatabaseLogonAccount.</span><span class="sxs-lookup"><span data-stu-id="ba694-118">The DatabaseLogonAccount property is ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba694-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba694-119">Requirements</span></span>  
 <span data-ttu-id="ba694-120">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba694-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba694-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba694-121">See Also</span></span>  
 [<span data-ttu-id="ba694-122">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ba694-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
