---
title: Método SetEmailConfiguration (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetEmailConfiguration (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEmailConfiguration method
ms.assetid: b40a2224-2c90-4d32-892f-1fe73a0591ca
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19068d7d7fff8c31c455ef76e8d2c2caa26b743f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748573"
---
# <a name="setemailconfiguration-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="79e37-102">Método SetEmailConfiguration (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="79e37-102">SetEmailConfiguration Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="79e37-103">Configura la extensión de entrega de correo electrónico utilizada por el servidor de informes para enviar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="79e37-103">Configures the e-mail delivery extension used by the report server to send e-mail.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79e37-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79e37-104">Syntax</span></span>  
  
```vb  
Public Sub SetEmailConfiguration(ByVal SendUsingSMTPServer As Boolean, _  
    ByVal SMTPServer As String, ByVal SenderEmailAddress As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetEmailConfiguration (Boolean SendUsingSMTPServer,   
   string SMTPServer, string SenderEmailAddress,   
   out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79e37-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="79e37-105">Parameters</span></span>  
 <span data-ttu-id="79e37-106">*SendUsingSMTPServer*</span><span class="sxs-lookup"><span data-stu-id="79e37-106">*SendUsingSMTPServer*</span></span>  
 <span data-ttu-id="79e37-107">Valor booleano que indica si el servidor utilizará el servidor SMTP para enviar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="79e37-107">A Boolean value indicating whether the server is to use the SMTP server to send email.</span></span> <span data-ttu-id="79e37-108">Este valor solamente se puede establecer en true.</span><span class="sxs-lookup"><span data-stu-id="79e37-108">This value can only be set to true.</span></span> <span data-ttu-id="79e37-109">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="79e37-109">Default value is false.</span></span>  
  
 <span data-ttu-id="79e37-110">*SMTPServer*</span><span class="sxs-lookup"><span data-stu-id="79e37-110">*SMTPServer*</span></span>  
 <span data-ttu-id="79e37-111">Cadena que contiene el nombre o dirección IP de un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="79e37-111">A string containing the name or IP address of an SMTP server.</span></span>  
  
 <span data-ttu-id="79e37-112">*SenderEmailAddress*</span><span class="sxs-lookup"><span data-stu-id="79e37-112">*SenderEmailAddress*</span></span>  
 <span data-ttu-id="79e37-113">Dirección de correo electrónico utilizada en el campo 'De:' para los correos electrónicos enviados desde el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="79e37-113">The e-mail address used in the 'From:' field for e-mails sent from the report server.</span></span>  
  
 <span data-ttu-id="79e37-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="79e37-114">*HRESULT*</span></span>  
 <span data-ttu-id="79e37-115">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="79e37-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79e37-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="79e37-116">Return Value</span></span>  
 <span data-ttu-id="79e37-117">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="79e37-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="79e37-118">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="79e37-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="79e37-119">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="79e37-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79e37-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="79e37-120">Remarks</span></span>  
 <span data-ttu-id="79e37-121">Cuando el parámetro *SendUsingSMTPServer* se establece en `true` , la entrada **SendUsing** del archivo de configuración del servidor de informes se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="79e37-121">When the *SendUsingSMTPServer* parameter is set to `true`, the **SendUsing** entry in the report server configuration file is set to 1.</span></span> <span data-ttu-id="79e37-122">Cuando *SendUsingSMTPServer* se establece en `false` , la entrada **SendUsing** no está configurada.</span><span class="sxs-lookup"><span data-stu-id="79e37-122">When *SendUsingSMTPServer* is set to `false`, the **SendUsing** entry is not configured.</span></span>  
  
 <span data-ttu-id="79e37-123">Este método no proporciona una manera para que los usuarios establezcan la entrada de **SendUsing** en el archivo de configuración del servidor de informes en un valor distinto de 1.</span><span class="sxs-lookup"><span data-stu-id="79e37-123">This method does not provide a way for users to set the **SendUsing** entry in the report server configuration file to a value other than 1.</span></span> <span data-ttu-id="79e37-124">Para configurar el servidor de informes para algo distinto del correo SMTP, debe modificar manualmente el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="79e37-124">To configure the report server for anything other than SMTP mail, you must edit the configuration file manually.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79e37-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79e37-125">Requirements</span></span>  
 <span data-ttu-id="79e37-126">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79e37-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e37-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79e37-127">See Also</span></span>  
 [<span data-ttu-id="79e37-128">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="79e37-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
