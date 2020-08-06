---
title: Propiedad DatabaseLogonAccount (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonAccount
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonAccount property
ms.assetid: 55f2863f-1ac1-4519-b512-e7f11c0ea5ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f9e844ff1d1447bd5abfefad8e82939575c7f47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748556"
---
# <a name="databaselogonaccount-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="1f7e0-102">Propiedad DatabaseLogonAccount (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="1f7e0-102">DatabaseLogonAccount Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="1f7e0-103">Especifica la cuenta de inicio de sesión que el servidor de informes utiliza al conectarse a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="1f7e0-103">Specifies the logon account that the report server uses when connecting to the report server database.</span></span> <span data-ttu-id="1f7e0-104">Solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1f7e0-104">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f7e0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f7e0-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonAccount As String  
```  
  
```csharp  
public string DatabaseLogonAccount;  
```  
  
## <a name="property-values"></a><span data-ttu-id="1f7e0-106">Valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="1f7e0-106">Property Values</span></span>  
 <span data-ttu-id="1f7e0-107">Un objeto `String` que representa el nombre de la cuenta de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="1f7e0-107">A `String` object that represents the logon account name.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="1f7e0-108">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f7e0-108">Example Code</span></span>  
 [<span data-ttu-id="1f7e0-109">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1f7e0-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="1f7e0-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1f7e0-110">Remarks</span></span>  
 <span data-ttu-id="1f7e0-111">Los valores válidos para esta propiedad variarán dependiendo del valor de la propiedad [DatabaseLogonType](configurationsetting-property-databaselogontype.md) .</span><span class="sxs-lookup"><span data-stu-id="1f7e0-111">Valid values for this property will vary depending on the value of the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property.</span></span>  
  
 <span data-ttu-id="1f7e0-112">Esta propiedad se omite si la propiedad [DatabaseLogonType](configurationsetting-property-databaselogontype.md) está establecida en `2 (Service)` .</span><span class="sxs-lookup"><span data-stu-id="1f7e0-112">This property is ignored if the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property is set to `2 (Service)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f7e0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f7e0-113">Requirements</span></span>  
 <span data-ttu-id="1f7e0-114">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f7e0-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f7e0-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f7e0-115">See Also</span></span>  
 [<span data-ttu-id="1f7e0-116">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1f7e0-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
