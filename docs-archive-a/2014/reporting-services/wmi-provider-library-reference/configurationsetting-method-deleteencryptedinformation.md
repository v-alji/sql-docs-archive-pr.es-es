---
title: Método DeleteEncryptedInformation (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptedInformation method
ms.assetid: c14ed187-bdd9-4304-88e3-72072f03c21b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d00dc3e90816cd04c84f124cdc3d25a9ac122bba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671922"
---
# <a name="deleteencryptedinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="c33aa-102">Método DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="c33aa-102">DeleteEncryptedInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="c33aa-103">Elimina la información cifrada de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c33aa-103">Deletes the encrypted information from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c33aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c33aa-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptedInformation(ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptedInformation(out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c33aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c33aa-105">Parameters</span></span>  
 <span data-ttu-id="c33aa-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="c33aa-106">*HRESULT*</span></span>  
 <span data-ttu-id="c33aa-107">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="c33aa-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="c33aa-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="c33aa-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="c33aa-109">[out] Matriz de cadenas que contiene los errores adicionales devueltos por la llamada.</span><span class="sxs-lookup"><span data-stu-id="c33aa-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c33aa-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c33aa-110">Return Value</span></span>  
 <span data-ttu-id="c33aa-111">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="c33aa-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="c33aa-112">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c33aa-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="c33aa-113">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="c33aa-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c33aa-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c33aa-114">Remarks</span></span>  
 <span data-ttu-id="c33aa-115">Cuando se invoca este método, se eliminan los datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c33aa-115">When this method is invoked, the following data is deleted:</span></span>  
  
-   <span data-ttu-id="c33aa-116">La información de origen de datos cifrada, incluso el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="c33aa-116">Data source information that is encrypted, including user name and password.</span></span>  
  
-   <span data-ttu-id="c33aa-117">Los datos de suscripción cifrados utilizando las interfaces de extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="c33aa-117">Subscription data that is encrypted using the delivery extension interfaces.</span></span>  
  
-   <span data-ttu-id="c33aa-118">Toda la información de la tabla de claves en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c33aa-118">All the information from the keys table in the report server database.</span></span>  
  
 <span data-ttu-id="c33aa-119">Una vez invocado este método, el usuario debe inicializar cada equipo que utiliza la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c33aa-119">After this method is invoked, the user must initialize each computer that uses the report server database.</span></span>  
  
 <span data-ttu-id="c33aa-120">Llamar al método DeleteEncryptedInformation no afecta al archivo de configuración del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c33aa-120">Calling the DeleteEncryptedInformation method does not affect the report server configuration file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c33aa-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c33aa-121">Requirements</span></span>  
 <span data-ttu-id="c33aa-122">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c33aa-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c33aa-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c33aa-123">See Also</span></span>  
 [<span data-ttu-id="c33aa-124">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="c33aa-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
