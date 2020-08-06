---
title: Editor del administrador de conexiones HTTP (página servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.server.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: 774778a0-ece6-4971-b93f-b121d8fc1fc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2349766b11b28ff258496dc966d554d49c7657b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663589"
---
# <a name="http-connection-manager-editor-server-page"></a><span data-ttu-id="b8eab-102">Editor del administrador de conexiones HTTP (página Servidor)</span><span class="sxs-lookup"><span data-stu-id="b8eab-102">HTTP Connection Manager Editor (Server Page)</span></span>
  <span data-ttu-id="b8eab-103">Utilice la pestaña **Servidor** del cuadro de diálogo **Editor del administrador de conexiones HTTP** para configurar el Administrador de conexiones HTTP especificando propiedades como la dirección URL y las credenciales de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b8eab-103">Use the **Server** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager by specifying properties such as the URL and security credentials.</span></span> <span data-ttu-id="b8eab-104">Una conexión HTTP habilita a un paquete para obtener acceso a un servidor web mediante HTTP para enviar o recibir archivos.</span><span class="sxs-lookup"><span data-stu-id="b8eab-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="b8eab-105">Después de configurar el Administrador de conexiones HTTP, también puede probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="b8eab-105">After configuring the HTTP Connection Manager, you can also test the connection.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b8eab-106">El administrador de conexiones HTTP solo es compatible con la autenticación anónima y la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="b8eab-106">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="b8eab-107">No es compatible con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="b8eab-107">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="b8eab-108">Para obtener más información acerca del administrador de conexiones HTTP, vea [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b8eab-108">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="b8eab-109">Para obtener más información acerca de un escenario común de uso para el Administrador de conexiones HTTP, vea [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="b8eab-109">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b8eab-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="b8eab-110">Options</span></span>  
 <span data-ttu-id="b8eab-111">**Dirección URL del servidor**</span><span class="sxs-lookup"><span data-stu-id="b8eab-111">**Server URL**</span></span>  
 <span data-ttu-id="b8eab-112">Escriba la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="b8eab-112">Type the URL for the server.</span></span>  
  
 <span data-ttu-id="b8eab-113">Si piensa utilizar el botón **Descargar WSDL** de la página **General** del **Editor de la tarea Servicio web** para descargar un archivo WSDL, escriba la dirección URL del archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="b8eab-113">If you plan to use the **Download WSDL** button on the **General** page of the **Web Service Task Editor** to download a WSDL file, type the URL for the WSDL file.</span></span> <span data-ttu-id="b8eab-114">Esta dirección URL finaliza con"?wsdl".</span><span class="sxs-lookup"><span data-stu-id="b8eab-114">This URL ends with "?wsdl".</span></span>  
  
 <span data-ttu-id="b8eab-115">**Utilizar credenciales**</span><span class="sxs-lookup"><span data-stu-id="b8eab-115">**Use credentials**</span></span>  
 <span data-ttu-id="b8eab-116">Especifique si desea que el Administrador de conexiones HTTP utilice las credenciales de seguridad del usuario para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="b8eab-116">Specify whether you want the HTTP Connection Manager to use the user's security credentials for authentication.</span></span>  
  
 <span data-ttu-id="b8eab-117">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="b8eab-117">**User name**</span></span>  
 <span data-ttu-id="b8eab-118">Si el Administrador de conexiones HTTP utiliza credenciales, debe especificar un nombre de usuario, una contraseña y un dominio.</span><span class="sxs-lookup"><span data-stu-id="b8eab-118">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="b8eab-119">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="b8eab-119">**Password**</span></span>  
 <span data-ttu-id="b8eab-120">Si el Administrador de conexiones HTTP utiliza credenciales, debe especificar un nombre de usuario, una contraseña y un dominio.</span><span class="sxs-lookup"><span data-stu-id="b8eab-120">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="b8eab-121">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="b8eab-121">**Domain**</span></span>  
 <span data-ttu-id="b8eab-122">Si el Administrador de conexiones HTTP utiliza credenciales, debe especificar un nombre de usuario, una contraseña y un dominio.</span><span class="sxs-lookup"><span data-stu-id="b8eab-122">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="b8eab-123">**Utilizar certificado de cliente**</span><span class="sxs-lookup"><span data-stu-id="b8eab-123">**Use client certificate**</span></span>  
 <span data-ttu-id="b8eab-124">Especifique si desea que el Administrador de conexiones HTTP utilice un certificado de cliente para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="b8eab-124">Specify whether you want the HTTP Connection Manager to use a client certificate for authentication.</span></span>  
  
 <span data-ttu-id="b8eab-125">**Certificate**</span><span class="sxs-lookup"><span data-stu-id="b8eab-125">**Certificate**</span></span>  
 <span data-ttu-id="b8eab-126">Seleccione un certificado de la lista mediante el cuadro de diálogo **Seleccionar certificado** .</span><span class="sxs-lookup"><span data-stu-id="b8eab-126">Select a certificate from the list by using the **Select Certificate** dialog box.</span></span> <span data-ttu-id="b8eab-127">El cuadro de texto muestra el nombre asociado con este certificado.</span><span class="sxs-lookup"><span data-stu-id="b8eab-127">The text box displays the name associated with this certificate.</span></span>  
  
 <span data-ttu-id="b8eab-128">**Tiempo de espera (en segundos)**</span><span class="sxs-lookup"><span data-stu-id="b8eab-128">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="b8eab-129">Indique un tiempo de espera para conectar con el servidor web.</span><span class="sxs-lookup"><span data-stu-id="b8eab-129">Provide a time-out for connecting to the Web server.</span></span> <span data-ttu-id="b8eab-130">El valor predeterminado de esta propiedad es 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="b8eab-130">The default value of this property is 30 seconds.</span></span>  
  
 <span data-ttu-id="b8eab-131">**Tamaño del fragmento (en KB)**</span><span class="sxs-lookup"><span data-stu-id="b8eab-131">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="b8eab-132">Indique un tamaño de fragmento para escribir datos.</span><span class="sxs-lookup"><span data-stu-id="b8eab-132">Provide a chunk size for writing data.</span></span>  
  
 <span data-ttu-id="b8eab-133">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="b8eab-133">**Test Connection**</span></span>  
 <span data-ttu-id="b8eab-134">Después de configurar el Administrador de conexiones HTTP, haga clic en **Probar conexión**para confirmar que la conexión es viable.</span><span class="sxs-lookup"><span data-stu-id="b8eab-134">After configuring the HTTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8eab-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8eab-135">See Also</span></span>  
 <span data-ttu-id="b8eab-136">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b8eab-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="b8eab-137">Editor del administrador de conexiones HTTP &#40;página Proxy&#41;</span><span class="sxs-lookup"><span data-stu-id="b8eab-137">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-proxy-page.md)  
  
  
