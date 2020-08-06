---
title: Editor del administrador de conexiones HTTP (página proxy) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.proxy.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: e831a830-49a3-49c5-8a31-9731fc4fd12e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f8269dbbeb226ffa3f56c226e1a416d99c1e3f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663594"
---
# <a name="http-connection-manager-editor-proxy-page"></a><span data-ttu-id="387cd-102">Editor del administrador de conexiones HTTP (página Proxy)</span><span class="sxs-lookup"><span data-stu-id="387cd-102">HTTP Connection Manager Editor (Proxy Page)</span></span>
  <span data-ttu-id="387cd-103">Utilice la pestaña **Proxy** del cuadro de diálogo **Editor del administrador de conexiones HTTP** para configurar el Administrador de conexiones HTTP para que utilice un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="387cd-103">Use the **Proxy** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager to use a proxy server.</span></span> <span data-ttu-id="387cd-104">Una conexión HTTP habilita a un paquete para obtener acceso a un servidor web mediante HTTP para enviar o recibir archivos.</span><span class="sxs-lookup"><span data-stu-id="387cd-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span>  
  
 <span data-ttu-id="387cd-105">Para obtener más información acerca del administrador de conexiones HTTP, vea [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="387cd-105">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="387cd-106">Para obtener más información acerca de un escenario común de uso para el Administrador de conexiones HTTP, vea [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="387cd-106">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="387cd-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="387cd-107">Options</span></span>  
 <span data-ttu-id="387cd-108">**Utilizar proxy**</span><span class="sxs-lookup"><span data-stu-id="387cd-108">**Use proxy**</span></span>  
 <span data-ttu-id="387cd-109">Especifique si desea que el Administrador de conexiones HTTP se conecte a través de un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="387cd-109">Specify whether you want the HTTP Connection Manager to connect through a proxy server.</span></span>  
  
 <span data-ttu-id="387cd-110">**Dirección URL del proxy**</span><span class="sxs-lookup"><span data-stu-id="387cd-110">**Proxy URL**</span></span>  
 <span data-ttu-id="387cd-111">Escriba la dirección URL para el servidor de proxy.</span><span class="sxs-lookup"><span data-stu-id="387cd-111">Type the URL for the proxy server.</span></span>  
  
 <span data-ttu-id="387cd-112">**No usar servidor proxy en el equipo local**</span><span class="sxs-lookup"><span data-stu-id="387cd-112">**Bypass proxy on local**</span></span>  
 <span data-ttu-id="387cd-113">Especifique si desea que el Administrador de conexiones HTTP no utilice el servidor proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="387cd-113">Specify whether you want the HTTP Connection Manager to bypass the proxy server for local addresses.</span></span>  
  
 <span data-ttu-id="387cd-114">**Utilizar credenciales**</span><span class="sxs-lookup"><span data-stu-id="387cd-114">**Use credentials**</span></span>  
 <span data-ttu-id="387cd-115">Especifique si desea que el Administrador de conexiones HTTP utilice credenciales de seguridad para el servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="387cd-115">Specify whether you want the HTTP Connection Manager to use security credentials for the proxy server.</span></span>  
  
 <span data-ttu-id="387cd-116">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="387cd-116">**User name**</span></span>  
 <span data-ttu-id="387cd-117">Si el Administrador de conexiones HTTP utiliza credenciales, debe especificar un nombre de usuario, una contraseña y un dominio.</span><span class="sxs-lookup"><span data-stu-id="387cd-117">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="387cd-118">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="387cd-118">**Password**</span></span>  
 <span data-ttu-id="387cd-119">Si el Administrador de conexiones HTTP utiliza credenciales, debe especificar un nombre de usuario, una contraseña y un dominio.</span><span class="sxs-lookup"><span data-stu-id="387cd-119">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="387cd-120">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="387cd-120">**Domain**</span></span>  
 <span data-ttu-id="387cd-121">Si el Administrador de conexiones HTTP utiliza credenciales, debe especificar un nombre de usuario, una contraseña y un dominio.</span><span class="sxs-lookup"><span data-stu-id="387cd-121">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="387cd-122">**Lista de omisión de proxy**</span><span class="sxs-lookup"><span data-stu-id="387cd-122">**Proxy bypass list**</span></span>  
 <span data-ttu-id="387cd-123">Lista de direcciones para la que desea omitir el servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="387cd-123">The list of addresses for which  you want to bypass the proxy server.</span></span>  
  
 <span data-ttu-id="387cd-124">**Add**</span><span class="sxs-lookup"><span data-stu-id="387cd-124">**Add**</span></span>  
 <span data-ttu-id="387cd-125">Escriba una dirección para la que no desee utilizar el servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="387cd-125">Type an address for which you want to bypass the proxy server.</span></span>  
  
 <span data-ttu-id="387cd-126">**Remove**</span><span class="sxs-lookup"><span data-stu-id="387cd-126">**Remove**</span></span>  
 <span data-ttu-id="387cd-127">Seleccione una dirección y quítela haciendo clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="387cd-127">Select an address, and then remove it by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="387cd-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="387cd-128">See Also</span></span>  
 <span data-ttu-id="387cd-129">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="387cd-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="387cd-130">Editor del administrador de conexiones HTTP &#40;página Servidor&#41;</span><span class="sxs-lookup"><span data-stu-id="387cd-130">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-server-page.md)  
  
  
