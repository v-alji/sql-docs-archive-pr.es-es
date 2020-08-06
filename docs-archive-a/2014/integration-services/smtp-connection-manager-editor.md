---
title: Editor del administrador de conexiones SMTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.smtpconnection.f1
helpviewer_keywords:
- SMTP Connection Manager Editor
ms.assetid: 2693de0d-b04d-4325-a856-ce667d2b8aa1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14ed49f64b9faca40f575fc6760a8d25c0d4573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751246"
---
# <a name="smtp-connection-manager-editor"></a><span data-ttu-id="a6661-102">Editor del administrador de conexiones SMTP</span><span class="sxs-lookup"><span data-stu-id="a6661-102">SMTP Connection Manager Editor</span></span>
  <span data-ttu-id="a6661-103">Use el cuadro de diálogo **Editor del administrador de conexiones SMTP** para especificar un servidor de protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="a6661-103">Use the **SMTP Connection Manager Editor** dialog box to specify a Simple Mail Transfer Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="a6661-104">Para obtener más información acerca del administrador de conexiones SMTP, vea [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a6661-104">To learn more about the SMTP connection manager, see [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a6661-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="a6661-105">Options</span></span>  
 <span data-ttu-id="a6661-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a6661-106">**Name**</span></span>  
 <span data-ttu-id="a6661-107">Proporcione un nombre único para el administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="a6661-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="a6661-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a6661-108">**Description**</span></span>  
 <span data-ttu-id="a6661-109">Describa el administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="a6661-109">Describe the connection manager.</span></span> <span data-ttu-id="a6661-110">Como método recomendado, describa el administrador de conexiones desde el punto de vista de su propósito, para que los paquetes estén autodocumentados y sean más fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="a6661-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="a6661-111">**Servidor SMTP**</span><span class="sxs-lookup"><span data-stu-id="a6661-111">**SMTP server**</span></span>  
 <span data-ttu-id="a6661-112">Proporcione el nombre del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="a6661-112">Provide the name of the SMTP server.</span></span>  
  
 <span data-ttu-id="a6661-113">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="a6661-113">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="a6661-114">Seleccione esta opción para enviar correo electrónico mediante un servidor SMTP que utiliza Autenticación de Windows para autenticar el acceso al servidor.</span><span class="sxs-lookup"><span data-stu-id="a6661-114">Select to send mail using an SMTP server that uses Windows Authentication to authenticate access to the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a6661-115">El administrador de conexiones SMTP solo es compatible con la autenticación anónima y la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="a6661-115">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="a6661-116">No admite la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="a6661-116">It does not support basic authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6661-117">Al usar Microsoft Exchange como servidor SMTP, es posible que deba establecer **usar autenticación de Windows** en `True` .</span><span class="sxs-lookup"><span data-stu-id="a6661-117">When using Microsoft Exchange as the SMTP server, you may need to set **Use Windows Authentication** to `True`.</span></span> <span data-ttu-id="a6661-118">Es posible que los servidores Exchange estén configurados para no permitir conexiones SMTP no autenticadas.</span><span class="sxs-lookup"><span data-stu-id="a6661-118">Exchange servers may be configured to disallow unauthenticated SMTP connections.</span></span>  
  
 <span data-ttu-id="a6661-119">**Habilitar capa de sockets seguros (SSL)**</span><span class="sxs-lookup"><span data-stu-id="a6661-119">**Enable Secure Sockets Layer (SSL)**</span></span>  
 <span data-ttu-id="a6661-120">Seleccione esta opción para cifrar comunicación mediante Capa de sockets seguros (SSL) al enviar mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a6661-120">Select to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6661-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6661-121">See Also</span></span>  
 [<span data-ttu-id="a6661-122">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="a6661-122">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
